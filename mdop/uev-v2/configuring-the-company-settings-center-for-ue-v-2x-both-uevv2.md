---
title: UE-V 2. x 用の会社設定センターを構成する
description: UE-V 2. x 用の会社設定センターを構成する
author: dansimp
ms.assetid: 48fadb0a-c0dc-4287-9474-f94ce1417003
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0226b3c156a6d6ca39b0214de8acf0c5990db349
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823294"
---
# UE-V 2. x 用の会社設定センターを構成する


Microsoft User Experience Virtualization (UE-V) 2.0、2.1、2.1 SP1 には、ユーザーが同期の設定を管理するために役立つ、会社設定センターの新しいアプリケーションが含まれています。 会社設定センターは、UE-V Agent を使用してインストールされます。 ユーザーは、コントロールパネルの [**スタート**] メニューまたは**スタート**画面、および ue-v 通知領域のアイコンを使って、会社の設定センターにアクセスできます。 [会社設定センター] には、同期されている設定が表示され、ユーザーは UE-V の同期状態を確認できます。 ユーザーは、[会社設定センター] を使って、設定をコンピューター間で同期するアプリケーションまたは Windows 機能を選ぶことができます。 [**今すぐ同期**] ボタンをクリックして、すべての設定をすぐに同期することもできます。 管理者は、会社設定センターでサポートのリンクを含めることもできます。

## 会社設定センターについて


[会社設定センター] デスクトップアプリケーションは、ユーザーに UE-V 設定の同期に関する情報を提供します。 会社設定センターには、さまざまな方法でアクセスできます。

-   通知領域アイコン–**トレイアイコン**のグループポリシー設定または Windows PowerShell 構成が有効になっていると、通知領域に ue-v アイコンが表示されます。 [UE-V] アイコンをクリックして、会社の設定センターを開きます。

    **注** 通知領域アイコンは、次の設定を使用して無効にすることができます。

    -   グループポリシーの設定: `Policy Tray Icon`

    -   Windows PowerShell コマンドレット: `TrayIconEnabled`

    -   SystemCenter2012 ConfigurationManager の UE-V 構成パックの構成項目: `Tray icon enabled`

     

-   コントロールパネルアプリケーション–コントロールパネルで、[**デスクトップのカスタマイズ**] を参照し、[**会社設定センター**] をクリックします。

-   最初の使用通知–無効の場合、UE-V Agent は、コンピューターでの初回実行時に設定が同期されるようにユーザーに通知します。 [通知] ダイアログボックスをクリックして、[会社の設定センター] を開きます。

-   **スタート**画面または [**スタート**] メニューには、会社設定センターへのリンクが含まれています。 [会社の設定] センターを検索すると、アプリケーションが検索されます。

## 会社設定センターでのサポートリンクの設定


[会社設定センター] には、ユーザーがクリックして UE-V 設定の同期の問題に関するサポートを受けることができるハイパーリンクを含めることができます。 このリンクでは、web ページの http://やメールの mailto://など、有効な URL プロトコルを開くことができます。 [サポート] リンクは、グループポリシー、Windows PowerShell、または System Center 2012 Configuration Manager UE-V 構成パックを使用して構成できます。

**会社設定センターのサポートリンクを構成する方法**

1.  優先する管理ツールを開きます。

    -   **グループポリシー** : [MDOP 管理用テンプレート](https://go.microsoft.com/fwlink/p/?LinkId=393941)から UE-V 2 用の ADMX テンプレートをダウンロードしていない場合は、ダウンロードします。

    -   **Windows powershell** – ue-v エージェントがインストールされているコンピューターでは、 **Windows powershell**を開きます。 Windows PowerShell を使用した UE-V の管理について詳しくは、「 [Windows powershell と WMI を使った ue-v 2. x の管理](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)」をご覧ください。

    -   **Microsoft User Experience Virtualization (ue-v) 向け System Center 2012 構成パック**– Ue-v 構成パックをインポートし、構成パックのドキュメントに従って構成項目を作成します。 UE-V 構成パックの詳細については、「 [System Center Configuration Manager 2012 で ue-v を構成する](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)」を参照してください。

2.  次のポリシーの設定を編集します。

    -   [**お問い合わせ先] リンクテキスト**-この設定では、[会社の設定] センターの [連絡先に連絡する] URL ハイパーリンクのテキストを指定します。 この設定を有効にした場合、[会社設定センター] の URL へのリンクに、指定されたテキストが表示されます。

        -   グループポリシーの設定: `Contact IT Link Text`

        -   Windows PowerShell コマンドレット: `ContactITDescription`

        -   構成パック構成項目: `IT contact descriptive text`

    -   [ **IT URL に連絡**する]-この設定では、web ページの http://やメールの mailto://などの有効な URL プロトコルで、会社設定センターの [連絡先 IT] リンクの url を指定します。

        -   グループポリシーの設定: `Contact IT URL`

        -   Windows PowerShell コマンドレット: `ContactITUrl`

        -   構成パック構成項目: `IT contact URL`

3.  管理ツールを使用して、ユーザーのコンピューターに設定を展開します。






 

 





