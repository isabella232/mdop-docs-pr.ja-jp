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
ms.openlocfilehash: de70c1df734bbf1168fd7dacf9410d3451a8a3c2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821904"
---
# セキュリティで保護された管理用の APP-V の構成


管理操作がセキュリティで保護されている環境では、app-v では、app-v Web Management サービスと App-v 管理コンソールの間で安全な通信を行うことができます。 管理サービスは Web ベースのアプリケーションであるため、管理サービスをホストしている Web サーバー上で App-v Management Server アプリケーションをセキュリティで保護する必要があります。 次の図に示すように、このプロセスでは、通信に HTTPS を使用し、Windows 統合認証のみを許可するように IIS サーバーを構成しています。

![app-v web service のネットワーク構成](images/appvmgmtwebservice.gif)

App-v Web 管理サービスは、IIS 上の Web ベースのアプリケーションとしてインストールされます。 Web 管理サービスで、App-v 管理コンソールと Web 管理サービスの間のセキュリティで保護された (SSL) 接続をサポートするには、Web 管理サービスがインストールされている IIS サーバーを構成し、App-v 管理コンソールを構成する必要があります。

## このセクションの内容


<a href="" id="configuring-certificates-to-support-the-app-v-web-management-service"></a>[App-V Web Management Service をサポートするための証明書の構成](configuring-certificates-to-support-the-app-v-web-management-service.md)  
SSL ベースの接続をサポートする証明書を構成する方法について説明します。この情報は、App-v Web Management Service の通信をセキュリティで保護するために役立ちます。

<a href="" id="how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment"></a>[より安全な環境のために APP-V Management Console をインストールして構成する方法](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)  
セキュリティで保護された接続を使用して、App-v Web 管理サービスに接続するための手順について説明します。

 

 





