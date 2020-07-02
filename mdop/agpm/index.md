---
title: 高度なグループ ポリシーの管理
description: 高度なグループ ポリシーの管理
author: dansimp
ms.assetid: 493ca3c3-c3d6-4bb1-9430-dc1e43c86bb0
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/23/2017
ms.openlocfilehash: 457cca9db5d39466691b0bc7c41455910b4483d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795656"
---
# <span data-ttu-id="587db-103">高度なグループ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="587db-103">Advanced Group Policy Management</span></span>


<span data-ttu-id="587db-104">Microsoft Advanced Group Policy Management (AGPM) では、グループポリシー管理コンソール (GPMC) の機能が拡張され、グループポリシーオブジェクト (Gpo) の包括的な変更の制御と管理の向上を実現します。</span><span class="sxs-lookup"><span data-stu-id="587db-104">Microsoft Advanced Group Policy Management (AGPM) extends the capabilities of the Group Policy Management Console (GPMC) to provide comprehensive change control and improved management for Group Policy Objects (GPOs).</span></span> <span data-ttu-id="587db-105">AGPM は、ソフトウェアアシュアランスの Microsoft デスクトップ最適化パック (MDOP) の一部として利用できます。</span><span class="sxs-lookup"><span data-stu-id="587db-105">AGPM is available as part of the Microsoft Desktop Optimization Pack (MDOP) for Software Assurance.</span></span>

## <span data-ttu-id="587db-106">AGPM のバージョン情報</span><span class="sxs-lookup"><span data-stu-id="587db-106">AGPM Version Information</span></span>


<span data-ttu-id="587db-107">[AGPM 4.0 SP3](agpm-40-sp3-navengl.md)は、windows 10、windows server 2019、windows server 2016、windows Server 2012 r2、windows 8.1、windows server 2012、windows Server 2008 r2、windows 7、windows server 2008、および WINDOWS Vista SP1 をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="587db-107">[AGPM 4.0 SP3](agpm-40-sp3-navengl.md) supports Windows 10, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows 8.1, Windows Server 2012, Windows Server 2008 R2, Windows 7, Windows Server 2008, and Windows Vista with SP1.</span></span>

<span data-ttu-id="587db-108">[AGPM 4.0 SP2](agpm-40-sp2-navengl.md)では、windows Server 2012 R2、windows 8.1、windows server 2012、windows Server 2008 R2、windows 7、windows server 2008、WINDOWS Vista SP1 がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="587db-108">[AGPM 4.0 SP2](agpm-40-sp2-navengl.md) supports Windows Server 2012 R2, Windows 8.1, Windows Server 2012, Windows Server 2008 R2, Windows 7, Windows Server 2008, and Windows Vista with SP1.</span></span>

<span data-ttu-id="587db-109">[AGPM 4.0 sp1](agpm-40-sp1-navengl.md)では、windows server 2012、windows Server 2008 R2、windows 7、windows server 2008、および WINDOWS Vista SP1 がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="587db-109">[AGPM 4.0 SP1](agpm-40-sp1-navengl.md) supports Windows Server 2012, Windows Server 2008 R2, Windows 7, Windows Server 2008, and Windows Vista with SP1.</span></span>

<span data-ttu-id="587db-110">[AGPM 4](agpm-4-navengl.md)では、windows Server 2008 R2、windows 7、windows Server 2008、および WINDOWS Vista SP1 がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="587db-110">[AGPM 4](agpm-4-navengl.md) supports Windows Server 2008 R2, Windows 7, Windows Server 2008, and Windows Vista with SP1.</span></span>

<span data-ttu-id="587db-111">[AGPM 3](agpm-3-navengl.md)では、windows Server 2008 と WINDOWS Vista SP1 がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="587db-111">[AGPM 3](agpm-3-navengl.md) supports Windows Server 2008 and Windows Vista with SP1.</span></span>

<span data-ttu-id="587db-112">[AGPM 2.5](agpm-25-navengl.md)は、service Pack と windows Server 2003 (32 ビット) を使用しない windows Vista (32 ビット) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="587db-112">[AGPM 2.5](agpm-25-navengl.md) supports Windows Vista (32-bit) with no service pack and Windows Server 2003 (32-bit).</span></span>

## <span data-ttu-id="587db-113">追加の MDOP 製品ガイダンス</span><span class="sxs-lookup"><span data-stu-id="587db-113">Supplemental MDOP Product Guidance</span></span>


