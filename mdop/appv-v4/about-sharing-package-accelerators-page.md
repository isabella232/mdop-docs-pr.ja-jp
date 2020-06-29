---
title: '[パッケージ アクセラレータの共有について] ページ'
description: '[パッケージ アクセラレータの共有について] ページ'
author: dansimp
ms.assetid: 9630cde0-e2c3-476f-8fa1-58b3c9f7d3f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 34fe55d910a7532f011b239ff5b8162aa9240f32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819994"
---
# <span data-ttu-id="0347b-103">[パッケージ アクセラレータの共有について] ページ</span><span class="sxs-lookup"><span data-stu-id="0347b-103">About Sharing Package Accelerators Page</span></span>


<span data-ttu-id="0347b-104">ここでは、パッケージアクセラレータの共有方法に関するベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="0347b-104">This following information provides best practice information about how to share Package Accelerators.</span></span> <span data-ttu-id="0347b-105">パッケージアクセラレータファイルを共有する予定がある場合は、コンピューター名、ユーザーアカウント情報、変換に含まれるアプリケーションに関する情報などの情報がパッケージアクセラレータファイルに含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0347b-105">If you plan to share Package Accelerators files, information such as computer names, user account information, and information about applications included in the transforms might be included in the Package Accelerators file.</span></span> <span data-ttu-id="0347b-106">アプリケーションに個人情報が含まれていないことを確認するには、仮想アプリケーションパッケージに関連付けられている設定または構成ファイルを確認する必要があります。このページには、次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0347b-106">You should review any settings or configuration files associated with the virtual application package to ensure the applications do not contain any personal information.This page contains the following elements.</span></span>

-   <span data-ttu-id="0347b-107">**ユーザー名**。</span><span class="sxs-lookup"><span data-stu-id="0347b-107">**Username**.</span></span> <span data-ttu-id="0347b-108">Microsoft App-v Sequencer を実行しているコンピューターにログオンするときは、組み込みの**管理者**アカウントなどの一般的なユーザーアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0347b-108">When you log on to the computer running the Microsoft App-V Sequencer, you should use a generic user account, such as the built-in **administrator** account.</span></span> <span data-ttu-id="0347b-109">既存のユーザー名に基づくアカウントは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="0347b-109">You should not use an account that is based on an existing user name.</span></span>

-   <span data-ttu-id="0347b-110">**コンピューター名**。</span><span class="sxs-lookup"><span data-stu-id="0347b-110">**Computer Name**.</span></span> <span data-ttu-id="0347b-111">Sequencer を実行しているコンピューターの一般的ではない識別名を指定します。</span><span class="sxs-lookup"><span data-stu-id="0347b-111">Specify a general, non-identifying name of the computer running the Sequencer.</span></span>

-   <span data-ttu-id="0347b-112">**サーバーの URL**。</span><span class="sxs-lookup"><span data-stu-id="0347b-112">**Server URL**.</span></span> <span data-ttu-id="0347b-113">App-v Sequencer コンソールの [**展開**] タブで、サーバー URL 構成情報の既定の設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="0347b-113">In the App-V Sequencer console, on the **Deployment** tab, use the default settings for the server URL configuration information.</span></span>

-   <span data-ttu-id="0347b-114">**アプリケーション**。</span><span class="sxs-lookup"><span data-stu-id="0347b-114">**Applications**.</span></span> <span data-ttu-id="0347b-115">パッケージアクセラレータの作成時に、Sequencer を実行しているコンピューターにインストールされているアプリケーションの一覧を共有しない場合は、 **appv\_manifest.xml**ファイルを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0347b-115">If you do not want to share the list of applications that were installed on the computer running the Sequencer when you created the Package Accelerator, you must delete the **appv\_manifest.xml** file.</span></span> <span data-ttu-id="0347b-116">このファイルは、仮想アプリケーションパッケージのパッケージルートディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="0347b-116">This file is located in the package root directory of the virtual application package.</span></span>

## <span data-ttu-id="0347b-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0347b-117">Related topics</span></span>


[<span data-ttu-id="0347b-118">パッケージ アクセラレータの作成ウィザード (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="0347b-118">Create Package Accelerator Wizard (AppV 4.6 SP1)</span></span>](create-package-accelerator-wizard--appv-46-sp1-.md)

[<span data-ttu-id="0347b-119">App-V パッケージ アクセラレータについて (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="0347b-119">About App-V Package Accelerators (App-V 4.6 SP1)</span></span>](about-app-v-package-accelerators--app-v-46-sp1-.md)

 

 





