---
title: App-V インストール後のチェックリスト
description: App-V インストール後のチェックリスト
author: dansimp
ms.assetid: 74db297e-a744-4287-bcc6-0e096ca8b57a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 79728bd2043076b20eb37ba0b1fa6f834a0d94bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819804"
---
# <span data-ttu-id="a8d53-103">App-V インストール後のチェックリスト</span><span class="sxs-lookup"><span data-stu-id="a8d53-103">App-V Postinstallation Checklist</span></span>


<span data-ttu-id="a8d53-104">次のチェックリストは、考慮すべき項目の概要と、Microsoft Application Virtualization (App-v) Management Server、App-v Streaming Server、および App-v Desktop Client のインストールを完了した後に実行する必要がある手順の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="a8d53-104">The following checklist provides a high-level list of items to consider and outlines the steps you should take after you have completed the installation of the Microsoft Application Virtualization (App-V) Management Server, App-V Streaming Server, and the App-V Desktop Client.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a8d53-105">ステップ</span><span class="sxs-lookup"><span data-stu-id="a8d53-105">Step</span></span></th>
<th align="left"><span data-ttu-id="a8d53-106">リファレンス</span><span class="sxs-lookup"><span data-stu-id="a8d53-106">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a8d53-107">App-v Management Server または Streaming Server サービスのファイアウォール例外を作成します。</span><span class="sxs-lookup"><span data-stu-id="a8d53-107">Create firewall exceptions for the App-V Management Server or Streaming Server services.</span></span></p></td>
<td align="left"><p><a href="configuring-the-firewall-for-the-app-v-servers.md" data-raw-source="[Configuring the Firewall for the App-V Servers](configuring-the-firewall-for-the-app-v-servers.md)"><span data-ttu-id="a8d53-108">App-V サーバー用にファイアウォールを構成する</span><span class="sxs-lookup"><span data-stu-id="a8d53-108">Configuring the Firewall for the App-V Servers</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a8d53-109">既定のアプリケーションの発行、ストリーミング、テストを行って、App-v システムが正常に動作していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a8d53-109">Verify that the App-V system is functioning correctly by publishing, streaming, and testing the default application.</span></span></p></td>
<td align="left"><p><a href="how-to-install-and-configure-the-default-application.md" data-raw-source="[How to Install and Configure the Default Application](how-to-install-and-configure-the-default-application.md)"><span data-ttu-id="a8d53-110">既定のアプリケーションをインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="a8d53-110">How to Install and Configure the Default Application</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a8d53-111"><strong>ApplicationSourceRoot </strong> 、 <strong> IconSourceRoot </strong> 、および <strong> osdsourceroot 設定を使って、アプリまたは他のサーバーを使用してストリーミングを行うように app-v クライアントを構成 </strong> します。</span><span class="sxs-lookup"><span data-stu-id="a8d53-111">Configure the App-V Client to use the App-V Streaming Server or other server for streaming by means of the <strong>ApplicationSourceRoot</strong>, <strong>IconSourceRoot</strong>, and <strong>OSDSourceRoot</strong> settings.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-client-for-application-package-retrieval.md" data-raw-source="[How to Configure the Client for Application Package Retrieval](how-to-configure-the-client-for-application-package-retrieval.md)"><span data-ttu-id="a8d53-112">アプリケーション パッケージを取得するためにクライアントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a8d53-112">How to Configure the Client for Application Package Retrieval</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a8d53-113">オフラインで展開するための、順序付けされたアプリケーションパッケージの .msi ファイルバージョンの使い方について説明します。</span><span class="sxs-lookup"><span data-stu-id="a8d53-113">Understand how to use the .msi file version of sequenced application packages for offline deployment.</span></span></p></td>
<td align="left"><p><a href="how-to-publish-a-virtual-application-on-the-client.md" data-raw-source="[How to Publish a Virtual Application on the Client](how-to-publish-a-virtual-application-on-the-client.md)"><span data-ttu-id="a8d53-114">クライアントで仮想アプリケーションを公開する方法</span><span class="sxs-lookup"><span data-stu-id="a8d53-114">How to Publish a Virtual Application on the Client</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a8d53-115">省略App-v データベースの SQL Server データベースミラーリングを構成します。</span><span class="sxs-lookup"><span data-stu-id="a8d53-115">(Optional) Configure SQL Server database mirroring for the App-V database.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-microsoft-sql-server-mirroring-support-for-app-v.md" data-raw-source="[How to Configure Microsoft SQL Server Mirroring Support for App-V](how-to-configure-microsoft-sql-server-mirroring-support-for-app-v.md)"><span data-ttu-id="a8d53-116">App-V 用に Microsoft SQL Server ミラーリングのサポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a8d53-116">How to Configure Microsoft SQL Server Mirroring Support for App-V</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="a8d53-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a8d53-117">Related topics</span></span>


[<span data-ttu-id="a8d53-118">Application Virtualization の展開およびアップグレードのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="a8d53-118">Application Virtualization Deployment and Upgrade Checklists</span></span>](application-virtualization-deployment-and-upgrade-checklists.md)

 

 





