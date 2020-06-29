---
title: APP-V シーケンス処理中のセキュリティの強化
description: APP-V シーケンス処理中のセキュリティの強化
author: dansimp
ms.assetid: f30206dd-5749-4a27-bbaf-61fc21b9c663
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ba97c334c4ac9a928fee3d69c265c12e82e43619
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816357"
---
# <span data-ttu-id="b1ef2-103">APP-V シーケンス処理中のセキュリティの強化</span><span class="sxs-lookup"><span data-stu-id="b1ef2-103">Improving Security During App-V Sequencing</span></span>


<span data-ttu-id="b1ef2-104">順序付け用のパッケージアプリケーションは、App-v インフラストラクチャの中で実行される最大の作業です。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-104">Packaging applications for sequencing is the largest ongoing task in an App-V infrastructure.</span></span> <span data-ttu-id="b1ef2-105">このタスクは継続的なものであるため、アプリケーションを優先する場合は、ポリシーと手順を慎重に作成することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-105">Because this task is ongoing, you should carefully consider creating policies and procedures to follow when sequencing applications.</span></span> <span data-ttu-id="b1ef2-106">アプリ-V 4.5 では、シーケンス中に、仮想化されたアプリケーションのファイルアセットにアクセス制御リスト (Acl) をキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-106">In App-V4.5, during sequencing, you can capture Access Control Lists (ACLs) on the file assets of the virtualized application.</span></span>

## <span data-ttu-id="b1ef2-107">Sequencer でのウイルススキャン</span><span class="sxs-lookup"><span data-stu-id="b1ef2-107">Virus Scanning on the Sequencer</span></span>


<span data-ttu-id="b1ef2-108">シーケンスコンピューターにスキャンソフトウェアをインストールしてから、ウイルスとマルウェアをスキャンするようにコンピューターをスキャンすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-108">It is a best practice to install the scanning software on the sequencing computer and then scan the computer for viruses and malware.</span></span> <span data-ttu-id="b1ef2-109">シーケンスコンピューターがスキャンされ、ウイルスやマルウェアが含まれていない場合は、アプリケーションを順序付けする前に、すべてのウイルス対策コンピューターとマルウェア検出ソフトウェアを含むスキャンソフトウェアを無効にします。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-109">After the sequencing computer is scanned and free of any viruses or malware, disable the scanning software, including all antivirus and malware detection software, on the sequencing computer before sequencing any applications.</span></span> <span data-ttu-id="b1ef2-110">これにより、シーケンス処理が高速化され、シーケンス中にスキャンソフトウェアコンポーネントが検出されず、仮想アプリケーションパッケージに含まれなくなります。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-110">This speeds the sequencing process and prevents the scanning software components from being detected during sequencing and included in the virtual application package.</span></span>

## <span data-ttu-id="b1ef2-111">ファイル (NTFS) で Acl をキャプチャする</span><span class="sxs-lookup"><span data-stu-id="b1ef2-111">Capturing ACLs on Files (NTFS)</span></span>


<span data-ttu-id="b1ef2-112">Sequencer は、シーケンスのインストールフェーズで監視されるファイルの NTFS アクセス許可 (Acl) をキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-112">The Sequencer captures NTFS permissions (the ACLs) for the files that are monitored during the sequencing installation phase.</span></span> <span data-ttu-id="b1ef2-113">(App-v 4.5 のリリース前に、シーケンス処理の一環として Acl がキャプチャされませんでした)。この新機能により、管理者特権が必要となる低レベルのアクセス許可を持つユーザーが、特定のアプリケーションを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-113">(Before the release of App-V4.5, ACLs were not captured as part of the sequencing process.) This new feature enables certain applications to run for users with a low level of permission that would normally require Administrative privileges.</span></span>

<span data-ttu-id="b1ef2-114">この機能では、ベンダーによって識別されたセキュリティ設定をシーケンスエンジニアがキャプチャすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-114">This feature also enables the sequencing engineer to capture the security settings identified by the vendor.</span></span> <span data-ttu-id="b1ef2-115">ベンダーによって推奨された設定を適用できない場合は、アプリケーションを開いたままにして、ユーザーによる攻撃や悪用を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-115">Failing to apply the settings recommended by the vendor could leave the application open to attack or misuse by users.</span></span> <span data-ttu-id="b1ef2-116">オープン Acl を使用してアプリケーションを展開する必要があるかどうかについては、「アプリケーションサポートグループ」または「ソフトウェアベンダー」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-116">For information about whether or not you should deploy an application with open ACLs, refer to your application support group or the software vendor.</span></span>

<span data-ttu-id="b1ef2-117">**重要** Sequencer は、シーケンスのインストールフェーズを監視しながら NTFS Acl をキャプチャしますが、レジストリの Acl はキャプチャしません。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-117">**Important** Although the sequencer captures the NTFS ACLs while monitoring the installation phase of sequencing, it does not capture the ACLs for the registry.</span></span> <span data-ttu-id="b1ef2-118">ユーザーは、サービスを除く仮想アプリケーションのすべてのレジストリキーへのフルアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-118">Users have full access to all registry keys for virtual applications except for services.</span></span> <span data-ttu-id="b1ef2-119">ただし、ユーザーが仮想アプリケーションのレジストリを変更すると、その変更は特定の場所 () に保存され、 `uservol_sftfs_v1.pkg` 他のユーザーには影響しません。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-119">However, if a user modifies the registry of a virtual application, that change is stored in a specific location (`uservol_sftfs_v1.pkg`) and won’t affect other users.</span></span>

 

<span data-ttu-id="b1ef2-120">インストールフェーズでは、必要に応じて、シーケンスエンジニアがファイルの既定のアクセス許可を変更できます。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-120">During the installation phase, a sequencing engineer can modify the default permissions of the files if necessary.</span></span> <span data-ttu-id="b1ef2-121">シーケンス処理が完了した後、パッケージを保存する前に、シーケンスエンジニアはインストールフェーズでキャプチャされたセキュリティ記述子を適用することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-121">After the sequencing process is complete, but before saving the package, the sequencing engineer can then choose to enforce security descriptors that were captured during the installation phase.</span></span> <span data-ttu-id="b1ef2-122">他のソリューションでは、仮想化されたアプリケーションを適切に実行することを許可していない場合は、セキュリティ記述子を適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b1ef2-122">It is a best practice to enforce security descriptors if no other solution allows the application to run properly once virtualized.</span></span>

 

 





