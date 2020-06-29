---
title: Dynamic Suite Composition を使用する方法
description: Dynamic Suite Composition を使用する方法
author: dansimp
ms.assetid: 24147feb-a0a8-4791-a8e5-cbe5fe13c762
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3bff4c9721352785cf6db5c497234ceaa3c5e448
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816417"
---
# <span data-ttu-id="896d1-103">Dynamic Suite Composition を使用する方法</span><span class="sxs-lookup"><span data-stu-id="896d1-103">How To Use Dynamic Suite Composition</span></span>


<span data-ttu-id="896d1-104">Application Virtualization の動的なスイートコンポジションを使用すると、ミドルウェアやプラグインなどの別のアプリケーションに依存するようにアプリケーションを定義できます。</span><span class="sxs-lookup"><span data-stu-id="896d1-104">Dynamic Suite Composition in Application Virtualization enables you to define an application as being dependent on another application, such as middleware or a plug-in.</span></span> <span data-ttu-id="896d1-105">これにより、アプリケーションは仮想環境内のミドルウェアまたはプラグインを操作することができます。これは、通常は禁止されています。</span><span class="sxs-lookup"><span data-stu-id="896d1-105">This enables the application to interact with the middleware or plug-in in the virtual environment, where typically this is prevented.</span></span> <span data-ttu-id="896d1-106">これは、*プライマリアプリケーションと*呼ばれる他のいくつかのアプリケーションと共にセカンダリアプリケーションパッケージを使用して、各プライマリアプリケーションが同じセカンダリパッケージを参照できるようにするために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="896d1-106">This is useful because a secondary application package can be used with several other applications, referred to as the *primary applications*, which enables each primary application to reference the same secondary package.</span></span>

<span data-ttu-id="896d1-107">動的スイートコンポジションは、ActiveX コントロールなどのプラグインに依存するアプリケーションや、OLE DB や Java Runtime Environment (JRE) などのミドルウェアに依存するアプリケーションに対しても使用できます。</span><span class="sxs-lookup"><span data-stu-id="896d1-107">You can use Dynamic Suite Composition when you sequence applications that depend on plug-ins such as ActiveX controls or for applications that depend on middleware such as OLE DB or the Java Runtime Environment (JRE).</span></span> <span data-ttu-id="896d1-108">これらの依存コンポーネントを使用した各アプリケーションで、コンポーネントなどの順序指定が必要である場合、これらのコンポーネントの更新には、すべてのプライマリアプリケーションの順序を再適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="896d1-108">If each application that used these dependent components required sequencing, including the components, updates to those components would require re-sequencing all the primary applications.</span></span> <span data-ttu-id="896d1-109">コンポーネントを使わずにプライマリアプリケーションをシーケンスして、ミドルウェアまたはプラグインをセカンダリパッケージとしてシーケンスする場合は、セカンダリパッケージのみを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="896d1-109">If you sequence the primary applications without the components and then sequence the middleware or plug-in as a secondary package, then only the secondary package must be updated.</span></span>

<span data-ttu-id="896d1-110">この方法の1つの利点は、プライマリパッケージのサイズが小さくなることです。</span><span class="sxs-lookup"><span data-stu-id="896d1-110">One advantage of this approach is that it reduces the size of the primary packages.</span></span> <span data-ttu-id="896d1-111">もう1つの利点は、セカンダリアプリケーションに対するアクセス許可をより適切に制御できることです。</span><span class="sxs-lookup"><span data-stu-id="896d1-111">Another advantage is that it provides you with better control of access permissions on the secondary applications.</span></span> <span data-ttu-id="896d1-112">セカンダリアプリケーションは、通常の方法でストリーミングできます。また、実行するために完全にキャッシュする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="896d1-112">Note that the secondary application can be streamed in the regular way and does not have to be fully cached to run.</span></span>

<span data-ttu-id="896d1-113">プライマリパッケージには、複数のセカンダリパッケージを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="896d1-113">A primary package can have more than one secondary package.</span></span> <span data-ttu-id="896d1-114">ただし、依存関係のレベルは1つしかサポートされていないため、セカンダリパッケージを別のセカンダリパッケージに依存するように定義することはできません。</span><span class="sxs-lookup"><span data-stu-id="896d1-114">However, only one level of dependency is supported, so you cannot define a secondary package as dependent on another secondary package.</span></span> <span data-ttu-id="896d1-115">また、セカンダリアプリケーションは、ミドルウェアまたはプラグインとしてのみ使用できます。また、その他の完全なソフトウェア製品にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="896d1-115">Also the secondary application can only be middleware or a plug-in and cannot be another full software product.</span></span>

