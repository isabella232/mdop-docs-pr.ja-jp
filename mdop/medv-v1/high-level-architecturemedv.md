---
title: アーキテクチャの概要
description: アーキテクチャの概要
author: dansimp
ms.assetid: a78e12ad-5aa6-40e0-ae8b-51acaf005712
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 00df29c751653645ab4bee9762af57576a40092a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826204"
---
# <span data-ttu-id="738ce-103">アーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="738ce-103">High-Level Architecture</span></span>


<span data-ttu-id="738ce-104">MED-V ソリューションは、次の要素で構成されています。</span><span class="sxs-lookup"><span data-stu-id="738ce-104">The MED-V solution comprises the following elements:</span></span>

-   <span data-ttu-id="738ce-105">**管理者が定義した仮想マシン**: オペレーティングシステム、アプリケーション、オプションの管理およびセキュリティツールなど、完全なデスクトップ環境をカプセル化します。</span><span class="sxs-lookup"><span data-stu-id="738ce-105">**Administrator-defined virtual machine**—Encapsulates a full desktop environment, including an operating system, applications, and optional management and security tools.</span></span>

-   <span data-ttu-id="738ce-106">**イメージリポジトリ**—すべての仮想イメージを標準の IIS サーバーに保存し、仮想イメージのバージョン管理、クライアントで認証された画像の取得、およびトリム転送テクノロジを使用した効率的なダウンロード (新しいイメージまたは更新) を可能にします。</span><span class="sxs-lookup"><span data-stu-id="738ce-106">**Image repository**—Stores all virtual images on a standard IIS server and enables virtual images version management, client-authenticated image retrieval, and efficient download (of a new image or updates) via Trim Transfer technology.</span></span>

-   <span data-ttu-id="738ce-107">**管理サーバー**: イメージリポジトリの仮想画像と管理者の使用ポリシーを、ユーザーまたはグループ® Active Directory に関連付けます。</span><span class="sxs-lookup"><span data-stu-id="738ce-107">**Management server**—Associates virtual images from the image repository along with administrator usage policies to Active Directory® users or groups.</span></span> <span data-ttu-id="738ce-108">管理サーバーでは、監視とレポートの目的で、クライアントのイベントを収集して外部データベース (Microsoft SQL Server®) に保存することもできます。</span><span class="sxs-lookup"><span data-stu-id="738ce-108">The management server also aggregates clients' events and stores them in an external database (Microsoft SQL Server®) for monitoring and reporting purposes.</span></span>

-   <span data-ttu-id="738ce-109">**管理コンソール**—管理者が管理サーバーとイメージリポジトリを制御できるようにします。</span><span class="sxs-lookup"><span data-stu-id="738ce-109">**Management console**—Enables administrators to control the management server and the image repository.</span></span>

-   **<span data-ttu-id="738ce-110">エンドユーザークライアント</span><span class="sxs-lookup"><span data-stu-id="738ce-110">End-user client</span></span>**

    1.  <span data-ttu-id="738ce-111">仮想イメージのライフサイクル: 認証、イメージ取得、使用ポリシーの適用。</span><span class="sxs-lookup"><span data-stu-id="738ce-111">Virtual image life-cycle—Authentication, image retrieval, enforcement of usage policies.</span></span>

    2.  <span data-ttu-id="738ce-112">仮想マシンセッション管理—仮想マシンを起動、停止、ロックします。</span><span class="sxs-lookup"><span data-stu-id="738ce-112">Virtual machine session management—Start, stop, lock the virtual machine.</span></span>

    3.  <span data-ttu-id="738ce-113">単一のデスクトップエクスペリエンス: 仮想マシンにインストールされたアプリケーションは、標準のデスクトップの [スタート] メニューでシームレスに使用できるようになり、ユーザーデスクトップ上の他のアプリケーションと統合されます。</span><span class="sxs-lookup"><span data-stu-id="738ce-113">Single desktop experience—Applications installed in the virtual machine seamlessly available through the standard desktop Start menu and integrated with other applications on the user desktop.</span></span>

<span data-ttu-id="738ce-114">クライアントとサーバー (管理サーバーとイメージリポジトリ) 間のすべての通信は、標準の HTTP または HTTPS チャネルの上に伝達されます。</span><span class="sxs-lookup"><span data-stu-id="738ce-114">All communication between the client and the servers (management server and image repository) is carried on top of a standard HTTP or HTTPS channel.</span></span>

![](images/506f54d0-38fa-446a-8070-17ae26da5355.gif)

 

 





