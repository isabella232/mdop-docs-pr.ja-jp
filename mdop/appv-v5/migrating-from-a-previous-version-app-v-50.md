---
title: 旧バージョンからの移行
description: 旧バージョンからの移行
author: dansimp
ms.assetid: a13cd353-b22a-48f7-af1e-5d54ede2a7e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a05bbd498cdb77a1ddf694b1aab6aeb42124775b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813555"
---
# <span data-ttu-id="69645-103">旧バージョンからの移行</span><span class="sxs-lookup"><span data-stu-id="69645-103">Migrating from a Previous Version</span></span>


<span data-ttu-id="69645-104">App-v 5.0 を使用すると、既存の App-v 4.6 インフラストラクチャを、より柔軟かつ統合化され、より簡単に5.0 管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="69645-104">With App-V 5.0 you can migrate your existing App-V 4.6 infrastructure to the more flexible, integrated, and easier to manage App-V 5.0 infrastructure.</span></span>

<span data-ttu-id="69645-105">移行戦略を計画するときは、次のセクションを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="69645-105">Consider the following sections when you plan your migration strategy:</span></span>

<span data-ttu-id="69645-106">**注** App-v 4.6 と App-v 5.0 の違いの詳細については、「 [app-v 5.0 について](about-app-v-50.md)」の「app-v **4.6 と app-v 5.0」セクション**を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69645-106">**Note** For more information about the differences between App-V 4.6 and App-V 5.0, see the **Differences between App-V 4.6 and App-V 5.0 section** of [About App-V 5.0](about-app-v-50.md).</span></span>

 

## <span data-ttu-id="69645-107">以前のバージョンの App-v を使用して作成されたパッケージの変換</span><span class="sxs-lookup"><span data-stu-id="69645-107">Converting packages created using a prior version of App-V</span></span>


<span data-ttu-id="69645-108">以前のバージョンの App-v を使用して作成された仮想アプリケーションパッケージをアップグレードするには、パッケージコンバーターユーティリティを使用します。</span><span class="sxs-lookup"><span data-stu-id="69645-108">Use the package converter utility to upgrade virtual application packages created using previous versions of App-V.</span></span> <span data-ttu-id="69645-109">パッケージコンバーターは、PowerShell を使用してパッケージを変換し、変換が必要なパッケージが多い場合は、プロセスの自動化に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="69645-109">The package converter uses PowerShell to convert packages and can help automate the process if you have many packages that require conversion.</span></span>

<span data-ttu-id="69645-110">**重要** 既存のパッケージを変換した後は、パッケージを展開する前にパッケージをテストして、変換処理が正常に完了したことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69645-110">**Important** After you convert an existing package you should test the package prior to deploying the package to ensure the conversion process was successful.</span></span>

 

