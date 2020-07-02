---
title: Microsoft User Experience Virtualization (UE-V) 2. x
description: Microsoft User Experience Virtualization (UE-V) 2. x
author: dansimp
ms.assetid: b860fed0-b846-415d-bdd6-ba60231a64be
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 573b8bb2027e5c7f117a8254005a43c656f047a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795816"
---
# <span data-ttu-id="f722a-103">Microsoft User Experience Virtualization (UE-V) 2. x</span><span class="sxs-lookup"><span data-stu-id="f722a-103">Microsoft User Experience Virtualization (UE-V) 2.x</span></span>

>[!NOTE]
><span data-ttu-id="f722a-104">このドキュメントは、Microsoft デスクトップ最適化パック (MDOP) に含まれている UE-V のバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="f722a-104">This documentation is a for version of UE-V that was included in the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="f722a-105">Windows 10 Enterprise に含まれている最新バージョンの UE-V の詳細については、「 [ue-v の使用を開始](https://docs.microsoft.com/windows/configuration/ue-v/uev-getting-started)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f722a-105">For information about the latest version of UE-V which is included in Windows 10 Enterprise, see [Get Started with UE-V](https://docs.microsoft.com/windows/configuration/ue-v/uev-getting-started).</span></span>


<span data-ttu-id="f722a-106">Microsoft User Experience Virtualization (UE-V) 2.0 または2.1 を実装して、ユーザーのアプリケーション設定と Windows OS 設定をキャプチャして集中化します。</span><span class="sxs-lookup"><span data-stu-id="f722a-106">Capture and centralize your users’ application settings and Windows OS settings by implementing Microsoft User Experience Virtualization (UE-V) 2.0 or 2.1.</span></span> <span data-ttu-id="f722a-107">次に、デスクトップコンピューター、ノート pc、仮想デスクトップインフラストラクチャ (VDI) セッションなど、エンタープライズのユーザーアクセスデバイスにこれらの設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="f722a-107">Then, apply these settings to the devices users access in your enterprise, like desktop computers, laptops, or virtual desktop infrastructure (VDI) sessions.</span></span>

**<span data-ttu-id="f722a-108">UE-V では...</span><span class="sxs-lookup"><span data-stu-id="f722a-108">With UE-V you can…</span></span>**

-   <span data-ttu-id="f722a-109">どのアプリケーションとデスクトップの設定を同期するかを指定する</span><span class="sxs-lookup"><span data-stu-id="f722a-109">Specify which application and desktop settings synchronize</span></span>

-   <span data-ttu-id="f722a-110">エンタープライズ規模で、ユーザーが作業する時間や場所を問わず、設定を提供する。</span><span class="sxs-lookup"><span data-stu-id="f722a-110">Deliver the settings anytime and anywhere users work throughout the enterprise</span></span>

-   <span data-ttu-id="f722a-111">サード パーティ製アプリケーションまたは基幹アプリケーション用のカスタム テンプレートを作成する。</span><span class="sxs-lookup"><span data-stu-id="f722a-111">Create custom templates for your third-party or line-of-business applications</span></span>

-   <span data-ttu-id="f722a-112">ハードウェアの置き換えまたはアップグレード後、または仮想マシンを初期状態に再イメージした後に設定を回復する</span><span class="sxs-lookup"><span data-stu-id="f722a-112">Recover settings after hardware replacement or upgrade, or after reimaging a virtual machine to its initial state</span></span>

## <span data-ttu-id="f722a-113">UE-V 2. x の構成要素</span><span class="sxs-lookup"><span data-stu-id="f722a-113">Components of UE-V 2.x</span></span>


<span data-ttu-id="f722a-114">次の図は、展開された UE-V コンポーネントが連携して設定を同期する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="f722a-114">This diagram shows how deployed UE-V components work together to synchronize settings.</span></span>

![uev2 のアーキテクチャ図](images/uev2archdiagram.gif)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f722a-116">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f722a-116">Component</span></span></th>
<th align="left"><span data-ttu-id="f722a-117">機能</span><span class="sxs-lookup"><span data-stu-id="f722a-117">Function</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="f722a-118">UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="f722a-118">UE-V Agent</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="f722a-119">設定を同期する必要があるすべてのコンピューターにインストールされている <strong> Ue-v agent は、 </strong> 登録済みアプリケーションとオペレーティングシステムを監視して、すべての設定を変更し、コンピューター間でこれらの設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="f722a-119">Installed on every computer that needs to synchronize settings, the <strong>UE-V Agent</strong> monitors registered applications and the operating system for any settings changes, then synchronizes those settings between computers.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="f722a-120">設定パッケージ</span><span class="sxs-lookup"><span data-stu-id="f722a-120">Settings packages</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="f722a-121">アプリケーション設定と Windows 設定は <strong> </strong> 、ue-v agent によって作成された設定パッケージに保存されます。</span><span class="sxs-lookup"><span data-stu-id="f722a-121">Application settings and Windows settings are stored in <strong>settings packages</strong> created by the UE-V Agent.</span></span> <span data-ttu-id="f722a-122">構築された設定パッケージはローカル保存され、設定の保存場所にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="f722a-122">Settings packages are built, locally stored, and copied to the settings storage location.</span></span></p>
<ul>
<li><p><span data-ttu-id="f722a-123">デスクトップアプリケーションの設定値 <strong> </strong> は、ユーザーがアプリケーションを閉じると保存されます。</span><span class="sxs-lookup"><span data-stu-id="f722a-123">The setting values for <strong>desktop applications</strong> are stored when the user closes the application.</span></span></p></li>
<li><p><span data-ttu-id="f722a-124"><strong>Windows 設定の値 </strong> は、ユーザーがログオフしたとき、コンピューターがロックされているとき、またはユーザーがコンピューターからリモートで切断したときに保存されます。</span><span class="sxs-lookup"><span data-stu-id="f722a-124">Values for <strong>Windows settings</strong> are stored when the user logs off, when the computer is locked, or when the user disconnects remotely from a computer.</span></span></p></li>
</ul>
<p><span data-ttu-id="f722a-125">同期プロバイダーは、アプリケーションまたはオペレーティングシステムの設定が設定パッケージから読み取られるタイミングを決定し、 <strong> </strong> 同期されます。</span><span class="sxs-lookup"><span data-stu-id="f722a-125">The sync provider determines when the application or operating system settings are read from the <strong>Settings Packages</strong> and synchronized.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="f722a-126">設定の保存場所</span><span class="sxs-lookup"><span data-stu-id="f722a-126">Settings storage location</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="f722a-127">これは、ユーザーがアクセスできる標準のネットワーク共有です。</span><span class="sxs-lookup"><span data-stu-id="f722a-127">This is a standard network share that your users can access.</span></span> <span data-ttu-id="f722a-128">UE-V Agent は、その場所を確認し、ユーザー設定を保存して取得する非表示のシステムフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="f722a-128">The UE-V Agent verifies the location and creates a hidden system folder in which to store and retrieve user settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="f722a-129">設定場所テンプレート</span><span class="sxs-lookup"><span data-stu-id="f722a-129">Settings location templates</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="f722a-130">UE-V は、設定場所テンプレートとして XML ファイルを使用して、デスクトップアプリケーションの設定と、ユーザーのコンピューター間の Windows デスクトップの設定を監視および同期します。</span><span class="sxs-lookup"><span data-stu-id="f722a-130">UE-V uses XML files as settings location templates to monitor and synchronize desktop application settings and Windows desktop settings between user computers.</span></span> <span data-ttu-id="f722a-131">既定では、一部の設定場所テンプレートは UE-V に含まれています。</span><span class="sxs-lookup"><span data-stu-id="f722a-131">By default, some settings location templates are included in UE-V .</span></span> <span data-ttu-id="f722a-132">カスタムアプリケーションの設定の同期を管理することによって、カスタム設定の場所テンプレートを作成、編集、または検証することもでき <a href="#customapps" data-raw-source="[managing settings synchronization for custom applications](#customapps)"> </a> ます。</span><span class="sxs-lookup"><span data-stu-id="f722a-132">You can also create, edit, or validate custom settings location templates by <a href="#customapps" data-raw-source="[managing settings synchronization for custom applications](#customapps)">managing settings synchronization for custom applications</a>.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="f722a-133">注</span><span class="sxs-lookup"><span data-stu-id="f722a-133">Note</span></span></strong><br/><p><span data-ttu-id="f722a-134">設定場所テンプレートは、Windows アプリでは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="f722a-134">Settings location templates are not required for Windows apps.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="f722a-135">Windows アプリの一覧</span><span class="sxs-lookup"><span data-stu-id="f722a-135">Windows app list</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="f722a-136">Windows アプリの設定は、動的にキャプチャおよび適用されます。</span><span class="sxs-lookup"><span data-stu-id="f722a-136">Settings for Windows apps are captured and applied dynamically.</span></span> <span data-ttu-id="f722a-137">アプリの開発者は、アプリごとに同期される設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="f722a-137">The app developer specifies the settings that are synchronized for each app.</span></span> <span data-ttu-id="f722a-138">UE-V は、アプリの管理リストを使用して、設定の同期にどの Windows アプリを有効にするかを決定します。</span><span class="sxs-lookup"><span data-stu-id="f722a-138">UE-V determines which Windows apps are enabled for settings synchronization using a managed list of apps.</span></span> <span data-ttu-id="f722a-139">既定では、この一覧にはほとんどの Windows アプリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="f722a-139">By default, this list includes most Windows apps.</span></span></p>
<p><span data-ttu-id="f722a-140">次に示す手順に従って、Windows アプリリストのアプリケーションを追加または削除することができ <a href="https://technet.microsoft.com/library/dn458925.aspx" data-raw-source="[here](https://technet.microsoft.com/library/dn458925.aspx)"> </a> ます。</span><span class="sxs-lookup"><span data-stu-id="f722a-140">You can add or remove applications in the Windows app list by following the procedures shown <a href="https://technet.microsoft.com/library/dn458925.aspx" data-raw-source="[here](https://technet.microsoft.com/library/dn458925.aspx)">here</a>.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="customapps"></a><span data-ttu-id="f722a-141">カスタムアプリケーションの設定の同期を管理する</span><span class="sxs-lookup"><span data-stu-id="f722a-141">Managing Settings Synchronization for Custom Applications</span></span>

<span data-ttu-id="f722a-142">これらの UE-V コンポーネントを使用して、サードパーティまたは基幹業務アプリケーションのカスタムテンプレートを作成し、管理します。</span><span class="sxs-lookup"><span data-stu-id="f722a-142">Use these UE-V components to create and manage custom templates for your third-party or line-of-business applications.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="f722a-143">UE-V Generator</span><span class="sxs-lookup"><span data-stu-id="f722a-143">UE-V Generator</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="f722a-144"><strong>Ue-v Generator を使って、 </strong> ユーザー設定の場所テンプレートを作成し、ユーザーコンピューターに配布することができます。</span><span class="sxs-lookup"><span data-stu-id="f722a-144">Use the <strong>UE-V Generator</strong> to create custom settings location templates that you can then distribute to user computers.</span></span> <span data-ttu-id="f722a-145">UE-V Generator を使うと、既存のテンプレートを編集したり、別の XML エディターを使って作成されたテンプレートを検証したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f722a-145">The UE-V Generator also lets you edit an existing template or validate a template that was created by using another XML editor.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="f722a-146">設定テンプレートカタログ</span><span class="sxs-lookup"><span data-stu-id="f722a-146">Settings template catalog</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="f722a-147"><strong>設定テンプレートカタログ </strong> は、カスタム設定の場所テンプレートが保存されている ue-v (ue-v) コンピューター上のフォルダーパスまたはサーバーメッセージブロック (SMB) ネットワーク共有です。</span><span class="sxs-lookup"><span data-stu-id="f722a-147">The <strong>settings template catalog</strong> is a folder path on UE-V computers or a Server Message Block (SMB) network share that stores the custom settings location templates.</span></span> <span data-ttu-id="f722a-148">UE-V Agent は、この場所を1日に1回チェックし、新規または更新されたテンプレートを取得し、その同期動作を更新します。</span><span class="sxs-lookup"><span data-stu-id="f722a-148">The UE-V Agent checks this location once a day, retrieves new or updated templates, and updates its synchronization behavior.</span></span></p>
<p><span data-ttu-id="f722a-149">UE-V の既定の設定の場所テンプレートのみを使用している場合、設定テンプレートカタログは不要です。</span><span class="sxs-lookup"><span data-stu-id="f722a-149">If you use only the UE-V default settings location templates, then a settings template catalog is unnecessary.</span></span> <span data-ttu-id="f722a-150">設定展開カタログの詳細については、「 <a href="https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue" data-raw-source="[Configure a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)"> ue-v 設定テンプレートカタログを構成する」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="f722a-150">For more information about settings deployment catalogs, see <a href="https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue" data-raw-source="[Configure a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)">Configure a UE-V settings template catalog</a>.</span></span></p></td>
</tr>
</tbody>
</table>



![ue-v generator プロセス](images/ue-vgeneratorprocess.gif)

## <span data-ttu-id="f722a-152">既定で同期されている設定</span><span class="sxs-lookup"><span data-stu-id="f722a-152">Settings Synchronized by Default</span></span>


<span data-ttu-id="f722a-153">UE-V は、既定でこれらのアプリケーションの設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="f722a-153">UE-V synchronizes settings for these applications by default.</span></span> <span data-ttu-id="f722a-154">完全なリストと詳細情報については、「 [ue-v 展開で自動的に同期される設定](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f722a-154">For a complete list and more detailed information, see [Settings that are automatically synchronized in a UE-V deployment](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings).</span></span>

<span data-ttu-id="f722a-155">Microsoft Office 2013 アプリケーション (UE-V 2.1 SP1 および 2.1)</span><span class="sxs-lookup"><span data-stu-id="f722a-155">Microsoft Office 2013 applications (UE-V 2.1 SP1 and 2.1)</span></span>

<span data-ttu-id="f722a-156">Microsoft Office 2010 アプリケーション (UE-V 2.1 SP1、2.1、2.0)</span><span class="sxs-lookup"><span data-stu-id="f722a-156">Microsoft Office 2010 applications (UE-V 2.1 SP1, 2.1, and 2.0)</span></span>

<span data-ttu-id="f722a-157">Microsoft Office 2007 アプリケーション (UE-V 2.0 のみ)</span><span class="sxs-lookup"><span data-stu-id="f722a-157">Microsoft Office 2007 applications (UE-V 2.0 only)</span></span>

<span data-ttu-id="f722a-158">Internet Explorer 8、9、10</span><span class="sxs-lookup"><span data-stu-id="f722a-158">Internet Explorer 8, 9, and 10</span></span>

<span data-ttu-id="f722a-159">Internet Explorer 11 (UE-V 2.1 SP1 および 2.1)</span><span class="sxs-lookup"><span data-stu-id="f722a-159">Internet Explorer 11 in UE-V 2.1 SP1 and 2.1</span></span>

<span data-ttu-id="f722a-160">多くの Windows アプリケーション (Xbox など)</span><span class="sxs-lookup"><span data-stu-id="f722a-160">Many Windows applications, such as Xbox</span></span>

<span data-ttu-id="f722a-161">メモ帳などの多くの Windows デスクトップアプリケーション</span><span class="sxs-lookup"><span data-stu-id="f722a-161">Many Windows desktop applications, such as Notepad</span></span>

<span data-ttu-id="f722a-162">デスクトップの背景や壁紙など、多くの Windows 設定</span><span class="sxs-lookup"><span data-stu-id="f722a-162">Many Windows settings, such as desktop background or wallpaper</span></span>

**<span data-ttu-id="f722a-163">注</span><span class="sxs-lookup"><span data-stu-id="f722a-163">Note</span></span>**  
<span data-ttu-id="f722a-164">また、UE-V をカスタマイズして、既定で同期されていないアプリケーションの[設定を同期する](https://technet.microsoft.com/library/dn458942.aspx)こともできます。</span><span class="sxs-lookup"><span data-stu-id="f722a-164">You can also [customize UE-V to synchronize settings](https://technet.microsoft.com/library/dn458942.aspx) for applications other than those synchronized by default.</span></span>



## <span data-ttu-id="f722a-165">UE-V を他の Microsoft 製品と比較する</span><span class="sxs-lookup"><span data-stu-id="f722a-165">Compare UE-V to other Microsoft products</span></span>


<span data-ttu-id="f722a-166">この表を使用して、UE-V と Windows 7 のプロファイルの同期、Windows 8 でのプロファイルの同期、Microsoft アカウントの同期 PC 設定機能の比較を行います。</span><span class="sxs-lookup"><span data-stu-id="f722a-166">Use this table to compare UE-V to Synchronize Profiles in Windows 7, Synchronize Profiles in Windows 8, and the Sync PC Settings feature of Microsoft account.</span></span>

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f722a-167">機能</span><span class="sxs-lookup"><span data-stu-id="f722a-167">Feature</span></span></th>
<th align="left"><span data-ttu-id="f722a-168">Windows 7 を使用してプロファイルを同期する</span><span class="sxs-lookup"><span data-stu-id="f722a-168">Synchronize Profiles using Windows 7</span></span></th>
<th align="left"><span data-ttu-id="f722a-169">Windows 8 を使用してプロファイルを同期する</span><span class="sxs-lookup"><span data-stu-id="f722a-169">Synchronize Profiles using Windows 8</span></span></th>
<th align="left"><span data-ttu-id="f722a-170">Windows 10 を使用してプロファイルを同期する</span><span class="sxs-lookup"><span data-stu-id="f722a-170">Synchronize Profiles using Windows 10</span></span></th>
<th align="left"><span data-ttu-id="f722a-171">Microsoft アカウント</span><span class="sxs-lookup"><span data-stu-id="f722a-171">Microsoft account</span></span></th>
<th align="left"><span data-ttu-id="f722a-172">UE-V 2.0</span><span class="sxs-lookup"><span data-stu-id="f722a-172">UE-V 2.0</span></span></th>
<th align="left"><span data-ttu-id="f722a-173">UE-V 2.1 および 2.1 SP1</span><span class="sxs-lookup"><span data-stu-id="f722a-173">UE-V 2.1 and 2.1 SP1</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f722a-174">複数のコンピューター間で設定を同期する</span><span class="sxs-lookup"><span data-stu-id="f722a-174">Synchronize settings between multiple computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-175">●</span><span class="sxs-lookup"><span data-stu-id="f722a-175">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-176">●</span><span class="sxs-lookup"><span data-stu-id="f722a-176">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-177">●</span><span class="sxs-lookup"><span data-stu-id="f722a-177">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-178">●</span><span class="sxs-lookup"><span data-stu-id="f722a-178">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-179">●</span><span class="sxs-lookup"><span data-stu-id="f722a-179">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-180">●</span><span class="sxs-lookup"><span data-stu-id="f722a-180">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f722a-181">物理アプリと仮想アプリの間で設定を同期する</span><span class="sxs-lookup"><span data-stu-id="f722a-181">Synchronize settings between physical and virtual apps</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f722a-182">●</span><span class="sxs-lookup"><span data-stu-id="f722a-182">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-183">●</span><span class="sxs-lookup"><span data-stu-id="f722a-183">●</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f722a-184">Windows アプリの設定を同期する</span><span class="sxs-lookup"><span data-stu-id="f722a-184">Synchronize Windows app settings</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f722a-185">●</span><span class="sxs-lookup"><span data-stu-id="f722a-185">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-186">●</span><span class="sxs-lookup"><span data-stu-id="f722a-186">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-187">●</span><span class="sxs-lookup"><span data-stu-id="f722a-187">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f722a-188">WMI を使用して管理する</span><span class="sxs-lookup"><span data-stu-id="f722a-188">Manage via WMI</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f722a-189">●</span><span class="sxs-lookup"><span data-stu-id="f722a-189">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-190">●</span><span class="sxs-lookup"><span data-stu-id="f722a-190">●</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f722a-191">●</span><span class="sxs-lookup"><span data-stu-id="f722a-191">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-192">●</span><span class="sxs-lookup"><span data-stu-id="f722a-192">●</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f722a-193">設定の変更を定期的に同期する</span><span class="sxs-lookup"><span data-stu-id="f722a-193">Synchronize settings changes on a regular basis</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f722a-194">●</span><span class="sxs-lookup"><span data-stu-id="f722a-194">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-195">●</span><span class="sxs-lookup"><span data-stu-id="f722a-195">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-196">●</span><span class="sxs-lookup"><span data-stu-id="f722a-196">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f722a-197">セットアップの最小構成</span><span class="sxs-lookup"><span data-stu-id="f722a-197">Minimal configuration for Setup</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-198">●</span><span class="sxs-lookup"><span data-stu-id="f722a-198">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-199">●</span><span class="sxs-lookup"><span data-stu-id="f722a-199">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-200">●</span><span class="sxs-lookup"><span data-stu-id="f722a-200">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-201">●</span><span class="sxs-lookup"><span data-stu-id="f722a-201">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-202">●</span><span class="sxs-lookup"><span data-stu-id="f722a-202">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-203">●</span><span class="sxs-lookup"><span data-stu-id="f722a-203">●</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f722a-204">ドメインに参加していないコンピューターでのサポート</span><span class="sxs-lookup"><span data-stu-id="f722a-204">Supported on non-domain joined computers</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f722a-205">●</span><span class="sxs-lookup"><span data-stu-id="f722a-205">●</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f722a-206">プライマリコンピューターの Active Directory 属性をサポートしています</span><span class="sxs-lookup"><span data-stu-id="f722a-206">Supports Primary Computer Active Directory attribute</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f722a-207">●</span><span class="sxs-lookup"><span data-stu-id="f722a-207">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-208">●</span><span class="sxs-lookup"><span data-stu-id="f722a-208">●</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f722a-209">仮想デスクトップインフラストラクチャ (VDI)/デスクトップサービス (RDS) とリッチデスクトップの間で設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="f722a-209">Synchronizes settings between virtual desktop infrastructure (VDI)/Remote Desktop Services (RDS) and rich desktops</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f722a-210">●</span><span class="sxs-lookup"><span data-stu-id="f722a-210">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-211">●</span><span class="sxs-lookup"><span data-stu-id="f722a-211">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f722a-212">無制限のストレージスペースの設定</span><span class="sxs-lookup"><span data-stu-id="f722a-212">Unlimited setting storage space</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-213">●</span><span class="sxs-lookup"><span data-stu-id="f722a-213">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-214">●</span><span class="sxs-lookup"><span data-stu-id="f722a-214">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-215">●</span><span class="sxs-lookup"><span data-stu-id="f722a-215">●</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f722a-216">●</span><span class="sxs-lookup"><span data-stu-id="f722a-216">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-217">●</span><span class="sxs-lookup"><span data-stu-id="f722a-217">●</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f722a-218">同期するアプリの設定の選択</span><span class="sxs-lookup"><span data-stu-id="f722a-218">Choice in which app settings to synchronize</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f722a-219">●</span><span class="sxs-lookup"><span data-stu-id="f722a-219">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-220">●</span><span class="sxs-lookup"><span data-stu-id="f722a-220">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f722a-221">IT プロフェッショナル向けのバックアップ/復元</span><span class="sxs-lookup"><span data-stu-id="f722a-221">Backup/Restore for IT Pro</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f722a-222">●</span><span class="sxs-lookup"><span data-stu-id="f722a-222">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-223">一部</span><span class="sxs-lookup"><span data-stu-id="f722a-223">Partial</span></span></p></td>
<td align="left"><p><span data-ttu-id="f722a-224">●</span><span class="sxs-lookup"><span data-stu-id="f722a-224">●</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="f722a-225">UE-V 2. x のリリースノート</span><span class="sxs-lookup"><span data-stu-id="f722a-225">UE-V 2.x Release Notes</span></span>


<span data-ttu-id="f722a-226">詳細と最新ニュースについては、このドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f722a-226">For more information, and for late-breaking news that did not make it into the documentation, see</span></span>

-   [<span data-ttu-id="f722a-227">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="f722a-227">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

-   [<span data-ttu-id="f722a-228">Microsoft User Experience Virtualization (UE-V) 2.1 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="f722a-228">Microsoft User Experience Virtualization (UE-V) 2.1 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

-   [<span data-ttu-id="f722a-229">Microsoft User Experience Virtualization (UE-V) 2.0 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="f722a-229">Microsoft User Experience Virtualization (UE-V) 2.0 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

## <span data-ttu-id="f722a-230">この製品のその他のリソース</span><span class="sxs-lookup"><span data-stu-id="f722a-230">Other resources for this product</span></span>


-   [<span data-ttu-id="f722a-231">UE-V 2.x の概要</span><span class="sxs-lookup"><span data-stu-id="f722a-231">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="f722a-232">UE-V の展開を準備する</span><span class="sxs-lookup"><span data-stu-id="f722a-232">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [<span data-ttu-id="f722a-233">UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="f722a-233">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="f722a-234">UE-V 2. x のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="f722a-234">Troubleshooting UE-V 2.x</span></span>](troubleshooting-ue-v-2x-both-uevv2.md)

-   [<span data-ttu-id="f722a-235">UE-V 2.x のテクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="f722a-235">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

### <span data-ttu-id="f722a-236">詳細情報</span><span class="sxs-lookup"><span data-stu-id="f722a-236">More information</span></span>

<a href="" id="mdop-techcenter-page"></a><span data-ttu-id="f722a-237">[MDOP TechCenter ページ](https://go.microsoft.com/fwlink/p/?LinkId=225286)最新の MDOP 情報とリソースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f722a-237">[MDOP TechCenter Page](https://go.microsoft.com/fwlink/p/?LinkId=225286) Learn about the latest MDOP information and resources.</span></span>

<a href="" id="mdop-information-experience"></a><span data-ttu-id="f722a-238">[MDOP 情報の操作](https://go.microsoft.com/fwlink/p/?LinkId=236032)MDOP テクノロジについては、ドキュメント、ビデオ、およびその他のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f722a-238">[MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) Find documentation, videos, and other resources for MDOP technologies.</span></span> <span data-ttu-id="f722a-239">また、 [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)または[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)をフォローして、[フィードバックを送信](mailto:MDOPDocs@microsoft.com)したり、更新プログラムに関する情報を確認したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="f722a-239">You can also [send us feedback](mailto:MDOPDocs@microsoft.com) or learn about updates by following us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>














