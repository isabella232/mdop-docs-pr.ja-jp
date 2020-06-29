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
# <span data-ttu-id="fb32b-103">UE-V 1.0 のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="fb32b-103">UE-V 1.0 Security Considerations</span></span>


<span data-ttu-id="fb32b-104">このトピックでは、Microsoft User Experience Virtualization (UE-V) に関するアカウントとグループ、ログファイル、およびその他のセキュリティ関連の考慮事項について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-104">This topic contains a brief overview of accounts and groups, log files, and other security-related considerations for Microsoft User Experience Virtualization (UE-V).</span></span> <span data-ttu-id="fb32b-105">詳細については、ここに記載されているリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="fb32b-105">For more information, follow the links that are provided here.</span></span>

## <span data-ttu-id="fb32b-106">UE-V 構成のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="fb32b-106">Security considerations for UE-V configuration</span></span>


**<span data-ttu-id="fb32b-107">設定の保存共有を作成するときに、アクセス権が必要なユーザーへの共有アクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-107">When you create the settings storage share, limit the share access to users that need access.</span></span>**

<span data-ttu-id="fb32b-108">設定パッケージには個人情報が含まれている場合があるため、可能な限り保護するように注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb32b-108">Because settings packages may contain personal information, you should take care to protect them as well as possible.</span></span> <span data-ttu-id="fb32b-109">一般的に、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="fb32b-109">In general, do the following:</span></span>

-   <span data-ttu-id="fb32b-110">共有を、アクセス権が必要なユーザーのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-110">Restrict the share to only the users that need access.</span></span> <span data-ttu-id="fb32b-111">特定の共有にリダイレクトされたフォルダーを持つユーザーのセキュリティグループを作成し、アクセスをこれらのユーザーのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-111">Create a security group for users that have redirected folders on a particular share, and limit access to only those users.</span></span>

-   <span data-ttu-id="fb32b-112">共有を作成するときに、共有名の後に $ を付けることで共有を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="fb32b-112">When you create the share, hide the share by putting a $ after the share name.</span></span> <span data-ttu-id="fb32b-113">これにより、カジュアルブラウザーからの共有が非表示になり、[マイネットワーク] に共有が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="fb32b-113">This will hide the share from casual browsers, and the share will not be visible in My Network Places.</span></span>

-   <span data-ttu-id="fb32b-114">必要最小限のアクセス許可をユーザーに与えます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-114">Only give users the minimum amount of permissions needed.</span></span> <span data-ttu-id="fb32b-115">必要な権限が下の表に表示されます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-115">The permissions needed are shown in the tables below.</span></span>

    1.  <span data-ttu-id="fb32b-116">[記憶域の場所の設定] フォルダーに対して、次の共有レベル (SMB) の権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-116">Set the following share-level (SMB) permissions for the setting storage location folder:</span></span>

        <table>
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><span data-ttu-id="fb32b-117">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="fb32b-117">User account</span></span></th>
        <th align="left"><span data-ttu-id="fb32b-118">推奨されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="fb32b-118">Recommended permissions</span></span></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><span data-ttu-id="fb32b-119">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="fb32b-119">Everyone</span></span></p></td>
        <td align="left"><p><span data-ttu-id="fb32b-120">権限なし</span><span class="sxs-lookup"><span data-stu-id="fb32b-120">No Permissions</span></span></p></td>
        </tr>
        <tr class="even">
        <td align="left"><p><span data-ttu-id="fb32b-121">UE-V のセキュリティグループ</span><span class="sxs-lookup"><span data-stu-id="fb32b-121">Security group of UE-V</span></span></p></td>
        <td align="left"><p><span data-ttu-id="fb32b-122">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="fb32b-122">Full Control</span></span></p></td>
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



### <span data-ttu-id="fb32b-123">Windows Server 2003 以降のサーバーを使用して、リダイレクトされたファイル共有をホストする</span><span class="sxs-lookup"><span data-stu-id="fb32b-123">Use Windows Server 2003 or later servers to host redirected file shares</span></span>

<span data-ttu-id="fb32b-124">ユーザー設定パッケージファイルには、クライアントコンピューターと設定パッケージを保存するサーバーの間で転送される個人情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fb32b-124">User settings package files contain personal information that is transferred between the client computer and the server that stores the settings packages.</span></span> <span data-ttu-id="fb32b-125">このため、ネットワーク上を移動している間もデータが保護されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb32b-125">Because of this, you should ensure that the data is protected while it travels over the network.</span></span>

