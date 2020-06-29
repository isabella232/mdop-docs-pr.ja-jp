---
title: MBAM 2.0 グループ ポリシー オブジェクトの展開
description: MBAM 2.0 グループ ポリシー オブジェクトの展開
author: dansimp
ms.assetid: f17f3897-73ab-431b-a6ec-5a6cff9f279a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1ce2c2a37631d9d678d6de7c1d66b7fdafb2ade9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823494"
---
# MBAM 2.0 グループ ポリシー オブジェクトの展開


Microsoft BitLocker の管理と監視 (MBAM) を正常に展開するには、まず Microsoft BitLocker の管理と監視の実装で使用するグループポリシーを決定する必要があります。 使用可能なさまざまなポリシーの詳細については、「 [MBAM 2.0 グループポリシーの要件](planning-for-mbam-20-group-policy-requirements-mbam-2.md)」を参照してください。 使用するポリシーを決定したら、MBAM 2.0 グループポリシーテンプレートを使用して、MBAM のポリシー設定を含む1つ以上のグループポリシーオブジェクト (GPO) を作成して展開する必要があります。

## MBAM 2.0 グループポリシーテンプレートをインストールする


サーバーに関連する Microsoft BitLocker の管理機能と監視機能に加えて、server setup アプリケーションには MBAM グループポリシーテンプレートが含まれています。 このテンプレートは、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を実行できる任意のコンピューターにインストールできます。

[MBAM 2.0 グループ ポリシー テンプレートをインストールする方法](how-to-install-the-mbam-20-group-policy-template-mbam-2.md)

## MBAM 2.0 グループポリシー設定の展開


必要な Gpo を作成したら、MBAM グループポリシー設定を組織のクライアントコンピューターに展開する必要があります。

[MBAM 2.0 GPO 設定を編集する方法](how-to-edit-mbam-20-gpo-settings-mbam-2.md)

## Windows で MBAM コントロールパネルを表示する


MBAM はカスタマイズされた MBAM コントロールパネルを提供して、既定の Windows BitLocker コントロールパネルを置き換えることができるため、グループポリシーを使用して、既定の BitLocker コントロールパネルをエンドユーザーに表示しないようにすることもできます。

[Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel-mbam-2.md)

## MBAM 2.0 グループポリシーオブジェクトの展開に関するその他のリソース


[MBAM 2.0 の展開](deploying-mbam-20-mbam-2.md)

 

 





