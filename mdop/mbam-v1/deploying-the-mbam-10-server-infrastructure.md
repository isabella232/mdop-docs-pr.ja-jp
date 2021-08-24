---
title: MBAM 1.0 サーバー インフラストラクチャの展開
description: MBAM 1.0 サーバー インフラストラクチャの展開
author: dansimp
ms.assetid: 90529379-b70e-4c92-b188-3d7aaf1844af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 63099d425b51bfde52eac59771007b1c765acf05
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910422"
---
# <a name="deploying-the-mbam-10-server-infrastructure"></a>MBAM 1.0 サーバー インフラストラクチャの展開


Microsoft BitLocker Administration and Monitoring (MBAM) Server の機能は、1 台から 5 台のサーバーを使用して、異なる構成でインストールできます。 一般に、スケーラビリティのニーズに応じて、3 ~ 5 つのサーバーの構成を実稼働環境に使用する必要があります。 MBAM のパフォーマンスのスケーラビリティと推奨される展開トポロジの詳細については、「MBAM のスケーラビリティとセキュリティ ガイド [」High-Availabilityを参照してください](https://go.microsoft.com/fwlink/p/?LinkId=258314)。

## <a name="deploy-all-mbam-10-on-a-single-server"></a>すべての MBAM 1.0 を 1 つのサーバーに展開する


この構成では、すべての MBAM 機能が 1 つのサーバーにインストールされます。 MBAM サーバー インフラストラクチャのこの展開トポロジでは、最大 21,000 MBAM のクライアント コンピューターがサポートされます。

**重要**  
この構成はサポートされますが、テスト専用にすることをお勧めします。

 

このセクションの手順では、1 台のサーバーに MBAM 機能を完全にインストールする方法について説明します。

[単一サーバーに MBAM をインストールして構成する方法](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)

## <a name="deploy-mbam-10-on-distributed-servers"></a>分散サーバーに MBAM 1.0 を展開する


MBAM 機能は、スケーラビリティのニーズに応じて異なる構成でインストールできます。 MBAM サーバー機能の展開を計画する方法の詳細については [、「Planning for MBAM 1.0 Server Deployment」を参照してください](planning-for-mbam-10-server-deployment.md)。

このセクションの手順では、分散サーバーでの MBAM 機能の完全なインストールについて説明します。

### <a name="three-computer-configuration"></a>3 コンピューター構成

次の図は、MBAM の 3 つのコンピューター展開トポロジを示しています。 最大 55,000 MBAM クライアントをサポートする実稼働環境では、このトポロジをお勧めします。

![mbam 3 つのコンピューター展開トポロジ。](images/mbam-3-server.jpg)

この構成では、MBAM 機能が次の構成にインストールされます。

1.  回復およびハードウェア データベース、コンプライアンスと監査データベース、コンプライアンスレポートと監査レポートがサーバーにインストールされます。

2.  サーバーの管理および監視機能がサーバーにインストールされます。

3.  MBAM グループ ポリシー テンプレートは、グループ ポリシー オブジェクト (GPO) を変更できるコンピューターにインストールされます。

### <a name="four-computer-configuration"></a>4 台のコンピューター構成

次の図は、MBAM の 4 台のコンピューター展開トポロジを示しています。 最大 110,000 MBAM クライアントをサポートする実稼働環境では、このトポロジをお勧めします。

![mbam 4 台のコンピューター展開トポロジ。](images/mbam-4-computer.jpg)

この構成では、MBAM 機能が次の構成にインストールされます。

1.  回復およびハードウェア データベース、コンプライアンスと監査データベース、コンプライアンスレポートと監査レポートがサーバーにインストールされます。

2.  管理および監視サーバー機能は、ネットワーク負荷分散 (NLB) サーバー クラスターで構成されているサーバーにインストールされます。

3.  MBAM グループ ポリシー テンプレートは、グループ ポリシー オブジェクトを変更できるコンピューターにインストールされます。

### <a name="five-computer-configuration"></a>5 コンピューター構成

次の図は、MBAM の 5 コンピューター展開トポロジを示しています。 最大 135,000 MBAM クライアントをサポートする実稼働環境では、このトポロジをお勧めします。

![mbam 5 つのコンピューター展開トポロジ。](images/mbam-5-computer.jpg)

この構成では、MBAM 機能が次の構成にインストールされます。

1.  回復とハードウェア データベースがサーバーにインストールされます。

2.  コンプライアンスと監査データベースとコンプライアンスレポートと監査レポートがサーバーにインストールされます。

3.  管理および監視サーバー機能は、ネットワーク負荷分散 (NLB) サーバー クラスターで構成されているサーバーにインストールされます。

4.  MBAM グループ ポリシー テンプレートは、グループ ポリシー オブジェクトを変更できるコンピューターにインストールされます。

[分散サーバーに MBAM をインストールして構成する方法](how-to-install-and-configure-mbam-on-distributed-servers-mbam-1.md)

[MBAM のネットワーク負荷分散を構成する方法](how-to-configure-network-load-balancing-for-mbam.md)

## <a name="other-resources-for-mbam-10-server-features-deployment"></a>MBAM 1.0 Server 機能の展開に関するその他のリソース


[MBAM 1.0 の展開](deploying-mbam-10.md)

 

 