<span data-ttu-id="fb32b-126">ユーザー設定データは、次の潜在的な脅威に対して脆弱です。ネットワーク上でのデータの傍受。ネットワーク上でのデータの改ざん。データをホストしているサーバーのスプーフィング。</span><span class="sxs-lookup"><span data-stu-id="fb32b-126">User settings data is vulnerable to these potential threats: interception of the data as it passes over the network; tampering with the data as it passes over the network; and spoofing of the server that hosts the data.</span></span>

<span data-ttu-id="fb32b-127">Windows Server 2003 以上の一部の機能を使用すると、ユーザーデータをセキュリティで保護することができます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-127">Several features of Windows Server 2003 and above can help to secure user data:</span></span>

-   <span data-ttu-id="fb32b-128">**Kerberos** -kerberos は、windows 2000 および windows Server 2003 以降のすべてのバージョンで標準で搭載されています。</span><span class="sxs-lookup"><span data-stu-id="fb32b-128">**Kerberos** - Kerberos is standard on all versions of Windows 2000 and Windows Server 2003 and later.</span></span> <span data-ttu-id="fb32b-129">Kerberos は、ネットワークリソースに対する最高レベルのセキュリティを確保します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-129">Kerberos ensures the highest level of security to network resources.</span></span> <span data-ttu-id="fb32b-130">NTLM はクライアントのみを認証します。Kerberos は、サーバーとクライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-130">NTLM authenticates the client only; Kerberos authenticates the server and the client.</span></span> <span data-ttu-id="fb32b-131">NTLM が使用されている場合、クライアントはサーバーが有効であるかどうかを確認しません。</span><span class="sxs-lookup"><span data-stu-id="fb32b-131">When NTLM is used, the client does not know whether the server is valid.</span></span> <span data-ttu-id="fb32b-132">これは、ローミングプロファイルの場合と同様に、クライアントがサーバーと個人用ファイルを交換する場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="fb32b-132">This is particularly important if the client is exchanging personal files with the server, as is the case with Roaming Profiles.</span></span> <span data-ttu-id="fb32b-133">Kerberos は、NTLM よりもセキュリティが強化されています。</span><span class="sxs-lookup"><span data-stu-id="fb32b-133">Kerberos provides better security than NTLM.</span></span> <span data-ttu-id="fb32b-134">Kerberos は、Windows NT バージョン4.0 またはそれ以前のオペレーティングシステムでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="fb32b-134">Kerberos is not available on Windows NT version 4.0 or earlier operating systems.</span></span>

-   <span data-ttu-id="fb32b-135">**Ipsec** -IP セキュリティプロトコル (ipsec) では、ネットワークレベルの認証、データの整合性、暗号化が提供されます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-135">**IPsec** - The IP Security Protocol (IPsec) provides network-level authentication, data integrity, and encryption.</span></span> <span data-ttu-id="fb32b-136">IPsec では、次のことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-136">IPsec ensures the following:</span></span>

    -   <span data-ttu-id="fb32b-137">ローミングデータは、ルーティング中のデータの変更から安全です。</span><span class="sxs-lookup"><span data-stu-id="fb32b-137">Roamed data is safe from data modification while en route.</span></span>

    -   <span data-ttu-id="fb32b-138">ローミングされたデータは、傍受、表示、コピーから安全です。</span><span class="sxs-lookup"><span data-stu-id="fb32b-138">Roamed data is safe from interception, viewing, or copying.</span></span>

    -   <span data-ttu-id="fb32b-139">ローミングされたデータは、認証されていない当事者によるアクセスから安全です。</span><span class="sxs-lookup"><span data-stu-id="fb32b-139">Roamed data is safe from being accessed by unauthenticated parties.</span></span>

