---
title: App-V 5.0 の動的構成について
description: App-V 5.0 の動的構成について
author: dansimp
ms.assetid: 88afaca1-68c5-45c4-a074-9371c56b5804
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0294a60570d6dea99193c8bd411639c4888ae6b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815034"
---
# App-V 5.0 の動的構成について


動的構成を使用して、ユーザーのために App-v 5.0 パッケージをカスタマイズすることができます。 既存の動的構成ファイルを作成または編集するには、次の情報を使用します。

動的構成ファイルを編集すると、ユーザーまたはグループに対して App-v 5.0 パッケージが実行される方法がカスタマイズされます。 これにより、必要な設定を使用してパッケージを再シーケンスする必要がなくなり、パッケージコンテンツとカスタム設定を独立したままにすることができます。

## 詳細設定: 動的構成


仮想アプリケーションパッケージには、パッケージのすべてのコア情報を提供するマニフェストが含まれています。 この情報には、パッケージ設定の既定値が含まれており、最も基本的な形式 (追加のカスタマイズなし) で設定を決定します。 特定のユーザーまたはグループに対して既定の設定を調整する場合は、次のファイルを作成して編集します。

-   ユーザー構成ファイル

-   展開構成ファイル

前の .xml ファイルでパッケージ設定を指定し、パッケージに直接影響を与えずにパッケージをカスタマイズできるようにします。 パッケージを作成すると、sequencer はパッケージマニフェストデータを使用して、既定の展開とユーザー構成の .xml ファイルを自動的に生成します。 そのため、これらの自動生成された構成ファイルには、シーケンス中に構成されているように、パッケージ本質的の既定の設定が単純に反映されます。 Sequencer によって生成されたフォームで、これらの構成ファイルをパッケージに適用すると、そのマニフェストに由来する既定の設定がパッケージに適用されます。 これにより、パッケージ固有のテンプレートが提供され、既定のいずれかを変更する必要がある場合に使い始めることができます。

**注** 以下の情報は、sequencer で生成された構成ファイルを変更して、特定のユーザーまたはグループの要件を満たすようにパッケージをカスタマイズする場合にのみ使用できます。

 

### 動的構成ファイルの内容

構成ファイル内のすべての追加、削除、更新は、パッケージのマニフェスト情報で指定された既定値に関連して作成される必要があります。 次の表を確認します。

<table>
<colgroup>
<col width="100%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>ユーザー構成 .xml ファイル</p></td>
</tr>
<tr class="even">
<td align="left"><p>展開構成 xml ファイル</p></td>
</tr>
<tr class="odd">
<td align="left"><p>パッケージマニフェスト</p></td>
</tr>
</tbody>
</table>

 

上の表は、ファイルがどのように読み取られるかを示しています。 1つ目のエントリは、最後に読み取られる内容を表します。そのため、コンテンツは優先されます。 そのため、すべてのパッケージには、パッケージマニフェストの既定の設定が含まれています。 カスタマイズされた設定を含む配置構成 .xml ファイルを適用した場合は、パッケージマニフェストの既定値が上書きされます。 カスタマイズされた設定を含むユーザー構成の .xml ファイルが適用されている場合は、展開構成とパッケージマニフェストの既定値が上書きされます。

次の一覧に、2つのファイルの種類についての詳細情報が表示されています。

-   **ユーザー構成ファイル (UserConfig)** –パッケージのカスタム設定を指定または変更できます。 この設定は、App-v 5.0 クライアントを実行しているコンピューターにパッケージを展開するときに、特定のユーザーに適用されます。

-   **展開構成ファイル (DeploymentConfig)** –パッケージの既定の設定を指定または変更できます。 この設定は、App-v 5.0 クライアントを実行しているコンピューターにパッケージを展開した場合に、すべてのユーザーに適用されます。

コンピューター上の特定のユーザーのセットに対してパッケージの設定をカスタマイズしたり、HKCU などのローカルユーザーの場所に適用される変更を行ったりするには、UserConfig ファイルを使用する必要があります。 マシン上のすべてのユーザーに対してパッケージの既定の設定を変更するか、または HKEY \ _LOCAL \ _MACHINE および [すべてのユーザー] フォルダーなどのグローバルな場所に適用される変更を行うには、DeploymentConfig ファイルを使用する必要があります。

UserConfig ファイルには、クライアント上の他のユーザーに影響を与えずに1人のユーザーに適用できる構成設定が用意されています。

