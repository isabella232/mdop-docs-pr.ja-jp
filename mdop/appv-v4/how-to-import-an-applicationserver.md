---
title: アプリケーションをインポートする方法
description: アプリケーションをインポートする方法
author: dansimp
ms.assetid: ab40acad-1025-478d-8e13-0e1ff1bd37e4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d9cd6d065ca28b5d856acdae7d10a1280105e9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817404"
---
# <span data-ttu-id="60934-103">アプリケーションをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="60934-103">How to Import an Application</span></span>


<span data-ttu-id="60934-104">通常は、アプリケーションをインポートして、アプリケーションの仮想化管理サーバーからストリーミングできるようにします。</span><span class="sxs-lookup"><span data-stu-id="60934-104">Typically, you import applications to make them available to stream from an Application Virtualization Management Server.</span></span> <span data-ttu-id="60934-105">アプリケーションを手動で追加することもできますが、そのためには、アプリケーションに関する詳細な情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="60934-105">You can also add an application manually, but you must provide precise, detailed information about the application to do so.</span></span> <span data-ttu-id="60934-106">詳細については、「[手動でアプリケーションを追加する方法](how-to-manually-add-an-application.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="60934-106">For more information, see [How to Manually Add an Application](how-to-manually-add-an-application.md).</span></span>

<span data-ttu-id="60934-107">**注** アプリケーションをインポートするには、シーケンシャルオープンソフトウェア記述子 (OSD) ファイルまたはその Sequencer プロジェクト (SPRJ) ファイルがサーバーで利用できる状態になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="60934-107">**Note** To import an application, you must have its sequenced Open Software Descriptor (OSD) file or its Sequencer Project (SPRJ) file available on the server.</span></span>

 

<span data-ttu-id="60934-108">アプリケーションをインポートするときは、[**システムオプション**] ダイアログの **[全般**] タブにある [**既定のコンテンツパス**] フィールドにサーバーが設定されていることを確認する必要があります (このプロパティは、App-v server 本体の**application Virtualization System**ノードを右クリックするとアクセスできます)。</span><span class="sxs-lookup"><span data-stu-id="60934-108">When importing an application, you should make sure the server is configured with a value in the **Default Content Path** field on the **General** tab of the **System Options** dialog (accessible by right-clicking the **Application Virtualization System** node in the App-V Server Console).</span></span> <span data-ttu-id="60934-109">既定のコンテンツパスの値は、アプリケーションをインポートする場所を定義するもので、インポートプロセス時には、SFT ファイルとアイコンのショートカットの OSD ファイルで定義されたパスを変更するためにこの値を使用します。</span><span class="sxs-lookup"><span data-stu-id="60934-109">The default content path value defines where the applications will be imported, and during the import process, this value is used to modify the paths defined in the OSD file for the SFT file and for the icon shortcuts.</span></span> <span data-ttu-id="60934-110">OSD ファイルの場合、SFT ファイルのパスは CODEBASE HREF エントリで指定され、アイコンのパスはショートカットエントリで指定されます。</span><span class="sxs-lookup"><span data-stu-id="60934-110">In the OSD file, the path for the SFT file is specified in the CODEBASE HREF entry and the path for the icons is specified in the SHORTCUTS entry.</span></span>

<span data-ttu-id="60934-111">インポートプロセス中には、OSD ファイルの2つのパスで指定された port、server、および (存在する場合) が、既定のコンテンツパスの値に置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="60934-111">During the import process, the protocol, server, and, if present, port specified in these two paths in the OSD file will be replaced with the value from the default content path.</span></span> <span data-ttu-id="60934-112">次の表では、インポートパスの影響について例を示します。</span><span class="sxs-lookup"><span data-stu-id="60934-112">The following table provides an example of how the import path will be affected.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="60934-113">既定のコンテンツパス</span><span class="sxs-lookup"><span data-stu-id="60934-113">Default Content Path</span></span></th>
<th align="left"><span data-ttu-id="60934-114">OSD ファイルのコードベース HREF</span><span class="sxs-lookup"><span data-stu-id="60934-114">OSD File CODEBASE HREF</span></span></th>
<th align="left"><span data-ttu-id="60934-115">結果の値</span><span class="sxs-lookup"><span data-stu-id="60934-115">Resulting Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="60934-116">\ \ ターミナルコンテンツ &lt; /p&gt;</span><span class="sxs-lookup"><span data-stu-id="60934-116">\server\content&lt;/p&gt;</span></span></td>
<td align="left"><p><a href="http://WebServer/myFolder/package.sft" data-raw-source="http://WebServer/myFolder/package.sft">http://WebServer/myFolder/package.sft</a></p></td>
<td align="left"><p><span data-ttu-id="60934-117">\server\content\myFolder\package.sft</span><span class="sxs-lookup"><span data-stu-id="60934-117">\server\content\myFolder\package.sft</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="60934-118">アプリケーションをインポートするには</span><span class="sxs-lookup"><span data-stu-id="60934-118">To import an application</span></span>**

1.  <span data-ttu-id="60934-119">左側のウィンドウで [**アプリケーション**] ノードを右クリックし、[**アプリケーションのインポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="60934-119">Right-click the **Applications** node in the left pane, and choose **Import Applications**.</span></span>

2.  <span data-ttu-id="60934-120">[**開く**] ダイアログボックスで、アプリケーションの SPRJ または OSD ファイルに移動します。</span><span class="sxs-lookup"><span data-stu-id="60934-120">In the **Open** dialog box, navigate to the application's SPRJ or OSD file.</span></span> <span data-ttu-id="60934-121">ファイルを強調表示し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60934-121">Highlight the file and click **Open**.</span></span>

3.  <span data-ttu-id="60934-122">**新しいアプリケーションウィザード**で、ストリーミングするアプリケーションに対し**て [有効**] ボックスがオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="60934-122">In the **New Application Wizard**, be sure the **Enabled** box is selected for applications you want to stream.</span></span> <span data-ttu-id="60934-123">また、説明を入力して、サーバーとファイルのパスを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="60934-123">There you can also enter a description and verify the server and file paths.</span></span> <span data-ttu-id="60934-124">また、ライセンスおよびサーバーグループを設定してある場合は、それらを選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="60934-124">Also, if you have set up license and server groups, you can select those.</span></span>

4.  <span data-ttu-id="60934-125">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60934-125">Click **Next**.</span></span>

5.  <span data-ttu-id="60934-126">[公開された**ショートカット**] 画面で、クライアントコンピューターにアプリケーションのショートカットを表示する場所のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="60934-126">On the **Published Shortcuts** screen, select the boxes for the locations where you would like the application shortcuts to appear on the client computers.</span></span>

6.  <span data-ttu-id="60934-127">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60934-127">Click **Next**.</span></span>

7.  <span data-ttu-id="60934-128">[**ファイルの関連付け**] 画面で、このアプリケーションに新しいファイルの関連付けを追加できます。</span><span class="sxs-lookup"><span data-stu-id="60934-128">In the **File Associations** screen, you can add new file associations to this application.</span></span> <span data-ttu-id="60934-129">そのためには、[**追加**] をクリックし、拡張機能 (前のドットは不要) を入力して、説明を入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60934-129">To do so, click **Add**, enter the extension (without a preceding dot), enter a description, and click **OK**.</span></span>

    <span data-ttu-id="60934-130">**注** Sequencer 4.0 でシーケンス処理されたアプリケーションは、管理コンソールを使用してインポートまたは作成するときに、[**ファイルの関連付け**] ダイアログボックスを作成します。</span><span class="sxs-lookup"><span data-stu-id="60934-130">**Note** Applications sequenced with Sequencer 4.0 populate the **File Associations** dialog box when you import or create them through the management console.</span></span> <span data-ttu-id="60934-131">以前のバージョンの Sequencer パッケージを使用したアプリケーションは実行されません。</span><span class="sxs-lookup"><span data-stu-id="60934-131">Applications with previous Sequencer version packages do not.</span></span>

     

8.  <span data-ttu-id="60934-132">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60934-132">Click **Next**.</span></span>

9.  <span data-ttu-id="60934-133">[**アクセス許可**] 画面で、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60934-133">In the **Access Permissions** screen, click **Add**.</span></span>

10. <span data-ttu-id="60934-134">**[グループの選択**] ダイアログボックスに入力します。</span><span class="sxs-lookup"><span data-stu-id="60934-134">Complete the **Select Groups** dialog box.</span></span> <span data-ttu-id="60934-135">完了したら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60934-135">When you finish, click **OK**.</span></span>

11. <span data-ttu-id="60934-136">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="60934-136">Click **Next**.</span></span>

12. <span data-ttu-id="60934-137">[**概要**] 画面では、インポート設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="60934-137">On the **Summary** screen, you can review the import settings.</span></span> <span data-ttu-id="60934-138">[**完了**] をクリックするか、[**戻る**] をクリックしてインポートを変更するか、[**キャンセル**] をクリックしてインポートをキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="60934-138">Click **Finish**, or click **Back** to change the import or click **Cancel** to cancel the import.</span></span>

## <span data-ttu-id="60934-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="60934-139">Related topics</span></span>


[<span data-ttu-id="60934-140">サーバー管理コンソールでアプリケーション グループを管理する方法</span><span class="sxs-lookup"><span data-stu-id="60934-140">How to Manage Application Groups in the Server Management Console</span></span>](how-to-manage-application-groups-in-the-server-management-console.md)

[<span data-ttu-id="60934-141">サーバー管理コンソールでアプリケーションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="60934-141">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

[<span data-ttu-id="60934-142">アプリケーションを手動で追加する方法</span><span class="sxs-lookup"><span data-stu-id="60934-142">How to Manually Add an Application</span></span>](how-to-manually-add-an-application.md)

 

 





