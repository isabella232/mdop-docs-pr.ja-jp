---
title: パッケージをアップグレードする方法
description: パッケージをアップグレードする方法
author: dansimp
ms.assetid: 831c7556-6f6c-4b3a-aefb-26889094dc1a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a9b3eca2c996337d79e551784818a421f495316
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816504"
---
# <span data-ttu-id="18a0e-103">パッケージをアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="18a0e-103">How to Upgrade a Package</span></span>


<span data-ttu-id="18a0e-104">自動アップグレードのプロセスは、Application Virtualization Server 管理コンソールでのパッケージバージョンの追加と同じです。</span><span class="sxs-lookup"><span data-stu-id="18a0e-104">The process for an automatic upgrade is the same as for adding a package version in the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="18a0e-105">既存のパッケージでアプリケーションを再シーケンスすると、自動アップグレードが実行されます。</span><span class="sxs-lookup"><span data-stu-id="18a0e-105">An automatic upgrade is performed when you resequence the application in an existing package.</span></span> <span data-ttu-id="18a0e-106">次に、この新しいバージョンをサーバーに追加してストリーミングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="18a0e-106">Then you can add this new version to your servers for streaming.</span></span>

<span data-ttu-id="18a0e-107">新しいバージョンでパッケージをアップグレードする場合は、既存のバージョンをそのまま残しておくか、削除してから最新のバージョンを残しておくことができます。</span><span class="sxs-lookup"><span data-stu-id="18a0e-107">When you upgrade a package with a new version, you can leave the existing version in place or delete it and leave only the newest one.</span></span> <span data-ttu-id="18a0e-108">以前のドキュメントとの互換性を維持するために古いバージョンをそのまま残しておくことをお勧めします。また、すべてのユーザーが使用できるようにする前に、新しいバージョンのテストを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="18a0e-108">You might want to leave the old version in place for compatibility with legacy documents or so that you can test the new version before making it available to all users.</span></span>

**<span data-ttu-id="18a0e-109">パッケージを自動的にアップグレードするには</span><span class="sxs-lookup"><span data-stu-id="18a0e-109">To upgrade a package automatically</span></span>**

1.  <span data-ttu-id="18a0e-110">新しい SFT ファイルを Application Virtualization サーバーのコンテンツフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="18a0e-110">Copy the new SFT file to the Application Virtualization Server's content folder.</span></span>

    <span data-ttu-id="18a0e-111">**注** Resequencing で、Open Software Descriptor (OSD)、icon (ICO)、または Sequencer Project (SPRJ) ファイルを変更した機能が追加されなかった場合は、それらをコピーする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="18a0e-111">**Note** If resequencing did not add features that changed the Open Software Descriptor (OSD), icon (ICO), or Sequencer Project (SPRJ) files, you do not need to copy those.</span></span> <span data-ttu-id="18a0e-112">すべてのファイルに同じ日付を表示する場合は、これらのファイルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="18a0e-112">You can include these files if you want all these files to display the same date.</span></span>

     

2.  <span data-ttu-id="18a0e-113">Application Virtualization Server 管理コンソールの左側のウィンドウで、[**パッケージ**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="18a0e-113">In left pane of the Application Virtualization Server Management Console, expand **Packages**.</span></span>

3.  <span data-ttu-id="18a0e-114">アップグレードするパッケージを右クリックし、[**バージョンの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="18a0e-114">Right-click the package you want to upgrade, and select **Add Version**.</span></span>

4.  <span data-ttu-id="18a0e-115">[**パッケージバージョンの追加**] ダイアログボックスで、新しいアプリケーションバージョンの完全パス名を [ファイル] フィールド**のフルパス**で参照するか、入力します。</span><span class="sxs-lookup"><span data-stu-id="18a0e-115">In the **Add Package Version** dialog box, browse for or type the full path name for the new application version in the **Full Path for the file** field.</span></span> <span data-ttu-id="18a0e-116">これは、SFT ファイルである必要があります。</span><span class="sxs-lookup"><span data-stu-id="18a0e-116">This must be an SFT file.</span></span>

5.  <span data-ttu-id="18a0e-117">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18a0e-117">Click **Next**.</span></span>

6.  <span data-ttu-id="18a0e-118">[**概要**] ダイアログボックスにファイルの場所が表示され、ファイルのコピーをまだ行っていない場合は、ファイルをコピーするように求められます。</span><span class="sxs-lookup"><span data-stu-id="18a0e-118">The **Summary** dialog box shows the file location and prompts you to copy the file there if you have not already done so.</span></span> <span data-ttu-id="18a0e-119">情報を確認したら、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="18a0e-119">Click **Finish** after you have verified the information.</span></span>

    <span data-ttu-id="18a0e-120">これで、新しいバージョンが完成し、ストリーミングする準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="18a0e-120">The new version is now complete and ready to stream.</span></span>

## <span data-ttu-id="18a0e-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="18a0e-121">Related topics</span></span>


[<span data-ttu-id="18a0e-122">サーバー管理コンソールでパッケージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="18a0e-122">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





