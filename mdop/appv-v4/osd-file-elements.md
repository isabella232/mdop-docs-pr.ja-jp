---
title: OSD ファイルの要素
description: OSD ファイルの要素
author: dansimp
ms.assetid: 8211b562-7549-4331-8321-144f52574e99
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a8e3ebcf53ff39ecd2ef7ad0feec0bbbcae199db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816107"
---
# <span data-ttu-id="b575d-103">OSD ファイルの要素</span><span class="sxs-lookup"><span data-stu-id="b575d-103">OSD File Elements</span></span>


<span data-ttu-id="b575d-104">Sequencer のインストールディレクトリには、オープンソフトウェア記述子 (OSD) ファイルの有効な構造を定義する XML スキーマファイル**Softricity**が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b575d-104">The Sequencer installation directory contains an XML schema file, **Softricity.xsd**, which defines the valid structure of an Open Software Descriptor (OSD) file.</span></span> <span data-ttu-id="b575d-105">よく使用される OSD 要素の一部を次に示します。</span><span class="sxs-lookup"><span data-stu-id="b575d-105">Following are some of the more frequently used OSD elements.</span></span>

<a href="" id="softpkg"></a><span data-ttu-id="b575d-106">ソフトパッケージ</span><span class="sxs-lookup"><span data-stu-id="b575d-106">SOFTPKG</span></span>  
<span data-ttu-id="b575d-107">ソフトウェアパッケージを定義するすべての要素を含む OSD ファイルのルート要素です。</span><span class="sxs-lookup"><span data-stu-id="b575d-107">The root element of the OSD file containing all elements defining the software package.</span></span>

<a href="" id="codebase"></a><span data-ttu-id="b575d-108">コード</span><span class="sxs-lookup"><span data-stu-id="b575d-108">CODEBASE</span></span>  
<span data-ttu-id="b575d-109">HREF、FILENAME、GUID の各属性を含む、このパッケージの sft ファイルに関する情報。</span><span class="sxs-lookup"><span data-stu-id="b575d-109">Information about the .sft file for this package, including the HREF, FILENAME, and GUID attributes.</span></span> <span data-ttu-id="b575d-110">HREF 属性は、この特定のパッケージの配布ポイントを変更すると編集できます。</span><span class="sxs-lookup"><span data-stu-id="b575d-110">You can edit the HREF attribute if you change the distribution point of this particular package.</span></span>

<a href="" id="os"></a><span data-ttu-id="b575d-111">OS</span><span class="sxs-lookup"><span data-stu-id="b575d-111">OS</span></span>  
<span data-ttu-id="b575d-112">シーケンスウィザードで最初に設定された値に基づいて、このアプリケーションが実行できるオペレーティングシステムを定義します。</span><span class="sxs-lookup"><span data-stu-id="b575d-112">Defines on what operating systems this application can run based on values that are initially set in the Sequencing Wizard.</span></span> <span data-ttu-id="b575d-113">この値には、 **Softricity**で定義された値のみを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b575d-113">This value can contain only the values defined in **Softricity.xsd**.</span></span>

<a href="" id="local-interaction-allowed"></a><span data-ttu-id="b575d-114">ローカル \ _INTERACTION \ _ALLOWED</span><span class="sxs-lookup"><span data-stu-id="b575d-114">LOCAL\_INTERACTION\_ALLOWED</span></span>  
<span data-ttu-id="b575d-115">TRUE に設定すると、特定の仮想環境内ではなく、グローバル名前空間内で名前付きオブジェクト (イベント、ミューテックス、セマフォー、ファイルマッピング、mailslots) を作成できるようになり、仮想アプリケーションとホストオペレーティングシステムのアプリケーションとのやり取りが可能になります。</span><span class="sxs-lookup"><span data-stu-id="b575d-115">Set to TRUE, this enables creation of named objects (events, mutexes, semaphores, file mappings, and mailslots) and COM objects in the global namespace rather than isolated inside a particular virtual environment, which allows virtual applications to interact with the host operating system's applications.</span></span>

<span data-ttu-id="b575d-116">例: &lt; softpkg の &gt; &lt; 実装&gt;</span><span class="sxs-lookup"><span data-stu-id="b575d-116">Example:&lt;SOFTPKG&gt;&lt;IMPLEMENTATION&gt;</span></span>

<span data-ttu-id="b575d-117">&lt;VIRTUALENV &gt; &lt; ポリシー&gt;</span><span class="sxs-lookup"><span data-stu-id="b575d-117">&lt;VIRTUALENV&gt;&lt;POLICIES&gt;</span></span>

<span data-ttu-id="b575d-118">&lt;ローカル \ _INTERACTION \ _ALLOWED &gt; TRUE</span><span class="sxs-lookup"><span data-stu-id="b575d-118">&lt;LOCAL\_INTERACTION\_ALLOWED&gt;TRUE</span></span>

<span data-ttu-id="b575d-119">&lt;/LOCAL\ _INTERACTION \ _ALLOWED&gt;</span><span class="sxs-lookup"><span data-stu-id="b575d-119">&lt;/LOCAL\_INTERACTION\_ALLOWED&gt;</span></span>

<span data-ttu-id="b575d-120">&lt;/ポリシー &gt; &lt; /VIRTUALENV&gt;</span><span class="sxs-lookup"><span data-stu-id="b575d-120">&lt;/POLICIES&gt;&lt;/VIRTUALENV&gt;</span></span>

