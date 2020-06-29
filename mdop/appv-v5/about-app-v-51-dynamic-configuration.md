---
title: App-v 5.1 の動的構成について
description: 動的構成を使用して、ユーザーのために App-v 5.1 パッケージをカスタマイズすることができます。 既存の動的構成ファイルを作成または編集するには、次の情報を使用します。
author: dansimp
ms.assetid: 35bc9908-d502-4a9c-873f-8ee17b6d9d74
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/28/2018
ms.author: dansimp
ms.openlocfilehash: ec8a25da6e139ac329810b1e04f7097cadaa6ab4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814964"
---
# App-v 5.1 の動的構成について 
動的構成では、動的構成ファイルを編集して、ユーザーまたはグループに対して App-v 5.1 パッケージを実行する方法をカスタマイズできます。 パッケージをカスタマイズすると、必要な設定を使ってシーケンスパッケージを再設定する必要がなくなります。  また、パッケージコンテンツとカスタム設定を独立して保持する方法も提供されています。

仮想アプリケーションパッケージには、パッケージのすべてのコア情報を提供するマニフェストが含まれています。 この情報には、パッケージ設定の既定値が含まれており、最も基本的な形式 (追加のカスタマイズなし) で設定を決定します。 

パッケージを作成すると、sequencer はパッケージマニフェストデータを使用して、既定の展開とユーザー構成の .xml ファイルを自動的に生成します。 そのため、これらの生成されたファイルには、シーケンス時に構成される既定の設定が反映されます。 Sequencer によって生成されたフォームで、これらのファイルをパッケージに適用すると、そのマニフェストに由来する既定の設定がパッケージに適用されます。 

これらの生成されたファイルを使って、必要に応じて変更を加えます。これは、パッケージに直接影響を与えません。 構成ファイルを追加、削除、更新する場合は、マニフェスト情報の既定値について変更を加えます。

>[!TIP]
>ファイルの読み取り順序は次のとおりです。<ul><li>UserConfig.xml</li><li>DeploymentConfig.xml</li><li>ノート</li></ul><p>1つ目のエントリは、"前回の読み取り" を表します。 そのため、コンテンツの優先順位が高くなり、すべてのパッケージには、パッケージマニフェストの既定の設定が含まれています。<ol><li> DeploymentConfig.xml ファイルをカスタマイズしてカスタマイズされた設定を適用する場合、パッケージマニフェストの既定の設定は上書きされます。 </li><li> UserConfig.xml をカスタマイズしてカスタマイズされた設定を適用する場合、展開構成とパッケージマニフェストの両方の既定の設定が上書きされます。 </li></ol>

## ユーザー構成ファイルの内容 (UserConfig.xml)
UserConfig ファイルには、App-v 5.1 クライアントを実行しているコンピューターにパッケージを展開するときに、特定のユーザーに適用される構成設定が用意されています。  これらの設定は、クライアント上の他のユーザーに影響を与えません。

ユーザー構成ファイルを使用して、パッケージのカスタム設定を指定または変更します。

-   ユーザーごとのネイティブシステムに統合された拡張機能: ショートカット、ファイルの種類の関連付け、URL プロトコル、AppPaths、ソフトウェアクライアント、COM
-   仮想サブシステム: アプリケーションオブジェクト、環境変数、レジストリの変更、サービス、フォント
-   スクリプト (ユーザーコンテキストのみ)
-   権限の管理 (app-v 4.6 でパッケージの共存を制御するため)

### ヘッダー

動的なユーザー構成ファイルのヘッダーは、次のようになります。

```xml
<?xml version="1.0" encoding="utf-8"?><UserConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved" xmlns="http://schemas.microsoft.com/appv/2010/userconfiguration">
```

**PackageId**は、マニフェストファイルに存在する値と同じです。


### 本文

動的ユーザー構成ファイルの本文には、マニフェストファイルで定義されているすべてのアプリ拡張ポイントと、仮想アプリケーションを構成するための情報を含めることができます。 本文では、次の4つのサブセクションを使用できます。

