---
title: App-V Client レジストリの値
description: App-V Client レジストリの値
author: dansimp
ms.assetid: 46af5209-9762-47b9-afdb-9a2947e013f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 05cd807ff9882bc478aca07abc4a28cdea83086a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819807"
---
# <span data-ttu-id="2b4e9-103">App-V Client レジストリの値</span><span class="sxs-lookup"><span data-stu-id="2b4e9-103">App-V Client Registry Values</span></span>


<span data-ttu-id="2b4e9-104">Microsoft Application Virtualization (App-v) クライアントでは、その構成がレジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-104">The Microsoft Application Virtualization (App-V) client stores its configuration in the registry.</span></span> <span data-ttu-id="2b4e9-105">レジストリ内のデータの形式を理解している場合は、クライアントに関する有用な情報を収集することができます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-105">You can gather some useful information about the client if you understand the format of data in the registry.</span></span> <span data-ttu-id="2b4e9-106">また、レジストリエントリを変更して、多くのクライアント操作を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-106">You can also configure many client actions by changing registry entries.</span></span> <span data-ttu-id="2b4e9-107">このトピックでは、Application Virtualization (App-v) クライアントのレジストリキーをすべて一覧表示し、その用途について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-107">This topic lists all the Application Virtualization (App-V) client registry keys and explains their uses.</span></span>

**<span data-ttu-id="2b4e9-108">重要</span><span class="sxs-lookup"><span data-stu-id="2b4e9-108">Important</span></span>**  
<span data-ttu-id="2b4e9-109">64ビットオペレーティングシステムを実行しているコンピューターでは、次のセクションで説明されているキーと値は、HKEY \ _LOCAL \ _MACHINE \\ pc \\ wow6432node¥にあります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-109">On a computer running a 64-bit operating system, the keys and values described in the following sections will be under HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client.</span></span>



## <span data-ttu-id="2b4e9-110">構成キー</span><span class="sxs-lookup"><span data-stu-id="2b4e9-110">Configuration Key</span></span>


<span data-ttu-id="2b4e9-111">次の表では、HKEY \ _LOCAL \ _MACHINE \ ソフトウェア¥のレジストリ値に関連付けられているレジストリ値について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-111">The following table provides information about the registry values associated with the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2b4e9-112">名前</span><span class="sxs-lookup"><span data-stu-id="2b4e9-112">Name</span></span></th>
<th align="left"><span data-ttu-id="2b4e9-113">型</span><span class="sxs-lookup"><span data-stu-id="2b4e9-113">Type</span></span></th>
<th align="left"><span data-ttu-id="2b4e9-114">データ (例)</span><span class="sxs-lookup"><span data-stu-id="2b4e9-114">Data (Examples)</span></span></th>
<th align="left"><span data-ttu-id="2b4e9-115">説明</span><span class="sxs-lookup"><span data-stu-id="2b4e9-115">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-116">ProductName</span><span class="sxs-lookup"><span data-stu-id="2b4e9-116">ProductName</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-117">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-117">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-118">Microsoft Application Virtualization デスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="2b4e9-118">Microsoft Application Virtualization Desktop Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-119">変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-119">Do not modify.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-120">バージョン</span><span class="sxs-lookup"><span data-stu-id="2b4e9-120">Version</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-121">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-121">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-122">4.5.0.xxx</span><span class="sxs-lookup"><span data-stu-id="2b4e9-122">4.5.0.xxx</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-123">変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-123">Do not modify.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-124">ドライバー</span><span class="sxs-lookup"><span data-stu-id="2b4e9-124">Drivers</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-125">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-125">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-126">Sftfs.sys</span><span class="sxs-lookup"><span data-stu-id="2b4e9-126">Sftfs.sys</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-127">このキー値が存在する場合、最後にコアが開始されたときに停止エラーの原因となったドライバーの名前が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-127">If this key value is present, it contains the name of the driver that caused a stop error the last time the core was starting.</span></span> <span data-ttu-id="2b4e9-128">Stop エラーを修正した後、このキー値を削除して、sftlist を開始できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-128">After you have fixed the stop error, you must delete this key value so that sftlist can start.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-129">InstallPath</span><span class="sxs-lookup"><span data-stu-id="2b4e9-129">InstallPath</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-130">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-130">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-131">Default = C:\Program の Application Virtualization クライアント</span><span class="sxs-lookup"><span data-stu-id="2b4e9-131">Default=C:\Program Files\Microsoft Application Virtualization Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-132">クライアントがインストールされている場所。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-132">The location where the client is installed.</span></span> <span data-ttu-id="2b4e9-133">変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-133">Do not modify.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-134">LogFileName</span><span class="sxs-lookup"><span data-stu-id="2b4e9-134">LogFileName</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-135">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-135">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-136">既定値 = CSIDL_COMMON_APPDATA \Microsoft\Application 仮想化 Client\sftlog.txt</span><span class="sxs-lookup"><span data-stu-id="2b4e9-136">Default=CSIDL_COMMON_APPDATA\Microsoft\Application Virtualization Client\sftlog.txt</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-137">クライアントログファイルのパスと名前。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-137">The path and name for the client log file.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="2b4e9-138">注</span><span class="sxs-lookup"><span data-stu-id="2b4e9-138">Note</span></span></strong><br/><p><span data-ttu-id="2b4e9-139">以前のバージョンの App-v 4.6 SP1 を実行していて、ログファイルの名前や場所を変更した場合は、その変更を有効にするには、sftlist サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-139">If you are running an earlier version than App-V 4.6, SP1 and you modify the log file name or location, you must restart the sftlist service for the change to take effect.</span></span></p>
</div>
<div>

