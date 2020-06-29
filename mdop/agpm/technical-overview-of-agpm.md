---
title: AGPM の技術概要
description: AGPM の技術概要
author: dansimp
ms.assetid: 36bc0ab5-f752-474c-8559-721ea95169c2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0cc635f46c2aabb0c9fa1f472a258a3e65a07b55
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818297"
---
# <span data-ttu-id="64251-103">AGPM の技術概要</span><span class="sxs-lookup"><span data-stu-id="64251-103">Technical Overview of AGPM</span></span>


<span data-ttu-id="64251-104">Microsoft Advanced グループポリシー管理 (AGPM) は、クライアント/サーバーアプリケーションです。</span><span class="sxs-lookup"><span data-stu-id="64251-104">Microsoft Advanced Group Policy Management (AGPM) is a client/server application.</span></span> <span data-ttu-id="64251-105">AGPM サーバーは、サーバーのファイルシステムで作成されたアーカイブに、グループポリシーオブジェクト (Gpo) をオフラインで保存します。</span><span class="sxs-lookup"><span data-stu-id="64251-105">The AGPM Server stores Group Policy Objects (GPOs) offline in the archive that AGPM creates on the server's file system.</span></span> <span data-ttu-id="64251-106">グループポリシー管理者は、グループポリシー管理コンソール (GPMC) 用の AGPM スナップインを使用して、アーカイブをホストしているサーバー上の Gpo を操作します。</span><span class="sxs-lookup"><span data-stu-id="64251-106">Group Policy administrators use the AGPM snap-in for the Group Policy Management Console (GPMC) to work with GPOs on the server that hosts the archive.</span></span> <span data-ttu-id="64251-107">AGPM と関連アイテムの要素、ファイルシステムへの Gpo の格納方法、および各ユーザーロールで利用可能なアクセス許可を制御することによって、AGPM によるグループポリシー管理者の効率性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="64251-107">Understanding the parts of AGPM and related items, how they store GPOs in the file system, and how permissions control the actions available to each user role can improve Group Policy administrators' effectiveness with AGPM.</span></span>

## <span data-ttu-id="64251-108">用語</span><span class="sxs-lookup"><span data-stu-id="64251-108">Terminology</span></span>


<span data-ttu-id="64251-109">次に、基本的な AGPM 用語について説明します。</span><span class="sxs-lookup"><span data-stu-id="64251-109">The following explains the basic AGPM terms.</span></span>

-   <span data-ttu-id="64251-110">**AGPM クライアント:** グループポリシー管理コンソール (GPMC) で AGPM スナップインを実行し、グループポリシー管理者が Gpo を管理するコンピューター。</span><span class="sxs-lookup"><span data-stu-id="64251-110">**AGPM Client:** A computer that runs the AGPM snap-in for the Group Policy Management Console (GPMC) and from which Group Policy administrators manage GPOs.</span></span>

-   <span data-ttu-id="64251-111">**AGPM スナップイン:** AGPM クライアントにインストールされている AGPM のソフトウェアコンポーネントであり、Gpo を管理できるようにします。</span><span class="sxs-lookup"><span data-stu-id="64251-111">**AGPM snap-in:** The software component of AGPM installed on AGPM Clients so that they can manage GPOs.</span></span>

-   <span data-ttu-id="64251-112">**AGPM サーバー:** AGPM サービスを実行してアーカイブを管理するサーバー。</span><span class="sxs-lookup"><span data-stu-id="64251-112">**AGPM Server:** A server that runs the AGPM Service and manages an archive.</span></span> <span data-ttu-id="64251-113">各 AGPM サーバーは1つのアーカイブしか管理できませんが、1つの AGPM サーバーは1つのアーカイブの複数のドメインのアーカイブデータを管理できます。</span><span class="sxs-lookup"><span data-stu-id="64251-113">Each AGPM Server can manage only one archive, but one AGPM Server can manage archive data for multiple domains in one archive.</span></span> <span data-ttu-id="64251-114">アーカイブは、AGPM サーバー以外のコンピューターでホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="64251-114">An archive can be hosted on a computer other than an AGPM Server.</span></span>

-   <span data-ttu-id="64251-115">**AGPM サービス:** サービスとして AGPM サーバー上で実行される AGPM のソフトウェアコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="64251-115">**AGPM Service:** The software component of AGPM that runs on an AGPM Server as a service.</span></span> <span data-ttu-id="64251-116">このサービスは、アーカイブおよびそのフォレストの運用環境での Gpo を管理します。</span><span class="sxs-lookup"><span data-stu-id="64251-116">The service manages GPOs in the archive and in the production environment in that forest.</span></span>

