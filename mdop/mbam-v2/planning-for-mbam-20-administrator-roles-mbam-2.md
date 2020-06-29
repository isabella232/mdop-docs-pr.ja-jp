---
title: MBAM 2.0 管理者ロールの計画
description: MBAM 2.0 管理者ロールの計画
author: dansimp
ms.assetid: 6f813297-6479-42d3-a21b-896d54466b5b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a89a04c0ef074407dc3cd081d351d44023e65e70
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824894"
---
# MBAM 2.0 管理者ロールの計画


このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) およびローカルグループが作成されているサーバーの場所で利用できる管理者ロールについて説明します。

## MBAM 管理者ロール


<a href="" id="---------------mbam-system-administrators"></a> **MBAM システム管理者**  
この役割の管理者は、Microsoft BitLocker のすべての管理機能と監視機能にアクセスできます。 この役割のローカルグループは、管理/監視サーバーにインストールされます。

<a href="" id="---------------mbam-helpdesk-users"></a> **MBAM ヘルプデスクユーザー**  
このロールの管理者は、MBAM からのヘルプデスク機能にアクセスできます。 この役割のローカルグループは、管理/監視サーバーにインストールされます。

<a href="" id="---------------mbam-report-users"></a> **MBAM レポートユーザー**  
このロールの管理者は、MBAM からのコンプライアンスおよび監査レポートにアクセスできます。 この役割のローカルグループは、管理/監視サーバー、コンプライアンスおよび監査データベース、コンプライアンスおよび監査レポートをホストしているサーバーにインストールされます。

<a href="" id="---------------mbam-advanced-helpdesk-users"></a> **MBAM Advanced ヘルプデスクユーザー**  
この役割の管理者は、MBAM からのヘルプデスク機能へのアクセス権を強化しています。 この役割のローカルグループは、管理/監視サーバーにインストールされます。 ユーザーが MBAM ヘルプデスクユーザーと MBAM Advanced ヘルプデスクユーザーの両方のメンバーである場合、MBAM Advanced ヘルプデスクのユーザーのアクセス許可は、MBAM ヘルプデスクのユーザーアクセス許可よりも優先されます。

**重要** レポートを表示するには、管理者ユーザーは、管理/監視サーバー、コンプライアンスおよび監査データベース、およびコンプライアンスと監査レポート機能をホストしているサーバー上の**Mbam レポートユーザー**セキュリティグループのメンバーである必要があります。 ベストプラクティスとして、ローカル**Mbam Report Users**セキュリティグループの権限を持つセキュリティグループを、管理と監視サーバーと、コンプライアンスと監査レポートをホストするサーバーの両方で作成します。

 

## 関連トピック


[MBAM 2.0 に対応する環境の準備](preparing-your-environment-for-mbam-20-mbam-2.md)

 

 