<span data-ttu-id="896d1-116">複数の主要なアプリケーションを1つのミドルウェア製品に依存することを計画している場合は、この構成をテストして、展開する前にシステムパフォーマンスへの影響を与える可能性があることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="896d1-116">If you plan to make several primary applications dependent on a single middleware product, make sure that you test this configuration to determine the potential effect on system performance before you deploy it.</span></span>

<span data-ttu-id="896d1-117">**重要** パッケージの依存関係は、プライマリアプリケーションに対して必須として指定できます。</span><span class="sxs-lookup"><span data-stu-id="896d1-117">**Important** Package dependencies can be specified as mandatory for a primary application.</span></span> <span data-ttu-id="896d1-118">セカンダリパッケージが必須としてマークされ、読み込み中に何らかの理由でアクセスできない場合、セカンダリパッケージの読み込みは失敗します。</span><span class="sxs-lookup"><span data-stu-id="896d1-118">If a secondary package is flagged as mandatory and it cannot be accessed for some reason during loading, the load of the secondary package will fail.</span></span> <span data-ttu-id="896d1-119">また、プライマリアプリケーションは、ユーザーがアプリを起動しようとしたときに失敗します。</span><span class="sxs-lookup"><span data-stu-id="896d1-119">Also, the primary application will fail when the user tries to start it.</span></span>

 

<span data-ttu-id="896d1-120">次の手順を使用して、プラグインまたはミドルウェアコンポーネント用にセカンダリパッケージを作成することができます。その後、最後の手順を使用して、セカンダリパッケージの OSD ファイルで依存関係を定義できます。</span><span class="sxs-lookup"><span data-stu-id="896d1-120">You can use the following procedures to create a secondary package, for either a plug-in or a middleware component, and then you can use the final procedure to define the dependency in the OSD file of the secondary package.</span></span>

**<span data-ttu-id="896d1-121">動的スイートコンポジションを使用してプラグインのセカンダリパッケージを作成するには</span><span class="sxs-lookup"><span data-stu-id="896d1-121">To create a secondary package for a plug-in by using Dynamic Suite Composition</span></span>**

1.  <span data-ttu-id="896d1-122">クリーンイメージで設定されているシーケンスコンピューターでは、Application Virtualization Sequencer をインストールして、コンピューターの状態を保存します。</span><span class="sxs-lookup"><span data-stu-id="896d1-122">On a sequencing computer that is set up with a clean image, install Application Virtualization Sequencer and save the computer state.</span></span>

2.  <span data-ttu-id="896d1-123">プライマリアプリケーションをシーケンスし、サーバーのコンテンツフォルダーにパッケージを保存します。</span><span class="sxs-lookup"><span data-stu-id="896d1-123">Sequence the primary application, and save the package to the Content folder on the server.</span></span>

3.  <span data-ttu-id="896d1-124">優先順位のコンピューターを手順1の保存された状態に復元します。</span><span class="sxs-lookup"><span data-stu-id="896d1-124">Restore the sequencing computer to its saved state from step 1.</span></span>

4.  <span data-ttu-id="896d1-125">優先順位のコンピューターで、プライマリアプリケーションをローカルにインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="896d1-125">Install and configure the primary application locally on the sequencing computer.</span></span>

    <span data-ttu-id="896d1-126">**重要** セカンダリパッケージ用の新しいパッケージルートを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="896d1-126">**Important** You must specify a new package root for the secondary package.</span></span>

     

5.  <span data-ttu-id="896d1-127">Sequencer 監視フェーズを開始します。</span><span class="sxs-lookup"><span data-stu-id="896d1-127">Start the sequencer monitoring phase.</span></span>

6.  <span data-ttu-id="896d1-128">シーケンスコンピューターにプラグインをインストールし、必要に応じて構成します。</span><span class="sxs-lookup"><span data-stu-id="896d1-128">Install the plug-in on the sequencing computer and configure it as needed.</span></span>

7.  <span data-ttu-id="896d1-129">プライマリアプリケーションを開き、プラグインが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="896d1-129">Open the primary application, and confirm that the plug-in is working correctly.</span></span>

8.  <span data-ttu-id="896d1-130">Sequencer コンソールで、プラグインを含むセカンダリパッケージを表すダミーアプリケーションを作成し、アイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="896d1-130">In the sequencer console, create a dummy application to represent the secondary package that will contain the plug-in and select an icon.</span></span>

9.  <span data-ttu-id="896d1-131">パッケージをサーバーのコンテンツフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="896d1-131">Save the package to the Content folder on the server.</span></span>

    <span data-ttu-id="896d1-132">**注** セカンダリパッケージを管理するには、パッケージ名に "セカンダリパッケージ" という用語を含めることをお勧めします。これは、 **\ [プラグイン名 \] セカンダリパッケージ**など、スタンドアロンアプリケーションとしては機能しないパッケージであることを強調することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="896d1-132">**Note** To assist with management of secondary packages, it is recommended that the package name include the term “Secondary package” to emphasize that this is a package that will not function as a stand-alone application—for example, **\[Plug In Name\] Secondary package**.</span></span>

     

