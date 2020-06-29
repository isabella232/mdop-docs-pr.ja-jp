---
title: MBAM 2.0 SP1 の概要
description: MBAM 2.0 SP1 の概要
author: dansimp
ms.assetid: 5ba89ed8-bb6e-407b-82c2-e2e36dd1078e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 73b92cd852d4f75f63f3dcba9f18167012b61401
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823554"
---
# MBAM 2.0 SP1 の概要

このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) 2.0 Service Pack 1 (SP1) での変更について説明します。 MBAM の一般的な説明については、「 [mbam 2.0](getting-started-with-mbam-20-mbam-2.md)の概要」を参照してください。

## <a href="" id="what-s-new-in-mbam-2-0-sp1"></a>MBAM 2.0 SP1 の新機能

このバージョンの MBAM には、次のような新機能があります。

### Windows 8.1、Windows Server 2012 R2、System Center 2012 R2 構成マネージャーのサポート

Microsoft BitLocker 管理および監視 (MBAM) 2.0 Service Pack 1 (SP1) では、Windows 8.1、Windows Server 2012 R2、System Center 2012 R2 構成マネージャーのサポートが追加されています。

### Microsoft SQL Server 2008 R2 SP2 のサポート

Microsoft BitLocker 管理および監視 (MBAM) 2.0 Service Pack 1 (SP1) では、Microsoft SQL Server 2008 R2 SP2 のサポートが追加されています。 Microsoft System Center Configuration Manager 2007 R2 を実行している場合は、Microsoft SQL Server 2008 R2 以降を使用する必要があります。

### 顧客フィードバックの重ね合わせ

MBAM 2.0 SP1 には、Microsoft BitLocker の管理と監視 (MBAM) 2.0 リリース以降に検出された問題に対処するための修正プログラムが含まれています。 これらの変更の一部として、Microsoft System Center Configuration Manager 2007 で MBAM を実行すると、[コンピューター名] フィールドが [BitLocker コンピューターのコンプライアンスと BitLocker エンタープライズ準拠の詳細] に表示されるようになりました。

### セルフサービスポータルと管理と監視の web サイトのポートにファイアウォールの例外を設定する必要がある

セルフサービスポータルと管理/監視 web サイトを構成するときは、指定したポートを介した通信を有効にするために、ファイアウォールの例外を設定する必要があります。 以前は、MBAM サーバーのインストールでは、Windows ファイアウォールでポートが自動的に開かれました。

### Configuration Manager で MBAM レポートの場所が変更されている

Configuration Manager の統合トポロジの MBAM レポートは、MBAM ノード内のサブフォルダーで利用できるようになりました。 サブフォルダー名は、サブフォルダー内のレポートの言語を表します。

### Configuration Manager を使用して MBAM をインストールするときに、プライマリサイトサーバーに MBAM をインストールする機能

Configuration Manager の統合トポロジを使用して MBAM をインストールする場合は、プライマリサイトサーバーまたは中央管理サイトサーバーに MBAM をインストールできます。 以前は、中央管理サイトサーバーに MBAM をインストールする必要がありました。

**重要**  
MBAM をインストールするサーバーは、階層のトップ層サーバーである必要があります。



MBAM インストールの動作は、Microsoft System Center Configuration Manager 2007 と Microsoft System Center 2012 構成マネージャーと次のように異なります。

-   **Configuration manager 2007** : 大規模な configuration manager 階層の一部であり、セントラルサイトの親サーバーがあるプライマリサイトサーバーに mbam をインストールすると、mbam はセントラルサイトの親サーバーを解決し、その親サーバー上のすべてのインストールアクションを実行します。 インストールアクションには、前提条件の確認や Configuration Manager オブジェクトとレポートのインストールが含まれます。 たとえば、セントラルサイトの親サーバーの子であるプライマリサイトサーバーに MBAM をインストールすると、MBAM は親サーバー上のすべての Configuration Manager オブジェクトとレポートをインストールします。 MBAM を親サーバーにインストールする場合、MBAM はその親サーバー上のすべてのインストールアクションを実行します。

-   **System Center 2012 構成マネージャー** : mbam をプライマリサイトサーバーまたはサーバーの全体管理サーバーにインストールする場合、mbam はそのサイトサーバー上のすべてのインストールアクションを実行します。

### <a href="" id="-------------configuration-manager-console-must-be-installed-on-the--computer-on-which-you-install-the-mbam-server"></a> MBAM サーバーをインストールするコンピューターに Configuration Manager コンソールがインストールされている必要がある

