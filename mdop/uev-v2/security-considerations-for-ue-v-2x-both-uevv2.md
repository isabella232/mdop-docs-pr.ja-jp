---
title: UE-V 2.x のセキュリティに関する考慮事項
description: UE-V 2.x のセキュリティに関する考慮事項
author: dansimp
ms.assetid: 9d5c3cae-9fcb-4dea-bd67-741b3dea63be
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8e24e9e37de11053663bb90974fabf2ff369aeca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824664"
---
# <span data-ttu-id="0ba25-103">UE-V 2.x のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="0ba25-103">Security Considerations for UE-V 2.x</span></span>


<span data-ttu-id="0ba25-104">このトピックでは、Microsoft User Experience Virtualization (UE-V) 2.0、2.1、2.1 SP1 のアカウントとグループ、ログファイル、およびその他のセキュリティ関連の考慮事項について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-104">This topic contains a brief overview of accounts and groups, log files, and other security-related considerations for Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1.</span></span> <span data-ttu-id="0ba25-105">詳細については、ここに記載されているリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="0ba25-105">For more information, follow the links that are provided here.</span></span>

## <span data-ttu-id="0ba25-106">UE-V 構成のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="0ba25-106">Security considerations for UE-V configuration</span></span>


<span data-ttu-id="0ba25-107">**重要** 設定の保存共有を作成するときに、アクセス権が必要なユーザーへの共有アクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-107">**Important** When you create the settings storage share, limit the share access to users who require access.</span></span>

 

<span data-ttu-id="0ba25-108">設定パッケージには個人情報が含まれている場合があるため、可能な限り、それらを保護する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ba25-108">Because settings packages might contain personal information, you should take care to protect them as well as possible.</span></span> <span data-ttu-id="0ba25-109">一般的に、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0ba25-109">In general, do the following:</span></span>

-   <span data-ttu-id="0ba25-110">共有を、アクセスを必要とするユーザーのみに制限します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-110">Restrict the share to only those users who require access.</span></span> <span data-ttu-id="0ba25-111">特定の共有でフォルダーをリダイレクトし、それらのユーザーのみにアクセスを制限するユーザーのセキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-111">Create a security group for users who have redirected folders on a particular share and limit access to only those users.</span></span>

-   <span data-ttu-id="0ba25-112">共有を作成するときに、共有名の後に $ を付けることで共有を非表示にします。</span><span class="sxs-lookup"><span data-stu-id="0ba25-112">When you create the share, hide the share by putting a $ after the share name.</span></span> <span data-ttu-id="0ba25-113">この追加により、カジュアルブラウザーからの共有が非表示になり、[マイネットワーク] に共有が表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="0ba25-113">This addition hides the share from casual browsers, and the share is not visible in My Network Places.</span></span>

