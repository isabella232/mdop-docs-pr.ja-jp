---
title: 展開のプロパティを変更する方法
description: 展開のプロパティを変更する方法
author: dansimp
ms.assetid: 0a214a7a-cc83-4d04-89f9-5727153be918
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dfb42962d41159479db61da9c3beb3771ef35502
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818064"
---
# <span data-ttu-id="bb3d3-103">展開のプロパティを変更する方法</span><span class="sxs-lookup"><span data-stu-id="bb3d3-103">How to Change Deployment Properties</span></span>


<span data-ttu-id="bb3d3-104">次の手順を使用して、アプリケーションの仮想化サーバーの URL、仮想化されたアプリケーションで必要なオペレーティングシステム、インストールする仮想アプリケーションの出力オプションなど、優先順位を設定するアプリケーションの**展開**タブ情報を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="bb3d3-104">You can use the following procedures to change the **Deployment** tab information for an application you are sequencing, including the Application Virtualization server URL, the operating systems required by the virtualized applications, and the output options for the virtual application to be installed.</span></span>

**<span data-ttu-id="bb3d3-105">サーバーの URL を変更するには</span><span class="sxs-lookup"><span data-stu-id="bb3d3-105">To change the server URL</span></span>**

1.  <span data-ttu-id="bb3d3-106">ドロップダウンリストボックスからストリーミングプロトコルを選択します。</span><span class="sxs-lookup"><span data-stu-id="bb3d3-106">Select the streaming protocol from the drop-down list box.</span></span>

2.  <span data-ttu-id="bb3d3-107">仮想アプリケーションサーバーまたはサーバーグループのロードバランサーのホスト名を入力します。</span><span class="sxs-lookup"><span data-stu-id="bb3d3-107">Enter the host name of the virtual application server or the server group's load balancer.</span></span> <span data-ttu-id="bb3d3-108">実際のホスト名または IP アドレスを使用できます。</span><span class="sxs-lookup"><span data-stu-id="bb3d3-108">You can use the actual host name or IP address.</span></span>

3.  <span data-ttu-id="bb3d3-109">ストリームアプリケーションに対して、仮想アプリケーションサーバーまたはロードバランサーがアプリケーション仮想化デスクトップクライアント要求をリッスンするポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="bb3d3-109">Specify the port number on which the virtual application server or load balancer will listen for an Application Virtualization Desktop Client request for the streamed application.</span></span>

4.  <span data-ttu-id="bb3d3-110">ソフトウェアパッケージが保存されている仮想アプリケーションサーバー上の相対パスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bb3d3-110">Specify the relative path on the virtual application server where the software package is stored.</span></span>

**<span data-ttu-id="bb3d3-111">アプリケーションのオペレーティングシステム要件を変更するには</span><span class="sxs-lookup"><span data-stu-id="bb3d3-111">To change the application operating systems requirements</span></span>**

1.  <span data-ttu-id="bb3d3-112">必要なオペレーティングシステムを追加するには、[**利用可能**] ボックスの一覧で、選択**され**ているオペレーティングシステムのリストコントロールを指す矢印ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb3d3-112">To add the required operating system(s), select it in the **Available** list and click the arrow button pointing to the **Selected** operating systems list control.</span></span>

2.  <span data-ttu-id="bb3d3-113">オペレーティングシステムを削除するには、[**選択した**リスト] コントロールでオペレーティングシステムを選択し、[**利用可能な**オペレーティングシステム] リストコントロールを指す矢印ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb3d3-113">To remove an operating system, select it in the **Selected** list control, and click the arrow button pointing to the **Available** operating systems list control.</span></span>

**<span data-ttu-id="bb3d3-114">アプリケーションの出力オプションを変更するには</span><span class="sxs-lookup"><span data-stu-id="bb3d3-114">To change the application output options</span></span>**

1.  <span data-ttu-id="bb3d3-115">[**圧縮アルゴリズム**] ボックスの一覧で、アプリケーションのストリーミング時に使う圧縮方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="bb3d3-115">From the **Compression Algorithm** drop-down list, select the compression method to use when streaming the application.</span></span>

2.  <span data-ttu-id="bb3d3-116">パッケージ化されたアプリケーションのセキュリティ記述子が展開時に適用されるようにするには、[**セキュリティ記述子を適用**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="bb3d3-116">Select the **Enforce Security Descriptors** check box to ensure security descriptors of the packaged applications are enforced when deployed.</span></span>

3.  <span data-ttu-id="bb3d3-117">[**差分ファイルの生成**] を選択すると、以前の順序付けされたバージョンからアプリケーションの差分ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="bb3d3-117">Select **Generate Difference File** to generate a difference file for the application from the previous sequenced version.</span></span>

4.  <span data-ttu-id="bb3d3-118">[ **Microsoft Windows インストーラー (MSI) パッケージの生成**] を選択して、インストーラパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="bb3d3-118">Select **Generate Microsoft Windows Installer (MSI) Package** to create an installer package.</span></span>

## <span data-ttu-id="bb3d3-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bb3d3-119">Related topics</span></span>


[<span data-ttu-id="bb3d3-120">[展開] タブについて</span><span class="sxs-lookup"><span data-stu-id="bb3d3-120">About the Deployment Tab</span></span>](about-the-deployment-tab.md)

[<span data-ttu-id="bb3d3-121">Sequencer Console</span><span class="sxs-lookup"><span data-stu-id="bb3d3-121">Sequencer Console</span></span>](sequencer-console.md)

 

 





