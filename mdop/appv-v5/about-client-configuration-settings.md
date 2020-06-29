---
title: Client の構成設定について
description: Client の構成設定について
author: dansimp
ms.assetid: cc7ae28c-b2ac-4f68-b992-5ccdbd5316a4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 289f5b35ac223d488152ff7ee1f42b1cf50341df
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814939"
---
# <span data-ttu-id="b073a-103">Client の構成設定について</span><span class="sxs-lookup"><span data-stu-id="b073a-103">About Client Configuration Settings</span></span>


<span data-ttu-id="b073a-104">Microsoft Application Virtualization (App-v) 5.0 クライアントでは、その構成がレジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b073a-104">The Microsoft Application Virtualization (App-V) 5.0 client stores its configuration in the registry.</span></span> <span data-ttu-id="b073a-105">レジストリ内のデータの形式を理解している場合は、クライアントに関する有用な情報を収集することができます。</span><span class="sxs-lookup"><span data-stu-id="b073a-105">You can gather some useful information about the client if you understand the format of data in the registry.</span></span> <span data-ttu-id="b073a-106">また、レジストリエントリを変更して、多くのクライアント操作を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="b073a-106">You can also configure many client actions by changing registry entries.</span></span> <span data-ttu-id="b073a-107">このトピックでは、App-v 5.0 クライアント構成の設定を示し、その使い方について説明します。</span><span class="sxs-lookup"><span data-stu-id="b073a-107">This topic lists the App-V 5.0 Client configuration settings and explains their uses.</span></span> <span data-ttu-id="b073a-108">PowerShell を使用して、クライアント構成の設定を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b073a-108">You can use PowerShell to modify the client configuration settings.</span></span> <span data-ttu-id="b073a-109">PowerShell と App-v 5.0 の使用方法について詳しくは、「 [Powershell を使用](administering-app-v-by-using-powershell.md)した App-v の管理」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b073a-109">For more information about using PowerShell and App-V 5.0 see [Administering App-V by Using PowerShell](administering-app-v-by-using-powershell.md).</span></span>

## <a href="" id="---------app-v-5-0-client-configuration-settings"></a> <span data-ttu-id="b073a-110">App-v 5.0 クライアント構成の設定</span><span class="sxs-lookup"><span data-stu-id="b073a-110">App-V 5.0 Client Configuration Settings</span></span>


