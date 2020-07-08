---
title: MBAM 2.5 グループ ポリシー オブジェクトの展開
description: MBAM 2.5 グループ ポリシー オブジェクトの展開
author: dansimp
ms.assetid: 4b835054-6846-463d-af58-8ac4639a1188
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9624b94e9d4808a35e1199290f4cd90a8122f767
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824387"
---
# MBAM 2.5 グループ ポリシー オブジェクトの展開


MBAM を展開するには、BitLocker ドライブ暗号化の MBAM 実装設定を定義するグループポリシー設定を設定する必要があります。 このタスクを完了するには、MBAM グループポリシーテンプレートを、グループポリシー管理コンソール (GPMC) または Advanced グループポリシー管理 (AGPM) を実行できるサーバーまたはワークステーションにコピーして、設定を編集する必要があります。

**重要** **BitLocker ドライブ暗号化**ノードのグループポリシー設定を変更しないようにします。または、mbam が正しく動作しません。 [ **MDOP mbam (BitLocker Management)** ] ノードでグループポリシー設定を構成すると、mbam が自動的に**bitlocker ドライブ暗号化**設定を構成します。

 

## MBAM 2.5 グループ ポリシー テンプレートのコピー


MBAM クライアントをインストールする前に、MBAM 固有のグループポリシーオブジェクト (Gpo) を管理ワークステーションにコピーする必要があります。 これらの Gpo は、BitLocker ドライブ暗号化用の MBAM 実装設定を定義します。 グループポリシーテンプレートは、サポートされている Windows サーバーまたはクライアントコンピューターであり、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を実行できる任意のサーバーまたはワークステーションにコピーできます。

[MBAM 2.5 グループ ポリシー テンプレートのコピー](copying-the-mbam-25-group-policy-templates.md)

## MBAM 2.0 GPO 設定の編集


必要な Gpo を作成したら、MBAM グループポリシー設定を組織のクライアントコンピューターに展開する必要があります。 Gpo を表示および作成するには、グループポリシー管理コンソール (GPMC) または Advanced グループポリシー管理 (AGPM) がインストールされている必要があります。

[MBAM 2.5 グループ ポリシー設定の編集](editing-the-mbam-25-group-policy-settings.md)

## Windows のコントロールパネルで MBAM コントロールパネルを表示または非表示にする


MBAM はカスタマイズされた MBAM コントロールパネルを提供して、既定の Windows BitLocker コントロールパネルを置き換えることができるため、グループポリシー設定を使用して、エンドユーザーに対して既定の BitLocker コントロールパネルの表示と非表示を切り替えることができます。

[コントロール パネルの既定の BitLocker ドライブ暗号化項目を非表示にする](hiding-the-default-bitlocker-drive-encryption-item-in-control-panel-mbam-25.md)

## MBAM 2.0 グループポリシーオブジェクトの展開に関するその他のリソース


[MBAM 2.5 の展開](deploying-mbam-25.md)

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。

 

 





