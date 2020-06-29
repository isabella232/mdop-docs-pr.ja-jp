---
title: MDOP グループ ポリシー (.admx) テンプレートをダウンロードして展開する方法
description: MDOP グループ ポリシー (.admx) テンプレートをダウンロードして展開する方法
author: dansimp
ms.assetid: fdb64505-6c66-4fdf-ad74-a6a161191e3f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: 5bc5f8d536c113ccbc0a1931e6c7e4ed3c7a9a37
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826917"
---
# MDOP グループ ポリシー (.admx) テンプレートをダウンロードして展開する方法


グループポリシーテンプレート、admx、adml ファイルを使用して、特定の Microsoft デスクトップ最適化パック (MDOP) テクノロジ (たとえば、アプリ-V、UE-V、または MBAM など) の機能設定を管理できます。 MDOP グループポリシーテンプレートは、テクノロジとバージョンごとにグループ化された、自己解凍型の圧縮ファイルからダウンロードできます。

## MDOP グループポリシーテンプレート

**MDOP グループポリシーテンプレートをダウンロードして展開する方法**

1. 最新の[MDOP グループポリシーテンプレート](https://www.microsoft.com/download/details.aspx?id=55531)をダウンロードする 

2. 実行して、ダウンロードした .cab ファイルを展開します。 `expand <download_folder>\MDOP_ADMX_Templates.cab -F:* <destination_folder>`

   **Warning**  
   テンプレートは、グループポリシー展開ディレクトリに直接抽出しないでください。 このファイルには、複数の技術とバージョンがバンドルされています。

3. 展開されたフォルダーで、テクノロジのバージョンの admx ファイルを見つけます。 一部の MDOP テクノロジには、複数のグループポリシーオブジェクト (Gpo) のセットがあります。 たとえば、MBAM には、MBAM 管理設定と MBAM ユーザー設定が含まれています。

4. 言語によって適切な adml ファイルを見つけます (つまり、英語 (米国) の場合は*en-us* )。

5. Admx ファイルと adml ファイルをポリシー定義フォルダーにコピーします。 テンプレートの保存場所に応じて、ローカルデバイスまたはドメインの任意のコンピューターからグループポリシー設定を構成できます。

   - **ローカルファイル:** ローカルデバイスからグループポリシー設定を構成するには、テンプレートファイルを次の場所にコピーします。

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

   - **Domain central store:** グループポリシーの設定をグループポリシーの管理者がドメインの任意のコンピューターから有効にするには、ドメインコントローラーの次の場所にファイルをコピーします。

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
   <td align="left"><p><code>%systemroot%</code>&lt;強力な &gt; sysvol\domain\policies\PolicyDefinitions</strong></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>グループポリシー言語ファイル (adml)</p></td>
   <td align="left"><p><code>%systemroot%</code>&lt;強力な &gt; sysvol\domain\policies\PolicyDefinitions [MUIculture]</strong><code>[MUIculture]</code></p>
   <p>たとえば、米国英語 ADML の言語固有のファイルは、%systemroot%\sysvol\domain\policies\PolicyDefinitions\en-us. に保存されます。</p></td>
   </tr>
   </tbody>
   </table>

6. グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を使用してグループポリシー設定を編集し、MDOP テクノロジのグループポリシー設定を構成します。

### 技術別の MDOP グループポリシー

サポートされている MDOP グループポリシーの詳細については、技術に関する具体的なドキュメントを参照してください。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">MDOP 技術</th>
<th align="left">バージョンバンドル</th>
<th align="left">備考</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Application Virtualization (APP-V)</strong></p></td>
<td align="left"><p>App-v 5.0 および App-v 5.0 Service Pack</p></td>
<td align="left"><p><a href="../appv-v5/how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md" data-raw-source="[How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy](../appv-v5/how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)">ADMX テンプレートとグループ ポリシーを使用して App-V 5.0 Client 構成を変更する方法</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>User Experience Virtualization (UE-V)</strong></p></td>
<td align="left"><p>UE-V 2.0 および UE-V 2.1</p></td>
<td align="left"><p><a href="../uev-v2/configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md" data-raw-source="[Configuring UE-V 2.x with Group Policy Objects](../uev-v2/configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md)">グループポリシーオブジェクトを使用して UE-V 2. x を構成する</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>UE-V 1.0 (1.0 SP1 を含む)</p></td>
<td align="left"><p><a href="../uev-v1/configuring-ue-v-with-group-policy-objects.md" data-raw-source="[Configuring UE-V with Group Policy Objects](../uev-v1/configuring-ue-v-with-group-policy-objects.md)">グループ ポリシー オブジェクトを使用した UE-V の構成</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Microsoft BitLocker Administration and Monitoring (MBAM)</strong></p></td>
<td align="left"><p>MBAM 2.5</p></td>
<td align="left"><p><a href="../mbam-v25/planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](../mbam-v25/planning-for-mbam-25-group-policy-requirements.md)">MBAM 2.5 グループ ポリシー要件の計画</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>MBAM 2.0 (2.0 SP1 を含む)</p></td>
<td align="left"><p><a href="../mbam-v2/planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](../mbam-v2/planning-for-mbam-20-group-policy-requirements-mbam-2.md)">MBAM 2.0 グループ ポリシー要件の計画</a></p>
<p><a href="../mbam-v2/deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](../mbam-v2/deploying-mbam-20-group-policy-objects-mbam-2.md)">MBAM 2.0 グループ ポリシー オブジェクトの展開</a></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>MBAM 1.0</p></td>
<td align="left"><p><a href="../mbam-v1/how-to-edit-mbam-10-gpo-settings.md" data-raw-source="[How to Edit MBAM 1.0 GPO Settings](../mbam-v1/how-to-edit-mbam-10-gpo-settings.md)">MBAM 1.0 GPO 設定を編集する方法</a></p></td>
</tr>
</tbody>
</table>

 

 

 





