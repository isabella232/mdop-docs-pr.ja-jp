---
title: SQL スクリプトを使用して APP-V データベースを展開する方法
description: SQL スクリプトを使用して APP-V データベースを展開する方法
author: dansimp
ms.assetid: 23637936-475f-4ca5-adde-76bb27d2372b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 511d1020571eead25af9e9591fe1834a9f97f068
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814114"
---
# SQL スクリプトを使用して APP-V データベースを展開する方法


Windows インストーラーではなく SQL スクリプトを使用するには、次の手順を実行します。

-   App-v 5.0 データベースをインストールする

-   5.0 データベースを最新バージョンにアップグレードする

**SQL スクリプトを使用して app-v データベースをインストールする方法**

1. データベーススクリプトをインストールする前に、「App-v ライセンス条項のコピー」を確認して保存します。 データベーススクリプトを実行すると、ライセンス条項に同意したことになります。 同意しない場合は、このソフトウェアを使用しないでください。

2. **appv\_server\_setup.exe**を app-v リリースメディアから一時的な場所にコピーします。

3. コマンドプロンプトで**appv\_server\_setup.exe**を実行し、データベーススクリプトを抽出するための一時的な場所を指定します。

   例: appv\_server\_setup.exe/layout ¥ &lt; temp location path&gt;

4. 作成した一時的な場所を参照し、抽出された [ **Databasescripts** ] フォルダーを開いて、手順について適切な Readme.txt ファイルを確認します。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">Database (データベース)</th>
   <th align="left">使用する Readme.txt ファイルの場所</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>管理データベース</p></td>
   <td align="left"><p>ManagementDatabase サブフォルダー</p>
   <div class="alert">
   <strong>重要</strong><br/><p>App-v 5.0 SP3 管理データベースへのアップグレードまたはインストールを行う場合は、「 <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)"> 5.0 アプリをインストールまたはアップグレードするための SQL スクリプト」を参照してください </a> 。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p>レポートデータベース</p></td>
   <td align="left"><p>ReportingDatabase サブフォルダー</p></td>
   </tr>
   </tbody>
   </table>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 関連トピック


[App-V 5.0 Server の展開](deploying-the-app-v-50-server.md)

[App-V 5.0 Server を展開する方法](how-to-deploy-the-app-v-50-server-50sp3.md)









