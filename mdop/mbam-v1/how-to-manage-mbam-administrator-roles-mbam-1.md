---
title: MBAM 管理者ロールを管理する方法
description: MBAM 管理者ロールを管理する方法
author: dansimp
ms.assetid: c0f25a42-dbff-418d-a776-4fe23ee07d16
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9d00b8ebf66d2b066afae33e67298691285ce9fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812970"
---
# MBAM 管理者ロールを管理する方法


Microsoft BitLocker の管理と監視 (MBAM) のセットアップが完了したら、すべてのサーバー機能で、これらのサーバー機能へのアクセス権を管理ユーザーに付与する必要があります。 ベストプラクティスとして、MBAM server 機能を管理または使用する管理者は Active Directory のセキュリティグループに割り当てる必要があります。その後、それらのグループを適切な MBAM 管理ローカルグループに追加する必要があります。

**MBAM 管理者の役割のメンバーシップを管理するには**

1.  ActiveDirectoryDomain Services のセキュリティグループに管理ユーザーを割り当てます。

2.  ActiveDirectoryDomain サービスセキュリティグループを、Microsoft BitLocker 管理サーバーおよび監視サーバー上の MBAM 管理ローカルグループの役割に、それぞれの機能について追加します。 ユーザーの役割は次のとおりです。

    -   **Mbam システム管理者**は、mbam 管理 web サイトの Microsoft BitLocker 管理および監視機能のすべてにアクセスできます。

    -   **Mbam ハードウェアユーザー**は、mbam 管理 web サイトのハードウェア互換性機能にアクセスできます。

    -   **Mbam ヘルプデスクユーザー**は、mbam 管理 web サイトの [TPM およびドライブの回復] オプションにアクセスできますが、いずれかのオプションを使用する場合は、すべてのフィールドに入力する必要があります。

    -   **Mbam レポートユーザー**は、mbam 管理 web サイトのコンプライアンスおよび監査レポートにアクセスできます。

    -   **Mbam Advanced ヘルプデスクでは**、mbam 管理 web サイトの TPM およびドライブの回復オプションの管理にアクセスできます。 これらのユーザーは、いずれかのオプションを使用する場合、すべてのフィールドに入力する必要はありません。

    Microsoft BitLocker の管理と監視の役割の詳細については、「 [MBAM 1.0 管理者ロールの計画](planning-for-mbam-10-administrator-roles.md)」を参照してください。

## 関連トピック


[MBAM 1.0 機能の管理](administering-mbam-10-features.md)

 

 





