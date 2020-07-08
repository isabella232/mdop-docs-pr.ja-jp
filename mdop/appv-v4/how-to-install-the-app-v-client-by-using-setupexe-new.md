---
title: setup.exe を使用して App-V Client をインストールする方法
description: setup.exe を使用して App-V Client をインストールする方法
author: dansimp
ms.assetid: 106a5d97-b5f6-4a16-bf52-a84f4d558c74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60f79a2d2f74848ab121ba13cdf8c215088d54db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817337"
---
# setup.exe を使用して App-V Client をインストールする方法


このトピックでは、setup.exe プログラムを使用して App-v クライアントをインストールする方法について説明します。 setup.exe プログラムを使用して App-v クライアントをインストールすると、必要なソフトウェアがインストーラーによって決定され、クライアントをインストールする前に自動的にインストールされます。

**Setup.exe を使用して Application Virtualization クライアントをインストールするには**

1.  コンピューターの管理者権限を持つアカウントでログオンしていることを確認します。

2.  コマンドプロンプトウィンドウを開き、ディレクトリをセットアップファイルが格納されているフォルダーに変更します。 バージョン4.6 以降バージョンの App-v クライアントをインストールする場合、コンピューターのオペレーティングシステム32ビットまたは64ビットに適切なインストーラーを使用する必要があります。 インストールが失敗し、誤ったインストーラーを使用した場合にエラーメッセージが表示されます。

3.  コマンドプロンプトで、install コマンド文字列を入力します。 または、コマンドファイルを作成して、コマンドプロンプトから実行することもできます。 また、VBScript や Windows PowerShell などのスクリプト言語を使ってコマンドを実行することもできます。

4.  次のコマンドラインの例は、いくつかのオプションのパラメーターを使って setup.exe を使う方法を示しています。 これらのパラメーターの詳細については、「 [Application Virtualization クライアントインストーラーのコマンドラインパラメーター](application-virtualization-client-installer-command-line-parameters.md)」を参照してください。

    **"setup.exe"/s/v "/qn SWICACHESIZE = \ \" 10240 \ "System\\" SWIPUBSVRTYPE = \ \ "= \ \" = \ \ "SWIPUBSVRHOST = \ \" PRODSYS\\ "SWIPUBSVRPORT = \ \" SWIPUBSVRDISPLAY "SWIPUBSVRPATH = \ \"/AppVirt/appsntype.xml \ \ "SWIPUBSVRREFRESH = \ \" = \ \ "D:\\AppVirt\\Global\\" SWIUSERDATA = \ \ ""%\\Windows\\Application "Client\\ = \ \" # \ \ "# \ \" @ "**

    **重要**  
    -   "**/V**" セクションに表示される引用符は、特殊文字として扱われ、前に "" が付いて入力されている必要があり **\\** ます。 引用符は、値にスペースが含まれている場合にのみ必要です。ただし、一貫性を保つため、前の例のすべてのインスタンスは引用符で囲まれています。

    -   " **%** **% HomeDrive%**" の "" 文字の前には "" エスケープ文字を指定する必要があり **^** ます。 そうしないと、Windows コマンドシェルによって、インストールを実行しているユーザーの値が設定されます。

    -   この設定をサイレントインストールするには、 **InstallShield**スイッチ **/s**と **/qn**が必要です。 **/Qn**スイッチ**は、スペース**を入れずに引用符で囲む必要があります。

    -   **SWIGLOBALDATA**の値で指定したフォルダーは、既に存在している必要があります。

     

5.  インストールが完了したら、Microsoft Update スキャンを実行して、最新の更新プログラムがインストールされていることを確認することをお勧めします。

## 関連トピック


[コマンド ラインを使用してクライアントをインストールする方法](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





