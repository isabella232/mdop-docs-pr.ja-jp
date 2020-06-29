---
title: MBAM 管理者ロールを管理する方法
description: MBAM 管理者ロールを管理する方法
author: dansimp
ms.assetid: 813ac0c4-3cf9-47af-b4cb-9395fd915e5c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 14e9128904b448b20e0596a2630627b7ca8e711d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825117"
---
# MBAM 管理者ロールを管理する方法


Microsoft BitLocker の管理と監視 (MBAM) のセットアップが完了したら、すべてのサーバー機能で、管理者ユーザーにアクセス権を付与する必要があります。 ベストプラクティスとして、Microsoft BitLocker 管理および監視サーバー機能を管理または使用する管理者は、ドメインサービスセキュリティグループに割り当てる必要があります。その場合は、これらのグループを適切な MBAM 管理ローカルグループに追加する必要があります。

**MBAM 管理者の役割のメンバーシップを管理するには**

1.  Active Directory ドメインサービスのセキュリティグループに管理ユーザーを割り当てます。

2.  使用している各機能に対して、ActiveDirectory セキュリティグループを MBAM サーバー上の MBAM 管理ローカルグループの役割に追加します。

    -   **Mbam システム管理者**は、Mbam 管理と監視 web サイトのすべての mbam 機能にアクセスできます。

    -   **Mbam ヘルプデスクユーザー**は、mbam 管理と監視の web サイトで TPM およびドライブの回復オプションにアクセスできますが、いずれかのオプションを使用する場合は、すべてのフィールドに入力する必要があります。

    -   **Mbam レポートユーザー**は、Mbam 管理と監視 web サイトのコンプライアンスおよび監査レポートにアクセスできます。

    -   **Mbam Advanced のヘルプデスクユーザー**は、mbam 管理と監視の web サイトで TPM およびドライブの回復オプションにアクセスできますが、どちらのオプションを使用する場合でも、すべてのフィールドに入力する必要はありません。

    Microsoft BitLocker の管理と監視の役割の詳細については、「 [MBAM 2.0 管理者ロールの計画](planning-for-mbam-20-administrator-roles-mbam-2.md)」を参照してください。

## 関連トピック


[MBAM 2.0 機能の管理](administering-mbam-20-features-mbam-2.md)

 

 





