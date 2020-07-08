---
title: App-V Web Management Service をサポートするための証明書の構成
description: App-V Web Management Service をサポートするための証明書の構成
author: dansimp
ms.assetid: b7960161-2c19-4cbf-a98a-d4b06f547dce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 23839e6fad79c1f10eb2416941396ad3c6f04d26
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821887"
---
# App-V Web Management Service をサポートするための証明書の構成


通信をセキュリティで保護するために、SSL ベースの接続をサポートするように App-v Web 管理サービスを構成する必要があります。 このプロセスでは、管理サービスがインストールされている Web サーバーまたはコンピューターに、サービスまたはコンピューターに発行された証明書が必要です。

次のシナリオは、この目的で証明書を取得する方法を示しています。

1.  会社のインフラストラクチャには、自動的に証明書をコンピューターに発行する公開キー基盤 (PKI) が用意されています。

2.  会社のインフラストラクチャには、既に PKI が実装されていますが、コンピューターに対して自動的に証明書が発行されることはありません。

3.  会社のインフラストラクチャには、PKI は用意されていません。

上記のそれぞれのシナリオでは、証明書を取得する方法は異なりますが、最終的な結果は同じになります。 管理者は、IIS の既定の Web サイトに証明書を割り当てる必要があります。また、セキュリティで保護された通信を要求するように App-v Web Management サービスを構成する必要があります。

**重要** 証明書の名前は、サーバーの名前と一致する必要があります。 証明書の共通名には完全修飾ドメイン名 (Fqdn) を使用することをお勧めします。

 

App-v では、IIS サーバーを使用して、さまざまなインフラストラクチャ構成をサポートできます。 HTTPS をサポートするように IIS サーバーを構成する方法の詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=151972> 。

## 関連トピック


[より安全な環境のために APP-V Management Console をインストールして構成する方法](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)

 

 