Configuration Manager の統合トポロジを使用して MBAM をインストールする場合は、MBAM をインストールするコンピューターに Configuration Manager コンソールをインストールする必要があります。 推奨されるアーキテクチャ (「はじめに」「 [Configuration manager での MBAM の使用](getting-started---using-mbam-with-configuration-manager.md)」で説明) を使用する場合は、Configuration Manager プライマリサイトサーバーに mbam をインストールします。

### Configuration Manager の統合トポロジの新しいセットアップコマンドラインパラメーター

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コマンドラインパラメーター</th>
<th align="left">説明</th>
<th align="left">例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>CM_SSRS_REMOTE_SERVER_NAME</p></td>
<td align="left"><p>MBAM がインストールされている同じ Configuration Manager サイトの一部であるリモートの SQL Server Reporting Services (SSRS) サーバーに Configuration Manager レポートをインストールできるようにします。 この値は、リモートの SSRS ポイントの役割サーバーの完全修飾ドメイン名に設定できます。</p></td>
<td align="left"><p>MbamSetup.exe CM_SSRS_REMOTE_SERVER_NAME = ssrsServer: .com</p></td>
</tr>
<tr class="even">
<td align="left"><p>CM_REPORTS_ONLY</p></td>
<td align="left"><p>Configuration Manager レポートのみをインストールできるようにします。これには、ベースライン、コレクション、構成項目などの他の Configuration Manager オブジェクトは必要ありません。</p>
<div class="alert">
<strong>注</strong><br/><p>このパラメーターを CM_REPORTS_COLLECTION_ID パラメーターと組み合わせる必要があります。</p>
</div>
<div>

</div>
<p>有効なパラメーター値:</p>
<ul>
<li><p>True</p></li>
<li><p>False</p></li>
</ul>
<p>リモートの SSRS ポイントの役割サーバーにのみレポートをインストールする場合は、このパラメーターを CM_SSRS_REMOTE_SERVER_NAME パラメーターと組み合わせることができます。</p>
<p>パラメーターを設定していない場合、または False に設定した場合、MBAM Setup はレポートを含むすべての Configuration Manager オブジェクトをインストールします。</p></td>
<td align="left"><p>MbamSetup.exe CM_REPORTS_ONLY = True</p>
<p>CM_REPORTS_COLLECTION_ID = SMS00001</p></td>
</tr>
<tr class="odd">
<td align="left"><p>CM_REPORTS_COLLECTION_ID</p></td>
<td align="left"><p>レポートのコンプライアンスデータが表示されるコレクションを識別する既存のコレクション ID。 任意のコレクション ID を指定できます。 "MBAM サポートされているコンピューター" コレクション ID を使用する必要はありません。</p></td>
<td align="left"><p>MbamSetup.exe CM_REPORTS_ONLY = True</p>
<p>CM_REPORTS_COLLECTION_ID = SMS00001</p></td>
</tr>
</tbody>
</table>



### セルフサービスポータルの通知テキストを有効または無効にする機能

MBAM 2.0 SP1 では、セルフサービスポータルの通知テキストをオフにすることができます。 以前は、通知テキストは既定で表示されていましたが、オフにすることはできませんでした。

**通知テキストをオフにするには**

1.  セルフサービスポータルをインストールしたサーバーで、[インターネットインフォメーションサービス (IIS)] を開き、[ ** &gt; Microsoft BitLocker 管理] および [セルフ &gt; サービス &gt; アプリケーション設定の監視**] のサイトに移動します。

2.  [**名前**] 列で、[ **displaynotice**] を選択し、値を**false**に設定します。

### ユーザーがより多くのセルフサービスポータル情報を参照するように、ヘルプデスクのテキストステートメントをローカライズする機能

ユーザーがセルフサービスポータルを使用しているときに追加のヘルプを取得する方法については、ローカライズされたバージョンのセルフサービスポータル "Helpデスクテキスト" ステートメントを構成できます。 次の手順で説明するように、ステートメントのローカライズされたテキストを構成すると、MBAM にローカライズされたバージョンが表示されます。 MBAM でローカライズされたバージョンが見つからない場合は、 **Helpデスクテキスト**パラメーターの値が表示されます。

**Helpデスクテキストステートメントのローカライズされたバージョンを表示するには**

