---
title: AGPM 4.0 の新機能
description: AGPM 4.0 の新機能
author: dansimp
ms.assetid: 31775f7f-a59c-4e64-a875-0adc9f5bc835
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 82b4445a7d22fb7c1ef4f42d896f11908a22f2f5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820104"
---
# AGPM 4.0 の新機能


Microsoft Advanced グループポリシー管理 (AGPM) 4.0 には、グループポリシーオブジェクト (Gpo) の検索、表示された Gpo の一覧のフィルター処理、別のフォレストへの GPO のエクスポートとインポート、Windows7 と Windows Server2008R2 を実行しているコンピューターへの AGPM のインストールを実行できる新しい機能が含まれています。

## Gpo を検索してフィルター処理する


AGPM 4.0 では、特定の属性について Gpo の一覧を検索して、表示された Gpo の一覧をフィルター処理することができます。 たとえば、特定の名前、状態、またはコメントを含む Gpo を検索することができます。 特定のグループポリシー管理者または特定の日付によって最後に変更された Gpo を検索することもできます。

"Gpo の書式設定" 属性を使用して複雑な検索文字列を作成することができます。 *1: 検索テキスト 1 GPO 属性 2: 検索テキスト 2...* gpo 属性は、AGPM 内の gpo の一覧の列見出しになります。 たとえば、チェックインされている、ユーザー Editor03 によって最後に変更された、"MyGPO" というテキストを含むすべての Gpo を検索するには、次のように入力します。「 **name: MyGPO の状態:****チェックイン済み****: Editor03**」と入力します。 検索では部分一致が返されるため、GPO 名またはユーザー名の一部を入力し、そのテキストを含むすべての Gpo の一覧をその名前に表示することができます。

さらに、特定の日付または日付の範囲で変更された Gpo を検索するときに、Windows で検索するときに使用できる特殊な用語を使用できます。 たとえば、 **date:****lastmonth**または**date:****今週**の日付を変更します。

## Gpo を別のフォレストにエクスポートしてインポートする


AGPM 4.0 を使用すると、1つのフォレストのドメインから2つ目のフォレストのドメインに制御された GPO をコピーできます。 たとえば、AGPM を使用して1つのフォレストのドメインから CAB ファイルに GPO をエクスポートし、その CAB ファイルを USB ドライブにコピーし、USB ドライブを2番目のフォレストのドメイン内のコンピューターに接続して、2番目のフォレストのドメインの AGPM に GPO をインポートすることができます。 GPO を新しい制御された GPO としてインポートするか、またはその gpo をインポートして、チェックアウトされている既存の GPO の設定と置き換えることができます。

## Windows Server 2008 R2 と Windows 7 のサポート


AGPM 4.0 は、Windows Server2008R2 と Windows7 をサポートしていますが、Windows Server2008 および WindowsVista® Service Pack1 (SP1) でサポートされています。 ただし、次の表に示すように、新しいオペレーティングシステムと古いオペレーティングシステムの両方が含まれている混在環境には制限があります。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">AGPM サーバー4.0 が実行されているオペレーティングシステム</th>
<th align="left">AGPM クライアント4.0 が実行されるオペレーティングシステム</th>
<th align="left">AGPM 4.0 サポートの状態</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>サポートされています</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>サポートされていますが、Windows Server2008R2 または Windows7 にのみ存在するポリシー設定や設定項目は編集できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008R2 または Windows7</p></td>
<td align="left"><p>サポートされていません</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>Windows Server2008 または Windows Vista SP1</p></td>
<td align="left"><p>サポートされますが、Windows Server2008R2 または Windows7 にのみ存在するポリシー設定や基本設定項目は報告または編集できません。</p></td>
</tr>
</tbody>
</table>

 

 

 





