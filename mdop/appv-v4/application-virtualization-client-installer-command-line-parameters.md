---
title: Application Virtualization Client インストーラーのコマンド ライン パラメーター
description: Application Virtualization Client インストーラーのコマンド ライン パラメーター
author: dansimp
ms.assetid: 508fa404-52a5-4919-8788-2a3dfb00639b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 911d333c80060c1881c96430c1d2d0516b6a4855
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819717"
---
# <span data-ttu-id="0a092-103">Application Virtualization Client インストーラーのコマンド ライン パラメーター</span><span class="sxs-lookup"><span data-stu-id="0a092-103">Application Virtualization Client Installer Command-Line Parameters</span></span>


<span data-ttu-id="0a092-104">次の表に、使用できるすべての Microsoft Application Virtualization クライアントインストーラーのコマンドラインパラメーターとその値、および各パラメーターの簡単な説明を示します。</span><span class="sxs-lookup"><span data-stu-id="0a092-104">The following table lists all available Microsoft Application Virtualization Client installer command-line parameters, their values, and a brief description of each parameter.</span></span> <span data-ttu-id="0a092-105">パラメーターは大文字と小文字を区別し、すべて大文字で入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-105">Parameters are case-sensitive and must be entered as all-uppercase letters.</span></span> <span data-ttu-id="0a092-106">すべてのパラメーター値は二重引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-106">All parameter values must be enclosed in double quotes.</span></span>

**<span data-ttu-id="0a092-107">注</span><span class="sxs-lookup"><span data-stu-id="0a092-107">Note</span></span>**  
-   <span data-ttu-id="0a092-108">App-v バージョン4.6 の場合、クライアントのアップグレード中にコマンドラインパラメーターを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="0a092-108">For App-V version 4.6, command-line parameters cannot be used during a client upgrade.</span></span>

-   <span data-ttu-id="0a092-109">*Swicachesize*と*MINFREESPACEMB*の各パラメーターは、コマンドラインで組み合わせることはできません。</span><span class="sxs-lookup"><span data-stu-id="0a092-109">The *SWICACHESIZE* and *MINFREESPACEMB* parameters cannot be combined on the command line.</span></span> <span data-ttu-id="0a092-110">両方を使用する場合、 *Swicachesize*パラメーターは無視されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-110">If both are used, the *SWICACHESIZE* parameter will be ignored.</span></span>



