---
title: APP-V Management Server または Streaming Server をサポートするための証明書の構成
description: APP-V Management Server または Streaming Server をサポートするための証明書の構成
author: dansimp
ms.assetid: 2f24e550-585e-4b7e-b486-22a3f181f543
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e537244b24d7303af550b3ced8286ba2680009e7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821897"
---
# APP-V Management Server または Streaming Server をサポートするための証明書の構成


証明書のプロビジョニングプロセスを完了して、App-v のインストールをサポートするための秘密キーのアクセス許可を変更したら、管理サーバーまたはストリーミングサーバーのセットアップを起動できます。 セットアップ中に、セットアッププログラムを実行する前に証明書がプロビジョニングされた場合、ウィザードによって [**接続セキュリティモード**] 画面に証明書が表示され、既定では [強化された**セキュリティを使用する**] チェックボックスがオンになっています。

**注** このサーバーに対して複数の証明書がプロビジョニングされている場合は、App-v 用に構成された証明書を選びます。

 

**重要** バージョン4.2 からバージョン4.5 にアップグレードする場合、セットアップには強化された**セキュリティを使用**するオプションがあります。ただし、このオプションを選ぶと、RTSP 経由のストリーミングが無効になりません。 インストール後に RTSP を無効にするには、管理コンソールを使用する必要があります。

 

サービスがクライアント通信に使用する TCP ポートを選択します。 既定のポートは TCP 322 です。ただし、環境のポートをカスタムポートに変更することはできます。

ウィザードの残りの手順は、強化された**セキュリティ**機能を使わずに、app-v 管理またはストリーミングサーバーを展開している場合と同じです。

## NLB 環境用の証明書を構成する


大企業をサポートするために、多くの場合、管理サーバーはネットワーク負荷分散 (NLB) クラスターに配置され、多数の接続をサポートします。 これには、1つの管理サーバーとして表示される少なくとも2つの管理サーバーが必要です。 複数の管理サーバーで NLB クラスターを使用している環境では、NLB クラスターに使用される証明書の詳細構成が必要です。

App-v 証明書は、Windows Server2003 を実行しているコンピューターで構成されている証明機関 (CA) に送信されます。 SAN では、NLB クラスターを構成する最大32のサーバーが存在する可能性があるため、実際のコンピューター名とは異なるドメインネームシステム (DNS) 名を使って、特定の管理サーバー NLB クラスターホスト名に接続できます。

この構成は、NLB クラスターを使用する場合にのみ必要です。 クライアントがサーバーに接続すると、個々のサーバーの FQDN ではなく、NLB クラスターの完全修飾ドメイン名 (FQDN) を使って接続されます。 クラスターのサーバーノードの FQDN で SAN プロパティを追加しないと、証明書の共通名がサーバー名と一致しないため、すべてのクライアント接続が拒否されます。

SAN 属性を使った証明書の構成の詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=133228> 。

## 関連トピック


[安全なストリーミングをサポートするための証明書の構成](configuring-certificates-to-support-secure-streaming.md)

[Management Server または Streaming Server をサポートするために秘密キーのアクセス許可を変更する方法](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)

 

 





