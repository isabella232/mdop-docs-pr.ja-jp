---
title: Application Virtualization Client のログ ファイル
description: Application Virtualization Client のログ ファイル
author: dansimp
ms.assetid: ac4b3e4a-a220-4c06-bd60-af7dc318b3a9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 52908aa583d3d673b8a229df14e56f1c71633ef4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816227"
---
# <span data-ttu-id="223aa-103">Application Virtualization Client のログ ファイル</span><span class="sxs-lookup"><span data-stu-id="223aa-103">Log File for the Application Virtualization Client</span></span>


<span data-ttu-id="223aa-104">Application Virtualization (App-v) クライアントのログファイルには、操作とエラー状態に関する詳細情報がキャプチャされます。</span><span class="sxs-lookup"><span data-stu-id="223aa-104">The log file for the Application Virtualization (App-V) Client captures detailed information about operations and error conditions.</span></span> <span data-ttu-id="223aa-105">機能を確認するとき、および問題のトラブルシューティングを行うときに使用できます。</span><span class="sxs-lookup"><span data-stu-id="223aa-105">You can use it when you are verifying functionality and when you are troubleshooting issues.</span></span>

<span data-ttu-id="223aa-106">App-v クライアントが最初にインストールされると、次の表に示す場所に既定でログファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="223aa-106">When the App-V Client is first installed, the log file is created by default in the location shown in the following table.</span></span> <span data-ttu-id="223aa-107">ログファイルの場所は Application Virtualization (App-v) 4.5 では新しくなりましたが、クライアントが以前のバージョンからアップグレードされた場合、場所は変更されません。</span><span class="sxs-lookup"><span data-stu-id="223aa-107">The location of the log file is new for Application Virtualization (App-V) 4.5, although the location will not be changed if the client is upgraded from an earlier version.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="223aa-108">ログファイル名</span><span class="sxs-lookup"><span data-stu-id="223aa-108">Log File Name</span></span></th>
<th align="left"><span data-ttu-id="223aa-109">説明</span><span class="sxs-lookup"><span data-stu-id="223aa-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="223aa-110">sftlog.txt</span><span class="sxs-lookup"><span data-stu-id="223aa-110">sftlog.txt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="223aa-111">App-v クライアントの操作とエラーに関する一般的な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="223aa-111">Provides general information about App-V Client operations and errors.</span></span> <span data-ttu-id="223aa-112">このログは、App-v クライアントエラーのトラブルシューティングの出発点として使用します。</span><span class="sxs-lookup"><span data-stu-id="223aa-112">Use this log as a starting point for troubleshooting App-V Client errors.</span></span></p>
<p><span data-ttu-id="223aa-113">デスクトップクライアント、またはリモートデスクトップサービス (以前のターミナルサービス) のクライアントのログファイルの場所:</span><span class="sxs-lookup"><span data-stu-id="223aa-113">Log file location for either the Desktop Client or the Client for Remote Desktop Services (formerly Terminal Services):</span></span></p>
<ul>
<li><p><em><span data-ttu-id="223aa-114">C:\documents and と Settings\All Users\Application Data\Microsoft\Application Virtualization クライアント </em> : WindowsXP、Windows Server 2003</span><span class="sxs-lookup"><span data-stu-id="223aa-114">C:\Documents and Settings\All Users\Application Data\Microsoft\Application Virtualization Client</em>: WindowsXP, Windows Server 2003</span></span></p></li>
<li><p><em><span data-ttu-id="223aa-115">C:\ProgramData\Microsoft\Application 仮想化クライアント </em> : Windows Vista、Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="223aa-115">C:\ProgramData\Microsoft\Application Virtualization Client</em>: Windows Vista, Windows Server 2008</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="223aa-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="223aa-116">Related topics</span></span>


[<span data-ttu-id="223aa-117">Application Virtualization Client リファレンス</span><span class="sxs-lookup"><span data-stu-id="223aa-117">Application Virtualization Client Reference</span></span>](application-virtualization-client-reference.md)

 

 





