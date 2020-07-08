---
title: MBAM 1.0 の保守
description: MBAM 1.0 の保守
author: dansimp
ms.assetid: 02ffb093-c364-4837-bbe8-23d4c09fbd3d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7eecef4e82680b08fde1b1bef88487a6fc156fe4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825774"
---
# MBAM 1.0 の保守


必要な計画がすべて完了して、Microsoft BitLocker の管理と監視 (MBAM) を展開した後、MBAM を高可用性の方法で実行し、エンタープライズの BitLocker 暗号化操作の管理に使用します。 このセクションの情報では、MBAM の高可用性オプションについて説明し、必要に応じて MBAM サーバー機能を移動する方法についても説明します。

## MBAM 管理パック


MBAM 用の MicrosoftSystemCenterOperationsManager 管理パックは、Microsoft ダウンロードセンターからダウンロードできます。

この管理パックは、web サービスとデータベース間の接続、web サイトとそのサービスの管理 web サービスとの間の通信など、サーバー側インフラストラクチャでの重要な操作を監視します。 また、デスクトップクライアントとその受信 web サービスエンドポイントの間の要求もアップロードします。

[Microsoft BitLocker 管理パックと監視管理パック](https://go.microsoft.com/fwlink/p/?LinkId=258390)

## MBAM 1.0 の高可用性を確保する


MBAM はフォールトトレラントとして設計されています。 サーバーが利用できなくなった場合は、ユーザーに悪影響を与えないようにしてください。 このセクションの情報は、高可用性の MBAM インストールを構成するために使用できます。

[MBAM 1.0 の高可用性](high-availability-for-mbam-10.md)

## MBAM 1.0 機能を別のサーバーに移動する


MBAM サーバー機能をサーバーコンピューター間で移動する必要がある場合は、特定の順序と必須の手順を実行して、生産性やデータの損失を回避する必要があります。 このセクションでは、1つまたは複数の MBAM サーバー機能を別のコンピューターに移動するために実行する必要のある手順について説明します。

[MBAM 1.0 機能を別のコンピューターに移動する方法](how-to-move-mbam-10-features-to-another-computer.md)

## MBAM を管理するためのその他のリソース


[MBAM 1.0 の操作](operations-for-mbam-10.md)

 

 