-   <span data-ttu-id="0ba25-114">ユーザーに最低限必要なアクセス許可の最小量のみを付与します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-114">Only give users the minimum amount of permissions that they must have.</span></span> <span data-ttu-id="0ba25-115">次の表は、必要な権限を示しています。</span><span class="sxs-lookup"><span data-stu-id="0ba25-115">The following tables show the required permissions.</span></span>

    1.  <span data-ttu-id="0ba25-116">[記憶域の場所の設定] フォルダーに、次の共有レベルの SMB アクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-116">Set the following share-level SMB permissions for the setting storage location folder.</span></span>

        | <span data-ttu-id="0ba25-117">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="0ba25-117">User account</span></span> | <span data-ttu-id="0ba25-118">推奨されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0ba25-118">Recommended permissions</span></span> |
        | - | - |
        | <span data-ttu-id="0ba25-119">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="0ba25-119">Everyone</span></span> | <span data-ttu-id="0ba25-120">権限なし</span><span class="sxs-lookup"><span data-stu-id="0ba25-120">No permissions</span></span> |
        |<span data-ttu-id="0ba25-121">UE-V のセキュリティグループ</span><span class="sxs-lookup"><span data-stu-id="0ba25-121">Security group of UE-V</span></span> | <span data-ttu-id="0ba25-122">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="0ba25-122">Full control</span></span> |

    2.  <span data-ttu-id="0ba25-123">[設定の保存場所] フォルダーに、次の NTFS ファイルシステムの権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-123">Set the following NTFS file system permissions for the settings storage location folder.</span></span>

        | <span data-ttu-id="0ba25-124">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="0ba25-124">User account</span></span> | <span data-ttu-id="0ba25-125">推奨されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0ba25-125">Recommended permissions</span></span> | <span data-ttu-id="0ba25-126">Folder</span><span class="sxs-lookup"><span data-stu-id="0ba25-126">Folder</span></span> |
        | - | - | - |
        | <span data-ttu-id="0ba25-127">作成者/所有者</span><span class="sxs-lookup"><span data-stu-id="0ba25-127">Creator/Owner</span></span> | <span data-ttu-id="0ba25-128">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="0ba25-128">Full control</span></span> | <span data-ttu-id="0ba25-129">サブフォルダーとファイルのみ</span><span class="sxs-lookup"><span data-stu-id="0ba25-129">Subfolders and files only</span></span>|
        | <span data-ttu-id="0ba25-130">ドメイン管理者</span><span class="sxs-lookup"><span data-stu-id="0ba25-130">Domain Admins</span></span> | <span data-ttu-id="0ba25-131">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="0ba25-131">Full control</span></span> | <span data-ttu-id="0ba25-132">このフォルダー、サブフォルダー、ファイル</span><span class="sxs-lookup"><span data-stu-id="0ba25-132">This folder, subfolders, and files</span></span> |
        | <span data-ttu-id="0ba25-133">UE-V ユーザーのセキュリティグループ</span><span class="sxs-lookup"><span data-stu-id="0ba25-133">Security group of UE-V users</span></span> | <span data-ttu-id="0ba25-134">フォルダーの一覧/データの読み取り、フォルダーの作成/データの追加を行う</span><span class="sxs-lookup"><span data-stu-id="0ba25-134">List folder/read data, create folders/append data</span></span> | <span data-ttu-id="0ba25-135">このフォルダーのみ</span><span class="sxs-lookup"><span data-stu-id="0ba25-135">This folder only</span></span> |
        | <span data-ttu-id="0ba25-136">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="0ba25-136">Everyone</span></span> | <span data-ttu-id="0ba25-137">すべての権限を削除する</span><span class="sxs-lookup"><span data-stu-id="0ba25-137">Remove all permissions</span></span> | <span data-ttu-id="0ba25-138">権限なし</span><span class="sxs-lookup"><span data-stu-id="0ba25-138">No permissions</span></span> |

    3.  <span data-ttu-id="0ba25-139">設定テンプレートカタログフォルダーに対して、次の共有レベルの SMB アクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-139">Set the following share-level SMB permissions for the settings template catalog folder.</span></span>

        | <span data-ttu-id="0ba25-140">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="0ba25-140">User account</span></span> | <span data-ttu-id="0ba25-141">権限の推奨</span><span class="sxs-lookup"><span data-stu-id="0ba25-141">Recommend permissions</span></span> |
        | - | - |
        | <span data-ttu-id="0ba25-142">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="0ba25-142">Everyone</span></span> | <span data-ttu-id="0ba25-143">権限なし</span><span class="sxs-lookup"><span data-stu-id="0ba25-143">No permissions</span></span> |
        | <span data-ttu-id="0ba25-144">ドメインコンピューター</span><span class="sxs-lookup"><span data-stu-id="0ba25-144">Domain computers</span></span> | <span data-ttu-id="0ba25-145">アクセス許可レベルの読み取り</span><span class="sxs-lookup"><span data-stu-id="0ba25-145">Read permission Levels</span></span> |
        | <span data-ttu-id="0ba25-146">管理者</span><span class="sxs-lookup"><span data-stu-id="0ba25-146">Administrators</span></span> | <span data-ttu-id="0ba25-147">読み取り/書き込みアクセス許可レベル</span><span class="sxs-lookup"><span data-stu-id="0ba25-147">Read/write permission levels</span></span> |
         
    4.  <span data-ttu-id="0ba25-148">設定テンプレートカタログフォルダーに対して、次の NTFS アクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-148">Set the following NTFS permissions for the settings template catalog folder.</span></span>

        | <span data-ttu-id="0ba25-149">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="0ba25-149">User account</span></span> | <span data-ttu-id="0ba25-150">推奨されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="0ba25-150">Recommended permissions</span></span> | <span data-ttu-id="0ba25-151">適用対象</span><span class="sxs-lookup"><span data-stu-id="0ba25-151">Apply to</span></span> |
        | - | - | - |
        | <span data-ttu-id="0ba25-152">作成者/所有者</span><span class="sxs-lookup"><span data-stu-id="0ba25-152">Creator/Owner</span></span> | <span data-ttu-id="0ba25-153">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="0ba25-153">Full control</span></span> | <span data-ttu-id="0ba25-154">このフォルダー、サブフォルダー、ファイル</span><span class="sxs-lookup"><span data-stu-id="0ba25-154">This folder, subfolders, and files</span></span> |
        | <span data-ttu-id="0ba25-155">ドメインコンピューター</span><span class="sxs-lookup"><span data-stu-id="0ba25-155">Domain Computers</span></span> | <span data-ttu-id="0ba25-156">フォルダーの内容と読み取り権限を一覧表示する</span><span class="sxs-lookup"><span data-stu-id="0ba25-156">List folder contents and Read permissions</span></span> | <span data-ttu-id="0ba25-157">このフォルダー、サブフォルダー、ファイル</span><span class="sxs-lookup"><span data-stu-id="0ba25-157">This folder, subfolders, and files</span></span>|
        | <span data-ttu-id="0ba25-158">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="0ba25-158">Everyone</span></span>| <span data-ttu-id="0ba25-159">権限なし</span><span class="sxs-lookup"><span data-stu-id="0ba25-159">No permissions</span></span>| <span data-ttu-id="0ba25-160">権限なし</span><span class="sxs-lookup"><span data-stu-id="0ba25-160">No permissions</span></span>|
        | <span data-ttu-id="0ba25-161">管理者</span><span class="sxs-lookup"><span data-stu-id="0ba25-161">Administrators</span></span>| <span data-ttu-id="0ba25-162">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="0ba25-162">Full Control</span></span>| <span data-ttu-id="0ba25-163">このフォルダー、サブフォルダー、ファイル</span><span class="sxs-lookup"><span data-stu-id="0ba25-163">This folder, subfolders, and files</span></span>|

