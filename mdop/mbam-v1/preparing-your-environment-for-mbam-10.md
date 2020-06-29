---
title: MBAM 1.0 に対応する環境の準備
description: MBAM 1.0 に対応する環境の準備
author: dansimp
ms.assetid: 915f7c3c-70ad-4a90-a434-73e7fba97ecb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a2de4e825d5c89aeabcf57d78dc856bacb03e11
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823194"
---
# MBAM 1.0 に対応する環境の準備


Microsoft BitLocker の管理と監視 (MBAM) セットアップを始める前に、製品をインストールするために必要な前提条件を満たしていることを確認してください。 事前に前提条件がわかっている場合は、製品を効率的に展開し、その機能を有効にすることができます。これにより、組織のビジネス目標がより効率的にサポートされます。

## MBAM 1.0 の展開の前提条件を確認する


MBAM クライアントと MBAM サーバーの各機能には、適切にインストールする前に満たす必要がある特定の前提条件があります。

MBAM クライアントと MBAM サーバー機能を正常にインストールするには、MBAM Client または MBAM Server 機能のインストール用に指定されたコンピューターが MBAM セットアップ用に正しく準備されていることを確認する必要があります。

**注** MBAM セットアップインストールを開始する前に、すべての前提条件が満たされているかどうかを確認します。 満たされていない場合、セットアップは失敗します。

 

[MBAM 1.0 展開の前提条件](mbam-10-deployment-prerequisites.md)

## MBAM 1.0 グループポリシー要件を計画する


MBAM で企業のクライアントを管理するには、環境の暗号化要件のグループポリシーを定義する必要があります。

**重要** MBAM は、スタンドアロンの BitLocker ドライブ暗号化のポリシーでは動作しません。 MBAM にはグループポリシーを定義する必要があります。そうしないと、BitLocker の暗号化と強制は失敗します。

 

[MBAM 1.0 グループ ポリシー要件の計画](planning-for-mbam-10-group-policy-requirements.md)

## MBAM 1.0 管理者ロールの計画


MBAM 管理者ロールは、BitLocker の管理と監視のサーバー、コンプライアンスおよび監査レポート機能、コンプライアンスおよび監査ステータスデータベースをインストールするときに、MBAM セットアップによって作成されるローカルグループによって管理されます。

MBAM ロールのメンバーシップは、より効率的に管理することができます。 ActiveDirectoryDomainServices でセキュリティグループを作成し、そのグループに適切な管理者アカウントを追加して、これらのセキュリティグループを MBAM ローカルグループに追加します。 詳細については、「 [MBAM 管理者ロールを管理する方法](how-to-manage-mbam-administrator-roles-mbam-1.md)」を参照してください。

[MBAM 1.0 管理者ロールの計画](planning-for-mbam-10-administrator-roles.md)

## MBAM の計画に関するその他のリソース


[MBAM 1.0 の計画](planning-for-mbam-10.md)

 

 





