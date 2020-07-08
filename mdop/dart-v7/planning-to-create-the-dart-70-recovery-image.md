---
title: DaRT 7.0 の回復イメージの作成計画
description: DaRT 7.0 の回復イメージの作成計画
author: dansimp
ms.assetid: e5d49bee-ae4e-467b-9976-c1203f6355f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c370d2a69ec8ccea217696045e64e9a0ae724815
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821334"
---
# DaRT 7.0 の回復イメージの作成計画


Microsoft 診断/回復ツールセット (DaRT) 7 の回復イメージを作成する計画がある場合は、このセクションの情報を参照してください。

## DaRT 7 の回復イメージの作成を計画する


DaRT リカバリ画像を作成する場合は、イメージに含めるツールを決定する必要があります。 この決定を行うときは、さまざまな DaRT ツールへのアクセス権がエンドユーザーによって異なる可能性があることを覚えておいてください。 DaRT ツールの詳細については、「 [dart 7.0 でのツールの概要](overview-of-the-tools-in-dart-70-new-ia.md)」を参照してください。 セキュリティで保護された回復イメージの作成に役立つ詳細については、「 [DaRT 7.0 のセキュリティに関する考慮事項](security-considerations-for-dart-70-dart-7.md)」を参照してください。

DaRT リカバリ画像を作成する場合は、追加のドライバまたはファイルを含めるかどうかも指定します。 DaRT リカバリ画像に含める追加のドライバーまたはファイルの場所を確認します。

## 前提条件


DaRT リカバリ画像を作成するには、次の項目が必要または推奨されます。

-   Windows 7 のソースファイル

    Windows 7 DVD または Windows 7 のソースファイルのパスを指定する必要があります。 DaRT 回復イメージを作成するには、Windows 7 のソースファイルが必要です。

-   プラットフォーム用の Windows デバッグツール

    **クラッシュアナライザー**を実行して、コンピューターがクラッシュした原因を特定するには、Windows デバッグツールが必要です。 DaRT リカバリ画像を作成するときに、Windows のデバッグツールのパスを指定することをお勧めします。 必要に応じて、Windows デバッグツールをダウンロードできます。 [windows 用のデバッグツールをダウンロードしてインストール](https://go.microsoft.com/fwlink/?LinkId=99934)します。

-   オプション:**単体システム Sweeper**定義

    このツールを実行するときには、**スタンドアロンシステム Sweeper**の最新の定義が必要です。 **スタンドアロンシステム Sweeper**を実行するときに定義をダウンロードすることもできますが、DaRT 回復イメージを作成するときに最新の定義をダウンロードすることをお勧めします。 この方法でも、問題のあるコンピューターにネットワーク接続がない場合でも、最新の定義を使用してツールを実行できます。

-   オプション: **Crash Analyzer**で使用する Windows のシンボルファイル

    通常、デバッグ情報は、実行可能ファイルとは別のシンボルファイルに格納されます。 応答を停止したアプリケーションをデバッグするとき (たとえば、クラッシュした場合)、シンボル情報へのアクセス権を持っている必要があります。 詳細については、「[クラッシュアナライザーによるシステム障害の診断](diagnosing-system-failures-with-crash-analyzer--dart-7.md)」を参照してください。

## 関連トピック


[DaRT 7.0 の展開計画](planning-to-deploy-dart-70.md)

 

 





