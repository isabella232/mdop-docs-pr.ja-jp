---
title: 既存の Windows インストーラー ファイルに関連付けられているオペレーティング システムを変更する方法
description: 既存の Windows インストーラー ファイルに関連付けられているオペレーティング システムを変更する方法
author: dansimp
ms.assetid: 0633f7e2-aebf-4e00-be02-35bc59dec420
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 63184852f996cbe09b476f456f7c2b509549f4fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816954"
---
# 既存の Windows インストーラー ファイルに関連付けられているオペレーティング システムを変更する方法


次の手順を使用して、App-v Sequencer を使用して作成された既存の Windows インストーラー (**MSI**) ファイルに関連付けられているオペレーティングシステムのバージョンを変更します。

**既存の Windows インストーラーファイルのオペレーティングシステムを変更するには**

1.  オペレーティングシステムのみがインストールされている環境内のコンピューターに、App-v Sequencer をインストールします。 または、仮想環境を実行しているコンピューター (Microsoft Virtual PC など) に Sequencer をインストールすることもできます。 この方法は、最小限の追加構成で再利用できるクリーンなシーケンス環境を維持するのが容易であるために役立ちます。 App-v Sequencer のインストールの詳細については、「 [Sequencer をインストールする方法](how-to-install-the-sequencer.md)」を参照してください。

2.  変更する Windows Installer ファイルが格納されている仮想アプリケーションパッケージ全体を、Sequencer を実行しているコンピューターにコピーします。

3.  Windows インストーラファイルを変更するには、Sequencer コンソールを開き、[**パッケージ**を開く] を選択し  /  **Open**て、Windows installer ファイルに関連付けられている仮想アプリケーションパッケージの保存場所を参照します。

4.  オペレーティングシステムを追加または削除するには、Sequencer コンソールの [**展開**] タブを選択します。 Windows インストーラーファイルに関連付けられる追加のオペレーティングシステムを指定するには、目的のオペレーティングシステムを選択し、**選択**したオペレーティングシステムのリストコントロールを指す矢印をクリックします。

    オペレーティングシステムの関連付けを削除するには、削除するオペレーティングシステムを選択し、**使用可能な**オペレーティングシステムのリストコントロールを指す矢印をクリックします。

5.  仮想アプリケーションパッケージに関連付けられる新しい Windows インストーラーを作成するには、[ **Microsoft Windows installer (MSI) パッケージの生成**] を選びます。 または、「**ツール**」「MSI の作成」を選択することもでき  /  **Create MSI**ます。

    **注** [**ツール**] の [MSI の作成] を選ん / **Create MSI**で新しい Windows インストーラーファイルを作成する場合は、**手順 6**を省略できます。

     

6.  仮想アプリケーションパッケージを保存するには、[**パッケージ**の保存] を選び  /  **Save**ます。

## 関連トピック


[Application Virtualization Sequencer のタスク](tasks-for-the-application-virtualization-sequencer.md)

 

 