-   ユーザーごとのネイティブシステムに統合される拡張機能: ショートカット、ファイルの種類の関連付け、URL プロトコル、AppPaths、ソフトウェアクライアント、COM

-   仮想サブシステム: アプリケーションオブジェクト、環境変数、レジストリの変更、サービス、フォント

-   スクリプト (ユーザーコンテキストのみ)

-   権限の管理 (app-v 4.6 でパッケージの共存を制御するため)

DeploymentConfig ファイルは、マシンコンテキストに関連する2つのセクションの構成設定を提供し、上の UserConfig リストに記載されているのと同じ機能を提供します。

-   上のすべての UserConfig 設定

-   すべてのユーザーに対してグローバルに適用できる拡張機能

-   グローバルコンピューターの場所 (レジストリなど) 用に構成できる仮想サブシステム

-   製品ソースの URL

-   スクリプト (マシンコンテキストのみ)

-   子プロセスを終了するためのコントロール

### ファイル構造

App-v 5.0 の動的構成ファイルの構造については、次のセクションで説明します。

### 動的なユーザー構成ファイル

**ヘッダー** -動的ユーザー構成ファイルのヘッダーは、次のようになります。

&lt;? xml バージョン = "1.0" エンコード = "utf-8"? &gt; &lt;UserConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ;

**PackageId**は、マニフェストファイルに存在する値と同じです。

**本文**-動的ユーザー構成ファイルの本文には、マニフェストファイルで定義されているすべてのアプリ拡張ポイントと、仮想アプリケーションを構成するための情報を含めることができます。 本文では、次の4つのサブセクションを使用できます。

1. **アプリケーション**-パッケージ内のマニフェストファイルに含まれているすべてのアプリの拡張子は、マニフェストファイルでも定義されているアプリケーション ID を使って割り当てられます。 これにより、パッケージ内の特定のアプリケーションのすべての拡張機能を有効または無効にすることができます。 **アプリケーション ID**はマニフェストファイルに存在している必要があります。無視されます。

   &lt;UserConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ;

   &lt;アプリケーション&gt;

   &lt;!--新しいアプリケーションをポリシーに定義することはできません。 AppV クライアントでは、マニフェストファイルに含まれていないアプリケーション ID は無視されます。&gt;

   &lt;アプリケーション Id = "{a56fa627-c35f-4a01-9e79-7d36aed8225a}" Enabled = "false"&gt;

   &lt;/Application&gt;

   &lt;/アプリケーション&gt;

   …

   &lt;/UserConfiguration&gt;

