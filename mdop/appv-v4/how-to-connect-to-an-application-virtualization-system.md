---
title: Application Virtualization システムに接続する方法
description: Application Virtualization システムに接続する方法
author: dansimp
ms.assetid: ac38216c-5464-4c0b-a4d3-3949ba6358ac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 30d60e187e1b7595fd0dce6641fa027a1df68f3d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817714"
---
# <span data-ttu-id="502eb-103">Application Virtualization システムに接続する方法</span><span class="sxs-lookup"><span data-stu-id="502eb-103">How to Connect to an Application Virtualization System</span></span>


<span data-ttu-id="502eb-104">管理コンソールを使用して、アプリケーション、ファイルの種類の関連付け、パッケージ、アプリケーションライセンス、サーバーグループ、プロバイダーポリシー、管理者を管理するには、application Virtualization Server 管理コンソールをアプリケーションの仮想化システムに接続する必要があります。</span><span class="sxs-lookup"><span data-stu-id="502eb-104">You must connect the Application Virtualization Server Management Console to an Application Virtualization System before you can use the management console to manage applications, file type associations, packages, application licenses, server groups, provider policies and administrators.</span></span> <span data-ttu-id="502eb-105">次の手順では、本体をアプリケーションの仮想化システムに接続するために必要な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="502eb-105">The following procedure outlines the steps you must follow to connect the console to an Application Virtualization System.</span></span>

**<span data-ttu-id="502eb-106">アプリケーションの仮想化システムに接続するには</span><span class="sxs-lookup"><span data-stu-id="502eb-106">To connect to an Application Virtualization System</span></span>**

