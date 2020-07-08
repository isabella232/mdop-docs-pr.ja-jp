---
title: コンピューターの BitLocker 暗号化の除外を管理する方法
description: コンピューターの BitLocker 暗号化の除外を管理する方法
author: dansimp
ms.assetid: d4400a0d-b36b-4cf5-a294-1f53ec47f9ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51b93061468508900eaee7fce8a7827e2db61d19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825677"
---
# コンピューターの BitLocker 暗号化の除外を管理する方法


Microsoft BitLocker の管理と監視 (MBAM) を使用して、BitLocker 保護から特定のコンピューターを除外することができます。 たとえば、組織では、コンピューターごとに BitLocker の除外を制御することができます。

コンピューターを BitLocker 暗号化から除外するには、コンピューターベースの BitLocker 保護規則を回避するために、ActiveDirectoryDomainServices のセキュリティグループにコンピューターを追加する必要があります。

**注** コンピューターが既に BitLocker で保護されている場合は、コンピューターの除外ポリシーには影響ありません。

 

**BitLocker 暗号化からコンピューターを除外するには**

1.  ActiveDirectoryDomainServices のセキュリティグループに適用除外するコンピューターアカウントを追加します。 これにより、コンピューターベースの BitLocker 保護規則をすべてバイパスすることができます。

2.  MBAM グループポリシーテンプレートを使用してグループポリシーオブジェクトを作成し、前の手順で作成した Active Directory グループにグループポリシーオブジェクトを関連付けます。 必要なグループポリシーオブジェクトの作成について詳しくは、「 [MBAM 1.0 グループポリシーオブジェクトの展開](deploying-mbam-10-group-policy-objects.md)」をご覧ください。

3.  除外されたコンピューターが起動すると、MBAM クライアントはコンピューターの適用除外ポリシー設定を確認し、コンピューターが BitLocker の除外セキュリティグループの一部であるかどうかに基づいて保護を中断します。

## 関連トピック


[MBAM 1.0 機能の管理](administering-mbam-10-features.md)

 

 