-   <span data-ttu-id="fb32b-140">**Smb 署名**-サーバーメッセージブロック (smb) 認証プロトコルは、アクティブなメッセージと "man-in-the-middle" 攻撃を防止するメッセージ認証をサポートします。</span><span class="sxs-lookup"><span data-stu-id="fb32b-140">**SMB Signing** - The Server Message Block (SMB) authentication protocol supports message authentication which prevents active message and "man-in-the-middle" attacks.</span></span> <span data-ttu-id="fb32b-141">SMB 署名では、各 SMB にデジタル署名を配置することによって、この認証が提供されます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-141">SMB signing provides this authentication by placing a digital signature into each SMB.</span></span> <span data-ttu-id="fb32b-142">デジタル署名は、クライアントとサーバーの両方で確認されます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-142">The digital signature is then verified by both the client and the server.</span></span> <span data-ttu-id="fb32b-143">SMB 署名を使用するには、まず smb クライアントと SMB サーバーの両方で SMB 署名を有効にするか、必須にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fb32b-143">In order to use SMB signing, you must first either enable it or require it on both the SMB client and the SMB server.</span></span> <span data-ttu-id="fb32b-144">SMB 署名では、パフォーマンスが低下することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="fb32b-144">Note that the SMB signing imposes a performance penalty.</span></span> <span data-ttu-id="fb32b-145">これによりネットワークの帯域幅は消費されませんが、クライアントとサーバー側ではより多くの CPU サイクルを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-145">It does not consume any more network bandwidth, but it uses more CPU cycles on the client and server side.</span></span>

### <span data-ttu-id="fb32b-146">ユーザーデータが保持されているボリュームには常に NTFS ファイルシステムを使用する</span><span class="sxs-lookup"><span data-stu-id="fb32b-146">Always use the NTFS File system for volumes holding users data</span></span>

<span data-ttu-id="fb32b-147">最も安全な構成については、UE-V の設定ファイルをホストしているサーバーで NTFS ファイルシステムを使用するように構成します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-147">For the most secure configuration, configure servers that host the UE-V settings files to use the NTFS File System.</span></span> <span data-ttu-id="fb32b-148">FAT とは異なり、NTFS は随意アクセス制御リスト (Dacl) とシステムアクセス制御リスト (Sacl) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fb32b-148">Unlike FAT, NTFS supports Discretionary access control lists (DACLs) and system access control lists (SACLs).</span></span> <span data-ttu-id="fb32b-149">ファイルに対して操作を実行できる Dacl と Sacl 制御、ファイルに対して実行される操作のログをトリガーするイベント。</span><span class="sxs-lookup"><span data-stu-id="fb32b-149">DACLs and SACLs control who can perform operations on a file and what events will trigger the logging of actions performed on a file.</span></span>

### <a href="" id="do-not-rely-on-efs-to-encrypt-users--files-when-transmitted-over-the-network"></a><span data-ttu-id="fb32b-150">ネットワーク経由で送信されたユーザーのファイルを EFS に依存しないでください。</span><span class="sxs-lookup"><span data-stu-id="fb32b-150">Do not rely on EFS to encrypt users’ files when transmitted over the network</span></span>

<span data-ttu-id="fb32b-151">暗号化ファイルシステム (EFS) を使ってリモートサーバー上のファイルを暗号化する場合、暗号化されたデータはネットワーク経由で転送中に暗号化されません。このファイルは、ディスクに保存されている場合にのみ暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-151">When you use Encrypting File System (EFS) to encrypt files on a remote server, the encrypted data is not encrypted during transit over the network; It only becomes encrypted when stored on disk.</span></span>

<span data-ttu-id="fb32b-152">ただし、システムにインターネットプロトコルセキュリティ (IPsec) または Web 分散オーサリングとバージョン管理 (WebDAV) が含まれている場合は例外です。</span><span class="sxs-lookup"><span data-stu-id="fb32b-152">The exceptions to this are when your system includes Internet Protocol security (IPsec) or Web Distributed Authoring and Versioning (WebDAV).</span></span> <span data-ttu-id="fb32b-153">IPsec は、TCP/IP ネットワーク経由で転送されているデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-153">IPsec encrypts data while it is transported over a TCP/IP network.</span></span> <span data-ttu-id="fb32b-154">サーバー上の WebDAV フォルダーにコピーまたは移動する前に、ファイルが暗号化されている場合は、転送中とサーバーに保存されているファイルは暗号化されたままになります。</span><span class="sxs-lookup"><span data-stu-id="fb32b-154">If the file is encrypted before being copied or moved to a WebDAV folder on a server, it will remain encrypted during the transmission and while it is stored on the server.</span></span>

### <span data-ttu-id="fb32b-155">オフラインファイルキャッシュを暗号化する</span><span class="sxs-lookup"><span data-stu-id="fb32b-155">Encrypt the Offline Files cache</span></span>

