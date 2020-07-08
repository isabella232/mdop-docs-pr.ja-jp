---
title: MBAM 1.0 グループ ポリシー オブジェクトの展開
description: MBAM 1.0 グループ ポリシー オブジェクトの展開
author: dansimp
ms.assetid: 2129291e-d2b2-41ed-b643-1e311c49fee7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8d14123f1d5b197146e425cba063e8ce4c180641
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821217"
---
# MBAM 1.0 グループ ポリシー オブジェクトの展開


Microsoft BitLocker の管理と監視 (MBAM) を正常に展開するには、MBAM の実装で使用するグループポリシーを最初に確認する必要があります。 利用可能なさまざまなポリシーの詳細については、「 [MBAM 1.0 グループポリシーの要件の計画](planning-for-mbam-10-group-policy-requirements.md)」を参照してください。 使用するポリシーを決定したら、MBAM 1.0 グループポリシーテンプレートを使用して、MBAM ポリシー設定を含む1つ以上のグループポリシーオブジェクト (GPO) を作成して展開する必要があります。

## MBAM 1.0 グループポリシーテンプレートをインストールする


MBAM のサーバー関連機能を提供するだけでなく、server setup アプリケーションには MBAM グループポリシーテンプレートが含まれています。 このテンプレートは、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を実行できる任意のコンピューターにインストールできます。

[MBAM 1.0 グループ ポリシー テンプレートをインストールする方法](how-to-install-the-mbam-10-group-policy-template.md)

## MBAM 1.0 グループポリシー設定の展開


必要な Gpo を作成したら、MBAM グループポリシー設定を組織のクライアントコンピューターに展開する必要があります。

[MBAM 1.0 GPO 設定を編集する方法](how-to-edit-mbam-10-gpo-settings.md)

## Windows で MBAM コントロールパネルを表示する


MBAM はカスタマイズされた MBAM コントロールパネルを提供して、既定の Windows BitLocker コントロールパネルを置き換えることができるため、グループポリシーを使用して、既定の BitLocker コントロールパネルをエンドユーザーに表示しないようにすることもできます。

[Windows コントロール パネルで既定の BitLocker 暗号化を非表示にする方法](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md)

## MBAM 1.0 グループポリシーオブジェクトの展開に関するその他のリソース


[MBAM 1.0 の展開](deploying-mbam-10.md)

 

 





