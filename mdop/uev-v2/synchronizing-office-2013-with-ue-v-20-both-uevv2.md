---
title: Office 2013 と UE-V 2.0 を同期する
description: Office 2013 と UE-V 2.0 を同期する
author: dansimp
ms.assetid: c46feb6d-28a8-4799-888d-053531dc5842
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c9b079d3f21e6ced689fa2101f5321fa9b1406c8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826887"
---
# <span data-ttu-id="c00e8-103">Office 2013 と UE-V 2.0 を同期する</span><span class="sxs-lookup"><span data-stu-id="c00e8-103">Synchronizing Office 2013 with UE-V 2.0</span></span>


<span data-ttu-id="c00e8-104">Microsoft User Experience Virtualization (UE-V) 2.0 では、UE-V テンプレートギャラリーから利用可能なテンプレートを使用して、Microsoft Office 2013 アプリケーション設定の同期がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="c00e8-104">Microsoft User Experience Virtualization (UE-V) 2.0 supports the synchronization of Microsoft Office 2013 application setting using a template available from the UE-V template gallery.</span></span> <span data-ttu-id="c00e8-105">Office 2013 Professional Plus の UE-V 5.0 および App-v SP2 のサポートでは、任意の UE-V 対応デバイスまたは仮想化デスクトップから、Office 2013 の仮想化されたインスタンスと同じ操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c00e8-105">The combination of UE-V 2 and App-V 5.0 SP2 support of Office 2013 Professional Plus enables the same experience on virtualized instance of Office 2013 from any UE-V-enabled device or virtualized desktop.</span></span>

