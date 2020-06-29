---
title: MED-V クライアントをインストールする方法
description: MED-V クライアントをインストールする方法
author: dansimp
ms.assetid: bfac6de7-d96d-4b3e-bd8b-183e051e53c8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b2e4468b15c0c196bf605b1b5d129ab38678ec74
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827194"
---
# <span data-ttu-id="f8150-103">MED-V クライアントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="f8150-103">How to Install MED-V Client</span></span>


<span data-ttu-id="f8150-104">展開パッケージベースのシナリオでは、MED-V クライアントインストールは展開パッケージに含まれ、パッケージから直接インストールされます。</span><span class="sxs-lookup"><span data-stu-id="f8150-104">In a deployment package-based scenario, the MED-V client installation is included in the deployment package and installed directly from the package.</span></span>

**<span data-ttu-id="f8150-105">重要</span><span class="sxs-lookup"><span data-stu-id="f8150-105">Important</span></span>**  
<span data-ttu-id="f8150-106">画像が含まれていない展開パッケージを使用する場合は、画像が Web にアップロードされていること、または展開パッケージをインストールする前に事前ステージフォルダーにプッシュされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="f8150-106">When using a deployment package that does not include an image, ensure that the image is uploaded to the Web or pushed to the pre-stage folder prior to installing the deployment package.</span></span>



**<span data-ttu-id="f8150-107">展開パッケージをインストールするには</span><span class="sxs-lookup"><span data-stu-id="f8150-107">To install a deployment package</span></span>**

1.  <span data-ttu-id="f8150-108">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="f8150-108">Do one of the following:</span></span>

    -   <span data-ttu-id="f8150-109">Web から MED-V パッケージをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="f8150-109">Download the MED-V package from the Web.</span></span>

    -   <span data-ttu-id="f8150-110">展開 USB または DVD をホストドライブに挿入します。</span><span class="sxs-lookup"><span data-stu-id="f8150-110">Insert the deployment USB or DVD into the host drive.</span></span>

2.  <span data-ttu-id="f8150-111">MED-V が自動的に起動しない場合は、[MED-VAutoInstaller.exe] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="f8150-111">If MED-V does not launch automatically, double-click MED-VAutoInstaller.exe.</span></span>

    <span data-ttu-id="f8150-112">既にインストールされているコンポーネントと、現在インストールされているコンポーネントの一覧を示すダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8150-112">A dialog box appears listing the components that are already installed and those that are currently being installed.</span></span>

    **<span data-ttu-id="f8150-113">注</span><span class="sxs-lookup"><span data-stu-id="f8150-113">Note</span></span>**  
    <span data-ttu-id="f8150-114">ホストコンピューター上にサポートされていないバージョンの Microsoft 仮想 PC が存在する場合は、既存のバージョンをアンインストールしてインストーラーをもう一度実行するように指示するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8150-114">If a version of the Microsoft Virtual PC that is not supported exists on the host computer, a message will appear telling you to uninstall the existing version and run the installer again.</span></span>



~~~
**Note**  
If an older version of the MED-V client exists, it will prompt you asking whether you want to upgrade.



Depending on the components that have been installed, you might need to reboot. If rebooting is necessary, a message appears notifying you that you must reboot.
~~~

3. <span data-ttu-id="f8150-115">必要に応じて、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="f8150-115">If necessary, reboot the computer.</span></span>

   <span data-ttu-id="f8150-116">インストールが完了すると、MED-V が開始され、インストールが完了したことを通知するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="f8150-116">When the installation is complete, MED-V starts and a message appears notifying you that the installation is complete.</span></span>

4. <span data-ttu-id="f8150-117">次のユーザー名とパスワードを使用して MED-V にログインします。</span><span class="sxs-lookup"><span data-stu-id="f8150-117">Log in to MED-V using the following user name and password:</span></span>

   -   <span data-ttu-id="f8150-118">ドメイン名とユーザー名を入力し、その後、MED-V での操作が許可されているドメインユーザーのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="f8150-118">Type in the domain name and user name followed by the password of the domain user who is permitted to work with MED-V.</span></span>

       <span data-ttu-id="f8150-119">例: "domain \ _name \\ user\ _name", "password"</span><span class="sxs-lookup"><span data-stu-id="f8150-119">Example: "domain\_name\\user\_name", "password"</span></span>

## <span data-ttu-id="f8150-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f8150-120">Related topics</span></span>


[<span data-ttu-id="f8150-121">展開パッケージを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f8150-121">How to Configure a Deployment Package</span></span>](how-to-configure-a-deployment-package.md)

[<span data-ttu-id="f8150-122">MED-V イメージをサーバーにアップロードする方法</span><span class="sxs-lookup"><span data-stu-id="f8150-122">How to Upload a MED-V Image to the Server</span></span>](how-to-upload-a-med-v-image-to-the-server.md)

[<span data-ttu-id="f8150-123">クライアント インストールのコマンド ライン リファレンス</span><span class="sxs-lookup"><span data-stu-id="f8150-123">Client Installation Command Line Reference</span></span>](client-installation-command-line-reference.md)









