---
title: UE-V 1.0 のセキュリティに関する考慮事項
description: UE-V 1.0 のセキュリティに関する考慮事項
author: dansimp
ms.assetid: c5cdf9ff-dc96-4491-98e9-0eada898ffe0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b503028ae327f92759fe0f64f33fe0cffc62b05c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823997"
---
# UE-V 1.0 のセキュリティに関する考慮事項


このトピックでは、Microsoft User Experience Virtualization (UE-V) に関するアカウントとグループ、ログファイル、およびその他のセキュリティ関連の考慮事項について簡単に説明します。 詳細については、ここに記載されているリンクを参照してください。

## UE-V 構成のセキュリティに関する考慮事項


**設定の保存共有を作成するときに、アクセス権が必要なユーザーへの共有アクセスを制限します。**

設定パッケージには個人情報が含まれている場合があるため、可能な限り保護するように注意する必要があります。 一般的に、次の操作を行います。

-   共有を、アクセス権が必要なユーザーのみに制限します。 特定の共有にリダイレクトされたフォルダーを持つユーザーのセキュリティグループを作成し、アクセスをこれらのユーザーのみに制限します。

-   共有を作成するときに、共有名の後に $ を付けることで共有を非表示にします。 これにより、カジュアルブラウザーからの共有が非表示になり、[マイネットワーク] に共有が表示されなくなります。

-   必要最小限のアクセス許可をユーザーに与えます。 必要な権限が下の表に表示されます。

    1.  [記憶域の場所の設定] フォルダーに対して、次の共有レベル (SMB) の権限を設定します。

        <table>
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left">ユーザーアカウント</th>
        <th align="left">推奨されるアクセス許可</th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p>すべてのユーザー</p></td>
        <td align="left"><p>権限なし</p></td>
        </tr>
        <tr class="even">
        <td align="left"><p>UE-V のセキュリティグループ</p></td>
        <td align="left"><p>フルコントロール</p></td>
        </tr>
        </tbody>
        </table>



~~~
2.  Set the following NTFS permissions for the settings storage location folder:

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">User account</th>
    <th align="left">Recommended permissions</th>
    <th align="left">Folder</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Creator/Owner</p></td>
    <td align="left"><p>No Permissions</p></td>
    <td align="left"><p>No Permissions</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Domain Admins</p></td>
    <td align="left"><p>Full Control</p></td>
    <td align="left"><p>This Folder, Subfolders and Files</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Security group of UE-V users</p></td>
    <td align="left"><p>List Folder/Read Data, Create Folders/Append Data</p></td>
    <td align="left"><p>This Folder Only</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Everyone</p></td>
    <td align="left"><p>Remove all Permissions</p></td>
    <td align="left"><p>No Permissions</p></td>
    </tr>
    </tbody>
    </table>



3.  Set the following share-level (SMB) permissions for the settings template catalog folder.

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">User account</th>
    <th align="left">Recommend permissions</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Everyone</p></td>
    <td align="left"><p>No Permissions</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Domain Computers</p></td>
    <td align="left"><p>Read Permission Levels</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Administrators</p></td>
    <td align="left"><p>Read/Write Permission Levels</p></td>
    </tr>
    </tbody>
    </table>



4.  Set the following NTFS permissions for the settings template catalog folder.

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">User account</th>
    <th align="left">Recommended permissions</th>
    <th align="left">Apply to</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Creator/Owner</p></td>
    <td align="left"><p>Full Control</p></td>
    <td align="left"><p>This Folder, Subfolders and Files</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Domain Computers</p></td>
    <td align="left"><p>List Folder Contents and Read</p></td>
    <td align="left"><p>This Folder, Subfolders and Files</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Everyone</p></td>
    <td align="left"><p>No Permissions</p></td>
    <td align="left"><p>No Permissions</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Administrators</p></td>
    <td align="left"><p>Full Control</p></td>
    <td align="left"><p>This Folder, Subfolders and Files</p></td>
    </tr>
    </tbody>
    </table>
