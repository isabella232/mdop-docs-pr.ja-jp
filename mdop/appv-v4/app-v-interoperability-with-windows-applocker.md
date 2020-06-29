---
title: App-V と Windows AppLocker の相互運用性
description: App-V と Windows AppLocker の相互運用性
author: dansimp
ms.assetid: 9a488034-607d-411c-b495-ff184c726f49
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6f67bb87c0a4474acee3c4982b65c930e86c4917
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822314"
---
# <span data-ttu-id="b6362-103">App-V と Windows AppLocker の相互運用性</span><span class="sxs-lookup"><span data-stu-id="b6362-103">App-V Interoperability with Windows AppLocker</span></span>


<span data-ttu-id="b6362-104">Microsoft Application Virtualization (App-v) クライアントのバージョン 4.5 SP1 は、Windows 7 の AppLocker 機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b6362-104">Version 4.5 SP1 of the Microsoft Application Virtualization (App-V) client supports the AppLocker feature of Windows 7.</span></span> <span data-ttu-id="b6362-105">AppLocker 機能を使用すると、IT 管理者はコンピューターでの実行を制限するアプリケーションを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b6362-105">The AppLocker feature enables IT administrators to specify which applications are restricted from running on computers.</span></span> <span data-ttu-id="b6362-106">このドキュメントでは、App-v の仮想環境と仮想化されたアプリケーションと連携するように AppLocker の規則を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6362-106">This document describes how to configure the AppLocker rules to work with the App-V virtual environment and virtualized applications.</span></span>

<span data-ttu-id="b6362-107">**注** 仮想アプリケーションの Windows AppLocker ルールを構成するには、まず windows AppLocker を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6362-107">**Note** Windows AppLocker must first be enabled before configuring Windows AppLocker rules for virtual applications.</span></span> <span data-ttu-id="b6362-108">Windows AppLocker を有効にする方法の詳細については、 [Windows applocker](https://go.microsoft.com/fwlink/?LinkId=156732) ( https://go.microsoft.com/fwlink/?LinkId=156732) .</span><span class="sxs-lookup"><span data-stu-id="b6362-108">For more information about enabling Windows AppLocker, [Windows AppLocker](https://go.microsoft.com/fwlink/?LinkId=156732) (https://go.microsoft.com/fwlink/?LinkId=156732).</span></span>

 

## <span data-ttu-id="b6362-109">仮想アプリケーションの Windows AppLocker ルールを構成する</span><span class="sxs-lookup"><span data-stu-id="b6362-109">Configuring Windows AppLocker Rules for Virtual Applications</span></span>


<span data-ttu-id="b6362-110">ローカル管理者は、プログラムの実行可能ファイル (.exe ファイル)、Windows インストーラーファイル (.msi および .msp ファイル)、スクリプト (.ps、.bat、.cmd、.vbs、.js ファイル) の実行を制限する Windows AppLocker ルールを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b6362-110">Local administrators can create Windows AppLocker rules that restrict the running of program executables (.exe files), Windows Installer files (.msi and .msp files), and scripts (.ps, .bat, .cmd, .vbs and .js files).</span></span> <span data-ttu-id="b6362-111">これを行うには、管理者は、App-v クライアントがインストールされていて、すべての関連仮想アプリケーションがクライアントキャッシュにストリーミングされている参照コンピューターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b6362-111">The administrator does this by using a reference computer that has the App-V client installed and that has all the relevant virtual applications streamed to the client cache.</span></span> <span data-ttu-id="b6362-112">次に、管理者は、参照コンピューターのローカルセキュリティポリシー Microsoft 管理コンソール (MMC) スナップインの [Windows AppLocker] セクションを使用して、ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="b6362-112">The administrator then uses the Windows AppLocker section of the Local Security Policy Microsoft Management Console (MMC) snap-in on the reference computer to create the rules.</span></span>

<span data-ttu-id="b6362-113">ルールを作成するディレクトリパスまたは特定のファイルを参照するときに、非表示の共有へのパスを使用して、App-v ドライブにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b6362-113">When you browse to find a directory path or specific file for which you want to create a rule, you can access the App-V drive by using the path to the hidden share.</span></span> <span data-ttu-id="b6362-114">たとえば、アプリ-V ドライブがドライブ Q の場合、\\ Localhost\\ Q $ を参照することができます。ただし、ルールを作成するには、パスを編集して、\\ ¥ Localhost\\ Q $ への参照を削除し、代わりに Q:\\ を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6362-114">For example, you can browse to \\\\localhost\\Q$, where the App-V drive is drive Q. However, to create the rule, you must edit the path to remove the reference to \\\\localhost\\Q$ and use Q:\\ instead.</span></span> <span data-ttu-id="b6362-115">参照コンピューターで各アプリケーションを起動して、アプリケーションのファイルにアクセスする必要があります。また、\ ¥ localhost¥ Q $ を参照するには、管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="b6362-115">You must start each application on the reference computer to access the application’s files, and administrative rights are required to browse to \\\\localhost\\Q$.</span></span>

 

 





