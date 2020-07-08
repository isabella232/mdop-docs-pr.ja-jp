---
title: MBAM 1.0 管理者ロールの計画
description: MBAM 1.0 管理者ロールの計画
author: dansimp
ms.assetid: 95be0eb4-25e9-43ca-a8e7-27373d35544d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 104d650824330ea990881c520a7811511f496dd1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825887"
---
# MBAM 1.0 管理者ロールの計画


このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) で利用できる管理者の役割と、ローカルグループが作成されているサーバーの場所について説明します。

## MBAM 管理者ロール


<a href="" id="---------------mbam-system-administrators"></a> **MBAM システム管理者**  
この役割の管理者は、すべての MBAM 機能にアクセスできます。 この役割のローカルグループは、管理/監視サーバーにインストールされます。

<a href="" id="---------------mbam-hardware-users"></a> **MBAM ハードウェアユーザー**  
この役割の管理者は、MBAM からハードウェア機能機能にアクセスできます。 この役割のローカルグループは、管理/監視サーバーにインストールされます。

<a href="" id="---------------mbam-helpdesk-users"></a> **MBAM ヘルプデスクユーザー**  
この役割の管理者は、MBAM のヘルプデスク機能にアクセスできます。 この役割のローカルグループは、管理/監視サーバーにインストールされます。

<a href="" id="---------------mbam--report-users"></a> **MBAM レポートユーザー**  
このロールの管理者は、MBAM からコンプライアンスと監査レポート機能にアクセスできます。 この役割のローカルグループは、管理/監視サーバー、コンプライアンスおよび監査データベース、コンプライアンスおよび監査レポートをホストしているサーバーにインストールされます。

<a href="" id="---------------mbam--advanced-helpdesk-users"></a> **MBAM Advanced ヘルプデスクユーザー**  
この役割の管理者は、MBAM のヘルプデスク機能へのアクセスを強化しています。 この役割のローカルグループは、管理/監視サーバーにインストールされます。 ユーザーが MBAM ヘルプデスクユーザーと MBAM Advanced ヘルプデスクユーザーの両方のメンバーである場合、MBAM Advanced ヘルプデスクのユーザーアクセス許可によって、MBAM ヘルプデスクのユーザーアクセス許可が上書きされます。

**重要** レポートを表示するには、管理者ユーザーは、管理/監視サーバー、コンプライアンスおよび監査データベース、およびコンプライアンスとレポート機能をホストするサーバー上の**Mbam レポートユーザー**セキュリティグループのメンバーである必要があります。 ベストプラクティスとして、管理サーバーと監視サーバーの両方、またはコンプライアンスとレポートをホストしているサーバー上で、local **Mbam Report Users**セキュリティグループの権限を持つ Active Directory でセキュリティグループを作成します。

 

## 関連トピック


[MBAM 1.0 に対応する環境の準備](preparing-your-environment-for-mbam-10.md)

 

 