</div>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-140">LogMinSeverity</span><span class="sxs-lookup"><span data-stu-id="2b4e9-140">LogMinSeverity</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-141">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-141">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-142">既定値 = 4、情報</span><span class="sxs-lookup"><span data-stu-id="2b4e9-142">Default=4, Informational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-143">ログに書き込まれるメッセージを制御します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-143">Controls which messages are written to the log.</span></span> <span data-ttu-id="2b4e9-144">この値は、ログに記録されるもののしきい値を示します。その値以下のすべてがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-144">The value indicates a threshold of what is logged—everything less than or equal to that value is logged.</span></span> <span data-ttu-id="2b4e9-145">たとえば、値 0x3 (警告) の場合は、警告 (0x3)、エラー (0x2)、および重大なエラー (0x1) が記録されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-145">For example, a value of 0x3 (Warning) indicates that Warnings (0x3), Errors (0x2), and Critical Errors (0x1) are logged.</span></span></p>
<p><span data-ttu-id="2b4e9-146">値の範囲: 0x0 = なし、0x1 = Critical、0x2 = エラー、0x3 = 警告、0x4 = Information (既定)、0x5 = Verbose。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-146">Value Range: 0x0 = None, 0x1 = Critical, 0x2 = Error, 0x3 = Warning, 0x4 = Information (Default), 0x5 = Verbose.</span></span></p>
<p><span data-ttu-id="2b4e9-147">ログレベルは、Application Virtualization (App-v) クライアント本体とコマンドプロンプトから構成できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-147">The log level is configurable from the Application Virtualization (App-V) client console and from the command prompt.</span></span> <span data-ttu-id="2b4e9-148">コマンドプロンプトでは、/verboselog sftlist.exe コマンドはのログレベルを verbose に上げます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-148">At a command prompt, the command sftlist.exe /verboselog will increase the log level to verbose.</span></span> <span data-ttu-id="2b4e9-149">コマンドラインの詳細について詳しくは、</span><span class="sxs-lookup"><span data-stu-id="2b4e9-149">For more information on command-line details see</span></span></p>
<p><a href="https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467">https://go.microsoft.com/fwlink/?LinkId=141467https://go.microsoft.com/fwlink/?LinkId=141467</a></p>
<p><span data-ttu-id="2b4e9-150">.</span><span class="sxs-lookup"><span data-stu-id="2b4e9-150">.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-151">LogRolloverCount</span><span class="sxs-lookup"><span data-stu-id="2b4e9-151">LogRolloverCount</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-152">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-152">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-153">既定値 = 4</span><span class="sxs-lookup"><span data-stu-id="2b4e9-153">Default=4</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-154">リセットされたときに保持されるログファイルのバックアップコピーの数を定義します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-154">Defines the number of backup copies of the log file that are kept when it is reset.</span></span> <span data-ttu-id="2b4e9-155">有効な範囲は 0 ~ 9999 です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-155">The valid range is 0–9999.</span></span> <span data-ttu-id="2b4e9-156">既定値は4です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-156">The default is 4.</span></span> <span data-ttu-id="2b4e9-157">値が0の場合、コピーは保持されません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-157">A value of 0 means no copies will be kept.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-158">LogMaxSize</span><span class="sxs-lookup"><span data-stu-id="2b4e9-158">LogMaxSize</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-159">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-159">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-160">既定値 = 256</span><span class="sxs-lookup"><span data-stu-id="2b4e9-160">Default=256</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-161">リセットされるまでのログファイルの最大サイズをメガバイト (MB) で定義します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-161">Defines the maximum size in megabytes (MB) that the log file can grow before being reset.</span></span> <span data-ttu-id="2b4e9-162">既定のサイズは 256 MB です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-162">The default size is 256 MB.</span></span> <span data-ttu-id="2b4e9-163">このサイズに達すると、次回の書き込み時にログのリセットが強制的に行われます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-163">When this size is reached, a log reset will be forced on the next write attempt.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-164">SystemEventLogLevel</span><span class="sxs-lookup"><span data-stu-id="2b4e9-164">SystemEventLogLevel</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-165">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-165">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-166">既定値 = 0x4 (App-v 4.5)</span><span class="sxs-lookup"><span data-stu-id="2b4e9-166">Default=0x4 (App-V 4.5)</span></span></p>
<p><span data-ttu-id="2b4e9-167">Default = 0x3 (App-V 4.6)</span><span class="sxs-lookup"><span data-stu-id="2b4e9-167">Default=0x3 (App-V 4.6)</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-168">ログメッセージが NT イベントログに書き込まれるログレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-168">Indicates the logging level at which log messages are written to the NT event log.</span></span> <span data-ttu-id="2b4e9-169">この値は、ログに記録されるもののしきい値を示します。つまり、その値と同じか、またはそれより小さいすべてのものがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-169">The value indicates a threshold of what is logged—that is, everything equal to or less than that value is logged.</span></span> <span data-ttu-id="2b4e9-170">たとえば、値 0x3 (警告) の場合は、警告 (0x3)、エラー (0x2)、および重大なエラー (0x1) が記録されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-170">For example, a value of 0x3 (Warning) indicates that Warnings (0x3), Errors (0x2), and Critical Errors (0x1) are logged.</span></span></p>
<p><span data-ttu-id="2b4e9-171">値の範囲</span><span class="sxs-lookup"><span data-stu-id="2b4e9-171">Value Range</span></span></p>
<p><span data-ttu-id="2b4e9-172">0x0 = なし</span><span class="sxs-lookup"><span data-stu-id="2b4e9-172">0x0 = None</span></span></p>
<p><span data-ttu-id="2b4e9-173">0x1 = 重要</span><span class="sxs-lookup"><span data-stu-id="2b4e9-173">0x1 = Critical</span></span></p>
<p><span data-ttu-id="2b4e9-174">0x2 = エラー</span><span class="sxs-lookup"><span data-stu-id="2b4e9-174">0x2 = Error</span></span></p>
<p><span data-ttu-id="2b4e9-175">0x3 = 警告</span><span class="sxs-lookup"><span data-stu-id="2b4e9-175">0x3 = Warning</span></span></p>
<p><span data-ttu-id="2b4e9-176">0x4 = 情報 (既定)</span><span class="sxs-lookup"><span data-stu-id="2b4e9-176">0x4 = Information (Default)</span></span></p>
<p><span data-ttu-id="2b4e9-177">0x5 = Verbose</span><span class="sxs-lookup"><span data-stu-id="2b4e9-177">0x5 = Verbose</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-178">AllowIndependentFileStreaming</span><span class="sxs-lookup"><span data-stu-id="2b4e9-178">AllowIndependentFileStreaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-179">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-179">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-180">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-180">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-181">クライアントが APPLICATIONSOURCEROOT パラメーターで構成されているかどうかに関係なく、ファイルからのストリーミングを有効にするかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-181">Indicates whether streaming from file will be enabled regardless of how the client has been configured with the APPLICATIONSOURCEROOT parameter.</span></span> <span data-ttu-id="2b4e9-182">FALSE に設定すると、OSD HREF または APPLICATIONSOURCEROOT パラメーターにファイルパスが含まれている場合でも、トランスポートでファイルのストリーミングを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-182">If set to FALSE, the transport will not enable streaming from files even if the OSD HREF or the APPLICATIONSOURCEROOT parameter contains a file path.</span></span></p>
<p><span data-ttu-id="2b4e9-183">0x0 = False (既定値)</span><span class="sxs-lookup"><span data-stu-id="2b4e9-183">0x0=False (default)</span></span></p>
<p><span data-ttu-id="2b4e9-184">0x1 = True</span><span class="sxs-lookup"><span data-stu-id="2b4e9-184">0x1=True</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-185">ApplicationSourceRoot</span><span class="sxs-lookup"><span data-stu-id="2b4e9-185">ApplicationSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-186">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-186">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-187">rtsps://mainserver:322/prodapps</span><span class="sxs-lookup"><span data-stu-id="2b4e9-187">rtsps://mainserver:322/prodapps</span></span></p>
<p><a href="https://mainserver:443/prodapps" data-raw-source="https://mainserver:443/prodapps">https://mainserver:443/prodapps</a></p>
<p><span data-ttu-id="2b4e9-188">ファイル://\uncserver\share\prodapps</span><span class="sxs-lookup"><span data-stu-id="2b4e9-188">file://\uncserver\share\prodapps</span></span></p>
<p><span data-ttu-id="2b4e9-189">ファイル:/\ ターミナルの共有を、</span><span class="sxs-lookup"><span data-stu-id="2b4e9-189">file://\uncserver\share</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-190">管理者または電子ソフトウェア配布 (ESD) システムを有効にし、トポロジ管理スキームに従ってアプリケーションの読み込みを確実に実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-190">Enables an administrator or electronic software distribution (ESD) system to ensure application loading is performed according to the topology management scheme.</span></span> <span data-ttu-id="2b4e9-191">このキー値を使って、アプリケーションの HREF 要素 (ソースの場所など) の OSD コードベースをオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-191">Use this key value to override the OSD CODEBASE for the HREF element (for example, the source location) for an application.</span></span> <span data-ttu-id="2b4e9-192">アプリケーションソースのルートは、Url と汎用名前付け規則 (UNC) のパス形式をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-192">Application Source Root supports URLs and Universal Naming Convention (UNC) path formats.</span></span></p>
<p><span data-ttu-id="2b4e9-193">URL パスの正しい形式は、//servername: [port] [/path] [/] で、ポートとパスは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-193">The correct format for the URL path is protocol://servername:[port][/path][/], where port and path are optional.</span></span> <span data-ttu-id="2b4e9-194">ポートが指定されていない場合は、プロトコルの既定のポートが使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-194">If a port is not specified, the default port for the protocol is used.</span></span> <span data-ttu-id="2b4e9-195">OSD URL の protocol:/server: port 部分のみが置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-195">Only the protocol://server:port portion of the OSD URL is replaced.</span></span> </p>
<p><span data-ttu-id="2b4e9-196">UNC パスの正しい形式は \ computer名のフォルダーです。 [フォルダー] []。フォルダーは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-196">The correct format for the UNC path is \computername\sharefolder[folder][], where folder is optional.</span></span> <span data-ttu-id="2b4e9-197">コンピューター名には完全修飾ドメイン名 (FQDN) または IP アドレスを使用できます。また、フォルダー名はドライブ文字にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-197">The computer name can be a fully qualified domain name (FQDN) or an IP address, and sharefolder can be a drive letter.</span></span> <span data-ttu-id="2b4e9-198">OSD パスの \ computer¥¥フォルダーまたはドライブ文字の部分のみが置換されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-198">Only the \computername\sharefolder or drive letter portion of the OSD path is replaced.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-199">OSDSourceRoot</span><span class="sxs-lookup"><span data-stu-id="2b4e9-199">OSDSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-200">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-200">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-201">\computername\sharefolder\resource</span><span class="sxs-lookup"><span data-stu-id="2b4e9-201">\computername\sharefolder\resource</span></span></p>
<p><span data-ttu-id="2b4e9-202">\ コンピューターのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="2b4e9-202">\computername\content</span></span></p>
<p><span data-ttu-id="2b4e9-203">C:\ フォルダー名</span><span class="sxs-lookup"><span data-stu-id="2b4e9-203">C:\foldername</span></span></p>
<p><a href="http://computername/productivity/" data-raw-source="http://computername/productivity/">http://computername/productivity/</a></p>
<p><a href="https://computername/productivity/" data-raw-source="https://computername/productivity/">https://computername/productivity/</a></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-204">管理者が、文書中にシーケンス処理されたアプリケーションパッケージの OSD ファイル取得のソースの場所を指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-204">Enables an administrator to specify a source location for OSD file retrieval for a sequenced application package during publication.</span></span> <span data-ttu-id="2b4e9-205">OSDSourceRoot の受け付け可能な形式には、UNC パスと Url (http または https) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-205">Acceptable formats for the OSDSourceRoot include UNC paths and URLs (http or https).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-206">IconSourceRoot</span><span class="sxs-lookup"><span data-stu-id="2b4e9-206">IconSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-207">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-207">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-208">\computername\sharefolder\resource</span><span class="sxs-lookup"><span data-stu-id="2b4e9-208">\computername\sharefolder\resource</span></span></p>
<p><span data-ttu-id="2b4e9-209">\ コンピューターのコンテンツ</span><span class="sxs-lookup"><span data-stu-id="2b4e9-209">\computername\content</span></span></p>
<p><span data-ttu-id="2b4e9-210">C:\ フォルダー名</span><span class="sxs-lookup"><span data-stu-id="2b4e9-210">C:\foldername</span></span></p>
<p><a href="http://computername/productivity/" data-raw-source="http://computername/productivity/">http://computername/productivity/</a></p>
<p><a href="https://computername/productivity/" data-raw-source="https://computername/productivity/">https://computername/productivity/</a></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-211">管理者が、文書中にシーケンス処理されたアプリケーションパッケージのアイコンファイル取得のソースの場所を指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-211">Enables an administrator to specify a source location for icon file retrieval for a sequenced application package during publication.</span></span> <span data-ttu-id="2b4e9-212">IconSourceRoot に使用できる形式には、UNC パスと Url (http または https) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-212">Acceptable formats for the IconSourceRoot include UNC paths and URLs (http or https).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-213">AutoLoadTriggers</span><span class="sxs-lookup"><span data-stu-id="2b4e9-213">AutoLoadTriggers</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-214">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-214">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-215">既定値 = 5</span><span class="sxs-lookup"><span data-stu-id="2b4e9-215">Default=5</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-216">自動ロードはクライアントランタイムポリシー構成パラメーターであり、仮想化されたアプリケーションのセカンダリ機能ブロックをバックグラウンドで自動的にクライアントにストリーミングすることを可能にします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-216">AutoLoad is a client runtime policy configuration parameter that enables the secondary feature block of a virtualized application to be streamed to the client automatically in the background.</span></span> <span data-ttu-id="2b4e9-217">自動ロードトリガーは、アプリケーションの自動読み込みを開始するイベントを示すフラグです。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-217">The AutoLoad triggers are flags to indicate events that initiate auto-loading of applications.</span></span> <span data-ttu-id="2b4e9-218">自動ロードは、バックグラウンドストリーミングを暗黙的に使用して、アプリケーションをキャッシュに完全に読み込むことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-218">AutoLoad implicitly uses background streaming to enable the application to be fully loaded into cache.</span></span> <span data-ttu-id="2b4e9-219">プライマリ機能ブロックが最初に読み込まれ、その他の機能ブロックがバックグラウンドに読み込まれて、アプリケーションのユーザー操作などのフォアグラウンド操作が有効になり、最適に認識されたパフォーマンスが得られます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-219">The primary feature block will be loaded first, and the remaining feature blocks will be loaded in the background to enable foreground operations, such as user interaction with applications, to take place and provide optimal perceived performance.</span></span></p>
<p><span data-ttu-id="2b4e9-220">ビットマスク値:</span><span class="sxs-lookup"><span data-stu-id="2b4e9-220">Bit mask values:</span></span></p>
<p><span data-ttu-id="2b4e9-221">(0) Never: どのビットも設定されていません (値は 0)。トリガーが設定されていないため、自動読み込みは実行されません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-221">(0) Never: No bits are set (value is 0), no auto loading will be performed, because there are no triggers set.</span></span></p>
<p><span data-ttu-id="2b4e9-222">(1) OnLaunch: 読み込みは、ユーザーがアプリケーションを起動したときに開始されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-222">(1) OnLaunch: Loading starts when a user starts an application.</span></span></p>
<p><span data-ttu-id="2b4e9-223">(2) OnRefresh: アプリケーションが公開されると、読み込みが開始されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-223">(2) OnRefresh: Loading starts when the application is published.</span></span> <span data-ttu-id="2b4e9-224">これは、公開の更新が発生したときなど、パッケージレコードが追加または更新されたときに発生します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-224">This occurs whenever the package record is added or updated—for example, when a publishing refresh occurs.</span></span></p>
<p><span data-ttu-id="2b4e9-225">(4) OnLogin: ユーザーがログインしたときに読み込みが開始されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-225">(4) OnLogin: Loading starts when a user logs in.</span></span></p>
<p><span data-ttu-id="2b4e9-226">(5) OnLaunch と Onlaunch: Default。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-226">(5) OnLaunch and OnLogin: Default.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-227">AutoLoadTarget</span><span class="sxs-lookup"><span data-stu-id="2b4e9-227">AutoLoadTarget</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-228">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-228">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-229">Default = 1</span><span class="sxs-lookup"><span data-stu-id="2b4e9-229">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-230">自動ロードトリガーが発生したときに自動的に読み込まれる内容を示します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-230">Indicates what will be auto-loaded when any given AutoLoad triggers occur.</span></span> <span data-ttu-id="2b4e9-231">ビットマスク値:</span><span class="sxs-lookup"><span data-stu-id="2b4e9-231">Bit mask values:</span></span></p>
<p><span data-ttu-id="2b4e9-232">(0) None: 設定されているトリガーに関係なく、自動読み込みは行われません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-232">(0) None: No auto-loading, regardless of what triggers may be set.</span></span></p>
<p><span data-ttu-id="2b4e9-233">(1) 以前に使用されたもの (既定): 自動ロードトリガーが有効になっている場合は、パッケージ内の少なくとも1つのアプリケーションが使用されている (開始または precached) パッケージのみを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-233">(1) PreviouslyUsed (default): If any AutoLoad trigger is enabled, load only the packages where at least one application in the package has been previously used—that is, started or precached.</span></span></p>
<p><span data-ttu-id="2b4e9-234">(2) すべて: 自動ロードトリガーが有効になっている場合、パッケージ (パッケージごと) またはすべてのパッケージ (クライアント用に設定) のすべてのアプリケーションが、まだ開始されているかどうかにかかわらず、自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-234">(2) All: If any AutoLoad trigger is enabled, all applications in the package (per package) or all packages (set for client) will be automatically loaded, whether or not they have ever been started.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-235">Requireのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="2b4e9-235">RequireAuthorizationIfCached</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-236">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-236">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-237">Default = 1</span><span class="sxs-lookup"><span data-stu-id="2b4e9-237">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-238">アプリケーションが既にキャッシュに含まれているかどうかにかかわらず、常に承認が必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-238">Indicates that authorization is always required, whether or not an application is already in cache.</span></span> <span data-ttu-id="2b4e9-239">設定可能な値:</span><span class="sxs-lookup"><span data-stu-id="2b4e9-239">Possible values:</span></span></p>
<p><span data-ttu-id="2b4e9-240">0 = False: 常にサーバーへの接続を試行します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-240">0=False: Always try to connect to the server.</span></span> <span data-ttu-id="2b4e9-241">サーバーへの接続を確立できない場合でも、クライアントは、以前にキャッシュに読み込まれているアプリケーションを起動することを許可します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-241">If a connection to the server cannot be established, the client still allows the user to launch an application that has previously been loaded into cache.</span></span></p>
<p><span data-ttu-id="2b4e9-242">1 = True (既定): アプリケーションは、起動時に常に承認されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-242">1=True (default): Application always must be authorized at startup.</span></span> <span data-ttu-id="2b4e9-243">RTSP ストリームアプリケーションの場合は、ユーザー認証トークンがサーバーに送信され、承認があります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-243">For RTSP streamed applications, the user authorization token is sent to the server for authorization.</span></span> <span data-ttu-id="2b4e9-244">ファイルベースのアプリケーションの場合、ファイル Acl は、ユーザーがアプリケーションにアクセスできるかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-244">For file-based applications, file ACLs control whether a user may access the application.</span></span></p>
<p><span data-ttu-id="2b4e9-245">変更を有効にするには、sftlist サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-245">Restart the sftlist service for the change to take effect.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-246">UserDataDirectory</span><span class="sxs-lookup"><span data-stu-id="2b4e9-246">UserDataDirectory</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-247">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-247">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-248">APPDATA</span><span class="sxs-lookup"><span data-stu-id="2b4e9-248">%APPDATA%</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-249">アイコンキャッシュとユーザー設定が保存されている場所。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-249">Location where the icon cache and user settings are stored.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-250">GlobalDataDirectory</span><span class="sxs-lookup"><span data-stu-id="2b4e9-250">GlobalDataDirectory</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-251">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-251">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-252">C:\Users\Public\Documents</span><span class="sxs-lookup"><span data-stu-id="2b4e9-252">C:\Users\Public\Documents</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-253">グローバルアプリ-V データ (OSD ファイルのキャッシュ、アイコンファイル、ショートカット情報、.ini ファイルなどの SystemGuard リソースなど) に使用するディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-253">Directory to use for global App-V data, including caches for OSD files, icon files, shortcut information, and SystemGuard resources such as .ini files.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-254">AllowCrashes</span><span class="sxs-lookup"><span data-stu-id="2b4e9-254">AllowCrashes</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-255">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-255">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-256">0 または 1</span><span class="sxs-lookup"><span data-stu-id="2b4e9-256">0 or 1</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-257">Default = 0: 値が0の場合は、内部のプログラムの例外をキャッチして、クラッシュが発生したときに他のユーザーのアプリケーションが回復して続行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-257">Default=0: A value of 0 means that the client tries to catch internal program exceptions so that other user applications can recover and continue when a crash happens.</span></span> <span data-ttu-id="2b4e9-258">値1は、クライアントが内部プログラムの例外を処理できるようにして、デバッガーでキャプチャできるようにすることを意味します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-258">A value of 1 means that the client allows the internal program exceptions to occur so that they can be captured in a debugger.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-259">CoreInternalTimeout</span><span class="sxs-lookup"><span data-stu-id="2b4e9-259">CoreInternalTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-260">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-260">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-261">60</span><span class="sxs-lookup"><span data-stu-id="2b4e9-261">60</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-262">コアとフロントエンドの間の内部 IPC 要求のタイムアウト (秒単位)。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-262">Time-out in seconds for internal IPC requests between core and front-end.</span></span> <span data-ttu-id="2b4e9-263">変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-263">Do not modify.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-264">Default・ Ecombinetime</span><span class="sxs-lookup"><span data-stu-id="2b4e9-264">DefaultSuiteCombineTime</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-265">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-265">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-266">常用</span><span class="sxs-lookup"><span data-stu-id="2b4e9-266">10</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-267">この値は、プログラムが終了してから、同じスイート内の別のアプリケーションが実行されているときに、エラーメッセージが表示されないようになるまでの時間を示すために使われます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-267">This value is used to indicate how soon after being started that a program can shut down and not generate any error messages when another application in the same suite is running.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-268">SerializedSuiteLaunchTimeout</span><span class="sxs-lookup"><span data-stu-id="2b4e9-268">SerializedSuiteLaunchTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-269">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-269">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-270">Default = 60000</span><span class="sxs-lookup"><span data-stu-id="2b4e9-270">Default=60000</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-271">同じスイートでプログラムをシリアル化しようとしているときにクライアントが待機する時間 (ミリ秒単位) を定義します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-271">Defines how long in milliseconds the client will wait as it tries to serialize program starts in the same suite.</span></span> <span data-ttu-id="2b4e9-272">クライアントがタイムアウトすると、プログラムの開始は続行されますが、シリアル化は行われません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-272">If the client times out, the program start will continue but it will not be serialized.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-273">ScriptTimeout</span><span class="sxs-lookup"><span data-stu-id="2b4e9-273">ScriptTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-274">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-274">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-275">300</span><span class="sxs-lookup"><span data-stu-id="2b4e9-275">300</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-276">WAIT = TRUE の場合、OSD ファイル内のスクリプトの既定のタイムアウト (秒)。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-276">Default time-out in seconds for scripts in OSD file if WAIT=TRUE.</span></span> <span data-ttu-id="2b4e9-277">タイムアウトを使って、スクリプト単位のタイムアウトを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-277">You can specify per-script time-outs with TIMEOUT instead of WAIT.</span></span> <span data-ttu-id="2b4e9-278">値が0の場合は待機しません。0xFFFFFFFF は無期限で待機することを意味します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-278">A value of 0 means no wait, and 0xFFFFFFFF means wait forever.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-279">LaunchRecordLogPath</span><span class="sxs-lookup"><span data-stu-id="2b4e9-279">LaunchRecordLogPath</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-280">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-280">String</span></span> </p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-281">HKLM または HKCU のいずれかで、この値にログファイルへの有効なパスが含まれている場合、SFTTray は、プログラムの起動、シャットダウン、起動に失敗したときに、接続されていないモードを開始または終了するときに、このログに書き込みを行います。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-281">If, under either HKLM or HKCU, this value contains a valid path to a log file, SFTTray will write to this log when programs start, shut down, fail to launch, and enter or exit disconnected mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-282">LaunchRecordMask</span><span class="sxs-lookup"><span data-stu-id="2b4e9-282">LaunchRecordMask</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-283">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-283">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-284">0x1A (26) ログ起動エラーと切断モードのエントリと終了アクティビティ。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-284">0x1A (26) log launch errors and disconnected mode entry and exit activity.</span></span></p>
<p><span data-ttu-id="2b4e9-285">0x1F (31) すべてをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-285">0x1F (31) logs everything.</span></span></p>
<p><span data-ttu-id="2b4e9-286">0x0 (0) は何も記録しません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-286">0x0 (0) logs nothing.</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-287">記録する5つのイベント (ビットマスク値) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-287">Specifies which of the five events are logged (bitmask values):</span></span></p>
<p><span data-ttu-id="2b4e9-288">1プログラムの開始</span><span class="sxs-lookup"><span data-stu-id="2b4e9-288">1 for program starts</span></span></p>
<p><span data-ttu-id="2b4e9-289">2起動エラーエラー</span><span class="sxs-lookup"><span data-stu-id="2b4e9-289">2 for launch failure errors</span></span></p>
<p><span data-ttu-id="2b4e9-290">4 (シャットダウンの場合)</span><span class="sxs-lookup"><span data-stu-id="2b4e9-290">4 for shutdowns</span></span></p>
<p><span data-ttu-id="2b4e9-291">切断モードに入るための8</span><span class="sxs-lookup"><span data-stu-id="2b4e9-291">8 for entering disconnected mode</span></span></p>
<p><span data-ttu-id="2b4e9-292">16サーバーに再接続するための切断モードの終了</span><span class="sxs-lookup"><span data-stu-id="2b4e9-292">16 for exiting disconnected mode to reconnect to a server</span></span></p>
<p><span data-ttu-id="2b4e9-293">これらの番号の任意の組み合わせを追加して、各メッセージを有効にします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-293">Add any combination of those numbers to turn on the respective messages.</span></span> <span data-ttu-id="2b4e9-294">レジストリにない場合は、既定値として0x1F が設定されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-294">Defaults to 0x1F if not in registry.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-295">LaunchRecordWriteTimeout</span><span class="sxs-lookup"><span data-stu-id="2b4e9-295">LaunchRecordWriteTimeout</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-296">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-296">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-297">既定値 = 3000</span><span class="sxs-lookup"><span data-stu-id="2b4e9-297">Default=3000</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-298">別のプロセスで使用している場合に、開始レコードログへの書き込みを試みるときに、トレイが待機する時間 (ミリ秒単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-298">Specifies in milliseconds how long the tray will wait when trying to write to the launch record log if another process is using it.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-299">ImportSearchPath</span><span class="sxs-lookup"><span data-stu-id="2b4e9-299">ImportSearchPath</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-300">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-300">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-301">d:\files;C:\documents and と settings\user1\SFTs</span><span class="sxs-lookup"><span data-stu-id="2b4e9-301">d:\files;C:\documents and settings\user1\SFTs</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-302">ユーザーにディレクトリの選択を求める前に、ポータブル SFT ファイルを検索するための最大5つのディレクトリのセミコロンで区切られたリスト。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-302">A semicolon delimited list of up to five directories to search for portable SFT files before prompting the user to select a directory.</span></span> <span data-ttu-id="2b4e9-303">パスの末尾のバックスラッシュは省略可能です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-303">Trailing backslash in paths is optional.</span></span> <span data-ttu-id="2b4e9-304">この値は既定では存在しないため、手動で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-304">This value is not present by default and must be set manually.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-305">UserImportPath</span><span class="sxs-lookup"><span data-stu-id="2b4e9-305">UserImportPath</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-306">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-306">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-307">D:\SFTs</span><span class="sxs-lookup"><span data-stu-id="2b4e9-307">D:\SFTs</span></span>\ </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-308">[HKCU] の下でのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-308">Valid only under HKCU.</span></span> <span data-ttu-id="2b4e9-309">パッケージのインポート用の SFT ファイルを検索しているときに、ユーザーが最後に参照した場所。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-309">The last location the user browsed to while finding a SFT file for package import.</span></span> <span data-ttu-id="2b4e9-310">SFT が正常に見つかった場合は、自動的に設定します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-310">Set automatically if the SFT is found successfully.</span></span> <span data-ttu-id="2b4e9-311">これは、SFT ファイルを自動的に検索するときに、以降のインポートで使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-311">This is used on successive imports when trying to automatically locate SFT files.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="2b4e9-312">共有キー</span><span class="sxs-lookup"><span data-stu-id="2b4e9-312">Shared Key</span></span>


