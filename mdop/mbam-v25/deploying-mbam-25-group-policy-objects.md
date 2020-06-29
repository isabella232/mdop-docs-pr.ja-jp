---
title: MBAM 2.5 グループ ポリシー オブジェクトの展開
description: MBAM 2.5 グループ ポリシー オブジェクトの展開
author: dansimp
ms.assetid: 4b835054-6846-463d-af58-8ac4639a1188
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9624b94e9d4808a35e1199290f4cd90a8122f767
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824387"
---
# <span data-ttu-id="10548-103">MBAM 2.5 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="10548-103">Deploying MBAM 2.5 Group Policy Objects</span></span>


<span data-ttu-id="10548-104">MBAM を展開するには、BitLocker ドライブ暗号化の MBAM 実装設定を定義するグループポリシー設定を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10548-104">To deploy MBAM, you have to set Group Policy settings that define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="10548-105">このタスクを完了するには、MBAM グループポリシーテンプレートを、グループポリシー管理コンソール (GPMC) または Advanced グループポリシー管理 (AGPM) を実行できるサーバーまたはワークステーションにコピーして、設定を編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10548-105">To complete this task, you must copy the MBAM Group Policy Templates to a server or workstation that are capable of running Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM), and then edit the settings.</span></span>

<span data-ttu-id="10548-106">**重要** **BitLocker ドライブ暗号化**ノードのグループポリシー設定を変更しないようにします。または、mbam が正しく動作しません。</span><span class="sxs-lookup"><span data-stu-id="10548-106">**Important** Do not change the Group Policy settings in the **BitLocker Drive Encryption** node, or MBAM will not work correctly.</span></span> <span data-ttu-id="10548-107">[ **MDOP mbam (BitLocker Management)** ] ノードでグループポリシー設定を構成すると、mbam が自動的に**bitlocker ドライブ暗号化**設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="10548-107">When you configure the Group Policy settings in the **MDOP MBAM (BitLocker Management)** node, MBAM automatically configures the **BitLocker Drive Encryption** settings for you.</span></span>

 

## <span data-ttu-id="10548-108">MBAM 2.5 グループ ポリシー テンプレートのコピー</span><span class="sxs-lookup"><span data-stu-id="10548-108">Copying the MBAM 2.5 Group Policy Templates</span></span>


<span data-ttu-id="10548-109">MBAM クライアントをインストールする前に、MBAM 固有のグループポリシーオブジェクト (Gpo) を管理ワークステーションにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="10548-109">Before you install the MBAM Client, you must copy MBAM-specific Group Policy Objects (GPOs) to the Management Workstation.</span></span> <span data-ttu-id="10548-110">これらの Gpo は、BitLocker ドライブ暗号化用の MBAM 実装設定を定義します。</span><span class="sxs-lookup"><span data-stu-id="10548-110">These GPOs define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="10548-111">グループポリシーテンプレートは、サポートされている Windows サーバーまたはクライアントコンピューターであり、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を実行できる任意のサーバーまたはワークステーションにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="10548-111">You can copy the Group Policy templates to any server or workstation that is a supported Windows server or client computer and that is able to run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

[<span data-ttu-id="10548-112">MBAM 2.5 グループ ポリシー テンプレートのコピー</span><span class="sxs-lookup"><span data-stu-id="10548-112">Copying the MBAM 2.5 Group Policy Templates</span></span>](copying-the-mbam-25-group-policy-templates.md)

## <span data-ttu-id="10548-113">MBAM 2.0 GPO 設定の編集</span><span class="sxs-lookup"><span data-stu-id="10548-113">Editing MBAM 2.0 GPO settings</span></span>


<span data-ttu-id="10548-114">必要な Gpo を作成したら、MBAM グループポリシー設定を組織のクライアントコンピューターに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10548-114">After you create the necessary GPOs, you must deploy the MBAM Group Policy settings to your organization’s client computers.</span></span> <span data-ttu-id="10548-115">Gpo を表示および作成するには、グループポリシー管理コンソール (GPMC) または Advanced グループポリシー管理 (AGPM) がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="10548-115">To view and create GPOs, you must have Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM) installed.</span></span>

[<span data-ttu-id="10548-116">MBAM 2.5 グループ ポリシー設定の編集</span><span class="sxs-lookup"><span data-stu-id="10548-116">Editing the MBAM 2.5 Group Policy Settings</span></span>](editing-the-mbam-25-group-policy-settings.md)

## <span data-ttu-id="10548-117">Windows のコントロールパネルで MBAM コントロールパネルを表示または非表示にする</span><span class="sxs-lookup"><span data-stu-id="10548-117">Showing or hiding the MBAM Control Panel in Windows Control Panel</span></span>


<span data-ttu-id="10548-118">MBAM はカスタマイズされた MBAM コントロールパネルを提供して、既定の Windows BitLocker コントロールパネルを置き換えることができるため、グループポリシー設定を使用して、エンドユーザーに対して既定の BitLocker コントロールパネルの表示と非表示を切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="10548-118">Since MBAM offers a customized MBAM control panel that can replace the default Windows BitLocker control panel, you can also choose to show or hide the default BitLocker Control Panel from end users by using Group Policy settings.</span></span>

[<span data-ttu-id="10548-119">コントロール パネルの既定の BitLocker ドライブ暗号化項目を非表示にする</span><span class="sxs-lookup"><span data-stu-id="10548-119">Hiding the Default BitLocker Drive Encryption Item in Control Panel</span></span>](hiding-the-default-bitlocker-drive-encryption-item-in-control-panel-mbam-25.md)

## <span data-ttu-id="10548-120">MBAM 2.0 グループポリシーオブジェクトの展開に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="10548-120">Other Resources for deploying MBAM 2.0 Group Policy Objects</span></span>


[<span data-ttu-id="10548-121">MBAM 2.5 の展開</span><span class="sxs-lookup"><span data-stu-id="10548-121">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

## <span data-ttu-id="10548-122">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="10548-122">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="10548-123">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="10548-123">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="10548-124">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="10548-124">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





