---
title: MBAM 2.5 グループ ポリシー テンプレートのコピー
description: MBAM 2.5 グループ ポリシー テンプレートのコピー
author: dansimp
ms.assetid: e526ecec-07ff-435e-bc90-3084b617b84b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/28/2017
ms.openlocfilehash: a3436552256b1632a11037dc94751207cde89d5c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825224"
---
# MBAM 2.5 グループ ポリシー テンプレートのコピー


MBAM クライアントのインストールを展開する前に、「mbam の実装設定を定義する BitLocker ドライブ暗号化」のグループポリシー設定が含まれている MBAM グループポリシーテンプレートをダウンロードする必要があります。 テンプレートをダウンロードした後で、組織全体で実装するグループポリシー設定を設定します。

## MDOP グループポリシーテンプレートをダウンロードして展開する


MDOP グループポリシーテンプレートは、テクノロジとバージョンごとにグループ化された、自己解凍型の圧縮ファイルからダウンロードできます。

**MDOP グループポリシーテンプレートをダウンロードして展開する方法**

1. [Microsoft デスクトップ最適化パックのグループポリシー管理用テンプレート](https://www.microsoft.com/download/details.aspx?id=55531)から、MDOP グループポリシーテンプレートをダウンロードします。

2. ダウンロードしたファイルを実行して、テンプレートフォルダーを抽出します。

   **Warning**  
   テンプレートは、グループポリシー展開ディレクトリに直接抽出しないでください。 このファイルには、複数の技術とバージョンがバンドルされています。



3. 展開されたフォルダーで、テクノロジのバージョンの admx ファイルを見つけます。 一部の MDOP テクノロジには、複数のグループポリシーオブジェクト (Gpo) のセットがあります。 たとえば、MBAM には、MBAM 管理設定と MBAM ユーザー設定が含まれています。

4. 言語によって適切な adml ファイルを見つけます (*つまり、英語*(米国))。

5. Admx ファイルと adml ファイルをポリシー定義フォルダーにコピーします。 テンプレートの保存場所に応じて、ローカルデバイスまたはドメインの任意のコンピューターからグループポリシー設定を構成できます。

   **ローカルファイル。** ローカルデバイスからグループポリシー設定を構成するには、テンプレートファイルを次の場所にコピーします。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">ファイルの種類</th>
   <th align="left">ファイルの場所</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>グループポリシーテンプレート (admx)</p></td>
   <td align="left"><p><code>%systemroot%</code>&lt;強力な &gt; ポリシーの定義</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>グループポリシー言語ファイル (adml)</p></td>
   <td align="left"><p><code>%systemroot%</code>&lt;強力な &gt; ポリシーの定義</strong><code>[MUIculture]</code></p></td>
   </tr>
   </tbody>
   </table>



~~~
**Domain central store.** To enable Group Policy settings configuration by a Group Policy administrator from any computer on the domain, copy files to the following locations on the domain controller:

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">File type</th>
<th align="left">File location</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Group Policy template (.admx)</p></td>
<td align="left"><p><code>%systemroot%</code>\<strong>sysvol\domain\policies\PolicyDefinitions</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Group Policy language file (.adml)</p></td>
<td align="left"><p><code>%systemroot%</code>\<strong>sysvol\domain\policies\PolicyDefinitions\[MUIculture]</strong><code>\[MUIculture]</code></p>
<p>For example, the U.S. English ADML language-specific file will be stored in %systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us.</p></td>
</tr>
</tbody>
</table>
~~~



6. グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を使用してグループポリシー設定を編集し、MDOP テクノロジのグループポリシー設定を構成します。 詳細については[、「MBAM 2.5 グループポリシーの設定を編集](editing-the-mbam-25-group-policy-settings.md)する」を参照してください。

   グループポリシー設定の詳細については、「 [MBAM 2.5 グループポリシーの要件の計画](planning-for-mbam-25-group-policy-requirements.md)」を参照してください。


## 関連トピック


[MBAM 2.5 グループ ポリシー オブジェクトの展開](deploying-mbam-25-group-policy-objects.md)


## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。