<span data-ttu-id="2b4e9-313">HKEY \ _LOCAL \ _MACHINE \ ソフトウェア¥の共有キーは、App-v の各コンポーネント間で共有される値を制御します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-313">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Shared key controls values that are shared across App-V components.</span></span> <span data-ttu-id="2b4e9-314">次の表は、共有キーに関連付けられているレジストリ値に関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-314">The following table provides information about the registry values associated with the Shared key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2b4e9-315">名前</span><span class="sxs-lookup"><span data-stu-id="2b4e9-315">Name</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-316">型</span><span class="sxs-lookup"><span data-stu-id="2b4e9-316">Type</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-317">データ (例)</span><span class="sxs-lookup"><span data-stu-id="2b4e9-317">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-318">説明</span><span class="sxs-lookup"><span data-stu-id="2b4e9-318">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-319">DumpPath</span><span class="sxs-lookup"><span data-stu-id="2b4e9-319">DumpPath</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-320">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-320">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-321">Default = C:</span><span class="sxs-lookup"><span data-stu-id="2b4e9-321">Default=C:</span></span>\ </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-322">例外でミニダンプを生成するときに、ダンプファイルを作成する既定のパス。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-322">Default path to create dump files when generating a minidump on an exception.</span></span> <span data-ttu-id="2b4e9-323">これは既定で C:\ になります。指定しない場合は、</span><span class="sxs-lookup"><span data-stu-id="2b4e9-323">This defaults to C:\ if not specified.</span></span> <span data-ttu-id="2b4e9-324">クライアントインストーラーは、このキーを &lt; アプリの仮想化グローバルデータディレクトリ \Dumps. に設定します。 &gt;</span><span class="sxs-lookup"><span data-stu-id="2b4e9-324">The Client installer sets this key to the &lt;App Virtualization global data directory&gt;\Dumps.</span></span> <span data-ttu-id="2b4e9-325">Sequencer インストーラーは、このキーをインストールディレクトリに設定します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-325">The Sequencer installer sets this key to the installation directory.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-326">DumpPathSizeLimit</span><span class="sxs-lookup"><span data-stu-id="2b4e9-326">DumpPathSizeLimit</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-327">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-327">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-328">1000</span><span class="sxs-lookup"><span data-stu-id="2b4e9-328">1000</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-329">ミニダンプを保存するために使用できるディスク領域の最大サイズ (mb 単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-329">Specifies the maximum total amount of disk space in megabytes that can be used to store minidumps.</span></span> <span data-ttu-id="2b4e9-330">既定値は 1000 MB です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-330">Default = 1000 MB.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="2b4e9-331">ネットワークキー</span><span class="sxs-lookup"><span data-stu-id="2b4e9-331">Network Key</span></span>


<span data-ttu-id="2b4e9-332">HKEY \ _LOCAL \ _MACHINE ¥ \ ソフトウェア¥ the \ Softgrid\\ 4. 5\ client¥ネットワークキーは、さまざまなネットワーク関連パラメーターを制御します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-332">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network key controls a variety of network-related parameters.</span></span> <span data-ttu-id="2b4e9-333">このキーは主にネットワークトランスポートエージェントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-333">This key is primarily used by the network transport agent.</span></span> <span data-ttu-id="2b4e9-334">次の表は、ネットワークキーに関連付けられているレジストリ値に関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-334">The following table provides information about the registry values associated with the Network key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2b4e9-335">名前</span><span class="sxs-lookup"><span data-stu-id="2b4e9-335">Name</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-336">型</span><span class="sxs-lookup"><span data-stu-id="2b4e9-336">Type</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-337">データ (例)</span><span class="sxs-lookup"><span data-stu-id="2b4e9-337">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-338">説明</span><span class="sxs-lookup"><span data-stu-id="2b4e9-338">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-339">オンライン</span><span class="sxs-lookup"><span data-stu-id="2b4e9-339">Online</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-340">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-340">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-341">Default = 1</span><span class="sxs-lookup"><span data-stu-id="2b4e9-341">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-342">オフラインモードを有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-342">Enables or disables offline mode.</span></span> <span data-ttu-id="2b4e9-343">0に設定されている場合、クライアントは App-v 管理サーバーまたは公開サーバーと通信しません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-343">If set to 0, the client will not communicate with App-V Management Servers or publishing servers.</span></span> <span data-ttu-id="2b4e9-344">切断された操作の場合、クライアントは、アプリが app-v 管理サーバーに接続されていない場合でも、読み込まれたアプリケーションを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-344">In disconnected operations, the client can start a loaded application even when it is not connected to an App-V Management Server.</span></span> <span data-ttu-id="2b4e9-345">オフラインモードの場合、クライアントは、App-v 管理サーバーまたは公開サーバーに接続しようとしません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-345">In offline mode, the client does not attempt to connect to an App-V Management Server or publishing server.</span></span> <span data-ttu-id="2b4e9-346">切断された操作をオフラインでも使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-346">You must allow disconnected operations to be able to work offline.</span></span> <span data-ttu-id="2b4e9-347">既定値は1が有効 (オンライン) で、0は無効 (オフライン) です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-347">Default value is 1 enabled (online), and 0 is disabled (offline).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-348">AllowDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="2b4e9-348">AllowDisconnectedOperation</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-349">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-349">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-350">Default = 1</span><span class="sxs-lookup"><span data-stu-id="2b4e9-350">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-351">切断された操作を有効または無効にします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-351">Enables or disables disconnected operation.</span></span> <span data-ttu-id="2b4e9-352">既定値は1が有効で、0は無効です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-352">Default value is 1 enabled, and 0 is disabled.</span></span> <span data-ttu-id="2b4e9-353">切断された操作が有効になっている場合、app-v クライアントは、アプリが Hyper-v 管理サーバーに接続されていない場合でも、読み込まれたアプリケーションを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-353">When disconnected operations are enabled, the App-V client can start a loaded application even when it is not connected to an App-V Management Server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-354">FastConnectTimeout</span><span class="sxs-lookup"><span data-stu-id="2b4e9-354">FastConnectTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-355">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-355">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-356">既定値 = 1000</span><span class="sxs-lookup"><span data-stu-id="2b4e9-356">Default=1000</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-357">この値は、切断された操作モードに移行するタイミングを判断するために TCP 接続タイムアウト (ミリ秒単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-357">This value specifies the TCP connect time-out in milliseconds to determine when to go into disconnected operations mode.</span></span> <span data-ttu-id="2b4e9-358">この値は、既定の ConnectTimeout (20 秒) を上書きするために使用できます (ネットワークトランザクションの場合は、アプリ間の接続タイムアウト)。または、システムの TCP タイムアウトの約25秒。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-358">This value can be used to override the default ConnectTimeout of 20 seconds (App-V connect time-out for network transactions) or the system’s TCP time-out of approximately 25 seconds.</span></span> <span data-ttu-id="2b4e9-359">これにより、クライアントがすぐに切断された操作モードになります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-359">This brings the client into disconnected operations mode quickly.</span></span> <span data-ttu-id="2b4e9-360">次の接続で適用されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-360">Applied on the next connect.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-361">LimitDisconnectedOperation</span><span class="sxs-lookup"><span data-stu-id="2b4e9-361">LimitDisconnectedOperation</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-362">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-362">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-363">Default = 1</span><span class="sxs-lookup"><span data-stu-id="2b4e9-363">Default=1</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-364">AllowDisconnectedOperation が1の場合にのみ適用されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-364">Applicable only if AllowDisconnectedOperation is 1, enabled.</span></span> <span data-ttu-id="2b4e9-365">この値は、接続されていない操作でクライアントが操作できる時間制限があるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-365">This value determines whether there will be a time limit for how long the client will be allowed to operate in disconnected operations.</span></span> <span data-ttu-id="2b4e9-366">1 = 限定。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-366">1=limited.</span></span> <span data-ttu-id="2b4e9-367">0 = 無制限。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-367">0=unlimited.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-368">DOTimeoutMinutes</span><span class="sxs-lookup"><span data-stu-id="2b4e9-368">DOTimeoutMinutes</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-369">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-369">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-370">既定値 = 129600</span><span class="sxs-lookup"><span data-stu-id="2b4e9-370">Default=129,600</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-371">切断された操作モードでアプリケーションを使うことができる分数を示します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-371">Indicates how many minutes an application may be used in disconnected operation mode.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-372">有効な値は、1 ~ 999999 (1 ~ 1439998560 分) で表されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-372">The valid values are 1–999,999 in days expressed in minutes (1–1,439,998,560 minutes).</span></span> <span data-ttu-id="2b4e9-373">既定値は、90日または129600分です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-373">The default value is 90 days or 129,600 minutes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-374">プロトコル</span><span class="sxs-lookup"><span data-stu-id="2b4e9-374">Protocol</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-375">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-375">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-376">既定値 = 8</span><span class="sxs-lookup"><span data-stu-id="2b4e9-376">Default=8</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-377">使用する既定のプロトコル (TCP vs SSL)。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-377">Default protocol to use (TCP vs SSL).</span></span> <span data-ttu-id="2b4e9-378">[オプション] ダイアログで構成します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-378">Configure in Options Dialog.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-379">ReadTimeout</span><span class="sxs-lookup"><span data-stu-id="2b4e9-379">ReadTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-380">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-380">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-381">超える</span><span class="sxs-lookup"><span data-stu-id="2b4e9-381">20</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-382">ネットワークトランザクションのタイムアウトを秒単位で確認します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-382">Read time-out for network transactions, in seconds.</span></span> <span data-ttu-id="2b4e9-383">変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-383">Do not modify.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-384">WriteTimeout</span><span class="sxs-lookup"><span data-stu-id="2b4e9-384">WriteTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-385">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-385">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-386">超える</span><span class="sxs-lookup"><span data-stu-id="2b4e9-386">20</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-387">ネットワークトランザクションのタイムアウトを秒単位で作成します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-387">Write time-out for network transactions, in seconds.</span></span> <span data-ttu-id="2b4e9-388">変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-388">Do not modify.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-389">ConnectTimeout</span><span class="sxs-lookup"><span data-stu-id="2b4e9-389">ConnectTimeout</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-390">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-390">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-391">超える</span><span class="sxs-lookup"><span data-stu-id="2b4e9-391">20</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-392">ネットワークトランザクションのタイムアウトを秒単位で接続します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-392">Connect time-out for network transactions, in seconds.</span></span> <span data-ttu-id="2b4e9-393">変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-393">Do not modify.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-394">ReestablishmentRetries</span><span class="sxs-lookup"><span data-stu-id="2b4e9-394">ReestablishmentRetries</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-395">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-395">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-396">-</span><span class="sxs-lookup"><span data-stu-id="2b4e9-396">3</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-397">ドロップしたセッションを再確立する回数。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-397">The number of times to try to reestablish a dropped session.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-398">ReestablishmentInterval</span><span class="sxs-lookup"><span data-stu-id="2b4e9-398">ReestablishmentInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-399">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-399">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-400">マート</span><span class="sxs-lookup"><span data-stu-id="2b4e9-400">15</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-401">ドロップされたセッションを再確立するまでに待機する秒数。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-401">The number of seconds to wait between tries to reestablish a dropped session.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="2b4e9-402">Http キー</span><span class="sxs-lookup"><span data-stu-id="2b4e9-402">Http Key</span></span>


<span data-ttu-id="2b4e9-403">HKEY \ _LOCAL \ _MACHINE ¥ \ ソフトウェア¥ the \ Softgrid\\ 2015 (5: \) http キーは、Http ストリーミングに関連するパラメーターを制御します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-403">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\Http key controls the parameters that are related to Http streaming.</span></span> <span data-ttu-id="2b4e9-404">このキーは主にネットワークトランスポートエージェントによって使用されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-404">This key is used primarily by the network transport agent.</span></span> <span data-ttu-id="2b4e9-405">次の表は、Http キーに関連付けられているレジストリ値に関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-405">The following table provides information about the registry values that are associated with the Http key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2b4e9-406">名前</span><span class="sxs-lookup"><span data-stu-id="2b4e9-406">Name</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-407">型</span><span class="sxs-lookup"><span data-stu-id="2b4e9-407">Type</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-408">データ (例)</span><span class="sxs-lookup"><span data-stu-id="2b4e9-408">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-409">説明</span><span class="sxs-lookup"><span data-stu-id="2b4e9-409">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-410">LaunchIfNotFound</span><span class="sxs-lookup"><span data-stu-id="2b4e9-410">LaunchIfNotFound</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-411">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-411">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-412">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-412">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-413">Http サーバーへの接続が確立され、パッケージファイルが HTTP サーバーに存在しない場合の HTTP ストリーミングの動作を制御します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-413">Controls the behavior of HTTP streaming when a connection to the HTTP server can be established and the package file no longer exists on the HTTP server.</span></span> <span data-ttu-id="2b4e9-414">値が存在しない場合、または1に設定されていない場合は、以前にキャッシュに読み込まれていたアプリケーションを起動できません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-414">If the value does not exist or if it is not set to 1, the App-V client does not let you launch an application that has previously been loaded into cache.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-415">件</span><span class="sxs-lookup"><span data-stu-id="2b4e9-415">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-416">この値が1に設定されている場合は、以前にキャッシュに読み込まれたアプリケーションを App-v クライアントから起動できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-416">If this value is set to 1, the App-V client lets you launch an application that has previously been loaded into cache.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="2b4e9-417">ファイルシステムキー</span><span class="sxs-lookup"><span data-stu-id="2b4e9-417">File System Key</span></span>


<span data-ttu-id="2b4e9-418">HKEY \ _LOCAL \ _MACHINE ¥ xxx ¥ xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx ¥ xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx</span><span class="sxs-lookup"><span data-stu-id="2b4e9-418">The values that are contained under the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS key control the file system parameters for App-V.</span></span> <span data-ttu-id="2b4e9-419">次の表は、AppFS キーに関連付けられているレジストリ値に関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-419">The following table provides information about the registry values associated with the AppFS key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2b4e9-420">名前</span><span class="sxs-lookup"><span data-stu-id="2b4e9-420">Name</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-421">型</span><span class="sxs-lookup"><span data-stu-id="2b4e9-421">Type</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-422">データ (例)</span><span class="sxs-lookup"><span data-stu-id="2b4e9-422">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-423">説明</span><span class="sxs-lookup"><span data-stu-id="2b4e9-423">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-424">FileSize</span><span class="sxs-lookup"><span data-stu-id="2b4e9-424">FileSize</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-425">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-425">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-426">4096</span><span class="sxs-lookup"><span data-stu-id="2b4e9-426">4096</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-427">ファイルシステムキャッシュファイルの最大サイズ (mb)。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-427">Maximum size in megabytes of file system cache file.</span></span> <span data-ttu-id="2b4e9-428">レジストリでこの値を変更する場合は、状態を0に設定して再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-428">If you change this value in the registry, you must set State to 0 and reboot.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-429">FileName</span><span class="sxs-lookup"><span data-stu-id="2b4e9-429">FileName</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-430">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-430">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-431">C:\Users\Public\Documents\SoftGrid Client\sftfs.fsd</span><span class="sxs-lookup"><span data-stu-id="2b4e9-431">C:\Users\Public\Documents\SoftGrid Client\sftfs.fsd</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-432">ファイルシステムキャッシュファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-432">Location of file system cache file.</span></span> <span data-ttu-id="2b4e9-433">レジストリでこの値を変更する場合は、同じサイズのままにして、再起動するか、状態を0に設定して再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-433">If you change this value in the registry, you must either leave FileSize the same and reboot or set State to 0 and reboot.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-434">ドライブ</span><span class="sxs-lookup"><span data-stu-id="2b4e9-434">DriveLetter</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-435">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-435">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-436">Q:</span><span class="sxs-lookup"><span data-stu-id="2b4e9-436">Q:</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-437">使用可能な場合は、App-v ファイルシステムがマウントされるドライブ。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-437">Drive where App-V file system will be mounted, if it is available.</span></span> <span data-ttu-id="2b4e9-438">この値はリスナーまたはインストーラーによって設定され、ファイルシステムによって読み取られます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-438">This value is set either by the listener or the installer, and it is read by the file system.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-439">状態</span><span class="sxs-lookup"><span data-stu-id="2b4e9-439">State</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-440">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-440">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-441">0x100</span><span class="sxs-lookup"><span data-stu-id="2b4e9-441">0x100</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-442">ファイルシステムの状態。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-442">State of file system.</span></span> <span data-ttu-id="2b4e9-443">0に設定して再起動すると、ファイルシステムキャッシュが完全に消去されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-443">Set to 0 and reboot to completely clear the file system cache.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-444">FileSystemStorage</span><span class="sxs-lookup"><span data-stu-id="2b4e9-444">FileSystemStorage</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-445">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-445">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-446">¥ C $ SG</span><span class="sxs-lookup"><span data-stu-id="2b4e9-446">C:\Profiles\Joe\SG</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-447">[HKCU] の下に設定する、シンボリックリンクのパス。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-447">Path for symlinks, set under HKCU.</span></span> <span data-ttu-id="2b4e9-448">変更しない (構成の下でデータディレクトリを使用)。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-448">Do not modify (use data directory under Configuration to change).</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-449">GlobalFileSystemStorage</span><span class="sxs-lookup"><span data-stu-id="2b4e9-449">GlobalFileSystemStorage</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-450">String</span><span class="sxs-lookup"><span data-stu-id="2b4e9-450">String</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-451">C:\Users\Public\Documents\SoftGrid Client\AppFS ストレージ</span><span class="sxs-lookup"><span data-stu-id="2b4e9-451">C:\Users\Public\Documents\SoftGrid Client\AppFS Storage</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-452">グローバルファイルシステムデータのパス。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-452">Path for global file system data.</span></span> <span data-ttu-id="2b4e9-453">変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-453">Do not modify.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-454">MaxPercentToLockInCache</span><span class="sxs-lookup"><span data-stu-id="2b4e9-454">MaxPercentToLockInCache</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-455">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-455">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-456">既定値 = 90</span><span class="sxs-lookup"><span data-stu-id="2b4e9-456">Default=90</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-457">ロック可能なファイルシステムキャッシュファイルの最大割合を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-457">Specifies the maximum percentage of the file system cache file that can be locked.</span></span> <span data-ttu-id="2b4e9-458">変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-458">Do not modify.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-459">UnloadLeastRecentlyUsed</span><span class="sxs-lookup"><span data-stu-id="2b4e9-459">UnloadLeastRecentlyUsed</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-460">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-460">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-461">Default = 1</span><span class="sxs-lookup"><span data-stu-id="2b4e9-461">Default=1</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-462">ファイルシステムキャッシュスペース管理機能では、最近使用した (LRU) アルゴリズムが使用され、既定で有効になっています。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-462">The file system cache space management feature uses a Least Recently Used (LRU) algorithm and is enabled by default.</span></span> <span data-ttu-id="2b4e9-463">新しいパッケージに必要な領域がキャッシュ内の空き領域を超えている場合、App-v Client はこの機能を使用して、既存のパッケージがキャッシュから削除され、新しいパッケージ用のスペースが確保されるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-463">If the space that is required for a new package would exceed the available free space in the cache, the App-V Client uses this feature to determine which, if any, existing packages it can delete from the cache to make room for the new package.</span></span> <span data-ttu-id="2b4e9-464">クライアントは、"MinPkgAge" レジストリ値で指定された値よりも古い最終アクセス日のパッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-464">The client deletes the package with the oldest last-accessed date if it is older than the value specified in the MinPkgAge registry value.</span></span> <span data-ttu-id="2b4e9-465">0 (無効) と 1 (既定値、有効) の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-465">Values are 0 (disabled) and 1 (default, enabled).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-466">MinPackageAge</span><span class="sxs-lookup"><span data-stu-id="2b4e9-466">MinPackageAge</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-467">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-467">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-468">件</span><span class="sxs-lookup"><span data-stu-id="2b4e9-468">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-469">Discard の対象としてパッケージを選択できるかどうかを判断するには、このレジストリ値を、パッケージが最後にアクセスされてからの経過時間の最小日数と等しくなるように設定します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-469">To determine when the package can be selected for discard, set this registry value to equal the minimum number of days you want to elapse since the package was last accessed.</span></span> <span data-ttu-id="2b4e9-470">最近使用されたパッケージは破棄されません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-470">Packages that have been used more recently are not discarded.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="2b4e9-471">権限キー</span><span class="sxs-lookup"><span data-stu-id="2b4e9-471">Permissions Key</span></span>


<span data-ttu-id="2b4e9-472">ユーザーによるミスを防ぐために、管理者は、ユーザーが誤ってプログラムをアンロードしないようにするなど、管理者以外のユーザーのための一部の操作へのアクセスを制御するために、HKEY \ _LOCAL \ _MACHINE \ ソフトウェア \\ のアクセス許可キーを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-472">To help to prevent users from making mistakes, administrators can use the HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Permissions key to control access to some actions for non-administrative users—for example, to prevent users from accidentally unloading programs.</span></span> <span data-ttu-id="2b4e9-473">管理者権限を持つユーザーは、次のいずれかのアクセス許可を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-473">Users with administrative rights can give themselves any of these permissions.</span></span> <span data-ttu-id="2b4e9-474">リモートデスクトップセッションホスト (RD セッションホスト) サーバー (旧 Terminal Server) システムなどの共有システムでは、これらのアクセス許可の一部によって、ユーザーがシステム上のすべてのユーザーによって使用されるアプリケーションを制御することができるため、ユーザーにアクセス許可を付与する際に注意してください。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-474">On shared systems, such as a Remote Desktop Session Host (RD Session Host) server (formerly Terminal Server) system, be careful when granting additional permissions to users because some of these permissions would enable users to control the applications used by all users on the system.</span></span> <span data-ttu-id="2b4e9-475">これらの設定に使用できる値は 1 (許可) と 0 (許可しない) です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-475">Possible values for these settings are 1 (allow) and 0 (disallow).</span></span>

<span data-ttu-id="2b4e9-476">アクセス許可キーの設定では、名前付きのアクションを有効にするすべてのインターフェイスを制御します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-476">The Permissions key settings control all interfaces that enable the named actions.</span></span> <span data-ttu-id="2b4e9-477">これには、[オプション] ダイアログ、SFTTray、Sfttray が含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-477">This includes the Options Dialog, SFTTray, and SFTMime.</span></span> <span data-ttu-id="2b4e9-478">これらの設定は管理者には影響ありません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-478">These settings do not affect administrators.</span></span> <span data-ttu-id="2b4e9-479">次の表は、アクセス許可キーに関連付けられたレジストリ値に関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-479">The following table provides information about the registry values associated with the Permissions key.</span></span>

<span data-ttu-id="2b4e9-480">名前の種類データ (例) 説明 ChangeFSDrive</span><span class="sxs-lookup"><span data-stu-id="2b4e9-480">Name Type Data (Examples) Description ChangeFSDrive</span></span>

<span data-ttu-id="2b4e9-481">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-481">DWORD</span></span>

<span data-ttu-id="2b4e9-482">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-482">Default=0</span></span>

<span data-ttu-id="2b4e9-483">値1を指定すると、ユーザーはファイルシステムドライブとして使用する別のドライブ文字を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-483">A value of 1 allows users to pick a different drive letter to be used as the file system drive.</span></span>

<span data-ttu-id="2b4e9-484">ChangeCacheSize</span><span class="sxs-lookup"><span data-stu-id="2b4e9-484">ChangeCacheSize</span></span>

<span data-ttu-id="2b4e9-485">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-485">DWORD</span></span>

<span data-ttu-id="2b4e9-486">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-486">Default=0</span></span>

<span data-ttu-id="2b4e9-487">値1を指定すると、ユーザーはキャッシュサイズを変更できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-487">A value of 1 allows users to change the cache size.</span></span>

<span data-ttu-id="2b4e9-488">ChangeLogSettings</span><span class="sxs-lookup"><span data-stu-id="2b4e9-488">ChangeLogSettings</span></span>

<span data-ttu-id="2b4e9-489">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-489">DWORD</span></span>

<span data-ttu-id="2b4e9-490">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-490">Default=0</span></span>

<span data-ttu-id="2b4e9-491">値1を指定すると、ユーザーはログレベルを変更したり、位置を変更したり、ユーザーインターフェイスでリセットしたりできます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-491">A value of 1 allows users to modify the log level, change its location, and reset it through the user interface.</span></span>

<span data-ttu-id="2b4e9-492">AddApp</span><span class="sxs-lookup"><span data-stu-id="2b4e9-492">AddApp</span></span>

<span data-ttu-id="2b4e9-493">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-493">DWORD</span></span>

<span data-ttu-id="2b4e9-494">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-494">Default=0</span></span>

<span data-ttu-id="2b4e9-495">値1を指定すると、ユーザーはアプリケーションを明示的に追加できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-495">A value of 1 allows users to add applications explicitly.</span></span> <span data-ttu-id="2b4e9-496">これは、公開の更新によって追加されたアプリケーションには影響しません。また、まだ追加されていないアプリケーションは、ユーザーがアプリを起動することはできません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-496">This does not affect applications that are added through publishing refresh nor does it prevent users from starting (and thereby implicitly adding) applications that have not already been added.</span></span> <span data-ttu-id="2b4e9-497">値は0または1です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-497">Values are 0 or 1.</span></span>

<span data-ttu-id="2b4e9-498">LoadApp</span><span class="sxs-lookup"><span data-stu-id="2b4e9-498">LoadApp</span></span> 

<span data-ttu-id="2b4e9-499">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-499">DWORD</span></span> 

<span data-ttu-id="2b4e9-500">0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-500">0</span></span>

<span data-ttu-id="2b4e9-501">ユーザーがアプリケーションを読み込むことはできません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-501">Does not allow a user to load an application.</span></span> <span data-ttu-id="2b4e9-502">これは、RD セッションホストの既定値です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-502">This is the default for RD Session Hosts.</span></span> <span data-ttu-id="2b4e9-503">モバイルユーザーの場合は、接続されていない操作またはオフラインモードでアプリを使用するために、キャッシュにアプリケーションを完全に読み込むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-503">If you are a mobile user, you might want to fully load your applications in the cache to use them during disconnected operation or offline mode.</span></span> <span data-ttu-id="2b4e9-504">アプリケーションを App-v 管理サーバーまたは App-v ストリーミングサーバーからストリーミングするには、アプリケーションを読み込むためにサーバーに接続している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-504">To stream applications from the App-V Management Server or the App-V Streaming Server, you must be connected to a server to load applications.</span></span>

<span data-ttu-id="2b4e9-505">件</span><span class="sxs-lookup"><span data-stu-id="2b4e9-505">1</span></span>

<span data-ttu-id="2b4e9-506">ユーザーがアプリケーションを読み込むことを許可します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-506">Allows a user to load an application.</span></span> <span data-ttu-id="2b4e9-507">これは、Windows デスクトップの既定値です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-507">This is the default for Windows desktops.</span></span> 

<span data-ttu-id="2b4e9-508">UnloadApp</span><span class="sxs-lookup"><span data-stu-id="2b4e9-508">UnloadApp</span></span> 

<span data-ttu-id="2b4e9-509">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-509">DWORD</span></span> 

<span data-ttu-id="2b4e9-510">0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-510">0</span></span>

<span data-ttu-id="2b4e9-511">ユーザーがアプリケーションをアンロードすることを許可しません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-511">Does not allow a user to unload an application.</span></span> <span data-ttu-id="2b4e9-512">パッケージを読み込みまたはアンロードすると、パッケージ内のすべてのアプリケーションがキャッシュに読み込まれるか、またはキャッシュから削除されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-512">When you load or unload a package, all the applications in the package are loaded into or removed from cache.</span></span>

<span data-ttu-id="2b4e9-513">件</span><span class="sxs-lookup"><span data-stu-id="2b4e9-513">1</span></span>

<span data-ttu-id="2b4e9-514">ユーザーがアプリケーションをアンロードできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-514">Allows a user to unload an application.</span></span> 

<span data-ttu-id="2b4e9-515">LockApp</span><span class="sxs-lookup"><span data-stu-id="2b4e9-515">LockApp</span></span> 

<span data-ttu-id="2b4e9-516">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-516">DWORD</span></span> 

<span data-ttu-id="2b4e9-517">0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-517">0</span></span>

<span data-ttu-id="2b4e9-518">ユーザーは、アプリケーションのロックとロック解除を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-518">Does not allow a user to lock and unlock an application.</span></span> <span data-ttu-id="2b4e9-519">これは、RD セッションホストの既定値です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-519">This is the default for RD Session Hosts.</span></span> <span data-ttu-id="2b4e9-520">ロックされたアプリケーションをキャッシュから削除して、新しいアプリケーションのためのスペースを確保することはできません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-520">A locked application cannot be removed from the cache to make room for new applications.</span></span> <span data-ttu-id="2b4e9-521">ロックされているアプリケーションを、リモートデスクトップサービス (以前のターミナルサービス) キャッシュの App-v デスクトップまたはクライアントから削除するには、ロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-521">To remove a locked application from the App-V Desktop or Client for Remote Desktop Services (formerly Terminal Services) cache, you must unlock it.</span></span>

<span data-ttu-id="2b4e9-522">件</span><span class="sxs-lookup"><span data-stu-id="2b4e9-522">1</span></span>

<span data-ttu-id="2b4e9-523">ユーザーがアプリケーションのロックとロック解除を行うことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-523">Allows a user to lock and unlock an application.</span></span> <span data-ttu-id="2b4e9-524">これは、Windows デスクトップの既定値です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-524">This is the default for Windows Desktops.</span></span> 

<span data-ttu-id="2b4e9-525">ManageTypes</span><span class="sxs-lookup"><span data-stu-id="2b4e9-525">ManageTypes</span></span> 

<span data-ttu-id="2b4e9-526">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-526">DWORD</span></span> 

<span data-ttu-id="2b4e9-527">0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-527">0</span></span>

<span data-ttu-id="2b4e9-528">ユーザーは、そのユーザーに対してファイルの種類の関連付けを追加、編集、または削除することはできません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-528">Does not allow a user to add, edit, or remove file type associations for that User alone.</span></span> <span data-ttu-id="2b4e9-529">これは、RD セッションホストの既定値です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-529">This is the default for RD Session Hosts.</span></span> 

<span data-ttu-id="2b4e9-530">件</span><span class="sxs-lookup"><span data-stu-id="2b4e9-530">1</span></span>

<span data-ttu-id="2b4e9-531">ユーザーは、グローバルにではなく、そのユーザーに対してのみ、ファイルの種類の関連付けの追加、編集、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-531">Allows a user to add, edit, and remove file type associations for that user only and not globally.</span></span> <span data-ttu-id="2b4e9-532">これは、Windows デスクトップの既定値です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-532">This is the default for Windows Desktops.</span></span> 

<span data-ttu-id="2b4e9-533">RefreshServer</span><span class="sxs-lookup"><span data-stu-id="2b4e9-533">RefreshServer</span></span> 

<span data-ttu-id="2b4e9-534">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-534">DWORD</span></span> 

<span data-ttu-id="2b4e9-535">0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-535">0</span></span>

<span data-ttu-id="2b4e9-536">ユーザーが MIME 設定の更新をトリガーすることはできません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-536">Does not allow a user to trigger a refresh of MIME settings.</span></span> <span data-ttu-id="2b4e9-537">これは、RD セッションホストの既定値です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-537">This is the default for RD Session Hosts.</span></span> 

<span data-ttu-id="2b4e9-538">件</span><span class="sxs-lookup"><span data-stu-id="2b4e9-538">1</span></span>

<span data-ttu-id="2b4e9-539">ユーザーが MIME 設定の更新を開始できるようにします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-539">Enables a user to trigger a refresh of MIME settings.</span></span> <span data-ttu-id="2b4e9-540">これは、Windows デスクトップの既定値です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-540">This is the default for Windows Desktops.</span></span> 

<span data-ttu-id="2b4e9-541">UpdateOSDFile</span><span class="sxs-lookup"><span data-stu-id="2b4e9-541">UpdateOSDFile</span></span>

<span data-ttu-id="2b4e9-542">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-542">DWORD</span></span>

<span data-ttu-id="2b4e9-543">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-543">Default= 0</span></span>

<span data-ttu-id="2b4e9-544">値1を指定すると、ユーザーは修正された OSD ファイルを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-544">A value of 1 enables a user to use a modified OSD file.</span></span>

<span data-ttu-id="2b4e9-545">ImportApp</span><span class="sxs-lookup"><span data-stu-id="2b4e9-545">ImportApp</span></span> 

<span data-ttu-id="2b4e9-546">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-546">DWORD</span></span> 

<span data-ttu-id="2b4e9-547">0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-547">0</span></span>

<span data-ttu-id="2b4e9-548">ユーザーがアプリケーションをキャッシュにインポートすることを許可しません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-548">Does not allow a user to import applications into cache.</span></span> <span data-ttu-id="2b4e9-549">読み込みとインポートの違いは、読み込みがトリガーされると、クライアントは、OSD、ASR、または Override URL に含まれる現在構成されている場所からパッケージを取得することです。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-549">The difference between Load and Import is that when a Load is triggered, the client gets the package from the currently configured location contained in the OSD, ASR, or Override URL.</span></span> <span data-ttu-id="2b4e9-550">インポートを使用する場合は、パッケージを取得する場所を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-550">When using Import, a location to get the package from must be specified.</span></span> 

<span data-ttu-id="2b4e9-551">件</span><span class="sxs-lookup"><span data-stu-id="2b4e9-551">1</span></span>

<span data-ttu-id="2b4e9-552">ユーザーがアプリケーションをキャッシュにインポートできるようにします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-552">Allows a user to import applications into cache.</span></span> 

<span data-ttu-id="2b4e9-553">ChangeRefreshSettings</span><span class="sxs-lookup"><span data-stu-id="2b4e9-553">ChangeRefreshSettings</span></span>

<span data-ttu-id="2b4e9-554">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-554">DWORD</span></span>

<span data-ttu-id="2b4e9-555">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-555">Default=0</span></span>

<span data-ttu-id="2b4e9-556">値1を指定すると、ユーザーはサーバーの更新設定を変更できます (ログイン時と定期的な更新時に更新)。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-556">A value of 1 allows users to modify the refresh settings for servers (refresh on login and periodic refresh).</span></span> <span data-ttu-id="2b4e9-557">これは、ユーザーが他のサーバー設定 (path、host など) を変更できるというわけではありません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-557">This does not imply that the user can modify other server settings (path, host, and so on).</span></span>

<span data-ttu-id="2b4e9-558">ManageServers</span><span class="sxs-lookup"><span data-stu-id="2b4e9-558">ManageServers</span></span>

<span data-ttu-id="2b4e9-559">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-559">DWORD</span></span>

<span data-ttu-id="2b4e9-560">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-560">Default=0</span></span>

<span data-ttu-id="2b4e9-561">値1を指定すると、ユーザーは、ChangeRefreshSettings アクセス許可によって制御される更新設定を編集することを除き、サーバーの追加、編集、削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-561">A value of 1 allows the user to add, edit, and remove servers, except for editing the refresh settings, which is controlled by the ChangeRefreshSettings permission.</span></span>

<span data-ttu-id="2b4e9-562">PublishShortcut</span><span class="sxs-lookup"><span data-stu-id="2b4e9-562">PublishShortcut</span></span>

<span data-ttu-id="2b4e9-563">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-563">DWORD</span></span>

<span data-ttu-id="2b4e9-564">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-564">Default=0</span></span>

<span data-ttu-id="2b4e9-565">値1を指定すると、ユーザーはユーザーインターフェイスを使ってショートカットを発行できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-565">A value of 1 allows users to publish shortcuts through the user interface.</span></span> <span data-ttu-id="2b4e9-566">これは、公開の更新中に公開されるショートカットには影響しません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-566">This does not affect shortcuts that are published during a publishing refresh.</span></span>

<span data-ttu-id="2b4e9-567">ViewAllApplications</span><span class="sxs-lookup"><span data-stu-id="2b4e9-567">ViewAllApplications</span></span>

<span data-ttu-id="2b4e9-568">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-568">DWORD</span></span>

<span data-ttu-id="2b4e9-569">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-569">Default=0</span></span>

<span data-ttu-id="2b4e9-570">値1を指定すると、すべてのアプリケーションがユーザーインターフェイスを通じて表示されます。そうしないと、ユーザーのアプリケーションのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-570">A value of 1 displays all applications through the user interface; otherwise, only the user’s applications are displayed.</span></span>

<span data-ttu-id="2b4e9-571">RepairApp</span><span class="sxs-lookup"><span data-stu-id="2b4e9-571">RepairApp</span></span>

<span data-ttu-id="2b4e9-572">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-572">DWORD</span></span>

<span data-ttu-id="2b4e9-573">Default = 1</span><span class="sxs-lookup"><span data-stu-id="2b4e9-573">Default=1</span></span>

<span data-ttu-id="2b4e9-574">値1を指定すると、ユーザーは SFTMime またはクライアント管理コンソールのアプリケーションで修復操作を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-574">A value of 1 allows the user to use the Repair action on applications in SFTMime or the Client Management Console.</span></span> <span data-ttu-id="2b4e9-575">アプリケーションを修復する場合は、カスタムユーザー設定を削除して、既定の設定に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-575">When you repair an application, you remove any custom user settings and restore the default settings.</span></span> <span data-ttu-id="2b4e9-576">この操作では、ショートカットやファイルの種類の関連付けは変更または削除されず、キャッシュからアプリケーションが削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-576">This action does not change or delete shortcuts or file type associations, and it does not remove the application from cache.</span></span>

<span data-ttu-id="2b4e9-577">アプリのクリア</span><span class="sxs-lookup"><span data-stu-id="2b4e9-577">ClearApp</span></span>

<span data-ttu-id="2b4e9-578">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-578">DWORD</span></span>

<span data-ttu-id="2b4e9-579">Default = 1</span><span class="sxs-lookup"><span data-stu-id="2b4e9-579">Default=1</span></span>

<span data-ttu-id="2b4e9-580">値1を指定すると、ユーザーは SFTMime またはクライアント管理コンソールのアプリケーションに対してクリアアクションを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-580">A value of 1 allows the user to use the Clear action on applications in SFTMime or the Client Management Console.</span></span> <span data-ttu-id="2b4e9-581">コンソールからアプリケーションをクリアすると、そのアプリケーションは使えなくなります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-581">When you clear an application from the console, you can no longer use that application.</span></span> <span data-ttu-id="2b4e9-582">ただし、アプリケーションはキャッシュ内に保持され、同じシステム上の他のユーザーは引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-582">However, the application remains in cache and is still available to other users on the same system.</span></span> <span data-ttu-id="2b4e9-583">公開したアプリが更新されると、消去されたアプリケーションが再び利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-583">After a publishing refresh, the cleared applications will again become available to you.</span></span>

<span data-ttu-id="2b4e9-584">DeleteApp</span><span class="sxs-lookup"><span data-stu-id="2b4e9-584">DeleteApp</span></span>

<span data-ttu-id="2b4e9-585">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-585">DWORD</span></span>

<span data-ttu-id="2b4e9-586">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-586">Default=0</span></span>

<span data-ttu-id="2b4e9-587">値1を指定すると、ユーザーは SFTMime またはクライアント管理コンソールのアプリケーションに対して削除アクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-587">A value of 1 allows the user to use the Delete action on applications in SFTMime or the Client Management Console.</span></span> <span data-ttu-id="2b4e9-588">アプリケーションを削除すると、そのクライアントのユーザーは選択したアプリケーションを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-588">When you delete an application, the selected application will no longer be available to any users on that client.</span></span> <span data-ttu-id="2b4e9-589">ショートカットとファイルの種類の関連付けが削除され、アプリケーションがキャッシュから削除されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-589">Shortcuts and file type associations are deleted and the application is deleted from cache.</span></span> <span data-ttu-id="2b4e9-590">ただし、他のアプリケーションが、選択したアプリケーションのファイルシステムキャッシュまたは設定データを参照している場合は、これらの項目は削除されません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-590">However, if another application refers to data in the file system cache or settings data for the selected application, these items will not be deleted.</span></span>

<span data-ttu-id="2b4e9-591">公開した後は、削除されたアプリケーションを再び利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-591">After a publishing refresh, the deleted applications will again become available to you.</span></span>

<span data-ttu-id="2b4e9-592">ToggleOfflineMode</span><span class="sxs-lookup"><span data-stu-id="2b4e9-592">ToggleOfflineMode</span></span>

<span data-ttu-id="2b4e9-593">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-593">DWORD</span></span>

<span data-ttu-id="2b4e9-594">値1を指定すると、ユーザーはオフラインモードでクライアントを実行することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-594">A value of 1 allows the users to select to run the client in Offline Mode.</span></span> <span data-ttu-id="2b4e9-595">オフラインモードでは、application virtualization クライアントは、Application Virtualization Server に接続していない場合でも、読み込まれたアプリケーションを開始できます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-595">In Offline Mode, the Application Virtualization client can start a loaded application even when it is not connected to an Application Virtualization Server.</span></span>



## <span data-ttu-id="2b4e9-596">カスタム設定</span><span class="sxs-lookup"><span data-stu-id="2b4e9-596">Custom Settings</span></span>


<span data-ttu-id="2b4e9-597">HKEY \ _LOCAL \ _MACHINE ¥ $ ¥¥ \ Softgrid\\ 4.8 5 \ client¥ customsettings キーには、フロントエンドコンポーネントに固有の値が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-597">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\CustomSettings key contains values specific to front-end components.</span></span> <span data-ttu-id="2b4e9-598">すべてのカスタム設定は文字列として保存されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-598">All custom settings are stored as strings.</span></span> <span data-ttu-id="2b4e9-599">次の表は、CustomSettings キーに関連付けられたレジストリ値に関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-599">The following table provides information about the registry values associated with the CustomSettings key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2b4e9-600">名前</span><span class="sxs-lookup"><span data-stu-id="2b4e9-600">Name</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-601">型</span><span class="sxs-lookup"><span data-stu-id="2b4e9-601">Type</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-602">データ (例)</span><span class="sxs-lookup"><span data-stu-id="2b4e9-602">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-603">説明</span><span class="sxs-lookup"><span data-stu-id="2b4e9-603">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-604">TrayErrorDelay</span><span class="sxs-lookup"><span data-stu-id="2b4e9-604">TrayErrorDelay</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-605">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-605">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-606">既定値 = 30</span><span class="sxs-lookup"><span data-stu-id="2b4e9-606">Default=30</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-607">アプリケーションの仮想化通知領域に起動失敗などのエラーメッセージが表示されるまでの時間 (秒) &quot; &quot; 。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-607">Time in seconds that the Application Virtualization notification area will display error messages like &quot;Launch failed&quot;.</span></span> <span data-ttu-id="2b4e9-608">最小値は1です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-608">Minimum value of 1.</span></span> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-609">TraySuccessDelay</span><span class="sxs-lookup"><span data-stu-id="2b4e9-609">TraySuccessDelay</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-610">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-610">DWORD</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-611">既定値 = 10</span><span class="sxs-lookup"><span data-stu-id="2b4e9-611">Default=10</span></span> </p></td>
<td align="left"><p><span data-ttu-id="2b4e9-612">Appvmed 通知領域に、Word が起動された、 &quot; &quot; または Excel が &quot; シャットダウンしたときなどの成功メッセージが表示されるまでの時間 (秒) &quot; 。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-612">Time in seconds that the appvmed notification area will display success messages like &quot;Word launched&quot; or &quot;Excel shut down&quot;.</span></span> <span data-ttu-id="2b4e9-613">0の場合、これらのメッセージは抑制されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-613">If 0, those messages will be suppressed.</span></span> </p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-614">TrayVisibility</span><span class="sxs-lookup"><span data-stu-id="2b4e9-614">TrayVisibility</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-615">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-615">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-616">既定値 = 0</span><span class="sxs-lookup"><span data-stu-id="2b4e9-616">Default=0</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-617">0 = 仮想化されたアプリケーションを使用している場合は、[トレイを表示] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-617">0=Show Tray when virtualized applications are in use.</span></span></p>
<p><span data-ttu-id="2b4e9-618">1 = トレイを常に表示します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-618">1=Show Tray always.</span></span></p>
<p><span data-ttu-id="2b4e9-619">2 = トレイを表示しません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-619">2=Never show Tray.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-620">TrayShowRefresh</span><span class="sxs-lookup"><span data-stu-id="2b4e9-620">TrayShowRefresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-621">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-621">DWORD</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-622">値1に設定すると、メニュー項目更新アプリケーションがトレイメニューに表示され、ユーザーがアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-622">When present and set to a value of 1, allows menu item Refresh Applications to be displayed on the Tray menu and is accessible by the user.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-623">TrayShowLoad</span><span class="sxs-lookup"><span data-stu-id="2b4e9-623">TrayShowLoad</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-624">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-624">DWORD</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-625">値1に設定すると、メニュー項目の読み込みアプリケーションがトレイメニューに表示され、ユーザーがアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-625">When present and set to a value of 1, allows menu item Load Applications to be displayed on the Tray menu and is accessible by the user.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="2b4e9-626">レポートの設定</span><span class="sxs-lookup"><span data-stu-id="2b4e9-626">Reporting Settings</span></span>


<span data-ttu-id="2b4e9-627">HKEY \ _LOCAL \ _MACHINE ¥¥¥¥ \ xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx ()</span><span class="sxs-lookup"><span data-stu-id="2b4e9-627">The HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Reporting key contains values specific to reporting to an App-V Management Server.</span></span> <span data-ttu-id="2b4e9-628">次の表は、レポートキーに関連付けられているレジストリ値に関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-628">The following table provides information about the registry values associated with the Reporting key.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2b4e9-629">名前</span><span class="sxs-lookup"><span data-stu-id="2b4e9-629">Name</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-630">型</span><span class="sxs-lookup"><span data-stu-id="2b4e9-630">Type</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-631">データ (例)</span><span class="sxs-lookup"><span data-stu-id="2b4e9-631">Data (Examples)</span></span> </th>
<th align="left"><span data-ttu-id="2b4e9-632">説明</span><span class="sxs-lookup"><span data-stu-id="2b4e9-632">Description</span></span> </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b4e9-633">DataCacheLimit</span><span class="sxs-lookup"><span data-stu-id="2b4e9-633">DataCacheLimit</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-634">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-634">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-635">既定値 = 20</span><span class="sxs-lookup"><span data-stu-id="2b4e9-635">Default=20</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-636">この値は、レポート情報を格納する XML キャッシュの最大サイズ (MB) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-636">This value specifies the maximum size in megabytes (MB) of the XML cache for storing reporting information.</span></span> <span data-ttu-id="2b4e9-637">サイズは、メモリ内のキャッシュに適用されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-637">The size applies to the cache in memory.</span></span> <span data-ttu-id="2b4e9-638">上限に達すると、ログファイルがロールオーバーされます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-638">When the limit is reached, the log file will roll over.</span></span> <span data-ttu-id="2b4e9-639">新しいレコードが追加されると (リストの一番下にある)、空き領域を増やすために、1つ以上の最も古いレコード (リストの先頭) が削除されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-639">When a new record is added (bottom of the list), one or more of the oldest records (top of the list) will be deleted to make room.</span></span> <span data-ttu-id="2b4e9-640">このイベントが発生すると、最初に警告が表示されます。これは、送信時にキャッシュが正常に消去され、ログが再びいっぱいになるまで、ログに記録されません。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-640">A warning will be logged to the Client log and the event log the first time this occurs, and it will not be logged again until after the cache has been successfully cleared on transmission and the log has filled up again.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b4e9-641">"の場合</span><span class="sxs-lookup"><span data-stu-id="2b4e9-641">DataBlockSize</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-642">DWORD</span><span class="sxs-lookup"><span data-stu-id="2b4e9-642">DWORD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-643">Default = 65536</span><span class="sxs-lookup"><span data-stu-id="2b4e9-643">Default=65536</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b4e9-644">この値は、更新の公開時にサーバーに一度に送信する最大サイズをバイト単位で指定します。ログのサイズが大きくなったときに、永続的な転送エラーが発生しないようにします。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-644">This value specifies the maximum size in bytes to transmit to the server at once on publishing refresh, to avoid permanent transmission failures when the log has reached a significant size.</span></span> <span data-ttu-id="2b4e9-645">既定値は65536です。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-645">The default value is 65536.</span></span> <span data-ttu-id="2b4e9-646">レポートデータをサーバーに送信する場合、1つのアプリケーションレコードのブロック (XML データのバイト単位のブロックサイズ以下) は、キャッシュから削除され、サーバーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-646">When transmitting report data to the server, one block of application records—less than or equal to the block size in bytes of XML data—will be removed from the cache and sent to the server.</span></span> <span data-ttu-id="2b4e9-647">各ブロックには、一般的なクライアントデータとグローバルパッケージリストデータが付加されます。これらは、ブロックサイズの計算には関係ありません。非常に大きいパッケージリストの場合は、低帯域幅または信頼性の低い接続での伝送エラーの原因となる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b4e9-647">Each block will have the general Client data and global package list data prepended, and these will not factor into the block size calculations; the potential exists for an extremely large package list to result in transmission failures over low bandwidth or unreliable connections.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="2b4e9-648">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2b4e9-648">Related topics</span></span>


[<span data-ttu-id="2b4e9-649">Application Virtualization Client リファレンス</span><span class="sxs-lookup"><span data-stu-id="2b4e9-649">Application Virtualization Client Reference</span></span>](application-virtualization-client-reference.md)









