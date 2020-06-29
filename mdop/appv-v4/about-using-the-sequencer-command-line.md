---
title: Sequencer コマンド ラインの使用について
description: Sequencer コマンド ラインの使用について
author: dansimp
ms.assetid: 0fd5f81b-17f9-4065-bce2-8785e8aac7c7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: afb3fb8608c78a3b9237a80529a6c22d792661ba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819904"
---
# Sequencer コマンド ラインの使用について


コマンドラインを使って、シーケンスが適用されたアプリケーションパッケージを作成することができます。 コマンドラインを使用して仮想アプリケーションを作成することは、次のシナリオで役立ちます。

-   多数の順序が付けられたアプリケーションパッケージを作成する必要があります。

-   順序付けされたアプリケーションパッケージを定期的に作成する必要があります。

**重要** コマンドプロンプトでシーケンス処理を行うと、既定のシーケンスのみが許可されます。 既定のシーケンスパラメーターを変更する必要がある場合は、シーケンス処理されたアプリケーションパッケージを手動で変更するか、アプリケーションを再順序付ける必要があります。

 

シーケンスウィザードを使用して、既存のシーケンスされたアプリケーションパッケージに対する以降のすべての変更を行う必要があります。

## 前提条件


コマンドプロンプトを使用してアプリケーションを順序指定するには、次の条件を満たしている必要があります。

-   シーケンスを実行しようとしているアプリケーションは、インストーラまたは Windows インストーラパッケージの外部で、変更または回避策を要求する必要はありません。

-   シーケンス処理の前に、シーケンス処理されたアプリケーションパッケージを作成するためのバッチファイルの一覧を準備する必要があります。

-   レビューコマンドラインパラメーターの詳細については、「[コマンドラインパラメーター](command-line-parameters.md)」を参照してください。

-   コマンドラインを使用して、シーケンス付きのアプリケーションパッケージを作成するときに表示される可能性のあるエラーを確認します。 詳細については、「これらのエラー」を参照してください。[コマンドラインエラー](command-line-errors.md)について説明します。

## 関連トピック


[コマンド ラインを使用して仮想アプリケーションを管理する方法](how-to-manage-virtual-applications-using-the-command-line.md)

 

 





