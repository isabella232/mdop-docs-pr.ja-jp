---
title: クライアント ログ ファイルを構成する方法
description: クライアント ログ ファイルを構成する方法
author: dansimp
ms.assetid: dd79f8ce-61e2-4dc8-af03-2a353554a1b2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 729089d683c5d102eb7eb45314583023d3362639
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817797"
---
# <span data-ttu-id="4a44e-103">クライアント ログ ファイルを構成する方法</span><span class="sxs-lookup"><span data-stu-id="4a44e-103">How to Configure the Client Log File</span></span>


<span data-ttu-id="4a44e-104">次の手順を使用して、Application Virtualization (App-v) クライアントログファイルを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="4a44e-104">You can use the following procedures to configure the Application Virtualization (App-V) Client log file.</span></span>

**<span data-ttu-id="4a44e-105">ログファイルの場所を変更するには</span><span class="sxs-lookup"><span data-stu-id="4a44e-105">To change the log file location</span></span>**

-   <span data-ttu-id="4a44e-106">次のレジストリキーの値を編集して、ログファイルの新しいパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="4a44e-106">Edit the following registry key value to specify the new path for the log file.</span></span> <span data-ttu-id="4a44e-107">この値を変更した後で、 **sftlist**サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a44e-107">You must restart the **sftlist** service after changing this value.</span></span> <span data-ttu-id="4a44e-108">この場所は、インストール後に対話的に変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="4a44e-108">This location can also be changed interactively after installation.</span></span>

    <span data-ttu-id="4a44e-109">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogFileName</span><span class="sxs-lookup"><span data-stu-id="4a44e-109">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogFileName</span></span>

**<span data-ttu-id="4a44e-110">ログレポートのレベルを変更するには</span><span class="sxs-lookup"><span data-stu-id="4a44e-110">To change the log reporting level</span></span>**

-   <span data-ttu-id="4a44e-111">既定では、ログに書き込まれるメッセージの種類には、重大度レベル 4 (情報) 以上のすべてのイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4a44e-111">By default, the type of messages that are written to the log include all events of severity level 4 (Informational) or higher.</span></span> <span data-ttu-id="4a44e-112">重大度レベルは、次のキー値に格納されます。</span><span class="sxs-lookup"><span data-stu-id="4a44e-112">The severity level is stored in the following key value.</span></span> <span data-ttu-id="4a44e-113">詳細ログを有効にするには、このキー値を5に設定します。</span><span class="sxs-lookup"><span data-stu-id="4a44e-113">Set this key value to 5 to enable verbose logging.</span></span> <span data-ttu-id="4a44e-114">詳細ログは、非常に大量のメッセージを生成し、ログがすぐにいっぱいになるため、トラブルシューティングの際には短い期間のみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="4a44e-114">Use verbose logging only for short periods during troubleshooting because it will generate a very large volume of messages and cause the log to fill up quickly.</span></span>

    <span data-ttu-id="4a44e-115">HKEY \ _LOCAL \ _MACHINE ¥ $ ¥ (英語) \ のソフトの最小の構成 \\ logminseverity</span><span class="sxs-lookup"><span data-stu-id="4a44e-115">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogMinSeverity</span></span>

**<span data-ttu-id="4a44e-116">ログサイズを変更するには</span><span class="sxs-lookup"><span data-stu-id="4a44e-116">To change the log size</span></span>**

-   <span data-ttu-id="4a44e-117">Application Virtualization (App-v) 4.5 では、ログサイズは次のレジストリキー値によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="4a44e-117">In Application Virtualization (App-V) 4.5, the log size is controlled by the following registry key value.</span></span> <span data-ttu-id="4a44e-118">この値は既定で256MB になり、リセットされるまでにログが増加する最大サイズ (MB 単位) を定義します。</span><span class="sxs-lookup"><span data-stu-id="4a44e-118">This value defaults to 256MB and defines the maximum size, in MB, that the log can grow to before being reset.</span></span>

    <span data-ttu-id="4a44e-119">HKEY \ _LOCAL \ _MACHINE ¥ $ ¥ (英語) \ すべてのソフト (\\) \ logmaxsize</span><span class="sxs-lookup"><span data-stu-id="4a44e-119">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogMaxSize</span></span>

    <span data-ttu-id="4a44e-120">**注意** ログファイルがリセットされるようにするには、このレジストリキーの値を0より大きい値に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4a44e-120">**Caution** This registry key value must be set to a value greater than zero to ensure the log file does get reset.</span></span>

     