2. **サブシステム-** appextensions およびその他のサブシステムはサブシステムのサブノードとして配置され &lt; &gt; ます。

   &lt;UserConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ;

   &lt;サブシステム&gt;

   ..

   &lt;/サブシステム&gt;

   ..

   &lt;/UserConfiguration&gt;

   各サブシステムは、"**enabled**" 属性を使って有効または無効にすることができます。 以下に、さまざまなサブシステムと使用方法に関するサンプルを示します。

   **Extensions**

   一部のサブシステム (拡張サブシステム) コントロールの拡張機能。 これらのサブシステムは次のとおりです。ショートカット、ファイルの種類の関連付け、URL プロトコル、AppPaths、ソフトウェアクライアント、COM

   拡張サブシステムは、コンテンツとは別に有効または無効にすることができます。  そのため、ショートカットが有効になっている場合、クライアントは既定でマニフェストに含まれるショートカットを使います。 各拡張サブシステムには、Extensions ノードを含めることができ &lt; &gt; ます。 この子要素が存在する場合、クライアントはそのサブシステムのマニフェストファイル内のコンテンツを無視し、構成ファイル内のコンテンツのみを使用します。

   ショートカットサブシステムの使用例:

   1.  ユーザーが動的構成ファイルまたは展開構成ファイルでこれを定義した場合:

                                    **&lt;Shortcuts  Enabled="true"&gt;**

                                                **&lt;Extensions&gt;**

                                                 ...

                                                **&lt;/Extensions&gt;**

                                    **&lt;/Shortcuts&gt;**

                         Content in the manifest will be ignored.   

   2.  ユーザーが次のように定義した場合。

                                   **&lt;Shortcuts  Enabled="true"/&gt;**

                         Then the content in the Manifest will be integrated during publishing.

   3.  ユーザーが次のように定義した場合

                                  **&lt;Shortcuts  Enabled="true"&gt;**

                                                **&lt;Extensions/&gt;**

                                    **&lt;/Shortcuts&gt;**

   その場合でも、マニフェスト内のすべてのショートカットは無視されます。 統合されたショートカットはありません。

   サポートされている拡張サブシステムは次のとおりです。

   **ショートカット:** これにより、ローカルシステムに統合されるショートカットが制御されます。 次の例は、2つのショートカットがあります。

   &lt;サブシステム&gt;

   &lt;有効なショートカット = "true"&gt;

     &lt;拡張機能&gt;

       &lt;Extension Category="AppV.Shortcut"&gt;

         &lt;Shortcut&gt;

           &lt;File&gt;\[{Common Programs}\]\\Microsoft Contoso\\Microsoft ContosoApp Filler 2010.lnk&lt;/File&gt;

           &lt;Target&gt;\[{PackageRoot}\]\\Contoso\\ContosoApp.EXE&lt;/Target&gt;

           &lt;Icon&gt;\[{Windows}\]\\Installer\\{90140000-0011-0000-0000-0000000FF1CE}\\inficon.exe&lt;/Icon&gt;

           &lt;Arguments /&gt;

           &lt;WorkingDirectory /&gt;

           &lt;AppUserModelId&gt;ContosoApp.Filler.3&lt;/AppUserModelId&gt;

           &lt;Description&gt;Fill out dynamic forms to gather and reuse information throughout the organization using Microsoft ContosoApp.&lt;/Description&gt;

           &lt;Hotkey&gt;0&lt;/Hotkey&gt;

           &lt;ShowCommand&gt;1&lt;/ShowCommand&gt;

           &lt;ApplicationId&gt;\[{PackageRoot}\]\\Contoso\\ContosoApp.EXE&lt;/ApplicationId&gt;

         &lt;/Shortcut&gt;

     &lt;/内線番号&gt;

     &lt;拡張機能カテゴリ = "AppV. ショートカット"&gt;

       &lt;Shortcut&gt;

         &lt;File&gt;\[{AppData}\]\\Microsoft\\Contoso\\Recent\\Templates.LNK&lt;/File&gt;

         &lt;Target&gt;\[{AppData}\]\\Microsoft\\Templates&lt;/Target&gt;

         &lt;Icon /&gt;

         &lt;Arguments /&gt;

         &lt;WorkingDirectory /&gt;

         &lt;AppUserModelId /&gt;

         &lt;Description /&gt;

         &lt;Hotkey&gt;0&lt;/Hotkey&gt;

         &lt;ShowCommand&gt;1&lt;/ShowCommand&gt;

         &lt;!-- Note the ApplicationId is optional --&gt;

       &lt;/Shortcut&gt;

     &lt;/内線番号&gt;

    &lt;/内線番号&gt;

   &lt;/ショートカット&gt;

   **ファイルの種類の関連付け:** 既定で開くプログラムとファイルの種類を関連付けると共に、コンテキストメニューを設定します。 (この susbsystem を使用して MIME タイプを設定することもできます)。 ファイルの種類の関連付けの例を次に示します。

   &lt;FileTypeAssociations Enabled = "true"&gt;

   &lt;拡張機能&gt;

     &lt;拡張機能カテゴリ = "AppV. FileTypeAssociation"&gt;

       &lt;FileTypeAssociation&gt;

         &lt;FileExtension MimeAssociation="true"&gt;

         &lt;Name&gt;.docm&lt;/Name&gt;

         &lt;ProgId&gt;contosowordpad.DocumentMacroEnabled.12&lt;/ProgId&gt;

         &lt;PerceivedType&gt;document&lt;/PerceivedType&gt;

         &lt;ContentType&gt;application/vnd.ms-contosowordpad.document.macroEnabled.12&lt;/ContentType&gt;

         &lt;OpenWithList&gt;

           &lt;ApplicationName&gt;wincontosowordpad.exe&lt;/ApplicationName&gt;

         &lt;/OpenWithList&gt;

        &lt;OpenWithProgIds&gt;

           &lt;ProgId&gt;contosowordpad.8&lt;/ProgId&gt;

         &lt;/OpenWithProgIds&gt;

         &lt;ShellNew&gt;

           &lt;Command /&gt;

           &lt;DataBinary /&gt;

           &lt;DataText /&gt;

           &lt;FileName /&gt;

           &lt;NullFile&gt;true&lt;/NullFile&gt;

           &lt;ItemName /&gt;

           &lt;IconPath /&gt;

           &lt;MenuText /&gt;

           &lt;Handler /&gt;

         &lt;/ShellNew&gt;

       &lt;/FileExtension&gt;

       &lt;ProgId&gt;

          &lt;Name&gt;contosowordpad.DocumentMacroEnabled.12&lt;/Name&gt;

           &lt;DefaultIcon&gt;\[{Windows}\]\\Installer\\{90140000-0011-0000-0000-0000000FF1CE}\\contosowordpadicon.exe,15&lt;/DefaultIcon&gt;

           &lt;Description&gt;Blah Blah Blah&lt;/Description&gt;

           &lt;FriendlyTypeName&gt;\[{FOLDERID\_ProgramFilesX86}\]\\Microsoft Contoso 14\\res.dll,9182&lt;/FriendlyTypeName&gt;

           &lt;InfoTip&gt;\[{FOLDERID\_ProgramFilesX86}\]\\Microsoft Contoso 14\\res.dll,1424&lt;/InfoTip&gt;

           &lt;EditFlags&gt;0&lt;/EditFlags&gt;

           &lt;ShellCommands&gt;

             &lt;DefaultCommand&gt;Open&lt;/DefaultCommand&gt;

             &lt;ShellCommand&gt;

                &lt;ApplicationId&gt;{e56fa627-c35f-4a01-9e79-7d36aed8225a}&lt;/ApplicationId&gt;

                &lt;Name&gt;Edit&lt;/Name&gt;

                &lt;FriendlyName&gt;&Edit&lt;/FriendlyName&gt;

                &lt;CommandLine&gt;"\[{PackageRoot}\]\\Contoso\\WINcontosowordpad.EXE" /vu "%1"&lt;/CommandLine&gt;

             &lt;/ShellCommand&gt;

             &lt;/ShellCommand&gt;

               &lt;ApplicationId&gt;{e56fa627-c35f-4a01-9e79-7d36aed8225a}&lt;/ApplicationId&gt;

               &lt;Name&gt;Open&lt;/Name&gt;

               &lt;FriendlyName&gt;&Open&lt;/FriendlyName&gt;

               &lt;CommandLine&gt;"\[{PackageRoot}\]\\Contoso\\WINcontosowordpad.EXE" /n "%1"&lt;/CommandLine&gt;

               &lt;DropTargetClassId /&gt;

               &lt;DdeExec&gt;

                 &lt;Application&gt;mscontosowordpad&lt;/Application&gt;

                 &lt;Topic&gt;ShellSystem&lt;/Topic&gt;

                 &lt;IfExec&gt;\[SHELLNOOP\]&lt;/IfExec&gt;

                 &lt;DdeCommand&gt;\[SetForeground\]\[ShellNewDatabase "%1"\]&lt;/DdeCommand&gt;

               &lt;/DdeExec&gt;

             &lt;/ShellCommand&gt;

           &lt;/ShellCommands&gt;

         &lt;/ProgId&gt;

        &lt;/FileTypeAssociation&gt;

      &lt;/内線番号&gt;

     &lt;/内線番号&gt;

     &lt;/FileTypeAssociations&gt;

   **Url プロトコル**: クライアントコンピューターのローカルレジストリに統合されている url プロトコル ("mailto:" など) を制御します。

   &lt;URLProtocols 有効 = "true"&gt;

   &lt;拡張機能&gt;

   &lt;Extension Category = "AppV Protocol"&gt;

   &lt;URLProtocol&gt;

     &lt;名前 &gt; mailto &lt; /name&gt;

     &lt;ApplicationURLProtocol&gt;

     &lt;DefaultIcon &gt; \ [{ProgramFilesX86} \] \\ Microsoft Contoso\\Contoso\\contosomail.EXE、-9403 &lt; /DefaultIcon&gt;

     &lt;EditFlags &gt; 2 &lt; /EditFlags&gt;

     &lt;説明&gt;

     &lt;AppUserModelId&gt;

     &lt;FriendlyTypeName /&gt;

     &lt;チップ&gt;

   &lt;SourceFilter/&gt;

     &lt;ShellFolder/&gt;

     &lt;WebNavigableCLSID /&gt;

     &lt;ExplorerFlags &gt; 2 &lt; /ExplorerFlags&gt;

     &lt;CLSID&gt;

     &lt;ShellCommands&gt;

     &lt;DefaultCommand &gt; open &lt; /defaultcommand&gt;

     &lt;ShellCommand&gt;

     &lt;ApplicationId &gt; \ [{ProgramFilesX86} \] \\ Microsoft Contoso\\Contoso\\contosomail.EXE&lt; /ApplicationId&gt;

     &lt;名前 &gt; オープン &lt; /name&gt;

     &lt;CommandLine &gt; \ [{ProgramFilesX86} ¥ Microsoft Contoso\\Contoso\\contosomail.EXE "-c OEP"メモ/m "%1" &lt; /コマンドライン&gt;

     &lt;DropTargetClassId/&gt;

     &lt;FriendlyName&gt;

     &lt;拡張 &gt; 0 &lt; /拡張&gt;

     &lt;LegacyDisable &gt; 0 &lt; /LegacyDisable&gt;

     &lt;SuppressionPolicy &gt; 2 &lt; /SuppressionPolicy&gt;

      &lt;DdeExec&gt;

     &lt;Noのアクティブハンドラー/&gt;

     &lt;アプリケーション &gt; contosomail &lt; /Application&gt;

     &lt;トピック &gt; shellsystem &lt; /トピック&gt;

     &lt;IfExec &gt; \ [shellnoop \] &lt; /ifexec&gt;

     &lt;DdeCommand &gt; \ [setforeground \] \ [ShellNewDatabase "%1" \] &lt; /DdeCommand&gt;

     &lt;/Ddeexec&gt;

     &lt;/ShellCommand&gt;

     &lt;/シェルコマンド&gt;

     &lt;/Applicationurlprotocol&gt;

     &lt;/Urlprotocol&gt;

     &lt;/内線番号&gt;

     &lt;/内線番号&gt;

     &lt;/Urlプロトコル&gt;

   **ソフトウェアクライアント**: アプリをメールクライアント、ニュースリーダー、メディアプレーヤーとして登録し、[プログラムのアクセスとコンピューターの既定の設定] UI にアプリを表示することを許可します。 ほとんどの場合は、有効または無効にする必要があります。 また、そのクライアントを除き、他のクライアントを引き続き有効にしたい場合は、メールクライアントを有効または無効にするコントロールもあります。

   &lt;ソフトウェアクライアント有効 = "true"&gt;

     &lt;ClientConfiguration EmailEnabled = "false"/&gt;

   &lt;/ソフトウェアクライアント&gt;

   AppPaths:-contoso.exe example のアプリケーションが apppaths 名 "myapp" で登録されている場合は、[実行] メニューの下に「myapp」と入力すると contoso.exe が開きます。

   &lt;AppPaths Enabled = "true"&gt;

   &lt;拡張機能&gt;

   &lt;拡張機能カテゴリ = "AppV Path"&gt;

   &lt;AppPath&gt;

     &lt;ApplicationId &gt; \ [{ProgramFilesX86} \] \\ Microsoft Contoso\\Contoso\\contosomail.EXE&lt; /ApplicationId&gt;

     &lt;Name &gt;contosomail.exe&lt; /name&gt;

     &lt;ApplicationPath &gt; \ [{ProgramFilesX86} \] ¥ Microsoft Contoso\\Contoso\\contosomail.EXE&lt; /applicationpath&gt;

     &lt;Path環境変数プレフィックス/&gt;

     &lt;CanAcceptUrl &gt; false &lt; /canaccepturl&gt;

     &lt;SaveUrl/&gt;

   &lt;/Apppath&gt;

   &lt;/内線番号&gt;

   &lt;/内線番号&gt;

   &lt;/Apppaths&gt;

   **Com**: アプリケーションがローカル COM サーバーを登録できるようにします。 モードは、統合、分離、またはオフにすることができます。 Isol の場合

   &lt;COM モード = "分離"/&gt;

   **その他の設定**:

   拡張機能に加えて、他のサブシステムを有効または無効にしたり、編集したりすることができます。

   **仮想カーネルオブジェクト**:

   &lt;有効なオブジェクト = "false"/&gt;

   **仮想レジストリ**: HKCU 内の仮想レジストリでレジストリを設定する場合に使用されます。

   &lt;Registry Enabled = "true"&gt;

   &lt;含め&gt;

   &lt;キーパス = "\\ REGISTRY\\ USER\\ [{AppVCurrentUserSID} \] \\ ソフトウェア \\ ABC"&gt;

   &lt;値の種類 = "REG \ _SZ" Name = "Bar" データ = "NewValue"/&gt;

    &lt;/キー&gt;

     &lt;キーパス = "\\ REGISTRY\\ USER\\ [{AppVCurrentUserSID} \] \\ ソフトウェア \\ emptykey"/&gt;

    &lt;/Include&gt;

   &lt;Delete&gt;

     &lt;/レジストリ&gt;

   **仮想ファイルシステム**

         &lt;FileSystem Enabled="true" /&gt;

   **仮想フォント**

         &lt;Fonts Enabled="false" /&gt;

   **仮想環境変数**

   &lt;EnvironmentVariables Enabled = "true"&gt;

   &lt;含め&gt;

          &lt;Variable Name="UserPath" Value="%path%;%UserProfile%" /&gt;

          &lt;Variable Name="UserLib" Value="%UserProfile%\\ABC" /&gt;

          &lt;/Include&gt;

         &lt;Delete&gt;

          &lt;Variable Name="lib" /&gt;

           &lt;/Delete&gt;

           &lt;/EnvironmentVariables&gt;

   **仮想サービス**

         &lt;Services Enabled="false" /&gt;

3. **Userscripts** –スクリプトを使用して、仮想環境を設定または変更したり、アプリを実行する前に、展開または削除するときにスクリプトを実行したり、アプリケーションの終了後に環境を "クリーンアップ" するために使用したりすることができます。 Sequencer から出力されるサンプルのユーザー構成ファイルを参照して、サンプルスクリプトを確認してください。 以下のスクリプトセクションでは、使用できるさまざまなトリガーについて詳しく説明します。

4. **ManagingAuthority** –パッケージの2つのバージョンが同じコンピューター上にある場合に使用できます。1つは app-v 4.6 に展開され、もう1つはアプリ-v 5.0 に展開されています。 名前付きパッケージの app-v 4.6 extension points に対して、次のようにしてアプリから V を使用できるようにするには、UserConfig ファイルで次のように入力します (この場合、PackageName は App-v 4.6 のパッケージ GUID です)。

   &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PackageName = "032630c0-b8e2-417c-acef-76fc5297fe81"/&gt;

### 動的展開構成ファイル

**ヘッダー** -展開構成ファイルのヘッダーは、次のようになります。

&lt;? xml バージョン = "1.0" エンコード = "utf-8"? &gt; &lt;DeploymentConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/deploymentconfiguration"&gt> ;

**PackageId**は、マニフェストファイルに存在する値と同じです。

**本文**-展開構成ファイルの本文には、次の2つのセクションがあります。

-   [ユーザー構成] セクション–前のセクションで説明したユーザー構成ファイルと同じコンテンツを使用できます。 パッケージがユーザーに公開されると、このセクションの appextensions の構成設定によって、ユーザー構成ファイルも提供されていない限り、パッケージ内のマニフェストの対応する設定が上書きされます。 UserConfig ファイルも指定されている場合は、展開構成ファイルのユーザー設定ではなく、そのファイルが使用されます。 パッケージがグローバルに公開されている場合、マニフェストと組み合わせて展開構成ファイルのコンテンツのみが使用されます。

-   [マシン構成] セクション–コンピューター全体に対してのみ構成できる情報が含まれており、コンピューター上の特定のユーザーに対しては構成できません。 たとえば、VFS 内の HKEY \ _LOCAL \ _MACHINE レジストリキーを使用します。

&lt;DeploymentConfiguration **PackageId**= "1F8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName = "Reserved" xmlns = " <https://schemas.microsoft.com/appv/2010/deploymentconfiguration"&gt> ;

&lt;UserConfiguration&gt;

  ..

&lt;/UserConfiguration&gt;

&lt;コンピューターのしくみ&gt;

..

&lt;/コンピューターのしくみ&gt;

..

&lt;/コンピューターのしくみ&gt;

&lt;/Deploymentconfiguration&gt;

**ユーザー構成**-展開構成ファイルの [ユーザーの構成] セクションで指定されている設定については、「以前の**動的ユーザー構成ファイル**」セクションを参照してください。

[マシン構成]-展開構成ファイルの [コンピューターの構成] セクションを使って、コンピューター全体に対してのみ設定できる情報を構成します。これは、コンピューター上の特定のユーザーに対しては設定できません。 たとえば、仮想レジストリの HKEY \ _LOCAL \ _MACHINE レジストリキーを使用します。 この要素では、4つのサブセクションを使用できます。

1.  **サブシステム-** appextensions およびその他のサブシステムはサブノードとして配置されてい &lt; &gt; ます。

    &lt;コンピューターのしくみ&gt;

      &lt;サブシステム&gt;

      ..

      &lt;/サブシステム&gt;

    ..

    &lt;/コンピューターのしくみ&gt;

    次のセクションでは、さまざまなサブシステムと使用方法に関するサンプルを示します。

    **拡張子**:

    一部のサブシステム (拡張サブシステム) コントロールは、すべてのユーザーにのみ適用できます。 サブシステムはアプリケーションの機能です。 これはすべてのユーザーに適用されるため、この種類の拡張機能をローカルシステムに統合するためには、パッケージをグローバルに公開する必要があります。 ユーザー構成の拡張機能に適用されるコントロールや設定に関する同じ規則は、[コンピューターの構成] セクションのそれらにも適用されます。

    **アプリケーション機能**: windows オペレーティングシステムインターフェイスの既定のプログラムによって使用されます。 特定の windows MIME の種類を開くことができるように、特定のファイル拡張子を開くことができるように、アプリが、スタートメニューのインターネットブラウザースロットの contender として登録できるようにします。この拡張機能により、仮想アプリケーションも [既定のプログラムの設定」の UI に表示されるようになります。

    &lt;ApplicationCapabilities 有効 = "true"&gt;

      &lt;拡張機能&gt;

       &lt;拡張機能カテゴリ = "AppV 機能"&gt;

        &lt;ApplicationCapabilities&gt;

         &lt;ApplicationId&gt;\[{PackageRoot}\]\\LitView\\LitViewBrowser.exe&lt;/ApplicationId&gt;

         &lt;Reference&gt;

          &lt;Name&gt;LitView Browser&lt;/Name&gt;

          &lt;Path&gt;SOFTWARE\\LitView\\Browser\\Capabilities&lt;/Path&gt;

         &lt;/Reference&gt;

       &lt;CapabilityGroup&gt;

        &lt;Capabilities&gt;

         &lt;Name&gt;@\[{ProgramFilesX86}\]\\LitView\\LitViewBrowser.exe,-12345&lt;/Name&gt;

         &lt;Description&gt;@\[{ProgramFilesX86}\]\\LitView\\LitViewBrowser.exe,-12346&lt;/Description&gt;

         &lt;Hidden&gt;0&lt;/Hidden&gt;

         &lt;EMailSoftwareClient&gt;Lit View E-Mail Client&lt;/EMailSoftwareClient&gt;

         &lt;FileAssociationList&gt;

          &lt;FileAssociation Extension=".htm" ProgID="LitViewHTML" /&gt;

          &lt;FileAssociation Extension=".html" ProgID="LitViewHTML" /&gt;

          &lt;FileAssociation Extension=".shtml" ProgID="LitViewHTML" /&gt;

         &lt;/FileAssociationList&gt;

         &lt;MIMEAssociationList&gt;

          &lt;MIMEAssociation Type="audio/mp3" ProgID="LitViewHTML" /&gt;

          &lt;MIMEAssociation Type="audio/mpeg" ProgID="LitViewHTML" /&gt;

         &lt;/MIMEAssociationList&gt;

        &lt;URLAssociationList&gt;

          &lt;URLAssociation Scheme="http" ProgID="LitViewHTML.URL.http" /&gt;

         &lt;/URLAssociationList&gt;

         &lt;/Capabilities&gt;

      &lt;/CapabilityGroup&gt;

       &lt;/Applicationcapabilities&gt;

      &lt;/内線番号&gt;

    &lt;/内線番号&gt;

    &lt;/Applicationcapabilities&gt;

    **その他の設定**:

    拡張機能に加えて、他のサブシステムを編集することもできます。

    **マシン全体の仮想レジストリ**: HKEY \ _Local \ _Machine 内の仮想レジストリでレジストリキーを設定する場合に使用します。

    &lt;レジストリ&gt;

    &lt;含め&gt;

      &lt;キーパス = "\\ Registry\\ マシン \"&gt;

        &lt;Value Type="REG\_SZ" Name="Bar" Data="Baz" /&gt;

       &lt;/キー&gt;

      &lt;キーパス = "\\ Registry\\ machine¥ \ emptykey"/&gt;

     &lt;/Include&gt;

    &lt;Delete&gt;

    &lt;/レジストリ&gt;

    **マシン全体の仮想カーネルオブジェクト**

    &lt;対象&gt;

    &lt;NotIsolate&gt;

       &lt;オブジェクト名 = "testObject"/&gt;

     &lt;/NotIsolate&gt;

    &lt;/オブジェクト&gt;

2.  **Productsourceurloptout**: パッケージの URL がパッケージパッケージ (ブランチオフィスのシナリオをサポートするため) でグローバルに変更できるかどうかを示します。 Default は false であり、設定の変更は次の起動時に有効になります。  

    &lt;コンピューターのしくみ&gt;

      .. 

      &lt;ProductSourceURLOptOut Enabled = "true"/&gt;

      ..

    &lt;/コンピューターのしくみ&gt;

3.  **MachineScripts** –パッケージを展開、公開、または削除するときに、スクリプトを実行するように構成できます。 サンプルスクリプトを表示するには、sequencer によって生成されるサンプル展開構成ファイルを参照してください。 以下のスクリプトセクションでは、使用できるさまざまなトリガーについて詳しく説明します。

4.  **TerminateChildProcess**:-アプリケーションの実行可能ファイルを指定できます。これには、アプリケーション exe プロセスが終了すると子プロセスが終了します。

    &lt;コンピューターのしくみ&gt;

      ..   

      &lt;TerminateChildProcesses&gt;

        &lt;Application Path="\[{PackageRoot}\]\\Contoso\\ContosoApp.EXE" /&gt;

        &lt;Application Path="\[{PackageRoot}\]\\LitView\\LitViewBrowser.exe" /&gt;

        &lt;Application Path="\[{ProgramFilesX86}\]\\Microsoft Contoso\\Contoso\\contosomail.EXE" /&gt;

      &lt;/TerminateChildProcesses&gt;

      ..

    &lt;/コンピューターのしくみ&gt;

### スクリプト

次の表では、さまざまなスクリプトイベントと、それらを実行できるコンテキストについて説明します。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">スクリプトの実行時間</th>
<th align="left">展開構成で指定可能</th>
<th align="left">ユーザー構成で指定可能</th>
<th align="left">パッケージの仮想環境で実行可能</th>
<th align="left">特定のアプリケーションのコンテキストで実行可能</th>
<th align="left">システム/ユーザーコンテキストで実行されます: (展開構成、ユーザー構成)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AddPackage</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>(システム、該当なし)</p></td>
</tr>
<tr class="even">
<td align="left"><p>PublishPackage</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>(システム、ユーザー)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>アンインストールパッケージ</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>(システム、ユーザー)</p></td>
</tr>
<tr class="even">
<td align="left"><p>RemovePackage</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>(システム、該当なし)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>StartProcess</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>(ユーザー、ユーザー)</p></td>
</tr>
<tr class="even">
<td align="left"><p>ExitProcess</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>(ユーザー、ユーザー)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>StartVirtualEnvironment</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
<td align="left"><p>(ユーザー、ユーザー)</p></td>
</tr>
<tr class="even">
<td align="left"><p>TerminateVirtualEnvironment</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p>○</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>(ユーザー、ユーザー)</p></td>
</tr>
</tbody>
</table>

 

### App-v 5.0 マニフェストファイルを使用して動的構成ファイルを作成する

動的構成ファイルを作成するには、次の3つの方法のいずれかを使用します。手動5.0 で行うか、または2つのサンプルファイルで生成されるパッケージのシーケンスを指定します。

App-v 5.0 管理コンソールを使用してファイルを作成する方法の詳細については、「app-v [5.0 管理コンソールを使用してカスタム構成ファイルを作成する方法](how-to-create-a-custom-configuration-file-by-using-the-app-v-50-management-console.md)」を参照してください。

ファイルを手動で作成するには、前のセクションに記載されている情報を1つのファイルにまとめることができます。 Sequencer によって生成されたファイルを使うことをお勧めします。






## 関連トピック


[PowerShell を使用して展開構成ファイルを適用する方法](how-to-apply-the-deployment-configuration-file-by-using-powershell.md)

[PowerShell を使用してユーザー構成ファイルを適用する方法](how-to-apply-the-user-configuration-file-by-using-powershell.md)

[APP-V 5.0 の操作](operations-for-app-v-50.md)

 

 





