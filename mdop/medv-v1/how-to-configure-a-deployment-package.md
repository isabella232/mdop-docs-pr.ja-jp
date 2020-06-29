---
title: 展開パッケージを構成する方法
description: 展開パッケージを構成する方法
author: dansimp
ms.assetid: 748272a1-6af2-476e-a3f1-87435b8e94b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aba5e91a4da92f9e51a5ccc70502658ae724d76f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825947"
---
# <span data-ttu-id="023fc-103">展開パッケージを構成する方法</span><span class="sxs-lookup"><span data-stu-id="023fc-103">How to Configure a Deployment Package</span></span>


<span data-ttu-id="023fc-104">パッケージウィザードでは、ローカルコンピューター上にフォルダーを作成し、必要なすべてのインストールファイルを1つのフォルダーに転送することによって、パッケージの作成方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="023fc-104">The Packaging wizard walks you through the creation of a package by creating a folder on your local computer and transferring all the required installation files to the single folder.</span></span> <span data-ttu-id="023fc-105">このフォルダーの内容は、配布用に複数のリムーバブルメディアドライブに移動できます。</span><span class="sxs-lookup"><span data-stu-id="023fc-105">The contents of the folder can then be moved to multiple removable media drives for distribution.</span></span>

**<span data-ttu-id="023fc-106">注</span><span class="sxs-lookup"><span data-stu-id="023fc-106">Note</span></span>**  
<span data-ttu-id="023fc-107">1つのパッケージに、x86 システムと x64 システムの両方のインストールファイルを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="023fc-107">A single package cannot contain installation files for both x86 and x64 systems.</span></span>



## <span data-ttu-id="023fc-108">展開パッケージを作成する方法</span><span class="sxs-lookup"><span data-stu-id="023fc-108">How to Create a Deployment Package</span></span>


**<span data-ttu-id="023fc-109">展開パッケージを作成するには</span><span class="sxs-lookup"><span data-stu-id="023fc-109">To create a deployment package</span></span>**

1. <span data-ttu-id="023fc-110">少なくとも1つのローカルパックイメージを作成した**Images**モジュールで確認します。</span><span class="sxs-lookup"><span data-stu-id="023fc-110">Verify in the **Images** module that you have created at least one local packed image.</span></span>