<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0a092-111">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0a092-111">Parameter</span></span></th>
<th align="left"><span data-ttu-id="0a092-112">値</span><span class="sxs-lookup"><span data-stu-id="0a092-112">Values</span></span></th>
<th align="left"><span data-ttu-id="0a092-113">説明</span><span class="sxs-lookup"><span data-stu-id="0a092-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="0a092-114">ALLOWINDEPENDENTFILESTREAMING</span><span class="sxs-lookup"><span data-stu-id="0a092-114">ALLOWINDEPENDENTFILESTREAMING</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-115">TRUE</span><span class="sxs-lookup"><span data-stu-id="0a092-115">TRUE</span></span></p>
<p><span data-ttu-id="0a092-116">FALSE</span><span class="sxs-lookup"><span data-stu-id="0a092-116">FALSE</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-117">クライアントが APPLICATIONSOURCEROOT パラメーターで構成されているかどうかに関係なく、ファイルからのストリーミングを有効にするかどうかを示し <em> </em> ます。</span><span class="sxs-lookup"><span data-stu-id="0a092-117">Indicates whether streaming from file will be enabled regardless of how the client has been configured with the <em>APPLICATIONSOURCEROOT</em> parameter.</span></span> <span data-ttu-id="0a092-118">FALSE に設定すると、OSD HREF または <em> APPLICATIONSOURCEROOT </em> パラメーターにファイルパスが含まれている場合でも、トランスポートでファイルのストリーミングを有効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="0a092-118">If set to FALSE, the transport will not enable streaming from files even if the OSD HREF or the <em>APPLICATIONSOURCEROOT</em> parameter contains a file path.</span></span></p>
<p><span data-ttu-id="0a092-119">設定可能な値:</span><span class="sxs-lookup"><span data-stu-id="0a092-119">Possible values:</span></span></p>
<ul>
<li><p><span data-ttu-id="0a092-120">TRUE: 手動で展開されたアプリケーションは、ディスクから読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="0a092-120">TRUE—Manually deployed application may be loaded from disk.</span></span></p></li>
<li><p><span data-ttu-id="0a092-121">FALSE の場合、すべてのアプリケーションはソースストリーミングサーバーから取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-121">FALSE—All applications must come from source streaming server.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="0a092-122">APPLICATIONSOURCEROOT</span><span class="sxs-lookup"><span data-stu-id="0a092-122">APPLICATIONSOURCEROOT</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-123">RTSP:// <em> URL </em> (動的なパッケージ配信用)</span><span class="sxs-lookup"><span data-stu-id="0a092-123">RTSP:// <em>URL</em> (for dynamic package delivery)</span></span></p>
<p><span data-ttu-id="0a092-124">File:// <em> URL </em> または <em> UNC </em> (ファイルパッケージ配信からの読み込みの場合)</span><span class="sxs-lookup"><span data-stu-id="0a092-124">File:// <em>URL</em> or <em>UNC</em> (for load from file package delivery)</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-125">管理者または電子ソフトウェアの配布システムを有効にして、アプリケーションの読み込みがトポロジ管理スキームに準拠していることを確認するには、アプリケーション HREF 要素 (ソースの場所) の OSD コードベースを上書きできるようにします。</span><span class="sxs-lookup"><span data-stu-id="0a092-125">To enable an administrator or an electronic software distribution system to ensure that application loading is performed in compliance with the topology management scheme, allows an override of the OSD CODEBASE for the application HREF element (the source location).</span></span> <span data-ttu-id="0a092-126">この値が "" (既定値) の場合は、既存の OSD ファイルの設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-126">If the value is “”, which is the default value, the existing OSD file settings are used.</span></span></p>
<p><span data-ttu-id="0a092-127">URL にはいくつかの部分があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-127">A URL has several parts:</span></span></p>
<p><span data-ttu-id="0a092-128">&lt;protocol &gt; :/ &lt; server &gt; : &lt; port &gt; / &lt; path &gt; / &lt; ? クエリ &gt; &lt; #fragment&gt;</span><span class="sxs-lookup"><span data-stu-id="0a092-128">&lt;protocol&gt;://&lt;server&gt;:&lt;port&gt;/&lt;path&gt;/&lt;?query&gt;&lt;#fragment&gt;</span></span></p>
<p><span data-ttu-id="0a092-129">UNC パスには、次の3つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-129">A UNC path has three parts:</span></span></p>
<p><span data-ttu-id="0a092-130">&amp;lt; computername &gt; &amp; lt; フォルダーの共有 &gt; &amp; lt; リソース&gt;</span><span class="sxs-lookup"><span data-stu-id="0a092-130">&amp;lt;computername&gt;&amp;lt;share folder&gt;&amp;lt;resource&gt;</span></span></p>
<p><span data-ttu-id="0a092-131"><em>クライアントで APPLICATIONSOURCEROOT パラメーターが指定されている場合 </em> 、クライアントは、osd ファイルの URL または UNC パスを構成要素に区切り、osd セクションを対応する APPLICATIONSOURCEROOT セクションに置き換えます <em> </em> 。</span><span class="sxs-lookup"><span data-stu-id="0a092-131">If the <em>APPLICATIONSOURCEROOT</em> parameter is specified on a client, the client will break the URL or UNC path from an OSD file into its constituent parts and replace the OSD sections with the corresponding <em>APPLICATIONSOURCEROOT</em> sections.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="0a092-132">重要</span><span class="sxs-lookup"><span data-stu-id="0a092-132">Important</span></span></strong><br/><p><span data-ttu-id="0a092-133">UNC パスを使用して file://を使用する場合は、必ず正しい形式を使用してください。</span><span class="sxs-lookup"><span data-stu-id="0a092-133">Be sure to use the correct format when using file:// with a UNC path.</span></span> <span data-ttu-id="0a092-134">正しい形式は file:// &amp; lt; server &gt; &amp; lt; 共有 &gt; です。</span><span class="sxs-lookup"><span data-stu-id="0a092-134">The correct format is file://&amp;lt;server&gt;&amp;lt;share&gt;.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="0a092-135">ICONSOURCEROOT</span><span class="sxs-lookup"><span data-stu-id="0a092-135">ICONSOURCEROOT</span></span></em></p></td>
<td align="left"><p><em><span data-ttu-id="0a092-136">UNC</span><span class="sxs-lookup"><span data-stu-id="0a092-136">UNC</span></span></em></p>
<p><span data-ttu-id="0a092-137">HTTP:// <em> url </em> または HTTPS:// <em> url</span><span class="sxs-lookup"><span data-stu-id="0a092-137">HTTP://<em>URL</em> or HTTPS://<em>URL</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-138">管理者が、シーケンス処理されたアプリケーションパッケージのアイコン取得のソースの場所を、文書中に指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0a092-138">Enables an administrator to specify a source location for icon retrieval for a sequenced application package during publication.</span></span> <span data-ttu-id="0a092-139">アイコンソースルートは UNC パスと Url (HTTP または HTTPS) をサポートします。</span><span class="sxs-lookup"><span data-stu-id="0a092-139">Icon source roots support UNC paths and URLs (HTTP or HTTPS).</span></span> <span data-ttu-id="0a092-140">この値が "" (既定値) の場合は、既存の OSD ファイルの設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-140">If the value is “”, which is the default value, the existing OSD file settings are used.</span></span></p>
<p><span data-ttu-id="0a092-141">URL にはいくつかの部分があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-141">A URL has several parts:</span></span></p>
<p><span data-ttu-id="0a092-142">&lt;protocol &gt; :/ &lt; server &gt; : &lt; port &gt; / &lt; path &gt; / &lt; ? クエリ &gt; &lt; #fragment&gt;</span><span class="sxs-lookup"><span data-stu-id="0a092-142">&lt;protocol&gt;://&lt;server&gt;:&lt;port&gt;/&lt;path&gt;/&lt;?query&gt;&lt;#fragment&gt;</span></span></p>
<p><span data-ttu-id="0a092-143">UNC パスには、次の3つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-143">A UNC path has three parts:</span></span></p>
<p><span data-ttu-id="0a092-144">&amp;lt; computername &gt; &amp; lt; フォルダーの共有 &gt; &amp; lt; リソース&gt;</span><span class="sxs-lookup"><span data-stu-id="0a092-144">&amp;lt;computername&gt;&amp;lt;share folder&gt;&amp;lt;resource&gt;</span></span></p>
<div class="alert">
<strong><span data-ttu-id="0a092-145">重要</span><span class="sxs-lookup"><span data-stu-id="0a092-145">Important</span></span></strong><br/><p><span data-ttu-id="0a092-146">UNC パスを使用する場合は、必ず正しい形式を使用してください。</span><span class="sxs-lookup"><span data-stu-id="0a092-146">Be sure to use the correct format when using a UNC path.</span></span> <span data-ttu-id="0a092-147">使用可能な形式は &amp; lt、server &gt; &amp; lt、共有 &gt; または &lt; ドライブ文字 &gt; : &amp; lt; フォルダー &gt; 。</span><span class="sxs-lookup"><span data-stu-id="0a092-147">Acceptable formats are &amp;lt;server&gt;&amp;lt;share&gt; or &lt;drive letter&gt;:&amp;lt;folder&gt;.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="0a092-148">OSDSOURCEROOT</span><span class="sxs-lookup"><span data-stu-id="0a092-148">OSDSOURCEROOT</span></span></em></p></td>
<td align="left"><p><em><span data-ttu-id="0a092-149">UNC</span><span class="sxs-lookup"><span data-stu-id="0a092-149">UNC</span></span></em></p>
<p><span data-ttu-id="0a092-150">HTTP:// <em> url </em> または HTTPS:// <em> url</span><span class="sxs-lookup"><span data-stu-id="0a092-150">HTTP://<em>URL</em> or HTTPS://<em>URL</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-151">公開時に、管理者がアプリケーションパッケージの OSD ファイル取得のソースの場所を指定できるようにします。</span><span class="sxs-lookup"><span data-stu-id="0a092-151">Enables an administrator to specify a source location for OSD file retrieval for an application package during publication.</span></span> <span data-ttu-id="0a092-152">OSD ソースのルートは、UNC パスと Url (HTTP または HTTPS) をサポートします。</span><span class="sxs-lookup"><span data-stu-id="0a092-152">OSD source roots support UNC paths and URLs (HTTP or HTTPS).</span></span> <span data-ttu-id="0a092-153">この値が "" (既定値) の場合は、既存の OSD ファイルの設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-153">If the value is “”, which is the default value, the existing OSD file settings are used.</span></span></p>
<p><span data-ttu-id="0a092-154">URL にはいくつかの部分があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-154">A URL has several parts:</span></span></p>
<p><span data-ttu-id="0a092-155">&lt;protocol &gt; :/ &lt; server &gt; : &lt; port &gt; / &lt; path &gt; / &lt; ? クエリ &gt; &lt; #fragment&gt;</span><span class="sxs-lookup"><span data-stu-id="0a092-155">&lt;protocol&gt;://&lt;server&gt;:&lt;port&gt;/&lt;path&gt;/&lt;?query&gt;&lt;#fragment&gt;</span></span></p>
<p><span data-ttu-id="0a092-156">UNC パスには、次の3つの部分があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-156">A UNC path has three parts:</span></span></p>
<p><span data-ttu-id="0a092-157">&amp;lt; computername &gt; &amp; lt; フォルダーの共有 &gt; &amp; lt; リソース&gt;</span><span class="sxs-lookup"><span data-stu-id="0a092-157">&amp;lt;computername&gt;&amp;lt;share folder&gt;&amp;lt;resource&gt;</span></span></p>
<div class="alert">
<strong><span data-ttu-id="0a092-158">重要</span><span class="sxs-lookup"><span data-stu-id="0a092-158">Important</span></span></strong><br/><p><span data-ttu-id="0a092-159">UNC パスを使用する場合は、必ず正しい形式を使用してください。</span><span class="sxs-lookup"><span data-stu-id="0a092-159">Be sure to use the correct format when using a UNC path.</span></span> <span data-ttu-id="0a092-160">使用可能な形式は &amp; lt、server &gt; &amp; lt、共有 &gt; または &lt; ドライブ文字 &gt; : &amp; lt; フォルダー &gt; 。</span><span class="sxs-lookup"><span data-stu-id="0a092-160">Acceptable formats are &amp;lt;server&gt;&amp;lt;share&gt; or &lt;drive letter&gt;:&amp;lt;folder&gt;.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="0a092-161">AUTOLOADONLOGIN</span><span class="sxs-lookup"><span data-stu-id="0a092-161">AUTOLOADONLOGIN</span></span></em></p>
<p><em><span data-ttu-id="0a092-162">AUTOLOADONLAUNCH</span><span class="sxs-lookup"><span data-stu-id="0a092-162">AUTOLOADONLAUNCH</span></span></em></p>
<p><em><span data-ttu-id="0a092-163">AUTOLOADONREFRESH</span><span class="sxs-lookup"><span data-stu-id="0a092-163">AUTOLOADONREFRESH</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-164">[0 | 1]</span><span class="sxs-lookup"><span data-stu-id="0a092-164">[0|1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-165">アプリケーションの自動読み込みを開始するイベントを定義する自動ロードトリガー。</span><span class="sxs-lookup"><span data-stu-id="0a092-165">The AutoLoad triggers that define the events that initiate auto-loading of applications.</span></span> <span data-ttu-id="0a092-166">自動ロードは、バックグラウンドストリーミングを暗黙的に使用して、アプリケーションをキャッシュに完全に読み込むことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="0a092-166">AutoLoad implicitly uses background streaming to enable the application to be fully loaded into cache.</span></span></p>
<p><span data-ttu-id="0a092-167">プライマリ機能ブロックはできるだけ早く読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="0a092-167">The primary feature block will be loaded as quickly as possible.</span></span> <span data-ttu-id="0a092-168">その他の機能ブロックはバックグラウンドで読み込まれ、ユーザーのアプリケーション操作などのフォアグラウンド操作が優先され、最適なパフォーマンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-168">Remaining feature blocks will be loaded in the background to enable foreground operations, such as user interaction with applications, to take priority and provide optimal performance.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="0a092-169">注</span><span class="sxs-lookup"><span data-stu-id="0a092-169">Note</span></span></strong><br/><p><span data-ttu-id="0a092-170"><em>自動読み込み対象のアプリケーションは、autoloadtarget </em> パラメーターによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-170">The <em>AUTOLOADTARGET</em> parameter determines which applications are auto-loaded.</span></span> <span data-ttu-id="0a092-171">既定では、 <em> autoloadtarget が設定されていない限り、使用されているパッケージは自動ロードされ </em> ます。</span><span class="sxs-lookup"><span data-stu-id="0a092-171">By default, packages that have been used are auto-loaded unless <em>AUTOLOADTARGET</em> is set.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="0a092-172">各パラメーターは、次のように読み込み動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="0a092-172">Each parameter affects loading behavior as follows:</span></span></p>
<ul>
<li><p><em><span data-ttu-id="0a092-173">AUTOLOADONLOGIN </em> : ユーザーがログインしたときに読み込みが開始されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-173">AUTOLOADONLOGIN</em>—Loading starts when the user logs in.</span></span></p></li>
<li><p><em><span data-ttu-id="0a092-174">AUTOLOADONLAUNCH </em> : 読み込みは、ユーザーがアプリケーションを開始したときに開始されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-174">AUTOLOADONLAUNCH</em>—Loading starts when the user starts an application.</span></span></p></li>
<li><p><em><span data-ttu-id="0a092-175">AUTOLOADONREFRESH </em> —公開の更新が行われると、読み込みが開始されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-175">AUTOLOADONREFRESH</em>—Loading starts when a publishing refresh occurs.</span></span></p></li>
</ul>
<p><span data-ttu-id="0a092-176">3つの値を組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="0a092-176">The three values can be combined.</span></span> <span data-ttu-id="0a092-177">次の例では、自動ロードトリガーは、ユーザーログイン時と公開更新が発生するときの両方で有効になります。</span><span class="sxs-lookup"><span data-stu-id="0a092-177">In the following example, AutoLoad triggers are enabled both at user login and when publishing refresh occurs:</span></span></p>
<p><em><span data-ttu-id="0a092-178">AUTOLOADONLOGIN AUTOLOADONLOGIN</span><span class="sxs-lookup"><span data-stu-id="0a092-178">AUTOLOADONLOGIN AUTOLOADONREFRESH</span></span></em></p>
<div class="alert">
<strong><span data-ttu-id="0a092-179">注</span><span class="sxs-lookup"><span data-stu-id="0a092-179">Note</span></span></strong><br/><p><span data-ttu-id="0a092-180">クライアントが最初のインストール時にこれらの値で構成されている場合は、ユーザーが次回ログオフして再びログオンするまで、自動ロードはトリガーされません。</span><span class="sxs-lookup"><span data-stu-id="0a092-180">If the client is configured with these values at first install, Autoload will not be triggered until the next time the user logs off and logs back on.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="0a092-181">AUTOLOADTARGET</span><span class="sxs-lookup"><span data-stu-id="0a092-181">AUTOLOADTARGET</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-182">-</span><span class="sxs-lookup"><span data-stu-id="0a092-182">NONE</span></span></p>
<p><span data-ttu-id="0a092-183">[ALL] (すべて)</span><span class="sxs-lookup"><span data-stu-id="0a092-183">ALL</span></span></p>
<p><span data-ttu-id="0a092-184">PREVUSED</span><span class="sxs-lookup"><span data-stu-id="0a092-184">PREVUSED</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-185">自動ロードトリガーが発生したときに自動的に読み込まれる内容を示します。</span><span class="sxs-lookup"><span data-stu-id="0a092-185">Indicates what will be auto-loaded when any given AutoLoad triggers occur.</span></span></p>
<p><span data-ttu-id="0a092-186">設定可能な値:</span><span class="sxs-lookup"><span data-stu-id="0a092-186">Possible values:</span></span></p>
<ul>
<li><p><span data-ttu-id="0a092-187">NONE: 設定されているトリガーに関係なく、自動読み込みは行われません。</span><span class="sxs-lookup"><span data-stu-id="0a092-187">NONE—No auto-loading, regardless of what triggers might be set.</span></span></p></li>
<li><p><span data-ttu-id="0a092-188">[すべて]: 自動ロードトリガーが有効になっている場合、すべてのパッケージは、起動されたかどうかにかかわらず、自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="0a092-188">ALL—If any AutoLoad trigger is enabled, all packages are automatically loaded, whether or not they have ever been launched.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="0a092-189">注</span><span class="sxs-lookup"><span data-stu-id="0a092-189">Note</span></span></strong><br/><p><span data-ttu-id="0a092-190">この設定は、SFTMIME を追加してパッケージコマンドを構成することで、個々のパッケージに対して構成され <strong> </strong> <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="0a092-190">This setting is configured for individual packages by using the SFTMIME <strong>ADD PACKAGE</strong> and <strong>CONFIGURE PACKAGE</strong> commands.</span></span> <span data-ttu-id="0a092-191">これらのコマンドの詳細については、「 <a href="sftmime--command-reference.md" data-raw-source="[SFTMIME Command Reference](sftmime--command-reference.md)"> sftmime コマンドのリファレンス」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="0a092-191">For more information about these commands, see <a href="sftmime--command-reference.md" data-raw-source="[SFTMIME Command Reference](sftmime--command-reference.md)">SFTMIME Command Reference</a>.</span></span></p>
</div>
<div>