### <span data-ttu-id="0ba25-164">リダイレクトされたファイル共有をホストするには、WindowsServer2003 のように WindowsServer を使用します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-164">Use WindowsServer as of WindowsServer2003 to host redirected file shares</span></span>

<span data-ttu-id="0ba25-165">ユーザー設定パッケージファイルには、クライアントコンピューターと設定パッケージを保存するサーバーの間で転送される個人情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0ba25-165">User settings package files contain personal information that is transferred between the client computer and the server that stores the settings packages.</span></span> <span data-ttu-id="0ba25-166">このプロセスにより、ネットワーク上を移動している間もデータが保護されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ba25-166">Because of this process, you should ensure that the data is protected while it travels over the network.</span></span>

<span data-ttu-id="0ba25-167">ユーザー設定データは、ネットワーク上でのデータの傍受、ネットワーク上のデータの改ざん、データをホストしているサーバーのスプーフィングなど、潜在的な脅威の影響を受けます。</span><span class="sxs-lookup"><span data-stu-id="0ba25-167">User settings data is vulnerable to these potential threats: interception of the data as it passes over the network, tampering with the data as it passes over the network, and spoofing of the server that hosts the data.</span></span>

<span data-ttu-id="0ba25-168">Windows Server2003 の場合、Windows Server オペレーティングシステムのいくつかの機能を使用すると、ユーザーデータを保護することができます。</span><span class="sxs-lookup"><span data-stu-id="0ba25-168">As of Windows Server2003, several features of the Windows Server operating system can help secure user data:</span></span>

