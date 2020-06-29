---
title: 同時使用ライセンス グループをセットアップする方法
description: 同時使用ライセンス グループをセットアップする方法
author: dansimp
ms.assetid: 031abcf6-d8ed-49be-bddb-91b2c695d411
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6e3035362cd645b6488b07408d6a9444f632fc88
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816627"
---
# <span data-ttu-id="d3e94-103">同時使用ライセンス グループをセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="d3e94-103">How to Set Up a Concurrent License Group</span></span>


<span data-ttu-id="d3e94-104">Application Virtualization Server 管理コンソールで、次の手順を使用して、同時ライセンスグループを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="d3e94-104">You can use the following procedure in the Application Virtualization Server Management Console to set up a concurrent license group.</span></span> <span data-ttu-id="d3e94-105">同時ライセンスグループを設定するときに、特定の数の同時ユーザーにアプリケーションへのアクセスを制限することができます。</span><span class="sxs-lookup"><span data-stu-id="d3e94-105">When you set up a concurrent license group, you can limit access to applications to a specific number of concurrent users.</span></span>

**<span data-ttu-id="d3e94-106">同時ライセンスグループを設定するには</span><span class="sxs-lookup"><span data-stu-id="d3e94-106">To set up a concurrent license group</span></span>**

1.  <span data-ttu-id="d3e94-107">Application Virtualization Server 管理コンソールの左側のウィンドウで、[**アプリケーションライセンス**] ノードを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="d3e94-107">In the left pane of the Application Virtualization Server Management Console, right-click the **Application Licenses** node.</span></span>

2.  <span data-ttu-id="d3e94-108">[**新しい同時ライセンス**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="d3e94-108">Select **New Concurrent License**.</span></span>

3.  <span data-ttu-id="d3e94-109">[**アプリケーションライセンスグループ名**] フィールドに名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="d3e94-109">Enter a name in the **Application License Group Name** field.</span></span>

4.  <span data-ttu-id="d3e94-110">[**ライセンスの有効期限] 警告**フィールドに値 (分単位) を入力します。</span><span class="sxs-lookup"><span data-stu-id="d3e94-110">Enter a value (in minutes) in the **License Expiration Warning** field.</span></span>

5.  <span data-ttu-id="d3e94-111">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3e94-111">Click **Next**.</span></span>

6.  <span data-ttu-id="d3e94-112">「**ライセンスの説明**」フィールドに説明のテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="d3e94-112">Enter descriptive text in the **License Description** field.</span></span>

7.  <span data-ttu-id="d3e94-113">[**同時ライセンス数**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="d3e94-113">Enter a value in the **Concurrent License Quantity** field.</span></span>

8.  <span data-ttu-id="d3e94-114">ライセンスを有効にするには、[**有効**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="d3e94-114">Select the **Enabled** check box to enable the license.</span></span>

9.  <span data-ttu-id="d3e94-115">[**有効**期限] チェックボックスをオンにし (有効期限を設定する場合)、有効期限を入力するか、カレンダーユーティリティを使用して日付を選びます。</span><span class="sxs-lookup"><span data-stu-id="d3e94-115">Select the **Expiration Date** check box (if you want to set an expiration date), and enter the expiration date or use the calendar utility to select a date.</span></span>

10. <span data-ttu-id="d3e94-116">ライセンスにキーを関連付ける必要がある場合は、ライセンスキーの情報を [**ライセンスキー** ] フィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="d3e94-116">If you need to associate a key with the license, enter the license key information in the **License Key** field.</span></span>

11. <span data-ttu-id="d3e94-117">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d3e94-117">Click **Finish**.</span></span>

## <span data-ttu-id="d3e94-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d3e94-118">Related topics</span></span>


[<span data-ttu-id="d3e94-119">アプリケーションをライセンス グループに関連付ける方法</span><span class="sxs-lookup"><span data-stu-id="d3e94-119">How to Associate an Application with a License Group</span></span>](how-to-associate-an-application-with-a-license-group.md)

[<span data-ttu-id="d3e94-120">アプリケーション ライセンス グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="d3e94-120">How to Create an Application License Group</span></span>](how-to-create-an-application-license-group.md)

[<span data-ttu-id="d3e94-121">ライセンス グループからアプリケーションを削除する方法</span><span class="sxs-lookup"><span data-stu-id="d3e94-121">How to Remove an Application from a License Group</span></span>](how-to-remove-an-application-from-a-license-group.md)

[<span data-ttu-id="d3e94-122">名前付きライセンス グループをセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="d3e94-122">How to Set Up a Named License Group</span></span>](how-to-set-up-a-named-license-group.md)

[<span data-ttu-id="d3e94-123">無制限ライセンス グループをセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="d3e94-123">How to Set Up an Unlimited License Group</span></span>](how-to-set-up-an-unlimited-license-group.md)

 

 





