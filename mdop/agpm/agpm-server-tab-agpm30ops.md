---
title: '[AGPM サーバー] タブ'
description: '[AGPM サーバー] タブ'
author: dansimp
ms.assetid: fb3b0265-53ed-4bf6-88a4-c409f5f1bed4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 335cad07691f914884583636cef01be8dbaa0266
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819287"
---
# [AGPM サーバー] タブ


[**変更**] ウィンドウの [ **agpm サーバー** ] タブでは、完全修飾コンピューター名とポートを入力して agpm サーバーを選ぶことができます。また、agpm サーバー上のディスク領域を節約するために、古いバージョンのグループポリシーオブジェクト (gpo) をアーカイブから削除します。

## AGPM サーバーの指定


選択された AGPM サーバーによって、[**コンテンツ**] タブに表示されるアーカイブと、**ドメイン委任**設定が適用される場所が決まります。 高度なグループポリシー管理 (AGPM) の既定のポートは、ポート4600です。

AGPM サーバー接続が管理用テンプレート設定を使用して一元的に構成されている場合、接続を構成するためのこのタブのオプションは使用できません。 詳細については、「 [AGPM サーバー接続を構成する](configure-agpm-server-connections-agpm30ops.md)」を参照してください。

## 古い GPO のバージョンを削除する


既定では、すべての制御された GPO のすべてのバージョンがアーカイブに保持されます。 ただし、各 GPO に保持するバージョンの数を制限するように AGPM サービスを構成し、その制限を超えたときに最も古いバージョンを自動的に削除することができます。 [**履歴**] ウィンドウの [**一意のバージョン**] タブに表示される GPO バージョンのみが、制限をカウントします。

**注** 各 GPO に保存する一意のバージョンの最大数には、現在のバージョンが含まれていないため、0を入力すると現在のバージョンのみが保持されます。 制限は、999のバージョンよりも大きくする必要があります。

GPO のバージョンが削除されても、そのバージョンのレコードは GPO の履歴に残りますが、GPO のバージョン自体はアーカイブから削除されます。 削除されないように、GPO を履歴にマークすることで、その GPO のバージョンが削除されないようにすることができます。

 

### その他の参照情報

-   [ユーザー インターフェイス: 高度なグループ ポリシーの管理](user-interface-advanced-group-policy-management-agpm30ops.md)

-   [AGPM 管理者タスクの実行](performing-agpm-administrator-tasks-agpm30ops.md)

-   [レビュー担当者タスクの実行](performing-reviewer-tasks-agpm30ops.md)

 

 





