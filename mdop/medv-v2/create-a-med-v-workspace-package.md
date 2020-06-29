---
title: MED-V ワークスペース パッケージを作成する
description: MED-V ワークスペース パッケージを作成する
author: dansimp
ms.assetid: 3f75fe73-41ac-4389-ae21-5efb2d437f4d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e20cf4cc9394c4a5e90178fff4fc36ed83c12d60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823264"
---
# MED-V ワークスペース パッケージを作成する


MED-V ワークスペースとは、エンドユーザーが MED-V によって提供される仮想マシンと対話する Windows XP デスクトップ環境です。 管理者が、MED-V ワークスペースを作成し、カスタマイズします。 ワークスペースは、MED-V ワークスペースの規則と機能を定義するイメージとグループポリシーで構成されます。

独自の構成、設定、およびルールを使用してカスタマイズされた、複数の MED-V ワークスペースを作成できます。 ユーザー、グループ、または複数のユーザーまたはグループを各 MED-V ワークスペースに関連付けることができます。 カスタマイズを行うと、そのユーザーまたはグループに対してのみ、MED-V ワークスペースを使用できるようになります。

**Med-v Workspace パッケージャー**を使って、med-v ワークスペースを作成します。 **Med-v ワークスペースパッケージャー**は、次の2つの主なセクションに分かれています。

-   MED-V ワークスペースの作成と管理に使う3つのボタンが含まれているメインパネル。 [ **Med ワークスペースパッケージを作成**する] ボタンをクリックすると、med-v ワークスペースを作成するために使用する**Med ワークスペースパッケージの作成ウィザード**が開きます。

-   Windows の右側の**ヘルプセンター**には、med-v ワークスペースの作成、テスト、管理に役立つ情報とガイダンスが記載されています。

**重要**  
**Med-v Workspace パッケージャー**を使用するには、まず、Windows PowerShell の実行ポリシーが [制限なし] に設定されていることを確認する必要があります。

`Set-ExecutionPolicy Unrestricted`

さらに、 **Med-v ワークスペースパッケージャー**を実行するコンピューターの SAN ポリシーは、"オンラインですべて" に設定されている必要があります。 SAN ポリシーの設定を確認するには、管理者の資格情報を使用して、コマンドプロンプトで次のコマンドを実行します。

`diskpart.exe`

`DISKPART> san`

`DISKPART> exit`

必要に応じて、管理者の資格情報を使用して、コマンドプロンプトで次のコマンドを入力して、SAN ポリシーを "オンライン" に変更します。

`diskpart.exe`

`DISKPART> san policy=onlineall`

`DISKPART> exit`



**重要**  
仮想ハードディスクのマウントと MED-V ワークスペースパッケージの構築に使用するコンピューターに、自動ディスク暗号化ソフトウェアがインストールされている場合は、起動する前にソフトウェアを無効にする必要があります。 それ以外の場合は、他のコンピューターで MED-V ワークスペースを使用することはできません。



ここで提供する情報は、MED-V ワークスペース展開パッケージの作成に役立ちます。

## <a href="" id="bkmk-prereq"></a>前提条件


MED-V ワークスペース展開パッケージの作成を開始する前に、次のアイテムへのアクセス権があることを確認します。

-   **Windows XP の準備された画像**

    MED-V で使用する Windows XP イメージを作成する方法の詳細については、「 [Med-v イメージを準備](prepare-a-med-v-image.md)する」を参照してください。

-   **URL リダイレクション情報が含まれているテキストファイルまたはリスト**

    URL リダイレクションテキストファイルまたはリストには、ホストコンピューターから、MED-V ワークスペースの Internet Explorer にリダイレクトする Url が含まれています。 パッケージウィザードを使って MED-V ワークスペースを作成する場合は、このリダイレクト情報をインポート、入力、またはコピーして貼り付けて、パッケージの作成プロセスのいずれかの手順に従ってください。

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



## MED-V workspace パッケージャーコンピューターの言語以外の言語の MED-V ワークスペースをパッケージ化する


