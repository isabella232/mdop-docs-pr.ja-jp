---
title: MED-V のインストールの前提条件
description: MED-V のインストールの前提条件
author: dansimp
ms.assetid: cf3c0906-23eb-4c4a-8951-a65741720f95
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2b432b8c2b06e171eb339aab6c7b15efb20d5919
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824967"
---
# <span data-ttu-id="f25d4-103">MED-V のインストールの前提条件</span><span class="sxs-lookup"><span data-stu-id="f25d4-103">MED-V Installation Prerequisites</span></span>


<span data-ttu-id="f25d4-104">次に、MED-V をインストールするための前提条件を示します。</span><span class="sxs-lookup"><span data-stu-id="f25d4-104">The following are prerequisites for installing MED-V:</span></span>

[<span data-ttu-id="f25d4-105">Active Directory の要件</span><span class="sxs-lookup"><span data-stu-id="f25d4-105">Active Directory Requirements</span></span>](#bkmk-activedirectoryrequirements)

[<span data-ttu-id="f25d4-106">レポートデータベース</span><span class="sxs-lookup"><span data-stu-id="f25d4-106">Report Database</span></span>](#bkmk-howtoinstallthereportdatabase)

[<span data-ttu-id="f25d4-107">ウイルス対策/バックアップソフトウェアの構成</span><span class="sxs-lookup"><span data-stu-id="f25d4-107">Antivirus/Backup Software Configuration</span></span>](#bkmk-antivirusbackupsoftwareconfiguration)

[<span data-ttu-id="f25d4-108">Microsoft Virtual PC 2007 SP1</span><span class="sxs-lookup"><span data-stu-id="f25d4-108">Microsoft Virtual PC 2007 SP1</span></span>](#bkmk-howtoinstallandconfiguremicrosoftvirtualpc2007sp1)

## <a href="" id="bkmk-activedirectoryrequirements"></a><span data-ttu-id="f25d4-109">Active Directory の要件</span><span class="sxs-lookup"><span data-stu-id="f25d4-109">Active Directory Requirements</span></span>


<span data-ttu-id="f25d4-110">ユーザーがサーバーが属しているドメインと同じドメインに属していない場合は、MED-V サーバーを構成するときに、ドメイン間に信頼を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f25d4-110">When configuring the MED-V server, if users are not part of the same domain the server belongs to, a trust must be set between the domains.</span></span>

## <a href="" id="bkmk-howtoinstallthereportdatabase"></a><span data-ttu-id="f25d4-111">レポートデータベースのインストール方法</span><span class="sxs-lookup"><span data-stu-id="f25d4-111">How to Install the Report Database</span></span>


<span data-ttu-id="f25d4-112">すべての MED-V ワークスペースログを保存するには、レポートデータベースが必要です。</span><span class="sxs-lookup"><span data-stu-id="f25d4-112">The report database is required for storing all MED-V workspace logs.</span></span> <span data-ttu-id="f25d4-113">ログデータベースは、MED-V レポートを生成するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f25d4-113">The log database is then used for generating MED-V reports.</span></span> <span data-ttu-id="f25d4-114">レポートの詳細については、「 [Med-v レポート](med-v-reporting.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f25d4-114">For information about reports, see [MED-V Reporting](med-v-reporting.md).</span></span>

<span data-ttu-id="f25d4-115">SQL Server は、MED-V サーバーまたはリモートサーバーと同じサーバーにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f25d4-115">SQL Server can be installed on the same server as the MED-V server or on a remote server.</span></span> <span data-ttu-id="f25d4-116">リモートサーバーにインストールする場合は、「[リモートサーバーに SQL server をインストール](#bkmk-installingsqlserveronaremoteserver)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f25d4-116">If installing on a remote server, see [Installing SQL Server on a Remote Server](#bkmk-installingsqlserveronaremoteserver).</span></span>

### <a href="" id="bkmk-installingsqlserveronaremoteserver"></a><span data-ttu-id="f25d4-117">リモートサーバーへの SQL Server のインストール</span><span class="sxs-lookup"><span data-stu-id="f25d4-117">Installing SQL Server on a Remote Server</span></span>

**<span data-ttu-id="f25d4-118">リモートサーバーに SQL Server をインストールするには</span><span class="sxs-lookup"><span data-stu-id="f25d4-118">To install SQL Server on a remote server</span></span>**

1.  <span data-ttu-id="f25d4-119">リモートサーバーで次のように構成します。</span><span class="sxs-lookup"><span data-stu-id="f25d4-119">Configure the following on the remote server:</span></span>

    -   <span data-ttu-id="f25d4-120">インスタンス名—既定のインスタンス</span><span class="sxs-lookup"><span data-stu-id="f25d4-120">Instance name—Default instance</span></span>

    -   <span data-ttu-id="f25d4-121">認証モード (混在モード)</span><span class="sxs-lookup"><span data-stu-id="f25d4-121">Authentication mode—Mixed mode</span></span>

    -   <span data-ttu-id="f25d4-122">ユーザー: 作成された既定のユーザーは "sa" です。</span><span class="sxs-lookup"><span data-stu-id="f25d4-122">User—The default user created is “sa”</span></span>

    -   <span data-ttu-id="f25d4-123">パスワード: 目的のパスワード</span><span class="sxs-lookup"><span data-stu-id="f25d4-123">Password—Desired password</span></span>

    -   <span data-ttu-id="f25d4-124">照合順序の設定—既定</span><span class="sxs-lookup"><span data-stu-id="f25d4-124">Collation Settings—Default</span></span>

    -   <span data-ttu-id="f25d4-125">利用状況レポートの設定でエラーが発生した場合 (既定)</span><span class="sxs-lookup"><span data-stu-id="f25d4-125">Error in usage report settings—Default</span></span>

2.  <span data-ttu-id="f25d4-126">MED-V サーバーに次のファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f25d4-126">Install the following files on the MED-V server:</span></span>

    -   <span data-ttu-id="f25d4-127">Microsoft SQL Server2008 の管理パックオブジェクトコレクションの前提条件をインストールするには、microsoft ダウンロードセンターから[MICROSOFT Sql Server2008 Native Client](https://go.microsoft.com/fwlink/?LinkId=164039)をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="f25d4-127">To install the prerequisites for the management pack objects collection for Microsoft SQL Server2008, download [Microsoft SQL Server2008 Native Client](https://go.microsoft.com/fwlink/?LinkId=164039) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="f25d4-128">Microsoft SQL Server2005 の管理パックオブジェクトコレクションの前提条件をインストールするには、microsoft ダウンロードセンターから[MICROSOFT Sql Server2005 Native Client](https://go.microsoft.com/fwlink/?LinkId=164038)をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="f25d4-128">To install the prerequisites for the management pack objects collection for Microsoft SQL Server2005, download [Microsoft SQL Server2005 Native Client](https://go.microsoft.com/fwlink/?LinkId=164038) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="f25d4-129">Microsoft SQL Server2008 に必要な dll ファイルをインストールするには、microsoft ダウンロードセンターから[MICROSOFT Sql Server 2008 管理オブジェクトコレクション](https://go.microsoft.com/fwlink/?LinkId=164041)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f25d4-129">To install the required dll files for Microsoft SQL Server2008, download [Microsoft SQL Server 2008 Management Objects Collection](https://go.microsoft.com/fwlink/?LinkId=164041) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="f25d4-130">Microsoft SQL Server2005 に必要な dll ファイルをインストールするには、microsoft ダウンロードセンターから[MICROSOFT Sql Server2005 管理オブジェクト](https://go.microsoft.com/fwlink/?LinkId=164040)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f25d4-130">To install the required dll files for Microsoft SQL Server2005, download [Microsoft SQL Server2005 Management Objects](https://go.microsoft.com/fwlink/?LinkId=164040) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="f25d4-131">SQL Server2008 の追加の値を提供する単体インストールパッケージをインストールするには、microsoft ダウンロードセンターから[MICROSOFT SQL Server2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=163960)をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="f25d4-131">To install the stand-alone install packages that provide additional value for SQL Server2008, download the [Microsoft SQL Server2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=163960) from the Microsoft Download Center.</span></span>

    -   <span data-ttu-id="f25d4-132">SQL Server2005 の追加の値を提供する単体インストールパッケージをインストールするには、Microsoft ダウンロードセンターから[MICROSOFT SQL Server2005 の Feature Pack]( https://go.microsoft.com/fwlink/?LinkId=163961)をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="f25d4-132">To install the stand-alone install packages that provide additional value for SQL Server2005, download the [Feature Pack for Microsoft SQL Server2005]( https://go.microsoft.com/fwlink/?LinkId=163961) from the Microsoft Download Center.</span></span>

    <span data-ttu-id="f25d4-133">これらのファイルの詳細について[Microsoft SQL Server2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=163960)は、Microsoft ダウンロードセンター ( https://go.microsoft.com/fwlink/?LinkId=163960) または microsoft ダウンロードセンターの[機能パック Server2008 の feature](https://go.microsoft.com/fwlink/?LinkId=163961) pack () を参照してください https://go.microsoft.com/fwlink/?LinkId=163961) 。</span><span class="sxs-lookup"><span data-stu-id="f25d4-133">For more information about these files, see [Microsoft SQL Server2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=163960) on the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=163960) or [Feature Pack for Microsoft SQL Server2005](https://go.microsoft.com/fwlink/?LinkId=163961) on the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=163961).</span></span>

## <a href="" id="bkmk-antivirusbackupsoftwareconfiguration"></a><span data-ttu-id="f25d4-134">ウイルス対策/バックアップソフトウェアの構成</span><span class="sxs-lookup"><span data-stu-id="f25d4-134">Antivirus/Backup Software Configuration</span></span>


<span data-ttu-id="f25d4-135">ウイルス対策によって仮想デスクトップのパフォーマンスが影響を受けないようにするには、ホストで実行されているすべてのウイルス対策またはバックアップ処理から、次の仮想マシンのファイルの種類を除外することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f25d4-135">To prevent antivirus activity from affecting the performance of the virtual desktop, it is recommended where possible to exclude the following virtual machine file types from any antivirus or backup processing running on the host:</span></span>

-   <span data-ttu-id="f25d4-136">\*..VMC</span><span class="sxs-lookup"><span data-stu-id="f25d4-136">\*.VMC</span></span>

-   <span data-ttu-id="f25d4-137">\*.VUD</span><span class="sxs-lookup"><span data-stu-id="f25d4-137">\*.VUD</span></span>

-   <span data-ttu-id="f25d4-138">\*.VSV</span><span class="sxs-lookup"><span data-stu-id="f25d4-138">\*.VSV</span></span>

-   <span data-ttu-id="f25d4-139">\*.CKM</span><span class="sxs-lookup"><span data-stu-id="f25d4-139">\*.CKM</span></span>

-   <span data-ttu-id="f25d4-140">\*.EVHD</span><span class="sxs-lookup"><span data-stu-id="f25d4-140">\*.EVHD</span></span>

## <a href="" id="bkmk-howtoinstallandconfiguremicrosoftvirtualpc2007sp1"></a><span data-ttu-id="f25d4-141">Microsoft Virtual PC2007 SP1 をインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="f25d4-141">How to Install and Configure Microsoft Virtual PC2007 SP1</span></span>


<span data-ttu-id="f25d4-142">**重要** Windows 用仮想 PC がホストコンピューターに存在する場合は、Virtual PC2007 SP1 をインストールする前にアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="f25d4-142">**Important** If Virtual PC for Windows exists on the host computer, uninstall it before installing Virtual PC2007 SP1.</span></span>

 

**<span data-ttu-id="f25d4-143">Microsoft Virtual PC2007 SP1 をインストールするには</span><span class="sxs-lookup"><span data-stu-id="f25d4-143">To install Microsoft Virtual PC2007 SP1</span></span>**

1.  <span data-ttu-id="f25d4-144">Microsoft ダウンロードセンター [VIRTUAL PC 2007 sp1](https://go.microsoft.com/fwlink/?LinkId=142994)から VIRTUAL PC2007 SP1 をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f25d4-144">Download Virtual PC2007 SP1 from the Microsoft Download Center [Virtual PC 2007 SP1](https://go.microsoft.com/fwlink/?LinkId=142994).</span></span>

2.  <span data-ttu-id="f25d4-145">ホストコンピューターでインストールファイルを実行し、ウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="f25d4-145">Run the installation file on the host computer, and follow the wizard.</span></span>

3.  <span data-ttu-id="f25d4-146">昇格モードでホストコンピューターに Virtual PC2007 SP1 更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="f25d4-146">Install Virtual PC2007 SP1 update on the host computer in elevated mode.</span></span>

    <span data-ttu-id="f25d4-147">詳細については、「 [VIRTUAL PC 2007 SP1 の修正プログラムパッケージの説明](https://go.microsoft.com/fwlink/?LinkId=150575)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f25d4-147">For more information, see [the description of the hotfix package for Virtual PC 2007 SP1](https://go.microsoft.com/fwlink/?LinkId=150575).</span></span>

    <span data-ttu-id="f25d4-148">**注** Virtual PC2007 SP1 を実行するには、Virtual PC2007 SP1 更新プログラムが必要です。</span><span class="sxs-lookup"><span data-stu-id="f25d4-148">**Note** The Virtual PC2007 SP1 update is required for running Virtual PC2007 SP1.</span></span>

     

## <span data-ttu-id="f25d4-149">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f25d4-149">Related topics</span></span>


[<span data-ttu-id="f25d4-150">サポートされる構成</span><span class="sxs-lookup"><span data-stu-id="f25d4-150">Supported Configurations</span></span>](supported-configurationsmedv-orientation.md)

 

 





