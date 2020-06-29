---
title: サーバーを追加する方法
description: サーバーを追加する方法
author: dansimp
ms.assetid: 1f31678a-8edf-4d35-a812-e4a2abfd979b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d08b79bcbf34910ce357f39635431d11e3e99bd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821387"
---
# <span data-ttu-id="30789-103">サーバーを追加する方法</span><span class="sxs-lookup"><span data-stu-id="30789-103">How to Add a Server</span></span>


<span data-ttu-id="30789-104">アプリケーションの仮想化管理サーバーをより効率的に管理できるように、サーバーグループに整理します。</span><span class="sxs-lookup"><span data-stu-id="30789-104">To help you manage your Application Virtualization Management Servers more efficiently, organize them into server groups.</span></span> <span data-ttu-id="30789-105">Application Virtualization Server 管理コンソールでサーバーグループを作成した後、次の手順を使用して、グループにサーバーを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="30789-105">After you create a server group in the Application Virtualization Server Management Console, you can use the following procedure to add a server to the group.</span></span>

<span data-ttu-id="30789-106">**注** サーバーグループ内のすべてのサーバーは、同じデータストアに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30789-106">**Note** All servers in a server group must be connected to the same data store.</span></span>

 

**<span data-ttu-id="30789-107">サーバーをグループに追加するには</span><span class="sxs-lookup"><span data-stu-id="30789-107">To add a server to a group</span></span>**

1.  <span data-ttu-id="30789-108">左側のウィンドウで [**サーバーグループ**] ノードをクリックして、サーバーグループの一覧を展開します。</span><span class="sxs-lookup"><span data-stu-id="30789-108">Click the **Server Groups** node in the left pane to expand the list of server groups.</span></span>

2.  <span data-ttu-id="30789-109">目的のサーバーグループを右クリックし、[**新しい Application Virtualization Management server**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="30789-109">Right-click the desired server group, and select **New Application Virtualization Management Server**.</span></span>

3.  <span data-ttu-id="30789-110">**新しいサーバーグループウィザード**で、**表示名**と**DNS ホスト名**を入力します。</span><span class="sxs-lookup"><span data-stu-id="30789-110">In the **New Server Group Wizard**, enter the **Display Name** and the **DNS Host Name**.</span></span>

4.  <span data-ttu-id="30789-111">サーバーキャッシュの [**最大メモリ割り当て**] フィールドと [**メモリ割り当ての警告**] フィールドの既定値のままにして、しきい値警告レベルを指定します。</span><span class="sxs-lookup"><span data-stu-id="30789-111">Leave the default values in the **Maximum Memory Allocation** field for the server cache and the **Warn Memory Allocation** field to specify the threshold warning level.</span></span>

5.  <span data-ttu-id="30789-112">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30789-112">Click **Next**.</span></span>

6.  <span data-ttu-id="30789-113">[**接続セキュリティモード**] ダイアログボックスで、[**強化セキュリティを使用**] チェックボックスをオンにし、必要に応じて [拡張セキュリティモード] を選択します。</span><span class="sxs-lookup"><span data-stu-id="30789-113">In the **Connection Security Mode** dialog, check the **Use enhanced security** box to select enhanced security mode, if desired.</span></span> <span data-ttu-id="30789-114">必要に応じて、**証明書ウィザード**を完了するか、既存の証明書を表示します。</span><span class="sxs-lookup"><span data-stu-id="30789-114">If necessary, complete the **Certificate Wizard** or view existing certificates.</span></span>

7.  <span data-ttu-id="30789-115">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30789-115">Click **Next**.</span></span>

8.  <span data-ttu-id="30789-116">[ **App Virt Port Setting** ] ダイアログで、[ **Use Default port** ] または [ **User custom port** ] ラジオボタンを選択し、カスタムポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="30789-116">In the **App Virt Port Setting** dialog, select the **Use Default Port** or the **User Custom Port** radio button and enter the custom port number.</span></span>

9.  <span data-ttu-id="30789-117">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="30789-117">Click **Finish**.</span></span>

## <span data-ttu-id="30789-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="30789-118">Related topics</span></span>


[<span data-ttu-id="30789-119">サーバー グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="30789-119">How to Create a Server Group</span></span>](how-to-create-a-server-group.md)

[<span data-ttu-id="30789-120">サーバーを削除する方法</span><span class="sxs-lookup"><span data-stu-id="30789-120">How to Remove a Server</span></span>](how-to-remove-a-server.md)

 

 





