---
title: インストール後の安全な通信のための Management Server または Streaming Server の構成
description: インストール後の安全な通信のための Management Server または Streaming Server の構成
author: dansimp
ms.assetid: 1062a213-470b-4ae2-b12f-b3e28a6ab745
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2a2713f130809c431b7444f3e928a523838597a6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821877"
---
# インストール後の安全な通信のための Management Server または Streaming Server の構成


適切な証明書が、app-v 管理サーバーまたは App-v Streaming Server のインストール前にプロビジョニングされなかった場合は、最初のインストール後にセキュリティを強化するように App-v を構成できます。 App-v Management Server は、App-v 管理コンソールを使って構成できます。 ただし、App-v ストリーミングサーバーはレジストリによって管理されます。 どちらの場合も、証明書にサーバー認証用の適切な*拡張キー使用法*(EKU) を含める必要があり、ネットワークサービスは秘密キーに対する読み取りアクセス権を持っている必要があります。

## このセクションの内容


<a href="" id="how-to-configure-management-server-security-post-installation"></a>[Management Server のインストール後のセキュリティを構成する方法](how-to-configure-management-server-security-post-installation.md)  
アプリ-V 管理コンソールを使用して、証明書を追加し、セキュリティを強化するために App-v Management Server を構成するために、インストール後に実行できる手順について説明します。

<a href="" id="how-to-configure-streaming-server-security-post-installation"></a>[Streaming Server のインストール後のセキュリティを構成する方法](how-to-configure-streaming-server-security-post-installation.md)  
インストール後に実行できる手順と、証明書を追加して、セキュリティ強化のために App-v ストリーミングサーバーを構成する手順について説明します。

<a href="" id="troubleshooting-certificate-permission-issues"></a>[証明書のアクセス許可の問題のトラブルシューティング](troubleshooting-certificate-permission-issues.md)  
秘密キーがネットワークサービス用の適切な ACL で構成されていない場合のトラブルシューティングのガイダンスを提供します。

 

 