<span data-ttu-id="b575d-121">&lt;/実装 &gt; &lt; /ソフトパッケージ&gt;</span><span class="sxs-lookup"><span data-stu-id="b575d-121">&lt;/IMPLEMENTATION&gt;&lt;/SOFTPKG&gt;</span></span>

<a href="" id="dependencies"></a><span data-ttu-id="b575d-122">物</span><span class="sxs-lookup"><span data-stu-id="b575d-122">DEPENDENCIES</span></span>  
<span data-ttu-id="b575d-123">別のパッケージから CODEBASE タグを使用して、動的なスイートコンポジション (他のパッケージに依存) を定義します。</span><span class="sxs-lookup"><span data-stu-id="b575d-123">Defines Dynamic Suite Composition (dependencies on other packages) by using a CODEBASE tag from another package.</span></span>

<span data-ttu-id="b575d-124">例: &lt; 依存 &gt; &lt; コードの HREF = "rtsps://サーバー/package" GUID = "7579 f4df-2461-4219-BD43-469E1FDC E3" sysgu/osguard "SIZE =" 6572748 "/" SIZE = "" 必須 = "FALSE"/ &gt; &lt; /依存関係&gt;</span><span class="sxs-lookup"><span data-stu-id="b575d-124">Example:&lt;DEPENDENCIES&gt;&lt;CODEBASE HREF="rtsps://server/package.sft" GUID="7579F4DF-2461-4219-BD43-494E1FDC69E3" SYSGUARDFILE="pkg.1\\osguard.cp" SIZE="6572748" MANDATORY="FALSE"/&gt;&lt;/DEPENDENCIES&gt;</span></span>

<a href="" id="package-name"></a><span data-ttu-id="b575d-125">パッケージ名</span><span class="sxs-lookup"><span data-stu-id="b575d-125">PACKAGE NAME</span></span>  
<span data-ttu-id="b575d-126">シーケンスウィザードの**パッケージ情報**ページに入力されたパッケージの共通名。複数のアプリケーションを含むシーケンス処理されたアプリケーションに使われる単一の名前を指定できます。</span><span class="sxs-lookup"><span data-stu-id="b575d-126">A common name for the package entered into the Sequencing Wizard **Package Information** page, which enables you to specify a single name used for a sequenced application containing multiple applications.</span></span>

<a href="" id="title"></a><span data-ttu-id="b575d-127">部署</span><span class="sxs-lookup"><span data-stu-id="b575d-127">TITLE</span></span>  
<span data-ttu-id="b575d-128">順序を指定するアプリケーションのわかりやすい名前です。</span><span class="sxs-lookup"><span data-stu-id="b575d-128">Optional descriptive name of the application you are sequencing.</span></span>

<a href="" id="abstract"></a><span data-ttu-id="b575d-129">抽象</span><span class="sxs-lookup"><span data-stu-id="b575d-129">ABSTRACT</span></span>  
<span data-ttu-id="b575d-130">シーケンスウィザードの**パッケージ情報**ページの [**コメント**] フィールドに入力されたソフトウェアパッケージの短い説明。</span><span class="sxs-lookup"><span data-stu-id="b575d-130">Short description of the software package entered in the **Comments** field in the Sequencing Wizard **Package Information** page.</span></span> <span data-ttu-id="b575d-131">ベストプラクティスとしては、Sequencer ワークステーション、Sequencer バージョン、シーケンスエンジニアの名前などのオペレーティングシステムやサービスパックのレベルなどの情報を指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b575d-131">A best practice is to specify information such as the operating system and service-pack level of the Sequencer workstation, Sequencer version, and the sequencing engineer’s name.</span></span>

<a href="" id="script"></a><span data-ttu-id="b575d-132">化</span><span class="sxs-lookup"><span data-stu-id="b575d-132">SCRIPT</span></span>  
<span data-ttu-id="b575d-133">起動、シャットダウン、またはストリーミング中に発生する特定のスクリプトイベントを定義します。</span><span class="sxs-lookup"><span data-stu-id="b575d-133">Defines specific scripted events to occur during startup, shutdown, or streaming.</span></span>

<a href="" id="mgmt-shortcutlist"></a><span data-ttu-id="b575d-134">管理 \ _SHORTCUTLIST</span><span class="sxs-lookup"><span data-stu-id="b575d-134">MGMT\_SHORTCUTLIST</span></span>  
<span data-ttu-id="b575d-135">ウィザードで定義されているすべてのショートカットの一覧です。</span><span class="sxs-lookup"><span data-stu-id="b575d-135">List of all shortcuts defined in the wizard.</span></span>

<a href="" id="mgmt-fileassociations"></a><span data-ttu-id="b575d-136">管理 \ _FILEASSOCIATIONS</span><span class="sxs-lookup"><span data-stu-id="b575d-136">MGMT\_FILEASSOCIATIONS</span></span>  
<span data-ttu-id="b575d-137">ウィザードで指定したファイルの種類の一覧。</span><span class="sxs-lookup"><span data-stu-id="b575d-137">List of the file types specified in the wizard.</span></span>

## <span data-ttu-id="b575d-138">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b575d-138">Related topics</span></span>


[<span data-ttu-id="b575d-139">[OSD] タブについて</span><span class="sxs-lookup"><span data-stu-id="b575d-139">About the OSD Tab</span></span>](about-the-osd-tab.md)

 

 





