---
title: パッケージのバージョンを追加する方法
description: パッケージのバージョンを追加する方法
author: dansimp
ms.assetid: dbb829c1-e5cb-4a2f-bc17-9a9bb50c671c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a60252e8b43af61ad548df30a93d8fbc9bae0cb7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821404"
---
# <span data-ttu-id="326bc-103">パッケージのバージョンを追加する方法</span><span class="sxs-lookup"><span data-stu-id="326bc-103">How to Add a Package Version</span></span>


<span data-ttu-id="326bc-104">Application Virtualization Server 管理コンソールでパッケージを再処理するときに、次の手順を使用して、ストリーミングのために新しいバージョンをサーバーに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="326bc-104">In the Application Virtualization Server Management Console, when you resequence a package, you can use the following procedure to add the new version to your servers for streaming.</span></span>

<span data-ttu-id="326bc-105">**注** 新しいバージョンでパッケージをアップグレードする場合は、既存のバージョンをそのまま残しておくか、削除してから最新のバージョンを残しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="326bc-105">**Note** When you upgrade a package with a new version, you can leave the existing version in place or delete it and leave only the newest one.</span></span> <span data-ttu-id="326bc-106">以前のドキュメントとの互換性を維持するために古いバージョンをそのまま残しておくことをお勧めします。また、すべてのユーザーが使用できるようにする前に、新しいバージョンのテストを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="326bc-106">You might want to leave the old version in place for compatibility with legacy documents or so that you can test the new version before making it available to all users.</span></span>

 

**<span data-ttu-id="326bc-107">パッケージバージョンを追加するには</span><span class="sxs-lookup"><span data-stu-id="326bc-107">To add a package version</span></span>**

1.  <span data-ttu-id="326bc-108">新しい SFT ファイルをアプリケーションサーバーのコンテンツフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="326bc-108">Copy the new SFT file to the application server's content folder.</span></span> <span data-ttu-id="326bc-109">Resequencing で、オープンソフトウェア記述子 (OSD)、icon (ICO)、または Sequencer Project (SPRJ) ファイルに変更が追加されなかった場合は、それらをコピーする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="326bc-109">If resequencing did not add changes to the Open Software Descriptor (OSD), icon (ICO), or Sequencer Project (SPRJ) files, you do not need to copy those.</span></span> <span data-ttu-id="326bc-110">すべてのファイルに同じ日付を表示する場合は、これらのファイルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="326bc-110">You can include those files if you want all the files to display the same date.</span></span>

2.  <span data-ttu-id="326bc-111">Application Virtualization Server 管理コンソールの左側のウィンドウで、[**パッケージ**] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="326bc-111">In left pane of the Application Virtualization Server Management Console, expand the **Packages** node.</span></span>

3.  <span data-ttu-id="326bc-112">アップグレードするパッケージを右クリックし、[**バージョンの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="326bc-112">Right-click the package you want to upgrade, and choose **Add Version**.</span></span>

4.  <span data-ttu-id="326bc-113">[**パッケージバージョンの追加**] ダイアログボックスで、[**パッケージファイルのフルパス**] フィールドに新しいアプリケーションファイルのパス名を参照するか、入力します。</span><span class="sxs-lookup"><span data-stu-id="326bc-113">In the **Add Package Version** dialog box, browse for or type the path name for the new application file in the **Full path for package file** field.</span></span> <span data-ttu-id="326bc-114">これは、SFT ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="326bc-114">This must be an SFT file.</span></span>

5.  <span data-ttu-id="326bc-115">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="326bc-115">Click **Next**.</span></span>

6.  <span data-ttu-id="326bc-116">[**概要**] ダイアログボックスにファイルの場所が表示され、ファイルのコピーをまだ行っていない場合は、ファイルをコピーするように求められます。</span><span class="sxs-lookup"><span data-stu-id="326bc-116">The **Summary** dialog box shows the file location and prompts you to copy the file there if you have not already done so.</span></span> <span data-ttu-id="326bc-117">情報を確認したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="326bc-117">Click **Finish** after you have verified the information.</span></span>

    <span data-ttu-id="326bc-118">これで、新しいバージョンが完成し、ストリーミングする準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="326bc-118">The new version is now complete and ready to stream.</span></span>

## <span data-ttu-id="326bc-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="326bc-119">Related topics</span></span>


[<span data-ttu-id="326bc-120">パッケージを削除する方法</span><span class="sxs-lookup"><span data-stu-id="326bc-120">How to Delete a Package</span></span>](how-to-delete-a-packageserver.md)

[<span data-ttu-id="326bc-121">サーバー管理コンソールでパッケージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="326bc-121">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





