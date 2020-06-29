---
title: '[パッケージ アクセラレータの選択] ページ'
description: '[パッケージ アクセラレータの選択] ページ'
author: dansimp
ms.assetid: 865c2702-4dfd-41ae-8cfc-3514d5f41f76
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a5723f8244563539c27a3fa915c1a680905e61e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815594"
---
# [パッケージ アクセラレータの選択] ページ


**[パッケージアクセラレータの選択**] ページを使用して、新しい仮想アプリケーションパッケージの作成に使用するパッケージアクセラレータを選択します。 パッケージアクセラレータは、App-v Sequencer を実行しているコンピューター上のフォルダーにコピーする必要があります。 詳細については、「app-v[パッケージアクセラレータについて (app-v 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md)」を参照してください。

信頼できる発行元からのパッケージアクセラレータのみを実行します。 パッケージアクセラレータには、通常、デジタル署名が含まれています。 デジタル署名は、ソフトウェアの発行元を示すことができる電子セキュリティマークであり、変換が最初に署名された後でパッケージが改ざんされたかどうかを示します。 発行元によってデジタル署名されている変換を使用し、発行元が証明機関で身元を確認した場合は、その発行元からの変換であり、改変されていないという確信があります。

次の条件のいずれかに該当する場合は、App-v によって通知されます。

-   選択された変換は、デジタル署名されていません。

-   選択した変換は、証明機関によって身元を確認していない発行元によって署名されています。

-   選択した変換は、デジタル署名され、リリースされた後に変更されています。

パッケージアクセラレータを使用してこれらのメッセージが表示された場合は、パッケージアクセラレータの publisher の web サイトにアクセスして、デジタル署名された変換のバージョンを取得してください。

このページには、次の要素が含まれています。

<a href="" id="browse"></a>**閲覧**  
[**参照**] をクリックして、仮想アプリケーションパッケージの作成に使うパッケージアクセラレータを指定します。 Sequencer を実行しているコンピューター上で、ローカルで指定したパッケージアクセラレータを保存します。

## 関連トピック


[Sequencer ウィザード - パッケージ アクセラレータ (AppV 4.6 SP1)](sequencer-wizard---package-accelerator--appv-46-sp1-.md)

 

 