<span data-ttu-id="fb32b-156">既定では、オフラインファイルキャッシュは Acl によって NTFS パーティションで保護されますが、キャッシュを暗号化すると、ローカルコンピューターのセキュリティがさらに強化されます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-156">By default, the Offline Files cache is protected on NTFS partitions by ACLs, but encrypting the cache further enhances security on a local computer.</span></span> <span data-ttu-id="fb32b-157">既定では、ローカルコンピューターのキャッシュは暗号化されていないため、ネットワークからキャッシュされたすべての暗号化されたファイルは、ローカルコンピューターでは暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="fb32b-157">By default, the cache on the local computer is not encrypted, so any encrypted files cached from the network will not be encrypted on the local computer.</span></span> <span data-ttu-id="fb32b-158">これは、環境によってはセキュリティ上のリスクを引き起こす可能性があります。</span><span class="sxs-lookup"><span data-stu-id="fb32b-158">This may pose a security risk in some environments.</span></span>

<span data-ttu-id="fb32b-159">暗号化が有効になっていると、オフラインファイルキャッシュ内のすべてのファイルが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-159">When encryption is enabled, all files in the Offline Files cache are encrypted.</span></span> <span data-ttu-id="fb32b-160">これには、既存のファイルの暗号化、および後で追加されるファイルも含まれます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-160">This includes encrypting existing files as well as files that are added later.</span></span> <span data-ttu-id="fb32b-161">ローカルコンピューター上のキャッシュコピーは影響を受けますが、関連付けられたネットワークコピーは変更されません。</span><span class="sxs-lookup"><span data-stu-id="fb32b-161">The cached copy on the local computer is affected, but the associated network copy is not.</span></span>

<span data-ttu-id="fb32b-162">キャッシュは、次の2つの方法のいずれかで暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-162">The cache can be encrypted in one of two ways:</span></span>

1.  <span data-ttu-id="fb32b-163">グループポリシーを使って行います。</span><span class="sxs-lookup"><span data-stu-id="fb32b-163">Via Group Policy.</span></span> <span data-ttu-id="fb32b-164">-グループポリシーエディターで、コンピューター構成¥管理 Templates\\Network\\Offline ファイルにある [**オフラインファイルキャッシュの暗号化**] 設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="fb32b-164">- Enable the **Encrypt the Offline Files Cache** setting, located at Computer Configuration\\Administrative Templates\\Network\\Offline Files, in the Group Policy editor.</span></span>

2.  <span data-ttu-id="fb32b-165">手.</span><span class="sxs-lookup"><span data-stu-id="fb32b-165">Manually.</span></span> <span data-ttu-id="fb32b-166">-Windows エクスプローラーのコマンドメニューで、[ツール]、[フォルダーオプション] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-166">- Select Tools and then Folder Options in the command menu of Windows Explorer.</span></span> <span data-ttu-id="fb32b-167">[オフラインファイル] タブを選択し、[**オフラインファイルを暗号化してデータを保護する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="fb32b-167">Select the Offline Files tab, and then select the **Encrypt offline files to secure data** check box.</span></span>

### <span data-ttu-id="fb32b-168">UE-V Agent が各ユーザーのフォルダーを作成できるようにする</span><span class="sxs-lookup"><span data-stu-id="fb32b-168">Let the UE-V Agent create folders for each user</span></span>

<span data-ttu-id="fb32b-169">UE-V が最適に動作するようにするには、サーバー上でルート共有のみを作成し、UE-V Agent が各ユーザーのフォルダーを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="fb32b-169">To ensure that UE-V works optimally, create only the root share on the server, and let the UE-V Agent create the folders for each user.</span></span> <span data-ttu-id="fb32b-170">UE-V は、適切なセキュリティを使用してこれらのユーザーフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-170">UE-V will create these user folders with the appropriate security.</span></span>