既定では、MED-V ワークスペースでは、コンピューターの言語と英語の文字の文字がサポートされています。 コンピューターにインストールされているもの以外の言語用の MED-V ワークスペースを作成するには、MED-V のワークスペース名の後に、PowerShell スクリプト (. ps1) に **-loc \ [locale \]** を指定します。

Med-v workspace パッケージャーコンピューターの既定の言語以外の言語で MED ワークスペースパッケージを作成するには、MED-V ワークスペースパッケージャーを実行し、ロケールに応じて出力スクリプトを変更して、既定の言語でスクリプトを生成します。 このスクリプトは、パッケージ化時に指定された MED-V ワークスペースの出力ディレクトリにあります。 ロケール設定の名前はにあります。次のディレクトリにあるファイルを WXL します。

Virtualization\\WindowsPowerShell\\Modules\\Microsoft.Medv.Administration.Commands.WorkspacePackager\\locale ¥¥ \\ Microsoft Enterprise デスクトップ

## MED-V ワークスペースパッケージを作成する


MED-V ワークスペースパッケージを作成するには、次の手順を実行します。

****

1.  **Med-v ワークスペースのパッケージャー**を開くには、 **[スタート**]、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v workspace パッケージャー**] の順にクリックします。

2.  **Med-v ワークスペースパッケージャー**メインパネルで、[ **Med-v ワークスペースパッケージの作成**] をクリックします。

    MED-V を作成する med-v**ワークスペースパッケージウィザード**が表示されます。 このウィザードは、次のページで構成されています。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>パッケージ情報</strong></p></td>
    <td align="left"><p>MED-V ワークスペースの名前を指定し、MED-V ワークスペースパッケージファイルが保存されているフォルダーを選択します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>Windows XP のイメージを選ぶ</strong></p></td>
    <td align="left"><p>Windows XP の仮想 PC イメージを準備します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>初回のセットアップ</strong></p></td>
    <td align="left"><p>初回のセットアップ時に実行される MED-V のセットアッププロセスを指定します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>MED-V メッセージ</strong></p></td>
    <td align="left"><p>最初のセットアップ時にエンドユーザーに表示されるヘルプ情報のメッセージと省略可能な URL を指定します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>コンピューターに名前を付ける</strong></p></td>
    <td align="left"><p>MED-V 仮想マシンの名前を指定します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>ホストから設定をコピーする</strong></p></td>
    <td align="left"><p>MED-V ワークスペースの設定を定義する方法を指定します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>起動とネットワーク</strong></p></td>
    <td align="left"><p>MED-V ワークスペース、ネットワーク、ユーザーの資格情報を開始するための設定を指定します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>Web リダイレクション</strong></p></td>
    <td align="left"><p>MED-V ワークスペースの Internet Explorer にリダイレクトするテキストファイルまたは Url の一覧を指定します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><strong>まとめ</strong></p></td>
    <td align="left"><p>MED-V ワークスペースの設定を確認し、MED-V ワークスペース展開パッケージの作成を開始します。</p></td>
    </tr>
    </tbody>
    </table>



3.  [**パッケージ情報**] ページで、med-v ワークスペースの名前を入力し、med-v ワークスペースパッケージファイルが保存されているフォルダーを選択します。

    **Warning**  
    MED-V ワークスペースに名前を指定し、続行するフォルダーを指定する必要があります。



~~~
After you have finished, click **Next**.
~~~

4. **[WINDOWS Xp イメージの選択**] ページで、準備済みの MED-V Windows XP 仮想 PC イメージ (.vhd ファイル) の場所を指定します。

   **Warning**  
   続行するには、Windows XP の VHD イメージを指定する必要があります。



~~~
After you have finished, click **Next**.
~~~

