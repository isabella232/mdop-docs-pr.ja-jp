---
title: setup.msi を使用して App-V Client をインストールする方法
description: setup.msi を使用して App-V Client をインストールする方法
author: dansimp
ms.assetid: 7221f384-36d6-409a-94a2-86f54fd75322
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fb3a145a6c57cccbae3f4e6b191b89d93278ff8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817334"
---
# <span data-ttu-id="c13e1-103">setup.msi を使用して App-V Client をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="c13e1-103">How to Install the App-V Client by Using Setup.msi</span></span>


<span data-ttu-id="c13e1-104">このトピックでは、setup.msi プログラムを使用して App-v クライアントをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c13e1-104">This topic describes how to install the App-V client by using the setup.msi program.</span></span> <span data-ttu-id="c13e1-105">setup.msi プログラムを使用して App-v クライアントをインストールする前に、まず必要なソフトウェアがインストールされているかどうかを確認してから、インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c13e1-105">Before you install the App-V client using the setup.msi program, you must first determine if any prerequisite software must be installed, and then you must install it.</span></span> <span data-ttu-id="c13e1-106">必須ソフトウェアをインストールするには、このトピックの「[必要なソフトウェアをインストール](#prereq-sw)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c13e1-106">To install the prerequisite software, see the [Installing Prerequisite Software](#prereq-sw) section of this topic.</span></span> <span data-ttu-id="c13e1-107">クライアントソフトウェアをインストールするには、このトピックの「 [Setup.msi プログラムを使用して App-v クライアントをインストール](#msi-setup)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c13e1-107">To install the client software, see the [Installing the App-V Client Using the Setup.msi Program](#msi-setup) section of this topic.</span></span>

## <a href="" id="prereq-sw"></a><span data-ttu-id="c13e1-108">必須ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="c13e1-108">Installing Prerequisite Software</span></span>


<span data-ttu-id="c13e1-109">次の手順を使用して、必要なソフトウェアをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="c13e1-109">You can use the following procedures to install the prerequisite software.</span></span> <span data-ttu-id="c13e1-110">コマンドファイルを作成してコマンドプロンプトからコマンドを実行するか、VBScript や Windows PowerShell などのスクリプト言語を使ってコマンドを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="c13e1-110">You can create a command file and run the commands from the command prompt, or you can use a scripting language such as VBScript or Windows PowerShell to run the commands.</span></span>

<span data-ttu-id="c13e1-111">**注** X86 と x64 の両方のバージョンの App-v クライアントには、次のソフトウェアの x86 バージョンが必要です。</span><span class="sxs-lookup"><span data-stu-id="c13e1-111">**Note** The x86 versions of the following software are required for both x86 and x64 versions of the App-V client.</span></span>

 

**<span data-ttu-id="c13e1-112">Microsoft VisualC + + 2005SP1 の再頒布可能パッケージ (x86) をインストールするには</span><span class="sxs-lookup"><span data-stu-id="c13e1-112">To install Microsoft VisualC++2005SP1 Redistributable Package (x86)</span></span>**

1. <span data-ttu-id="c13e1-113">Microsoft ダウンロードセンター () から[Microsoft Visual C++ 2005 SP1 再頒布可能パッケージ (x86)](https://go.microsoft.com/fwlink/?LinkId=119961)ソフトウェアパッケージをダウンロードし <https://go.microsoft.com/fwlink/?LinkId=119961> ます。</span><span class="sxs-lookup"><span data-stu-id="c13e1-113">Download the [Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=119961) software package from the Microsoft Download Center (<https://go.microsoft.com/fwlink/?LinkId=119961>).</span></span> <span data-ttu-id="c13e1-114">\ [Template Token Value \] バージョン 4.5 SP2 以降、App-v クライアントの場合は、vcredist\_x86.exe をダウンロードしてください。 [Microsoft Visual C++ 2005 Service Pack 1 の再頒布可能パッケージ ATL セキュリティ更新プログラム](https://go.microsoft.com/fwlink/?LinkId=169360)( https://go.microsoft.com/fwlink/?LinkId=169360).\ [テンプレートトークン値])</span><span class="sxs-lookup"><span data-stu-id="c13e1-114">\[Template Token Value\] For version 4.5 SP2 and later of the App-V client, download vcredist\_x86.exe from [Microsoft Visual C++ 2005 Service Pack 1 Redistributable Package ATL Security Update](https://go.microsoft.com/fwlink/?LinkId=169360) (https://go.microsoft.com/fwlink/?LinkId=169360).\[Template Token Value\]</span></span>

2. <span data-ttu-id="c13e1-115">サイレントインストールするには、コマンドラインオプション "/Q" を vcredist\_x86.exe と共に使用します (例: **vcredist\_x86.exe/q**)。</span><span class="sxs-lookup"><span data-stu-id="c13e1-115">To install silently, use the command-line option “/Q” with vcredist\_x86.exe—for example, **vcredist\_x86.exe /Q**.</span></span>

3. <span data-ttu-id="c13e1-116">vcredist\_x86.msi ファイルを使用してソフトウェアをインストールするには、コマンドラインオプション "/C/T: &lt; fullpathtofolder &gt; " を使用して vcredist.msi ファイルを抽出し、vcredist\_x86.exe から一時フォルダーに vcredis1.cab します。</span><span class="sxs-lookup"><span data-stu-id="c13e1-116">To install the software by using the vcredist\_x86.msi file, use the command-line option “/C /T:&lt;fullpathtofolder&gt;” to extract the files vcredist.msi and vcredis1.cab from vcredist\_x86.exe to a temporary folder.</span></span> <span data-ttu-id="c13e1-117">サイレントインストールするには、コマンドラインオプション/quiet ( **msiexec/i vcredist.msi** /quiet. など) を使用します。</span><span class="sxs-lookup"><span data-stu-id="c13e1-117">To install silently, use the command-line option /quiet—for example, **msiexec /i vcredist.msi** /quiet.</span></span>

### <span data-ttu-id="c13e1-118">Microsoft VisualC + + 2008SP1 の再頒布可能パッケージ (x86) をインストールするには</span><span class="sxs-lookup"><span data-stu-id="c13e1-118">To install Microsoft VisualC++2008SP1 Redistributable Package (x86)</span></span>

<span data-ttu-id="c13e1-119">**重要** バージョン4.6 以降の App-v クライアントでは、Microsoft Visual C++ 2008 Service Pack 1 の再頒布可能パッケージ ATL セキュリティ更新プログラムもインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c13e1-119">**Important** For version4.6 and later of the App-V client, you must also install the Microsoft Visual C++ 2008 Service Pack 1 Redistributable Package ATL Security Update.</span></span>

 

****

1.  <span data-ttu-id="c13e1-120">Microsoft [Visual C++ 2008 Service Pack 1 の再頒布可能パッケージ ATL セキュリティ更新プログラム](https://go.microsoft.com/fwlink/?LinkId=150700)ソフトウェアパッケージを Microsoft ダウンロードセンター () からダウンロードし https://go.microsoft.com/fwlink/?LinkId=150700) ます。</span><span class="sxs-lookup"><span data-stu-id="c13e1-120">Download the [Microsoft Visual C++ 2008 Service Pack 1 Redistributable Package ATL Security Update](https://go.microsoft.com/fwlink/?LinkId=150700) software package from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=150700).</span></span>

2.  <span data-ttu-id="c13e1-121">サイレントインストールするには、コマンドラインオプション "/Q" を vcredist\_x86.exe と共に使用します (例: **vcredist\_x86.exe/q**)。</span><span class="sxs-lookup"><span data-stu-id="c13e1-121">To install silently, use the command-line option “/Q” with vcredist\_x86.exe—for example, **vcredist\_x86.exe /Q**.</span></span>

### <span data-ttu-id="c13e1-122">Microsoft Core XML Services (MSXML) 6.0 SP1 (x86) をインストールするには</span><span class="sxs-lookup"><span data-stu-id="c13e1-122">To install Microsoft Core XML Services (MSXML)6.0SP1 (x86)</span></span>

****

1.  <span data-ttu-id="c13e1-123">Microsoft ダウンロードセンター () から[Microsoft CORE XML サービス (MSXML)](https://go.microsoft.com/fwlink/?LinkId=63266)のソフトウェアパッケージをダウンロードし https://go.microsoft.com/fwlink/?LinkId=63266) ます。</span><span class="sxs-lookup"><span data-stu-id="c13e1-123">Download the [Microsoft Core XML Services (MSXML)6.0SP1 (x86)](https://go.microsoft.com/fwlink/?LinkId=63266) software package from the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=63266).</span></span>

2.  <span data-ttu-id="c13e1-124">サイレントインストールするには、コマンドラインオプション/quiet を使用します (例: **msiexec/i msxml6\_x86.msi/quiet**)。</span><span class="sxs-lookup"><span data-stu-id="c13e1-124">To install silently, use the command-line option /quiet—for example, **msiexec /i msxml6\_x86.msi /quiet**.</span></span>

### <span data-ttu-id="c13e1-125">Microsoft アプリケーションエラー報告をインストールするには</span><span class="sxs-lookup"><span data-stu-id="c13e1-125">To install Microsoft Application Error Reporting</span></span>

<span data-ttu-id="c13e1-126">Microsoft アプリケーションエラー報告をインストールする場合は、 *Appguid*パラメーターを使って app-v 製品コードを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c13e1-126">When installing Microsoft Application Error Reporting, you must use the *APPGUID* parameter to specify the App-V product code.</span></span> <span data-ttu-id="c13e1-127">製品コードは、各 App-v クライアントの種類とバージョンごとに異なります。</span><span class="sxs-lookup"><span data-stu-id="c13e1-127">The product code is unique for each App-V client type and version.</span></span> <span data-ttu-id="c13e1-128">次の表から正しい製品コードを選択します。</span><span class="sxs-lookup"><span data-stu-id="c13e1-128">Select the correct product code from the following table.</span></span>

<span data-ttu-id="c13e1-129">**重要** App-v 4.6 SP2 以降では、Microsoft アプリケーションエラー報告 (dw20shared.msi) をインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c13e1-129">**Important** For App-V4.6SP2 and later, you no longer need to install Microsoft Application Error Reporting (dw20shared.msi).</span></span> <span data-ttu-id="c13e1-130">現在、app-v は Microsoft エラー報告を使用しています。</span><span class="sxs-lookup"><span data-stu-id="c13e1-130">App-V now uses Microsoft Error Reporting.</span></span>

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c13e1-131">バージョン</span><span class="sxs-lookup"><span data-stu-id="c13e1-131">Version</span></span></th>
<th align="left"><span data-ttu-id="c13e1-132">デスクトップクライアントの製品コード</span><span class="sxs-lookup"><span data-stu-id="c13e1-132">Product Code for Desktop Client</span></span></th>
<th align="left"><span data-ttu-id="c13e1-133">リモートデスクトップサービスのクライアントの製品コード</span><span class="sxs-lookup"><span data-stu-id="c13e1-133">Product Code for Client for Remote Desktop Services</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c13e1-134">App-v 4.5 CU1</span><span class="sxs-lookup"><span data-stu-id="c13e1-134">App-V 4.5 CU1</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-135">FE495DBC-6D42-4698-B61F-86E655E0796D</span><span class="sxs-lookup"><span data-stu-id="c13e1-135">FE495DBC-6D42-4698-B61F-86E655E0796D</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-136">8A97C241-D92A-47DC-B360-E716C1AAA929</span><span class="sxs-lookup"><span data-stu-id="c13e1-136">8A97C241-D92A-47DC-B360-E716C1AAA929</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c13e1-137">App-v 4.5 SP1</span><span class="sxs-lookup"><span data-stu-id="c13e1-137">App-V 4.5 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-138">93468B43-C19D-44F9-8BCC-114076DB0443</span><span class="sxs-lookup"><span data-stu-id="c13e1-138">93468B43-C19D-44F9-8BCC-114076DB0443</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-139">0042AD3C-99A4-4E58-B5F0-744D5AD96E1C</span><span class="sxs-lookup"><span data-stu-id="c13e1-139">0042AD3C-99A4-4E58-B5F0-744D5AD96E1C</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c13e1-140">App-v 4.5 SP2</span><span class="sxs-lookup"><span data-stu-id="c13e1-140">App-V 4.5 SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-141">C6FC75B9-7D86-4C44-8BDB-EAFE1F0E200D</span><span class="sxs-lookup"><span data-stu-id="c13e1-141">C6FC75B9-7D86-4C44-8BDB-EAFE1F0E200D</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-142">ECF80BBA-CA07-4A74-9ED6-E064F38AF1F5</span><span class="sxs-lookup"><span data-stu-id="c13e1-142">ECF80BBA-CA07-4A74-9ED6-E064F38AF1F5</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c13e1-143">App-v 4.6 x86</span><span class="sxs-lookup"><span data-stu-id="c13e1-143">App-V 4.6 x86</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-144">9E9D30B2-2065-4FDE-B756-8F1A6EABAFC3</span><span class="sxs-lookup"><span data-stu-id="c13e1-144">9E9D30B2-2065-4FDE-B756-8F1A6EABAFC3</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-145">439FAC21-B4234-1D4-8126-54F9FCB70039</span><span class="sxs-lookup"><span data-stu-id="c13e1-145">439FAC21-B423-41D4-8126-54F9FCB70039</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c13e1-146">App-v 4.6 x64</span><span class="sxs-lookup"><span data-stu-id="c13e1-146">App-V 4.6 x64</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-147">E569E45F-7BA6-4C7F-B6BA-3FFCBE92FC22</span><span class="sxs-lookup"><span data-stu-id="c13e1-147">E569E45F-7BA6-4C7F-B6BA-3FFCBE92FC22</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-148">D2977C18-D88A-47CB-AFD8-652DD36F4D0D</span><span class="sxs-lookup"><span data-stu-id="c13e1-148">D2977C18-D88A-47CB-AFD8-652DD36F4D0D</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c13e1-149">App-v 4.6 x86 ¹</span><span class="sxs-lookup"><span data-stu-id="c13e1-149">App-V 4.6 x86 ¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-150">40C3258B-F9D1-46DF-AE97-72C1F86F2427</span><span class="sxs-lookup"><span data-stu-id="c13e1-150">40C3258B-F9D1-46DF-AE97-72C1F86F2427</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-151">9915D911-CC73-4122-AF4F-564F89454655</span><span class="sxs-lookup"><span data-stu-id="c13e1-151">9915D911-CC73-4122-AF4F-564F89454655</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c13e1-152">App-v 4.6 x64 ¹</span><span class="sxs-lookup"><span data-stu-id="c13e1-152">App-V 4.6 x64 ¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-153">1650E31FE23B8-40B5-A60A7B C5934F557E3B</span><span class="sxs-lookup"><span data-stu-id="c13e1-153">1650E31F-23B8-40B5-A60A-C5934F557E3B</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-154">7580D918-C621-49E7-9877-3CC59F9BD1DA</span><span class="sxs-lookup"><span data-stu-id="c13e1-154">7580D918-C621-49E7-9877-3CC59F9BD1DA</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c13e1-155">App-v 4.6 x86 SP1</span><span class="sxs-lookup"><span data-stu-id="c13e1-155">App-V 4.6 x86 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-156">DB9F70CD-29BC-480B-8BA2-C9C2232C4553</span><span class="sxs-lookup"><span data-stu-id="c13e1-156">DB9F70CD-29BC-480B-8BA2-C9C2232C4553</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-157">1354855A2-229847 C73-9022-EF0686C65991</span><span class="sxs-lookup"><span data-stu-id="c13e1-157">1354855A-2298-4C73-9022-EF0686C65991</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c13e1-158">App-v 4.6 x64 SP1</span><span class="sxs-lookup"><span data-stu-id="c13e1-158">App-V 4.6 x64 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-159">342C9BB8-65A0-46DE-AB7A-8031E151AF69</span><span class="sxs-lookup"><span data-stu-id="c13e1-159">342C9BB8-65A0-46DE-AB7A-8031E151AF69</span></span></p></td>
<td align="left"><p><span data-ttu-id="c13e1-160">B2C6C8D5-FE76-4056-A326-EE5D633EA175</span><span class="sxs-lookup"><span data-stu-id="c13e1-160">B2C6C8D5-FE76-4056-A326-EE5D633EA175</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="c13e1-161">¹ App-V "Languages" リリース。</span><span class="sxs-lookup"><span data-stu-id="c13e1-161">¹App-V “Languages” release.</span></span>

<span data-ttu-id="c13e1-162">**注** 製品コードを検索する必要がある場合は、Orca.exe データベースエディターまたは同様のツールを使用して、Windows インストーラーファイルを調べて、 *ProductCode*プロパティの値を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="c13e1-162">**Note** If you need to find the product code, you can use the Orca.exe database editor or a similar tool to examine Windows Installer files to find the value of the *ProductCode* property.</span></span> <span data-ttu-id="c13e1-163">Orca.exe の使い方の詳細については、「 [Windows インストーラー開発ツール](https://go.microsoft.com/fwlink/?LinkId=150008)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=150008) 。</span><span class="sxs-lookup"><span data-stu-id="c13e1-163">For more information about using Orca.exe, see [Windows Installer Development Tools](https://go.microsoft.com/fwlink/?LinkId=150008) (https://go.microsoft.com/fwlink/?LinkId=150008).</span></span>

 

****

1.  <span data-ttu-id="c13e1-164">[Microsoft アプリケーションエラー報告ツール] インストールプログラム、dw20shared.msi を見つけます。これは、リリースメディアの**support¥ Watson**フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="c13e1-164">Locate the Microsoft Application Error Reporting install program, dw20shared.msi, which can be found in the **Support\\Watson** folder on the release media.</span></span>

2.  <span data-ttu-id="c13e1-165">ソフトウェアをインストールするには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="c13e1-165">To install the software, run the following command:</span></span>

         **msiexec /i dw20shared.msi APPGUID={valuefromtable} REBOOT=Suppress REINSTALL=ALL REINSTALLMODE=vomus**

## <a href="" id="msi-setup"></a><span data-ttu-id="c13e1-166">Setup.msi プログラムを使用して App-v クライアントをインストールする</span><span class="sxs-lookup"><span data-stu-id="c13e1-166">Installing the App-V Client by Using the Setup.msi Program</span></span>


<span data-ttu-id="c13e1-167">次の手順を使用して、App-v クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c13e1-167">Use the following procedure to install the App-V client.</span></span> <span data-ttu-id="c13e1-168">必要なすべての必須ソフトウェアがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c13e1-168">Ensure that any necessary prerequisite software has been installed.</span></span> <span data-ttu-id="c13e1-169">\ [Template Token Value \] バージョン4.6 以降の App-v クライアントの場合、setup.msi プログラムはシステムをチェックし、必須ソフトウェアがインストールされていない場合は、インストールを続行できないことを示すエラーメッセージを生成します。</span><span class="sxs-lookup"><span data-stu-id="c13e1-169">\[Template Token Value\] For version4.6 and later of the App-V client, the setup.msi program checks the system and if prerequisite software is not installed, it generates an error message indicating that installation cannot continue.</span></span> <span data-ttu-id="c13e1-170">\ [テンプレートトークンの値 \]</span><span class="sxs-lookup"><span data-stu-id="c13e1-170">\[Template Token Value\]</span></span>

**<span data-ttu-id="c13e1-171">Setup.msi を使用して Application Virtualization クライアントをインストールするには</span><span class="sxs-lookup"><span data-stu-id="c13e1-171">To install the Application Virtualization Client by Using Setup.msi</span></span>**

1.  <span data-ttu-id="c13e1-172">コンピューターの管理者権限を持つアカウントでログオンしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c13e1-172">Make sure you are logged on with an account that has administrator rights on the computer.</span></span>

2.  <span data-ttu-id="c13e1-173">[昇格した権限] を使用してコマンドプロンプトウィンドウを開き、ディレクトリをセットアップファイルが格納されているフォルダーに変更します。</span><span class="sxs-lookup"><span data-stu-id="c13e1-173">Open a Command Prompt window by using elevated rights, and then change the directory to the folder that contains the setup files.</span></span> <span data-ttu-id="c13e1-174">バージョン4.6 以降バージョンの App-v クライアントをインストールする場合、コンピューターのオペレーティングシステム32ビットまたは64ビットに適切なインストーラーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c13e1-174">When installing version4.6 or a later version of the App-V client, you must use the correct installer for the computer’s operating system, 32-bit or 64-bit.</span></span> <span data-ttu-id="c13e1-175">インストールが失敗し、誤ったインストーラーを使用した場合にエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c13e1-175">The installation will fail and an error message will be displayed if you use the wrong installer.</span></span>

3.  <span data-ttu-id="c13e1-176">コマンドプロンプトで、install コマンド文字列を入力します。</span><span class="sxs-lookup"><span data-stu-id="c13e1-176">Enter the install command string at the command prompt.</span></span> <span data-ttu-id="c13e1-177">または、コマンドファイルを作成して、コマンドプロンプトから実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="c13e1-177">Alternatively, you can create a command file and run it from the command prompt.</span></span> <span data-ttu-id="c13e1-178">また、VBScript や Windows PowerShell などのスクリプト言語を使ってコマンドを実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="c13e1-178">You can also use a scripting language such as VBScript or Windows PowerShell to run the command.</span></span>

4.  <span data-ttu-id="c13e1-179">次のコマンドラインの例は、いくつかのオプションのパラメーターを使って setup.msi を使う方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="c13e1-179">The following command-line example shows how setup.msi can be used with a number of optional parameters.</span></span> <span data-ttu-id="c13e1-180">これらのパラメーターの詳細については、「 [Application Virtualization クライアントインストーラーのコマンドラインパラメーター](application-virtualization-client-installer-command-line-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c13e1-180">For more information about these parameters, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md).</span></span>

    **<span data-ttu-id="c13e1-181">msiexec.exe/i "setup.msi" SWICACHESIZE = "10240" SWIPUBSVRDISPLAY = "SWIPUBSVRTYPE =" SWIPUBSVRHOST = "PRODSYS" SWIPUBSVRPORT = "443" SWIPUBSVRPATH = "/AppVirt/appsntype.xml" SWIPUBSVRREFRESH = "SWIGLOBALDATA =" D:\\AppVirt\\Global = "SWIUSERDATA ="%\\Windows\\Application = "SWIFSDRIVE =" = "=" = "=" ^% LOCALAPPDATA ^ 仮想クライアント "=" S "</span><span class="sxs-lookup"><span data-stu-id="c13e1-181">msiexec.exe /i "setup.msi" SWICACHESIZE="10240" SWIPUBSVRDISPLAY="Production System" SWIPUBSVRTYPE="HTTP /secure" SWIPUBSVRHOST="PRODSYS" SWIPUBSVRPORT="443" SWIPUBSVRPATH="/AppVirt/appsntype.xml" SWIPUBSVRREFRESH="on" SWIGLOBALDATA="D:\\AppVirt\\Global" SWIUSERDATA="^% LOCALAPPDATA^%\\Windows\\Application Virtualization Client" SWIFSDRIVE="S" /q</span></span>**

    **<span data-ttu-id="c13e1-182">重要</span><span class="sxs-lookup"><span data-stu-id="c13e1-182">Important</span></span>**  
    -   <span data-ttu-id="c13e1-183">このようなサイレントインストールを行うには、Windows Installer スイッチ "**/q**" が使用されます。</span><span class="sxs-lookup"><span data-stu-id="c13e1-183">The Windows Installer switch "**/q**" is used to make this a silent installation.</span></span>

    -   <span data-ttu-id="c13e1-184">" **%** **% HomeDrive%**" の "" 文字の前には "" エスケープ文字を指定する必要があり **^** ます。</span><span class="sxs-lookup"><span data-stu-id="c13e1-184">The "**%**" characters in "**%HomeDrive%**" must be preceded by the "**^**" escape character.</span></span> <span data-ttu-id="c13e1-185">そうしないと、Windows コマンドシェルによって、インストールを実行しているユーザーの値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="c13e1-185">Otherwise, the Windows command shell sets the value to that of the user who is performing the installation.</span></span>

    -   <span data-ttu-id="c13e1-186">インストールログを有効にするには、msiexec スイッチ **/l\ \* v ファイル名**を使用します。</span><span class="sxs-lookup"><span data-stu-id="c13e1-186">To turn on installation logging, use the msiexec switch **/l\*v filename.log**.</span></span>

     

## <span data-ttu-id="c13e1-187">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c13e1-187">Related topics</span></span>


[<span data-ttu-id="c13e1-188">コマンド ラインを使用してクライアントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="c13e1-188">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