**<span data-ttu-id="896d1-133">動的スイートコンポジションを使用してミドルウェア用のセカンダリパッケージを作成するには</span><span class="sxs-lookup"><span data-stu-id="896d1-133">To create a secondary package for middleware by using Dynamic Suite Composition</span></span>**

1.  <span data-ttu-id="896d1-134">クリーンイメージで設定されているシーケンスコンピューターでは、Application Virtualization Sequencer をインストールして、コンピューターの状態を保存します。</span><span class="sxs-lookup"><span data-stu-id="896d1-134">On a sequencing computer that is set up with a clean image, install Application Virtualization Sequencer and save the computer state.</span></span>

2.  <span data-ttu-id="896d1-135">優先順位のコンピューターに、ミドルウェアをローカルにインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="896d1-135">Install the middleware locally on the sequencing computer, and configure it.</span></span>

3.  <span data-ttu-id="896d1-136">プライマリアプリケーションをシーケンスし、サーバーのコンテンツフォルダーにパッケージを保存します。</span><span class="sxs-lookup"><span data-stu-id="896d1-136">Sequence the primary application, and save the package to the Content folder on the server.</span></span>

4.  <span data-ttu-id="896d1-137">優先順位のコンピューターを手順1の保存された状態に復元します。</span><span class="sxs-lookup"><span data-stu-id="896d1-137">Restore the sequencing computer to its saved state from step 1.</span></span>

5.  <span data-ttu-id="896d1-138">Sequencer を起動して新しいパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="896d1-138">Start the sequencer to create a new package.</span></span>

6.  <span data-ttu-id="896d1-139">Sequencer 監視フェーズを開始します。</span><span class="sxs-lookup"><span data-stu-id="896d1-139">Start the sequencer monitoring phase.</span></span>

7.  <span data-ttu-id="896d1-140">優先順位のコンピューターにミドルウェアアプリケーションをインストールして、標準インストールの場合と同様に構成します。</span><span class="sxs-lookup"><span data-stu-id="896d1-140">Install the middleware application on the sequencing computer, and configure it as in a typical installation.</span></span>

8.  <span data-ttu-id="896d1-141">シーケンス処理を完了します。</span><span class="sxs-lookup"><span data-stu-id="896d1-141">Complete the sequencing process.</span></span>

9.  <span data-ttu-id="896d1-142">パッケージをサーバーのコンテンツフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="896d1-142">Save the package to the Content folder on the server.</span></span>

    <span data-ttu-id="896d1-143">**注** セカンダリパッケージの管理に役立てるために、パッケージ名に "セカンダリパッケージ" という用語を含めることをお勧めします。これは、スタンドアロンアプリケーションとして機能しないパッケージ ( **\ [ミドルウェア名 \] セカンダリパッケージ**など) であることを強調することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="896d1-143">**Note** To assist with management of secondary packages, it is recommended that the package name include the term “Secondary package” to emphasize that this is a package that will not function as a stand-alone application—for example, **\[Middleware Name\] Secondary package**.</span></span>

     

**<span data-ttu-id="896d1-144">プライマリパッケージの依存関係を定義するには</span><span class="sxs-lookup"><span data-stu-id="896d1-144">To define the dependency in the primary package</span></span>**

1. <span data-ttu-id="896d1-145">サーバーで、編集するセカンダリパッケージの OSD ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="896d1-145">On the server, open the OSD file of the secondary package for editing.</span></span> <span data-ttu-id="896d1-146">(OSD ファイルに変更を加える場合は、XML エディターを使うことをお勧めします。ただし、メモ帳を代替として使用することをお勧めします)。</span><span class="sxs-lookup"><span data-stu-id="896d1-146">(It is a good idea to use an XML editor to make changes to the OSD file; however, you can use Notepad as an alternative.)</span></span>

2. <span data-ttu-id="896d1-147">そのファイルから**コードベース HREF**をコピーします。</span><span class="sxs-lookup"><span data-stu-id="896d1-147">Copy the **CODEBASE HREF** line from that file.</span></span>

3. <span data-ttu-id="896d1-148">編集するプライマリパッケージの OSD ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="896d1-148">Open the OSD file of the primary package for editing.</span></span>