2. <span data-ttu-id="023fc-111">[**ツール**] メニューの [**パッケージウィザード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="023fc-111">On the **Tools** menu, select **Packaging wizard**.</span></span>

3. <span data-ttu-id="023fc-112">**パッケージウィザード**の [ようこそ] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="023fc-112">On the **Packaging wizard** welcome page, click **Next**.</span></span>

4. <span data-ttu-id="023fc-113">[**ワークスペースイメージ**] ページで、[**パッケージに画像を含める**] チェックボックスをオンにして、パッケージに画像を追加します。</span><span class="sxs-lookup"><span data-stu-id="023fc-113">On the **Workspace Image** page, select the **Include image in the package** check box to include an image in the package.</span></span>

   <span data-ttu-id="023fc-114">[**画像**] フィールドが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="023fc-114">The **Image** field is enabled.</span></span>

   **<span data-ttu-id="023fc-115">注</span><span class="sxs-lookup"><span data-stu-id="023fc-115">Note</span></span>**  
   <span data-ttu-id="023fc-116">イメージは、MED-V パッケージでは必要ありません。パッケージはイメージなしで作成することができます。</span><span class="sxs-lookup"><span data-stu-id="023fc-116">An image is not required in a MED-V package; the package can be created without an image.</span></span> <span data-ttu-id="023fc-117">このような場合は、後でネットワーク経由でクライアントにダウンロードしたり、イメージの事前ステージフォルダーにプッシュしたりできるように、画像をサーバーにアップロードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="023fc-117">In such a case, the image should be uploaded to the server so that it can later be downloaded over the network to the client, or pushed to an image pre-stage folder.</span></span>



5. <span data-ttu-id="023fc-118">**画像**リストをクリックして、利用可能なすべての画像を表示します。</span><span class="sxs-lookup"><span data-stu-id="023fc-118">Click the **Image** list to view all available images.</span></span> <span data-ttu-id="023fc-119">パッケージにコピーする画像を選びます。</span><span class="sxs-lookup"><span data-stu-id="023fc-119">Select the image to be copied to the package.</span></span> <span data-ttu-id="023fc-120">[**更新**] をクリックすると、使用可能な画像の一覧が更新されます。</span><span class="sxs-lookup"><span data-stu-id="023fc-120">Click **Refresh** to refresh the list of available images.</span></span>

6. <span data-ttu-id="023fc-121">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="023fc-121">Click **Next**.</span></span>

7. <span data-ttu-id="023fc-122">[ **Med-v のインストール設定**] ページで、次のいずれかの操作を行って、med-v インストールファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="023fc-122">On the **MED-V Installation Settings** page, select the MED-V installation file by doing one of the following:</span></span>

   -   <span data-ttu-id="023fc-123">[ **Med-v インストールファイル**] フィールドに、インストールファイルが保存されているディレクトリへのフルパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="023fc-123">In the **MED-V installation file** field, type the full path to the directory where the installation file is located.</span></span>

   -   <span data-ttu-id="023fc-124">[ **...** ] をクリックして、インストールファイルが配置されているディレクトリを参照します。</span><span class="sxs-lookup"><span data-stu-id="023fc-124">Click **...** to browse to the directory where the installation file is located.</span></span>

   **<span data-ttu-id="023fc-125">注</span><span class="sxs-lookup"><span data-stu-id="023fc-125">Note</span></span>**  
   <span data-ttu-id="023fc-126">このフィールドは必須であり、有効なファイル名がないとウィザードは続行されません。</span><span class="sxs-lookup"><span data-stu-id="023fc-126">This field is mandatory, and the wizard will not continue without a valid file name.</span></span>



8. <span data-ttu-id="023fc-127">[**サーバーアドレス**] フィールドに、サーバー名または IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="023fc-127">In the **Server address** field, type the server name or IP address.</span></span>

9. <span data-ttu-id="023fc-128">[**サーバーポート**] フィールドにサーバーのポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="023fc-128">In the **Server port** field, type the server port.</span></span>

10. <span data-ttu-id="023fc-129">サーバーへの接続に https 接続を要求するには、[**サーバーにアクセス**します] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="023fc-129">Select the **Server is accessed using https** check box to require an https connection to connect to the server.</span></span>

11. <span data-ttu-id="023fc-130">次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="023fc-130">Do one of the following:</span></span>

    -   <span data-ttu-id="023fc-131">[**既定のインストール設定**] をクリックして、[**次へ**] をクリックし、既定の設定のままにします。</span><span class="sxs-lookup"><span data-stu-id="023fc-131">Click **Default installation settings**, and then click **Next** to continue and leave the default settings.</span></span>

    -   <span data-ttu-id="023fc-132">[**カスタムインストール設定**] をクリックし、[**次**へ] をクリックしてインストール設定をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="023fc-132">Click **Custom installation settings**, and then click **Next** to customize the installation settings.</span></span>

        1.  <span data-ttu-id="023fc-133">[ **Med-v のインストールカスタム設定**] ページにある [**インストールフォルダー** ] フィールドに、ホストコンピューター上の med-v ファイルがインストールされるフォルダーのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="023fc-133">On the **MED-V Installation Custom Settings** page, in the **Installation folder** field, type the path of the folder where the MED-V files will be installed on the host computer.</span></span>

            **<span data-ttu-id="023fc-134">注</span><span class="sxs-lookup"><span data-stu-id="023fc-134">Note</span></span>**  
            <span data-ttu-id="023fc-135">定数ではなく、パスの変数を使うことをお勧めします。これは、コンピューターによって異なる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="023fc-135">It is recommended to use variables in the path rather than constants, which might vary from computer to computer.</span></span>

            <span data-ttu-id="023fc-136">たとえば、 *c:\\MED-V*の代わりに *%ProgramFiles%\\MED-V*を使います。</span><span class="sxs-lookup"><span data-stu-id="023fc-136">For example, use *%ProgramFiles%\\MED-V* instead of *c:\\MED-V*.</span></span>



    ~~~
    2.  In the **Virtual machines images folder** field, type the path of the folder where the virtual images files will be installed on the host computer.

        **Note**  
        If you are using image pre-staging, this is the image pre-stage folder where the image is located.



    3.  In the **Minimal required RAM** field, enter the RAM required to install a MED-V package. If the user installing the MED-V package does not have the minimal required RAM, the installation will fail.

    4.  Select the **Install the MED-V management application** check box to include the MED-V management console application in the installation.

    5.  Select the **Create a shortcut to MED-V on the desktop** check box to create a shortcut to MED-V on the host's desktop.

    6.  Select the **Start automatically on computer startup** check box to start MED-V automatically on startup.

    7.  Click **Next**.
    ~~~

12. <span data-ttu-id="023fc-137">[**追加のインストール**] ページで、[仮想**化ソフトウェアのインストールを含める**] チェックボックスをオンにして、パッケージに仮想 PC のインストールを含めます。</span><span class="sxs-lookup"><span data-stu-id="023fc-137">On the **Additional Installations** page, select the **Include installation of virtualization software** check box to include the Virtual PC installation in the package.</span></span>

    <span data-ttu-id="023fc-138">[**インストールファイル**] フィールドが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="023fc-138">The **Installation file** field is enabled.</span></span> <span data-ttu-id="023fc-139">仮想化ソフトウェアのインストールファイルの完全なパスを入力するか、[ **...** ] をクリックしてディレクトリを参照します。</span><span class="sxs-lookup"><span data-stu-id="023fc-139">Type the full path of the virtualization software installation file, or click **...** to browse to the directory.</span></span>

13. <span data-ttu-id="023fc-140">[ **VIRTUAL PC QFE のインストールを含める**] チェックボックスをオンにして、仮想 pc の更新プログラムのインストールをパッケージに含めます。</span><span class="sxs-lookup"><span data-stu-id="023fc-140">Select the **Include installation of Virtual PC QFE** check box to include Virtual PC update installation in the package.</span></span>

    <span data-ttu-id="023fc-141">[**インストールファイル**] フィールドが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="023fc-141">The **Installation file** field is enabled.</span></span> <span data-ttu-id="023fc-142">仮想 PC 更新プログラムのインストールファイルの完全なパスを入力するか **、[...]** をクリックしてディレクトリを参照します。</span><span class="sxs-lookup"><span data-stu-id="023fc-142">Type the full path of the Virtual PC update installation file, or click **...** to browse to the directory.</span></span>

14. <span data-ttu-id="023fc-143">[ **Microsoft .Net framework 2.0 のインストールを含める**] チェックボックスをオンにして、パッケージに Microsoft .net framework 2.0 インストールを含めます。</span><span class="sxs-lookup"><span data-stu-id="023fc-143">Select the **Include installation of Microsoft .NET Framework 2.0** check box to include the Microsoft .NET Framework 2.0 installation in the package.</span></span>

    <span data-ttu-id="023fc-144">[**インストールファイル**] フィールドが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="023fc-144">The **Installation file** field is enabled.</span></span> <span data-ttu-id="023fc-145">Microsoft .NET Framework 2.0 インストールファイルの完全なパスを入力するか、[ **...** ] をクリックしてディレクトリを参照します。</span><span class="sxs-lookup"><span data-stu-id="023fc-145">Type the full path of the Microsoft .NET Framework 2.0 installation file, or click **...** to browse to the directory.</span></span>

15. <span data-ttu-id="023fc-146">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="023fc-146">Click **Next**.</span></span>

16. <span data-ttu-id="023fc-147">[**完了**] ページで、次のいずれかの操作を行って、パッケージを保存する場所を選びます。</span><span class="sxs-lookup"><span data-stu-id="023fc-147">On the **Finalize** page, select the location where the package should be saved by doing one of the following:</span></span>

    -   <span data-ttu-id="023fc-148">[**パッケージの宛先**] フィールドに、パッケージを保存するディレクトリの完全なパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="023fc-148">In the **Package destination** field, type the full path to the directory where the package should be saved.</span></span>

    -   <span data-ttu-id="023fc-149">[ **...** ] をクリックして、インストールファイルが保存されるディレクトリを参照します。</span><span class="sxs-lookup"><span data-stu-id="023fc-149">Click **...** to browse to the directory where the installation files should be saved.</span></span>

    **<span data-ttu-id="023fc-150">注</span><span class="sxs-lookup"><span data-stu-id="023fc-150">Note</span></span>**  
    <span data-ttu-id="023fc-151">パッケージをビルドすると、実際のパッケージサイズよりも多くの領域が消費される場合があります。</span><span class="sxs-lookup"><span data-stu-id="023fc-151">Building the package might consume more space than the actual package size.</span></span> <span data-ttu-id="023fc-152">このため、ハードドライブにパッケージを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="023fc-152">It is therefore recommended to build the package on the hard drive.</span></span> <span data-ttu-id="023fc-153">パッケージを作成したら、USB にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="023fc-153">After the package is created, it can then be copied to the USB.</span></span>



17. <span data-ttu-id="023fc-154">[**パッケージ名**] フィールドに、パッケージの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="023fc-154">In the **Package name** field, enter a name for the package.</span></span>

18. <span data-ttu-id="023fc-155">[**完了**] をクリックして、パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="023fc-155">Click **Finish** to create the package.</span></span>

    <span data-ttu-id="023fc-156">パッケージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="023fc-156">The package is created.</span></span> <span data-ttu-id="023fc-157">数分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="023fc-157">This might take several minutes.</span></span>

    <span data-ttu-id="023fc-158">パッケージが作成されると、正常に完了したことを通知するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="023fc-158">After the package is created, a message appears notifying you that it has been completed successfully.</span></span>

**<span data-ttu-id="023fc-159">注</span><span class="sxs-lookup"><span data-stu-id="023fc-159">Note</span></span>**  
<span data-ttu-id="023fc-160">リムーバブルメディアに直接ではなく、すべてのファイルをローカルで保存した場合は、フォルダー自体ではなく、フォルダー自体をコピーして、リムーバブルメディアにコピーしてください。</span><span class="sxs-lookup"><span data-stu-id="023fc-160">If you saved all the files locally, and not directly on the removable media, ensure that you copy only the contents of the folder and not the folder itself to the removable media.</span></span>



**<span data-ttu-id="023fc-161">注</span><span class="sxs-lookup"><span data-stu-id="023fc-161">Note</span></span>**  
<span data-ttu-id="023fc-162">リムーバブルメディアは、パッケージのコンテンツが、リムーバブルメディアのメモリの3分の1しか消費しないように、十分な大きさである必要があります。</span><span class="sxs-lookup"><span data-stu-id="023fc-162">The removable media must be large enough so that the package contents consume a maximum of only three-quarters of the removable media's memory.</span></span>



**<span data-ttu-id="023fc-163">注</span><span class="sxs-lookup"><span data-stu-id="023fc-163">Note</span></span>**  
<span data-ttu-id="023fc-164">パッケージを作成するときに、ビルドが完了したときに、実際のパッケージサイズの最大2倍のサイズが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="023fc-164">When creating the package, up to double the size of the actual package size might be required when the build is complete.</span></span>



## <span data-ttu-id="023fc-165">関連トピック</span><span class="sxs-lookup"><span data-stu-id="023fc-165">Related topics</span></span>


[<span data-ttu-id="023fc-166">MED-V イメージの作成</span><span class="sxs-lookup"><span data-stu-id="023fc-166">Creating a MED-V Image</span></span>](creating-a-med-v-image.md)









