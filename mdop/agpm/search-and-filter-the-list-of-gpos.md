---
title: GPO の一覧を検索およびフィルター処理する
description: GPO の一覧を検索およびフィルター処理する
author: dansimp
ms.assetid: 1bc58a38-033c-4aed-9eb4-c239827f5501
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5646a51a37a4ca9195fb9ef858e8c5920ca7738a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820264"
---
# GPO の一覧を検索およびフィルター処理する


高度なグループポリシー管理 (AGPM) では、グループポリシーオブジェクト (Gpo) の一覧とその属性を検索して、表示された Gpo の一覧をフィルター処理することができます。 たとえば、特定の名前、状態、またはコメントを含む Gpo を検索することができます。 特定のグループポリシー管理者または特定の日付によって最後に変更された Gpo を検索することもできます。

## 複雑な検索を実行する


"Gpo の書式設定" 属性を使って複雑な検索を実行することができます。 *1: 検索文字列 1 GPO 属性 2: 検索文字列 2...すべての列の検索文字列*。 検索では、大文字と小文字は区別されません。

-   **GPO 属性:****コンピューターのバージョン**または**ユーザーのバージョン**以外の AGPM に含まれる gpo の一覧の列見出し。 Gpo 属性には、gpo 名、状態、GPO を最後に変更したユーザー、gpo が最近変更された日時、コメント、GPO の状態、GPO に適用された WMI フィルターが含まれます。

-   **検索文字列:** 指定した列で検索するテキスト。 文字列にスペースが含まれている場合は、文字列を引用符で囲む必要があります。

-   **すべての列の検索文字列:****コンピューターのバージョン**と**ユーザーのバージョン**以外の AGPM に含まれる gpo の一覧のすべての列で検索するテキスト。 複数の文字列をスペースで区切って含めることができます。 文字列にスペースが含まれている場合は、文字列を引用符で囲む必要があります。

各 GPO 属性と検索文字列の組み合わせと、各列の検索文字列は、論理 AND 演算を使って結合されます。 結果として、指定した各属性に指定した検索文字列が含まれ、すべての列の検索文字列が1つ以上の列に表示されるすべての Gpo の一覧が表示されます。 検索では、GPO 名またはユーザー名の一部を入力して、そのテキストが含まれているすべての Gpo の一覧をその名前に表示できるように、文字列の部分一致を返します。

次に、検索の例を示します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">検索結果の説明</th>
<th align="left">検索クエリ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>テキストの <strong> セキュリティ </strong> と <strong> 北アメリカの名前を含むすべての gpo </strong> 。</p></td>
<td align="left"><p><strong>名前: </strong><strong> セキュリティ </strong><strong> 名: </strong> &quot; <strong> 北アメリカ</strong>&quot;</p></td>
</tr>
<tr class="even">
<td align="left"><p>すべてのチェックアウトされた Gpo。</p></td>
<td align="left"><p><strong>状態: </strong> &quot; <strong> チェックアウト済み</strong>&quot;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>[管理者] という名前のユーザーによって最近変更されたすべて <strong> </strong> の gpo、および前月以内に変更された。</p></td>
<td align="left"><p><strong>変更者: </strong><strong> 管理者の </strong><strong> 変更日: </strong><strong> lastmonth</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Word <strong> ファイアウォール </strong> が最新のコメントに含まれていて、 <strong> </strong> どの列にも word のセキュリティが表示されるすべての gpo。</p></td>
<td align="left"><p><strong>コメント: </strong><strong> ファイアウォールの </strong><strong> セキュリティ</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p>すべての設定の状態が無効になっているすべての Gpo <strong> </strong> 。</p></td>
<td align="left"><p><strong>gpo の状態: </strong><strong> すべて</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Wmi フィルターという名前の WMI フィルターが適用されていて、 <strong> </strong> ユーザー構成設定の状態が [無効] になっているすべての gpo <strong> </strong> 。</p></td>
<td align="left"><p><strong>wmi フィルター: </strong> &quot; <strong> マイ wmi フィルター </strong> &quot; <strong> gpo の状態: </strong><strong> ユーザー</strong></p></td>
</tr>
</tbody>
</table>

 

## 日付の指定


Windows で検索するときに、特定の日付、特定の時刻、または一定期間内に変更された Gpo を検索することができます。 特定の日付または時刻を入力する場合は、[**日付の変更**] 列で使用されている形式を使用する必要があります。 次に、[**変更日 (Date** ) 列の検索の例を示します。

-   **日付の変更:****10/10/2009**

-   **日付の変更:****10/10/2009 9:00:00 AM**

-   **変更日:****今週**

[**日付の変更**] 列を検索するときに、大文字と小文字を区別しない次の特別な用語を使用できます。

-   **Today**

-   **昨日**

-   **今週**

-   **LastWeek**

-   **今月**

-   **最終月**

-   **TwoMonths**

-   **ThreeMonths**

-   **ThisYear**

-   **LastYear**

### その他の考慮事項

-   既定では、この手順を実行するには、レビュー担当者、編集者、承認者、AGPM 管理者 (フルコントロール) である必要があります。 具体的には、ドメインの**リストコンテンツ**のアクセス許可を持っている必要があります。

-   GPO 属性の詳細については、「 [[コンテンツ] タブの機能](contents-tab-features-agpm40.md)」を参照してください。

### その他の参照情報

-   [Advanced Group Policy Management 4.0](advanced-group-policy-management-40.md)

 

 