**<span data-ttu-id="69645-111">既存のパッケージを変換する前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="69645-111">What to know before you convert existing packages</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="69645-112">問題</span><span class="sxs-lookup"><span data-stu-id="69645-112">Issue</span></span></th>
<th align="left"><span data-ttu-id="69645-113">回避策</span><span class="sxs-lookup"><span data-stu-id="69645-113">Workaround</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="69645-114">パッケージスクリプトは変換されません。</span><span class="sxs-lookup"><span data-stu-id="69645-114">Package scripts are not converted.</span></span></p></td>
<td align="left"><p><span data-ttu-id="69645-115">変換されたパッケージをテストします。</span><span class="sxs-lookup"><span data-stu-id="69645-115">Test the converted package.</span></span> <span data-ttu-id="69645-116">必要に応じて、スクリプトを変換します。</span><span class="sxs-lookup"><span data-stu-id="69645-116">If necessary convert the script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="69645-117">パッケージのレジストリ設定の上書きは変換されません。</span><span class="sxs-lookup"><span data-stu-id="69645-117">Package registry setting overrides are not converted.</span></span></p></td>
<td align="left"><p><span data-ttu-id="69645-118">変換されたパッケージをテストします。</span><span class="sxs-lookup"><span data-stu-id="69645-118">Test the converted package.</span></span> <span data-ttu-id="69645-119">必要に応じて、レジストリの上書きを再度追加します。</span><span class="sxs-lookup"><span data-stu-id="69645-119">If necessary, re-add registry overrides.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="69645-120">変換後、DSC を使用する仮想パッケージはリンクされません。</span><span class="sxs-lookup"><span data-stu-id="69645-120">Virtual packages using DSC are not linked after conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="69645-121">接続グループを使ってパッケージをリンクします。</span><span class="sxs-lookup"><span data-stu-id="69645-121">Link the packages using connection groups.</span></span> <span data-ttu-id="69645-122">「 <a href="managing-connection-groups.md" data-raw-source="[Managing Connection Groups](managing-connection-groups.md)"> 接続グループの管理」をご覧ください </a> 。</span><span class="sxs-lookup"><span data-stu-id="69645-122">See <a href="managing-connection-groups.md" data-raw-source="[Managing Connection Groups](managing-connection-groups.md)">Managing Connection Groups</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="69645-123">変換中に環境変数の競合が検出されます。</span><span class="sxs-lookup"><span data-stu-id="69645-123">Environment variable conflicts are detected during conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="69645-124">関連付けられている .osd ファイル内の競合を解決 <strong> </strong> します。</span><span class="sxs-lookup"><span data-stu-id="69645-124">Resolve any conflicts in the associated <strong>.osd</strong> file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="69645-125">変換中にハードコーディングされたパスが検出されます。</span><span class="sxs-lookup"><span data-stu-id="69645-125">Hard-coded paths are detected during conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="69645-126">ハードコーディングされたパスは正しく変換されにくくなります。</span><span class="sxs-lookup"><span data-stu-id="69645-126">Hard-coded paths are difficult to convert correctly.</span></span> <span data-ttu-id="69645-127">パッケージコンバーターは、ハードコーディングされたパスを含むファイルを含むパッケージを検出して返します。</span><span class="sxs-lookup"><span data-stu-id="69645-127">The package converter will detect and return packages with files that contain hard-coded paths.</span></span> <span data-ttu-id="69645-128">ハードコーディングされたパスでファイルを表示し、パッケージにファイルが必要かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="69645-128">View the file with the hard-coded path, and determine whether the package requires the file.</span></span> <span data-ttu-id="69645-129">その場合は、パッケージの順序を再確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69645-129">If so, it is recommended to re-sequence the package.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="69645-130">パッケージを変換するときに、エラーが発生したファイルまたはショートカットを確認します。</span><span class="sxs-lookup"><span data-stu-id="69645-130">When converting a package check for failing files or shortcuts.</span></span> <span data-ttu-id="69645-131">App-V 4.6 パッケージでアイテムを見つけます。</span><span class="sxs-lookup"><span data-stu-id="69645-131">Locate the item in App-V 4.6 package.</span></span> <span data-ttu-id="69645-132">ハードコードされている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="69645-132">It could possibly be hard-coded path.</span></span> <span data-ttu-id="69645-133">パスを変換します。</span><span class="sxs-lookup"><span data-stu-id="69645-133">Convert the path.</span></span>

<span data-ttu-id="69645-134">**注** 機能を活用する必要がある重要なアプリケーションやアプリケーションを変換するには、App-v 5.0 sequencer を使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69645-134">**Note** It is recommended that you use the App-V 5.0 sequencer for converting critical applications or applications that need to take advantage of features.</span></span> <span data-ttu-id="69645-135">「 [App-v 5.0 を使って新しいアプリケーションを順序付けする方法](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69645-135">See, [How to Sequence a New Application with App-V 5.0](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md).</span></span>