1. <span data-ttu-id="502eb-107">**スコープ**ウィンドウで [Application virtualization system] ノードを右クリックし、ポップアップメニューから [**アプリケーション仮想化システムに接続する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="502eb-107">Right-click the Application Virtualization System node in the **Scope** pane, and select **Connect to Application Virtualization System** from the pop-up menu.</span></span>

   **<span data-ttu-id="502eb-108">注</span><span class="sxs-lookup"><span data-stu-id="502eb-108">Note</span></span>**  
   <span data-ttu-id="502eb-109">Application Virtualization server の管理には、Application Virtualization 管理コンソール、管理 Web サービス、SQL データストアという3つのコンポーネントがあります。</span><span class="sxs-lookup"><span data-stu-id="502eb-109">There are three components to Application Virtualization server management: the Application Virtualization Management Console, the Management Web Service, and the SQL Datastore.</span></span> <span data-ttu-id="502eb-110">これらのコンポーネントが複数の物理マシンに分散されている場合は、コンポーネントがシステム間で通信するためのセキュリティを適切に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="502eb-110">If these components are distributed across different physical machines, you must configure security properly for the components to communicate across the system.</span></span> <span data-ttu-id="502eb-111">詳細については、次のマニュアルと記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="502eb-111">For more information, see the following manuals and articles:</span></span>

   <span data-ttu-id="502eb-112">[委任に対して信頼されるようにサーバーを構成する方法](https://go.microsoft.com/fwlink/?LinkID=166682)(https://go.microsoft.com/fwlink/?LinkID=166682)</span><span class="sxs-lookup"><span data-stu-id="502eb-112">[How to Configure the Server to be Trusted for Delegation](https://go.microsoft.com/fwlink/?LinkID=166682) (https://go.microsoft.com/fwlink/?LinkID=166682)</span></span>

   <span data-ttu-id="502eb-113">[Application Virtualization システムの計画と展開ガイド](https://go.microsoft.com/fwlink/?LinkID=122063)(https://go.microsoft.com/fwlink/?LinkID=122063)</span><span class="sxs-lookup"><span data-stu-id="502eb-113">[Planning and Deployment Guide for the Application Virtualization System](https://go.microsoft.com/fwlink/?LinkID=122063) (https://go.microsoft.com/fwlink/?LinkID=122063)</span></span>

   <span data-ttu-id="502eb-114">[Application Virtualization システムの運用ガイド](https://go.microsoft.com/fwlink/?LinkID=133129)(https://go.microsoft.com/fwlink/?LinkID=133129)</span><span class="sxs-lookup"><span data-stu-id="502eb-114">[Operations Guide for the Application Virtualization System](https://go.microsoft.com/fwlink/?LinkID=133129) (https://go.microsoft.com/fwlink/?LinkID=133129)</span></span>

   <span data-ttu-id="502eb-115">Microsoft サポート技術情報の[記事 930472](https://go.microsoft.com/fwlink/?LinkId=114647) (https://go.microsoft.com/fwlink/?LinkId=114647)</span><span class="sxs-lookup"><span data-stu-id="502eb-115">[Article 930472](https://go.microsoft.com/fwlink/?LinkId=114647) in the Microsoft Knowledge Base (https://go.microsoft.com/fwlink/?LinkId=114647)</span></span>

   <span data-ttu-id="502eb-116">Microsoft サポート技術情報の[記事 930565](https://go.microsoft.com/fwlink/?LinkId=114648) (https://go.microsoft.com/fwlink/?LinkId=114648)</span><span class="sxs-lookup"><span data-stu-id="502eb-116">[Article 930565](https://go.microsoft.com/fwlink/?LinkId=114648) in the Microsoft Knowledge Base (https://go.microsoft.com/fwlink/?LinkId=114648)</span></span>

     

2. <span data-ttu-id="502eb-117">[**アプリケーション仮想化システムに接続**します] ダイアログボックスのフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="502eb-117">Complete the fields in the **Connect to Application Virtualization System** dialog box:</span></span>

   1. <span data-ttu-id="502eb-118">[ **Web Service Host Name**]: 接続するアプリケーションの仮想化システムの名前を入力するか、ローカルサーバーに接続するには**localhost**を入力します。</span><span class="sxs-lookup"><span data-stu-id="502eb-118">**Web Service Host Name**—Enter the name of the Application Virtualization System to which you want to connect, or enter **localhost** to connect to the local server.</span></span>

   2. <span data-ttu-id="502eb-119">[**セキュリティで保護さ**れた接続を使用する]: セキュリティで保護された接続でサーバーに接続する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="502eb-119">**Use Secure Connection**—Select this check box if you want to connect to the server with a secure connection.</span></span>

   3. <span data-ttu-id="502eb-120">[ **Port (ポート**) 数-接続に使用するポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="502eb-120">**Port**—Enter the port number you want to use for the connection.</span></span> <span data-ttu-id="502eb-121">**80**は既定の標準ポート番号で、 **443**はセキュリティで保護されたポート番号です。</span><span class="sxs-lookup"><span data-stu-id="502eb-121">**80** is the default regular port number, and **443** is the secure-port number.</span></span>

   4. <span data-ttu-id="502eb-122">[**現在の Windows アカウントを使用**する] —現在の windows アカウントの資格情報を使用する場合は、このラジオボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="502eb-122">**Use Current Windows Account**—Select this radio button to use the current Windows account credentials.</span></span>

   5. <span data-ttu-id="502eb-123">[ **Windows アカウントの指定**]: 別のユーザーとしてサーバーに接続する場合は、このラジオボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="502eb-123">**Specify Windows Account**—Select this radio button when you want to connect to the server as a different user.</span></span>

   6. <span data-ttu-id="502eb-124">**名前**: *DOMAIN\\username*または username@domain のいずれかの形式を使用して、新しいユーザーの名前を入力し <em> </em> ます。</span><span class="sxs-lookup"><span data-stu-id="502eb-124">**Name**—Enter the name of the new user by using either the *DOMAIN\\username* or the <em>username@domain</em> format.</span></span>

   7. <span data-ttu-id="502eb-125">[ **Password (パスワード**) 新しいユーザーに対応するパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="502eb-125">**Password**—Enter the password that corresponds to the new user.</span></span>

3. <span data-ttu-id="502eb-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="502eb-126">Click **OK**.</span></span>

## <span data-ttu-id="502eb-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="502eb-127">Related topics</span></span>


[<span data-ttu-id="502eb-128">Application Virtualization サーバー管理コンソールで管理タスクを実行する方法</span><span class="sxs-lookup"><span data-stu-id="502eb-128">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

 

 





