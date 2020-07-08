---
title: MED-V ワークスペース パッケージ ツールを使用して URL のリダイレクトを管理する方法
description: MED-V ワークスペース パッケージ ツールを使用して URL のリダイレクトを管理する方法
author: dansimp
ms.assetid: 1a8d25af-479f-42d3-bf5f-c7fd974bbf8c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 88167923e3bd47f2a3b0b3ada5e818715740dbe3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824817"
---
# MED-V ワークスペース パッケージ ツールを使用して URL のリダイレクトを管理する方法


MED-V ワークスペースパッケージャーを使って、MED-V ワークスペースの URL リダイレクションを管理することができます。

**MED-V ワークスペースで web アドレスリダイレクションを管理するには**

1.  **Med-v ワークスペースのパッケージャー**を開くには、 **[スタート**]、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v workspace パッケージャー**] の順にクリックします。

2.  **Med-v ワークスペースパッケージャー**メインパネルで、[ **Web リダイレクションの管理**] をクリックします。

3.  [ **Web リダイレクトの管理**] ウィンドウでは、med-v ワークスペースの Internet Explorer にリダイレクトされる url の一覧を入力、貼り付け、またはインポートすることができます。

    **注**  
    MED-V の URL リダイレクションは、プロトコル HTTP と HTTPS のみをサポートしています。 MED-V では、FTP やその他のプロトコルのサポートは提供されません。



~~~
Enter each web address on a single line, for example:

http://www.contoso.com/webapps/webapp1

http://www.contoso.com/webapps/webapp2

http://\*.contoso.com

http://www.contoso.com/webapps/\*

**Important**  
If you import a text file that includes a URL that uses special characters (such as ~ ! @ \# and so on), make sure that you specify UTF-8 encoding when you save the text file. Special characters do not import correctly into the MED-V Workspace Packager if the text file was saved using the default ANSI encoding.
~~~



4. [**名前を付けて保存**] をクリックします。 指定したフォルダーにある更新された URL リダイレクトファイルを保存します。 MED-V は、更新された URL リダイレクション情報を含むレジストリファイルを作成します。 グループポリシーを使用して、更新されたレジストリキーを展開します。 グループポリシーの使用方法の詳細については、「[グループポリシーソフトウェアのインストール](https://go.microsoft.com/fwlink/?LinkId=195931)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=195931) 。

   MED-V は、指定されたフォルダーに Windows PowerShell スクリプトを作成します。これは、更新された MED-V ワークスペースパッケージを再作成するために使うことができます。

## 関連トピック


[展開された MED-V ワークスペースの URL リダイレクトの情報を追加または削除する方法](how-to-add-or-remove-url-redirection-information-in-a-deployed-med-v-workspace.md)

[MED-V の URL リダイレクトの管理](manage-med-v-url-redirection.md)