<span data-ttu-id="69645-136">変換後に変換されたパッケージが開かない場合は、App-v 5.0 sequencer を使用してアプリケーションを再シーケンスすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69645-136">If a converted package does not open after you convert it, it is also recommended that you re-sequence the application using the App-V 5.0 sequencer.</span></span>

 

[<span data-ttu-id="69645-137">以前のバージョンの APP-V で作成されたパッケージを変換する方法</span><span class="sxs-lookup"><span data-stu-id="69645-137">How to Convert a Package Created in a Previous Version of App-V</span></span>](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)

## <span data-ttu-id="69645-138">クライアントの移行</span><span class="sxs-lookup"><span data-stu-id="69645-138">Migrating Clients</span></span>


<span data-ttu-id="69645-139">次の表は、クライアントをアップグレードするための推奨される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="69645-139">The following table displays the recommended method for upgrading clients.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="69645-140">タスク</span><span class="sxs-lookup"><span data-stu-id="69645-140">Task</span></span></th>
<th align="left"><span data-ttu-id="69645-141">詳細情報</span><span class="sxs-lookup"><span data-stu-id="69645-141">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="69645-142">環境を App V 4.6 SP2 にアップグレードする</span><span class="sxs-lookup"><span data-stu-id="69645-142">Upgrade your environment to App-V4.6SP2</span></span></p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)"><span data-ttu-id="69645-143">アプリケーションの仮想化の展開とアップグレードに関する考慮事項 </a> 。</span><span class="sxs-lookup"><span data-stu-id="69645-143">Application Virtualization Deployment and Upgrade Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="69645-144">共存を有効にした App-v 5.0 クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="69645-144">Install the App-V 5.0 client with co-existence enabled.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md" data-raw-source="[How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)"><span data-ttu-id="69645-145">同じコンピューターに app-v 4.6 と App-v 5.0 クライアントを展開する方法を説明 </a> します。</span><span class="sxs-lookup"><span data-stu-id="69645-145">How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="69645-146">アプリ-V 5.0 パッケージのシーケンスとロールアウト。</span><span class="sxs-lookup"><span data-stu-id="69645-146">Sequence and roll out App-V 5.0 packages.</span></span> <span data-ttu-id="69645-147">必要に応じて、App-v 4.6 パッケージの発行を取り消します。</span><span class="sxs-lookup"><span data-stu-id="69645-147">As needed, unpublish App-V 4.6 packages.</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md" data-raw-source="[How to Sequence a New Application with App-V 5.0](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)"><span data-ttu-id="69645-148">App-V 5.0 を使って新しいアプリケーションをシーケンスする方法について説明 </a> します。</span><span class="sxs-lookup"><span data-stu-id="69645-148">How to Sequence a New Application with App-V 5.0</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="69645-149">**重要** 共存モードを使用するには、App-v 4.6 SP3 を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="69645-149">**Important** You must be running App-V4.6SP3 to use coexistence mode.</span></span> <span data-ttu-id="69645-150">さらに、パッケージをシーケンス処理するときには、 **[ユーザーの\*\*\*\*構成] セクションに**ある [管理権限] 設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69645-150">Additionally, when you sequence a package, you must configure the Managing Authority setting, which is in the **User Configuration** is located in the **User Configuration** section.</span></span>

 

## <span data-ttu-id="69645-151">App-v 5.0 Server の完全なインフラストラクチャを移行する</span><span class="sxs-lookup"><span data-stu-id="69645-151">Migrating the App-V 5.0 Server Full Infrastructure</span></span>