</div></li>
<li><p><span data-ttu-id="0a092-192">PREVUSED —自動ロードトリガーが有効になっている場合は、パッケージ内の少なくとも1つのアプリケーションが以前に使用されていた (つまり、起動または precached) パッケージのみを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="0a092-192">PREVUSED—If any AutoLoad trigger is enabled, load only the packages where at least one application in the package has been previously used (that is, launched or precached).</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="0a092-193">注</span><span class="sxs-lookup"><span data-stu-id="0a092-193">Note</span></span></strong><br/><p><span data-ttu-id="0a092-194">読み取り専用キャッシュ (たとえば、VDI サーバーの実装として) を使用するように App-v クライアントをインストールする場合、 <em> </em> クライアントが読み取り専用キャッシュ内のアプリケーションを更新しないように、autoloadtarget パラメーターを NONE に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-194">When you install the App-V client to use a read-only cache, (for example, as a VDI server implementation), you must set the <em>AUTOLOADTARGET</em> parameter to NONE to prevent the client from trying to update applications in the read-only cache.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="0a092-195">DOTIMEOUTMINUTES</span><span class="sxs-lookup"><span data-stu-id="0a092-195">DOTIMEOUTMINUTES</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-196">29600 (既定)</span><span class="sxs-lookup"><span data-stu-id="0a092-196">29600 (default)</span></span></p>
<p><span data-ttu-id="0a092-197">1– 1439998560 minutes (範囲)</span><span class="sxs-lookup"><span data-stu-id="0a092-197">1–1439998560 minutes (range)</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-198">切断された操作でアプリケーションを使うことができる分数を示します。</span><span class="sxs-lookup"><span data-stu-id="0a092-198">Indicates how many minutes an application may be used in disconnected operation.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="0a092-199">INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="0a092-199">INSTALLDIR</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-200">&lt;>&gt;</span><span class="sxs-lookup"><span data-stu-id="0a092-200">&lt;pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-201">App-v クライアントのインストールディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="0a092-201">Specifies the installation directory of the App-V Client.</span></span></p>
<p><span data-ttu-id="0a092-202">例: INSTALLDIR = &quot; C:\Program の Application Virtualization クライアント&quot;</span><span class="sxs-lookup"><span data-stu-id="0a092-202">Example: INSTALLDIR=&quot;C:\Program Files\Microsoft Application Virtualization Client&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="0a092-203">OPTIN</span><span class="sxs-lookup"><span data-stu-id="0a092-203">OPTIN</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-204">TRUE</span><span class="sxs-lookup"><span data-stu-id="0a092-204">“TRUE”</span></span></p>
<p><span data-ttu-id="0a092-205">“”</span><span class="sxs-lookup"><span data-stu-id="0a092-205">“”</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-206">Microsoft Application Virtualization クライアントコンポーネントは、一般公開の更新プログラムが利用可能になったときに、Microsoft Update を通じてアップグレード可能になります。</span><span class="sxs-lookup"><span data-stu-id="0a092-206">Microsoft Application Virtualization Client components will be upgradable through Microsoft Update when updates are made available to the general public.</span></span> <span data-ttu-id="0a092-207">Windows オペレーティングシステムにインストールされている Microsoft Update エージェントでは、サービスを使用するためにユーザーが明示的にオプトインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-207">The Microsoft Update Agent installed on Windows operating systems requires a user to explicitly opt-in to use the service.</span></span> <span data-ttu-id="0a092-208">このオプトインは、デバイス上のすべてのアプリケーションで1回だけ必要です。</span><span class="sxs-lookup"><span data-stu-id="0a092-208">This opt-in is required only one time for all applications on the device.</span></span> <span data-ttu-id="0a092-209">既に Microsoft Update に登録している場合は、デバイス上の Microsoft Application Virtualization コンポーネントによって自動的にサービスが利用されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-209">If you have already opted into Microsoft Update, the Microsoft Application Virtualization components on the device will automatically take advantage of the service.</span></span></p>
<p><span data-ttu-id="0a092-210">コマンドラインインストールの場合、microsoft update を手動で有効にする必要があるため、Microsoft Update は既定でオプトインされます (以前のアプリケーションで既にデバイスが有効になっている場合を除きます)。</span><span class="sxs-lookup"><span data-stu-id="0a092-210">For command-line installation, use of Microsoft Update is by default opt-out (unless a previous application already enabled the device to be opted in) due to the requirement for manually opting into Microsoft Update.</span></span> <span data-ttu-id="0a092-211">そのため、コマンドラインインストールの場合は、[in in] を明示的に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-211">Therefore, opting in must be explicit for command-line installations.</span></span> <span data-ttu-id="0a092-212">コマンドラインパラメーター <em> OPTIN </em> を TRUE に設定すると、Microsoft Update のオプトインが強制的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-212">Setting the command-line parameter <em>OPTIN</em> to TRUE forces the Microsoft Update opt-in to be set.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="0a092-213">REQUIREのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="0a092-213">REQUIREAUTHORIZATIONIFCACHED</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-214">TRUE</span><span class="sxs-lookup"><span data-stu-id="0a092-214">TRUE</span></span></p>
<p><span data-ttu-id="0a092-215">FALSE</span><span class="sxs-lookup"><span data-stu-id="0a092-215">FALSE</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-216">アプリケーションが既にキャッシュに含まれているかどうかにかかわらず、常に承認が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0a092-216">Indicates whether authorization is always required, whether or not an application is already in cache.</span></span></p>
<p><span data-ttu-id="0a092-217">設定可能な値:</span><span class="sxs-lookup"><span data-stu-id="0a092-217">Possible values:</span></span></p>
<ul>
<li><p><span data-ttu-id="0a092-218">TRUE: アプリケーションは、起動時に常に承認されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-218">TRUE—Application always must be authorized at startup.</span></span> <span data-ttu-id="0a092-219">RTSP ストリームアプリケーションの場合は、ユーザー認証トークンがサーバーに送信され、承認があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-219">For RTSP streamed applications, the user authorization token is sent to the server for authorization.</span></span> <span data-ttu-id="0a092-220">ファイルベースのアプリケーションの場合、ファイル Acl は、ユーザーがアプリケーションにアクセスできるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0a092-220">For file-based applications, file ACLs dictate whether a user may access the application.</span></span></p></li>
<li><p><span data-ttu-id="0a092-221">FALSE —常にサーバーへの接続を試みます。</span><span class="sxs-lookup"><span data-stu-id="0a092-221">FALSE—Always try to connect to the server.</span></span> <span data-ttu-id="0a092-222">サーバーへの接続を確立できない場合でも、クライアントは、以前にキャッシュに読み込まれているアプリケーションを起動することを許可します。</span><span class="sxs-lookup"><span data-stu-id="0a092-222">If a connection to the server cannot be established, the client still allows the user to launch an application that has previously been loaded into cache.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="0a092-223">SWICACHESIZE</span><span class="sxs-lookup"><span data-stu-id="0a092-223">SWICACHESIZE</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-224">キャッシュサイズ (MB)</span><span class="sxs-lookup"><span data-stu-id="0a092-224">Cache size in MB</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-225">クライアントキャッシュのサイズ (mb 単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="0a092-225">Specifies the size in megabytes of the client cache.</span></span> <span data-ttu-id="0a092-226">既定のサイズは 4096 MB で、最大サイズは 1048576 MB (1 TB) です。</span><span class="sxs-lookup"><span data-stu-id="0a092-226">The default size is 4096 MB, and the maximum size is 1,048,576 MB (1 TB).</span></span> <span data-ttu-id="0a092-227">システムはインストール時に利用可能な領域をチェックしますが、スペースは予約されません。</span><span class="sxs-lookup"><span data-stu-id="0a092-227">The system checks for the available space at installation time, but the space is not reserved.</span></span></p>
<p><span data-ttu-id="0a092-228">例: <strong> swicachesize = &quot; 1024&quot;</span><span class="sxs-lookup"><span data-stu-id="0a092-228">Example: <strong>SWICACHESIZE=&quot;1024&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="0a092-229">SWIPUBSVRDISPLAY</span><span class="sxs-lookup"><span data-stu-id="0a092-229">SWIPUBSVRDISPLAY</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-230">表示名</span><span class="sxs-lookup"><span data-stu-id="0a092-230">Display name</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-231">公開サーバーの表示名を指定します。SWIPUBSVRHOST を使用する場合に必要 <em> </em> です。</span><span class="sxs-lookup"><span data-stu-id="0a092-231">Specifies the displayed name of the publishing server; required when <em>SWIPUBSVRHOST</em> is used.</span></span></p>
<p><span data-ttu-id="0a092-232">例: <strong> SWIPUBSVRDISPLAY = &quot; PRODUCTION ENVIRONMENT&quot;</span><span class="sxs-lookup"><span data-stu-id="0a092-232">Example: <strong>SWIPUBSVRDISPLAY=&quot;PRODUCTION ENVIRONMENT&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="0a092-233">SWIPUBSVRTYPE</span><span class="sxs-lookup"><span data-stu-id="0a092-233">SWIPUBSVRTYPE</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-234">[HTTP |RTSP</span><span class="sxs-lookup"><span data-stu-id="0a092-234">[HTTP|RTSP]</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-235">発行サーバーの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="0a092-235">Specifies the publishing server type.</span></span> <span data-ttu-id="0a092-236">既定のサーバーの種類は、Application Virtualization サーバーです。</span><span class="sxs-lookup"><span data-stu-id="0a092-236">The default server type is Application Virtualization Server.</span></span> <span data-ttu-id="0a092-237">セキュリティ保護された <strong> </strong> スイッチは、大文字と小文字を区別しません。</span><span class="sxs-lookup"><span data-stu-id="0a092-237">The <strong>/secure</strong> switch is not case sensitive.</span></span></p>
<ul>
<li><p><span data-ttu-id="0a092-238">HTTP —標準の HTTP サーバー</span><span class="sxs-lookup"><span data-stu-id="0a092-238">HTTP—Standard HTTP Server</span></span></p></li>
<li><p><span data-ttu-id="0a092-239">HTTP <strong> /secure </strong> —強化されたセキュリティ HTTP サーバー</span><span class="sxs-lookup"><span data-stu-id="0a092-239">HTTP <strong>/secure</strong>—Enhanced Security HTTP Server</span></span></p></li>
<li><p><span data-ttu-id="0a092-240">RTSP — Application Virtualization Server</span><span class="sxs-lookup"><span data-stu-id="0a092-240">RTSP—Application Virtualization Server</span></span></p></li>
<li><p><span data-ttu-id="0a092-241">RTSP <strong> /secure </strong> —強化されたセキュリティアプリケーションの仮想化サーバー</span><span class="sxs-lookup"><span data-stu-id="0a092-241">RTSP <strong>/secure</strong>—Enhanced Security Application Virtualization Server</span></span></p></li>
</ul>
<p><span data-ttu-id="0a092-242">例: <strong> SWIPUBSVRTYPE = &quot; HTTP/secure&quot;</span><span class="sxs-lookup"><span data-stu-id="0a092-242">Example: <strong>SWIPUBSVRTYPE=&quot;HTTP /secure&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="0a092-243">SWIPUBSVRHOST</span><span class="sxs-lookup"><span data-stu-id="0a092-243">SWIPUBSVRHOST</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-244">IP address | host name</span><span class="sxs-lookup"><span data-stu-id="0a092-244">IP address|host name</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-245">アプリケーションの仮想化サーバーの IP アドレス、またはサーバー&#39;の IP アドレスに解決されるサーバーのホスト名のいずれかを指定します。SWIPUBSVRDISPLAY を使用する場合に必要 <em> </em> です。</span><span class="sxs-lookup"><span data-stu-id="0a092-245">Specifies either the IP address of the Application Virtualization Server or a host name of the server that resolves into the server&#39;s IP address; required when <em>SWIPUBSVRDISPLAY</em> is used.</span></span></p>
<p><span data-ttu-id="0a092-246">例: <strong> SWIPUBSVRHOST = &quot; SERVER01&quot;</span><span class="sxs-lookup"><span data-stu-id="0a092-246">Example: <strong>SWIPUBSVRHOST=&quot;SERVER01&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="0a092-247">SWIPUBSVRPORT</span><span class="sxs-lookup"><span data-stu-id="0a092-247">SWIPUBSVRPORT</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-248">ポート番号</span><span class="sxs-lookup"><span data-stu-id="0a092-248">Port number</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-249">この Application Virtualization サーバーがクライアントからの要求をリッスンするために使用する論理ポートを指定します (既定値 = 554)。</span><span class="sxs-lookup"><span data-stu-id="0a092-249">Specifies the logical port that is used by this Application Virtualization Server to listen for requests from the client (default = 554).</span></span></p>
<ul>
<li><p><span data-ttu-id="0a092-250">標準 HTTP サーバー (既定 = 80)</span><span class="sxs-lookup"><span data-stu-id="0a092-250">Standard HTTP server—Default = 80.</span></span></p></li>
<li><p><span data-ttu-id="0a092-251">強化されたセキュリティ HTTP サーバー (既定 = 443)。</span><span class="sxs-lookup"><span data-stu-id="0a092-251">Enhanced Security HTTP Server—Default = 443.</span></span></p></li>
<li><p><span data-ttu-id="0a092-252">Application Virtualization Server (既定 = 554)</span><span class="sxs-lookup"><span data-stu-id="0a092-252">Application Virtualization Server—Default = 554.</span></span></p></li>
<li><p><span data-ttu-id="0a092-253">強化されたセキュリティアプリケーション仮想化サーバー-既定値は322です。</span><span class="sxs-lookup"><span data-stu-id="0a092-253">Enhanced Security Application Virtualization Server—Default = 322.</span></span></p></li>
</ul>
<p><span data-ttu-id="0a092-254">例: <strong> SWIPUBSVRPORT = &quot; 443&quot;</span><span class="sxs-lookup"><span data-stu-id="0a092-254">Example: <strong>SWIPUBSVRPORT=&quot;443&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="0a092-255">SWIPUBSVRPATH</span><span class="sxs-lookup"><span data-stu-id="0a092-255">SWIPUBSVRPATH</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-256">パス名</span><span class="sxs-lookup"><span data-stu-id="0a092-256">Path name</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-257">ファイルの種類の関連付けを定義するファイルの発行サーバー上の場所 (既定値 =/) を指定します。<em>SWIPUBSVRTYPE </em> パラメーターの値が HTTP のときに必要です。</span><span class="sxs-lookup"><span data-stu-id="0a092-257">Specifies the location on the publishing server of the file that defines file type associations (default = /); required when the <em>SWIPUBSVRTYPE</em> parameter value is HTTP.</span></span></p>
<p><span data-ttu-id="0a092-258">例: <strong> SWIPUBSVRPATH = &quot; /AppVirt/appsntypes.xml&quot;</span><span class="sxs-lookup"><span data-stu-id="0a092-258">Example: <strong>SWIPUBSVRPATH=&quot;/AppVirt/appsntypes.xml&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="0a092-259">SWIPUBSVRREFRESH</span><span class="sxs-lookup"><span data-stu-id="0a092-259">SWIPUBSVRREFRESH</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-260">[オン |ない</span><span class="sxs-lookup"><span data-stu-id="0a092-260">[ON|OFF]</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-261">ユーザーがクライアントにログインしたときに、ファイルの種類の関連付けとアプリケーションの公開サーバーに自動的にクエリを行うかどうかを指定します (既定値 = ON)。</span><span class="sxs-lookup"><span data-stu-id="0a092-261">Specifies whether the client automatically queries the publishing server for file type associations and applications when a user logs in to the client (default = ON).</span></span></p>
<p><span data-ttu-id="0a092-262">例: <strong> SWIPUBSVRREFRESH = &quot; off&quot;</span><span class="sxs-lookup"><span data-stu-id="0a092-262">Example: <strong>SWIPUBSVRREFRESH=&quot;off&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="0a092-263">SWIGLOBALDATA</span><span class="sxs-lookup"><span data-stu-id="0a092-263">SWIGLOBALDATA</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-264">グローバルデータディレクトリ</span><span class="sxs-lookup"><span data-stu-id="0a092-264">Global data directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-265">特定のユーザーに固有ではないデータを格納するディレクトリを指定します (既定 = C:\documents and and Settings\All Users\Documents)。</span><span class="sxs-lookup"><span data-stu-id="0a092-265">Specifies the directory where data will be stored that is not specific to particular users (default = C:\Documents and Settings\All Users\Documents).</span></span></p>
<p><span data-ttu-id="0a092-266">例: <strong> SWIGLOBALDATA = &quot; D:\Microsoft Application Virtualization Client\Global&quot;</span><span class="sxs-lookup"><span data-stu-id="0a092-266">Example: <strong>SWIGLOBALDATA=&quot;D:\Microsoft Application Virtualization Client\Global&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="0a092-267">SWIUSERDATA</span><span class="sxs-lookup"><span data-stu-id="0a092-267">SWIUSERDATA</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-268">ユーザーデータディレクトリ</span><span class="sxs-lookup"><span data-stu-id="0a092-268">User data directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-269">特定のユーザーに固有のデータを格納するディレクトリを指定します (既定値 =% APPDATA%)。</span><span class="sxs-lookup"><span data-stu-id="0a092-269">Specifies the directory where data will be stored that is specific to particular users (default = %APPDATA%).</span></span></p>
<p><span data-ttu-id="0a092-270">例: <strong> SWIUSERDATA = &quot; H:\Windows\Microsoft Application Virtualization クライアント&quot;</span><span class="sxs-lookup"><span data-stu-id="0a092-270">Example: <strong>SWIUSERDATA=&quot;H:\Windows\Microsoft Application Virtualization Client&quot;</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="0a092-271">SWIFSDRIVE</span><span class="sxs-lookup"><span data-stu-id="0a092-271">SWIFSDRIVE</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-272">優先ドライブ文字</span><span class="sxs-lookup"><span data-stu-id="0a092-272">Preferred drive letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-273">仮想ドライブ用に選択したドライブ文字に対応します。</span><span class="sxs-lookup"><span data-stu-id="0a092-273">Corresponds to the drive letter that you selected for the virtual drive.</span></span></p>
<p><span data-ttu-id="0a092-274">例: <strong> SWIFSDRIVE = &quot; S&quot;</span><span class="sxs-lookup"><span data-stu-id="0a092-274">Example: <strong>SWIFSDRIVE=&quot;S&quot;</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="0a092-275">SYSTEMEVENTLOGLEVEL</span><span class="sxs-lookup"><span data-stu-id="0a092-275">SYSTEMEVENTLOGLEVEL</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-276">0 ~ 4</span><span class="sxs-lookup"><span data-stu-id="0a092-276">0–4</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-277">ログメッセージが NT イベントログに書き込まれるログレベルを示します。</span><span class="sxs-lookup"><span data-stu-id="0a092-277">Indicates the logging level at which log messages are written to the NT event Log.</span></span> <span data-ttu-id="0a092-278">この値は、ログに記録されるもののしきい値を示します。つまり、その値と同じか、またはそれより小さいすべてのものがログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-278">The value indicates a threshold of what is logged—that is, everything equal to or less than that value is logged.</span></span> <span data-ttu-id="0a092-279">たとえば、値 0x3 (警告) の場合は、警告 (0x3)、エラー (0x2)、および重大なエラー (0x1) が記録されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-279">For example, a value of 0x3 (Warning) indicates that Warnings (0x3), Errors (0x2), and Critical Errors (0x1) are logged.</span></span></p>
<p><span data-ttu-id="0a092-280">設定可能な値:</span><span class="sxs-lookup"><span data-stu-id="0a092-280">Possible values:</span></span></p>
<ul>
<li><p><span data-ttu-id="0a092-281">0 = = なし</span><span class="sxs-lookup"><span data-stu-id="0a092-281">0 == None</span></span></p></li>
<li><p><span data-ttu-id="0a092-282">1 = Critical</span><span class="sxs-lookup"><span data-stu-id="0a092-282">1 == Critical</span></span></p></li>
<li><p><span data-ttu-id="0a092-283">2 = = エラー</span><span class="sxs-lookup"><span data-stu-id="0a092-283">2 == Error</span></span></p></li>
<li><p><span data-ttu-id="0a092-284">3 = = 警告</span><span class="sxs-lookup"><span data-stu-id="0a092-284">3 == Warning</span></span></p></li>
<li><p><span data-ttu-id="0a092-285">4 = = 情報</span><span class="sxs-lookup"><span data-stu-id="0a092-285">4 == Information</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><em><span data-ttu-id="0a092-286">MINFREESPACEMB</span><span class="sxs-lookup"><span data-stu-id="0a092-286">MINFREESPACEMB</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-287">MB</span><span class="sxs-lookup"><span data-stu-id="0a092-287">In MB</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-288">キャッシュサイズを増やすためにホストで使用できる空き領域の量 (mb 単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="0a092-288">Specifies the amount of free space (in megabytes) that must be available on the host before the cache size can increase.</span></span> <span data-ttu-id="0a092-289">次の例では、キャッシュのサイズを増加させる前に、ディスク上に少なくとも 5 GB の空き領域を確保するようにクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="0a092-289">The following example would configure the client to ensure at least 5 GB of free space on the disk before allowing the size of the cache to increase.</span></span> <span data-ttu-id="0a092-290">既定では、インストール時にディスク上で使用できる 5000 MB の空き領域があります。</span><span class="sxs-lookup"><span data-stu-id="0a092-290">The default is 5000 MB of free space available on disk at installation time.</span></span></p>
<p><span data-ttu-id="0a092-291">例: <strong> MINFREESPACEMB = &quot; 5000 &quot; (5 GB)</span><span class="sxs-lookup"><span data-stu-id="0a092-291">Example: <strong>MINFREESPACEMB =&quot;5000&quot; (5 GB)</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em><span data-ttu-id="0a092-292">KEEPCURRENTSETTINGS</span><span class="sxs-lookup"><span data-stu-id="0a092-292">KEEPCURRENTSETTINGS</span></span></em></p></td>
<td align="left"><p><span data-ttu-id="0a092-293">[0 | 1]</span><span class="sxs-lookup"><span data-stu-id="0a092-293">[0|1]</span></span></p></td>
<td align="left"><p><span data-ttu-id="0a092-294">クライアントを展開する前に (グループポリシーを使用するなど)、レジストリ設定を適用したときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-294">Used when you have applied registry settings prior to deploying a client—for example, by using Group Policy.</span></span> <span data-ttu-id="0a092-295">クライアントが展開されたら、レジストリ設定を上書きしないように、このパラメーターを値1に設定します。</span><span class="sxs-lookup"><span data-stu-id="0a092-295">When a client is deployed, set this parameter to a value of 1 so that it will not overwrite the registry settings.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="0a092-296">重要</span><span class="sxs-lookup"><span data-stu-id="0a092-296">Important</span></span></strong><br/><p><span data-ttu-id="0a092-297">値1に設定すると、次のクライアントインストーラーコマンドラインパラメーターが無視されます。</span><span class="sxs-lookup"><span data-stu-id="0a092-297">If set to a value of 1, the following client installer command-line parameters are ignored:</span></span></p>
<p><strong><span data-ttu-id="0a092-298">SWICACHESIZE </strong> 、 <strong> MINFREESPACEMB </strong> 、 <strong> ALLOWINDEPENDENTFILESTREAMING </strong> 、 <strong> APPLICATIONSOURCEROOT </strong> 、 <strong> ICONSOURCEROOT </strong> 、 <strong> osdsourceroot </strong> 、 <strong> SYSTEMEVENTLOGLEVEL </strong> 、 <strong> SWIGLOBALDATA </strong> 、 <strong> dotimeoutminutes </strong> 、 <strong> SWIFSDRIVE </strong> 、 <strong> autoloadtarget </strong> 、 <strong> autoloadtarget </strong> 、および <strong> SWIUSERDATA </strong> 。</span><span class="sxs-lookup"><span data-stu-id="0a092-298">SWICACHESIZE</strong>, <strong>MINFREESPACEMB</strong>, <strong>ALLOWINDEPENDENTFILESTREAMING</strong>, <strong>APPLICATIONSOURCEROOT</strong>, <strong>ICONSOURCEROOT</strong>, <strong>OSDSOURCEROOT</strong>, <strong>SYSTEMEVENTLOGLEVEL</strong>, <strong>SWIGLOBALDATA</strong>, <strong>DOTIMEOUTMINUTES</strong>, <strong>SWIFSDRIVE</strong>, <strong>AUTOLOADTARGET</strong>, <strong>AUTOLOADTRIGGERS</strong>, and <strong>SWIUSERDATA</strong>.</span></span></p>
<p><span data-ttu-id="0a092-299">これらの値をインストール後に設定する方法について詳しくは、Application Virtualization (App-v) Operations Guide () のコマンドラインを使用して、App-v クライアントのレジストリ設定を構成する方法をご覧ください <a href="https://go.microsoft.com/fwlink/?LinkId=122939" data-raw-source="[https://go.microsoft.com/fwlink/?LinkId=122939](https://go.microsoft.com/fwlink/?LinkId=122939)"> https://go.microsoft.com/fwlink/?LinkId=122939 </a> 。</span><span class="sxs-lookup"><span data-stu-id="0a092-299">For further information about setting these values after installation, see “How to Configure the App-V Client Registry Settings by Using the Command Line” in the Application Virtualization (App-V) Operations Guide (<a href="https://go.microsoft.com/fwlink/?LinkId=122939" data-raw-source="[https://go.microsoft.com/fwlink/?LinkId=122939](https://go.microsoft.com/fwlink/?LinkId=122939)">https://go.microsoft.com/fwlink/?LinkId=122939</a>).</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="0a092-300">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0a092-300">Related topics</span></span>


[<span data-ttu-id="0a092-301">Application Virtualization Client を手動でインストールする方法</span><span class="sxs-lookup"><span data-stu-id="0a092-301">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="0a092-302">Application Virtualization Client をアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="0a092-302">How to Upgrade the Application Virtualization Client</span></span>](how-to-upgrade-the-application-virtualization-client.md)

[<span data-ttu-id="0a092-303">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="0a092-303">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)