<span data-ttu-id="fb32b-171">このアクセス許可構成により、ユーザーは設定ストレージのフォルダーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-171">This permission configuration allows users to create folders for settings storage.</span></span> <span data-ttu-id="fb32b-172">UE-V agent は、ユーザーのコンテキストで実行されているときに、settingspackage フォルダーを作成して、セキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-172">The UE-V agent creates and secures a settingspackage folder while running in the context of the user.</span></span> <span data-ttu-id="fb32b-173">ユーザーは、settingspackage フォルダーに対してフルコントロールを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="fb32b-173">The user receives full control to their settingspackage folder.</span></span> <span data-ttu-id="fb32b-174">他のユーザーがこのフォルダーへのアクセス権を継承していない。</span><span class="sxs-lookup"><span data-stu-id="fb32b-174">Other users do not inherit access to this folder.</span></span> <span data-ttu-id="fb32b-175">個々のユーザーディレクトリを作成し、セキュリティで保護する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="fb32b-175">You do not need to create and secure individual user directories.</span></span> <span data-ttu-id="fb32b-176">これは、ユーザーのコンテキストで実行されるエージェントによって自動的に行われます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-176">This will be done automatically by the agent that runs in the context of the user.</span></span>

**<span data-ttu-id="fb32b-177">注</span><span class="sxs-lookup"><span data-stu-id="fb32b-177">Note</span></span>**  
<span data-ttu-id="fb32b-178">セキュリティの追加は、設定の記憶域共有に対して Windows server を使用したときに構成できます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-178">Additional security can be configured when a Windows server is utilized for the settings storage share.</span></span> <span data-ttu-id="fb32b-179">UE-V は、ローカル管理者のグループまたは現在のユーザーが、設定パッケージが保存されているフォルダーの所有者であるかどうかを確認するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="fb32b-179">UE-V can be configured to verify that either the local administrator's group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="fb32b-180">追加のセキュリティを有効にするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-180">To enable additional security use the following command:</span></span>

1.  <span data-ttu-id="fb32b-181">"RepositoryOwnerCheckEnabled" という名前の REG \ _DWORD レジストリキーをに追加 `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration` します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-181">Add a REG\_DWORD registry key named "RepositoryOwnerCheckEnabled" to `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="fb32b-182">レジストリキーの値を1に設定します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-182">Set registry key value to 1.</span></span>

<span data-ttu-id="fb32b-183">この構成設定が行われると、UE-V agent はローカル管理者のグループまたは現在のユーザーが settingspackage フォルダーの所有者であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="fb32b-183">When this configuration setting is in place, the UE-V agent verifies that the local administrator’s group or current user is the owner of the settingspackage folder.</span></span> <span data-ttu-id="fb32b-184">サポートされていない場合は、UE-V agent でフォルダーへのアクセスが許可されません。</span><span class="sxs-lookup"><span data-stu-id="fb32b-184">If not, then the UE-V agent will not allow access to the folder.</span></span>



<span data-ttu-id="fb32b-185">ユーザーのフォルダーを作成し、適切なアクセス許可が設定されていることを確認する必要がある場合。</span><span class="sxs-lookup"><span data-stu-id="fb32b-185">If you must create folders for the users and ensure that you have the correct permissions set.</span></span>

<span data-ttu-id="fb32b-186">フォルダーを precreate ないようにすることを強くお勧めします。代わりに、UE-V agent でユーザーのフォルダーを作成できるようにすることを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fb32b-186">We strongly recommend that you do not precreate folders and that instead, you allow the UE-V agent to create the folder for the user.</span></span>

### <a href="" id="ensure-that-correct-permissions-are-set-when-storing-ue-v-settings-in-a-user-s-home-directory"></a><span data-ttu-id="fb32b-187">ユーザーのホームディレクトリで UE-V の設定を保存するときに、適切なアクセス許可が設定されていることを確認する</span><span class="sxs-lookup"><span data-stu-id="fb32b-187">Ensure that correct permissions are set when storing UE-V settings in a user’s home directory</span></span>

<span data-ttu-id="fb32b-188">ユーザーのホームディレクトリに UE-V 設定をリダイレクトする場合は、ユーザーのホームディレクトリに対するアクセス許可が組織に対して適切に設定されていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="fb32b-188">If you redirect UE-V settings to a user’s home directory, be sure that the permissions on the user's home directory are set appropriately for your organization.</span></span>

## <span data-ttu-id="fb32b-189">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fb32b-189">Related topics</span></span>


[<span data-ttu-id="fb32b-190">UE-V 1.0 のセキュリティとプライバシー</span><span class="sxs-lookup"><span data-stu-id="fb32b-190">Security and Privacy for UE-V 1.0</span></span>](security-and-privacy-for-ue-v-10.md)









