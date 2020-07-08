---
title: UE-V の構成方法の計画
description: UE-V の構成方法の計画
author: dansimp
ms.assetid: 57bce7ab-1be5-434b-9ee5-c96026bbe010
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4894644d72392ae984d0de290bf634e137d5b85e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827094"
---
# UE-V の構成方法の計画


Microsoft User Experience Virtualization (UE-V) の構成によって、設定が企業全体でどのように同期されるかが決まります。 このトピックでは、お客様のビジネス要件に最も適した構成計画を策定するための UE-V 構成の作成方法について説明します。

## UE-V の構成方法


使用している構成方法によっては、エージェントのインストールの前、最中、またはインストール後に UE-V を構成できます。

**グループポリシー:** 既存のグループポリシーインフラストラクチャを使用して、ue-v エージェントの展開前または後の ue-v の構成を行うことができます。 UE-V は、ue-v Agent の一般的な構成オプションの一元管理を有効にし、ue-v の同期を構成するための設定も含まれています。 グループポリシーを使用するネットワーク環境では、エージェントの展開を見越して UE-V を事前に構成することができます。

[グループ ポリシー オブジェクトを使用した UE-V の構成](configuring-ue-v-with-group-policy-objects.md)

[UE-V グループ ポリシー ADMX テンプレートのインストール](installing-the-ue-v-group-policy-admx-templates.md)

**コマンドラインまたはバッチスクリプトのインストール:** ue-v Agent の展開で使用されるパラメーターによって、多数の ue-v 設定を構成できます。 System Center Configuration Manager などの電子ソフトウェア配布システムでは、UE-V Agent ソフトウェアの展開とインストール時にこれらのパラメーターを使ってクライアントを構成します。 インストールパラメーターの一覧とインストールスクリプトの例については、「 [Ue-v agent の展開](deploying-the-ue-v-agent.md)」をご覧ください。

**Powershell と wmi:** ue-v エージェントがインストールされた後に、powershell または wmi を使用してスクリプトコマンドを使用して構成を変更することができます。 PowerShell コマンドと WMI コマンドの一覧については、「 [ue-v 1.0 エージェントと powershell と wmi を使ったパッケージの管理](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)」を参照してください。

**レジストリ設定を編集します。** UE-V の設定はレジストリに格納され、レジストリ設定を変更できる任意のツール (RegEdit など) を使用して変更できます。

**注** レジストリを変更すると、データが失われるか、コンピューターが応答しなくなることがあります。 他の構成方法を使用することをお勧めします。

 

### UE-V 構成の設定

UE-V の構成設定の例を次に示します。

-   [**記憶域のパスの設定]:** ue-v の設定を保存するファイル共有の場所を指定します。

-   **設定テンプレートカタログのパス:** 新しい設定場所テンプレートがチェックされた場所を定義する汎用名前付け規則 (UNC) パスを指定します。

-   **Microsoft テンプレートの登録:** インストール時に既定の Microsoft テンプレートを登録するかどうかを指定します。

-   **同期方法:** Windows オフラインファイル機能がオフラインサポートに使用されるかどうかを指定します。

-   **同期タイムアウト:** 設定の保存場所からユーザー設定を取得するときにコンピューターがタイムアウトするまでの時間 (ミリ秒単位) を指定します。

-   **同期有効:** ue-v 設定の同期を有効にするか無効にするかを指定します。

-   [**パッケージの最大サイズ]:** ue-v agent が警告を報告する設定パッケージファイルのしきい値のサイズ (バイト単位) を指定します。

## 関連トピック


[UE-V 1.0 の計画](planning-for-ue-v-10.md)

[UE-V の構成計画](planning-for-ue-v-configuration.md)

 

 





