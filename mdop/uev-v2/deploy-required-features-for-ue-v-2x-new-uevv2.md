---
title: UE-V 2.x の必要な機能を展開する
description: UE-V 2.x の必要な機能を展開する
author: dansimp
ms.assetid: 10399bb3-cc7b-4578-bc0c-2f6b597abe4d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f2123ec75fb151a8f5b836b9b2522a9d6090b043
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824667"
---
# UE-V 2.x の必要な機能を展開する


すべての Microsoft User Experience Virtualization (UE-V) 2.0、2.1、2.1 SP1 の展開には、次の機能が必要です。

-   エンドユーザーがアクセスできる[設定の保存場所を展開](#ssl)します。

    これは、ユーザー設定を保存して取得する標準ネットワーク共有です。

-   [UE-V の構成方法を選択する](#config)

    UE-V は、グループポリシー、構成マネージャー、Windows 管理インフラストラクチャ、Powershell などの一般的な管理ツールを使用して展開および構成できます。

-   設定を同期するすべてのコンピューターにインストールされる[Ue-v agent を展開](#agent)します。

    これにより、登録されているアプリケーションとオペレーティングシステムがすべての設定の変更を監視し、コンピューター間でそれらの設定が同期されます。

このセクションのトピックでは、これらの機能を展開する方法について説明します。

## <a href="" id="ssl"></a>UE-V の設定の保存場所を展開する


UE-V では、ユーザー設定を保存する場所を設定パッケージファイルに格納する必要があります。 この設定の保存場所は、次のいずれかの方法で構成できます。

-   独自の設定の保存場所を作成する

-   設定の保存場所に既存の Active Directory を使用する

設定の保存場所を作成しない場合、UE-V Agent では既定で Active Directory (AD) が使用されます。

**注**  
[パフォーマンスとキャパシティの計画](https://technet.microsoft.com/library/dn458932.aspx#capacity)の問題で、ネットワーク待ち時間の問題を減らすために、ユーザーのコンピューターが存在する同じローカルネットワーク上に設定の保存場所を作成します。 設定の保存場所については、ユーザー1人につき 20 MB のディスク領域をお勧めします。



### UE-V の設定の保存場所を作成する

設定の保存場所を定義する前に、共有に設定を保存しているユーザーの読み取り/書き込みアクセス許可を持つルートディレクトリを作成する必要があります。 UE-V Agent は、このルートディレクトリの下にユーザー固有のフォルダーを作成します。

設定の保存場所は、SettingsStoragePath 構成オプションを設定することによって定義されます。これは、次のいずれかの方法を使用して構成できます。

-   コマンドラインパラメーターまたはバッチスクリプトを使用[して Ue-v agent を展開](#agent)する場合

-   [グループポリシー](https://technet.microsoft.com/library/dn458893.aspx)設定を使用する

-   UE-V の[System Center 構成パック](https://technet.microsoft.com/library/dn458917.aspx)

-   UE-V Agent をインストールした後、 [Windows PowerShell または Windows Management Instrumentation (WMI)](https://technet.microsoft.com/library/dn458937.aspx)を使用する

パスは、サーバーと共有の汎用名前付け規則 (UNC) パスに含まれている必要があります。 たとえば、 **\\ ¥ server¥¥ \ \**のように設定します。 この構成オプションは、特定の同期シナリオを有効にするための変数の使用をサポートしています。 たとえば、次のシナリオでは、変数を使用して `%username%\%computername%` エンドユーザーによる設定のエクスペリエンスを維持できます。

-   企業内の複数の物理コンピューターを使用するエンドユーザー

-   複数のエンドユーザーによって使用されるエンタープライズコンピューター

UE-V Agent は、 `SettingsPackages` **Settingsstoragepath**の構成設定に基づいて、という名前の隠しシステムフォルダーを使って、ユーザー固有の設定の記憶域のパスを動的に作成します。 エージェントは、登録されている UE-V 設定の場所テンプレートで定義されている場所に対して、設定を読み取りおよび書き込みします。

**Ue-v の設定は、"最終書き込み wins" ルールによって決定されます。** 設定の保存場所が、複数の管理コンピューターを持つユーザーに対して同じである場合、1つの UE-V Agent は、他のコンピューターで実行されているエージェントとは別に、設定の場所に対して読み取りと書き込みを行います。 最後に書き込まれた設定と値は、次のエージェントが設定の保存場所から読み取りを行ったときに適用されるものです。

**設定の保存場所を展開します。** 既存の Active Directory サービスを使うのではなく、設定の保存場所を定義するには、次の手順を実行します。 次の表に示すように、設定の記憶域の共有へのアクセスを必要とするユーザーだけに制限する必要があります。

**UE-V ネットワーク共有を展開するには**

1.  UE-V ユーザーの新しいセキュリティグループを作成します。

2.  UE-V 設定パッケージが保存されている中央のコンピューターに新しいフォルダーを作成し、そのフォルダーへのグループアクセス許可を使用して、UE-V ユーザーにアクセスを許可します。 UE-V をサポートしている管理者は、この共有フォルダーへのアクセス許可を持っている必要があります。

3.  [設定の保存場所] フォルダーに対して、次の共有レベルのサーバーメッセージブロック (SMB) 権限を設定します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>ユーザーアカウント</strong></th>
    <th align="left"><strong>推奨されるアクセス許可</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>すべてのユーザー</p></td>
    <td align="left"><p>権限なし</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UE-V ユーザーのセキュリティグループ</p></td>
    <td align="left"><p>フルコントロール</p></td>
    </tr>
    </tbody>
    </table>



4.  [設定の保存場所] フォルダーに、次の NTFS ファイルシステムの権限を設定します。

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>ユーザーアカウント</strong></th>
    <th align="left"><strong>推奨されるアクセス許可</strong></th>
    <th align="left"><strong>Folder</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>作成者/所有者</p></td>
    <td align="left"><p>フルコントロール</p></td>
    <td align="left"><p>サブフォルダーとファイルのみ</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UE-V ユーザーのセキュリティグループ</p></td>
    <td align="left"><p>フォルダーの一覧/データの読み取り、フォルダーの作成/データの追加を行う</p></td>
    <td align="left"><p>このフォルダーのみ</p></td>
    </tr>
    </tbody>
    </table>



この構成では、UE-V Agent はユーザーのコンテキストで実行されているときに Settingspackage フォルダーを作成して、セキュリティで保護し、各ユーザーに設定ストレージのフォルダーを作成するためのアクセス許可を付与します。 ユーザーは、他のユーザーがアクセスできない Settingspackage フォルダーに対してフルコントロールを受け取ります。

**注**  
Windows Server オペレーティングシステムを実行しているコンピューターで設定記憶域共有を作成する場合は、UE-V を構成して、ローカル管理者グループまたは現在のユーザーが、設定パッケージが保存されているフォルダーの所有者であるかどうかを確認します。 この追加のセキュリティを有効にするには、Windows Server レジストリエディターで次の設定を指定します。

1.  **"RepositoryOwnerCheckEnabled"** という名前の**REG \ _DWORD**のレジストリキーを**HKEY \ _LOCAL \ _MACHINE ¥**$ ¥の設定に追加します。

2.  レジストリキーの値を*1*に設定します。



### UE-V 2 x で Active Directory を使用する

UE-V Agent では、設定の保存場所が定義されていない場合、既定で Active Directory (AD) が使用されます。 このような場合、UE-V Agent では、各ユーザーの AD ホームディレクトリのルートの下に [設定の保存] フォルダーが動的に作成されます。 ただし、カスタムディレクトリ設定が AD で構成されている場合は、代わりにそのディレクトリが使用されます。

## <a href="" id="config"></a>UE-V 2. x の構成方法を選択します。


展開後に UE-V を管理するために使用する構成方法を理解する必要があります。これは、UE-V Agent の展開に使用する構成方法になります。 通常、これは、Windows PowerShell や Configuration Manager など、環境で既に使用している構成方法です。

使用している構成方法によっては、UE-V Agent をインストールする前、実行中、または後で UE-V を構成できます。

-   [グループポリシー](https://technet.microsoft.com/library/dn458893.aspx)**:** 既存のグループポリシーインフラストラクチャを使用して、ue-v エージェントの展開前または後の ue-v を構成できます。 UE-V グループポリシー ADMX テンプレートを使用すると、一般的な UE-V Agent 構成オプションの中央管理を有効にすることができます。また、UE-V の同期を構成する設定が含まれています。

    **Ue-v グループポリシーの ADMX テンプレートをインストールする:** UE-V のグループポリシー ADMX テンプレートでは、UE-V エージェントの同期設定を構成し、既存のグループポリシーインフラストラクチャを使用して、共通の UE-V エージェント構成設定の中央管理を有効にします。

    グループポリシーオブジェクトを展開するドメインコントローラーでサポートされているオペレーティングシステムには、次のようなものがあります。

    Windows Server 2008 R2

    Windows Server 2012 および Windows Server 2012 R2

-   [構成マネージャー](https://technet.microsoft.com/library/dn458917.aspx)**:** ue-v 構成パックを使用すると、System Center configuration manager 2012 SP1 以降のコンプライアンス設定機能を使用して、ue-v および Configuration manager がインストールされているサイト間で一貫した構成を適用することができます。

-   [Windows powershell と wmi](https://technet.microsoft.com/library/dn458937.aspx)**:** windows powershell 用のスクリプトコマンドと windows Management Instrumentation (WMI) を使って、ue-v agent をインストールした後に構成を変更することができます。

    **注**  
    レジストリの変更が原因でデータが失われる、またはコンピューターが応答しなくなることがあります。 他の構成方法を使用することをお勧めします。



-   **コマンドラインまたはバッチスクリプトのインストール:**[Ue-v agent を展開](#agent)するときに使用されるパラメーターによって、多くの ue-v の設定が構成されます。 System Center 2012 構成マネージャーなどの電子ソフトウェア配布システムでは、これらのパラメーターを使用して、UE-V Agent ソフトウェアを展開してインストールするときにクライアントを構成します。

## <a href="" id="agent"></a>UE-V Agent を展開する


UE-V Agent は、ue-v の展開の中核であり、アプリケーションと Windows の設定を同期するために UE-V を使用する各コンピューターで実行する必要があります。

**Ue-v agent のインストールファイル:** 1つのインストールファイル (AgentSetup.exe) は、32ビットと64ビットの両方のオペレーティングシステムに UE-V エージェントをインストールします。 また、AgentSetupx86.msi または AgentSetupx64.msi アーキテクチャ固有の Windows インストーラーファイルが用意されているため、それが小さいため、エージェントの展開が合理化される可能性があります。 [AgentSetup.exe installer のコマンドラインパラメーター](#params)も、Windows インストーラーのインストールでサポートされています。

**重要**  
UE-V Agent のインストールまたはアンインストール時には、AgentSetup.exe ファイルまたは AgentSetup arch ファイルは使用できますが、両方を使用することはでき &lt; &gt; ません。 UE-V Agent のインストールに使用した UE-V エージェントをアンインストールするには、同じファイルを使用する必要があります。



### UE-V エージェントを展開するには

UE-V Agent を展開するには、次のメソッドを使用できます。

-   Windows Installer (.msi) ファイルをインストールできる、構成マネージャーなどの電子ソフトウェア配布 (ESD) ソリューションシステム。

-   共有に一元的に保存されている Windows Installer (.msi) ファイルを参照するインストールスクリプト。

-   コンピューターで手動で実行するインストールプログラム。

ネットワーク共有から UE-V Agent を展開するには、次の手順を使用します。

**ネットワーク共有から UE-V Agent をインストールして構成するには**

1.  UE-V Agent インストールファイル AgentSetup.exe、ユーザーが読み取りアクセス許可を持つネットワーク共有上にステージングします。

2.  UE-V Agent をインストールするユーザーコンピューターにスクリプトを展開します。 スクリプトでは、設定の保存場所を指定する必要があります。

**展開オプション:** UE-V Agent をインストールする場合は、必ず正しい変数形式を使用してください。 次の表では、AgentSetup.exe または Windows Installer (.msi) ファイルを使用するための展開オプションの例を示します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>展開の種類</strong></th>
<th align="left"><strong>展開の説明</strong></th>
<th align="left"><strong>例</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>コマンドプロンプト</p></td>
<td align="left"><p>コマンドプロンプトで UE-V Agent をインストールする場合は、 <em> % ^ username% 変数形式を使用し </em> ます。 設定の記憶域のパスにスペースが含まれているために引用符が必要な場合は、展開用のバッチスクリプトファイルを使います。</p>
<p></p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%^username%</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>バッチスクリプト</p></td>
<td align="left"><p>UE-V Agent をバッチスクリプトファイルからインストールする場合は、 <em> %% username%% 変数形式を使い </em> ます。 このインストール方法を使う場合は、%% 文字の変数をエスケープする必要があります。 この文字がないと、スクリプトは <em> 実行時ではなく、インストール時にユーザー名変数を展開し </em> ます。これにより、ue-v は、すべてのユーザーに対して1つの設定の保存場所を使用します。</p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=&quot;\server\settingsshare%%username%%&quot;</code></p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows PowerShell</p></td>
<td align="left"><p>Windows PowerShell プロンプトまたは Windows PowerShell スクリプトから UE-V Agent をインストールする場合は、 <em> % username% 変数形式を使用し </em> ます。</p></td>
<td align="left"><p><code>&amp; AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p>
<p><code>&amp; msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l<em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare%username%</code></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager ソフトウェアの展開などの電子ソフトウェアの配布</p></td>
<td align="left"><p>Configuration Manager を使用して UE-V Agent をインストールする場合は、 <em> ^% username ^% </em> 変数形式を使います。</p></td>
<td align="left"><p><code>AgentSetup.exe /quiet /norestart /log &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p>
<p></p>
<p><code>msiexec.exe /i &quot;&lt;path to msi file&gt;&quot; /quiet /norestart /l</em>v &quot;%temp%\UE-VAgentInstaller.log&quot; SettingsStoragePath=\server\settingsshare^%username^%</code></p></td>
</tr>
</tbody>
</table>



**注**  
UE-V エージェントをインストールするには、管理者権限が必要です。 UE-V Agent を実行するには、コンピューターの再起動が必要です。



### <a href="" id="params"></a>UE-V エージェントの展開用のコマンドラインパラメーター

UE-V Agent のコマンドラインパラメーターは次のとおりです。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>コマンドラインパラメーター</strong></th>
<th align="left"><strong>定義</strong></th>
<th align="left"><strong>備考</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/help または/h または/?</p></td>
<td align="left"><p>[AgentSetup.exe 使用状況] ダイアログボックスを表示します。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>SettingsStoragePath</p></td>
<td align="left"><p>設定が保存される場所を定義する汎用名前付け規則 (UNC) パスを示します。</p></td>
<td align="left"><div class="alert">
<strong>重要</strong><br/><p>UE-V 2.1 および UE-V 2.1 SP1 では、SettingsStoragePath を指定する必要があります。 Adhome Path 文字列を設定して、ユーザー&#39;s の Active Directory ホームパスを使用することを指定できます。 (<code>SettingsStoragePath = \share\path|AdHomePath</code> など)。</p>
<p>UE-V 2.0 では、SettingsStoragePath を空のままにして、代わりに Active Directory ホームパスを使用できます。</p>
</div>
<div>

</div>
<p>% username% または% computername% の環境変数が受け入れられます。 スクリプトでは、変数をエスケープする必要があります。</p>
<p><strong>既定値 </strong> : &lt; なし&gt;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Settingsstoragepaん g</p></td>
<td align="left"><p>インストール時にレジストリから SettingsStoragePath の値を取得します。</p></td>
<td align="left"><p>コマンドプロンプトで、次の例を入力して、特定の UNC ではなく Active Directory のホームパスを強制的に使用するように指定します。</p>
<p><code>msiexec.exe /i AgentSetupx64.msi acceptlicenseterms=true SettingsStoragePathReg=TRUE /quiet /norestart</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>SettingsTemplateCatalogPath</p></td>
<td align="left"><p>新しい設定場所テンプレートがチェックされた場所を定義する汎用名前付け規則 (UNC) パスを示します。</p></td>
<td align="left"><p>カスタム設定の場所テンプレートでのみ必須</p></td>
</tr>
<tr class="odd">
<td align="left"><p>RegisterMSTemplates</p></td>
<td align="left"><p>インストール時に既定の Microsoft テンプレートを登録する必要があるかどうかを指定します。</p></td>
<td align="left"><p>True |返し</p>
<p><strong>既定値 </strong> : True</p></td>
</tr>
<tr class="even">
<td align="left"><p>方法</p></td>
<td align="left"><p>使用する同期方法を指定します。</p></td>
<td align="left"><p>SyncProvider |-</p>
<p><strong>既定 </strong> : syncprovider</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SyncTimeoutInMilliseconds</p></td>
<td align="left"><p>コンピューターが設定の保存場所からユーザー設定を取得したときにタイムアウトするまでの時間 (ミリ秒単位) を指定します。</p></td>
<td align="left"><p><strong>既定値 </strong> : 2000 ミリ秒</p>
<p>(最大2秒待ちます)</p></td>
</tr>
<tr class="even">
<td align="left"><p>SyncEnabled</p></td>
<td align="left"><p>UE-V の同期を有効にするか、無効にするかを指定します。</p></td>
<td align="left"><p>True |返し</p>
<p><strong>既定値 </strong> : True</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Maxパッケージパッケージ</p></td>
<td align="left"><p>UE-V Agent でファイルのしきい値を超えたことを報告した場合に、設定パッケージのファイルサイズをバイト単位で指定します。</p></td>
<td align="left"><p>&lt;大きさ&gt;</p>
<p><strong>既定値 </strong> : なし (警告のしきい値なし)</p></td>
</tr>
<tr class="even">
<td align="left"><p>CEIPEnabled</p></td>
<td align="left"><p>カスタマーエクスペリエンス向上プログラムに参加するための設定を指定します。 True に設定 <strong> する </strong> と、インストーラー情報が Microsoft カスタマーエクスペリエンス向上プログラムのサイトにアップロードされます。 False に設定 <strong> する </strong> と、情報はアップロードされません。</p></td>
<td align="left"><p>True |返し</p>
<p><strong>既定値 </strong> : False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>NoRestart</p></td>
<td align="left"><p>UE-V エージェントがインストールされた後のコンピューターの再起動の遅延をサポートします。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>INSTALLFOLDER</p></td>
<td align="left"><p>UE-V Generator または UE-V Generator で別のインストールフォルダーを設定できるようにします。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>MUENABLED</p></td>
<td align="left"><p>セットアップで、Microsoft Update プログラムに含まれるオプションを受け入れることができます。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>ACCEPTLICENSETERMS</p></td>
<td align="left"><p>UE-V をサイレントインストールできるようにします。 <strong> </strong> Ue-v をサイレントインストールして、ユーザーが ue-v ライセンス条項を受け入れるという要件を回避するには、この設定を True にする必要があります。 False に設定 <strong> する </strong> か、空白のままにすると、エラーメッセージが表示され、ue-v はインストールされません。</p></td>
<td align="left"><div class="alert">
<strong>重要</strong><br/><p>UE-V をサイレントモードでインストールする場合は、このパラメーターを指定する必要があります。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>NORESTART</p></td>
<td align="left"><p>UE-V エージェントをインストールした後に、必須の再起動が行われないようにします。</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### UE-V Agent を更新する

UE-V Agent ソフトウェアの更新プログラムは、Microsoft Update を通じて提供されます。 UE-V Agent の更新プログラムを展開するには、エンタープライズソフトウェア配布 (ESD) インフラストラクチャシステムを使用します。

UE-V Agent のアップグレード中に、一般的な Microsoft アプリケーションと Windows 設定用の設定場所テンプレートの既定のグループが更新されることがあります。

### UE-V Agent をアップグレードする

UE-V Agent では、さまざまな新機能が導入され、エージェントが設定記憶域の共有にコンテンツをアップロードする方法とタイミングが変更されます。 アップグレードプロセスによって、これらの変更が自動化されます。 UE-V Agent をアップグレードするには、ユーザーのコンピューターで UE-V Agent インストールパッケージ (AgentSetup.exe、AgentSetupx86.msi、または AgentSetupx64.msi) を実行します。

**注**  
UE-V Agent をアップグレードする場合は、前の UE-V Agent をインストールしたのと同じインストーラータイプ (.exe ファイルまたは .msi パケット) を使用する必要があります。 たとえば、AgentSetup.exe を使用してインストールされた UE-V 1.0 エージェントをアップグレードするには、UE-V 2 AgentSetup.exe を使います。



エージェントセットアッププログラムを実行すると、次の構成が維持されます。

-   設定の記憶域のパス

-   レジストリの設定

-   スケジュールされたタスク (間隔の設定が既定値にリセットされる)

**注**  
Ue-v 1.0 Agent register エラーに登録されている UE-V 2. x 設定の場所テンプレートが Windows イベントログに登録されているコンピューター。



Microsoft System Center 2012 構成マネージャー、または別のエンタープライズソフトウェア配布ツールを使用して、UE-V Agent のアップグレードを自動化および配布することができます。

**推奨事項:** すべての UE-V 1.0 エージェントをコンピューティング環境でアップグレードすることをお勧めしますが、必須ではありません。 UE-V の設定の場所テンプレートは、設定の記憶域のパスの設定のみを共有するため、UE-V 1.0 エージェントとやり取りすることができます。 ただし、管理を簡素化して UE-V をサポートするために、展開を単一のエージェントバージョンに移行することをお勧めします。

### アップグレードに失敗した後に UE-V Agent を修復する

次のいずれかの操作を実行しようとすると、エラーが発生する可能性があります。

-   UE-V 1.0 から UE-V 2 へのアップグレード

-   新しいバージョンの Windows にアップグレードします。たとえば、Windows 7 から Windows 8 へ、または Windows 8 から Windows 8.1 にアップグレードします。

-   UE-V エージェントのアップグレード後にエージェントをアンインストールする

問題を解決するには、エージェントがインストールされているコンピューターのコマンドプロンプトで次のコマンドを入力して、UE-V Agent の修復を試みます。

``` syntax
msiexec.exe /f "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log
```

次に、新しいバージョンの UE-V Agent をインストールすることで、アンインストールプロセスまたはアップグレードを再試行できます。






## 関連トピック


[UE-V の展開を準備する](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[カスタムアプリケーションの UE-V 2. x の展開](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)









