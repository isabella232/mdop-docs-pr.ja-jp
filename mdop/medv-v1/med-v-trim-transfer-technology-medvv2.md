---
title: MED-V トリム転送テクノロジ
description: MED-V トリム転送テクノロジ
author: dansimp
ms.assetid: 2744e855-a486-4028-9606-f0084794ec65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa11c8036954070bbff465a6ad78992fdd52f3a2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826187"
---
# <span data-ttu-id="150de-103">MED-V トリム転送テクノロジ</span><span class="sxs-lookup"><span data-stu-id="150de-103">MED-V Trim Transfer Technology</span></span>


## <a href="" id="bkmk-medvtrimtransfertechnology"></a>


<span data-ttu-id="150de-104">MED-V の高度なトリム移行の重複除去技術は、LAN または WAN 経由で初期および更新された仮想マシンのイメージをダウンロードすることによって、複数のエンドユーザーに対して、MED-V ワークスペース仮想マシンをトランスポートするために必要なネットワーク帯域幅を削減します。</span><span class="sxs-lookup"><span data-stu-id="150de-104">The MED-V advanced Trim Transfer de-duplication technology accelerates the download of initial and updated virtual machine images over the LAN or WAN, thereby reducing the network bandwidth needed to transport a MED-V workspace virtual machine to multiple end users.</span></span>

<span data-ttu-id="150de-105">この画期的なテクノロジでは、既存のローカルデータを使用して仮想マシンのイメージを作成します。多くの場合、仮想マシンの大半 (システムファイルやアプリケーションファイルなど) がエンドユーザーのディスクに既に存在していることを意味します。</span><span class="sxs-lookup"><span data-stu-id="150de-105">This breakthrough technology uses existing local data to build the virtual machine image, leveraging the fact that in many cases, much of the virtual machine (for example, system and application files) already exists on the end user's disk.</span></span> <span data-ttu-id="150de-106">たとえば、windowsxp を含む仮想マシンが、ローカルコピーを実行しているクライアントに配信された場合、MED-V は冗長な WindowsXP 要素を転送から自動的に削除します。</span><span class="sxs-lookup"><span data-stu-id="150de-106">For example, if a virtual machine containing WindowsXP is delivered to a client running a local copy of WindowsXP, MED-V will automatically remove the redundant WindowsXP elements from the transfer.</span></span> <span data-ttu-id="150de-107">有効な機能のあるワークスペースを確保するために、MED-V クライアントは、使用される前にローカルデータの整合性を確認します。これにより、データのローカルブロックは、目的の仮想マシンイメージ内のデータとまったく同じように動作することが保証されます。</span><span class="sxs-lookup"><span data-stu-id="150de-107">To ensure a valid and functional workspace, the MED-V client cryptographically verifies the integrity of local data before it is utilized, guaranteeing that the local blocks of data are absolutely bit-by-bit identical to those in the desired virtual machine image.</span></span> <span data-ttu-id="150de-108">一致しないブロックは使用されません。</span><span class="sxs-lookup"><span data-stu-id="150de-108">Blocks that do not match are not used.</span></span>

<span data-ttu-id="150de-109">このプロセスでは、帯域幅を効率的に透過し、未使用のネットワークと CPU リソースを使用して、バックグラウンドで転送を実行します。</span><span class="sxs-lookup"><span data-stu-id="150de-109">The process is bandwidth-efficient and transparent, and transfers run in the background, utilizing unused network and CPU resources.</span></span>

<span data-ttu-id="150de-110">新しいイメージのバージョンに更新する場合 (たとえば、管理者が新しいアプリケーションまたは更新プログラムを配布する場合)、変更された要素 ("差分") のみがダウンロードされ、仮想マシン全体ではなく、必要なネットワーク帯域幅と配信時間が大幅に減少します。</span><span class="sxs-lookup"><span data-stu-id="150de-110">When updating to a new image version (for example, when administrators want to distribute a new application or patch), only the elements that have changed ("deltas") are downloaded, and not the entire virtual machine, significantly reducing the required network bandwidth and delivery time.</span></span>

<span data-ttu-id="150de-111">ホストオペレーティングシステムに基づいて、トリム転送プロトコルの一部として、ホスト上でインデックスを作成するフォルダーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="150de-111">You can configure which folders are indexed on the host as part of the Trim Transfer protocol, based on the host operating system.</span></span> <span data-ttu-id="150de-112">これらの設定は*ClientSettings.xml*ファイルで構成されます。この設定は、 \**Servers\\Configuration \**フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="150de-112">These settings are configured in the *ClientSettings.xml* file, which can be found in the **Servers\\Configuration Server\\** folder.</span></span>

<span data-ttu-id="150de-113">新しい設定を適用する場合は、サービスを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="150de-113">When applying new settings, the service must be restarted.</span></span>

```xml
<HostIndexingXP type="System.String[]"> 
- <ArrayOfString>
<string>%WINDIR%</string> 
<string>%ProgramFiles%\Common Files</string> 
<string>%ProgramFiles%\Internet Explorer</string> 
<string>%ProgramFiles%\MED-V</string> 
<string>%ProgramFiles%\Microsoft Office</string> 
<string>%ProgramFiles%\Windows NT</string> 
<string>%ProgramFiles%\Messenger</string> 
<string>%ProgramFiles%\Adobe</string> 
<string>%ProgramFiles%\Outlook Express</string> 
</ArrayOfString> 
</HostIndexingXP> 
- <HostIndexingVista type="System.String[]"> 
- <ArrayOfString> 
<string>%WINDIR%\MSAgent</string> 
<string>%WINDIR%\winsxs</string> 
<string>%WINDIR%\system</string> 
<string>%WINDIR%\system32</string> 
<string>%WINDIR%\Microsoft.NET</string> 
<string>%WINDIR%\SoftwareDistribution</string> 
<string>%WINDIR%\L2Schemas</string> 
<string>%WINDIR%\Cursors</string> 
<string>%WINDIR%\Boot</string> 
<string>%WINDIR%\Help</string> 
<string>%WINDIR%\assembly</string> 
<string>%WINDIR%\inf</string> 
<string>%WINDIR%\fonts</string> 
<string>%WINDIR%\Installer</string> 
<string>%WINDIR%\IME</string> 
<string>%WINDIR%\Resources</string> 
<string>%WINDIR%\servicing</string> 
<string>%ProgramFiles%\MED-V</string> 
<string>%ProgramFiles%\Microsoft Office</string> 
</ArrayOfString> 
</HostIndexingVista>
```

 

 





