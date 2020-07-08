---
title: MBAM 2.0 機能の管理
description: MBAM 2.0 機能の管理
author: dansimp
ms.assetid: 065e0704-069e-4372-9b86-0b57dd7638dd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 35bb855e185ad8e3fa6880853938074cf6185a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823507"
---
# MBAM 2.0 機能の管理


必要な計画をすべて完了して、Microsoft BitLocker の管理と監視 (MBAM) を展開した後、このセクションの情報で、インストール後の日常的な Microsoft BitLocker の管理と監視の操作タスクについて説明します。

## MBAM 管理者の役割を管理する


すべてのサーバー機能について MBAM セットアップが完了したら、管理者はそのユーザーへのアクセス権を付与する必要があります。 ベストプラクティスとして、MBAM server 機能を管理または使用する管理者は Active Directory ドメインサービスのセキュリティグループに割り当てる必要があります。その場合は、これらのグループを適切な MBAM 管理ローカルグループに追加する必要があります。

[MBAM 管理者ロールを管理する方法](how-to-manage-mbam-administrator-roles-mbam-2.md)

## BitLocker 暗号化の除外を管理する


MBAM は、必要のない、またはドライブを暗号化する必要がある特定のユーザーに対して、暗号化の除外を与えることができます。 通常、コンピューターの除外は、開発やテストで使用されているコンピューター、または BitLocker をサポートしていない古いコンピューターなど、会社が暗号化する必要がないコンピューターを持っている場合に使用されます。 場合によっては、特定のコンピューターが暗号化されていないことが必要になる場合もあります。

[ユーザーの BitLocker 暗号化の除外を管理する方法](how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md)

## コントロールパネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する


MBAM は、[**システムとセキュリティ**] の下に表示される、[BitLocker 暗号化オプション] というカスタムコントロールパネルを提供します。 MBAM コントロールパネルを使用すると、暗号化された固定ドライブとリムーバブルドライブのロックを解除し、PIN またはパスワードを管理することもできます。

**注** このカスタマイズされたコントロールパネルは、既定の Windows BitLocker コントロールパネルに代わるものではありません。

 

[コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法](how-to-manage-mbam-client-bitlocker-encryption-options-by-using-the-control-panel-mbam-2.md)

## MBAM 機能の管理に関するその他のリソース


[MBAM 2.0 の操作](operations-for-mbam-20-mbam-2.md)

 

 





