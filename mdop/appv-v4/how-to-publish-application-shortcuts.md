---
title: アプリケーション ショートカットを公開する方法
description: アプリケーション ショートカットを公開する方法
author: dansimp
ms.assetid: fc5efe86-1bbe-438b-b7d8-4f9b815cc58e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eafdb85414a1a6cf3e1072fdc5532bcd04699653
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816844"
---
# <span data-ttu-id="674b8-103">アプリケーション ショートカットを公開する方法</span><span class="sxs-lookup"><span data-stu-id="674b8-103">How to Publish Application Shortcuts</span></span>


<span data-ttu-id="674b8-104">次の手順を使用して、application Virtualization クライアント管理コンソールの**アプリケーション**ノードの [**結果**] ウィンドウから、アプリケーションに直接ショートカットを公開できます。</span><span class="sxs-lookup"><span data-stu-id="674b8-104">You can use the following procedure to publish shortcuts to an application directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="674b8-105">アプリケーションのショートカットを発行するには</span><span class="sxs-lookup"><span data-stu-id="674b8-105">To publish application shortcuts</span></span>**

1.  <span data-ttu-id="674b8-106">[**結果**] ウィンドウにカーソルを移動し、目的のアプリケーションを右クリックして、ポップアップメニューから [**新しいショートカット**] を選んで、新しいショートカットウィザードを表示します。</span><span class="sxs-lookup"><span data-stu-id="674b8-106">Move the cursor to the **Results** pane, right-click the desired application, and select **New Shortcut** from the pop-up menu to display the New Shortcut Wizard.</span></span>

2.  <span data-ttu-id="674b8-107">新しいショートカットウィザードの最初のページで、アイコンを選択して、ショートカットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="674b8-107">On the first page of the New Shortcut Wizard, select an icon and specify a name for the shortcut.</span></span>

    1.  <span data-ttu-id="674b8-108">**変更アイコン**-標準の Windows アイコンのブラウザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="674b8-108">**Change Icon**—Displays a standard Windows icon browser.</span></span> <span data-ttu-id="674b8-109">目的のアイコンを参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="674b8-109">Browse to and select the desired icon.</span></span>

    2.  <span data-ttu-id="674b8-110">[**ショートカットのタイトル**の指定: ショートカットの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="674b8-110">**Shortcut Title**—Enter the name you want to give the shortcut.</span></span> <span data-ttu-id="674b8-111">このフィールドの既定値は、アプリケーションの既存名とバージョンです。</span><span class="sxs-lookup"><span data-stu-id="674b8-111">This field defaults to the existing name and version of the application.</span></span>

3.  <span data-ttu-id="674b8-112">ウィザードの2ページ目で、公開されたショートカットの場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="674b8-112">On the second page of the wizard, determine the location of the published shortcut.</span></span>

    1.  <span data-ttu-id="674b8-113">[**デスクトップ**] —ショートカットをデスクトップに発行するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="674b8-113">**The Desktop**—Select this check box to publish the shortcut to the desktop.</span></span>

    2.  <span data-ttu-id="674b8-114">**クイック起動ツールバー**: クイック起動ツールバーにショートカットを発行するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="674b8-114">**The Quick Launch Toolbar**—Select this check box to publish the shortcut to the Quick Launch toolbar.</span></span>

    3.  <span data-ttu-id="674b8-115">[**送信] メニュー**: ショートカットを [**送信**] メニューに発行するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="674b8-115">**The Send To Menu**—Select this check box to publish the shortcut to the **Send To** menu.</span></span>

    4.  <span data-ttu-id="674b8-116">[**スタート] メニュー**の [プログラム] チェックボックスをオンにすると、この**フィールドがアクティブ**になります。</span><span class="sxs-lookup"><span data-stu-id="674b8-116">**Programs in the Start Menu**—When you select the **Start Menu** check box, this field becomes active.</span></span> <span data-ttu-id="674b8-117">ショートカットを [プログラム] フォルダーのルートに直接公開するには、このフィールドを空白のままにします。または、"My \ _Computer ¥ Office アプリケーション" などのフォルダー名または階層を入力します。</span><span class="sxs-lookup"><span data-stu-id="674b8-117">Leave this field blank to publish the shortcut directly to the root of the Programs folder, or enter a folder name or hierarchy—for example, "My\_Computer\\Office Applications."</span></span> <span data-ttu-id="674b8-118">この方法で作成されたショートカットは、現在のユーザーに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="674b8-118">Shortcuts created this way are available only for the current user.</span></span>

    5.  <span data-ttu-id="674b8-119">**別の場所**と**参照**ボタン— [別の**場所**] チェックボックスをオンにすると、このフィールドがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="674b8-119">**Another location** and **Browse** button—When you select the **Another location** check box, this field becomes active.</span></span> <span data-ttu-id="674b8-120">コンピューター上の有効な場所、または利用可能な UNC パス (ネットワーク上の共有ファイルまたはディレクトリ) を入力します。</span><span class="sxs-lookup"><span data-stu-id="674b8-120">Enter any valid location on the computer or any available UNC path (shared file or directory on a network).</span></span> <span data-ttu-id="674b8-121">[**参照**] ボタンをクリックすると、Windows の標準的な **[ファイルを開く**] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="674b8-121">The **Browse** button displays a standard Windows **File Open** dialog box.</span></span>

4.  <span data-ttu-id="674b8-122">ウィザードの3ページ目で、必要なコマンドラインパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="674b8-122">On the third page of the wizard, enter desired command-line parameters.</span></span>

5.  <span data-ttu-id="674b8-123">[**完了**] をクリックして、ショートカットを発行し、[**結果**] ウィンドウに退出します。</span><span class="sxs-lookup"><span data-stu-id="674b8-123">Click **Finish** to publish the shortcuts and exit to the **Results** pane.</span></span>

## <span data-ttu-id="674b8-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="674b8-124">Related topics</span></span>


[<span data-ttu-id="674b8-125">ファイルの種類の関連付けを追加する方法</span><span class="sxs-lookup"><span data-stu-id="674b8-125">How to Add a File Type Association</span></span>](how-to-add-a-file-type-association.md)

[<span data-ttu-id="674b8-126">アプリケーションを追加する方法</span><span class="sxs-lookup"><span data-stu-id="674b8-126">How to Add an Application</span></span>](how-to-add-an-application.md)

[<span data-ttu-id="674b8-127">ファイルの種類の関連付けを削除する方法</span><span class="sxs-lookup"><span data-stu-id="674b8-127">How to Delete a File Type Association</span></span>](how-to-delete-a-file-type-association.md)

 

 