-   <span data-ttu-id="64251-117">**アーカイブ:** AGPM では、関連付けられている AGPM サーバーが管理している Gpo を含む、各 Gpo の履歴に加えて、それらの管理された Gpo を含む中央ストアです。</span><span class="sxs-lookup"><span data-stu-id="64251-117">**Archive:** In AGPM, a central store that contains the controlled GPOs that the associated AGPM Server manages, in addition to the history for each of those GPOs.</span></span> <span data-ttu-id="64251-118">これには、各 GPO の以前の制御バージョンがすべて含まれます。</span><span class="sxs-lookup"><span data-stu-id="64251-118">This includes all previous controlled versions of each GPO.</span></span> <span data-ttu-id="64251-119">アーカイブは、アーカイブインデックスファイルと関連アーカイブデータで構成され、複数のドメインに Gpo のデータが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="64251-119">An archive consists of an archive index file and associated archive data that may include data for GPOs in multiple domains.</span></span> <span data-ttu-id="64251-120">アーカイブは、AGPM サーバー以外のコンピューターでホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="64251-120">An archive can be hosted on a computer other than an AGPM Server.</span></span>

-   <span data-ttu-id="64251-121">制御された**GPO:** AGPM によって管理されている GPO。</span><span class="sxs-lookup"><span data-stu-id="64251-121">**Controlled GPO:** A GPO that is being managed by AGPM.</span></span> <span data-ttu-id="64251-122">AGPM は、アーカイブに保存される、管理された Gpo の履歴と権限を管理します。</span><span class="sxs-lookup"><span data-stu-id="64251-122">AGPM manages the history and permissions of controlled GPOs, which it stores in the archive.</span></span>

-   <span data-ttu-id="64251-123">**非制御 GPO:** ドメインの運用環境での GPO であり、AGPM で管理されません。</span><span class="sxs-lookup"><span data-stu-id="64251-123">**Uncontrolled GPO:** A GPO in the production environment for a domain and not managed by AGPM.</span></span>

## <span data-ttu-id="64251-124">AGPM のインストール、作成、および影響</span><span class="sxs-lookup"><span data-stu-id="64251-124">What AGPM installs, creates, and affects</span></span>


<span data-ttu-id="64251-125">AGPM サーバーでは、AGPM セットアッププログラムは AGPM サービスをインストールします。</span><span class="sxs-lookup"><span data-stu-id="64251-125">On an AGPM Server, the AGPM Setup program installs the AGPM Service.</span></span> <span data-ttu-id="64251-126">AGPM では、Active Directory®ディレクトリサービスまたはスキーマは変更されません。</span><span class="sxs-lookup"><span data-stu-id="64251-126">AGPM does not alter the Active Directory® directory service or the schema.</span></span> <span data-ttu-id="64251-127">既定では、AGPM サーバープログラムファイルは、% program files% ¥にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="64251-127">By default, the AGPM Server program files are installed in %ProgramFiles%\\Microsoft\\AGPM\\Server.</span></span> <span data-ttu-id="64251-128">必要に応じて、AGPM サービスをドメインコントローラーにインストールできます。ただし、メンバーサーバーに AGPM サービスをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="64251-128">You can install the AGPM Service on a domain controller if you have to; however, we recommend that you install the AGPM Service on a member server.</span></span>

<span data-ttu-id="64251-129">AGPM クライアントでは、AGPM セットアッププログラムは、AGPM スナップインをインストールし、GPMC に表示される各ドメインに**変更制御**フォルダーを追加します。</span><span class="sxs-lookup"><span data-stu-id="64251-129">On an AGPM Client, the AGPM Setup program installs the AGPM snap-in, adding a **Change Control** folder to each domain that appears in the GPMC.</span></span> <span data-ttu-id="64251-130">既定では、AGPM クライアントプログラムファイルは、% program files% ¥ \ agpm¥にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="64251-130">By default, the AGPM Client program files are installed in %ProgramFiles%\\Microsoft\\AGPM\\Client.</span></span>

