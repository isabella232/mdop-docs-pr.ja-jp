---
title: SFTTRAY コマンド リファレンス
description: SFTTRAY コマンド リファレンス
author: dansimp
ms.assetid: 6fa3a939-b047-4d6c-bd1d-dfb93e065eb2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45a664b91ff7edd5f8536f035417cc3b0f52d7ca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815354"
---
# <span data-ttu-id="bb5dd-103">SFTTRAY コマンド リファレンス</span><span class="sxs-lookup"><span data-stu-id="bb5dd-103">SFTTRAY Command Reference</span></span>


<span data-ttu-id="bb5dd-104">Microsoft Application Virtualization (App-v) クライアントトレイアプリケーションである sfttray.exe は、通常の使用時にユーザーが操作する app-v クライアントのメインユーザーインターフェイス要素です。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-104">The Microsoft Application Virtualization (App-V) Client Tray application, sfttray.exe, is the main user interface element of the App-V Client that users will interact with during normal use.</span></span> <span data-ttu-id="bb5dd-105">このプログラムは、すべての仮想アプリケーションのストリーミングと開始を制御し、通知領域に表示されるアイコンを右クリックしてクライアント機能のメニューを表示することによってアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-105">This program controls the streaming and starting of all virtual applications and is accessed by right-clicking the icon displayed in the notification area to display the menu of client functions.</span></span> <span data-ttu-id="bb5dd-106">メニューを使用すると、ユーザーはアプリケーションの読み込み、発行の更新の開始、要求のキャンセル、またはクライアントのオフラインモードへの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-106">The menu enables the user to load applications, start a publishing refresh, cancel a request, or change the client to offline mode.</span></span> <span data-ttu-id="bb5dd-107">ユーザーは、[**終了**] をクリックして、Application Virtualization クライアントトレイアプリケーションとアクティブなすべてのアプリケーションを終了することもできます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-107">The user can also close the Application Virtualization Client Tray application and all active applications by clicking **Exit**.</span></span>

<span data-ttu-id="bb5dd-108">既定では、仮想アプリケーションが開始されるたびにアイコンが表示されますが、この動作は、SFTTRAY コマンドを使って制御できます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-108">By default, the icon is displayed whenever a virtual application is started, although you can control this behavior by using SFTTRAY commands.</span></span> <span data-ttu-id="bb5dd-109">Application Virtualization クライアントトレイアプリケーションには、起動された各アプリケーションの進行状況バーと、アクティブなアプリケーションに関する状態メッセージも表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-109">The Application Virtualization Client Tray application also displays a progress bar for each application that is started, as well as status messages about active applications.</span></span> <span data-ttu-id="bb5dd-110">進行状況バーをクリックすると、アプリケーションの読み込みまたは開始をキャンセルできることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-110">Clicking the progress bar displays a message that allows you to cancel the loading or starting of an application.</span></span>

## <span data-ttu-id="bb5dd-111">SFTTRAY コマンド</span><span class="sxs-lookup"><span data-stu-id="bb5dd-111">SFTTRAY Commands</span></span>


<span data-ttu-id="bb5dd-112">コマンドウィンドウから次のコマンドを実行すると、コマンドとコマンドラインスイッチの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-112">The list of commands and command-line switches can be displayed by running the following command from a command window.</span></span>

**<span data-ttu-id="bb5dd-113">注</span><span class="sxs-lookup"><span data-stu-id="bb5dd-113">Note</span></span>**  
<span data-ttu-id="bb5dd-114">アプリケーションの仮想化クライアントのトレイインスタンスは、ユーザーコンテキストごとに1つしかありません。そのため、新しい SFTTRAY コマンドを開始すると、既に実行されているプログラムに渡されます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-114">There is only one Application Virtualization Client Tray instance for each user context, so if you start a new SFTTRAY command, it will be passed to the program that is already running.</span></span>



`Sfttray.exe /?`

### <span data-ttu-id="bb5dd-115">コマンドの使用方法</span><span class="sxs-lookup"><span data-stu-id="bb5dd-115">Command Usage</span></span>

`Sfttray.exe [/HIDE | /SHOW]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] [/EXE alternate-exe] /LAUNCH app [args]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LOAD app [/SFTFILE sft]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LOADALL`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /REFRESHALL`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LAUNCHRESULT <UNIQUE ID>  /LAUNCH app [args]`

`Sfttray.exe /EXIT`

