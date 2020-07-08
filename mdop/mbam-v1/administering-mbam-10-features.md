---
title: MBAM 1.0 機能の管理
description: MBAM 1.0 機能の管理
author: dansimp
ms.assetid: dd9a9eff-f1ad-4af3-85d9-c19131a4ad22
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a99ac556227c0f113fb20f3aca32d21c204877b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821224"
---
# MBAM 1.0 機能の管理


必要な Microsoft BitLocker 管理と監視 (MBAM) の計画と展開が完了したら、MBAM を構成して使用して、エンタープライズの BitLocker 暗号化を管理することができます。 このセクションの情報は、インストール後の日常的な MBAM 機能の操作タスクについて説明します。

## MBAM 管理者の役割を管理する


すべてのサーバー機能について MBAM セットアップが完了したら、管理ユーザーにこれらのサーバー機能へのアクセス権を付与する必要があります。 ベストプラクティスとして、MBAM server 機能を管理または使用する管理者は Active Directory のセキュリティグループに割り当てる必要があります。その後、それらのグループを適切な MBAM 管理ローカルグループに追加する必要があります。

[MBAM 管理者ロールを管理する方法](how-to-manage-mbam-administrator-roles-mbam-1.md)

## ハードウェアの互換性を管理する


MBAM Hardware Compatibility 機能は、サポートする BitLocker として指定したコンピューターハードウェアだけが暗号化されるようにするために役立ちます。 この機能が有効になっている場合、ビット \ _admmontla は互換性があるとマークされているコンピューターのみを暗号化します。

**重要** この機能を無効にすると、MBAM ポリシーが展開されているすべてのコンピューターが暗号化されます。

 

MBAM は、"ハードウェア互換性チェックの許可" グループポリシーを展開すると、クライアントコンピューターのメーカーとモデルの両方に関する情報を収集できます。 このポリシーを構成した場合、mbam クライアントがクライアントコンピューターに展開されると、mbam エージェントによって、コンピューターの製造元とモデル情報が MBAM サーバーに報告されます。

[ハードウェアの互換性を管理する方法](how-to-manage-hardware-compatibility-mbam-1.md)

[ユーザーの BitLocker 暗号化の除外を管理する方法](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)

## BitLocker 暗号化の除外を管理する


MBAM は、BitLocker 暗号化から、コンピューターの除外とユーザーの除外という2つの形式の除外を付与できます。 通常、コンピューターの除外は、開発やテストで使用されているコンピューター、または BitLocker をサポートしていない古いコンピューターなど、会社が暗号化する必要がないコンピューターを持っている場合に使用されます。 場合によっては、特定のコンピューターが暗号化されていないことが必要になる場合もあります。 不要なユーザーを除外したり、ドライブを暗号化したりすることもできます。

[コンピューターの BitLocker 暗号化の除外を管理する方法](how-to-manage-computer-bitlocker-encryption-exemptions.md)

## コントロールパネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する


グループポリシーオブジェクト (GPO) を使って有効にした場合、[BitLocker 暗号化オプション] という名前のカスタム MBAM コントロールパネルは、[**システムとセキュリティ**] の下に表示されます。 このカスタマイズされたコントロールパネルは、既定の Windows BitLocker コントロールパネルに置き換わるものです。 MBAM コントロールパネルでは、暗号化されたドライブ (固定およびリムーバブル) のロックを解除することができます。また、PIN やパスワードの管理にも役立ちます。

[コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法](how-to-manage-mbam-client-bitlocker-encryption-options-by-using-the-control-panel-mbam-1.md)

## MBAM 機能の管理に関するその他のリソース


[MBAM 1.0 の操作](operations-for-mbam-10.md)

 

 