<span data-ttu-id="64251-131">表1では、AGPM によってインストールまたは作成される項目、および AGPM 操作に影響を与えるオペレーティングシステムの部分について説明します。</span><span class="sxs-lookup"><span data-stu-id="64251-131">Table 1 describes both the items that AGPM installs or creates and the parts of the operating system that affect AGPM operation.</span></span>

**<span data-ttu-id="64251-132">表 1: AGPM によってインストール、作成、または影響を受ける項目</span><span class="sxs-lookup"><span data-stu-id="64251-132">Table 1: Items installed, created, or affected by AGPM</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64251-133">項目</span><span class="sxs-lookup"><span data-stu-id="64251-133">Item</span></span></th>
<th align="left"><span data-ttu-id="64251-134">説明</span><span class="sxs-lookup"><span data-stu-id="64251-134">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64251-135">AGPM サービス</span><span class="sxs-lookup"><span data-stu-id="64251-135">AGPM Service</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-136">AGPM サービスは AGPM サーバー上で実行されます。</span><span class="sxs-lookup"><span data-stu-id="64251-136">The AGPM Service runs on the AGPM Server.</span></span> <span data-ttu-id="64251-137">サービスは、オフライン Gpo を含むアーカイブを管理し、運用環境では制御された Gpo を管理します。</span><span class="sxs-lookup"><span data-stu-id="64251-137">The service manages the archive, which contains offline GPOs, and controlled GPOs in the production environment.</span></span> <span data-ttu-id="64251-138">AGPM サービスの既定の構成は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="64251-138">The default configuration of the AGPM Service is as follows:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="64251-139">サービス名: </strong> AGPM サービス</span><span class="sxs-lookup"><span data-stu-id="64251-139">Service name:</strong> AGPM Service</span></span></p></li>
<li><p><strong><span data-ttu-id="64251-140">表示名: </strong> AGPM サービス</span><span class="sxs-lookup"><span data-stu-id="64251-140">Display name:</strong> AGPM Service</span></span></p></li>
<li><p><strong><span data-ttu-id="64251-141">実行可能ファイルへのパス: </strong> % ProgramFiles% \Microsoft\AGPM\Server\Agpm.exe</span><span class="sxs-lookup"><span data-stu-id="64251-141">Path to executable:</strong> %ProgramFiles%\Microsoft\AGPM\Server\Agpm.exe</span></span></p></li>
<li><p><strong><span data-ttu-id="64251-142">スタートアップ: </strong> 自動</span><span class="sxs-lookup"><span data-stu-id="64251-142">Startup:</strong> Automatic</span></span></p></li>
<li><p><strong><span data-ttu-id="64251-143">ログオン: </strong> Agpm サーバーのインストール中に指定された Agpm サービスアカウント。 <strong> コントロールパネルの [プログラムと機能] を使って変更でき </strong> <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="64251-143">Log on as:</strong> AGPM Service Account specified during installation of AGPM Server, which can be changed using <strong>Programs and Features</strong> in the <strong>Control Panel</strong>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64251-144">AGPM アーカイブ</span><span class="sxs-lookup"><span data-stu-id="64251-144">AGPM archive</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-145">既定では、AGPM は、AGPM サーバー上の%ProgramData%\Microsoft\AGPM にアーカイブを作成します。</span><span class="sxs-lookup"><span data-stu-id="64251-145">By default, AGPM creates the archive in %ProgramData%\Microsoft\AGPM on the AGPM Server.</span></span> <span data-ttu-id="64251-146">アーカイブには、オフライン Gpo 用の記憶域が用意されています。また、各 GPO の複数のバージョンを格納することもできます。</span><span class="sxs-lookup"><span data-stu-id="64251-146">The archive provides storage for offline GPOs, and it can store multiple versions of each GPO.</span></span> <span data-ttu-id="64251-147">パッケージ内の Gpo に対して AGPM が行う変更は、AGPM 管理者または承認者が GPO を運用環境に展開し、GPO を組織単位 (OU) にリンクするまで、運用環境に影響を与えません。</span><span class="sxs-lookup"><span data-stu-id="64251-147">Changes that AGPM makes to GPOs in the archive do not affect the production environment until an AGPM Administrator or Approver deploys the GPO to the production environment and links the GPO to an organizational unit (OU).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64251-148">Windows ファイアウォール</span><span class="sxs-lookup"><span data-stu-id="64251-148">Windows Firewall</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-149">インストール時に、AGPM は、agpm クライアントが AGPM サーバーと通信するための受信 Windows ファイアウォール規則を有効にします。</span><span class="sxs-lookup"><span data-stu-id="64251-149">During installation, AGPM enables an inbound Windows Firewall rule that allows the AGPM Client to communicate with the AGPM Server.</span></span> <span data-ttu-id="64251-150">Windows ファイアウォールの既定の規則は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="64251-150">The default Windows Firewall rule is the following:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="64251-151">Name: </strong> AGPM サービス</span><span class="sxs-lookup"><span data-stu-id="64251-151">Name:</strong> AGPM Service</span></span></p></li>
<li><p><strong><span data-ttu-id="64251-152">アクション: </strong> 接続を許可する</span><span class="sxs-lookup"><span data-stu-id="64251-152">Action:</strong> Allow the connection</span></span></p></li>
<li><p><strong><span data-ttu-id="64251-153">プログラム: </strong> 指定した条件を満たすすべてのプログラム</span><span class="sxs-lookup"><span data-stu-id="64251-153">Programs:</strong> All programs that meet the specified conditions</span></span></p></li>
<li><p><strong><span data-ttu-id="64251-154">プロトコルの種類: </strong> TCP</span><span class="sxs-lookup"><span data-stu-id="64251-154">Protocol type:</strong> TCP</span></span></p></li>
<li><p><strong><span data-ttu-id="64251-155">ローカルポート: </strong> 4600</span><span class="sxs-lookup"><span data-stu-id="64251-155">Local port:</strong> 4600</span></span></p></li>
<li><p><strong><span data-ttu-id="64251-156">リモートポート: </strong> すべてのポート</span><span class="sxs-lookup"><span data-stu-id="64251-156">Remote port:</strong> All ports</span></span></p></li>
<li><p><strong><span data-ttu-id="64251-157">ローカル IP アドレス: </strong> Any</span><span class="sxs-lookup"><span data-stu-id="64251-157">Local IP address:</strong> Any</span></span></p></li>
<li><p><strong><span data-ttu-id="64251-158">リモート IP アドレス: </strong> Any</span><span class="sxs-lookup"><span data-stu-id="64251-158">Remote IP address:</strong> Any</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64251-159">メールサーバー</span><span class="sxs-lookup"><span data-stu-id="64251-159">E-mail server</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-160">AGPM は、Simple Mail Transfer Protocol (SMTP) を使って、[Domain Delegation] タブで構成されたアドレスに電子メール要求を送信し <strong> </strong> ます。たとえば、新しい GPO を作成するようにエディターから要求があった場合、AGPM は [Domain Delegation] タブで指定された各電子メールアドレスに通知し <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="64251-160">AGPM uses Simple Mail Transfer Protocol (SMTP) to send e-mail requests to the addresses configured on the <strong>Domain Delegation</strong> tab. For example, when an Editor requests that a new GPO be created, AGPM notifies each e-mail address specified on the <strong>Domain Delegation</strong> tab.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64251-161">AGPM スナップイン</span><span class="sxs-lookup"><span data-stu-id="64251-161">AGPM snap-in</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-162">GPMC の AGPM スナップインは、AGPM クライアントで実行され、グループポリシー管理者が Gpo を管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="64251-162">The AGPM snap-in for the GPMC runs on AGPM Clients and is used by Group Policy administrators to manage GPOs.</span></span> <span data-ttu-id="64251-163">スナップインは、GPMC の <strong> 各ドメインの変更制御フォルダーとして表示され </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="64251-163">The snap-in appears in the GPMC as a <strong>Change Control</strong> folder in each domain.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="64251-164">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="64251-164">Additional references</span></span>

