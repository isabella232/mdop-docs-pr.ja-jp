---
title: MBAM 2.0 に対応する環境の準備
description: MBAM 2.0 に対応する環境の準備
author: dansimp
ms.assetid: 5fb01da9-620e-4992-9e54-2ed3fb69e6af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f1be989112d456064db302952d50159d00b5597a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825607"
---
# MBAM 2.0 に対応する環境の準備


Microsoft BitLocker の管理と監視 (MBAM) のセットアップを開始する前に、製品をインストールするための前提条件を満たしていることを確認してください。 前提条件が事前に判明していることがわかっている場合は、組織のビジネス目標を効率的にサポートするために、製品を効率的に展開し、その機能を有効にすることができます。

Microsoft System Center Configuration Manager 2007 または MicrosoftSystemCenter2012 ConfigurationManager を使用して Microsoft BitLocker の管理と監視を展開している場合は、「 [Configuration manager で MBAM を展開するための計画](planning-to-deploy-mbam-with-configuration-manager-2.md)」を参照してください。

## MBAM 2.0 の展開の前提条件を確認する


MBAM クライアントと MBAM サーバーの各機能には、適切にインストールする前に満たす必要がある特定の前提条件があります。

MBAM クライアントと MBAM サーバー機能を正常にインストールするには、MBAM Client または MBAM Server 機能のインストール用に指定されたコンピューターが、MBAM セットアップ用に適切に準備されていることを確認します。

**注** MBAM セットアップインストールを開始する前に、すべての前提条件が満たされていることを確認します。 すべての前提条件が満たされていない場合、セットアップは失敗します。

 

[MBAM 2.0 展開の前提条件](mbam-20-deployment-prerequisites-mbam-2.md)

## MBAM 2.0 グループポリシー要件を計画する


MBAM で企業のクライアントを管理するには、環境の暗号化要件のグループポリシーを定義する必要があります。

**重要** MBAM は、スタンドアロンの BitLocker ドライブ暗号化のポリシーでは動作しません。 MBAM には、グループポリシー設定を定義する必要があります。または、BitLocker 暗号化と強制適用は失敗します。

 

[MBAM 2.0 グループ ポリシー要件の計画](planning-for-mbam-20-group-policy-requirements-mbam-2.md)

## MBAM 2.0 管理者ロールの計画


MBAM 管理者ロールは、BitLocker の管理および監視サーバー、コンプライアンスおよび監査レポート機能、コンプライアンスおよび監査ステータスデータベースをインストールするときに、MBAM セットアップによって作成されるローカルグループによって管理されます。

Microsoft BitLocker の管理と監視の役割のメンバーシップは、ActiveDirectoryDomainServices でセキュリティグループを作成し、適切な管理者アカウントをこれらのグループに追加して、これらのセキュリティグループを BitLocker 管理とローカルグループの監視に追加することによって、最適な管理を行うことができます。 詳細については、「 [MBAM 管理者ロールを管理する方法](how-to-manage-mbam-administrator-roles-mbam-2.md)」を参照してください。

## MBAM の計画に関するその他のリソース


[MBAM 2.0 の計画](planning-for-mbam-20-mbam-2.md)

[MBAM 2.0 がサポートされる構成](mbam-20-supported-configurations-mbam-2.md)

 

 





