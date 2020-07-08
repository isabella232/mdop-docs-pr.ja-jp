---
title: MED-V に影響を与えるネットワークの変更の検出
description: MED-V に影響を与えるネットワークの変更の検出
author: dansimp
ms.assetid: fd29b95a-cda2-464d-b86d-50b6bd64b4ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5f43c30dee9ef8e06a7ae226849a4f21e83257c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823374"
---
# MED-V に影響を与えるネットワークの変更の検出


Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 ソリューションを使用すると、MED-V ワークスペースの展開後に発生する可能性のある特定のネットワーク変更を検出し、MED-V に影響を与える可能性のある特定のネットワーク変更を検出するように環境を構成できます。

この機能には、ゲストオペレーティングシステムで実行されているコンポーネントが含まれており、ホストコンピューターでのネットワーク構成の変更について通知されます。 これにより、ゲストで実行されている Microsoft 以外の ESD または他のアプリケーションが、ホストの ESD またはアプリケーションで解決されるのと同じネットワークエンドポイントに解決することができます。

**注** この機能は、仮想マシンがネットワークアドレス変換 (NAT) モード用に構成されている場合にのみ使用できます。 仮想マシンがブリッジモードに構成されている場合、変更のインジケーターは生成されません。

 

このセクションでは、MED-V に影響を与える可能性があるネットワークの変更を監視する際に役立つ情報と手順について説明します。

## MED-V のネットワーク変更を検出するには


MED-V のワークスペースを展開した後、次のタスクを事前に構成することで、特定のネットワーク構成の変更を監視できます。

1. 監視するネットワーク構成の変更を検索する管理オブジェクト形式 (MOF) ファイルを作成します。 次のコードは、作成できる MOF ファイルの例を示しています。

   ``` syntax
   #pragma namespace ("\\\\.\\root\\ccm\\NetworkConfig")

   class CCM_IPConfig
   {
       [NotNull: ToInstance ToSubClass] uint32 AddressFamily; // AF_INET, AF_INET6
       [Key, NotNull: ToInstance ToSubClass] string IPAddress; // IPv4 or IPv6 address
       [NotNull: ToInstance ToSubClass] string SubnetMask; // IPv4 subnet mask
   };

   class CCM_NetworkAdapter
   {
       [Key, NotNull: ToInstance ToSubClass] string Name;
       [NotNull: ToInstance ToSubClass] uint32 DHCPEnabled = 0; 
       [NotNull: ToInstance ToSubClass] uint32 Quarantined = 0; // To check if it is quarantined.
       CCM_IPConfig IPConfigInfo[];
   };

   [singleton]
   class CCM_NetworkAdapters
   {
       [NotNull: ToInstance ToSubClass] String ProviderName; // MED-V or other provider
       CCM_NetworkAdapter AdaptersInfo[];
   };
   ```

2. MOF ファイルをコンパイルします。

3. ゲストに MOF ファイルをインストールします。

MOF ファイルをインストールしたら、 **CCM \ _NetworkAdapters**クラスの Windows Management INSTRUMENTATION (WMI) 作成イベント、変更イベント、削除イベントにサブスクライブするイベントサブスクリプションを作成できます。 これにより、ホストに次の変更が検出されます。

IP アドレスやネットワークアダプターの変更など、ネットワークの構成が変更されているかどうかを確認します。

ネットワークが利用可能かどうか、または利用できませんか?

ネットワーク設定がブリッジモードから NAT モードに変更されましたか?

ネットワーク設定が NAT モードからブリッジモードに変更されましたか?

ホスト上の MED-V コンポーネントによって、ネットワークが監視され、変更のゲストが通知されます。 ゲストのコンポーネントによって、これらの変更について MED-V ワークスペースを監視する WMI インスタンスが作成されます。

作成したイベントサブスクリプションは、1つ以上のネットワーク変更 (作成、変更、または削除) が発生したときに、WMI システム経由で通知を提供します。

## 関連トピック


[MED-V ワークスペースを監視する](monitor-med-v-workspaces.md)

[MED-V ワークスペースの設定を管理する](manage-med-v-workspace-settings.md)

 

 