<span data-ttu-id="64251-165">AGPM によってインストールされるファイルについて詳しくは、 [agpm の計画ガイド](https://go.microsoft.com/fwlink/?LinkId=160060)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="64251-165">For more information about the files installed by AGPM, see the [Planning Guide for AGPM](https://go.microsoft.com/fwlink/?LinkId=160060).</span></span>

## <span data-ttu-id="64251-166">アーカイブ</span><span class="sxs-lookup"><span data-stu-id="64251-166">Archive</span></span>


<span data-ttu-id="64251-167">既定では、AGPM サーバーのインストールプロセスによって、% programdata% ¥¥のローカルハードディスク上のアーカイブが作成されます。</span><span class="sxs-lookup"><span data-stu-id="64251-167">By default, the AGPM Server installation process creates the archive on the local hard disk of the AGPM Server at %ProgramData%\\Microsoft\\AGPM.</span></span> <span data-ttu-id="64251-168">ただし、インストール中にパスを変更したり、AGPM サーバー以外のサーバーにアーカイブを作成したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="64251-168">However, you can change the path during installation and even create the archive on a server other than the AGPM Server.</span></span>

<span data-ttu-id="64251-169">アーカイブには、アーカイブに含まれる各 GPO の各バージョンのサブフォルダーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="64251-169">The archive contains a subfolder for each version of each GPO the archive contains.</span></span> <span data-ttu-id="64251-170">各サブフォルダーの名前は、その GPO のバージョンを識別する GUID です。</span><span class="sxs-lookup"><span data-stu-id="64251-170">The name of each subfolder is a GUID that identifies a version of the GPO.</span></span>

<span data-ttu-id="64251-171">gpostate.xml ファイルには、アーカイブ内の各 GPO の状態が記録されます。</span><span class="sxs-lookup"><span data-stu-id="64251-171">The gpostate.xml file records the state of each GPO in the archive.</span></span> <span data-ttu-id="64251-172">ファイルは、アーカイブの内容を説明するマニフェストです。</span><span class="sxs-lookup"><span data-stu-id="64251-172">The file is a manifest that describes the contents of the archive.</span></span> <span data-ttu-id="64251-173">たとえば、GPO には多くのバージョンがあり、各バージョンはアーカイブ内の独自のサブフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="64251-173">For example, a GPO can have many versions, and each version is in its own subfolder in the archive.</span></span> <span data-ttu-id="64251-174">gpostate.xml ファイルには、1つの GPO の異なるバージョンが含まれるサブフォルダーが示されます。</span><span class="sxs-lookup"><span data-stu-id="64251-174">The gpostate.xml file indicates which subfolders contain different versions of a single GPO.</span></span> <span data-ttu-id="64251-175">さらに、GPO テンプレートにはアーカイブ内のサブフォルダーがあります gpostate.xml が、これはテンプレートであり、管理されている Gpo ではないことを示しています。</span><span class="sxs-lookup"><span data-stu-id="64251-175">Additionally, GPO templates have subfolders in the archive, but gpostate.xml indicates that these are templates and not controlled GPOs.</span></span> <span data-ttu-id="64251-176">同様に、グループポリシーの管理者が Gpo を削除するときに、AGPM は、**ごみ箱**の gpostate.xml 状態を変更しますが、実際には、gpo のサブフォルダーはアーカイブから削除されないことを示します。</span><span class="sxs-lookup"><span data-stu-id="64251-176">Similarly, when Group Policy administrators delete GPOs, AGPM changes their states in gpostate.xml to indicate that they are in the **Recycle Bin** but does not actually remove the GPOs' subfolders from the archive.</span></span>

<span data-ttu-id="64251-177">**注意** gpostate.xml またはアーカイブに含まれている Gpo を手動で編集しないでください。</span><span class="sxs-lookup"><span data-stu-id="64251-177">**Caution** Do not manually edit gpostate.xml or the GPOs the archive contains.</span></span> <span data-ttu-id="64251-178">この情報は、AGPM アーカイブの理解を深めるためにのみ提供されます。</span><span class="sxs-lookup"><span data-stu-id="64251-178">This information is provided only to enhance understanding of the AGPM archive.</span></span> <span data-ttu-id="64251-179">代わりに、AGPM スナップインを使って Gpo を変更します。</span><span class="sxs-lookup"><span data-stu-id="64251-179">Instead, use the AGPM snap-in to change GPOs.</span></span>

 

<span data-ttu-id="64251-180">AGPM によってアーカイブが作成されると、システム、管理者、agpm サービスアカウント (AGPM サーバーのセットアップで指定) へのフルコントロールが与えられます。</span><span class="sxs-lookup"><span data-stu-id="64251-180">When AGPM creates the archive, it gives Full Control to SYSTEM, Administrators, and the AGPM Service Account (specified in the setup of AGPM Server).</span></span> <span data-ttu-id="64251-181">Agpm サービスアカウントは、ログオンしているユーザーの代わりにすべての操作を実行するため、AGPM スナップインの AGPM ユーザーインターフェイスを使用してアクセス許可を変更しても、アーカイブのアクセス許可は変更されません。</span><span class="sxs-lookup"><span data-stu-id="64251-181">Changing permissions by using the AGPM user interface on the AGPM snap-in does not alter permissions on the archive, because the AGPM Service Account performs all operations on behalf of the logged-on user.</span></span>

### <span data-ttu-id="64251-182">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="64251-182">Additional references</span></span>

<span data-ttu-id="64251-183">アーカイブのバックアップ方法、バックアップからアーカイブを復元する方法、または AGPM サーバーとアーカイブの両方を移動する方法については、「[操作ガイド (agpm の操作ガイド](https://go.microsoft.com/fwlink/?LinkId=160061))」の「Agpm 管理者のタスクを実行する」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="64251-183">For information about how to back up the archive, restore the archive from a backup, or move both the AGPM Server and the archive, see the "Performing AGPM Administrator Tasks" section in the [Operations Guide for AGPM](https://go.microsoft.com/fwlink/?LinkId=160061).</span></span>

## <span data-ttu-id="64251-184">役割とアクセス許可</span><span class="sxs-lookup"><span data-stu-id="64251-184">Roles and permissions</span></span>


<span data-ttu-id="64251-185">役割によって委任が簡単になります。</span><span class="sxs-lookup"><span data-stu-id="64251-185">Roles simplify delegation.</span></span> <span data-ttu-id="64251-186">グループポリシー管理者に対して詳細なアクセス許可を割り当てる代わりに、AGPM 管理者は、その役割に関連する作業を実行できるように、次の4つの役割のいずれかをグループポリシー管理者に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="64251-186">Instead of assigning detailed permissions to Group Policy administrators, AGPM Administrators can assign one of four roles to Group Policy administrators to let them perform work related to that role:</span></span>

-   <span data-ttu-id="64251-187">**AGPM 管理者:** グループポリシー管理者は、AGPM 管理者 (フルコントロール) の役割を割り当てて、AGPM 内の任意のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="64251-187">**AGPM Administrator:** Group Policy administrators assigned the AGPM Administrator (Full Control) role can perform any task in AGPM.</span></span> <span data-ttu-id="64251-188">AGPM 管理者は、ドメイン全体のオプションを構成し、他のグループポリシー管理者にアクセス許可を委任することができます。</span><span class="sxs-lookup"><span data-stu-id="64251-188">AGPM Administrators can configure domain-wide options and delegate permissions to other Group Policy administrators.</span></span>

-   <span data-ttu-id="64251-189">**承認者:** グループポリシー管理者は、承認者の役割を割り当てた Gpo をドメインの運用環境に展開できます。</span><span class="sxs-lookup"><span data-stu-id="64251-189">**Approver:** Group Policy administrators assigned the Approver role can deploy GPOs to the production environment for a domain.</span></span> <span data-ttu-id="64251-190">承認者は、Gpo を作成および削除し、編集者から要求を承認または拒否することもできます。</span><span class="sxs-lookup"><span data-stu-id="64251-190">Approvers can also create and delete GPOs and approve or reject requests from Editors.</span></span> <span data-ttu-id="64251-191">承認者は、ドメイン内の Gpo の一覧を表示したり、Gpo のポリシー設定を表示したり、GPO のポリシー設定のレポートを作成して表示したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="64251-191">Approvers can view the list of GPOs in a domain, view the policy settings in GPOs, and create and view reports of the policy settings in a GPO.</span></span> <span data-ttu-id="64251-192">編集者の役割が割り当てられている場合を除き、Gpo のポリシー設定を編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="64251-192">They cannot edit the policy settings in GPOs unless they are also assigned the Editor role.</span></span>

-   <span data-ttu-id="64251-193">**エディター:** グループポリシー管理者は、ドメイン内の Gpo の一覧を表示したり、Gpo のポリシー設定を表示したり、gpo のポリシー設定を編集したり、GPO のポリシー設定のレポートを作成して表示したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="64251-193">**Editor:** Group Policy administrators assigned the Editor role can view the list of GPOs in a domain, view the policy settings in GPOs, edit the policy settings in GPOs, and create and view reports of the policy settings in a GPO.</span></span> <span data-ttu-id="64251-194">管理者は、承認者の役割も割り当てられていない限り、Gpo の作成、展開、削除を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="64251-194">Unless they are also assigned the Approver role, Editors cannot create, deploy, or delete GPOs.</span></span> <span data-ttu-id="64251-195">ただし、Gpo の作成、展開、または削除を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="64251-195">However, they can request that GPOs be created, deployed, or deleted.</span></span>

-   <span data-ttu-id="64251-196">**校閲者:** グループポリシー管理者は、レビュー担当者の役割を割り当てることで、ドメイン内の Gpo の一覧を表示したり、GPO のポリシー設定のレポートを作成して表示したりできます。</span><span class="sxs-lookup"><span data-stu-id="64251-196">**Reviewer:** Group Policy administrators assigned the Reviewer role can view the list of GPOs in a domain and create and view reports of the policy settings in a GPO.</span></span> <span data-ttu-id="64251-197">編集者の役割も割り当てられている場合を除き、GPO のポリシー設定を編集することはできません。</span><span class="sxs-lookup"><span data-stu-id="64251-197">Unless they are also assigned the Editor role, they cannot edit policy settings in a GPO.</span></span>

<span data-ttu-id="64251-198">Agpm は、agpm 管理者に対して、AGPM スナップインを使用して、ロールよりも詳細なレベルでアクセス許可を構成できる柔軟性を提供します。</span><span class="sxs-lookup"><span data-stu-id="64251-198">AGPM gives AGPM Administrators the flexibility to configure permissions at a more detailed level than roles by using the AGPM snap-in.</span></span> <span data-ttu-id="64251-199">表2に、これらのアクセス許可について説明します。既定では、各役割に付与されるアクセス許可を示しています。</span><span class="sxs-lookup"><span data-stu-id="64251-199">Table 2 describes these permissions and indicates the permissions granted to each role by default.</span></span>

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
<th align="left"><span data-ttu-id="64251-200">許可</span><span class="sxs-lookup"><span data-stu-id="64251-200">Permission</span></span></th>
<th align="left"><span data-ttu-id="64251-201">説明</span><span class="sxs-lookup"><span data-stu-id="64251-201">Description</span></span></th>
<th align="left"><span data-ttu-id="64251-202">AGPM 管理者</span><span class="sxs-lookup"><span data-stu-id="64251-202">AGPM Administrator</span></span></th>
<th align="left"><span data-ttu-id="64251-203">承認者</span><span class="sxs-lookup"><span data-stu-id="64251-203">Approver</span></span></th>
<th align="left"><span data-ttu-id="64251-204">エディター</span><span class="sxs-lookup"><span data-stu-id="64251-204">Editor</span></span></th>
<th align="left"><span data-ttu-id="64251-205">担当者</span><span class="sxs-lookup"><span data-stu-id="64251-205">Reviewer</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="64251-206">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="64251-206">Full Control</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="64251-207">すべての権限を持つ。</span><span class="sxs-lookup"><span data-stu-id="64251-207">Have all permissions.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-208">あり</span><span class="sxs-lookup"><span data-stu-id="64251-208">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="64251-209">GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="64251-209">Create GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="64251-210">ドメインで Gpo を作成します。</span><span class="sxs-lookup"><span data-stu-id="64251-210">Create GPOs in a domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-211">あり</span><span class="sxs-lookup"><span data-stu-id="64251-211">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-212">あり</span><span class="sxs-lookup"><span data-stu-id="64251-212">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="64251-213">リストの内容</span><span class="sxs-lookup"><span data-stu-id="64251-213">List Contents</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="64251-214">ドメイン内の Gpo を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="64251-214">List the GPOs in a domain.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-215">あり</span><span class="sxs-lookup"><span data-stu-id="64251-215">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-216">あり</span><span class="sxs-lookup"><span data-stu-id="64251-216">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-217">あり</span><span class="sxs-lookup"><span data-stu-id="64251-217">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-218">あり</span><span class="sxs-lookup"><span data-stu-id="64251-218">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="64251-219">設定の読み取り</span><span class="sxs-lookup"><span data-stu-id="64251-219">Read Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="64251-220">GPO 内のポリシー設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="64251-220">Read the policy settings within a GPO.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-221">あり</span><span class="sxs-lookup"><span data-stu-id="64251-221">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-222">あり</span><span class="sxs-lookup"><span data-stu-id="64251-222">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-223">あり</span><span class="sxs-lookup"><span data-stu-id="64251-223">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-224">あり</span><span class="sxs-lookup"><span data-stu-id="64251-224">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="64251-225">設定を編集する</span><span class="sxs-lookup"><span data-stu-id="64251-225">Edit Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="64251-226">GPO のポリシー設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="64251-226">Change the policy settings in a GPO.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-227">あり</span><span class="sxs-lookup"><span data-stu-id="64251-227">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="64251-228">あり</span><span class="sxs-lookup"><span data-stu-id="64251-228">Yes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="64251-229">GPO を削除する</span><span class="sxs-lookup"><span data-stu-id="64251-229">Delete GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="64251-230">GPO を削除します。</span><span class="sxs-lookup"><span data-stu-id="64251-230">Delete a GPO.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-231">あり</span><span class="sxs-lookup"><span data-stu-id="64251-231">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-232">あり</span><span class="sxs-lookup"><span data-stu-id="64251-232">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="64251-233">セキュリティを変更する</span><span class="sxs-lookup"><span data-stu-id="64251-233">Modify Security</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="64251-234">ドメインレベルのアクセスを委任したり、1つの GPO へのアクセスを委任したり、運用環境へのアクセスを委任したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="64251-234">Delegate domain-level access, delegate access to a single GPO, and delegate access to the production environment.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-235">あり</span><span class="sxs-lookup"><span data-stu-id="64251-235">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="64251-236">GPO の展開</span><span class="sxs-lookup"><span data-stu-id="64251-236">Deploy GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="64251-237">アーカイブから実稼働環境に GPO を展開します。</span><span class="sxs-lookup"><span data-stu-id="64251-237">Deploy a GPO from the archive to the production environment.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-238">あり</span><span class="sxs-lookup"><span data-stu-id="64251-238">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-239">あり</span><span class="sxs-lookup"><span data-stu-id="64251-239">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="64251-240">テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="64251-240">Create Template</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="64251-241">AGPM で GPO テンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="64251-241">Create a GPO template in AGPM.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-242">あり</span><span class="sxs-lookup"><span data-stu-id="64251-242">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="64251-243">あり</span><span class="sxs-lookup"><span data-stu-id="64251-243">Yes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="64251-244">オプションの変更</span><span class="sxs-lookup"><span data-stu-id="64251-244">Modify Options</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="64251-245">AGPM メールの通知を構成し、アーカイブに保存されている GPO のバージョンを制限します。</span><span class="sxs-lookup"><span data-stu-id="64251-245">Configure AGPM e-mail notification and limit the GPO versions stored in the archive.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-246">あり</span><span class="sxs-lookup"><span data-stu-id="64251-246">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="64251-247">GPO をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="64251-247">Export GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="64251-248">GPO をファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="64251-248">Export a GPO to a file.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-249">あり</span><span class="sxs-lookup"><span data-stu-id="64251-249">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="64251-250">あり</span><span class="sxs-lookup"><span data-stu-id="64251-250">Yes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="64251-251">GPO をインポートする</span><span class="sxs-lookup"><span data-stu-id="64251-251">Import GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="64251-252">ファイルから GPO をインポートします。</span><span class="sxs-lookup"><span data-stu-id="64251-252">Import a GPO from a file.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64251-253">あり</span><span class="sxs-lookup"><span data-stu-id="64251-253">Yes</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="64251-254">あり</span><span class="sxs-lookup"><span data-stu-id="64251-254">Yes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="64251-255">**注** 
**Gpo のエクスポート**と**gpo のインポート**のアクセス許可は、AGPM 3.0 または2.5 では利用できません。</span><span class="sxs-lookup"><span data-stu-id="64251-255">**Note**
**Export GPO** and **Import GPO** permissions are not available in AGPM 3.0 or 2.5.</span></span>

<span data-ttu-id="64251-256">ドメインの運用環境で Gpo へのアクセスを委任する機能と、保存されている GPO バージョンの数を制限する機能は、AGPM 2.5 では使用できません。</span><span class="sxs-lookup"><span data-stu-id="64251-256">The ability to delegate access to GPOs in the production environment for a domain and the ability to limit the number of GPO versions stored are not available in AGPM 2.5.</span></span>

 

### <span data-ttu-id="64251-257">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="64251-257">Additional references</span></span>

<span data-ttu-id="64251-258">グループポリシー管理者が特定の役割を割り当てた、または特定のタスクを実行するために必要なアクセス許可について、実行できるタスクの詳細については、「 [AGPM の操作ガイド](https://go.microsoft.com/fwlink/?LinkId=160061)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64251-258">For information about what tasks can be performed by Group Policy administrators assigned a particular role or about which permissions are required to perform a specific task, see the [Operations Guide for AGPM](https://go.microsoft.com/fwlink/?LinkId=160061).</span></span>

 

 





