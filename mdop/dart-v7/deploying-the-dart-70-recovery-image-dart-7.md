---
title: DaRT 7.0 の回復イメージの展開
description: DaRT 7.0 の回復イメージの展開
author: dansimp
ms.assetid: 6bba7bff-800f-44e4-bcfc-e143115607ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cef626e50bf1049529c51afca5e536b03b3d915d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812658"
---
# DaRT 7.0 の回復イメージの展開


Microsoft Diagnostics and Recovery ツールセット (DaRT) 7 の回復イメージを含む国際標準化機構 (ISO) ファイルを作成した後、エンドユーザーとヘルプデスクの担当者が利用できるように、企業全体で DaRT 回復イメージを展開することができます。 DaRT リカバリイメージの展開に使用できる、4つのサポートされるメソッドが用意されています。

-   ISO イメージファイルを CD または DVD に書き込む

-   ISO イメージファイルのコンテンツを USB フラッシュドライブ (UFD) に保存する

-   ISO イメージから boot.ini ファイルを抽出し、エンドユーザーのコンピューターで使用できるリモートパーティションとして展開する

-   ISO イメージから boot.ini ファイルを抽出し、新しい Windows 7 インストールの回復パーティションに展開する

**重要** **DaRT Recovery イメージウィザード**では、CD または DVD の書き込みオプションのみが提供されます。 回復イメージを保存および展開するその他のすべての方法については、DaRT に含まれていないツールに関連する追加の手順が必要です。 このセクションでは、これらの他の方法に関するガイダンスとリンクをいくつか紹介します。

 

## USB フラッシュドライブを使用して DaRT リカバリ画像を展開する


DaRT Recovery イメージウィザードの実行が完了したら、のツールを使って、 <https://go.microsoft.com/fwlink/?LinkId=218888> USB フラッシュドライブ (UFD) に ISO 画像ファイルをコピーできます。

[USB フラッシュ ドライブを使用して DaRT の回復イメージを展開する方法](how-to-deploy-the-dart-recovery-image-using-a-usb-flash-drive-dart-7.md)

## DaRT リカバリ画像を回復パーティションの一部として展開する


DaRT Recovery イメージウィザードの実行と回復イメージの作成が完了したら、ISO イメージファイルから boot.ini ファイルを抽出して、Windows 7 イメージの回復パーティションとして展開することができます。

[回復パーティションの一部として DaRT の回復イメージを展開する方法](how-to-deploy-the-dart-recovery-image-as-part-of-a-recovery-partition-dart-7.md)

## DaRT リカバリ画像をリモートのパーティションとして展開する


DaRT Recovery イメージウィザードの実行と回復イメージの作成が完了したら、ISO イメージファイルから boot.ini ファイルを抽出し、ネットワーク上のリモートパーティションとして展開することができます。

[リモート パーティションとして DaRT の回復イメージを展開する方法](how-to-deploy-the-dart-recovery-image-as-a-remote-partition-dart-7.md)

## DaRT リカバリイメージの展開を管理するためのその他のリソース


-   [DaRT 7.0 の展開](deploying-dart-70-new-ia.md)

 

 