~~~



### Windows Server 2003 以降のサーバーを使用して、リダイレクトされたファイル共有をホストする

ユーザー設定パッケージファイルには、クライアントコンピューターと設定パッケージを保存するサーバーの間で転送される個人情報が含まれています。 このため、ネットワーク上を移動している間もデータが保護されていることを確認する必要があります。

ユーザー設定データは、次の潜在的な脅威に対して脆弱です。ネットワーク上でのデータの傍受。ネットワーク上でのデータの改ざん。データをホストしているサーバーのスプーフィング。

Windows Server 2003 以上の一部の機能を使用すると、ユーザーデータをセキュリティで保護することができます。

-   **Kerberos** -kerberos は、windows 2000 および windows Server 2003 以降のすべてのバージョンで標準で搭載されています。 Kerberos は、ネットワークリソースに対する最高レベルのセキュリティを確保します。 NTLM はクライアントのみを認証します。Kerberos は、サーバーとクライアントを認証します。 NTLM が使用されている場合、クライアントはサーバーが有効であるかどうかを確認しません。 これは、ローミングプロファイルの場合と同様に、クライアントがサーバーと個人用ファイルを交換する場合に特に重要です。 Kerberos は、NTLM よりもセキュリティが強化されています。 Kerberos は、Windows NT バージョン4.0 またはそれ以前のオペレーティングシステムでは使用できません。

-   **Ipsec** -IP セキュリティプロトコル (ipsec) では、ネットワークレベルの認証、データの整合性、暗号化が提供されます。 IPsec では、次のことが保証されます。

    -   ローミングデータは、ルーティング中のデータの変更から安全です。

    -   ローミングされたデータは、傍受、表示、コピーから安全です。

    -   ローミングされたデータは、認証されていない当事者によるアクセスから安全です。

-   **Smb 署名**-サーバーメッセージブロック (smb) 認証プロトコルは、アクティブなメッセージと "man-in-the-middle" 攻撃を防止するメッセージ認証をサポートします。 SMB 署名では、各 SMB にデジタル署名を配置することによって、この認証が提供されます。 デジタル署名は、クライアントとサーバーの両方で確認されます。 SMB 署名を使用するには、まず smb クライアントと SMB サーバーの両方で SMB 署名を有効にするか、必須にする必要があります。 SMB 署名では、パフォーマンスが低下することに注意してください。 これによりネットワークの帯域幅は消費されませんが、クライアントとサーバー側ではより多くの CPU サイクルを使用します。

### ユーザーデータが保持されているボリュームには常に NTFS ファイルシステムを使用する

最も安全な構成については、UE-V の設定ファイルをホストしているサーバーで NTFS ファイルシステムを使用するように構成します。 FAT とは異なり、NTFS は随意アクセス制御リスト (Dacl) とシステムアクセス制御リスト (Sacl) をサポートしています。 ファイルに対して操作を実行できる Dacl と Sacl 制御、ファイルに対して実行される操作のログをトリガーするイベント。

### <a href="" id="do-not-rely-on-efs-to-encrypt-users--files-when-transmitted-over-the-network"></a>ネットワーク経由で送信されたユーザーのファイルを EFS に依存しないでください。

暗号化ファイルシステム (EFS) を使ってリモートサーバー上のファイルを暗号化する場合、暗号化されたデータはネットワーク経由で転送中に暗号化されません。このファイルは、ディスクに保存されている場合にのみ暗号化されます。

ただし、システムにインターネットプロトコルセキュリティ (IPsec) または Web 分散オーサリングとバージョン管理 (WebDAV) が含まれている場合は例外です。 IPsec は、TCP/IP ネットワーク経由で転送されているデータを暗号化します。 サーバー上の WebDAV フォルダーにコピーまたは移動する前に、ファイルが暗号化されている場合は、転送中とサーバーに保存されているファイルは暗号化されたままになります。