-   <span data-ttu-id="0ba25-169">**Kerberos** -kerberos は、WindowsServer2003 で始まるすべてのバージョンの Microsoft Windows2000Server および windowsserver で標準で使用されています。</span><span class="sxs-lookup"><span data-stu-id="0ba25-169">**Kerberos** - Kerberos is standard on all versions of Microsoft Windows2000Server and WindowsServer beginning with WindowsServer2003.</span></span> <span data-ttu-id="0ba25-170">Kerberos は、ネットワークリソースに対する最高レベルのセキュリティを確保します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-170">Kerberos ensures the highest level of security to network resources.</span></span> <span data-ttu-id="0ba25-171">NTLM はクライアントのみを認証します。Kerberos は、サーバーとクライアントを認証します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-171">NTLM authenticates the client only; Kerberos authenticates the server and the client.</span></span> <span data-ttu-id="0ba25-172">NTLM が使用されている場合、クライアントはサーバーが有効であるかどうかを確認しません。</span><span class="sxs-lookup"><span data-stu-id="0ba25-172">When NTLM is used, the client does not know whether the server is valid.</span></span> <span data-ttu-id="0ba25-173">この違いは、ローミングユーザープロファイルの場合と同様に、クライアントがサーバーと個人用ファイルを交換する場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="0ba25-173">This difference is particularly important if the client exchanges personal files with the server, as is the case with Roaming User Profiles.</span></span> <span data-ttu-id="0ba25-174">Kerberos は、NTLM よりもセキュリティが強化されています。</span><span class="sxs-lookup"><span data-stu-id="0ba25-174">Kerberos provides better security than NTLM.</span></span> <span data-ttu-id="0ba25-175">Kerberos は、Microsoft WindowsNTServer 4.0 またはそれ以前のオペレーティングシステムでは利用できません。</span><span class="sxs-lookup"><span data-stu-id="0ba25-175">Kerberos is not available on the Microsoft WindowsNTServer 4.0 or earlier operating systems.</span></span>

-   <span data-ttu-id="0ba25-176">**Ipsec** -IP セキュリティプロトコル (ipsec) では、ネットワークレベルの認証、データの整合性、暗号化が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0ba25-176">**IPsec** - The IP Security Protocol (IPsec) provides network-level authentication, data integrity, and encryption.</span></span> <span data-ttu-id="0ba25-177">IPsec では、次のことが保証されます。</span><span class="sxs-lookup"><span data-stu-id="0ba25-177">IPsec ensures the following:</span></span>

    -   <span data-ttu-id="0ba25-178">ローミングされたデータは、データがルーティングされている間、データの変更から安全です。</span><span class="sxs-lookup"><span data-stu-id="0ba25-178">Roamed data is safe from data modification while data is en route.</span></span>

    -   <span data-ttu-id="0ba25-179">ローミングされたデータは、傍受、表示、コピーから安全です。</span><span class="sxs-lookup"><span data-stu-id="0ba25-179">Roamed data is safe from interception, viewing, or copying.</span></span>

    -   <span data-ttu-id="0ba25-180">ローミングされたデータは、認証されていない当事者によるアクセスから安全です。</span><span class="sxs-lookup"><span data-stu-id="0ba25-180">Roamed data is safe from access by unauthenticated parties.</span></span>

-   <span data-ttu-id="0ba25-181">**Smb 署名**-サーバーメッセージブロック (SMB) 認証プロトコルは、メッセージ認証をサポートします。これにより、アクティブなメッセージと "man-in-the-middle" 攻撃が防止されます。</span><span class="sxs-lookup"><span data-stu-id="0ba25-181">**SMB Signing** - The Server Message Block (SMB) authentication protocol supports message authentication, which prevents active message and "man-in-the-middle" attacks.</span></span> <span data-ttu-id="0ba25-182">SMB 署名では、各 SMB にデジタル署名を配置することによって、この認証が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0ba25-182">SMB signing provides this authentication by placing a digital signature into each SMB.</span></span> <span data-ttu-id="0ba25-183">デジタル署名は、クライアントとサーバーの両方で確認されます。</span><span class="sxs-lookup"><span data-stu-id="0ba25-183">The digital signature is then verified by both the client and the server.</span></span> <span data-ttu-id="0ba25-184">SMB 署名を使用するには、まず SMB 署名を有効にするか、smb クライアントと SMB サーバーの両方で要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0ba25-184">In order to use SMB signing, you must first either enable it, or you must require it on both the SMB client and the SMB server.</span></span> <span data-ttu-id="0ba25-185">SMB 署名では、パフォーマンスが低下することに注意してください。</span><span class="sxs-lookup"><span data-stu-id="0ba25-185">Note that the SMB signing imposes a performance penalty.</span></span> <span data-ttu-id="0ba25-186">これによりネットワークの帯域幅は消費されませんが、クライアントとサーバー側ではより多くの CPU サイクルを使用します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-186">It does not consume any more network bandwidth, but it uses more CPU cycles on the client and server side.</span></span>