1.  **[アプリケーション](#applications)** 
2.  **[サブシステム](#subsystems)**
3.  **[UserScripts](#userscripts)**
4.  **[ManagingAuthority](#managingauthority)**

#### アプリケーション

パッケージ内のマニフェストファイルに含まれているすべてのアプリ拡張機能には、マニフェストファイルで見つかったアプリケーション ID が割り当てられています。 アプリケーション ID を使用すると、パッケージ内の特定のアプリケーションのすべての拡張機能を有効または無効にすることができます。 アプリケーション ID はマニフェストファイルに存在するか、無視されます。

```XML
<UserConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved"  xmlns="http://schemas.microsoft.com/appv/2010/userconfiguration">

<Applications>

<!--No new application can be defined in policy. AppV Client will ignore any application ID that is not also in the Manifest file-->

<Application Id="{a56fa627-c35f-4a01-9e79-7d36aed8225a}" Enabled="false">

</Application>

</Applications>

..

</UserConfiguration>
```

#### サブシステム

サブノードとして配置された AppExtensions とその他のサブシステム。

```XML
<UserConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved" xmlns="http://schemas.microsoft.com/appv/2010/userconfiguration">

<Subsystems>

..

</Subsystems>

..

</UserConfiguration>
```

**有効化**属性を使って各サブシステムを有効または無効にすることができます。

**拡張機能** 

一部のサブシステム (拡張サブシステム) コントロールの拡張機能。 これらのサブシステムは、ショートカット、ファイルの種類の関連付け、URL プロトコル、AppPaths、ソフトウェアクライアント、COM です。

拡張サブシステムは、コンテンツとは別に有効または無効にすることができます。 たとえば、ショートカットを有効にすると、既定ではマニフェスト内に含まれるショートカットが使用されます。 各拡張サブシステムには、ノードを含めることができ \<Extensions\> ます。 この子要素が存在する場合、クライアントはそのサブシステムのマニフェストファイル内のコンテンツを無視し、構成ファイル内のコンテンツのみを使用します。 

_**例:**_ 

- これをユーザーまたは配置の構成ファイルで定義する場合、マニフェストのコンテンツは無視されます。

  ```XML

  <Shortcuts  Enabled="true"\>

  <Extensions>

  ...

  </Extensions>

  </Shortcuts>
  ```
- 次のように定義した場合、マニフェストのコンテンツは発行中に統合されます。

  ```XML

  <Shortcuts  Enabled="true"/>
  ```

- 次のように定義した場合、マニフェスト内のすべてのショートカットは無視されます。 つまり、ショートカットは統合されません。

  ```XML

  <Shortcuts  Enabled="true">

     <Extensions/>

  </Shortcuts>
  ```

_**サポートされている拡張サブシステム:**_ 

**ショートカット**拡張サブシステムは、ローカルシステムに統合されたショートカットキーを制御します。  

```XML

<Subsystems>

<Shortcuts Enabled="true">

  <Extensions>

    <Extension Category="AppV.Shortcut">

      <Shortcut>

        <File>[{Common Programs}]\Microsoft Contoso\Microsoft ContosoApp Filler 2010.lnk</File>

        <Target>[{PackageRoot}]\Contoso\ContosoApp.EXE</Target>


      <Icon>[{Windows}]\Installer\{90140000-0011-0000-0000-0000000FF1CE}\inficon.exe</Icon>

        <Arguments />

        <WorkingDirectory />

        <AppUserModelId>ContosoApp.Filler.3</AppUserModelId>

        <Description>Fill out dynamic forms to gather and reuse information throughout the organization using Microsoft ContosoApp.</Description>

        <Hotkey>0</Hotkey>

        <ShowCommand>1</ShowCommand>

      <ApplicationId>[{PackageRoot}]\Contoso\ContosoApp.EXE</ApplicationId>

      </Shortcut>

  </Extension>

  <Extension Category="AppV.Shortcut">

    <Shortcut>

    <File>[{AppData}]\Microsoft\Contoso\Recent\Templates.LNK</File>

      <Target>[{AppData}]\Microsoft\Templates</Target>

      <Icon />

      <Arguments />

      <WorkingDirectory />

      <AppUserModelId />

      <Description />

      <Hotkey>0</Hotkey>

      <ShowCommand>1</ShowCommand>

      <!-- Note the ApplicationId is optional -->

    </Shortcut>

  </Extension>

 </Extensions>

</Shortcuts>
```

**ファイルの種類に関連付け**られた拡張サブシステムは、既定で開くプログラムとファイルの種類を関連付け、コンテキストメニューを設定します。 

>[!TIP]
>MIME タイプを使用してサブシステムを設定できます。

```XML

<FileTypeAssociations Enabled="true">

<Extensions>

  <Extension Category="AppV.FileTypeAssociation">

    <FileTypeAssociation>

      <FileExtension MimeAssociation="true">

      <Name>.docm</Name>

      <ProgId>contosowordpad.DocumentMacroEnabled.12</ProgId>

      <PerceivedType>document</PerceivedType>

    <ContentType>application/vnd.ms-contosowordpad.document.macroEnabled.12</ContentType>

      <OpenWithList>

        <ApplicationName>wincontosowordpad.exe</ApplicationName>

      </OpenWithList>

     <OpenWithProgIds>

        <ProgId>contosowordpad.8</ProgId>

      </OpenWithProgIds>

      <ShellNew>

        <Command />

        <DataBinary />

        <DataText />

        <FileName />

        <NullFile>true</NullFile>

        <ItemName />

        <IconPath />

        <MenuText />

        <Handler />

      </ShellNew>

    </FileExtension>

    <ProgId>

       <Name>contosowordpad.DocumentMacroEnabled.12</Name>

      <DefaultIcon\>[{Windows}]\Installer\{90140000-0011-0000-0000-000000FF1CE}\contosowordpadicon.exe,15</DefaultIcon>

        <Description>Blah Blah Blah</Description>

        <FriendlyTypeName>[{FOLDERID_ProgramFilesX86}]\Microsoft Contoso 14\res.dll,9182</FriendlyTypeName>

        <InfoTip>[{FOLDERID_ProgramFilesX86}]\Microsoft Contoso 14\res.dll,1424</InfoTip>

        <EditFlags>0</EditFlags>

        <ShellCommands>

          <DefaultCommand>Open</DefaultCommand>

          <ShellCommand>

           <ApplicationId>{e56fa627-c35f-4a01-9e79-7d36aed8225a}</ApplicationId>

             <Name>Edit</Name>

             <FriendlyName>&Edit</FriendlyName>

           <CommandLine>"[{PackageRoot}]\Contoso\WINcontosowordpad.EXE" /vu "%1"</CommandLine>

          </ShellCommand>

          </ShellCommand>

          <ApplicationId>{e56fa627-c35f-4a01-9e79-7d36aed8225a}</ApplicationId>

            <Name>Open</Name>

            <FriendlyName>&Open</FriendlyName>

            <CommandLine>"[{PackageRoot}]\Contoso\WINcontosowordpad.EXE" /n "%1"</CommandLine>

            <DropTargetClassId />

            <DdeExec>

              <Application>mscontosowordpad</Application>

              <Topic>ShellSystem</Topic>

              <IfExec>[SHELLNOOP]</IfExec>

              <DdeCommand>[SetForeground][ShellNewDatabase"%1"]</DdeCommand>

            </DdeExec>

          </ShellCommand>

        </ShellCommands>

      </ProgId>

     </FileTypeAssociation>

   </Extension>

  </Extensions>

  </FileTypeAssociations>
```

**Url プロトコル**拡張サブシステムは、クライアントコンピューターのローカルレジストリに統合された url プロトコル ( _mailto:_ など) を制御します。 

```XML

<URLProtocols Enabled="true">

<Extensions>

<Extension Category="AppV.URLProtocol">

<URLProtocol>

  <Name>mailto</Name>

  <ApplicationURLProtocol>

  <DefaultIcon>[{ProgramFilesX86}]\MicrosoftContoso\Contoso\contosomail.EXE,-9403</DefaultIcon>

  <EditFlags>2</EditFlags>

  <Description />

  <AppUserModelId />

  <FriendlyTypeName />

  <InfoTip />

<SourceFilter />

  <ShellFolder />

  <WebNavigableCLSID />

  <ExplorerFlags>2</ExplorerFlags>

  <CLSID />

  <ShellCommands>

  <DefaultCommand>open</DefaultCommand>

  <ShellCommand>

  <ApplicationId>[{ProgramFilesX86}]\Microsoft Contoso\Contoso\contosomail.EXE</ApplicationId>

  <Name>open</Name>

  <CommandLine>[{ProgramFilesX86}\Microsoft Contoso\Contoso\contosomail.EXE" -c OEP.Note /m "%1"</CommandLine>

  <DropTargetClassId />

  <FriendlyName />

  <Extended>0</Extended>

  <LegacyDisable>0</LegacyDisable>

  <SuppressionPolicy>2</SuppressionPolicy>

   <DdeExec>

  <NoActivateHandler />

  <Application>contosomail</Application>

  <Topic>ShellSystem</Topic>

  <IfExec>[SHELLNOOP]</IfExec>

  <DdeCommand>[SetForeground][ShellNewDatabase "%1"]</DdeCommand>

  </DdeExec>

  </ShellCommand>

  </ShellCommands>

  </ApplicationURLProtocol>

  </URLProtocol>

  </Extension>

  </Extension>

  </URLProtocols>
```

**ソフトウェアクライアント**拡張サブシステムにより、アプリはメールクライアント、ニュースリーダー、メディアプレーヤーとして登録できます。また、アプリは [プログラムのアクセスとコンピューターの既定の設定] の UI に表示されます。 ほとんどの場合、有効または無効にする必要があります。 また、そのクライアントを除き、他のクライアントを引き続き有効にしたい場合は、メールクライアントを有効または無効にするコントロールもあります。

```XML

<SoftwareClients Enabled="true">

  <ClientConfiguration EmailEnabled="false" />

</SoftwareClients>
```

**Apppaths** extension サブシステムは、アプリケーションパスと共に登録されているアプリを開きます。 たとえば、contoso.exe に_myapp_という apppath 名が含まれている場合、ユーザーは [実行] メニューから「 _myapp_ 」と入力し、contoso.exe を開くことができます。

```XML

<AppPaths Enabled="true">

<Extensions>

<Extension Category="AppV.AppPath">

<AppPath>

  <ApplicationId>[{ProgramFilesX86}]\Microsoft Contoso\Contoso\contosomail.EXE</ApplicationId>

  <Name>contosomail.exe</Name>

  <ApplicationPath>[{ProgramFilesX86}]\Microsoft Contoso\Contoso\contosomail.EXE</ApplicationPath>

  <PATHEnvironmentVariablePrefix />

  <CanAcceptUrl>false</CanAcceptUrl>

  <SaveUrl />

</AppPath>

</Extension>

</Extensions>

</AppPaths>
```

**Com**拡張機能サブシステムでは、アプリケーションをローカル com サーバーに登録できます。 モードには次のものがあります。

-   His
-   独立 
-   オフ

```XML

<COM Mode="Isolated"/>
```

**仮想カーネルオブジェクト**

```XML

<Objects Enabled="false" />
```

**仮想レジストリ**によって、HKCU 内の仮想レジストリにレジストリが設定されます。

```XML

<Registry Enabled="true">

<Include>

<Key Path="\REGISTRY\USER\[{AppVCurrentUserSID}]\Software\ABC">

<Value Type="REG_SZ" Name="Bar" Data="NewValue" />

 </Key>

  <Key Path="\REGISTRY\USER\[{AppVCurrentUserSID}]\Software\EmptyKey" />

 </Include>

<Delete>

</Registry>
```

**仮想ファイルシステム**

```XML

    <FileSystem Enabled="true" />
```

**仮想フォント**

```XML

      <Fonts Enabled="false" />
```

**仮想環境変数**

```XML

<EnvironmentVariables Enabled="true">

<Include>

       <Variable Name="UserPath" Value="%path%;%UserProfile%" />

       <Variable Name="UserLib" Value="%UserProfile%\ABC" />

       </Include>

      <Delete>

       <Variable Name="lib" />

        </Delete>

        </EnvironmentVariables>
```

**仮想サービス**

```XML

      <Services Enabled="false" />
```

#### UserScripts

UserScripts を使って仮想環境を設定または変更します。  また、展開時にスクリプトを実行したり、アプリケーションの終了後に環境をクリーンアップしたりすることもできます。 サンプルスクリプトを確認するには、sequencer によって生成されたユーザー構成ファイルを参照してください。 以下のスクリプトセクションでは、使用できるさまざまなトリガーについて詳しく説明します。

#### ManagingAuthority

ManagingAuthority は、パッケージの2つのバージョンが同じコンピューター上に共存する場合に使用します。1つは App-v 4.6 に展開され、もう1つはアプリ V 5.0 に展開されます。 名前付きパッケージの app-v 4.6 extension points に対して、次のようにしてアプリから V を使用できるようにするには、UserConfig ファイルで次のように入力します (この場合、PackageName は App-v 4.6 のパッケージ GUID です)。

```XML

<ManagingAuthority TakeoverExtensionPointsFrom46="true" PackageName="032630c0-b8e2-417c-acef-76fc5297fe81" />
```

## 展開構成ファイル (DeploymentConfig.xml)

DeploymentConfig ファイルには、UserConfig ファイルに示されている機能と同じ機能を提供する、マシンコンテキストとユーザーコンテキストの構成設定が用意されています。 App-v 5.1 クライアントを実行しているコンピューターにパッケージを展開するときに、設定が適用されます。

パッケージのカスタム設定を指定または変更するには、DeploymentConfig ファイルを使用します。

- すべての UserConfig 設定
- すべてのユーザーに対してグローバルに適用できる拡張機能
- グローバルコンピューターの場所の仮想サブシステム (レジストリなど)
- 製品ソースの URL
- スクリプト (マシンコンテキストのみ)
- 子プロセスを終了するためのコントロール

### ヘッダー

動的な配置構成ファイルのヘッダーは、次のようになります。

```XML
<?xml version="1.0" encoding="utf-8"?><DeploymentConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved" xmlns="http://schemas.microsoft.com/appv/2010/deploymentconfiguration">
```

**PackageId**は、マニフェストファイルに存在する値と同じです。

### 本文

動的な展開構成ファイルの本文には、次の2つのセクションがあります。

- **Userconfiguration:** 前のセクションで説明したユーザー構成ファイルと同じコンテンツを許可します。  ユーザーにパッケージを公開する場合、ユーザー構成ファイルを指定しない限り、このセクションのすべての appextensions の構成設定は、パッケージ内のマニフェストで対応する設定を上書きします。 UserConfig ファイルも提供する場合は、展開構成ファイルのユーザー設定ではなく、そのファイルを使用します。 パッケージをグローバルに公開する場合、展開構成ファイルの内容のみがマニフェストと組み合わせて使用されます。 詳細については、「[ユーザー構成ファイルの内容 (UserConfig.xml)](#user-configuration-file-contents-userconfigxml)」を参照してください。

- [コンピューター]: マシンの特定のユーザーに対してではなく、コンピューター全体に対してのみ構成できる情報が含まれ**ます**。 たとえば、VFS のレジストリキーを HKEY_LOCAL_MACHINE します。

```XML

<DeploymentConfiguration PackageId="1f8488bf-2257-46b4-b27f-09c9dbaae707" DisplayName="Reserved" xmlns="http://schemas.microsoft.com/appv/2010/deploymentconfiguration">

<UserConfiguration>

...

</UserConfiguration>

<MachineConfiguration>

...

</MachineConfiguration>

...

</MachineConfiguration>

</DeploymentConfiguration>
```

### UserConfiguration

このセクションで提供される設定の詳細については、「[ユーザー構成ファイルのコンテンツ (UserConfig.xml)](#user-configuration-file-contents-userconfigxml) 」を参照してください。 

### コンピューターのしくみ

マシン全体の情報を構成するには、[コンピューターの構成] セクションを使用します。コンピューター上の特定のユーザーには使用できません。 たとえば、仮想レジストリのレジストリキーを HKEY_LOCAL_MACHINE ます。 この要素では、次の4つのサブセクションを使用できます。

1.  **[サブシステム](#subsystems-1)**
2.  **[ProductSourceURLOptOut](#productsourceurloptout)**
3.  **[MachineScripts](#machinescripts)**
4.  **[TerminateChildProcess](#terminatechildprocess)**

#### サブシステム

サブノードとして配置された AppExtensions とその他のサブシステム。

```XML

<MachineConfiguration>

  <Subsystems>

  …

  </Subsystems>

…

</MachineConfiguration>
```

**有効化**属性を使って各サブシステムを有効または無効にすることができます。

**拡張機能** 

一部のサブシステム (拡張サブシステム) コントロールの拡張機能。 サブシステムは、既定のプログラムで使用するアプリケーション機能です。 この種類の拡張機能については、ローカルシステムに統合するためにパッケージをグローバルに公開する必要があります。 ユーザー構成の拡張機能に適用されるコントロールと設定についても、[コンピューターの構成] セクションのコントロールと同じ規則に適用されます。

**アプリケーション機能**: アプリケーションが次のように登録できる既定のプログラムによって使用されます。

- 特定のファイル拡張子を開くことができる
- [スタート] メニューのインターネットブラウザースロットの contender
- 特定の windows MIME タイプを開くことができる

この拡張機能により、仮想アプリケーションも [既定のプログラムの設定」の UI に表示されます。

```XML

<ApplicationCapabilities Enabled="true">

  <Extensions>

   <Extension Category="AppV.ApplicationCapabilities">

    <ApplicationCapabilities>


   <ApplicationId>[{PackageRoot}]\LitView\LitViewBrowser.exe</ApplicationId>

     <Reference>

      <Name>LitView Browser</Name>

      <Path>SOFTWARE\LitView\Browser\Capabilities</Path>

     </Reference>

   <CapabilityGroup>

    <Capabilities>


   <Name>@[{ProgramFilesX86}]\LitView\LitViewBrowser.exe,-12345</Name>


   <Description>@[{ProgramFilesX86}]\LitView\LitViewBrowser.exe,-12346</Description>

     <Hidden>0</Hidden>

     <EMailSoftwareClient>Lit View E-Mail Client</EMailSoftwareClient>

     <FileAssociationList>

      <FileAssociation Extension=".htm" ProgID="LitViewHTML" />

      <FileAssociation Extension=".html" ProgID="LitViewHTML" />

      <FileAssociation Extension=".shtml" ProgID="LitViewHTML" />

     </FileAssociationList>

     <MIMEAssociationList>

      <MIMEAssociation Type="audio/mp3" ProgID="LitViewHTML" />

      <MIMEAssociation Type="audio/mpeg" ProgID="LitViewHTML" />

     </MIMEAssociationList>

    <URLAssociationList>

      <URLAssociation Scheme="http" ProgID="LitViewHTML.URL.http" />

     </URLAssociationList>

     </Capabilities>

  </CapabilityGroup>

   </ApplicationCapabilities>

  </Extension>

</Extensions>

</ApplicationCapabilities>
```

_**サポートされている拡張サブシステム:**_ 

**Machine Wide Virtual registry** extension subsystem は HKEY_Local_Machine 内の仮想レジストリにレジストリキーを設定します。

```XML

<Registry>

<Include>

  <Key Path="\REGISTRY\\Machine\Software\ABC">

    <Value Type="REG_SZ" Name="Bar" Data="Baz" />

   </Key>

  <Key Path="\REGISTRY\Machine\Software\EmptyKey" />

 </Include>

<Delete>

</Registry>
```

**マシン全体の仮想カーネルオブジェクト**

```XML

<Objects>

<NotIsolate>

   <Object Name="testObject" />

 </NotIsolate>

</Objects>
```

#### ProductSourceURLOptOut

ProductSourceURLOptOut を使って、パッケージの URL がパッケージ_パッケージ (ブランチ_オフィスのシナリオをサポートするため) でグローバルに変更できることを示します。 変更は次の起動時に有効になります。 

```XML

<MachineConfiguration>

  ... 

  <ProductSourceURLOptOut Enabled="true" />

  ...

</MachineConfiguration>
```

#### MachineScripts

パッケージは、展開、パブリッシング、または削除の時点でスクリプトを実行するように構成できます。 サンプルスクリプトを確認するには、sequencer によって生成された展開構成ファイルを参照してください。 

以下のスクリプトセクションでは、使用できるさまざまなトリガーについて詳しく説明します。

#### TerminateChildProcess

アプリケーションの実行可能ファイルを指定して、アプリケーション exe プロセスが終了したときに子プロセスが終了するようにすることができます。

```XML

<MachineConfiguration>

  ...   

  <TerminateChildProcesses>

    <Application Path="[{PackageRoot}]\Contoso\ContosoApp.EXE" />

    <Application Path="[{PackageRoot}]\LitView\LitViewBrowser.exe" />

    <Application Path="[{ProgramFilesX86}]\Microsoft Contoso\Contoso\contosomail.EXE" />

  </TerminateChildProcesses>

  ...

</MachineConfiguration>
```



## スクリプト

次の表では、さまざまなスクリプトイベントと、それらを実行できるコンテキストについて説明します。

| スクリプトの実行時間       | 展開構成で指定可能 | ユーザー構成で指定可能 | パッケージの仮想環境で実行可能 | 特定のアプリケーションのコンテキストで実行可能 | システム/ユーザーコンテキストで実行されます: (展開構成、ユーザー構成) |
|-----------------------------|----------------------------------------------|----------------------------------------|---------------------------------------------------|-----------------------------------------------------|-----------------------------------------------------------------------------|
| AddPackage                  | ○                                            |                                        |                                                   |                                                     | (システム、該当なし)                                                               |
| PublishPackage              | ○                                            | ○                                      |                                                   |                                                     | (システム、ユーザー)                                                              |
| アンインストールパッケージ            | ○                                            | ○                                      |                                                   |                                                     | (システム、ユーザー)                                                              |
| RemovePackage               | ○                                            |                                        |                                                   |                                                     | (システム、該当なし)                                                               |
| StartProcess                | ○                                            | ○                                      | ○                                                 | ○                                                   | (ユーザー、ユーザー)                                                                |
| ExitProcess                 | ○                                            | ○                                      |                                                   | ○                                                   | (ユーザー、ユーザー)                                                                |
| StartVirtualEnvironment     | ○                                            | ○                                      | ○                                                 |                                                     | (ユーザー、ユーザー)                                                                |
| TerminateVirtualEnvironment | ○                                            | ○                                      |                                                   |                                                     | (ユーザー、ユーザー)                                                                |

### 1つのイベントトリガーでの複数のスクリプトの使用

App-v 5.1 では、app-v パッケージの1つのイベントトリガーで複数のスクリプトを使うことができます。これには、App-v 4.6 から App-v 5.0 以降に変換されたパッケージが含まれています。 複数のスクリプトを使用できるようにするために、App-v 5.1 は、ScriptRunner.exe という名前のスクリプト起動アプリケーションを使用します。このアプリケーションは、App-v クライアントのインストールの一部としてインストールされます。

### 1つのイベントトリガーで複数のスクリプトを使用する方法

実行するスクリプトごとに、そのスクリプトを引数として ScriptRunner.exe アプリケーションに渡します。 その後、各スクリプトで指定した引数と共に、各スクリプトが個別に実行されます。 トリガーごとに1つのスクリプト (ScriptRunner.exe) のみを使用します。

> [!NOTE]
> 
> 最初に、コマンドプロンプトから複数のスクリプトを実行して、すべての引数が正しく構築されていることを確認してから展開構成ファイルに追加することをお勧めします。

### スクリプトとパラメーターの説明の例

次の例のファイルとテーブルを使って、展開またはユーザー構成ファイルを変更して、実行するスクリプトを追加します。

```XML
<MachineScripts>
 <AddPackage>
   <Path>ScriptRunner.exe</Path>
   <Arguments>
   -appvscript script1.exe arg1 arg2 –appvscriptrunnerparameters –wait –timeout=10
   -appvscript script2.vbs arg1 arg2
   -appvscript script3.bat arg1 arg2 –appvscriptrunnerparameters –wait –timeout=30 –rollbackonerror
   </Arguments>
   <Wait timeout=”40” RollbackOnError=”true”/>
 </AddPackage>
</MachineScripts>
```


**サンプルファイルのパラメーターには、次のようなものがあります。**

#### \<AddPackage\>

パッケージの追加やパッケージの公開など、スクリプトを実行しているイベントトリガーの名前。

#### \<Path\>ScriptRunner.exe\</Path\>

App-v クライアントインストールの一部としてインストールされるスクリプト起動ツールアプリケーション。

> [!NOTE]
> 
> ScriptRunner.exe は App-v クライアントの一部としてインストールされますが、App-v クライアントの場所は% path% にするか、ScriptRunner は実行されません。 ScriptRunner.exe は、通常、C:FilesApplication Virtualizationfolder にあります。

#### \<Arguments\>

`-appvscript` -実行する実際のスクリプトを表すトークン。

`script1.exe` –実行するスクリプトの名前。

`arg1 arg2` –実行するスクリプトの引数。

`-appvscriptrunnerparameters` – script1.exe の実行オプションを表すトークン。

`-wait` –次のスクリプトに進む前に script1.exe の実行が完了するまで待機することを ScriptRunner に通知するトークン。

`-timeout=x` – X 秒後に現在のスクリプトの実行を停止することを ScriptRunner に通知するトークン。 その他の指定したすべてのスクリプトは引き続き実行されます。

`-rollbackonerror` –まだ実行されていないすべてのスクリプトの実行を停止し、エラーを App-v クライアントにロールバックすることを ScriptRunner に通知するトークン。

#### \<Wait timeout=”40” RollbackOnError=”true”/\>

ScriptRunner.exe の全体が完了するまで待機します。

ランナー全体のタイムアウト値は、個々のスクリプトのタイムアウト値の合計以上になるように設定します。

個々のスクリプトによってエラーが報告され、rollbackonerror が true に設定されている場合、ScriptRunner はエラーを App-v クライアントに報告します。

ScriptRunner は、ファイルの種類がコンピューターにインストールされているアプリケーションに関連付けられているスクリプトを実行します。 関連付けられたアプリケーションが見つからない場合、またはスクリプトのファイルの種類がコンピューター上のアプリケーションに関連付けられていない場合、スクリプトは実行されません。

### App-v 5.1 マニフェストファイルを使用して動的構成ファイルを作成する

動的構成ファイルを作成するには、次の3つの方法のいずれかを使用します。手動5.1 で行うか、またはパッケージをシーケンス処理して、2つのサンプルファイルを生成します。 App-v 5.1 管理コンソールを使用してファイルを作成する方法の詳細については、「app-v [5.1 管理コンソールを使用してカスタム構成ファイルを作成する方法](how-to-create-a-custom-configuration-file-by-using-the-app-v-51-management-console.md)」を参照してください。

ファイルを手動で作成するには、前のセクションに記載されている情報を1つのファイルにまとめることができます。 Sequencer によって生成されたファイルを使うことをお勧めします。



- [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。
- App-v の問題については、 [app-v の TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)ください。

## 関連トピック

- [PowerShell を使用して展開構成ファイルを適用する方法](how-to-apply-the-deployment-configuration-file-by-using-powershell51.md)

- [PowerShell を使用してユーザー構成ファイルを適用する方法](how-to-apply-the-user-configuration-file-by-using-powershell51.md)

- [APP-V 5.1 の操作](operations-for-app-v-51.md)

---
