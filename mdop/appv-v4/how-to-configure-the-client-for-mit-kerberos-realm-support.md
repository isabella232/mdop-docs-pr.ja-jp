---
title: MIT Kerberos 認証用のレルムをサポートするようにクライアントを構成する方法
description: MIT Kerberos 認証用のレルムをサポートするようにクライアントを構成する方法
author: dansimp
ms.assetid: 46102f4c-270c-4115-8eb4-7ff5ae3be32d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ae5cd73d00f340bc50070fdd0a5fd3e038cc3789
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817814"
---
# MIT Kerberos 認証用のレルムをサポートするようにクライアントを構成する方法


Application Virtualization (App-v) 4.5 SP1 では、MIT Kerberos 領域のサポートが追加されました。 このトピックでは、そのサポートを有効にする方法について詳しく説明します。

**MIT Kerberos 領域のサポートを有効にするには**

-   次のように、DWORD の**UseMitKerberos**という名前の新しいレジストリキーを作成して、値1に設定します。

    HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\Client\\Network\\UseMitKerberos

 

 





