---
title: 分散環境への App-V 管理の構成
description: 分散環境への App-V 管理の構成
author: dansimp
ms.assetid: 53971fa9-8319-435c-be74-c37feb9af1da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c1a638d6afde9270859c8aa98fc9f421c39cfc72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821914"
---
# 分散環境への App-V 管理の構成


特定の組織のインフラストラクチャを設計する場合は、app-v management Server をインストールするコンピューター以外のコンピューターに、App-v 管理 Web サービスをインストールできます。 これらの App-v コンポーネントを分離する一般的な理由には、次のようなものがあります。

-   パフォーマンス

-   信頼性

-   対象

-   スケーラビリティ

管理サーバーと管理 Web サービスを分離するには、インフラストラクチャが正常に動作するために追加の構成が必要です。 これらの2つの機能を分離しても、このトピックで説明する手順を実行しない場合、管理コンソールは管理 Web サービスに接続しますが、データストアで適切に認証することはできません。 管理コンソールが正しく読み込まれず、管理者が管理タスクをすべて実行できなくなります。

この動作が発生するのは、管理 Web サービスが管理コンソールから渡された資格情報を使用してデータストアにアクセスできないためです。 この解決策は、管理 Web サービスサーバーが委任に対して信頼されるように構成することです。

## Active Directory ドメインサービスの構成


また、分散環境で動作するように Active Directory ドメインサービスを適切に構成する必要があります。 このセクションには、Active Directory ドメインサービスを構成する必要がある情報が含まれています。

### SQL サービスがローカルシステムアカウントを使用している場合

SQL サービスがローカルシステムアカウントを使用している環境をセットアップするには、委任に対して信頼されるように、管理 Web サービスのコンピューターアカウントのプロパティを変更します。 この方法の詳細な手順については、「[委任に対して信頼されるようにサーバーを構成する方法](how-to-configure-the-server-to-be-trusted-for-delegation.md)」を参照してください。

### SQL サービスでドメインベースのアカウントを使用している場合

SQL Server がドメインベースのサービスアカウントを使用する環境をセットアップするには、次のようなさまざまな要因が適用されるかどうかを検討する必要があります。

-   SQL Server のクラスタリング

-   レプリケーション

-   自動化されたタスク

-   リンクサーバー

SQL サービスがドメインベースのアカウントを使用している場合の Active Directory ドメインサービスの構成の詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=151968> 。

 

 





