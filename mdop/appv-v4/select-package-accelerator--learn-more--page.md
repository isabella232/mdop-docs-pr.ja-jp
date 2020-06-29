---
title: '[パッケージ アクセラレータの選択] ページ (詳細情報)'
description: '[パッケージ アクセラレータの選択] ページ (詳細情報)'
author: dansimp
ms.assetid: 2db51514-8695-4b5e-b3e5-1e96e3ee4cc7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d51df0f8eb16816bacf681b1acaf4c911ee9da55
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815597"
---
# [パッケージ アクセラレータの選択] ページ (詳細情報)


信頼できる発行元からのパッケージアクセラレータのみを実行します。 パッケージアクセラレータには、通常、デジタル署名が含まれています。 デジタル署名は、ソフトウェアの発行元を示すことができる電子セキュリティマークであり、変換が最初に署名された後でパッケージが改ざんされていないことを意味します。 発行元によってデジタル署名されている変換を使用し、発行元が証明機関で身元を確認した場合は、その発行元からの変換であり、改変されていないという確信があります。

Sequencer は、次のいずれかの条件が満たされた場合に通知します。

-   選択された変換は、デジタル署名されていません。

-   選択した変換は、証明機関によって身元を確認していない発行元によって署名されています。

-   選択した変換は、デジタル署名され、リリースされた後に変更されています。

パッケージアクセラレータを使用してこれらのメッセージのいずれかが表示されている場合は、パッケージアクセラレータの publisher の web サイトにアクセスして、デジタル署名された変換のバージョンを取得してください。

## 関連トピック


[Sequencer ウィザード - パッケージ アクセラレータ (AppV 4.6 SP1)](sequencer-wizard---package-accelerator--appv-46-sp1-.md)

 

 