<span data-ttu-id="587db-114">オンラインで利用できる製品ドキュメントに加えて、情報ビデオや仮想ラボなどの補足的な製品ガイダンスは、ほとんどの MDOP 製品で利用できます。</span><span class="sxs-lookup"><span data-stu-id="587db-114">In addition to the product documentation available online, supplemental product guidance such as informational videos and virtual labs are available for most MDOP products.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="587db-115">MDOP 仮想ラボ</span><span class="sxs-lookup"><span data-stu-id="587db-115">MDOP Virtual Labs</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="587db-116">使用可能な MDOP 仮想ラボの一覧については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=234276" data-raw-source="[Microsoft Desktop Optimization Pack (MDOP) Virtual Labs](https://go.microsoft.com/fwlink/?LinkId=234276)"> Microsoft デスクトップ最適化パック (MDOP) 仮想ラボ ()」を参照 </a> <a href="https://go.microsoft.com/fwlink/?LinkId=234276" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=234276"> https://go.microsoft.com/fwlink/?LinkId=234276 </a> してください。</span><span class="sxs-lookup"><span data-stu-id="587db-116">For a list of available MDOP virtual labs, go to <a href="https://go.microsoft.com/fwlink/?LinkId=234276" data-raw-source="[Microsoft Desktop Optimization Pack (MDOP) Virtual Labs](https://go.microsoft.com/fwlink/?LinkId=234276)">Microsoft Desktop Optimization Pack (MDOP) Virtual Labs</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=234276" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=234276">https://go.microsoft.com/fwlink/?LinkId=234276</a>).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="587db-117">MDOP の TechCenter</span><span class="sxs-lookup"><span data-stu-id="587db-117">MDOP TechCenter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="587db-118">技術関連のホワイトペーパー、評価資料、ブログ、その他の MDOP リソースについては、「 <a href="https://go.microsoft.com/fwlink/?LinkId=225286" data-raw-source="[MDOP TechCenter](https://go.microsoft.com/fwlink/?LinkId=225286)"> Mdop TechCenter ()」を参照してください </a> <a href="https://go.microsoft.com/fwlink/?LinkId=225286" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=225286"> https://go.microsoft.com/fwlink/?LinkId=225286 </a> 。</span><span class="sxs-lookup"><span data-stu-id="587db-118">For technical whitepapers, evaluation materials, blogs, and additional MDOP resources, go to <a href="https://go.microsoft.com/fwlink/?LinkId=225286" data-raw-source="[MDOP TechCenter](https://go.microsoft.com/fwlink/?LinkId=225286)">MDOP TechCenter</a> (<a href="https://go.microsoft.com/fwlink/?LinkId=225286" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=225286">https://go.microsoft.com/fwlink/?LinkId=225286</a>)</span></span></p>
<p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-getmdop"></a><span data-ttu-id="587db-119">MDOP の入手方法</span><span class="sxs-lookup"><span data-stu-id="587db-119">How to Get MDOP</span></span>


<span data-ttu-id="587db-120">MDOP は、デスクトップの展開、管理、および企業全体のサポートを合理化するために役立つ一連の製品です。</span><span class="sxs-lookup"><span data-stu-id="587db-120">MDOP is a suite of products that can help streamline desktop deployment, management, and support across the enterprise.</span></span> <span data-ttu-id="587db-121">MDOP は、ソフトウェアアシュアランスのお客様向けの追加サブスクリプションとして提供されています。</span><span class="sxs-lookup"><span data-stu-id="587db-121">MDOP is available as an additional subscription for Software Assurance customers.</span></span>

<a href="" id="evaluate-mdop"></a><span data-ttu-id="587db-122">**MDOP の評価**また、MDOP は、msdn および TechNet 契約書に従って、 [msdn](https://msdn.microsoft.com/subscriptions/downloads/default.aspx?PV=42:178)および[technet](https://technet.microsoft.com/subscriptions/downloads/default.aspx?PV=42:178)サブスクライバーへのテストと評価に使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="587db-122">**Evaluate MDOP** MDOP is also available for test and evaluation to [MSDN](https://msdn.microsoft.com/subscriptions/downloads/default.aspx?PV=42:178) and [TechNet](https://technet.microsoft.com/subscriptions/downloads/default.aspx?PV=42:178) subscribers in accordance with MSDN and TechNet agreements.</span></span>

<a href="" id="download-mdop"></a><span data-ttu-id="587db-123">**MDOP のダウンロード**MDOP 加入者は、 [Microsoft ボリュームライセンス web サイト (MVLS)](https://go.microsoft.com/fwlink/?LinkId=166331)でソフトウェアをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="587db-123">**Download MDOP** MDOP subscribers can download the software at the [Microsoft Volume Licensing website (MVLS)](https://go.microsoft.com/fwlink/?LinkId=166331).</span></span>

<a href="" id="purchase-mdop"></a><span data-ttu-id="587db-124">**MDOP の購入**企業向けに MDOP を購入する方法については、enterprise [Purchase Windows Enterprise ライセンス](https://www.microsoft.com/windows/enterprise/how-to-buy.aspx)web サイトを参照してください。</span><span class="sxs-lookup"><span data-stu-id="587db-124">**Purchase MDOP** Visit the enterprise [Purchase Windows Enterprise Licensing](https://www.microsoft.com/windows/enterprise/how-to-buy.aspx) website to find out how to purchase MDOP for your business.</span></span>

 

 





