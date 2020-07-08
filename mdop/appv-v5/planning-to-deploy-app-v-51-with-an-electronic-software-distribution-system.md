---
title: 電子ソフトウェア配布システムを使った App-V 5.1 の展開計画
description: 電子ソフトウェア配布システムを使った App-V 5.1 の展開計画
author: dansimp
ms.assetid: c26602c2-5e8d-44e6-90df-adacc593607e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fde3f0ea4f1dec72b97143b4b27dd0b32a503b15
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813402"
---
# 電子ソフトウェア配布システムを使った App-V 5.1 の展開計画


App-v パッケージを展開するために電子ソフトウェア配布システムを使用している場合は、次の計画の考慮事項を確認してください。 System Center Configuration Manager を使用した App-v の展開の詳細については、「[構成マネージャーでのアプリケーション管理の概要](https://go.microsoft.com/fwlink/?LinkId=281816)」を参照してください。

ESD を使って App-v パッケージを展開するときに適用される、次のコンポーネントとアーキテクチャの要件のオプションを確認します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">展開の要件またはオプション</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Management server、管理データベース、およびパブリッシングサーバーは必要ありません。</p></td>
<td align="left"><p>これらの関数は、実装された ESD ソリューションによって処理されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>アプリ V レポートサーバーとレポートデータベースを ESD と並行して展開することができます。</p></td>
<td align="left"><p>サイドバイサイド展開では、データを収集し、レポートを生成することができます。</p>
<p>レポート情報を送信するように App-v クライアントを有効にしていて、App-v レポートサーバーを使っていない場合、レポートデータは関連付けられた .xml ファイルに格納されます。</p></td>
</tr>
</tbody>
</table>

 






## 関連トピック


[App-V の展開計画](planning-to-deploy-app-v51.md)

 

 





