---
title: サーバーのキャッシュ サイズを変更する方法
description: サーバーのキャッシュ サイズを変更する方法
author: dansimp
ms.assetid: 24e63744-21c3-458e-b137-9592f4fe785c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92e56a8a28f7a00d71805b497f9e404cca65919d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818027"
---
# <span data-ttu-id="07a92-103">サーバーのキャッシュ サイズを変更する方法</span><span class="sxs-lookup"><span data-stu-id="07a92-103">How to Change the Server Cache Size</span></span>


<span data-ttu-id="07a92-104">次の手順を使用して、Application Virtualization Server 管理コンソールから任意のサーバーのキャッシュサイズを直接変更できます。</span><span class="sxs-lookup"><span data-stu-id="07a92-104">You can use the following procedure to change the cache size for any server directly from the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="07a92-105">**注** キャッシュサイズを変更することはできますが、特に設定でサイズを変更する必要がある場合を除き、キャッシュサイズは既定値に設定しておくことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="07a92-105">**Note** Although you can change the cache size, unless your configuration specifically requires you to change the size, it is recommended that you leave the cache size set to the default values.</span></span>

 

**<span data-ttu-id="07a92-106">サーバーキャッシュのサイズを変更するには</span><span class="sxs-lookup"><span data-stu-id="07a92-106">To change the server cache size</span></span>**

1.  <span data-ttu-id="07a92-107">左側のウィンドウで [**サーバーグループ**] ノードをクリックして、サーバーグループの一覧を展開します。</span><span class="sxs-lookup"><span data-stu-id="07a92-107">Click the **Server Groups** node in the left pane to expand the list of server groups.</span></span>

2.  <span data-ttu-id="07a92-108">[**結果**] ウィンドウで、目的のサーバーグループをダブルクリックして、グループ内のサーバーの一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="07a92-108">In the **Results** pane, double-click the desired server group to display the list of servers in the group.</span></span>

3.  <span data-ttu-id="07a92-109">[**結果**] ウィンドウで、目的のサーバーを右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="07a92-109">In the **Results** pane, right-click the desired server and select **Properties**.</span></span>

4.  <span data-ttu-id="07a92-110">[**詳細設定**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="07a92-110">Select the **Advanced** tab.</span></span>

5.  <span data-ttu-id="07a92-111">サーバーキャッシュの [**最大メモリ割り当て**] フィールドに値を入力して、[**メモリ割り当ての警告**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="07a92-111">Enter a value in the **Maximum Memory Allocation** field for the server cache, and enter a value for the threshold warning level in the **Warn Memory Allocation** field.</span></span>

6.  <span data-ttu-id="07a92-112">[**最大ブロックサイズ**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="07a92-112">Enter a value in the **Maximum Block Size** field.</span></span> <span data-ttu-id="07a92-113">この数値は、サーバーからストリーミングされる最大のパッケージの最大ブロックサイズ以上である必要があります。</span><span class="sxs-lookup"><span data-stu-id="07a92-113">This number must be greater than or equal to the maximum block size of the largest package that will be streamed from the server.</span></span>

7.  <span data-ttu-id="07a92-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="07a92-114">Click **OK**.</span></span>

## <span data-ttu-id="07a92-115">関連トピック</span><span class="sxs-lookup"><span data-stu-id="07a92-115">Related topics</span></span>


[<span data-ttu-id="07a92-116">サーバー ポートを変更する方法</span><span class="sxs-lookup"><span data-stu-id="07a92-116">How to Change the Server Port</span></span>](how-to-change-the-server-port.md)

[<span data-ttu-id="07a92-117">サーバー管理コンソールでサーバーを管理する方法</span><span class="sxs-lookup"><span data-stu-id="07a92-117">How to Manage Servers in the Server Management Console</span></span>](how-to-manage-servers-in-the-server-management-console.md)

 

 