5. [**初回セットアップ**] ページで、有人または無人での初回セットアップを実行するかどうか、または共有コンピューターのすべてのエンドユーザーに対して個別に使用するか、または使用するかを選択します。

   **通知なしで無人セットアップ**を選択した場合、セットアップを初めて実行する前にエンドユーザーには通知されず、最初のセットアップ時に仮想マシンがエンドユーザーに表示されません。 さらに、最初に完全無人モードで実行された場合、メッセージは必要ないため、ウィザードの**Med-v メッセージ**ページは非表示になっています。

   [無人セットアップ] を選択した**が、最初にセットアップを開始する前にエンド**ユーザーに通知する場合、セットアップが初めて実行される前にエンドユーザーに通知されます。 ただし、仮想マシンは、初めてセットアップするときにエンドユーザーに表示されません。

   エンドユーザーが初めてセットアップするときに情報を入力する必要がある場合は、[**有人セットアップ**] を選びます。

   既定の動作は**無人セットアップですが、最初のセットアップが開始される前にエンドユーザーに通知**します。

   **注意**  
   Mini-setup ファイルを作成して、ミニセットアップでユーザーの入力を完了する必要がある場合は、[**有人セットアップ**] を選択するか、初めてセットアップするときに問題が発生する可能性があります。



~~~
You can also specify how a MED-V workspace is used on computers that are shared by multiple end users. You can decide that you want to create a unique MED-V workspace for each end user or that you want the MED-V workspace made available to all end users who share the computer. The default is that the MED-V workspace is unique for each end user.

**Important**  
We recommend that you disable the fast user switching feature in Windows if you configure the MED-V workspace to be accessed by all users on a shared computer. Problems can occur if an end user logs on by using the fast user switching feature in Windows when another user is still logged on.



**Tip**  
When you create a name mask for the MED-V workspace on the **Naming Computers** page, make sure that each virtual machine on a shared computer has a unique computer name.



You can also specify whether the MED-V workspace is added to the Administrators group or administrator credentials are managed outside MED-V. By default, the MED-V workspace is not automatically added to the Administrators group.

After you have finished, click **Next**.
~~~

6. [ **MED メッセージ**] ページで、最初のセットアップ時にエンドユーザーに表示される次のメッセージを指定します。

   -   エンドユーザーが最初にセットアップを開始したときに表示されるメッセージ。

   -   初めてセットアップに失敗した場合またはエラーが発生した場合にエンドユーザーに表示されるメッセージ。

   **注**  
   [**無人セットアップ]** が選択さ**れている**場合、ウィザードの [ **med-v メッセージ**] ページは表示されません。



~~~
You can also specify an optional URL location for help information that is provided to the end user when first time setup is running.

For example, the URL can point to an internal IT webpage with answers to questions such as "How long will this take and how will I know when it has completed?" or "What do you do if you get an error message?"

**Note**  
If you specify a URL, a link is shown during first time setup that points the end user to this help information. If you do not specify a URL, no link is provided.



After you have finished, click **Next**.
~~~

7. [**コンピューターの名前付け**] ページでは、コンピューターの名前付けを med-v で管理するか、Sysprep などのシステム管理ツールで管理するかを指定できます。 既定では、コンピューターの名前付けはシステム管理ツールによって管理されます。

   コンピューターの名前付けが MED-V で管理されるように指定する場合は、ドロップダウンリストから定義済みのコンピューターの名前付け規則 (マスク) を選択します。 サンプルのコンピューター名のプレビューは、MED-V ワークスペースパッケージの作成に使用しているコンピューターに基づいて表示されます。

   カスタムの名前付け規則のいずれかを選択すると、指定できるフィールドは次の文字に制限されます。

   -   "プレフィックス" フィールドと "敬称" フィールドの文字数は、A ~ Z、a ~ z、0-9、特殊文字に制限されています。 @ \ # $% ^ & ()-\ _ ' {} ~.

   -   [Hostname] および [username] フィールドは、0 ~ 9 の数字に制限されています。

   **重要**  
   コンピューター名は一意であり、最大15文字に制限されている必要があります。 コンピューターの名前付け方法を決定する際には、複数のコンピューターを所有している、またはコンピューターを共有しているエンドユーザーを検討してください。また、ネットワークで競合を引き起こす可能性のあるコンピューター名のマスクを使用しないようにしてください。



~~~
**Caution**  
The computer name settings that you specify on this page override those specified in the Sysprep.inf answer file.



After you have finished, click **Next**.
~~~