4. <span data-ttu-id="896d1-149"><strong> &lt; &gt; </strong> \*\* &lt; /ENVLIST &gt; \*\*タグの終わりの後に、 \*\* &lt; /virtualenv &gt; **タグの直前に** &lt; &gt; \*\*ある [依存関係] タグを挿入します。</span><span class="sxs-lookup"><span data-stu-id="896d1-149">Insert the <strong>&lt;DEPENDENCIES&gt;</strong>tag after the close of **&lt;/ENVLIST&gt;** tag at the end of the **&lt;VIRTUALENV&gt;** section just before the **&lt;/VIRTUALENV&gt;** tag.</span></span>

5. <span data-ttu-id="896d1-150">作成した\*\* &lt; 依存性 &gt; **タグの後に、セカンダリパッケージから**コードベース HREF\*\*を貼り付けます。</span><span class="sxs-lookup"><span data-stu-id="896d1-150">Paste the **CODEBASE HREF** line from the secondary package after the **&lt;DEPENDENCIES&gt;** tag you just created.</span></span>

6. <span data-ttu-id="896d1-151">セカンダリパッケージが、プライマリパッケージを開始する前に開始する必要があることを意味する必須パッケージである場合は、 **CODEBASE**タグ内に**必須の "TRUE"** プロパティを追加します。</span><span class="sxs-lookup"><span data-stu-id="896d1-151">If the secondary package is a mandatory package, which means that it must be started before the primary package is started, add the **MANDATORY=”TRUE”** property inside the **CODEBASE** tag.</span></span> <span data-ttu-id="896d1-152">必須でない場合は、プロパティを省略できます。</span><span class="sxs-lookup"><span data-stu-id="896d1-152">If it is not mandatory, the property can be omitted.</span></span>

7. <span data-ttu-id="896d1-153">次の内容を挿入して、 \*\* &lt; 依存性 &gt; \*\*タグを閉じます。</span><span class="sxs-lookup"><span data-stu-id="896d1-153">Close the **&lt;DEPENDENCIES&gt;** tag by inserting the following:</span></span>

   **<span data-ttu-id="896d1-154">&lt;/依存関係&gt;</span><span class="sxs-lookup"><span data-stu-id="896d1-154">&lt;/DEPENDENCIES&gt;</span></span>**

8. <span data-ttu-id="896d1-155">OSD ファイルに加えた変更を確認してから、ファイルを保存して閉じます。</span><span class="sxs-lookup"><span data-stu-id="896d1-155">Review the changes that you made to the OSD file, and then save and close the file.</span></span> <span data-ttu-id="896d1-156">次の例は、追加されたセクションを表示する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="896d1-156">The following example shows how the added section should appear.</span></span> <span data-ttu-id="896d1-157">ここに示すタグ値は、たとえば、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="896d1-157">The tag values shown here are for example only.</span></span>

   **<span data-ttu-id="896d1-158">&lt;VIRTUALENV&gt;</span><span class="sxs-lookup"><span data-stu-id="896d1-158">&lt;VIRTUALENV&gt;</span></span>**

        **&lt;ENVLIST&gt;**

   **<span data-ttu-id="896d1-159">…</span><span class="sxs-lookup"><span data-stu-id="896d1-159">…</span></span>**

        **&lt;/ENVLIST&gt;**

        **&lt;DEPENDENCIES&gt;**

             **&lt;CODEBASE HREF="rtsp://virt\_apps/package.1/package.1.sft" GUID="D54C80FA-9DFF-459D-AA33-DD852C9FBFBA" SYSGUARDFILE="package.1\\osguard.cp"/&gt;**

             **&lt;CODEBASE HREF="rtsp://sample\_apps/package.2/sample.sft" GUID="D54C80FA-9DFF-459D-AA33-DD852C9FBFBA" SYSGUARDFILE="package.2\\osguard.cp" MANDATORY="TRUE" /&gt;**

        **&lt;/DEPENDENCIES&gt;**

   **<span data-ttu-id="896d1-160">&lt;/仮想 env&gt;</span><span class="sxs-lookup"><span data-stu-id="896d1-160">&lt;/VIRTUALENV&gt;</span></span>**

9. <span data-ttu-id="896d1-161">セカンダリパッケージの OSD ファイルの\*\* &lt; ENVLIST &gt; \*\*セクションにエントリがある場合は、それらのエントリをプライマリパッケージの同じセクションにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="896d1-161">If the secondary package has any entries in the **&lt;ENVLIST&gt;** section of the OSD file, you must copy those entries to the same section in the primary package.</span></span>

## <span data-ttu-id="896d1-162">関連トピック</span><span class="sxs-lookup"><span data-stu-id="896d1-162">Related topics</span></span>


[<span data-ttu-id="896d1-163">App-v Sequencer を使用して仮想アプリケーションを作成またはアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="896d1-163">How to Create or Upgrade Virtual Applications Using the App-V Sequencer</span></span>](how-to-create-or-upgrade-virtual-applications-using--the-app-v-sequencer.md)

 

 