<span data-ttu-id="c00e8-106">Office 2013 の UE-V アプリケーション設定のサポートを有効にするには、 [Microsoft User Experience Virtualization (ue-v) 2 テンプレートギャラリー](https://go.microsoft.com/fwlink/p/?LinkId=246589)からオフィシャルバージョンの ue-v Office 2013 テンプレートをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="c00e8-106">To activate UE-V application settings support of Office 2013, you can download official UE-V Office 2013 templates from the [Microsoft User Experience Virtualization (UE-V) 2 Template Gallery](https://go.microsoft.com/fwlink/p/?LinkId=246589).</span></span> <span data-ttu-id="c00e8-107">このリソースは、Microsoft が作成した UE-V の設定場所テンプレートと、コミュニティで開発された設定場所テンプレートを提供します。</span><span class="sxs-lookup"><span data-stu-id="c00e8-107">This resource provides Microsoft-authored UE-V settings location templates as well as community-developed settings location templates.</span></span>

## <span data-ttu-id="c00e8-108">UE-V での Microsoft Office のサポート</span><span class="sxs-lookup"><span data-stu-id="c00e8-108">Microsoft Office support in UE-V</span></span>


<span data-ttu-id="c00e8-109">UE-V 1.0 および UE-V 2 には、Microsoft Office 2010 の設定場所テンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c00e8-109">UE-V 1.0 and UE-V 2 include settings location templates for Microsoft Office 2010.</span></span> <span data-ttu-id="c00e8-110">これらのテンプレートは、UE-V Agent のインストールプロセスの一部として配布および登録されます。</span><span class="sxs-lookup"><span data-stu-id="c00e8-110">These templates are distributed and registered as part of the UE-V Agent installation process.</span></span> <span data-ttu-id="c00e8-111">これらのテンプレートは、ユーザーの Office エクスペリエンスをデバイス間で同期するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c00e8-111">These templates help synchronize users’ Office experience between devices.</span></span> <span data-ttu-id="c00e8-112">Office 2013 用の UE-V テンプレートは、Office 2010 のテンプレートについてよく似た設定エクスペリエンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="c00e8-112">The UE-V templates for Office 2013 provide a very similar settings experience to the templates for Office 2010.</span></span> <span data-ttu-id="c00e8-113">Office 365 のエクスペリエンスによってローミングされた Microsoft Office 2013 の設定は、これらの設定に含まれていません。</span><span class="sxs-lookup"><span data-stu-id="c00e8-113">Microsoft Office 2013 settings roamed by Office 365 experience are not included in these settings.</span></span> <span data-ttu-id="c00e8-114">Office 365 固有の設定のリストについては、「 [office 2013 のユーザーとローミングの設定の概要](https://go.microsoft.com/fwlink/p/?LinkId=391220)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c00e8-114">For a list of Office 365-specific settings, see [Overview of user and roaming settings for Office 2013](https://go.microsoft.com/fwlink/p/?LinkId=391220).</span></span>

## <span data-ttu-id="c00e8-115">同期された Office 2013 の設定</span><span class="sxs-lookup"><span data-stu-id="c00e8-115">Synchronized Office 2013 Settings</span></span>


<span data-ttu-id="c00e8-116">次の表には、UE-V での Office 2013 サポートの詳細情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c00e8-116">The following tables contain the details for Office 2013 support in UE-V:</span></span>

### <span data-ttu-id="c00e8-117">サポートされている Microsoft Office の UE-V テンプレート</span><span class="sxs-lookup"><span data-stu-id="c00e8-117">Supported UE-V templates for Microsoft Office</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c00e8-118">Office 2013 テンプレート (ue-v ギャラリーで利用可能な UE-V 2.0):</span><span class="sxs-lookup"><span data-stu-id="c00e8-118">Office 2013 templates (UE-V 2.0, available on UE-V gallery):</span></span></th>
<th align="left"><span data-ttu-id="c00e8-119">Office 2010 テンプレート (UE-V 1.0 &amp; 1.0 SP1):</span><span class="sxs-lookup"><span data-stu-id="c00e8-119">Office 2010 templates (UE-V 1.0 &amp; 1.0 SP1):</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c00e8-120">MicrosoftOffice2013Win32.xml</span><span class="sxs-lookup"><span data-stu-id="c00e8-120">MicrosoftOffice2013Win32.xml</span></span></p>
<p><span data-ttu-id="c00e8-121">MicrosoftOffice2013Win64.xml</span><span class="sxs-lookup"><span data-stu-id="c00e8-121">MicrosoftOffice2013Win64.xml</span></span></p>
<p><span data-ttu-id="c00e8-122">MicrosoftLync2013Win32.xml</span><span class="sxs-lookup"><span data-stu-id="c00e8-122">MicrosoftLync2013Win32.xml</span></span></p>
<p><span data-ttu-id="c00e8-123">MicrosoftLync2013Win64.xml</span><span class="sxs-lookup"><span data-stu-id="c00e8-123">MicrosoftLync2013Win64.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="c00e8-124">MicrosoftOffice2010Win32.xml</span><span class="sxs-lookup"><span data-stu-id="c00e8-124">MicrosoftOffice2010Win32.xml</span></span></p>
<p><span data-ttu-id="c00e8-125">MicrosoftOffice2010Win64.xml</span><span class="sxs-lookup"><span data-stu-id="c00e8-125">MicrosoftOffice2010Win64.xml</span></span></p>
<p><span data-ttu-id="c00e8-126">MicrosoftLync2010.xml</span><span class="sxs-lookup"><span data-stu-id="c00e8-126">MicrosoftLync2010.xml</span></span></p>
<p></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="c00e8-127">UE-V テンプレートでサポートされている Microsoft Office アプリケーション</span><span class="sxs-lookup"><span data-stu-id="c00e8-127">Microsoft Office Applications supported by the UE-V templates</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c00e8-128">Microsoft Access 2013</span><span class="sxs-lookup"><span data-stu-id="c00e8-128">Microsoft Access 2013</span></span></p>
<p><span data-ttu-id="c00e8-129">Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="c00e8-129">Microsoft Lync 2013</span></span></p>
<p><span data-ttu-id="c00e8-130">Microsoft Excel 2013</span><span class="sxs-lookup"><span data-stu-id="c00e8-130">Microsoft Excel 2013</span></span></p>
<p><span data-ttu-id="c00e8-131">Microsoft InfoPath 2013</span><span class="sxs-lookup"><span data-stu-id="c00e8-131">Microsoft InfoPath 2013</span></span></p>
<p><span data-ttu-id="c00e8-132">Microsoft OneNote 2013</span><span class="sxs-lookup"><span data-stu-id="c00e8-132">Microsoft OneNote 2013</span></span></p>
<p><span data-ttu-id="c00e8-133">Microsoft Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="c00e8-133">Microsoft Outlook 2013</span></span></p>
<p><span data-ttu-id="c00e8-134">Microsoft PowerPoint 2013</span><span class="sxs-lookup"><span data-stu-id="c00e8-134">Microsoft PowerPoint 2013</span></span></p>
<p><span data-ttu-id="c00e8-135">Microsoft Project 2013</span><span class="sxs-lookup"><span data-stu-id="c00e8-135">Microsoft Project 2013</span></span></p>
<p><span data-ttu-id="c00e8-136">Microsoft Publisher 2013</span><span class="sxs-lookup"><span data-stu-id="c00e8-136">Microsoft Publisher 2013</span></span></p>
<p><span data-ttu-id="c00e8-137">Microsoft SharePoint Designer 2013</span><span class="sxs-lookup"><span data-stu-id="c00e8-137">Microsoft SharePoint Designer 2013</span></span></p>
<p><span data-ttu-id="c00e8-138">Microsoft Visio 2013</span><span class="sxs-lookup"><span data-stu-id="c00e8-138">Microsoft Visio 2013</span></span></p>
<p><span data-ttu-id="c00e8-139">Microsoft Word 2013</span><span class="sxs-lookup"><span data-stu-id="c00e8-139">Microsoft Word 2013</span></span></p>
<p><span data-ttu-id="c00e8-140">Microsoft Office アップロードマネージャー</span><span class="sxs-lookup"><span data-stu-id="c00e8-140">Microsoft Office Upload Manager</span></span></p></td>
<td align="left"><p><span data-ttu-id="c00e8-141">Microsoft Access 2010</span><span class="sxs-lookup"><span data-stu-id="c00e8-141">Microsoft Access 2010</span></span></p>
<p><span data-ttu-id="c00e8-142">Microsoft Lync 2010</span><span class="sxs-lookup"><span data-stu-id="c00e8-142">Microsoft Lync 2010</span></span></p>
<p><span data-ttu-id="c00e8-143">Microsoft Excel 2010</span><span class="sxs-lookup"><span data-stu-id="c00e8-143">Microsoft Excel 2010</span></span></p>
<p><span data-ttu-id="c00e8-144">Microsoft InfoPath 2010</span><span class="sxs-lookup"><span data-stu-id="c00e8-144">Microsoft InfoPath 2010</span></span></p>
<p><span data-ttu-id="c00e8-145">Microsoft OneNote 2010</span><span class="sxs-lookup"><span data-stu-id="c00e8-145">Microsoft OneNote 2010</span></span></p>
<p><span data-ttu-id="c00e8-146">Microsoft Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="c00e8-146">Microsoft Outlook 2010</span></span></p>
<p><span data-ttu-id="c00e8-147">Microsoft PowerPoint 2010</span><span class="sxs-lookup"><span data-stu-id="c00e8-147">Microsoft PowerPoint 2010</span></span></p>
<p><span data-ttu-id="c00e8-148">Microsoft Project 2010</span><span class="sxs-lookup"><span data-stu-id="c00e8-148">Microsoft Project 2010</span></span></p>
<p><span data-ttu-id="c00e8-149">Microsoft Publisher 2010</span><span class="sxs-lookup"><span data-stu-id="c00e8-149">Microsoft Publisher 2010</span></span></p>
<p><span data-ttu-id="c00e8-150">Microsoft SharePoint Designer 2010</span><span class="sxs-lookup"><span data-stu-id="c00e8-150">Microsoft SharePoint Designer 2010</span></span></p>
<p><span data-ttu-id="c00e8-151">Microsoft Visio 2010</span><span class="sxs-lookup"><span data-stu-id="c00e8-151">Microsoft Visio 2010</span></span></p>
<p><span data-ttu-id="c00e8-152">Microsoft Word 2010</span><span class="sxs-lookup"><span data-stu-id="c00e8-152">Microsoft Word 2010</span></span></p>
<p></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c00e8-153">Office 2013 テンプレートの展開</span><span class="sxs-lookup"><span data-stu-id="c00e8-153">Deploying the Office 2013 templates</span></span>


<span data-ttu-id="c00e8-154">次のメソッドを使用して、UE-V 設定の場所テンプレートを展開できます。</span><span class="sxs-lookup"><span data-stu-id="c00e8-154">You can deploy UE-V settings location template with the following methods:</span></span>

-   <span data-ttu-id="c00e8-155">**PowerShell を使用**してテンプレートを登録しています。</span><span class="sxs-lookup"><span data-stu-id="c00e8-155">**Registering template via PowerShell**.</span></span> <span data-ttu-id="c00e8-156">Windows PowerShell を使用してコンピューターを管理する場合は、次の Windows PowerShell コマンドを管理者として開いて、この設定場所テンプレートを登録します。</span><span class="sxs-lookup"><span data-stu-id="c00e8-156">If you use Windows PowerShell to manage computers, run the following Windows PowerShell command open as an administrator to register this settings location template:</span></span>

    ``` syntax
    Register-UevTemplate -Path <Path_to_Template>
    ```

    <span data-ttu-id="c00e8-157">UE-V と Windows PowerShell を使用した詳細については、「 [Windows powershell と WMI を使った ue-v の設定の場所テンプレートの管理](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c00e8-157">For more information using UE-V and Windows PowerShell, see [Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md).</span></span>

-   <span data-ttu-id="c00e8-158">テンプレート**カタログパスを使用**してテンプレートを登録しています。</span><span class="sxs-lookup"><span data-stu-id="c00e8-158">**Registering template via Template Catalog Path**.</span></span> <span data-ttu-id="c00e8-159">ユーザーのコンピューター上のテンプレートを管理するために設定テンプレートカタログパスを使用している場合は、Office 2013 テンプレートを UE-V Agent で定義されているフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="c00e8-159">If you use the Settings Template Catalog Path to manage templates on users’ computers, copy the Office 2013 template into the folder defined in the UE-V Agent.</span></span> <span data-ttu-id="c00e8-160">次に、テンプレートの自動更新 (ApplySettingsCatalog.exe) スケジュールされたタスクが実行されたときに、設定場所テンプレートがデバイスに登録されます。</span><span class="sxs-lookup"><span data-stu-id="c00e8-160">The next time the Template Auto Update (ApplySettingsCatalog.exe) scheduled task runs, the settings location template will be registered on the device.</span></span> <span data-ttu-id="c00e8-161">詳細については、「 [ue-v 2 用の設定テンプレートカタログの展開](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c00e8-161">For more information, see [Deploying the Settings Template Catalog for UE-V 2](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue).</span></span>

-   <span data-ttu-id="c00e8-162">**Configuration Manager を使用**してテンプレートを登録しています。</span><span class="sxs-lookup"><span data-stu-id="c00e8-162">**Registering template via Configuration Manager**.</span></span> <span data-ttu-id="c00e8-163">Configuration Manager を使用して UE-V 設定ストレージテンプレートを管理している場合は、テンプレートベースライン CAB を再作成し、それを Configuration Manager にインポートして、ベースラインをクライアントに展開します。</span><span class="sxs-lookup"><span data-stu-id="c00e8-163">If you use Configuration Manager to manage your UE-V settings storage templates, then recreate the Template Baseline CAB, import it into Configuration Manager, and then deploy the baseline to your clients.</span></span> <span data-ttu-id="c00e8-164">詳細については、 [System Center 2012 構成パックの Microsoft User Experience Virtualization 2](https://go.microsoft.com/fwlink/?LinkId=317263)のドキュメントに記載されているガイダンスを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c00e8-164">For more information, see the guidance provided in the documentation for the [System Center 2012 Configuration Pack for Microsoft User Experience Virtualization 2](https://go.microsoft.com/fwlink/?LinkId=317263).</span></span>






 

 





