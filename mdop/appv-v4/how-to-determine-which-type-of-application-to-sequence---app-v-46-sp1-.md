---
title: 順序を指定するアプリケーションの種類を決定する方法 (App-v 4.6 SP1)
description: 順序を指定するアプリケーションの種類を決定する方法 (App-v 4.6 SP1)
author: dansimp
ms.assetid: 936abee2-98f1-45fb-9f0d-786e1d7464b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 001f6afa36ca28eb1b8e0cc2ccc161cef4194d24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817487"
---
# 順序を指定するアプリケーションの種類を決定する方法 (App-v 4.6 SP1)


Microsoft Application Virtualization (App-v) Sequencer を使用して、3種類の基本的なアプリケーションをシーケンスできます。

## 順序を指定するアプリケーションの種類を決定するには


次の表を使用して、どの種類のアプリケーションを順序指定するかを決定し、アプリケーションの順序を指定する方法についての詳細を確認します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アプリケーションの種類</th>
<th align="left">説明</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>標準</p></td>
<td align="left"><p>アプリケーションまたはアプリケーションスイートを含むパッケージを作成するには、このオプションを選択します。 順序を設定するほとんどのアプリケーションには、このオプションを選択する必要があります。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-standard-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Standard Application (App-V 4.6 SP1)](how-to-sequence-a-new-standard-application--app-v-46-sp1-.md)">新しい標準アプリケーションをシーケンス処理する方法 (App-V 4.6 SP1)</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>アドオンまたはプラグイン</p></td>
<td align="left"><p>このオプションは、Microsoft Excel のプラグインなど、標準アプリケーションの機能を拡張するパッケージを作成する場合に選択します。 さらに、ネイティブにインストールされているアプリケーション、または動的なスイートコンポジションを使ってリンクされている別のパッケージのプラグインを使うことができます。 動的なスイートコンポジションの詳細については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)"> 動的なスイートコンポジション </a> () の使い方」を参照してください <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804"> https://go.microsoft.com/fwlink/?LinkId=203804 </a> 。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-add-on-or-plug-in-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Add-on or Plug-in Application (App-V 4.6 SP1)](how-to-sequence-a-new-add-on-or-plug-in-application--app-v-46-sp1-.md)">新しいアドオンまたはプラグイン アプリケーションをシーケンス処理する方法 (App-V 4.6 SP1)</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>ミドルウェア</p></td>
<td align="left"><p>標準アプリケーション (Microsoft .NET Framework など) で必要なパッケージを作成するには、このオプションを選択します。 ミドルウェアパッケージは、動的スイートコンポジションを使用して他のパッケージにリンクするために使用されます。 動的なスイートコンポジションの詳細については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)"> 動的なスイートコンポジション </a> () の使い方」を参照してください <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804"> https://go.microsoft.com/fwlink/?LinkId=203804 </a> 。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-middleware-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Middleware Application (App-V 4.6 SP1)](how-to-sequence-a-new-middleware-application--app-v-46-sp1-.md)">新しいミドルウェア アプリケーションをシーケンス処理する方法 (App-V 4.6 SP1)</a></p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[Application Virtualization Sequencer のタスク (APP-V 4.6 SP1)](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

 

 