### <span data-ttu-id="0ba25-187">ユーザーデータが保持されているボリュームには常に NTFS ファイルシステムを使用する</span><span class="sxs-lookup"><span data-stu-id="0ba25-187">Always use the NTFS file system for volumes that hold user data</span></span>

<span data-ttu-id="0ba25-188">最も安全な構成については、UE-V の設定ファイルをホストしているサーバーで NTFS ファイルシステムを使用するように構成します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-188">For the most secure configuration, configure servers that host the UE-V settings files to use the NTFS file system.</span></span> <span data-ttu-id="0ba25-189">FAT ファイルシステムとは異なり、NTFS は随意アクセス制御リスト (Dacl) とシステムアクセス制御リスト (Sacl) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0ba25-189">Unlike the FAT file system, NTFS supports Discretionary access control lists (DACLs) and system access control lists (SACLs).</span></span> <span data-ttu-id="0ba25-190">Dacl と Sacl コントロールファイルに対して操作を実行できます。また、ファイルに対して実行される操作のログをトリガーするイベントが発生します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-190">DACLs and SACLs control who can perform operations on a file and what events trigger the logging of actions that is performed on a file.</span></span>

### <span data-ttu-id="0ba25-191">ネットワーク経由で送信されたユーザーファイルの暗号化を EFS に依存しない</span><span class="sxs-lookup"><span data-stu-id="0ba25-191">Do not rely on EFS to encrypt user files when they are transmitted over the network</span></span>

<span data-ttu-id="0ba25-192">暗号化ファイルシステム (EFS) を使ってリモートサーバー上のファイルを暗号化する場合、暗号化されたデータはネットワーク経由で転送中に暗号化されません。このファイルは、ディスクに保存されている場合にのみ暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="0ba25-192">When you use the Encrypting File System (EFS) to encrypt files on a remote server, the encrypted data is not encrypted during transit over the network; it only becomes encrypted when it is stored on disk.</span></span>

<span data-ttu-id="0ba25-193">この暗号化処理は、システムにインターネットプロトコルセキュリティ (IPsec) または Web 分散オーサリングとバージョン管理 (WebDAV) が含まれている場合は適用されません。</span><span class="sxs-lookup"><span data-stu-id="0ba25-193">This encryption process does not apply when your system includes Internet Protocol security (IPsec) or Web Distributed Authoring and Versioning (WebDAV).</span></span> <span data-ttu-id="0ba25-194">IPsec は、TCP/IP ネットワーク経由で転送されているデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-194">IPsec encrypts data while it is transported over a TCP/IP network.</span></span> <span data-ttu-id="0ba25-195">ファイルがサーバー上の WebDAV フォルダーにコピーまたは移動される前に、ファイルが暗号化されている場合は、転送中とサーバーに保存されているファイルは暗号化されたままになります。</span><span class="sxs-lookup"><span data-stu-id="0ba25-195">If the file is encrypted before it is copied or moved to a WebDAV folder on a server, it remains encrypted during the transmission and while it is stored on the server.</span></span>

### <span data-ttu-id="0ba25-196">UE-V Agent が各ユーザーのフォルダーを作成できるようにする</span><span class="sxs-lookup"><span data-stu-id="0ba25-196">Let the UE-V Agent create folders for each user</span></span>

<span data-ttu-id="0ba25-197">UE-V が最適に動作するようにするには、サーバー上でルート共有のみを作成し、UE-V Agent が各ユーザーのフォルダーを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0ba25-197">To ensure that UE-V works optimally, create only the root share on the server, and let the UE-V Agent create the folders for each user.</span></span> <span data-ttu-id="0ba25-198">UE-V は、適切なセキュリティを使用して、ユーザーフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-198">UE-V creates these user folders with the appropriate security.</span></span>