8. [**ホストからの設定のコピー** ] ページでは、次の設定を選択して、med-v ワークスペースの構成方法を指定できます。

   **注意**  
   このページで指定した設定は、ホストコンピューターから MED-V ワークスペースにコピーされます。これは、Sysprep.inf 応答ファイルで指定された設定より優先されます。



~~~
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Copy regional settings</strong></p></td>
<td align="left"><p>Select this check box to copy the regional settings from the host computer to the MED-V workspace.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>If you select this check box, the following settings are set in the Sysprep.inf file:</p>
<pre class="syntax" space="preserve"><code>[RegionalSettings]
Language
SystemLocale
UserLocale
UserLocale_DefaultUser
InputLocale
InputLocale_DefaultUser
</code></pre></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy user settings</strong></p></td>
<td align="left"><p>Select this check box to copy certain user settings, such as user name and company name, from the host to the MED-V workspace.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>If you select this check box, the following settings are set in the Sysprep.inf file:</p>
<pre class="syntax" space="preserve"><code>[UserData]
OrgName
FullName</code></pre>
<div class="alert">
<strong>Note</strong>  
<p>Personal settings, such as Internet browsing history, are not copied over to the MED-V workspace.</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy domain name</strong></p></td>
<td align="left"><p>Select this check box to let the guest join the same domain as the host.</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><div class="alert">
<strong>Important</strong>  
<p>The MED-V guest must be configured to join a domain that lets users log on by using the credentials that they use to log on to the MED-V host.</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Copy domain organizational unit</strong></p></td>
<td align="left"><p>Select this check box to copy the domain organizational unit from the host computer to the MED-V workspace. This check box is only enabled if you select to copy the domain name from the host computer.</p></td>
</tr>
</tbody>
</table>



After you have finished, click **Next**.
~~~

