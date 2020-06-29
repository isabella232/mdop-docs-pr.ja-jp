---
title: Windows Vista の適切な資格情報を割り当てる方法
description: Windows Vista の適切な資格情報を割り当てる方法
author: dansimp
ms.assetid: cc11d2af-a350-4d16-ba7b-f9c1d89e14b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 111dafea505133f123cf8531a2891a452e725ac2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821367"
---
# <span data-ttu-id="ad369-103">Windows Vista の適切な資格情報を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="ad369-103">How to Assign the Proper Credentials for Windows Vista</span></span>


<span data-ttu-id="ad369-104">次の手順に従って、適切な windows Vista の資格情報を使用して App-v デスクトップクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="ad369-104">Use the following procedure to configure the App-V Desktop Client for proper WindowsVista credentials.</span></span>

<span data-ttu-id="ad369-105">**注** この手順は、ドメインに参加していない各コンピューターで完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad369-105">**Note** This procedure must be completed on each non-domain joined computer.</span></span> <span data-ttu-id="ad369-106">環境内のドメインに参加していないコンピューターの数によっては、非常に面倒な操作になることがあります。</span><span class="sxs-lookup"><span data-stu-id="ad369-106">Depending on the number of non-domain joined computers in your environment, this could be a very tedious operation.</span></span> <span data-ttu-id="ad369-107">Credential Manager のスクリプトとコマンドラインインターフェイスを使用すると、管理者がこのプロセスを自動化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ad369-107">You can use scripts and the command-line interface for Credential Manager to help administrators automate this process.</span></span>

 

**<span data-ttu-id="ad369-108">Windows Vista を実行している App-v クライアントに適切な資格情報を割り当てるには</span><span class="sxs-lookup"><span data-stu-id="ad369-108">To assign the proper credentials for App-V clients running Windows Vista</span></span>**

1.  <span data-ttu-id="ad369-109">Windows Vista を実行している App-v デスクトップクライアントで管理者権限がある場合は、[**ユーザーアカウント**] コントロールパネル (クラシックコントロールパネル) を開きます。</span><span class="sxs-lookup"><span data-stu-id="ad369-109">With administrator privileges on the App-V Desktop Client running Windows Vista, open the **User Accounts** control panel (Classic Control Panel).</span></span>

2.  <span data-ttu-id="ad369-110">左側のタスクウィンドウで、[**ユーザーアカウント**から**ネットワークパスワードを管理**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad369-110">Select **Manage your network passwords** from **User Accounts** in the left tasks pane.</span></span>

3.  <span data-ttu-id="ad369-111">[**ユーザー名とパスワードの保存**] 画面の [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad369-111">Select **Add** on the **Stored User Names and Passwords** screen.</span></span>

4.  <span data-ttu-id="ad369-112">[**保存されている資格情報のプロパティ**] 画面で、app-v インフラストラクチャの情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ad369-112">On the **Stored Credential Properties** screen, provide the information for the App-V infrastructure:</span></span>

    1.  <span data-ttu-id="ad369-113">**ログオン:** 発行サーバーの外部名。</span><span class="sxs-lookup"><span data-stu-id="ad369-113">**Log on to:** External name of the publishing server.</span></span>

    2.  <span data-ttu-id="ad369-114">**ユーザー名:** フォーム Domain\\Username. の外部ユーザーのユーザー名</span><span class="sxs-lookup"><span data-stu-id="ad369-114">**User name:** User name for the external user in the form Domain\\Username.</span></span>

    3.  <span data-ttu-id="ad369-115">**パスワード:**[**ユーザー名**] フィールドに入力されたユーザーアカウントのパスワードです。</span><span class="sxs-lookup"><span data-stu-id="ad369-115">**Password:** Password for the user account entered in the **User name** field.</span></span>

    4.  <span data-ttu-id="ad369-116">**資格情報の種類**を選択したままにして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad369-116">Leave **Credential Type** selected, and click **OK**.</span></span>

5.  <span data-ttu-id="ad369-117">**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ad369-117">Click **Close**.</span></span> <span data-ttu-id="ad369-118">資格情報は、App-v インフラストラクチャへの適切な認証のために資格情報ストアに保存されます。</span><span class="sxs-lookup"><span data-stu-id="ad369-118">The credentials are stored in the credential store for proper authentication to the App-V infrastructure.</span></span>

## <span data-ttu-id="ad369-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ad369-119">Related topics</span></span>


[<span data-ttu-id="ad369-120">ドメインに参加しているクライアントとドメインに参加していないクライアント</span><span class="sxs-lookup"><span data-stu-id="ad369-120">Domain-Joined and Non-Domain-Joined Clients</span></span>](domain-joined-and-non-domain-joined-clients.md)

[<span data-ttu-id="ad369-121">Windows XP の適切な資格情報を割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="ad369-121">How to Assign the Proper Credentials for Windows XP</span></span>](how-to-assign--the-proper-credentials-for-windows-xp.md)

 

 





