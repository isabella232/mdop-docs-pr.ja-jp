---
title: setup.msi を使用して App-V Client をインストールする方法
description: setup.msi を使用して App-V Client をインストールする方法
author: dansimp
ms.assetid: 7221f384-36d6-409a-94a2-86f54fd75322
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fb3a145a6c57cccbae3f4e6b191b89d93278ff8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817334"
---
# setup.msi を使用して App-V Client をインストールする方法


このトピックでは、setup.msi プログラムを使用して App-v クライアントをインストールする方法について説明します。 setup.msi プログラムを使用して App-v クライアントをインストールする前に、まず必要なソフトウェアがインストールされているかどうかを確認してから、インストールする必要があります。 必須ソフトウェアをインストールするには、このトピックの「[必要なソフトウェアをインストール](#prereq-sw)する」を参照してください。 クライアントソフトウェアをインストールするには、このトピックの「 [Setup.msi プログラムを使用して App-v クライアントをインストール](#msi-setup)する」を参照してください。

## <a href="" id="prereq-sw"></a>必須ソフトウェアのインストール


次の手順を使用して、必要なソフトウェアをインストールすることができます。 コマンドファイルを作成してコマンドプロンプトからコマンドを実行するか、VBScript や Windows PowerShell などのスクリプト言語を使ってコマンドを実行することができます。

**注** X86 と x64 の両方のバージョンの App-v クライアントには、次のソフトウェアの x86 バージョンが必要です。

 

**Microsoft VisualC + + 2005SP1 の再頒布可能パッケージ (x86) をインストールするには**

1. Microsoft ダウンロードセンター () から[Microsoft Visual C++ 2005 SP1 再頒布可能パッケージ (x86)](https://go.microsoft.com/fwlink/?LinkId=119961)ソフトウェアパッケージをダウンロードし <https://go.microsoft.com/fwlink/?LinkId=119961> ます。 \ [Template Token Value \] バージョン 4.5 SP2 以降、App-v クライアントの場合は、vcredist\_x86.exe をダウンロードしてください。 [Microsoft Visual C++ 2005 Service Pack 1 の再頒布可能パッケージ ATL セキュリティ更新プログラム](https://go.microsoft.com/fwlink/?LinkId=169360)( https://go.microsoft.com/fwlink/?LinkId=169360).\ [テンプレートトークン値])

2. サイレントインストールするには、コマンドラインオプション "/Q" を vcredist\_x86.exe と共に使用します (例: **vcredist\_x86.exe/q**)。

3. vcredist\_x86.msi ファイルを使用してソフトウェアをインストールするには、コマンドラインオプション "/C/T: &lt; fullpathtofolder &gt; " を使用して vcredist.msi ファイルを抽出し、vcredist\_x86.exe から一時フォルダーに vcredis1.cab します。 サイレントインストールするには、コマンドラインオプション/quiet ( **msiexec/i vcredist.msi** /quiet. など) を使用します。

### Microsoft VisualC + + 2008SP1 の再頒布可能パッケージ (x86) をインストールするには

**重要** バージョン4.6 以降の App-v クライアントでは、Microsoft Visual C++ 2008 Service Pack 1 の再頒布可能パッケージ ATL セキュリティ更新プログラムもインストールする必要があります。

 

****

1.  Microsoft [Visual C++ 2008 Service Pack 1 の再頒布可能パッケージ ATL セキュリティ更新プログラム](https://go.microsoft.com/fwlink/?LinkId=150700)ソフトウェアパッケージを Microsoft ダウンロードセンター () からダウンロードし https://go.microsoft.com/fwlink/?LinkId=150700) ます。

2.  サイレントインストールするには、コマンドラインオプション "/Q" を vcredist\_x86.exe と共に使用します (例: **vcredist\_x86.exe/q**)。

### Microsoft Core XML Services (MSXML) 6.0 SP1 (x86) をインストールするには

****

1.  Microsoft ダウンロードセンター () から[Microsoft CORE XML サービス (MSXML)](https://go.microsoft.com/fwlink/?LinkId=63266)のソフトウェアパッケージをダウンロードし https://go.microsoft.com/fwlink/?LinkId=63266) ます。

2.  サイレントインストールするには、コマンドラインオプション/quiet を使用します (例: **msiexec/i msxml6\_x86.msi/quiet**)。

### Microsoft アプリケーションエラー報告をインストールするには

Microsoft アプリケーションエラー報告をインストールする場合は、 *Appguid*パラメーターを使って app-v 製品コードを指定する必要があります。 製品コードは、各 App-v クライアントの種類とバージョンごとに異なります。 次の表から正しい製品コードを選択します。

**重要** App-v 4.6 SP2 以降では、Microsoft アプリケーションエラー報告 (dw20shared.msi) をインストールする必要はありません。 現在、app-v は Microsoft エラー報告を使用しています。

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">バージョン</th>
<th align="left">デスクトップクライアントの製品コード</th>
<th align="left">リモートデスクトップサービスのクライアントの製品コード</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 4.5 CU1</p></td>
<td align="left"><p>FE495DBC-6D42-4698-B61F-86E655E0796D</p></td>
<td align="left"><p>8A97C241-D92A-47DC-B360-E716C1AAA929</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 4.5 SP1</p></td>
<td align="left"><p>93468B43-C19D-44F9-8BCC-114076DB0443</p></td>
<td align="left"><p>0042AD3C-99A4-4E58-B5F0-744D5AD96E1C</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 4.5 SP2</p></td>
<td align="left"><p>C6FC75B9-7D86-4C44-8BDB-EAFE1F0E200D</p></td>
<td align="left"><p>ECF80BBA-CA07-4A74-9ED6-E064F38AF1F5</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 4.6 x86</p></td>
<td align="left"><p>9E9D30B2-2065-4FDE-B756-8F1A6EABAFC3</p></td>
<td align="left"><p>439FAC21-B4234-1D4-8126-54F9FCB70039</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 4.6 x64</p></td>
<td align="left"><p>E569E45F-7BA6-4C7F-B6BA-3FFCBE92FC22</p></td>
<td align="left"><p>D2977C18-D88A-47CB-AFD8-652DD36F4D0D</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 4.6 x86 ¹</p></td>
<td align="left"><p>40C3258B-F9D1-46DF-AE97-72C1F86F2427</p></td>
<td align="left"><p>9915D911-CC73-4122-AF4F-564F89454655</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 4.6 x64 ¹</p></td>
<td align="left"><p>1650E31FE23B8-40B5-A60A7B C5934F557E3B</p></td>
<td align="left"><p>7580D918-C621-49E7-9877-3CC59F9BD1DA</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 4.6 x86 SP1</p></td>
<td align="left"><p>DB9F70CD-29BC-480B-8BA2-C9C2232C4553</p></td>
<td align="left"><p>1354855A2-229847 C73-9022-EF0686C65991</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 4.6 x64 SP1</p></td>
<td align="left"><p>342C9BB8-65A0-46DE-AB7A-8031E151AF69</p></td>
<td align="left"><p>B2C6C8D5-FE76-4056-A326-EE5D633EA175</p></td>
</tr>
</tbody>
</table>

 

¹ App-V "Languages" リリース。

**注** 製品コードを検索する必要がある場合は、Orca.exe データベースエディターまたは同様のツールを使用して、Windows インストーラーファイルを調べて、 *ProductCode*プロパティの値を見つけることができます。 Orca.exe の使い方の詳細については、「 [Windows インストーラー開発ツール](https://go.microsoft.com/fwlink/?LinkId=150008)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=150008) 。

 

****

1.  [Microsoft アプリケーションエラー報告ツール] インストールプログラム、dw20shared.msi を見つけます。これは、リリースメディアの**support¥ Watson**フォルダーにあります。

2.  ソフトウェアをインストールするには、次のコマンドを実行します。

         **msiexec /i dw20shared.msi APPGUID={valuefromtable} REBOOT=Suppress REINSTALL=ALL REINSTALLMODE=vomus**

## <a href="" id="msi-setup"></a>Setup.msi プログラムを使用して App-v クライアントをインストールする


次の手順を使用して、App-v クライアントをインストールします。 必要なすべての必須ソフトウェアがインストールされていることを確認します。 \ [Template Token Value \] バージョン4.6 以降の App-v クライアントの場合、setup.msi プログラムはシステムをチェックし、必須ソフトウェアがインストールされていない場合は、インストールを続行できないことを示すエラーメッセージを生成します。 \ [テンプレートトークンの値 \]

**Setup.msi を使用して Application Virtualization クライアントをインストールするには**

1.  コンピューターの管理者権限を持つアカウントでログオンしていることを確認します。

2.  [昇格した権限] を使用してコマンドプロンプトウィンドウを開き、ディレクトリをセットアップファイルが格納されているフォルダーに変更します。 バージョン4.6 以降バージョンの App-v クライアントをインストールする場合、コンピューターのオペレーティングシステム32ビットまたは64ビットに適切なインストーラーを使用する必要があります。 インストールが失敗し、誤ったインストーラーを使用した場合にエラーメッセージが表示されます。

3.  コマンドプロンプトで、install コマンド文字列を入力します。 または、コマンドファイルを作成して、コマンドプロンプトから実行することもできます。 また、VBScript や Windows PowerShell などのスクリプト言語を使ってコマンドを実行することもできます。

4.  次のコマンドラインの例は、いくつかのオプションのパラメーターを使って setup.msi を使う方法を示しています。 これらのパラメーターの詳細については、「 [Application Virtualization クライアントインストーラーのコマンドラインパラメーター](application-virtualization-client-installer-command-line-parameters.md)」を参照してください。

    **msiexec.exe/i "setup.msi" SWICACHESIZE = "10240" SWIPUBSVRDISPLAY = "SWIPUBSVRTYPE =" SWIPUBSVRHOST = "PRODSYS" SWIPUBSVRPORT = "443" SWIPUBSVRPATH = "/AppVirt/appsntype.xml" SWIPUBSVRREFRESH = "SWIGLOBALDATA =" D:\\AppVirt\\Global = "SWIUSERDATA ="%\\Windows\\Application = "SWIFSDRIVE =" = "=" = "=" ^% LOCALAPPDATA ^ 仮想クライアント "=" S "**

    **重要**  
    -   このようなサイレントインストールを行うには、Windows Installer スイッチ "**/q**" が使用されます。

    -   " **%** **% HomeDrive%**" の "" 文字の前には "" エスケープ文字を指定する必要があり **^** ます。 そうしないと、Windows コマンドシェルによって、インストールを実行しているユーザーの値が設定されます。

    -   インストールログを有効にするには、msiexec スイッチ **/l\ * v ファイル名**を使用します。

     

## 関連トピック


[コマンド ラインを使用してクライアントをインストールする方法](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





