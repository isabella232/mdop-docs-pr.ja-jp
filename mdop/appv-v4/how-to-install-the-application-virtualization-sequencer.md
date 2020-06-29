---
title: Application Virtualization Sequencer をインストールする方法
description: Application Virtualization Sequencer をインストールする方法
author: dansimp
ms.assetid: 89cdf60d-18b0-4204-aa9f-b402610f8f0e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 56a6fe03f2149504b6c34c70b2b82ce2ba0b55ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817307"
---
# Application Virtualization Sequencer をインストールする方法


Microsoft Application Virtualization Sequencer は、アプリケーションを仮想アプリケーションとして実行できるように、アプリのインストールとセットアップのプロセスを監視および記録します。 オペレーティングシステムのみがインストールされているコンピューターに Sequencer をインストールする必要があります。 または、仮想環境を実行しているコンピューター (Microsoft Virtual PC など) に Sequencer をインストールすることもできます。 この方法は、最小限の追加構成で再利用できるクリーンなシーケンス環境を維持するのが簡単なため便利です。

アプリケーションのシーケンスに使用しているコンピューターの管理者権限を持っている必要があります。また、コンピューターは、Application Virtualization (App-v) クライアントのいずれかのバージョンを実行していない必要があります。 Sequencer を使用した仮想アプリケーションの作成はリソースを大量に消費するため、推奨された要件を満たしている、または超えているコンピューターに Sequencer をインストールすることが重要です。 セーフモードでの App-v sequencer の実行はサポートされていません。 システム要件の詳細については、「 [Application Virtualization のシステム要件](application-virtualization-system-requirements.md)」を参照してください。

**重要** アプリケーションの順序を設定した後で、新しいアプリケーションを正しい順序で処理するには、アプリケーションのシーケンスに使用しているコンピューターに、オペレーティングシステムと Sequencer を再インストールする必要があります。

 

**Microsoft Application Virtualization Sequencer をインストールするには**

1.  Microsoft Application Virtualization Sequencer インストールファイルをインストールするコンピューターにコピーします。

2.  Microsoft Application Virtualization Sequencer のインストールウィザードを開始するには、[ **setup.exe**] を選びます。 **Microsoft Visual C++ SP1 の再頒布可能パッケージ (x86)** がインストール前に検出されない場合は、 **setup.exe**によってインストールされます。

3.  [**ようこそ**] ページで、[**次へ**] をクリックします。

4.  [**使用**許諾契約書] ページで、使用許諾契約書に同意する場合は、[**使用許諾契約書に同意**します] を選択します。 **[次へ]** をクリックします。

5.  [**インポート先のフォルダー** ] ページで、既定のインストールフォルダーを承認するには、[**次へ**] をクリックします。 別の保存先フォルダーを指定するには、[**変更**] をクリックし、インストールに使用するインストールフォルダーを指定します。 **[次へ]** をクリックします。

6.  [**プログラムをインストールする準備ができ**ました] ページで、インストールを開始するには、[**インストール**] をクリックします。

7.  **InstallShield ウィザード**の [完了] ページで、インストールウィザードを閉じて Sequencer を開くには、[**完了**] をクリックします。 Sequencer を開かずにインストールウィザードを閉じるには、[**プログラムの起動**] をオフにし、[**完了**] をクリックします。

## 関連トピック


[Application Virtualization Sequencer をアップグレードする方法](how-to-upgrade-the-application-virtualization-sequencer.md)

[Application Virtualization の展開要件](application-virtualization-deployment-requirements.md)

 

 