**<span data-ttu-id="4a44e-121">バックアップコピーの数を変更するには</span><span class="sxs-lookup"><span data-stu-id="4a44e-121">To change the number of backup copies</span></span>**

-   <span data-ttu-id="4a44e-122">ログファイルが最大サイズに達すると、ログの次の書き込みが発生するときにリセットが強制されます。</span><span class="sxs-lookup"><span data-stu-id="4a44e-122">When the log file reaches the maximum size, a reset is forced when the next write to the log occurs.</span></span> <span data-ttu-id="4a44e-123">リセットすると、新しいログファイルが作成され、古いファイルはバックアップとして名前が変更されます。</span><span class="sxs-lookup"><span data-stu-id="4a44e-123">A reset causes a new log file to be created, and the old file is renamed as a backup.</span></span> <span data-ttu-id="4a44e-124">次のレジストリ設定は、ファイルがリセットされたときに保持されるログファイルのバックアップコピーの数を制御します。</span><span class="sxs-lookup"><span data-stu-id="4a44e-124">The following registry setting controls the number of backup copies of the log file that are kept when the file is reset.</span></span> <span data-ttu-id="4a44e-125">既定値は4です。</span><span class="sxs-lookup"><span data-stu-id="4a44e-125">The default value is 4.</span></span>

    <span data-ttu-id="4a44e-126">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogRolloverCount</span><span class="sxs-lookup"><span data-stu-id="4a44e-126">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Configuration\\LogRolloverCount</span></span>

    <span data-ttu-id="4a44e-127">バックアップログファイル名の形式は次のとおりです。再設定時刻 (UTC) でのリセット時間に基づいて、 **sftlog\_YYYYMMDD\_hhmmss-uuu.txt**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="4a44e-127">The format of the backup log file names is: **sftlog\_YYYYMMDD\_hhmmss-uuu.txt** and is based on the reset time, in Universal Coordinated Time (UTC).</span></span> <span data-ttu-id="4a44e-128">次の表に、ファイル名とその説明の作成に使用する記号を示します。</span><span class="sxs-lookup"><span data-stu-id="4a44e-128">The following table lists the symbols used in creating the file names and their descriptions.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="4a44e-129">シンボル</span><span class="sxs-lookup"><span data-stu-id="4a44e-129">Symbol</span></span></th>
    <th align="left"><span data-ttu-id="4a44e-130">説明</span><span class="sxs-lookup"><span data-stu-id="4a44e-130">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="4a44e-131">YYYY</span><span class="sxs-lookup"><span data-stu-id="4a44e-131">YYYY</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4a44e-132">4桁の年</span><span class="sxs-lookup"><span data-stu-id="4a44e-132">4-digit year</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="4a44e-133">TU</span><span class="sxs-lookup"><span data-stu-id="4a44e-133">MM</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4a44e-134">2桁の月 (01 ~ 12)</span><span class="sxs-lookup"><span data-stu-id="4a44e-134">2-digit month (01–12)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="4a44e-135">DD</span><span class="sxs-lookup"><span data-stu-id="4a44e-135">DD</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4a44e-136">月を2桁の日付で表記します (01 ~ 31)。</span><span class="sxs-lookup"><span data-stu-id="4a44e-136">2-digit day of the month (01–31)</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="4a44e-137">かつ</span><span class="sxs-lookup"><span data-stu-id="4a44e-137">hh</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4a44e-138">hour (00 ~ 23)</span><span class="sxs-lookup"><span data-stu-id="4a44e-138">hour (00–23)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="4a44e-139">tu</span><span class="sxs-lookup"><span data-stu-id="4a44e-139">mm</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4a44e-140">分 (00 ~ 59)</span><span class="sxs-lookup"><span data-stu-id="4a44e-140">minutes (00–59)</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="4a44e-141">ss</span><span class="sxs-lookup"><span data-stu-id="4a44e-141">ss</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4a44e-142">秒 (00 ~ 59)</span><span class="sxs-lookup"><span data-stu-id="4a44e-142">seconds (00–59)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="4a44e-143">uuu</span><span class="sxs-lookup"><span data-stu-id="4a44e-143">uuu</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4a44e-144">ミリ秒 (000 ~ 999)</span><span class="sxs-lookup"><span data-stu-id="4a44e-144">milliseconds (000–999)</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

## <span data-ttu-id="4a44e-145">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4a44e-145">Related topics</span></span>


[<span data-ttu-id="4a44e-146">コマンド ラインを使用して App-V Client レジストリ設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="4a44e-146">How to Configure the App-V Client Registry Settings by Using the Command Line</span></span>](how-to-configure-the-app-v-client-registry-settings-by-using-the-command-line.md)

 

 





