---
title: MED-V 2.0 のエンド ツー エンドの展開シナリオ
description: MED-V 2.0 のエンド ツー エンドの展開シナリオ
author: dansimp
ms.assetid: 91bb5a9a-5fb1-4743-8494-9d4dee2ec222
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6d56e70ad359ebf2d76cf3f30f54f73cd9ca1c66
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826174"
---
# MED-V 2.0 のエンド ツー エンドの展開シナリオ


このサンプルシナリオ Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 では、複数のシナリオをエンドツーエンドで使用して、企業内の MED-V コンポーネントを展開することができます。 このサンプルシナリオは、個々のシナリオと手順をコンテキストにまとめる際に役立つケーススタディと考えることができます。

このセクションでは、企業内のエンドツーエンドのソリューションとして MED-V コンポーネントを展開するための基本的な情報と手順について説明します。

## MED-V の展開ステップバイステップのシナリオ


このステップバイステップのシナリオのトピックには、次のようなものがあります。

-   [Med-v 2.0 でサポートされている構成](med-v-20-supported-configurations.md)では、環境に Microsoft Enterprise Desktop VIRTUALIZATION (med-v) 2.0 をインストールして実行するために必要な要件について説明します。 このトピックでは、オペレーティングシステム要件、構成要件、および MED-V ワークスペースの要件について説明します。 このトピックには、MED-V 2.0 でサポートされている言語に関するローカライズ情報も含まれています。

-   [Med-v 2.0 展開の概要](med-v-20-deployment-overview.md)企業全体で med-v をインストールして展開するのに役立つ一般的な情報と手順について説明します。 MED-V コンポーネントはクライアントベースであり、既存のエンタープライズインフラストラクチャとプロセスを使用して配信および管理されます。 このトピックでは、med-v ソリューションの概要について説明します。 med-v ソリューションの概要について説明します。この記事では、展開する MED-V のインストールファイルと MED-V コンポーネントに関する情報が含まれています。 このトピックでは、MED-V のインストールと展開プロセスの概要についても説明します。

-   [Med-v の展開環境を準備する-](prepare-the-deployment-environment-for-med-v.md) hyper-v 2.0 展開用に環境を準備する方法について説明します。 このセクションでは、Microsoft Windows 7 や Active Directory インフラストラクチャなどの MED-V 環境で必要とされる前提条件について説明します。グループポリシーを使用して、オペレーティングシステム、アプリケーション、ユーザーの設定の一元管理と構成を提供します。 このセクションでは、Windows 仮想 PC や必要な Windows 仮想 PC の更新など、企業全体で MED-V 2.0 をインストールして展開するために必要な前提条件についても説明します。

-   [Med-v コンポーネントを展開](deploy-the-med-v-components.md)すると、すべての必要なインストールファイルと med-v コンポーネントをエンタープライズ全体にインストールするさまざまな方法について説明します。 MED-V をインストールして展開するには、通常、次の手順を実行します。

    1.  Med-v ワークスペースパッケージを作成するために使用する管理コンピューターに、 **Med-v Workspace パッケージャー**をインストールします。 詳細については、「 [Med-v ワークスペースパッケージャーをインストールする方法](how-to-install-the-med-v-workspace-packager.md)」を参照してください。

    2.  MED-V ワークスペースパッケージを作成してテストします。 詳細については、「 [Med-v ワークスペースパッケージを作成する](create-a-med-v-workspace-package.md)」および「 [Med-v ワークスペースパッケージのテスト](testing-the-med-v-workspace-package.md)」を参照してください。

    3.  会社の既存のアプリケーション展開方法を使用して、エンタープライズ全体で MED-V を展開します。 詳細については、「 [Med-v ワークスペースパッケージの展開](deploying-the-med-v-workspace-package.md)」を参照してください。

## 関連トピック


[MED-V の展開](deployment-of-med-v.md)

[MED-V 2.0 のエンド ツー エンドのプランニング シナリオ](end-to-end-planning-scenario-for-med-v-20.md)

[MED-V 2.0 のエンド ツー エンドの操作シナリオ](end-to-end-operations-scenario-for-med-v-20.md)

 

 





