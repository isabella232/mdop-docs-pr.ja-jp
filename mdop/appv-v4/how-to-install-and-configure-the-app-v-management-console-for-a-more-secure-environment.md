---
title: より安全な環境のために APP-V Management Console をインストールして構成する方法
description: より安全な環境のために APP-V Management Console をインストールして構成する方法
author: dansimp
ms.assetid: 9d89ef09-cdbf-48fc-99da-b24fc987ef8f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9887787d1e203410b5517439d897260305d7526e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817374"
---
# より安全な環境のために APP-V Management Console をインストールして構成する方法


App-v 管理コンソールの既定のインストールには、セキュリティで保護された通信のサポートが含まれています。 各管理コンソールは、コンソールが初めて起動されたとき、または追加の App-v Web 管理サービスに接続したときに、接続ごとに構成されます。 既定の構成では、TCP ポート443で SSL を使用しています。 サーバーでポート番号が変更された場合は、ポート番号を変更できます。 セキュリティで保護された接続を使用して、次の手順に従って App-v Web 管理サービスに接続することができます。

**SSL 接続を使用して App-v 管理サービスに接続する方法**

1.  Application Virtualization 管理コンソールを起動します。

2.  コンソールの操作ウィンドウで [**接続の構成**] をクリックします。

3.  **Web サービスのホスト名**を入力し、[**セキュリティで保護**された接続の使用] が選択されていることを確認します。

    **重要** Web サービスのホスト名で指定された名前は、証明書の一般的な名前と一致する必要があります。接続は失敗します。

     

4.  適切なログイン資格情報を選択して、[ **OK]** をクリックします。

## 関連トピック


[App-V Web Management Service をサポートするための証明書の構成](configuring-certificates-to-support-the-app-v-web-management-service.md)

 

 





