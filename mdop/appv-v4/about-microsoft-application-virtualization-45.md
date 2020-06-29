---
title: Microsoft Application Virtualization 4.5 について
description: Microsoft Application Virtualization 4.5 について
author: dansimp
ms.assetid: 39f45a6f-ac55-4fd7-8a83-865e1a7034f8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 30f285680ab24e9c638ff8a200946925074bddf1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820027"
---
# <span data-ttu-id="0fda8-103">Microsoft Application Virtualization 4.5 について</span><span class="sxs-lookup"><span data-stu-id="0fda8-103">About Microsoft Application Virtualization 4.5</span></span>


<span data-ttu-id="0fda8-104">以前は SoftGrid Application Virtualization、Microsoft Application Virtualization (App-v) 4.5 と呼ばれていたのは、製品の最初の Microsoft ブランドリリースです。</span><span class="sxs-lookup"><span data-stu-id="0fda8-104">Formerly known as SoftGrid Application Virtualization, Microsoft Application Virtualization (App-V) 4.5 is the first Microsoft-branded release of the product.</span></span> <span data-ttu-id="0fda8-105">企業の IT 組織が大規模のグローバルアプリケーション仮想化実装を簡単にサポートできるようになる新機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="0fda8-105">It includes new capabilities that make it easy for enterprise IT organizations to support large-scale, global application virtualization implementations.</span></span>

-   <span data-ttu-id="0fda8-106">動的な仮想化: App-v 4.5 は、仮想アプリケーションの操作を柔軟に制御できます。</span><span class="sxs-lookup"><span data-stu-id="0fda8-106">Dynamic Virtualization: App-V 4.5 provides the flexibility to control virtual application interaction.</span></span> <span data-ttu-id="0fda8-107">仮想環境を統合し、より高速で簡単に管理できるようにする管理者は、製品の動的なスイートコンポジションを使用できます。これにより、ミドルウェアアプリケーションのパッケージの順序指定と管理がメインアプリケーションとは別に行われます。</span><span class="sxs-lookup"><span data-stu-id="0fda8-107">Administrators who want to consolidate virtual environments and enable faster, easier administration, can use the product’s Dynamic Suite Composition, which sequences and manages packages for middleware applications separately from the main application.</span></span> <span data-ttu-id="0fda8-108">ミドルウェアの冗長パッケージを除去することで、潜在的なパッケージサイズを圧縮します。</span><span class="sxs-lookup"><span data-stu-id="0fda8-108">It shrinks potential package size by eliminating redundant packaging of middleware.</span></span> <span data-ttu-id="0fda8-109">これにより、複数の Web アプリケーションは、たとえば、Microsoft .NET Framework や Sun Java Runtime Environment (JRE) などの仮想化されたアプリケーションの同じ単一のインスタンスと通信できます。</span><span class="sxs-lookup"><span data-stu-id="0fda8-109">This lets multiple Web applications communicate with the same single instance of a virtualized application of, for example, Microsoft .NET Framework or Sun Java Runtime Environment (JRE).</span></span> <span data-ttu-id="0fda8-110">一般的な仮想ミドルウェアの更新が簡素化され、1つの仮想アプリケーションが複数の方法で更新されます。</span><span class="sxs-lookup"><span data-stu-id="0fda8-110">Updates for the common virtual middleware are simplified and one virtual application is updated instead of several.</span></span> <span data-ttu-id="0fda8-111">この「多対一」の機能により、更新プログラムのコストが大幅に削減されます。</span><span class="sxs-lookup"><span data-stu-id="0fda8-111">This “many-to-one” capability greatly reduces the cost of updates.</span></span> <span data-ttu-id="0fda8-112">また、複数のプラグインとアドインを使用するアプリケーションの展開と管理が簡単になり、さまざまなユーザーグループへのプラグイン配布の管理が向上します。</span><span class="sxs-lookup"><span data-stu-id="0fda8-112">It also makes it easier to deploy and manage applications that use multiple plug-ins and add-ins, and improves management of plug-in distribution to different user groups.</span></span>

