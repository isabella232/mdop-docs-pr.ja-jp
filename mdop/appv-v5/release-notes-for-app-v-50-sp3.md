---
title: App-V 5.0 SP3 リリース ノート
description: App-V 5.0 SP3 リリース ノート
author: dansimp
ms.assetid: bc4806e0-2aba-4c7b-9ecc-1b2cc54af1d0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5b6d5834e4d0c953365f955922403c1a7a2058b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813323"
---
# <span data-ttu-id="8fb07-103">App-V 5.0 SP3 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="8fb07-103">Release Notes for App-V 5.0 SP3</span></span>


<span data-ttu-id="8fb07-104">Microsoft Application Virtualization (App-v) 5.0 SP3 の既知の問題を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="8fb07-104">The following are known issues in Microsoft Application Virtualization (App-V) 5.0 SP3.</span></span>

## <span data-ttu-id="8fb07-105">新しい5.0 アプリのインストール後にサーバーファイルが削除されない</span><span class="sxs-lookup"><span data-stu-id="8fb07-105">Server files fail to get deleted after a new App-V 5.0 SP3 Server installation</span></span>


<span data-ttu-id="8fb07-106">App-v 5.0 SP1 サーバーをアンインストールしてから、app-v 5.0 SP3 サーバーをインストールすると、インストールが失敗し、管理サーバーのバージョンが正しくインストールされません。</span><span class="sxs-lookup"><span data-stu-id="8fb07-106">If you uninstall the App-V 5.0 SP1 Server and then install the App-V 5.0 SP3 Server, the installation fails and the wrong version of the Management server is installed.</span></span> <span data-ttu-id="8fb07-107">次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8fb07-107">The following errors are displayed:</span></span>

`[0A5C:06F8][2014-09-12T19:08:00]i102: Detected related bundle: {bee44f0f-05be-48e4-81dd-d34a83600b95}, type: Upgrade, scope: PerMachine, version: 5.0.1218.0, operation: MajorUpgrade``[0A5C:06F8][2014-09-12T19:08:00]i000: AppvUX: A previous version of this product is installed; requesting upgrade.``[0A5C:06F8][2014-09-12T19:08:00]i102: Detected related bundle: {e1ca9d65-0ebf-4fd5-98e5-00d6453967a4}, type: Upgrade, scope: PerMachine, version: 5.0.1224.0, operation: MajorUpgrade``[0A5C:06F8][2014-09-12T19:08:00]i000: AppvUX: A previous version of this product is installed; requesting upgrade.`

<span data-ttu-id="8fb07-108">この問題は、App-v 5.0 SP1 をアンインストールしたときにサーバーファイルが削除されないために発生します。そのため、App-v 5.0 SP3 のインストールプロセスでは、新しいインストールの代わりにアップグレードが誤って行われます。</span><span class="sxs-lookup"><span data-stu-id="8fb07-108">The issue occurs because the Server files are not being deleted when you uninstall App-V 5.0 SP1, so the App-V 5.0 SP3 installation process erroneously does an upgrade instead of a new installation.</span></span>

<span data-ttu-id="8fb07-109">**回避策**: 次のレジストリキーを削除してから、App-V 5.0 SP3 のインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="8fb07-109">**Workaround**: Delete the following registry key before you start installing App-V 5.0 SP3:</span></span>

`HKEY_LOCAL_MACHINE\SOFTWARE\Wow6432Node\Microsoft\Windows\CurrentVersion\Uninstall`

## <span data-ttu-id="8fb07-110">AD DS に問い合わせると、一部のアプリケーションが正しく動作しない場合がある</span><span class="sxs-lookup"><span data-stu-id="8fb07-110">Querying AD DS can cause some applications to work incorrectly</span></span>


<span data-ttu-id="8fb07-111">更新されたグループメンバーシップのために Active Directory ドメインサービスを照会することによって更新されたパッケージを受け取った場合、アプリケーションがユーザーのアクセストークンに依存していると、一部のアプリケーションが正しく動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="8fb07-111">When you receive updated packages by querying Active Directory Domain Services for updated group memberships, it can cause some applications to work incorrectly if the applications depend on the user’s access token.</span></span> <span data-ttu-id="8fb07-112">さらに、グループメンバーシップのクエリを頻繁に行うと、ドメインコントローラーの過負荷が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8fb07-112">In addition, frequent group membership queries can cause the domain controller to overload.</span></span> <span data-ttu-id="8fb07-113">ユーザーアクセストークンの詳細については、「[アクセストークン](https://msdn.microsoft.com/library/windows/desktop/aa374909.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8fb07-113">For more information about user access tokens, see [Access Tokens](https://msdn.microsoft.com/library/windows/desktop/aa374909.aspx).</span></span>

<span data-ttu-id="8fb07-114">**回避策**: 更新されたグループメンバーシップを照会する前に、ユーザーがログオフしてから再びログインするまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="8fb07-114">**Workaround**: Wait until the user logs off and then logs back on before you query for updated group memberships.</span></span> <span data-ttu-id="8fb07-115">更新されたグループメンバーシップを照会するには、「 [Microsoft Application Virtualization 5.0 Service Pack 1 の修正プログラムパッケージ 2](https://support.microsoft.com/kb/2897087)」に記載されているレジストリキーを使わないでください。</span><span class="sxs-lookup"><span data-stu-id="8fb07-115">Do not use the registry key, described in [Hotfix Package 2 for Microsoft Application Virtualization 5.0 Service Pack 1](https://support.microsoft.com/kb/2897087), to query for updated group memberships.</span></span>






## <span data-ttu-id="8fb07-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8fb07-116">Related topics</span></span>


[<span data-ttu-id="8fb07-117">App-V 5.0 SP3 について</span><span class="sxs-lookup"><span data-stu-id="8fb07-117">About App-V 5.0 SP3</span></span>](about-app-v-50-sp3.md)

 

 