<span data-ttu-id="69645-152">完全な App-v 5.0 インフラストラクチャにアップグレードする直接的な方法はありません。</span><span class="sxs-lookup"><span data-stu-id="69645-152">There is no direct method to upgrade to a full App-V 5.0 infrastructure.</span></span> <span data-ttu-id="69645-153">App-v server のアップグレードについては、次のセクションの情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69645-153">Use the information in the following section for information about upgrading the App-V server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="69645-154">タスク</span><span class="sxs-lookup"><span data-stu-id="69645-154">Task</span></span></th>
<th align="left"><span data-ttu-id="69645-155">詳細情報</span><span class="sxs-lookup"><span data-stu-id="69645-155">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="69645-156">環境を App V 4.6 SP3 にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="69645-156">Upgrade your environment to App-V4.6SP3.</span></span></p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)"><span data-ttu-id="69645-157">アプリケーションの仮想化の展開とアップグレードに関する考慮事項 </a> 。</span><span class="sxs-lookup"><span data-stu-id="69645-157">Application Virtualization Deployment and Upgrade Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="69645-158">クライアントの App-v 5.0 バージョンを展開します。</span><span class="sxs-lookup"><span data-stu-id="69645-158">Deploy App-V 5.0 version of the client.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)"><span data-ttu-id="69645-159">App-v クライアントを展開する方法を説明 </a> します。</span><span class="sxs-lookup"><span data-stu-id="69645-159">How to Deploy the App-V Client</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="69645-160">App-v 5.0 server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="69645-160">Install App-V 5.0 server.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)"><span data-ttu-id="69645-161">App-v 5.0 サーバーを展開する方法について説明 </a> します。</span><span class="sxs-lookup"><span data-stu-id="69645-161">How to Deploy the App-V 5.0 Server</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="69645-162">既存のパッケージを移行します。</span><span class="sxs-lookup"><span data-stu-id="69645-162">Migrate existing packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="69645-163"><strong>この記事の「以前のバージョンの app-v を使用して作成されたパッケージの変換」を参照してください </strong> 。</span><span class="sxs-lookup"><span data-stu-id="69645-163">See the <strong>Converting packages created using a prior version of App-V</strong> section of this article.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="69645-164">その他の移行タスク</span><span class="sxs-lookup"><span data-stu-id="69645-164">Additional Migration tasks</span></span>


<span data-ttu-id="69645-165">また、エンドポイントの再構成や、App-v 5.0 クライアントを実行しているコンピューター上で以前のバージョンを使用して作成されたパッケージの開くなど、追加の移行タスクを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="69645-165">You can also perform additional migration tasks such as reconfiguring end points as well as opening a package created using a prior version on a computer running the App-V 5.0 client.</span></span> <span data-ttu-id="69645-166">次のリンクでは、これらのタスクを実行する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="69645-166">The following links provide more information about performing these tasks.</span></span>

[<span data-ttu-id="69645-167">特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法</span><span class="sxs-lookup"><span data-stu-id="69645-167">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.0 Package for All Users on a Specific Computer</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="69645-168">特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法</span><span class="sxs-lookup"><span data-stu-id="69645-168">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.0 for a Specific User</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)

[<span data-ttu-id="69645-169">特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.0 パッケージから App-V 4.6 パッケージに戻す方法</span><span class="sxs-lookup"><span data-stu-id="69645-169">How to Revert Extension Points from an App-V 5.0 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="69645-170">特定のユーザーの拡張ポイントを App-V 5.0 パッケージから App-V 4.6 パッケージに戻す方法</span><span class="sxs-lookup"><span data-stu-id="69645-170">How to Revert Extension Points From an App-V 5.0 Package to an App-V 4.6 Package for a Specific User</span></span>](how-to-revert-extension-points-from-an-app-v-50-package-to-an-app-v-46-package-for-a-specific-user.md)







## <span data-ttu-id="69645-171">App-v の移行タスクを実行するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="69645-171">Other resources for performing App-V migration tasks</span></span>


[<span data-ttu-id="69645-172">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="69645-172">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

[<span data-ttu-id="69645-173">簡素化された Microsoft App-V 5.1 Management Server のアップグレード手順</span><span class="sxs-lookup"><span data-stu-id="69645-173">A simplified Microsoft App-V 5.1 Management Server upgrade procedure</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=786330)

 

 