### <span data-ttu-id="bb5dd-116">コマンドラインスイッチ</span><span class="sxs-lookup"><span data-stu-id="bb5dd-116">Command-Line Switches</span></span>

<span data-ttu-id="bb5dd-117">SFTTRAY コマンドラインスイッチについては、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-117">The SFTTRAY command-line switches are described in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bb5dd-118">スイッチ</span><span class="sxs-lookup"><span data-stu-id="bb5dd-118">Switch</span></span></th>
<th align="left"><span data-ttu-id="bb5dd-119">説明</span><span class="sxs-lookup"><span data-stu-id="bb5dd-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb5dd-120">/非表示</span><span class="sxs-lookup"><span data-stu-id="bb5dd-120">/HIDE</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb5dd-121">Windows 通知領域の SFTTRAY アイコンを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-121">Hides the SFTTRAY icon in the Windows notification area.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb5dd-122">/SHOW</span><span class="sxs-lookup"><span data-stu-id="bb5dd-122">/SHOW</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb5dd-123">Windows 通知領域に SFTTRAY アイコンを表示します。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-123">Displays the SFTTRAY icon in the Windows notification area.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb5dd-124">/QUIET</span><span class="sxs-lookup"><span data-stu-id="bb5dd-124">/QUIET</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb5dd-125">ユーザーの確認が必要なメッセージボックスの表示を回避して、無人使用をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-125">Supports unattended usage by preventing errors from displaying message boxes that require user acknowledgement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb5dd-126">/Exe &lt; 代替 exe&gt;</span><span class="sxs-lookup"><span data-stu-id="bb5dd-126">/EXE &lt;alternate-exe&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb5dd-127">/LAUNCH と共に使用して、OSD で指定されたターゲットファイルの代わりに仮想アプリケーションが開始される場合に、実行可能プログラムを仮想環境で開始することを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-127">Used with /LAUNCH to specify that an executable program is to be started in the virtual environment when a virtual application is started in place of the target file specified in the OSD.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="bb5dd-128">注</span><span class="sxs-lookup"><span data-stu-id="bb5dd-128">Note</span></span></strong><br/><p><span data-ttu-id="bb5dd-129">たとえば、"SFTTRAY.EXE/EXE REGEDIT.EXE/LAUNCH app" を使って、 &lt; &gt; アプリケーションが実行されている仮想環境のレジストリを調べることができます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-129">For example, use “SFTTRAY.EXE /EXE REGEDIT.EXE /LAUNCH &lt;app&gt;” to enable you to examine the registry of the virtual environment in which the application is running.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb5dd-130">/LAUNCH &lt; アプリ &gt; [ &lt; args &gt; ]</span><span class="sxs-lookup"><span data-stu-id="bb5dd-130">/LAUNCH &lt;app&gt; [&lt;args&gt;]</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb5dd-131">仮想アプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-131">Starts a virtual application.</span></span> <span data-ttu-id="bb5dd-132">アプリケーションの名前とバージョン、または OSD ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-132">Specify the name and version of an application or the path to an OSD file.</span></span> <span data-ttu-id="bb5dd-133">必要に応じて、コマンドライン引数を仮想アプリケーションに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-133">Optionally, command-line arguments can be passed to the virtual application.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="bb5dd-134">注</span><span class="sxs-lookup"><span data-stu-id="bb5dd-134">Note</span></span></strong><br/><p><span data-ttu-id="bb5dd-135">使用可能な仮想アプリケーションの名前とバージョンの一覧を取得するには、"SFTMIME.EXE/QUERY OBJ: APP/SHORT" というコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-135">Use the command “SFTMIME.EXE /QUERY OBJ:APP /SHORT” to obtain a list of the names and versions of available virtual applications.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb5dd-136">/読み込み</span><span class="sxs-lookup"><span data-stu-id="bb5dd-136">/LOAD</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb5dd-137">仮想アプリケーションを読み込むか、インポートします。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-137">Loads or imports a virtual application.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb5dd-138">すべて loadall</span><span class="sxs-lookup"><span data-stu-id="bb5dd-138">/LOADALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb5dd-139">すべてのアプリケーションをキャッシュに読み込みます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-139">Loads all applications into cache.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb5dd-140">/REFRESHALL</span><span class="sxs-lookup"><span data-stu-id="bb5dd-140">/REFRESHALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb5dd-141">すべてのアプリケーションの公開更新を開始します。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-141">Starts a publishing refresh for all applications.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb5dd-142">/LAUNCHRESULT の &lt; 固有 ID&gt;</span><span class="sxs-lookup"><span data-stu-id="bb5dd-142">/LAUNCHRESULT &lt;UNIQUE ID&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb5dd-143">グローバルイベントと、固有の ID の指定されたルート名に基づくメモリマップトファイルを使用して sfttray.exe を起動するプロセスに対して、起動結果コードを返します。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-143">Returns the launch result code to the process that launches sfttray.exe by using a global event and a memory mapped file that are based on the specified root name for the UNIQUE ID.¹</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bb5dd-144">/SFTFILE &lt; sft&gt;</span><span class="sxs-lookup"><span data-stu-id="bb5dd-144">/SFTFILE &lt;sft&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb5dd-145">アプリケーションの SFT ファイルへのパスを指定するために、/LOAD と共にオプションのスイッチを使用します。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-145">Optional switch used with /LOAD to specify the path to the application’s SFT file.</span></span> <span data-ttu-id="bb5dd-146">指定すると、アプリは読み込まれずにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-146">If specified, the application is imported rather than loaded.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bb5dd-147">/終了</span><span class="sxs-lookup"><span data-stu-id="bb5dd-147">/EXIT</span></span></p></td>
<td align="left"><p><span data-ttu-id="bb5dd-148">SFTTRAY プログラムとすべてのアクティブな仮想アプリケーションを閉じ、Windows 通知領域からアイコンを削除します。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-148">Closes the SFTTRAY program and all active virtual applications and removes the icon from the Windows notification area.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="bb5dd-149">注</span><span class="sxs-lookup"><span data-stu-id="bb5dd-149">Note</span></span>**  
<span data-ttu-id="bb5dd-150">¹ */launchresult*コマンドラインパラメーターは、グローバルイベントのルート名を指定するために sfttray.exe を起動するための手段を提供します。また、プロセスに起動結果コードを返すために使用されるメモリマップファイルが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-150">¹ The */LAUNCHRESULT* command line parameter provides a means for the process that launches sfttray.exe to specify the root name for a global event and a memory mapped file that are used to return the launch result code to the process.</span></span> <span data-ttu-id="bb5dd-151">仮想環境内で起動プロセスが呼び出されたときに、イベント名が仮想化されないようにするには、一意の識別子の名前を "SFT-" で開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-151">The unique identifier name should start with “SFT-” to prevent the event name from getting virtualized when the launching process is invoked within a virtual environment.</span></span> <span data-ttu-id="bb5dd-152">メモリマップ領域は、64ビットのサイズになります。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-152">The memory mapped region will be 64 bits in size.</span></span>

