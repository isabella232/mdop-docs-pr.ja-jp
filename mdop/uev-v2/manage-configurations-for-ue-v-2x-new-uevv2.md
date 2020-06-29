---
title: UE-V 2.x の構成を管理する
description: UE-V 2.x の構成を管理する
author: dansimp
ms.assetid: e2332eca-a9cd-4446-8f7c-d17058b03466
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 20d5d2942dbd805a4054a9431b237c821cbb70fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827384"
---
# UE-V 2.x の構成を管理する


Microsoft User Experience Virtualization (UE-V) 2.0、2.1、または 2.1 SP1 のライフサイクルでは、UE-V Agent の構成を管理し、設定パッケージファイルなどのリソースの保存場所を管理する必要があります。 ユーザーが UE-V を操作する方法を定義するために、会社設定センターの構成など、他のタスクを実行することが必要な場合があります。 次のトピックでは、これらの UE-V リソースを管理するためのガイダンスを提供します。

## グループポリシーオブジェクトを使用して UE-V を構成する


グループポリシーオブジェクトを使用して、UE-V によるコンピューター上の設定の同期方法を定義する設定を変更できます。

[グループポリシーオブジェクトを使用して UE-V 2. x を構成する](configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md)

## System Center Configuration Manager 2012 で UE-V を構成する


SystemCenter2012 ConfigurationManager を使用して、ue-v Agent を管理するには、UE-V 2 構成パックを使用します。

[System Center Configuration Manager 2012 で UE-V を構成する](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)

## PowerShell と WMI を使った UE-V 2. x の管理


UE-V は、Windows PowerShell コマンドレットを提供します。これは、管理者がさまざまな UE-V タスクを実行するときに役立ちます。

[Windows PowerShell と WMI を使用した UE-V 2. x の管理](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

## UE-V 2. x 用の会社設定センターを構成する


UE-V Agent を使用してインストールされた会社設定センターを構成すると、ユーザーが UE-V を操作する方法を定義できます。

[UE-V 2. x 用の会社設定センターを構成する](configuring-the-company-settings-center-for-ue-v-2x-both-uevv2.md)

## UE-V 2. x の構成設定の例


UE-V 構成の設定の例をいくつか紹介します。

-   **設定の記憶域のパス:** UE-V の設定を保存するファイル共有の場所を指定します。

-   **設定テンプレートカタログのパス:** 新しい設定場所テンプレートがチェックされた場所を定義する汎用名前付け規則 (UNC) パスを指定します。

-   **Microsoft テンプレートの登録:** インストール時に既定の Microsoft テンプレートを登録する必要があるかどうかを指定します。

-   **同期方法:** UE-V で同期プロバイダーを使うか、"none" を使うかを指定します。 "SyncProvider" は、ネットワークに接続されていないコンピューターをサポートします。 [なし] は、コンピューターが常にネットワークに接続されているときに適用されます。 Sync メソッドの詳細については、「 [ue-v の同期メソッド](sync-methods-for-ue-v-2x-both-uevv2.md)」を参照してください。

-   **同期タイムアウト:** コンピューターが設定の保存場所からユーザー設定を取得したときにタイムアウトするまでの時間 (ミリ秒単位) を指定します。

-   **同期有効:** UE-V 設定の同期を有効または無効にするかどうかを指定します。

-   **最大パッケージサイズ:** UE-V Agent が警告を報告する設定パッケージファイルのしきい値のサイズ (バイト単位) を指定します。

-   **Windows アプリの設定を同期しない:** UE-V で Windows アプリを同期させないことを指定します。

-   **最初の使用通知を有効/無効**にする:ユーザーのコンピューターで UE-V Agent を初めて実行するときに、UE-V がダイアログボックスを表示するかどうかを指定します。

-   **トレイアイコンを有効/無効にする:** 通知領域のアイコンと、関連付けられた通知を表示するかどうかを指定します。 このアイコンは、会社設定センターへのリンクを提供します。

-   **ユーザー設定の連絡先のハイパーリンク:** 会社設定センターの [**連絡先に連絡**する] ハイパーリンクのパス、テキスト、説明を定義します。






## 関連トピック


[UE-V 2. x の管理](administering-ue-v-2x-new-uevv2.md)

[UE-V 2.x の必要な機能を展開する](deploy-required-features-for-ue-v-2x-new-uevv2.md)

[カスタムアプリケーションの UE-V 2. x の展開](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

 

 