### オフラインファイルキャッシュを暗号化する

既定では、オフラインファイルキャッシュは Acl によって NTFS パーティションで保護されますが、キャッシュを暗号化すると、ローカルコンピューターのセキュリティがさらに強化されます。 既定では、ローカルコンピューターのキャッシュは暗号化されていないため、ネットワークからキャッシュされたすべての暗号化されたファイルは、ローカルコンピューターでは暗号化されません。 これは、環境によってはセキュリティ上のリスクを引き起こす可能性があります。

暗号化が有効になっていると、オフラインファイルキャッシュ内のすべてのファイルが暗号化されます。 これには、既存のファイルの暗号化、および後で追加されるファイルも含まれます。 ローカルコンピューター上のキャッシュコピーは影響を受けますが、関連付けられたネットワークコピーは変更されません。

キャッシュは、次の2つの方法のいずれかで暗号化できます。

1.  グループポリシーを使って行います。 -グループポリシーエディターで、コンピューター構成¥管理 Templates\\Network\\Offline ファイルにある [**オフラインファイルキャッシュの暗号化**] 設定を有効にします。

2.  手. -Windows エクスプローラーのコマンドメニューで、[ツール]、[フォルダーオプション] の順に選択します。 [オフラインファイル] タブを選択し、[**オフラインファイルを暗号化してデータを保護する**] チェックボックスをオンにします。

### UE-V Agent が各ユーザーのフォルダーを作成できるようにする

UE-V が最適に動作するようにするには、サーバー上でルート共有のみを作成し、UE-V Agent が各ユーザーのフォルダーを作成できるようにします。 UE-V は、適切なセキュリティを使用してこれらのユーザーフォルダーを作成します。

このアクセス許可構成により、ユーザーは設定ストレージのフォルダーを作成できます。 UE-V agent は、ユーザーのコンテキストで実行されているときに、settingspackage フォルダーを作成して、セキュリティで保護します。 ユーザーは、settingspackage フォルダーに対してフルコントロールを受け取ります。 他のユーザーがこのフォルダーへのアクセス権を継承していない。 個々のユーザーディレクトリを作成し、セキュリティで保護する必要はありません。 これは、ユーザーのコンテキストで実行されるエージェントによって自動的に行われます。

**注**  
セキュリティの追加は、設定の記憶域共有に対して Windows server を使用したときに構成できます。 UE-V は、ローカル管理者のグループまたは現在のユーザーが、設定パッケージが保存されているフォルダーの所有者であるかどうかを確認するように構成できます。 追加のセキュリティを有効にするには、次のコマンドを使用します。

1.  "RepositoryOwnerCheckEnabled" という名前の REG \ _DWORD レジストリキーをに追加 `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration` します。

2.  レジストリキーの値を1に設定します。

この構成設定が行われると、UE-V agent はローカル管理者のグループまたは現在のユーザーが settingspackage フォルダーの所有者であることを確認します。 サポートされていない場合は、UE-V agent でフォルダーへのアクセスが許可されません。



ユーザーのフォルダーを作成し、適切なアクセス許可が設定されていることを確認する必要がある場合。

フォルダーを precreate ないようにすることを強くお勧めします。代わりに、UE-V agent でユーザーのフォルダーを作成できるようにすることを強くお勧めします。

### <a href="" id="ensure-that-correct-permissions-are-set-when-storing-ue-v-settings-in-a-user-s-home-directory"></a>ユーザーのホームディレクトリで UE-V の設定を保存するときに、適切なアクセス許可が設定されていることを確認する

ユーザーのホームディレクトリに UE-V 設定をリダイレクトする場合は、ユーザーのホームディレクトリに対するアクセス許可が組織に対して適切に設定されていることを確認してください。

## 関連トピック


[UE-V 1.0 のセキュリティとプライバシー](security-and-privacy-for-ue-v-10.md)