1.  セルフサービスポータルをインストールしたサーバーで、[IIS] を開き、[ ** &gt; Microsoft BitLocker 管理] および [セルフ &gt; サービス &gt; アプリケーション設定の監視**] のサイトに移動します。

2.  [**操作**] ウィンドウの [**追加**] をクリックして、[**アプリケーション設定の追加**] ダイアログボックスを開きます。

3.  [**名前**] フィールドに「**ヘルプ**」と入力し &lt; *language* &gt; ます。ここで、 &lt; *言語* &gt; は、テキストの適切な言語コードです。 たとえば、ローカライズされたヘルプデスクのテキストステートメントをスペイン語で作成するには、パラメーターに「\ _es」という名前を入力します。 使用できる有効な言語コードの一覧については、「[国内言語サポート (NLS) API リファレンス](https://go.microsoft.com/fwlink/?LinkId=317947)」をご覧ください。

4.  [**値**] フィールドに、エンドユーザーに対して表示するローカライズされたテキストを入力します。

### セルフサービスポータルのヘルプの Url をローカライズする機能

既定でエンドユーザーに表示する、セルフサービスポータルのヘルプデスク Url のローカライズされたバージョンを構成できます。 次の手順で説明するように、ローカライズされたバージョンを作成すると、MBAM でローカライズされたバージョンが検索されて表示されます。 MBAM でローカライズされたバージョンが見つからない場合は、Helpデスク Url パラメーターに対して構成されている URL が表示されます。

**ローカライズされたヘルプデスクの Url を表示するには**

1.  セルフサービスポータルをインストールしたサーバーで、[IIS] を開き、[ ** &gt; Microsoft BitLocker 管理] および [セルフ &gt; サービス &gt; アプリケーション設定の監視**] のサイトに移動します。

2.  [**操作**] ウィンドウの [**追加**] をクリックして、[**アプリケーション設定の追加**] ダイアログボックスを開きます。

3.  [**名前**] フィールドに「**ヘルプ**」と入力し &lt; *language* &gt; ます。ここで、 &lt; *言語* &gt; は url の適切な言語コードです。 たとえば、スペイン語でヘルプのローカライズされた Url を作成するには、パラメーター Help"Url \ _es という名前を指定します。 使用できる有効な言語コードの一覧については、「[各国語サポート (NLS) API リファレンス](https://go.microsoft.com/fwlink/?LinkId=317947)」をご覧ください。

4.  [**値**] フィールドに、エンドユーザーに表示するローカライズされたヘルプデスクの url を入力します。

### セルフサービスポータル通知テキストのローカライズ機能

セルフサービスポータルで既定でエンドユーザーに表示する、ローカライズされた通知テキストを構成することができます。 通知テキストが表示された notice.txt ファイルは、次のルートディレクトリにあります。

&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website\\

ローカライズされた通知テキストを表示するには、ローカライズされた notice.txt ファイルを作成し、次のディレクトリの特定の言語フォルダーに保存します。

&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website\\

MBAM 次のルールに基づいて、通知テキストが表示されます。

-   適切な言語フォルダーにローカライズされた notice.txt ファイルを作成すると、MBAM にローカライズされた通知テキストが表示されます。

-   MBAM でローカライズされたバージョンの notice.txt ファイルが見つからない場合は、既定の notice.txt ファイルにテキストが表示されます。

-   MBAM が既定の notice.txt ファイルを見つけられない場合は、セルフサービスポータルに既定のテキストが表示されます。

**注**  
エンドユーザーのブラウザーが、対応する言語のサブフォルダーまたは notice.txt のない言語に設定されている場合は、次のルートディレクトリの notice.txt ファイルに含まれているテキストが表示されます。

&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website\\



**ローカライズされた notice.txt ファイルを作成するには**

1.  セルフサービスポータルをインストールしたサーバー上で、 &lt; 次のディレクトリに*言語*フォルダーを作成し &gt; ます。ここでは、言語がローカライズされた &lt; *language* &gt; 言語の名前であることを示します。

    &lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website\\

    **注**  
    一部の言語フォルダーは既に存在しているため、作成する必要はありません。 言語フォルダーを作成する必要がある場合は、言語フォルダーに使用できる有効な名前の一覧については、「[各国語サポート (NLS) API リファレンス](https://go.microsoft.com/fwlink/?LinkId=317947)」を参照してください &lt; *language* &gt; 。



2.  ローカライズされた通知テキストを含む notice.txt ファイルを作成します。

3.  notice.txt ファイルを [言語] フォルダーに保存し &lt; *language* &gt; ます。 たとえば、スペイン語でローカライズされた notice.txt ファイルを作成するには、ローカライズされた notice.txt ファイルを次のフォルダーに保存します。

    &lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website\\es-es

## MBAM 2.0 SP1 へのアップグレード


以前のバージョンの MBAM から MBAM 2.0 SP1 にアップグレードできます。

### MBAM インフラストラクチャのアップグレード

MBAM サーバーインフラストラクチャを MBAM 2.0 SP1 にアップグレードするには、次の手順を実行します。

**手動のインプレースサーバー置き換え**: 既存の mbam サーバーインフラストラクチャを手動でアンインストールしてから、mbam 2.0 SP1 サーバーインフラストラクチャをインストールする必要があります。 アップグレードを実行するためにデータベースを削除する必要はありません。 代わりに、MBAM の以前のバージョンが作成された既存のデータベースを選択します。 MBAM 2.0 SP1 アップグレードインストールでは、既存のデータベースを MBAM 2.0 SP1 に移行します。

**分散クライアントアップグレード**: スタンドアロンの mbam トポロジを使用している場合は、mbam 2.0 SP1 サーバーインフラストラクチャをインストールした後、Mbam クライアントを段階的にアップグレードできます。

Mbam Server インフラストラクチャをアップグレードした後、MBAM 1.0 または2.0 クライアントは、MBAM 2.0 SP1 サーバーに正常に報告し、回復データを保存しますが、コンプライアンスは、現在インストールされている MBAM クライアントバージョンで利用可能なポリシーに基づいています。 MBAM 2.0 SP1 ポリシーに対してレポート機能を有効にするには、クライアントコンピューターを MBAM 2.0 SP1 にアップグレードする必要があります。 クライアントコンピューターは、以前のクライアントをアンインストールせずに MBAM 2.0 SP1 クライアントにアップグレードできます。クライアントは、MBAM 2.0 SP1 ポリシーに基づいて、適用および報告を開始します。

MBAM サーバーのアップグレードの詳細については、「[以前のバージョンの mbam からアップグレード](upgrading-from-previous-versions-of-mbam.md)する」を参照してください。

### MBAM クライアントの MBAM 2.0 SP1 へのアップグレード

エンドユーザーコンピューターを MBAM 2.0 SP1 クライアントにアップグレードするには、各クライアントコンピューターで**MbamClientSetup.exe**を実行します。 インストーラーは、クライアントを MBAM 2.0 SP1 クライアントに自動的に更新します。 インストール後、クライアントコンピューターを再起動する必要はありません。 MBAM 2.0 SP1 クライアントは、MBAM 2.0 SP1 ポリシーの適用と報告を開始します。

MBAM を Configuration Manager で使用している場合は、MBAM クライアントコンピューターを MBAM 2.0 SP1 にアップグレードする必要があります。

MBAM クライアントコンピューターのアップグレードの詳細については、「[以前のバージョンの mbam からアップグレード](upgrading-from-previous-versions-of-mbam.md)する」を参照してください。

## Configuration Manager を使用して MBAM 2.0 SP1 をインストールまたはアップグレードする


このセクションでは、MBAM 2.0 SP1 を新規インストールとしてインストールする場合、または以前の MBAM 2.0 SP1 インストールへのアップグレードとしてインストールする場合の要件について説明します。

### Mbam 2.0 SP1 をインストールするのに必要なファイル (MBAM を Configuration Manager で使用している場合)

MBAM を初めてインストールするときに、MBAM 2.0 SP1 を System Center Configuration Manager で使用している場合、MBAM を構成マネージャーで正しく動作させるためには、mof ファイルを作成または編集する必要があります。

-   **構成の .mof ファイル**

    -   Configuration Manager 2007 を使っている場合は、「 **mbam 2.0 SP1 にアップグレードした場合に、構成マネージャー2007で mbam を使用**していて、この項目の後に mbam を使っている場合、構成の .mof ファイルを更新する必要があります。」

    -   System Center 2012 構成マネージャーを使用している場合は、「[構成の .Mof ファイルを編集](edit-the-configurationmof-file.md)する」の手順に従って構成の .mof ファイルを編集します。

-   **sms \ _def ファイル**: 「 [sms \ _def .Mof ファイルを作成または編集](create-or-edit-the-sms-defmof-file.md)する」の手順に従います。

### MBAM 2.0 SP1 にアップグレードして、Configuration Manager 2007 で MBAM を使用している場合に構成の .mof ファイルを更新する

MBAM 2.0 SP1 にアップグレードしていて、MBAM を Configuration Manager 2007 で使用している場合は、MBAM 2.0 SP1 が正しく動作するように構成の .mof ファイルを更新する必要があります。

**構成の .mof ファイルを更新するには、次の操作を行います。**

1.  Configuration Manager サーバーで、構成の .mof ファイルの場所を参照します。

    &lt;CMInstallLocation &gt; \\Inboxes\\clifiles.src\\hinv\\

    既定のインストールの場合、インストール場所は \ systemsystem% ¥ Program Files (x86) \\ Microsoft 構成マネージャーです。

2.  構成の .mof ファイルに追加したコードのブロックを確認して、削除します。 コードのブロックは、次の手順に示すようなものになります。

3.  次のコードブロックをコピーし、それを構成の .mof ファイルに追加して、次の必要な MBAM クラスをファイルに追加します。

    ``` syntax
    //===================================================
    // Microsoft BitLocker Administration and Monitoring 
    //===================================================

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32_BitLockerEncryptionDetails", NOFAIL) 

    [Union, ViewSources{"select DeviceId, BitlockerPersistentVolumeId, BitLockerManagementPersistentVolumeId, BitLockerManagementVolumeType, DriveLetter, Compliant, ReasonsForNonCompliance, KeyProtectorTypes, EncryptionMethod, ConversionStatus, ProtectionStatus, IsAutoUnlockEnabled from Mbam_Volume"}, ViewSpaces{"\\\\.\\root\\microsoft\\mbam"}, dynamic, Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class Win32_BitLockerEncryptionDetails
    {
        [PropertySources{"DeviceId"},key]
        String     DeviceId;
        [PropertySources{"BitlockerPersistentVolumeId"}]
        String     BitlockerPersistentVolumeId;
        [PropertySources{"BitLockerManagementPersistentVolumeId"}]
        String     MbamPersistentVolumeId;
        //UNKNOWN = 0, OS_Volume = 1, FIXED_VOLUME = 2, REMOVABLE_VOLUME = 3
        [PropertySources{"BitLockerManagementVolumeType"}]
        SInt32     MbamVolumeType;
        [PropertySources{"DriveLetter"}]
        String     DriveLetter;
        //VOLUME_NOT_COMPLIANT = 0, VOLUME_COMPLIANT = 1, NOT_APPLICABLE = 2
        [PropertySources{"Compliant"}]
        SInt32     Compliant;
        [PropertySources{"ReasonsForNonCompliance"}]
        SInt32     ReasonsForNonCompliance[];
        [PropertySources{"KeyProtectorTypes"}]
        SInt32     KeyProtectorTypes[];
        [PropertySources{"EncryptionMethod"}]
        SInt32     EncryptionMethod;
        [PropertySources{"ConversionStatus"}]
        SInt32     ConversionStatus;
        [PropertySources{"ProtectionStatus"}]
        SInt32     ProtectionStatus;
        [PropertySources{"IsAutoUnlockEnabled"}]
        Boolean     IsAutoUnlockEnabled;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32Reg_MBAMPolicy", NOFAIL)
     [DYNPROPS]
    Class Win32Reg_MBAMPolicy
    {
        [key]
        string KeyName;

        //General encryption requirements
        UInt32    OsDriveEncryption;
        UInt32    FixedDataDriveEncryption;
        UInt32    EncryptionMethod;

        //Required protectors properties
        UInt32    OsDriveProtector;
        UInt32    FixedDataDriveAutoUnlock;
        UInt32    FixedDataDrivePassphrase;

        //MBAM agent fields
        Uint32    MBAMPolicyEnforced;
        string    LastConsoleUser;
        datetime  UserExemptionDate;
        UInt32    MBAMMachineError;

        // Encoded computer name
        string    EncodedComputerName;
    };

     [DYNPROPS]
    Instance of Win32Reg_MBAMPolicy
    {
        KeyName="BitLocker policy";

        //General encryption requirements
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptOsDrive"),Dynamic,Provider("RegPropProv")]
        OsDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|EncryptionMethod"),Dynamic,Provider("RegPropProv")]
        EncryptionMethod;

        //Required protectors properties
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|OSVolumeProtectorPolicy"),Dynamic,Provider("RegPropProv")]
        OsDriveProtector;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|AutoUnlockFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveAutoUnlock;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|FDVPassphrase"),Dynamic,Provider("RegPropProv")]
        FixedDataDrivePassphrase;

        //MBAM agent fields
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMPolicyEnforced"),Dynamic,Provider("RegPropProv")]
        MBAMPolicyEnforced;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|LastConsoleUser"),Dynamic,Provider("RegPropProv")]
        LastConsoleUser;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|UserExemptionDate"),Dynamic,Provider("RegPropProv")]
        UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMMachineError"),Dynamic,Provider("RegPropProv")]
        MBAMMachineError;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|EncodedComputerName"),Dynamic,Provider("RegPropProv")]
        EncodedComputerName;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32Reg_MBAMPolicy_64", NOFAIL)
    [DYNPROPS]
    Class Win32Reg_MBAMPolicy_64
    {
        [key]
        string KeyName;

        //General encryption requirements
        UInt32    OsDriveEncryption;
        UInt32    FixedDataDriveEncryption;
        UInt32    EncryptionMethod;

        //Required protectors properties
        UInt32    OsDriveProtector;
        UInt32    FixedDataDriveAutoUnlock;
        UInt32    FixedDataDrivePassphrase;

        //MBAM agent fields
        Uint32    MBAMPolicyEnforced;
        string    LastConsoleUser;
        datetime  UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        UInt32    MBAMMachineError;

        // Encoded computer name
        string    EncodedComputerName;
    };

    [DYNPROPS]
    Instance of Win32Reg_MBAMPolicy_64
    {
        KeyName="BitLocker policy 64";

        //General encryption requirements
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptOsDrive"),Dynamic,Provider("RegPropProv")]
        OsDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|EncryptionMethod"),Dynamic,Provider("RegPropProv")]
        EncryptionMethod;

        //Required protectors properties
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|OSVolumeProtectorPolicy"),Dynamic,Provider("RegPropProv")]
        OsDriveProtector;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|AutoUnlockFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveAutoUnlock;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|FDVPassphrase"),Dynamic,Provider("RegPropProv")]
        FixedDataDrivePassphrase;

        //MBAM agent fields
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMPolicyEnforced"),Dynamic,Provider("RegPropProv")]
        MBAMPolicyEnforced;
         [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|LastConsoleUser"),Dynamic,Provider("RegPropProv")]
        LastConsoleUser;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|UserExemptionDate"),Dynamic,Provider("RegPropProv")]
        UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMMachineError"),Dynamic,Provider("RegPropProv")]
        MBAMMachineError;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|EncodedComputerName"),Dynamic,Provider("RegPropProv")]
        EncodedComputerName;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("CCM_OperatingSystemExtended", NOFAIL)
    [Union, ViewSources{"select Name,OperatingSystemSKU from Win32_OperatingSystem"}, ViewSpaces{"\\\\.\\root\\cimv2"},
    dynamic,Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class CCM_OperatingSystemExtended
    {
        [PropertySources{"Name"},key]
        string     Name;
        [PropertySources{"OperatingSystemSKU"}]
        uint32     SKU;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("CCM_ComputerSystemExtended", NOFAIL)
    [Union, ViewSources{"select Name,PCSystemType from Win32_ComputerSystem"}, ViewSpaces{"\\\\.\\root\\cimv2"},
    dynamic,Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class CCM_ComputerSystemExtended
    {
        [PropertySources{"Name"},key]
        string     Name;
        [PropertySources{"PCSystemType"}]
        uint16     PCSystemType;
    };

    //=======================================================
    // Microsoft BitLocker Administration and Monitoring end
    //=======================================================

    ```

### MBAM 2.0 SP1 の翻訳

MBAM 2.0 SP1 は、次の言語で利用できるようになりました。

-   英語 (米国) en-us
-   フランス語 (フランス) fr-fr
-   イタリア語 (イタリア) it IT IT
-   ドイツ語 (ドイツ) デデュープ
-   スペイン語、インターナショナルソート (スペイン) es
-   韓国語 (韓国) ko-KR
-   日本語 (日本) ja-jp
-   ポルトガル語 (ブラジル) pt-BR
-   ロシア語 (ロシア) ru-RU
-   繁体字中国語 zh-cn&platform
-   簡体字中国語 zh-cn&platform-CN

## MDOP 技術の入手方法

MBAM 2.0 SP1 は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。 MDOP は、Microsoft ソフトウェアアシュアランスの一部です。 Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。

## 関連トピック

[MBAM 2.0 SP1 のリリース ノート](release-notes-for-mbam-20-sp1.md)









