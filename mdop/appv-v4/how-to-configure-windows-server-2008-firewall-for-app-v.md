---
title: App-V 用に Windows Server 2008 ファイアウォールを構成する方法
description: App-V 用に Windows Server 2008 ファイアウォールを構成する方法
author: dansimp
ms.assetid: 57f4ed17-0651-4a3c-be1e-29d9520c6aeb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 19e4cda9ac3b908f68e4f69b9663033d8a21ae41
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817717"
---
# <span data-ttu-id="2dca1-103">App-V 用に Windows Server 2008 ファイアウォールを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2dca1-103">How to Configure Windows Server 2008 Firewall for App-V</span></span>


<span data-ttu-id="2dca1-104">Windows Server2008 を導入することで、ファイアウォールと IPsec コンポーネントが1つのサービスに統合され、このサービスの機能が強化されました。</span><span class="sxs-lookup"><span data-stu-id="2dca1-104">With the introduction of Windows Server2008, the firewall and IPsec components were merged into one service, and the capabilities of this service were enhanced.</span></span> <span data-ttu-id="2dca1-105">新しいファイアウォールサービスでは、受信と発信のステートフル検査がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2dca1-105">The new firewall service supports incoming and outgoing stateful inspection.</span></span> <span data-ttu-id="2dca1-106">また、グループポリシーを使用して、特定のファイアウォール規則と IPsec ポリシーを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2dca1-106">Also, you can configure specific firewall rules and IPsec policies through group policies.</span></span> <span data-ttu-id="2dca1-107">Windows Server2008 の Windows ファイアウォールの詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=151980> 。</span><span class="sxs-lookup"><span data-stu-id="2dca1-107">For additional information about the Windows firewall in Windows Server2008, see <https://go.microsoft.com/fwlink/?LinkId=151980>.</span></span>

<span data-ttu-id="2dca1-108">次の手順では、SMB または HTTP/HTTPS での ICO と OSD の公開の例外の追加については説明しません。</span><span class="sxs-lookup"><span data-stu-id="2dca1-108">The following procedure does not include adding an exception for ICO and OSD publishing through SMB or HTTP/HTTPS.</span></span> <span data-ttu-id="2dca1-109">これらの例外は、Windows Server 2008 ファイアウォールにインストールされているネットワークプロファイルとロールに基づいて自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="2dca1-109">Those exceptions are automatically added based on the network profile and roles installed on the Windows Server 2008 firewall.</span></span>

<span data-ttu-id="2dca1-110">**注** 管理サーバーが RTSP を使用するように構成されている場合は、この手順を繰り返し `sghwsvr.exe` てプログラムを例外として追加します。</span><span class="sxs-lookup"><span data-stu-id="2dca1-110">**Note** If the Management Server is configured to use RTSP, repeat this procedure to add the `sghwsvr.exe` program as an exception.</span></span>

<span data-ttu-id="2dca1-111">App-v ストリーミングサーバーには、RTSPS 通信のプログラム例外が必要です `sglwdsptr.exe` 。</span><span class="sxs-lookup"><span data-stu-id="2dca1-111">The App-V Streaming Server requires the program exception `sglwdsptr.exe` for RTSPS communication.</span></span> <span data-ttu-id="2dca1-112">接続用に RTSP を使用する App-v ストリーミングサーバーでは、のプログラム例外も必要です `sglwsvr.exe` 。</span><span class="sxs-lookup"><span data-stu-id="2dca1-112">An App-V Streaming Server that uses RTSP for communication also requires a program exception for `sglwsvr.exe`.</span></span>

 

**<span data-ttu-id="2dca1-113">Windows Server2008 firewall for App-v を構成するには</span><span class="sxs-lookup"><span data-stu-id="2dca1-113">To configure Windows Server2008 firewall for App-V</span></span>**

1.  <span data-ttu-id="2dca1-114">コントロールパネルを使用するか、または [実行] 行に入力して、**高度なセキュリティ管理コンソールを使用して Windows ファイアウォール**を開き `wf.msc` ます。</span><span class="sxs-lookup"><span data-stu-id="2dca1-114">Open the **Windows Firewall with Advanced Security** management console through the Control Panel or by typing `wf.msc` on the Run line.</span></span>

2.  <span data-ttu-id="2dca1-115">新しい受信ルールを作成し、[**プログラム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2dca1-115">Create a new inbound rule, and select **Program**.</span></span>

3.  <span data-ttu-id="2dca1-116">プログラムパスを選択して、[ `sghwdsptr.exe` 既定で使用されている] の場所を参照し `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin` ます。</span><span class="sxs-lookup"><span data-stu-id="2dca1-116">Select the program path, and browse to `sghwdsptr.exe`, which is located by default at `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\bin`.</span></span>

4.  <span data-ttu-id="2dca1-117">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dca1-117">Click **Next**.</span></span>

5.  <span data-ttu-id="2dca1-118">[**操作**] ページで、[**接続を許可する**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dca1-118">On the **Action** page, select **Allow the connection**, and then click **Next**.</span></span>

6.  <span data-ttu-id="2dca1-119">受信ルールに適用する適切な**プロファイル**を選択します。</span><span class="sxs-lookup"><span data-stu-id="2dca1-119">Select the appropriate **Profiles** to apply to the inbound rule.</span></span>

7.  <span data-ttu-id="2dca1-120">ルールの名前と説明を入力し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2dca1-120">Provide a name and description for the rule, and click **Finish**.</span></span>

## <span data-ttu-id="2dca1-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2dca1-121">Related topics</span></span>


[<span data-ttu-id="2dca1-122">App-V 用に Windows Server 2003 ファイアウォールを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2dca1-122">How to Configure Windows Server 2003 Firewall for App-V</span></span>](how-to-configure-windows-server-2003-firewall-for-app-v.md)

 

 