-   <span data-ttu-id="0fda8-113">拡張スケーラビリティ: 柔軟性のある3つの展開モードの中から選択します。</span><span class="sxs-lookup"><span data-stu-id="0fda8-113">Extended Scalability: Choose among three flexible deployment modes:</span></span>

    1.  <span data-ttu-id="0fda8-114">Microsoft デスクトップ最適化パックの一部として、またリモートデスクトップサービスパッケージ用の Microsoft Application Virtualization の一部として出荷される Application Virtualization Management Server は、パッケージやアクティブなアップグレードなどの動的ストリーミングを可能にし、Microsoft Active Directory ドメインサービスと Microsoft SQL Server を必要とします。</span><span class="sxs-lookup"><span data-stu-id="0fda8-114">Application Virtualization Management Server, which ships as part of the Microsoft Desktop Optimization Pack and Microsoft Application Virtualization for Remote Desktop Services packages, enables dynamic streaming including package and active upgrades, and requires Microsoft Active Directory Domain Services and Microsoft SQL Server.</span></span>

    2.  <span data-ttu-id="0fda8-115">Application Virtualization Streaming Server、Microsoft デスクトップ最適化パックの一部としても配布される簡易バージョン、およびリモートデスクトップサービスパッケージの Microsoft Application Virtualization には、Active Directory ドメインサービスとデータベースのオーバーヘッドを伴わずにパッケージ化とアクティブなアップグレードを含む、アプリのストリーミング機能を提供し、管理者が既存のサーバーに展開したり、電子ソフトウェア配信 (ESD) システム</span><span class="sxs-lookup"><span data-stu-id="0fda8-115">Application Virtualization Streaming Server, a lightweight version which also ships as part of the Microsoft Desktop Optimization Pack and Microsoft Application Virtualization for Remote Desktop Services packages, offers application streaming including package and active upgrades without the Active Directory Domain Services and database overheads, and enables administrators to deploy to existing servers or add streaming to Electronic Software Delivery (ESD) systems.</span></span>

    3.  <span data-ttu-id="0fda8-116">単体モードでは、仮想アプリケーションはストリーミングなしで実行できます。また、Microsoft Endpoint Configuration Manager とサードパーティの ESD システムとの相互運用も可能です。</span><span class="sxs-lookup"><span data-stu-id="0fda8-116">Standalone mode enables virtual applications to run without streaming and is interoperable with Microsoft Endpoint Configuration Manager and third-party ESD systems.</span></span>

-   <span data-ttu-id="0fda8-117">グローバリゼーション: 製品は11の言語にローカライズされ、特殊文字を使用する外国語アプリケーションのサポート、外国語の Active Directory とサーバー、およびランタイムロケール検出をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0fda8-117">Globalization: The product is localized across 11 languages, includes support for foreign language applications that use special characters, and supports foreign language Active Directory and servers and runtime locale detection.</span></span>

-   <span data-ttu-id="0fda8-118">Microsoft Security 規格: Microsoft Application Virtualization (App-v) 4.5 は、信頼できるコンピューティング、セキュリティで保護された Windows イニシアチブ、セキュリティ開発ライフサイクルなどの Microsoft セキュリティ標準に準拠しています。</span><span class="sxs-lookup"><span data-stu-id="0fda8-118">Microsoft Security Standards: Microsoft Application Virtualization (App-V) 4.5 complies with Microsoft security standards including Trustworthy Computing, Secure Windows Initiative and Security Development Lifecycle.</span></span> <span data-ttu-id="0fda8-119">この機能には、インターネット向けのシナリオのサポートが含まれており、既定の設定によってこのボックスからはセキュリティで保護されています。</span><span class="sxs-lookup"><span data-stu-id="0fda8-119">It includes support for Internet-facing scenarios and provides Secure by Default configuration out of the box.</span></span>

## <span data-ttu-id="0fda8-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="0fda8-120">In This Section</span></span>


<a href="" id="microsoft-application-virtualization-management-system-release-notes"></a>[<span data-ttu-id="0fda8-121">Microsoft Application Virtualization Management System のリリースノート</span><span class="sxs-lookup"><span data-stu-id="0fda8-121">Microsoft Application Virtualization Management System Release Notes</span></span>](microsoft-application-virtualization-management-system-release-notes.md)  
<span data-ttu-id="0fda8-122">Microsoft Application Virtualization (App-v) 4.5 の既知の問題に関する最新情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="0fda8-122">Provides the most up-to-date information about known issues with Microsoft Application Virtualization (App-V) 4.5.</span></span>

 

 