9. [**起動とネットワーク**] ページでは、次の設定の既定の動作を変更することができます。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>MED-V ワークスペースを開始する</strong></p></td>
   <td align="left"><p>ユーザーのログオン時に MED-V workspace を起動するか、最初に使用するか、またはエンドユーザーが MED-V ワークスペースを開始するタイミングを決定できるようにするかを選択します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p>MED-V ワークスペースは、エンドユーザーがログオンしたとき、または公開されたアプリケーションを開くときや、リダイレクトが必要な URL を入力するときなど、MED-V が必要なアクションを最初に開始したときに、次の2つの方法のいずれかで開始されます。</p>
   <p>エンドユーザー向けにこの設定を定義するか、または MED-V の開始方法をエンドユーザーが制御できるようにすることができます。</p>
   <div class="alert">
   <strong>注</strong><br/><p>エンドユーザーによって決定されたことを指定した場合、そのユーザーが遭遇する既定の動作は、ログオン時に MED-V ワークスペースが開始されることです。 既定の設定を変更するには、通知領域の MED-V アイコンを右クリックし、[Med-v] の [ユーザー設定] を選び <strong> </strong> ます。 エンドユーザーに対してこの設定を定義した場合は、MED-V の開始方法を変更することはできません。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>ネットワーク</strong></p></td>
   <td align="left"><p>[ <strong> ネットワーク設定] で [共有] または [ブリッジ] を選択し </strong> <strong> </strong> ます。 既定値は [共有されてい <strong> </strong> ます。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><strong>共有 </strong> - Med-v workspace は、ネットワークアドレス変換 (NAT) を使って、発信トラフィック用にホスト&#39;s IP を共有します。</p>
   <p><strong>つなぎ </strong> - ます。 med-v ワークスペースには独自のネットワークアドレスがあり、通常は DHCP 経由で取得します。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>資格情報を保存する</strong></p></td>
   <td align="left"><p>エンドユーザーの資格情報を保存するかどうかを選択します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p>既定の動作では、資格情報の保存機能が無効になっているため、ユーザーがログオンするたびにエンドユーザーの認証を行う必要があります。</p>
   <div class="alert">
   <strong>重要</strong><br/><p>エンドユーザーの資格情報をキャッシュすると、ユーザーエクスペリエンスが最大限に向上しますが、そのリスクについて注意する必要があります。</p>
   <p>エンドユーザーのドメイン資格情報は、Windows Credential Manager の元に戻す形式で格納されます。 このため、攻撃者は、パスワードを取得してユーザーの資格情報にアクセスできるプログラムを作成することができます。 このリスクを軽減するには、エンドユーザーの資格情報の保存を無効にする必要があります。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



~~~
After you have finished, click **Next**.
~~~

10. [ **Web リダイレクション**] ページでは、med-v ワークスペースの Internet Explorer にリダイレクトされる url の一覧を入力、貼り付け、またはインポートすることができます。 URL リダイレクション情報を構成する方法の詳細については、「[前提条件](#bkmk-prereq)」を参照してください。

   また、MED-V ワークスペースの Internet Explorer がエンドユーザーに対してどのように構成されるかを指定することもできます。 既定では、インターネットゾーンのセキュリティレベルは [高] に設定されています。 また、アドレスバーなどの一部の既定の参照機能も削除されます。 MED-V ワークスペースの Internet Explorer の既定の構成では、より安全な参照環境がエンドユーザーに提供されます。

   **注意**  
   既定の設定を変更することで、MED-V ワークスペースで Internet Explorer をカスタマイズできます。 ただし、既定の設定を変更してセキュリティを保護しないようにすると、Internet Explorer の以前のバージョンで使用されているセキュリティ上のリスクに組織が公開されることに注意してください。 詳細については、「 [Med-v 操作のセキュリティのベストプラクティス](security-best-practices-for-med-v-operations.md)」を参照してください。



~~~
After you have finished, click **Next**.
~~~

11. [**概要**] ページで、この med-v ワークスペースのパッケージ設定を確認できます。 設定を変更する場合は、[**前**へ] ボタンをクリックして、関連するページに戻ります。 設定の確認が完了したら、[**作成**] をクリックします。

   パッケージの作成の進行状況を表示するために、 **MED ワークスペースパッケージの作成ウィザード**の [**完了**] ページが開きます。

   **注**  
   指定した VHD のサイズによっては、MED-V ワークスペースパッケージの作成プロセスが完了するまで数分かかる場合があります。



~~~
If the MED-V workspace package is created successfully, the **Completion** page displays a list of the files that you created and their respective locations. The following is a list of the files that are created and their descriptions:

-   **setup.exe**—an installation program that you deploy and run on end-user computers to install the MED-V workspaces.

-   **&lt;*workspace\_name*&gt;.msi**—an installer file that you deploy to the end-user computers. The setup.exe file will run this file to install the MED-V workspaces.

-   **&lt;*vhd\_name*&gt;.medv**—a compressed VHD file that you deploy to the end-user computers. The setup.exe file uses it when it installs the MED-V workspaces.

-   **&lt;*workspace\_name*&gt;.reg**—the configuration settings that are installed when the setup.exe, &lt;*workspace\_name*&gt;.msi, and &lt;*vhd\_name*&gt;.medv files are deployed and setup.exe is run.

-   **&lt;*workspace\_name*&gt;.ps1**—a Windows PowerShell script that you can use to rebuild the registry file and re-build the MED-V workspace package.

    **Important**  
    Before deployment, you can edit configuration settings by updating the .ps1 file that has your preferred method of script editing, such as Windows PowerShell. After you change the .ps1 file, use that file to rebuild the MED-V workspace package that you deploy to your enterprise. For more information, see [Configuring Advanced Settings by Using Windows PowerShell](configuring-advanced-settings-by-using-windows-powershell.md).

    However, after the MED-V workspace is deployed, you must edit configuration settings through the registry. For a list and description of the configuration settings, see [Managing MED-V Workspace Configuration Settings](managing-med-v-workspace-configuration-settings.md).
~~~



12. [**閉じる**] をクリックしてパッケージウィザードを閉じ、 **Med-v ワークスペースパッケージャー**に戻ります。

MED-V ワークスペースパッケージを展開する前にテストできるようになりました。

## 関連トピック


[Windows PowerShell を使用した高度な設定の構成](configuring-advanced-settings-by-using-windows-powershell.md)

[MED-V ワークスペース パッケージのテスト](testing-the-med-v-workspace-package.md)

[MED-V イメージを準備する](prepare-a-med-v-image.md)









