---
title: DaRT 10 の回復イメージの作成計画
description: DaRT 10 の回復イメージの作成計画
author: dansimp
ms.assetid: a0087d93-b88f-454b-81b2-3c7ce3718023
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 44cf052eaffd19645885618da9104e5b0a50cfd5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822977"
---
# DaRT 10 の回復イメージの作成計画


Microsoft 診断/回復ツールセット (DaRT) 10 復元イメージの作成を計画している場合は、このセクションの情報を使用します。

## DaRT 10 の回復イメージの作成を計画する


DaRT リカバリ画像を作成する場合は、イメージに含めるツールを決定する必要があります。 決定を行うには、エンドユーザーがこれらのツールにアクセスできる可能性があることを考慮してください。 サポートエンジニアが回復イメージメディアを使用して、問題を診断している場合は、回復イメージにすべてのツールをインストールすることができます。 エンドユーザーのコンピューターをリモートで診断することを計画している場合は、ディスクワイプやレジストリエディターなどのツールの一部を無効にして、リモート接続など、他のツールを有効にすることができます。

DaRT リカバリ画像を作成する場合は、追加のドライバまたはファイルを含めるかどうかも指定します。 DaRT リカバリ画像に含める追加のドライバーまたはファイルの場所を確認します。

DaRT ツールの詳細については、「 [dart 10 のツールの概要](overview-of-the-tools-in-dart-10.md)」を参照してください。 セキュリティで保護された回復イメージを作成する方法の詳細については、「 [DaRT 10 のセキュリティに関する考慮事項](security-considerations-for-dart-10.md)」を参照してください。

## 回復イメージの前提条件


DaRT リカバリ画像を作成するには、次の項目が必要または推奨されます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>受講</strong></p></td>
<td align="left"><p><strong>詳細</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10 のソースファイル</p></td>
<td align="left"><p>DaRT リカバリ画像の作成に必要。 Windows 10 DVD または Windows 10 のソースファイルのパスを指定します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>プラットフォーム用の Windows デバッグツール</p></td>
<td align="left"><p><strong>クラッシュアナライザーを実行して、 </strong> コンピューターの障害の原因を特定する場合に必要です。 DaRT リカバリ画像を作成するときに、Windows のデバッグツールのパスを指定することをお勧めします。 Windows デバッグツールをダウンロードするには、次の手順を実行します。 <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/" data-raw-source="[Download and Install Debugging Tools for Windows](https://docs.microsoft.com/windows-hardware/drivers/debugger/)"> windows 用のデバッグツールをダウンロードしてインストール </a> します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>オプション: Crash Analyzer で使用する Windows のシンボルファイル <strong></strong></p></td>
<td align="left"><p>通常、デバッグ情報は、プログラムとは別のシンボルファイルに格納されます。 動作が停止した場合など、応答が停止しているアプリケーションをデバッグするときは、シンボル情報へのアクセス権を持っている必要があります。 詳細については、「 <a href="diagnosing-system-failures-with-crash-analyzer-dart-10.md" data-raw-source="[Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer-dart-10.md)"> クラッシュアナライザーによるシステム障害の診断」を参照してください </a> 。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック

[DaRT 10 の展開計画](planning-to-deploy-dart-10.md)

 

 