<span data-ttu-id="0ba25-199">このアクセス許可構成により、ユーザーは設定ストレージのフォルダーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0ba25-199">This permission configuration enables users to create folders for settings storage.</span></span> <span data-ttu-id="0ba25-200">UE-V Agent は、ユーザーのコンテキストで実行されているときに、設定パッケージフォルダーを作成して、セキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-200">The UE-V Agent creates and secures a settings package folder while it runs in the context of the user.</span></span> <span data-ttu-id="0ba25-201">ユーザーは、設定パッケージフォルダーに対してフルコントロールを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0ba25-201">Users receive full control to their settings package folder.</span></span> <span data-ttu-id="0ba25-202">他のユーザーがこのフォルダーへのアクセス権を継承していない。</span><span class="sxs-lookup"><span data-stu-id="0ba25-202">Other users do not inherit access to this folder.</span></span> <span data-ttu-id="0ba25-203">個々のユーザーディレクトリを作成し、セキュリティで保護する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="0ba25-203">You do not have to create and secure individual user directories.</span></span> <span data-ttu-id="0ba25-204">ユーザーのコンテキストで実行されるエージェントは、自動的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="0ba25-204">The agent that runs in the context of the user does it automatically.</span></span>

<span data-ttu-id="0ba25-205">**注** 設定の記憶域の共有に Windows Server を使用する場合は、追加のセキュリティを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="0ba25-205">**Note** Additional security can be configured when a Windows Server is used for the settings storage share.</span></span> <span data-ttu-id="0ba25-206">UE-V は、[ローカル管理者] グループまたは現在のユーザーが、設定パッケージが保存されているフォルダーの所有者であることを確認するように構成できます。</span><span class="sxs-lookup"><span data-stu-id="0ba25-206">UE-V can be configured to verify that either the local Administrators group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="0ba25-207">追加のセキュリティを有効にするには、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-207">To enable additional security, use the following command:</span></span>

1.  <span data-ttu-id="0ba25-208">REG \ _DWORD レジストリキーの RepositoryOwnerCheckEnabled をに追加 `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration` します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-208">Add the REG\_DWORD registry key RepositoryOwnerCheckEnabled to `HKEY_LOCAL_MACHINE\Software\Microsoft\UEV\Agent\Configuration`.</span></span>

2.  <span data-ttu-id="0ba25-209">レジストリキーの値を*1*に設定します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-209">Set the registry key value to *1*.</span></span>

<span data-ttu-id="0ba25-210">この構成設定が行われると、UE-V Agent はローカルの管理者グループまたは現在のユーザーが設定パッケージフォルダーの所有者であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-210">When this configuration setting is in place, the UE-V Agent verifies that the local Administrators group or current user is the owner of the settings package folder.</span></span> <span data-ttu-id="0ba25-211">許可されていない場合は、UE-V Agent でフォルダーへのアクセスが許可されません。</span><span class="sxs-lookup"><span data-stu-id="0ba25-211">If not, then the UE-V Agent does not grant access to the folder.</span></span>

 

<span data-ttu-id="0ba25-212">ユーザー用にフォルダーを作成する必要がある場合は、適切なアクセス許可が設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-212">If you must create folders for the users, ensure that you have the correct permissions set.</span></span>

<span data-ttu-id="0ba25-213">フォルダーを事前に作成しないことを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0ba25-213">We strongly recommend that you do not pre-create folders.</span></span> <span data-ttu-id="0ba25-214">代わりに、UE-V Agent がユーザー用のフォルダーを作成できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0ba25-214">Instead, let the UE-V Agent create the folder for the user.</span></span>

### <span data-ttu-id="0ba25-215">ホームディレクトリまたはカスタムディレクトリに UE-V 2 の設定を保存するための適切な権限を確認する</span><span class="sxs-lookup"><span data-stu-id="0ba25-215">Ensure correct permissions to store UE-V 2 settings in a home directory or custom directory</span></span>

<span data-ttu-id="0ba25-216">ユーザーのホームディレクトリまたはカスタム Active Directory (AD) ディレクトリに UE-V 設定をリダイレクトする場合は、そのディレクトリに対するアクセス許可が組織に適切に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0ba25-216">If you redirect UE-V settings to a user’s home directory or a custom Active Directory (AD) directory, ensure that the permissions on the directory are set appropriately for your organization.</span></span>






## <span data-ttu-id="0ba25-217">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0ba25-217">Related topics</span></span>


[<span data-ttu-id="0ba25-218">UE-V 2.x のテクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="0ba25-218">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





