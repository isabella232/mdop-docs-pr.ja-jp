---
title: セキュリティで保護された管理用の APP-V の構成
description: セキュリティで保護された管理用の APP-V の構成
author: dansimp
ms.assetid: 4543fa81-c8cc-4b10-83b7-060778eb1349
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c95fab4b2b4f402df4ff0f82f2f346c9bd226e00
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910482"
---
# <a name="configuring-app-v-for-secure-administration"></a>セキュリティで保護された管理用の APP-V の構成


管理操作のセキュリティ保護が重要な環境では、App-V を使用すると、App-V Web 管理サービスと App-V 管理コンソール間の安全な通信が可能になります。 管理サービスは Web ベースのアプリケーションなので、管理サービスをホストする Web サーバー上で App-V 管理サーバー アプリケーションをセキュリティ保護する必要があります。 次の図に示すように、このプロセスには、通信に HTTPS を使用し、統合認証のみを許可するように IIS サーバー Windows含まれます。

![app-v Web サービスのネットワーク構成。](images/appvmgmtwebservice.gif)

App-V Web 管理サービスは、IIS に Web ベースのアプリケーションとしてインストールされます。 Web 管理サービスが App-V 管理コンソールと Web 管理サービスの間でセキュリティで保護された (SSL) 接続をサポートするには、Web 管理サービスがインストールされている IIS サーバーを構成し、App-V 管理コンソールを構成する必要があります。

## <a name="in-this-section"></a>このセクションの内容


<a href="" id="configuring-certificates-to-support-the-app-v-web-management-service"></a>[App-V Web Management Service をサポートするための証明書の構成](configuring-certificates-to-support-the-app-v-web-management-service.md)  
App-V Web Management Service の通信をセキュリティで保護するために、SSL ベースの接続をサポートするための証明書の構成に関する役立つ情報を提供します。

<a href="" id="how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment"></a>[より安全な環境のために APP-V Management Console をインストールして構成する方法](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)  
セキュリティで保護された接続を使用して App-V Web 管理サービスに接続するための手順を詳しい手順で示します。

 

 