<span data-ttu-id="b073a-111">次の表は、App-v 5.0 クライアントの構成設定に関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="b073a-111">The following table displays information about the App-V 5.0 client configuration settings:</span></span>

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
<th align="left"><span data-ttu-id="b073a-112">設定名</span><span class="sxs-lookup"><span data-stu-id="b073a-112">Setting Name</span></span></th>
<th align="left"><span data-ttu-id="b073a-113">設定フラグ</span><span class="sxs-lookup"><span data-stu-id="b073a-113">Setup Flag</span></span></th>
<th align="left"><span data-ttu-id="b073a-114">説明</span><span class="sxs-lookup"><span data-stu-id="b073a-114">Description</span></span></th>
<th align="left"><span data-ttu-id="b073a-115">オプションを設定する</span><span class="sxs-lookup"><span data-stu-id="b073a-115">Setting Options</span></span></th>
<th align="left"><span data-ttu-id="b073a-116">レジストリキー値</span><span class="sxs-lookup"><span data-stu-id="b073a-116">Registry Key Value</span></span></th>
<th align="left"><span data-ttu-id="b073a-117">ポリシーの状態のキーと値が無効になっている</span><span class="sxs-lookup"><span data-stu-id="b073a-117">Disabled Policy State Keys and Values</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-118">PackageInstallationRoot</span><span class="sxs-lookup"><span data-stu-id="b073a-118">PackageInstallationRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-119">PACKAGEINSTALLATIONROOT</span><span class="sxs-lookup"><span data-stu-id="b073a-119">PACKAGEINSTALLATIONROOT</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-120">すべての新しいアプリケーションと更新プログラムをインストールするディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-120">Specifies directory where all new applications and updates will be installed.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-121">String</span><span class="sxs-lookup"><span data-stu-id="b073a-121">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-122">Streaming\PackageInstallationRoot</span><span class="sxs-lookup"><span data-stu-id="b073a-122">Streaming\PackageInstallationRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-123">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-123">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-124">パッケージパッケージ</span><span class="sxs-lookup"><span data-stu-id="b073a-124">PackageSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-125">パッケージパッケージ</span><span class="sxs-lookup"><span data-stu-id="b073a-125">PACKAGESOURCEROOT</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-126">パッケージコンテンツをダウンロードするためのソースの場所をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="b073a-126">Overrides source location for downloading package content.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-127">String</span><span class="sxs-lookup"><span data-stu-id="b073a-127">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-128">Streaming\PackageSourceRoot</span><span class="sxs-lookup"><span data-stu-id="b073a-128">Streaming\PackageSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-129">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-129">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-130">AllowHighCostLaunch</span><span class="sxs-lookup"><span data-stu-id="b073a-130">AllowHighCostLaunch</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-131">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-131">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-132">この設定は、従量制課金接続を介して接続された Windows 8 コンピューターで、仮想化されたアプリケーションを起動するかどうかを制御します (4G など)。</span><span class="sxs-lookup"><span data-stu-id="b073a-132">This setting controls whether virtualized applications are launched on Windows 8 machines connected via a metered network connection (For example, 4G).</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-133">True (有効)、False (無効状態)</span><span class="sxs-lookup"><span data-stu-id="b073a-133">True (enabled); False (Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-134">Streaming\AllowHighCostLaunch</span><span class="sxs-lookup"><span data-stu-id="b073a-134">Streaming\AllowHighCostLaunch</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-135">0</span><span class="sxs-lookup"><span data-stu-id="b073a-135">0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-136">ReestablishmentRetries</span><span class="sxs-lookup"><span data-stu-id="b073a-136">ReestablishmentRetries</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-137">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-137">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-138">ドロップしたセッションを再試行する回数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-138">Specifies the number of times to retry a dropped session.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-139">Integer (0-99)</span><span class="sxs-lookup"><span data-stu-id="b073a-139">Integer (0-99)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-140">Streaming\ReestablishmentRetries</span><span class="sxs-lookup"><span data-stu-id="b073a-140">Streaming\ReestablishmentRetries</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-141">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-141">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-142">ReestablishmentInterval</span><span class="sxs-lookup"><span data-stu-id="b073a-142">ReestablishmentInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-143">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-143">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-144">ドロップされたセッションを再確立するまでの試行の秒数を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-144">Specifies the number of seconds between attempts to reestablish a dropped session.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-145">Integer (0-3600)</span><span class="sxs-lookup"><span data-stu-id="b073a-145">Integer (0-3600)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-146">Streaming\ReestablishmentInterval</span><span class="sxs-lookup"><span data-stu-id="b073a-146">Streaming\ReestablishmentInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-147">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-147">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-148">ロード</span><span class="sxs-lookup"><span data-stu-id="b073a-148">AutoLoad</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-149">ロード</span><span class="sxs-lookup"><span data-stu-id="b073a-149">AUTOLOAD</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-150">特定のコンピューター上の App-v によって、新しいパッケージを自動的に読み込む方法を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-150">Specifies how new packages should be loaded automatically by App-V on a specific computer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-151">(0x0) なし;(0x1) 以前に使用されました。(0x2) すべて</span><span class="sxs-lookup"><span data-stu-id="b073a-151">(0x0) None; (0x1) Previously used; (0x2) All</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-152">Streaming\AutoLoad</span><span class="sxs-lookup"><span data-stu-id="b073a-152">Streaming\AutoLoad</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-153">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-153">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-154">LocationProvider</span><span class="sxs-lookup"><span data-stu-id="b073a-154">LocationProvider</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-155">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-155">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-156">IAppvPackageLocationProvider インターフェイスの互換性のある実装の CLSID を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-156">Specifies the CLSID for a compatible implementation of the IAppvPackageLocationProvider interface.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-157">String</span><span class="sxs-lookup"><span data-stu-id="b073a-157">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-158">Streaming\LocationProvider</span><span class="sxs-lookup"><span data-stu-id="b073a-158">Streaming\LocationProvider</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-159">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-159">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-160">CertFilterForClientSsl</span><span class="sxs-lookup"><span data-stu-id="b073a-160">CertFilterForClientSsl</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-161">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-161">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-162">証明書ストア内の有効な証明書へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-162">Specifies the path to a valid certificate in the certificate store.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-163">String</span><span class="sxs-lookup"><span data-stu-id="b073a-163">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-164">Streaming\CertFilterForClientSsl</span><span class="sxs-lookup"><span data-stu-id="b073a-164">Streaming\CertFilterForClientSsl</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-165">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-165">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-166">VerifyCertificateRevocationList</span><span class="sxs-lookup"><span data-stu-id="b073a-166">VerifyCertificateRevocationList</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-167">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-167">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-168">HTTPS を使用して steaming する前にサーバー証明書の取り消し状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="b073a-168">Verifies Server certificate revocation status before steaming using HTTPS.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-169">True (有効)、False (無効状態)</span><span class="sxs-lookup"><span data-stu-id="b073a-169">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-170">Streaming\VerifyCertificateRevocationList</span><span class="sxs-lookup"><span data-stu-id="b073a-170">Streaming\VerifyCertificateRevocationList</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-171">0</span><span class="sxs-lookup"><span data-stu-id="b073a-171">0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-172">SharedContentStoreMode</span><span class="sxs-lookup"><span data-stu-id="b073a-172">SharedContentStoreMode</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-173">SHAREDCONTENTSTOREMODE</span><span class="sxs-lookup"><span data-stu-id="b073a-173">SHAREDCONTENTSTOREMODE</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-174">ストリーミングされたパッケージコンテンツをローカルのハードディスクに保存しないように指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-174">Specifies that streamed package contents will be not be saved to the local hard disk.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-175">True (有効)、False (無効状態)</span><span class="sxs-lookup"><span data-stu-id="b073a-175">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-176">Streaming\SharedContentStoreMode</span><span class="sxs-lookup"><span data-stu-id="b073a-176">Streaming\SharedContentStoreMode</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-177">0</span><span class="sxs-lookup"><span data-stu-id="b073a-177">0</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-178">名前</span><span class="sxs-lookup"><span data-stu-id="b073a-178">Name</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b073a-179">注</span><span class="sxs-lookup"><span data-stu-id="b073a-179">Note</span></span></strong><br/><p><span data-ttu-id="b073a-180">この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b073a-180">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="b073a-181">AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="b073a-181">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="b073a-182">発行サーバー名</span><span class="sxs-lookup"><span data-stu-id="b073a-182">PUBLISHINGSERVERNAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-183">発行サーバーの名前が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b073a-183">Displays the name of publishing server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-184">String</span><span class="sxs-lookup"><span data-stu-id="b073a-184">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-185">Publishing\Servers {serverId} \ FriendlyName</span><span class="sxs-lookup"><span data-stu-id="b073a-185">Publishing\Servers{serverId}\FriendlyName</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-186">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-186">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-187">URL</span><span class="sxs-lookup"><span data-stu-id="b073a-187">URL</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b073a-188">注</span><span class="sxs-lookup"><span data-stu-id="b073a-188">Note</span></span></strong><br/><p><span data-ttu-id="b073a-189">この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b073a-189">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="b073a-190">AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="b073a-190">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="b073a-191">発行する SERVERURL</span><span class="sxs-lookup"><span data-stu-id="b073a-191">PUBLISHINGSERVERURL</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-192">発行サーバーの URL を表示します。</span><span class="sxs-lookup"><span data-stu-id="b073a-192">Displays the URL of publishing server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-193">String</span><span class="sxs-lookup"><span data-stu-id="b073a-193">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-194">Publishing\Servers {serverId} \ URL</span><span class="sxs-lookup"><span data-stu-id="b073a-194">Publishing\Servers{serverId}\URL</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-195">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-195">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-196">GlobalRefreshEnabled</span><span class="sxs-lookup"><span data-stu-id="b073a-196">GlobalRefreshEnabled</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b073a-197">注</span><span class="sxs-lookup"><span data-stu-id="b073a-197">Note</span></span></strong><br/><p><span data-ttu-id="b073a-198">この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b073a-198">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="b073a-199">AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="b073a-199">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="b073a-200">GLOBALREFRESHENABLED</span><span class="sxs-lookup"><span data-stu-id="b073a-200">GLOBALREFRESHENABLED</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-201">グローバル発行の更新 (ブール値) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b073a-201">Enables global publishing refresh (Boolean)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-202">True (有効)、False (無効状態)</span><span class="sxs-lookup"><span data-stu-id="b073a-202">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-203">Publishing\Servers {serverId} \ GlobalEnabled</span><span class="sxs-lookup"><span data-stu-id="b073a-203">Publishing\Servers{serverId}\GlobalEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-204">False</span><span class="sxs-lookup"><span data-stu-id="b073a-204">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-205">GlobalRefreshOnLogon</span><span class="sxs-lookup"><span data-stu-id="b073a-205">GlobalRefreshOnLogon</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b073a-206">注</span><span class="sxs-lookup"><span data-stu-id="b073a-206">Note</span></span></strong><br/><p><span data-ttu-id="b073a-207">この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b073a-207">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="b073a-208">AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="b073a-208">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="b073a-209">GLOBALREFRESHONLOGON</span><span class="sxs-lookup"><span data-stu-id="b073a-209">GLOBALREFRESHONLOGON</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-210">ログオン時にグローバル公開の更新をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="b073a-210">Triggers a global publishing refresh on logon.</span></span> <span data-ttu-id="b073a-211">ブール</span><span class="sxs-lookup"><span data-stu-id="b073a-211">( Boolean)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-212">True (有効)、False (無効状態)</span><span class="sxs-lookup"><span data-stu-id="b073a-212">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-213">Publishing\Servers {serverId} \ GlobalLogonRefresh</span><span class="sxs-lookup"><span data-stu-id="b073a-213">Publishing\Servers{serverId}\GlobalLogonRefresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-214">False</span><span class="sxs-lookup"><span data-stu-id="b073a-214">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-215">GlobalRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="b073a-215">GlobalRefreshInterval</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b073a-216">注</span><span class="sxs-lookup"><span data-stu-id="b073a-216">Note</span></span></strong><br/><p><span data-ttu-id="b073a-217">この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b073a-217">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="b073a-218">AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="b073a-218">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="b073a-219">GLOBALREFRESHINTERVAL</span><span class="sxs-lookup"><span data-stu-id="b073a-219">GLOBALREFRESHINTERVAL</span></span>  </p></td>
<td align="left"><p><span data-ttu-id="b073a-220">GlobalRefreshIntervalUnit を使った公開の更新間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-220">Specifies the publishing refresh interval using the GlobalRefreshIntervalUnit.</span></span> <span data-ttu-id="b073a-221">パッケージの更新を無効にするには、[0] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b073a-221">To disable package refresh, select 0.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-222">Integer (0-744</span><span class="sxs-lookup"><span data-stu-id="b073a-222">Integer (0-744</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-223">Publishing\Servers{serverId}\GlobalPeriodicRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="b073a-223">Publishing\Servers{serverId}\GlobalPeriodicRefreshInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-224">0</span><span class="sxs-lookup"><span data-stu-id="b073a-224">0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-225">GlobalRefreshIntervalUnit</span><span class="sxs-lookup"><span data-stu-id="b073a-225">GlobalRefreshIntervalUnit</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b073a-226">注</span><span class="sxs-lookup"><span data-stu-id="b073a-226">Note</span></span></strong><br/><p><span data-ttu-id="b073a-227">この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b073a-227">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="b073a-228">AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="b073a-228">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="b073a-229">GLOBALREFRESHINTERVALUNI</span><span class="sxs-lookup"><span data-stu-id="b073a-229">GLOBALREFRESHINTERVALUNI</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-230">間隔の単位 (Hour 0-23, Day 0-31) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-230">Specifies the interval unit (Hour 0-23, Day 0-31).</span></span> </p></td>
<td align="left"><p><span data-ttu-id="b073a-231">0 (hour)、1日の場合</span><span class="sxs-lookup"><span data-stu-id="b073a-231">0 for hour, 1 for day</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-232">Publishing\Servers {serverId} \ GlobalPeriodicRefreshIntervalUnit</span><span class="sxs-lookup"><span data-stu-id="b073a-232">Publishing\Servers{serverId}\GlobalPeriodicRefreshIntervalUnit</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-233">件</span><span class="sxs-lookup"><span data-stu-id="b073a-233">1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-234">UserRefreshEnabled</span><span class="sxs-lookup"><span data-stu-id="b073a-234">UserRefreshEnabled</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b073a-235">注</span><span class="sxs-lookup"><span data-stu-id="b073a-235">Note</span></span></strong><br/><p><span data-ttu-id="b073a-236">この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b073a-236">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="b073a-237">AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="b073a-237">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="b073a-238">USERREFRESHENABLED</span><span class="sxs-lookup"><span data-stu-id="b073a-238">USERREFRESHENABLED</span></span> </p></td>
<td align="left"><p><span data-ttu-id="b073a-239">ユーザー発行の更新 (ブール値) を有効にします。</span><span class="sxs-lookup"><span data-stu-id="b073a-239">Enables user publishing refresh (Boolean)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-240">True (有効)、False (無効状態)</span><span class="sxs-lookup"><span data-stu-id="b073a-240">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-241">Publishing\Servers {serverId} \ UserEnabled</span><span class="sxs-lookup"><span data-stu-id="b073a-241">Publishing\Servers{serverId}\UserEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-242">False</span><span class="sxs-lookup"><span data-stu-id="b073a-242">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-243">UserRefreshOnLogon 使い方</span><span class="sxs-lookup"><span data-stu-id="b073a-243">UserRefreshOnLogon</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b073a-244">注</span><span class="sxs-lookup"><span data-stu-id="b073a-244">Note</span></span></strong><br/><p><span data-ttu-id="b073a-245">この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b073a-245">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="b073a-246">AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="b073a-246">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="b073a-247">USERREFRESHONLOGON 使い方</span><span class="sxs-lookup"><span data-stu-id="b073a-247">USERREFRESHONLOGON</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-248">ユーザー公開の更新方法をトリガーします。</span><span class="sxs-lookup"><span data-stu-id="b073a-248">Triggers a user publishing refresh onlogon.</span></span> <span data-ttu-id="b073a-249">ブール</span><span class="sxs-lookup"><span data-stu-id="b073a-249">( Boolean)</span></span></p>
<p><span data-ttu-id="b073a-250">文字数 (スペースを含む):60</span><span class="sxs-lookup"><span data-stu-id="b073a-250">Word count (with spaces): 60</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-251">True (有効)、False (無効状態)</span><span class="sxs-lookup"><span data-stu-id="b073a-251">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-252">Publishing\Servers {serverId} \ UserLogonRefresh</span><span class="sxs-lookup"><span data-stu-id="b073a-252">Publishing\Servers{serverId}\UserLogonRefresh</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-253">False</span><span class="sxs-lookup"><span data-stu-id="b073a-253">False</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-254">UserRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="b073a-254">UserRefreshInterval</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b073a-255">注</span><span class="sxs-lookup"><span data-stu-id="b073a-255">Note</span></span></strong><br/><p><span data-ttu-id="b073a-256">この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b073a-256">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="b073a-257">AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="b073a-257">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="b073a-258">USERREFRESHINTERVAL</span><span class="sxs-lookup"><span data-stu-id="b073a-258">USERREFRESHINTERVAL</span></span>     </p></td>
<td align="left"><p><span data-ttu-id="b073a-259">UserRefreshIntervalUnit を使った公開の更新間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-259">Specifies the publishing refresh interval using the UserRefreshIntervalUnit.</span></span> <span data-ttu-id="b073a-260">パッケージの更新を無効にするには、[0] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b073a-260">To disable package refresh, select 0.</span></span></p>
<p><span data-ttu-id="b073a-261">文字数 (スペースを含む):85</span><span class="sxs-lookup"><span data-stu-id="b073a-261">Word count (with spaces): 85</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-262">Integer (0-744 時間)</span><span class="sxs-lookup"><span data-stu-id="b073a-262">Integer (0-744 Hours)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-263">Publishing\Servers{serverId}\UserPeriodicRefreshInterval</span><span class="sxs-lookup"><span data-stu-id="b073a-263">Publishing\Servers{serverId}\UserPeriodicRefreshInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-264">0</span><span class="sxs-lookup"><span data-stu-id="b073a-264">0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-265">UserRefreshIntervalUnit</span><span class="sxs-lookup"><span data-stu-id="b073a-265">UserRefreshIntervalUnit</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b073a-266">注</span><span class="sxs-lookup"><span data-stu-id="b073a-266">Note</span></span></strong><br/><p><span data-ttu-id="b073a-267">この設定は、 <strong> AppvclientConfiguration コマンドレットを使用して変更することはできません </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b073a-267">This setting cannot be modified using the <strong>set-AppvclientConfiguration</strong> cmdLet.</span></span> <span data-ttu-id="b073a-268">AppvPublishingServer コマンドレットを使用する必要があり <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="b073a-268">You must use the <strong>Set-AppvPublishingServer</strong> cmdlet.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="b073a-269">USERREFRESHINTERVALUNIT</span><span class="sxs-lookup"><span data-stu-id="b073a-269">USERREFRESHINTERVALUNIT</span></span>  </p></td>
<td align="left"><p><span data-ttu-id="b073a-270">間隔の単位 (Hour 0-23, Day 0-31) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-270">Specifies the interval unit (Hour 0-23, Day 0-31).</span></span> </p></td>
<td align="left"><p><span data-ttu-id="b073a-271">0 (hour)、1日の場合</span><span class="sxs-lookup"><span data-stu-id="b073a-271">0 for hour, 1 for day</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-272">Publishing\Servers {serverId} \ UserPeriodicRefreshIntervalUnit</span><span class="sxs-lookup"><span data-stu-id="b073a-272">Publishing\Servers{serverId}\UserPeriodicRefreshIntervalUnit</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-273">件</span><span class="sxs-lookup"><span data-stu-id="b073a-273">1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-274">MigrationMode</span><span class="sxs-lookup"><span data-stu-id="b073a-274">MigrationMode</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-275">MIGRATIONMODE</span><span class="sxs-lookup"><span data-stu-id="b073a-275">MIGRATIONMODE</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-276">移行モードでは、以前のバージョンの App-v を使用して作成されたパッケージのショートカットと FTA を、App-v クライアントで変更することができます。</span><span class="sxs-lookup"><span data-stu-id="b073a-276">Migration mode allows the App-V client to modify shortcuts and FTA’s for packages created using a previous version of App-V.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-277">True (有効状態)False (無効状態)</span><span class="sxs-lookup"><span data-stu-id="b073a-277">True(enabled state); False (disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-278">Coexistence\MigrationMode</span><span class="sxs-lookup"><span data-stu-id="b073a-278">Coexistence\MigrationMode</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-279">CEIPOPTIN</span><span class="sxs-lookup"><span data-stu-id="b073a-279">CEIPOPTIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-280">CEIPOPTIN</span><span class="sxs-lookup"><span data-stu-id="b073a-280">CEIPOPTIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-281">アプリケーションをさらに向上させるために、App-v 5.0 クライアントを実行しているコンピューターで特定の使用状況情報を収集して返すことを許可します。</span><span class="sxs-lookup"><span data-stu-id="b073a-281">Allows the computer running the App-V 5.0 Client to collect and return certain usage information to help allow us to further improve the application.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-282">無効の場合は0有効にする場合は1</span><span class="sxs-lookup"><span data-stu-id="b073a-282">0 for disabled; 1 for enabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-283">ソフトウェア/Microsoft/AppV/CEIP/CEIPEnable</span><span class="sxs-lookup"><span data-stu-id="b073a-283">SOFTWARE/Microsoft/AppV/CEIP/CEIPEnable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-284">0</span><span class="sxs-lookup"><span data-stu-id="b073a-284">0</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-285">EnablePackageScripts</span><span class="sxs-lookup"><span data-stu-id="b073a-285">EnablePackageScripts</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-286">ENABLEPACKAGESCRIPTS</span><span class="sxs-lookup"><span data-stu-id="b073a-286">ENABLEPACKAGESCRIPTS</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-287">実行する必要がある構成ファイルのパッケージマニフェストで定義されているスクリプトを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b073a-287">Enables scripts defined in the package manifest of configuration files that should run.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-288">True (有効)、False (無効状態)</span><span class="sxs-lookup"><span data-stu-id="b073a-288">True(enabled); False(Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-289">\Scripting\EnablePackageScripts</span><span class="sxs-lookup"><span data-stu-id="b073a-289">\Scripting\EnablePackageScripts</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-290">RoamingFileExclusions</span><span class="sxs-lookup"><span data-stu-id="b073a-290">RoamingFileExclusions</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-291">ROAMINGFILEEXCLUSIONS</span><span class="sxs-lookup"><span data-stu-id="b073a-291">ROAMINGFILEEXCLUSIONS</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-292">ユーザー&#39;s プロファイルでローミングしない% userprofile% を基準としたファイルパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-292">Specifies the file paths relative to %userprofile% that do not roam with a user&#39;s profile.</span></span> <span data-ttu-id="b073a-293">使用例:/ROAMINGFILEEXCLUSIONS =&#39;デスクトップ、マイピクチャ&#39;</span><span class="sxs-lookup"><span data-stu-id="b073a-293">Example usage:  /ROAMINGFILEEXCLUSIONS=&#39;desktop;my pictures&#39;</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-294">RoamingRegistryExclusions</span><span class="sxs-lookup"><span data-stu-id="b073a-294">RoamingRegistryExclusions</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-295">ROAMINGREGISTRYEXCLUSIONS</span><span class="sxs-lookup"><span data-stu-id="b073a-295">ROAMINGREGISTRYEXCLUSIONS</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-296">ユーザープロファイルでローミングされないレジストリパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-296">Specifies the registry paths that do not roam with a user profile.</span></span> <span data-ttu-id="b073a-297">使用例:/ROAMINGREGISTRYEXCLUSIONS = ソフトウェア \ クラス; ソフトウェア \ クライアント</span><span class="sxs-lookup"><span data-stu-id="b073a-297">Example usage: /ROAMINGREGISTRYEXCLUSIONS=software\classes;software\clients</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-298">String</span><span class="sxs-lookup"><span data-stu-id="b073a-298">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-299">Integration\RoamingRegistryExclusions</span><span class="sxs-lookup"><span data-stu-id="b073a-299">Integration\RoamingRegistryExclusions</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-300">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-300">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-301">統合ルートユーザ</span><span class="sxs-lookup"><span data-stu-id="b073a-301">IntegrationRootUser</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-302">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-302">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-303">ユーザーごとに公開されたパッケージの現在のバージョンに関連付けられているシンボリックリンクを作成する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-303">Specifies the location to create symbolic links associated with the current version of a per-user published package.</span></span> <span data-ttu-id="b073a-304">ショートカットやファイルの種類の関連付けなどのすべての仮想アプリケーションの拡張は、このパスをポイントします。</span><span class="sxs-lookup"><span data-stu-id="b073a-304">all virtual application extensions, for example shortcuts and file type associations, will point to this path.</span></span> <span data-ttu-id="b073a-305">パスを指定しない場合、パッケージを公開するときにシンボリックリンクは使用されません。</span><span class="sxs-lookup"><span data-stu-id="b073a-305">If you do not specify a path, symbolic links will not be used when you publish the package.</span></span> <span data-ttu-id="b073a-306">例:%localappdata%\Microsoft\AppV\Client\Integration.</span><span class="sxs-lookup"><span data-stu-id="b073a-306">For example: %localappdata%\Microsoft\AppV\Client\Integration.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-307">String</span><span class="sxs-lookup"><span data-stu-id="b073a-307">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-308">統合と統合 rootuser</span><span class="sxs-lookup"><span data-stu-id="b073a-308">Integration\IntegrationRootUser</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-309">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-309">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-310">統合 Rootグローバル</span><span class="sxs-lookup"><span data-stu-id="b073a-310">IntegrationRootGlobal</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-311">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-311">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-312">グローバルに公開されたパッケージの現在のバージョンに関連付けられているシンボリックリンクを作成する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-312">Specifies the location to create symbolic links associated with the current version of a globally published package.</span></span> <span data-ttu-id="b073a-313">ショートカットやファイルの種類の関連付けなどのすべての仮想アプリケーションの拡張は、このパスをポイントします。</span><span class="sxs-lookup"><span data-stu-id="b073a-313">all virtual application extensions, for example shortcuts and file type associations, will point to this path.</span></span> <span data-ttu-id="b073a-314">パスを指定しない場合、パッケージを公開するときにシンボリックリンクは使用されません。</span><span class="sxs-lookup"><span data-stu-id="b073a-314">If you do not specify a path, symbolic links will not be used when you publish the package.</span></span> <span data-ttu-id="b073a-315">例:%allusersprofile%\Microsoft\AppV\Client\Integration</span><span class="sxs-lookup"><span data-stu-id="b073a-315">For example: %allusersprofile%\Microsoft\AppV\Client\Integration</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-316">String</span><span class="sxs-lookup"><span data-stu-id="b073a-316">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-317">統合と統合 rootグローバル</span><span class="sxs-lookup"><span data-stu-id="b073a-317">Integration\IntegrationRootGlobal</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-318">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-318">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-319">VirtualizableExtensions</span><span class="sxs-lookup"><span data-stu-id="b073a-319">VirtualizableExtensions</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-320">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-320">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-321">ローカルにインストールされたアプリケーションを仮想環境で実行できるかどうかを判断するために使用できるファイル名拡張子のコンマ区切りリスト。</span><span class="sxs-lookup"><span data-stu-id="b073a-321">A comma -delineated list of file name extensions that can be used to determine if a locally installed application can be run in the virtual environment.</span></span></p>
<p><span data-ttu-id="b073a-322">公開時にショートカット、FTAs、およびその他の拡張ポイントを作成すると、その拡張ポイントに関連付けられたアプリケーションがローカルにインストールされている場合、App-v はファイル名の拡張子を一覧と比較します。</span><span class="sxs-lookup"><span data-stu-id="b073a-322">When shortcuts, FTAs, and other extension points are created during publishing, App-V will compare the file name extension to the list if the application that is associated with the extension point is locally installed.</span></span> <span data-ttu-id="b073a-323">拡張機能がある場合は、 <strong> runvirtual </strong> コマンドラインパラメーターが追加され、アプリケーションは実質的に実行されます。</span><span class="sxs-lookup"><span data-stu-id="b073a-323">If the extension is located, the <strong>RunVirtual</strong> command line parameter will be added, and the application will run virtually.</span></span></p>
<p><span data-ttu-id="b073a-324"><strong>Runvirtual パラメーターの詳細につい </strong> ては、「 <a href="running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md" data-raw-source="[Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)"> 仮想化されたアプリケーションを使って、仮想環境内でローカルにインストールされたアプリケーションを実行する」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="b073a-324">For more information about the <strong>RunVirtual</strong> parameter, see <a href="running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md" data-raw-source="[Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)">Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications</a>.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-325">String</span><span class="sxs-lookup"><span data-stu-id="b073a-325">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-326">統合 \ virtualizableextensions</span><span class="sxs-lookup"><span data-stu-id="b073a-326">Integration\VirtualizableExtensions</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-327">ポリシーの値が書き込まれない</span><span class="sxs-lookup"><span data-stu-id="b073a-327">Policy value not written</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-328">ReportingEnabled</span><span class="sxs-lookup"><span data-stu-id="b073a-328">ReportingEnabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-329">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-329">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-330">クライアントが情報をレポートサーバーに返すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="b073a-330">Enables the client to return information to a reporting server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-331">True (有効)、False (無効状態)</span><span class="sxs-lookup"><span data-stu-id="b073a-331">True (enabled); False (Disabled state)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-332">Reporting\EnableReporting</span><span class="sxs-lookup"><span data-stu-id="b073a-332">Reporting\EnableReporting</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-333">False</span><span class="sxs-lookup"><span data-stu-id="b073a-333">False</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-334">ReportingServerURL</span><span class="sxs-lookup"><span data-stu-id="b073a-334">ReportingServerURL</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-335">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-335">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-336">クライアント情報が保存されている、レポートサーバー上の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-336">Specifies the location on the reporting server where client information is saved.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-337">String</span><span class="sxs-lookup"><span data-stu-id="b073a-337">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-338">Reporting\ReportingServer</span><span class="sxs-lookup"><span data-stu-id="b073a-338">Reporting\ReportingServer</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-339">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-339">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-340">Reportingdatacachlimit</span><span class="sxs-lookup"><span data-stu-id="b073a-340">ReportingDataCacheLimit</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-341">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-341">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-342">レポート情報を格納する XML キャッシュの最大サイズ (MB) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-342">Specifies the maximum size in megabytes (MB) of the XML cache for storing reporting information.</span></span> <span data-ttu-id="b073a-343">サイズは、メモリ内のキャッシュに適用されます。</span><span class="sxs-lookup"><span data-stu-id="b073a-343">The size applies to the cache in memory.</span></span> <span data-ttu-id="b073a-344">上限に達すると、ログファイルがロールオーバーされます。</span><span class="sxs-lookup"><span data-stu-id="b073a-344">When the limit is reached, the log file will roll over.</span></span> <span data-ttu-id="b073a-345">0 ~ 1024 の間で設定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-345">Set between 0 and 1024.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-346">Integer [0-1024]</span><span class="sxs-lookup"><span data-stu-id="b073a-346">Integer [0-1024]</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-347">Reporting\DataCacheLimit</span><span class="sxs-lookup"><span data-stu-id="b073a-347">Reporting\DataCacheLimit</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-348">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-348">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-349">Reportingの各の Locksize</span><span class="sxs-lookup"><span data-stu-id="b073a-349">ReportingDataBlockSize</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-350">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-350">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-351">アップロード要求を報告するためにサーバーに送信する最大サイズ (バイト単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-351">Specifies the maximum size in bytes to transmit to the server for reporting upload requests.</span></span> <span data-ttu-id="b073a-352">これにより、ログのサイズが大きくなったときに、永続的な送信エラーが発生しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b073a-352">This can help avoid permanent transmission failures when the log has reached a significant size.</span></span> <span data-ttu-id="b073a-353">1024と無制限の間で設定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-353">Set between 1024 and unlimited.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-354">Integer [1024-実質無制限]</span><span class="sxs-lookup"><span data-stu-id="b073a-354">Integer [1024 - Unlimited]</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-355">Reporting\DataBlockSize</span><span class="sxs-lookup"><span data-stu-id="b073a-355">Reporting\DataBlockSize</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-356">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-356">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-357">ReportingStartTime</span><span class="sxs-lookup"><span data-stu-id="b073a-357">ReportingStartTime</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-358">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-358">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-359">クライアントの開始時刻を指定して、データをレポートサーバーに送信します。</span><span class="sxs-lookup"><span data-stu-id="b073a-359">Specifies the time to initiate the client to send data to the reporting server.</span></span> <span data-ttu-id="b073a-360">1日の時刻に対応する0-23 の間に有効な整数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b073a-360">You must specify a valid integer between 0-23 corresponding to the hour of the day.</span></span> <span data-ttu-id="b073a-361">既定では、 <strong> reportingstarttime は、 </strong> 現在の日である 10 P. または22で開始されます。</span><span class="sxs-lookup"><span data-stu-id="b073a-361">By default the <strong>ReportingStartTime</strong> will start on the current day at 10 P.M.or 22.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b073a-362">注</span><span class="sxs-lookup"><span data-stu-id="b073a-362">Note</span></span></strong><br/><p><span data-ttu-id="b073a-363">この設定は、App-v 5.0 クライアントを実行しているコンピューターが少なくともオフラインになる可能性のある時刻に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b073a-363">You should configure this setting to a time when computers running the App-V 5.0 client are least likely to be offline.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="b073a-364">整数 (0 ~ 23)</span><span class="sxs-lookup"><span data-stu-id="b073a-364">Integer (0 – 23)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-365">レポート \ 開始時刻</span><span class="sxs-lookup"><span data-stu-id="b073a-365">Reporting\ StartTime</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-366">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-366">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-367">ReportingInterval</span><span class="sxs-lookup"><span data-stu-id="b073a-367">ReportingInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-368">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-368">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-369">クライアントがデータをレポートサーバーに再送信するために使用する再試行間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-369">Specifies the retry interval that the client will use to resend data to the reporting server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-370">Integer</span><span class="sxs-lookup"><span data-stu-id="b073a-370">Integer</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-371">Reporting\RetryInterval</span><span class="sxs-lookup"><span data-stu-id="b073a-371">Reporting\RetryInterval</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-372">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-372">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-373">ReportingRandomDelay</span><span class="sxs-lookup"><span data-stu-id="b073a-373">ReportingRandomDelay</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-374">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-374">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-375">レポートサーバーに送信されるデータの最大遅延 (分単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="b073a-375">Specifies the maximum delay (in minutes) for data to be sent to the reporting server.</span></span> <span data-ttu-id="b073a-376">スケジュールされたタスクが開始されると、クライアントは0と ReportingRandomDelay の間のランダムな遅延を生成 <strong> </strong> し、データを送信する前に指定された期間待機します。</span><span class="sxs-lookup"><span data-stu-id="b073a-376">When the scheduled task is started, the client generates a random delay between 0 and <strong>ReportingRandomDelay</strong> and will wait the specified duration before sending data.</span></span> <span data-ttu-id="b073a-377">これは、サーバーでの競合を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b073a-377">This can help to prevent collisions on the server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-378">Integer [0-ReportingRandomDelay]</span><span class="sxs-lookup"><span data-stu-id="b073a-378">Integer [0 - ReportingRandomDelay]</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-379">Reporting\RandomDelay</span><span class="sxs-lookup"><span data-stu-id="b073a-379">Reporting\RandomDelay</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-380">ポリシー値が書き込まれていない (構成されていない)</span><span class="sxs-lookup"><span data-stu-id="b073a-380">Policy value not written (same as Not Configured)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-381">EnableDynamicVirtualization</span><span class="sxs-lookup"><span data-stu-id="b073a-381">EnableDynamicVirtualization</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b073a-382">重要</span><span class="sxs-lookup"><span data-stu-id="b073a-382">Important</span></span></strong><br/><p><span data-ttu-id="b073a-383">この設定は、App-v 5.0 SP2 以降でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b073a-383">This setting is available only with App-V 5.0 SP2 or later.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="b073a-384">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-384">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-385">サポートされているシェルの拡張機能、ブラウザーヘルパーオブジェクト、アクティブな X コントロールを仮想アプリケーションで仮想化して実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="b073a-385">Enables supported Shell Extensions, Browser Helper Objects, and Active X controls to be virtualized and run with virtual applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-386">1 (有効)、0 (無効)</span><span class="sxs-lookup"><span data-stu-id="b073a-386">1 (Enabled), 0 (Disabled)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-387">HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Virtualization</span><span class="sxs-lookup"><span data-stu-id="b073a-387">HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\Virtualization</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-388">EnablePublishingRefreshUI</span><span class="sxs-lookup"><span data-stu-id="b073a-388">EnablePublishingRefreshUI</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b073a-389">重要</span><span class="sxs-lookup"><span data-stu-id="b073a-389">Important</span></span></strong><br/><p><span data-ttu-id="b073a-390">この設定は、App-v 5.0 SP2 でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b073a-390">This setting is available only with App-V 5.0 SP2.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="b073a-391">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-391">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-392">App-v 5.0 クライアントを実行しているコンピューターの公開更新の進行状況バーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="b073a-392">Enables the publishing refresh progress bar for the computer running the App-V 5.0 Client.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-393">1 (有効)、0 (無効)</span><span class="sxs-lookup"><span data-stu-id="b073a-393">1 (Enabled), 0 (Disabled)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-394">HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Publishing</span><span class="sxs-lookup"><span data-stu-id="b073a-394">HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\Publishing</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b073a-395">HideUI</span><span class="sxs-lookup"><span data-stu-id="b073a-395">HideUI</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b073a-396">重要</span><span class="sxs-lookup"><span data-stu-id="b073a-396">Important</span></span></strong><br/><p><span data-ttu-id="b073a-397">この設定は、App-v 5.0 SP2 でのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="b073a-397">This setting is available only with App-V 5.0 SP2.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="b073a-398">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-398">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-399">公開の更新の進行状況バーを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="b073a-399">Hides the publishing refresh progress bar.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-400">1 (有効)、0 (無効)</span><span class="sxs-lookup"><span data-stu-id="b073a-400">1 (Enabled), 0 (Disabled)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b073a-401">プロセスの仮想コンポーネントの方法</span><span class="sxs-lookup"><span data-stu-id="b073a-401">ProcessesUsingVirtualComponents</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-402">利用不可。</span><span class="sxs-lookup"><span data-stu-id="b073a-402">Not available.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-403">プロセスパス (ワイルドカードが含まれている可能性がある) の一覧を指定します。これは、動的仮想化 (サポートされているシェル拡張機能、ブラウザーヘルパーオブジェクト、および ActiveX コントロール) を使用するための候補です。</span><span class="sxs-lookup"><span data-stu-id="b073a-403">Specifies a list of process paths (that may contain wildcards), which are candidates for using dynamic virtualization (supported shell extensions, browser helper objects, and ActiveX controls).</span></span> <span data-ttu-id="b073a-404">完全なパスがこれらの項目のいずれかに一致するプロセスのみが、動的仮想化を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="b073a-404">Only processes whose full path matches one of these items can use dynamic virtualization.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-405">String</span><span class="sxs-lookup"><span data-stu-id="b073a-405">String</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-406">Virtualization\ProcessesUsingVirtualComponents</span><span class="sxs-lookup"><span data-stu-id="b073a-406">Virtualization\ProcessesUsingVirtualComponents</span></span></p></td>
<td align="left"><p><span data-ttu-id="b073a-407">空の文字列。</span><span class="sxs-lookup"><span data-stu-id="b073a-407">Empty string.</span></span></p></td>
</tr>
</tbody>
</table>








## <span data-ttu-id="b073a-408">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b073a-408">Related topics</span></span>


[<span data-ttu-id="b073a-409">App-V 5.0 Sequencer および Client の展開</span><span class="sxs-lookup"><span data-stu-id="b073a-409">Deploying the App-V 5.0 Sequencer and Client</span></span>](deploying-the-app-v-50-sequencer-and-client.md)

[<span data-ttu-id="b073a-410">ADMX テンプレートとグループ ポリシーを使用して App-V 5.0 Client 構成を変更する方法</span><span class="sxs-lookup"><span data-stu-id="b073a-410">How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy</span></span>](how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)

[<span data-ttu-id="b073a-411">APP-V Client を展開する方法</span><span class="sxs-lookup"><span data-stu-id="b073a-411">How to Deploy the App-V Client</span></span>](how-to-deploy-the-app-v-client-gb18030.md)









