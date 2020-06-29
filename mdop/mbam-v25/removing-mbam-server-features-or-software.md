---
title: MBAM サーバーの機能またはソフトウェアの削除
description: MBAM サーバーの機能またはソフトウェアの削除
author: dansimp
ms.assetid: 5212ba3f-124d-43c5-824a-608e9a192e86
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2e6e57c3d2a62a4e01242ade7a82a7bfa551da83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824977"
---
# MBAM サーバーの機能またはソフトウェアの削除


次の手順では、Microsoft BitLocker の管理と監視 (MBAM) からソフトウェアと機能を削除する方法について説明します。 MBAM サーバー機能を削除した場合は、MBAM サーバーソフトウェアではなく、構成された機能のみがサーバーから削除されます。 MBAM サーバーソフトウェアを削除すると、そのサーバー上で構成したソフトウェアと MBAM サーバー機能は削除されます。

**注** データが誤って削除されるのを防ぐため、MBAM にはデータベースを削除するメカニズムはありません。この操作は手動で行う必要があります。

 

## <a href="" id="bkmk-removeserverfeatures"></a>MBAM サーバー機能の削除


以下のいずれかの方法を使用して、設定済みの MBAM サーバー機能を削除できます。

-   MBAM サーバー構成ウィザード

-   Windows PowerShell コマンドレット

### MBAM サーバー構成ウィザードを使用して機能を削除する

次の手順に従って、MBAM サーバー構成ウィザードを使用して、構成済みの MBAM サーバー機能をサーバーから削除します。

**ウィザードを使用して MBAM 機能を削除するには**

1.  機能を削除するサーバーで、[ **Mbam Server 構成**] を選択して、構成ウィザードを開きます。

2.  [**機能の削除**] をクリックし、削除する機能を選択して、[**次へ**] をクリックします。 [**概要**] ページには、削除するために選択した機能が表示されます。

3.  機能の削除を開始するには、[**削除**] をクリックし、[**閉じる**] をクリックします。

### Windows PowerShell を使用して機能を削除する

Windows PowerShell コマンドレットを使用して、MBAM サーバー機能を削除する一般的なガイドとして、次の手順を使用します。

**Windows PowerShell を使用して MBAM 機能を削除するには**

1.  機能を削除するには、「Windows PowerShell を使用して Windows PowerShell を使用するための前提条件を確認する」を参照して、 [MBAM 2.5 サーバー機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)するを参照してください。

2.  次のコマンドレットを使用して、MBAM サーバー機能を削除します。

    -   無効化-MbamReport

    -   Disable-MbamWebApplication

    -   Disable-MbamCMIntegration

    Windows powershell コマンドレットに関するヘルプを表示するには、「 **get-ヘルプ**」 &lt; *コマンドレット*を入力する &gt; か、mbam windows powershell コマンドレットの[windows powershell ページで Microsoft デスクトップ最適化パックオートメーション](https://go.microsoft.com/fwlink/?LinkId=393498)を参照してください。

## MBAM サーバーソフトウェアの削除


次の手順を使用して、MBAM サーバーソフトウェアと、そのサーバーに構成した MBAM サーバー機能を削除します。

**MBAM サーバーソフトウェアを削除するには**

1.  MBAM サーバーソフトウェアをアンインストールするサーバーで**MBAMserversetup.exe**を実行して、Microsoft BitLocker の管理と監視のセットアップウィザードを開始します。

2.  [**アンインストール**] を選択し、残りの指示に従って Mbam サーバーソフトウェアのアンインストールプロセスを完了します。



## 関連トピック


[MBAM 2.5 の展開](deploying-mbam-25.md)

 

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。