<span data-ttu-id="bb5dd-153">このパラメーターを使うには、"一意の id-result \ _event" という名前のイベントを作成します。このイベントには、"一意の id- &lt; &gt; result \ _value" という名前のメモリマップファイル &lt; と、必要に応じて &gt; "一意の &lt; id &gt; -shutdown \ _event sfttray.exe" という名前のイベントが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-153">To use this parameter, the launching process creates an event with the name “&lt;UNIQUE ID&gt;-result\_event”, a memory mapped file with the name “&lt;UNIQUE ID&gt;-result\_value”, and optionally an event with the name “&lt;UNIQUE ID&gt;-shutdown\_event”, and then the launching process launches sfttray.exe and waits on the event to be signaled.</span></span> <span data-ttu-id="bb5dd-154">イベント " &lt; 一意 &gt; の ID-result \ _event" がシグナル状態になると、起動プロセスで、メモリマップ領域から64ビットのリターンコードが取得されます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-154">After the event “&lt;UNIQUE ID&gt;-result\_event” is signaled, the launching process retrieves the 64-bit return code from the memory mapped region.</span></span>

<span data-ttu-id="bb5dd-155">&lt; &gt; 仮想アプリケーションの終了時に、"一意の ID-shutdown \ _event" という省略可能なイベントが発生すると、sfttray.exe が開き、イベントが通知されます。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-155">If the optional event “&lt;UNIQUE ID&gt;-shutdown\_event” exists when the virtual application exits, sfttray.exe opens and signals the event.</span></span> <span data-ttu-id="bb5dd-156">起動プロセスは、仮想アプリケーションが終了するタイミングを判断する必要がある場合に、このシャットダウンイベントを待機します。</span><span class="sxs-lookup"><span data-stu-id="bb5dd-156">The launching process waits on this shutdown event if it needs to determine when the virtual application exits.</span></span>











