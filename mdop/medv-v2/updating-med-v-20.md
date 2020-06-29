---
title: MED-V 2.0 の更新
description: MED-V 2.0 の更新
author: dansimp
ms.assetid: beea2f54-42d7-4a17-98e0-d243a8562265
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 62e8987ec511783422b8dd336dd4f3be2008c9b2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823734"
---
# MED-V 2.0 の更新


Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 に適切なセキュリティ更新プログラムを適用して、システムのセキュリティを強化します。

## MED-V の更新


MED-V は、エンドユーザーが、または電子的なソフトウェア配布システムを使用してサイレントモードで更新することができます。 MED-V Host agent をインストールすると、MED-V Host Agent がアップグレードされ、必要に応じて MED-V ワークスペースが更新されます。 MED-V ホストエージェントとゲストエージェントの同期が維持されます。MED-V Host Agent が更新されているときに、アプリケーションが MED-V ワークスペースから実行されている場合は、更新を完了するためにホストコンピューターの再起動が必要になります。 アプリケーションが実行されていない場合、MED-V は自動的に再開され、ホストコンピューターの再起動なしでアップグレードが完了します。

電子ソフトウェア配布システムを使用して MED-V を更新する場合は、再起動の動作を制御できます。 これを行うには、MED-V\_HostAgent\_Setup.exe をインストールするときに、コマンドプロンプトで **「REBOOT = "ReallySuppress"** 」と入力して、再起動を抑制します。 次に、3010のリターンコード (再起動が必要であることを示すシグナル) を取得するように電子ソフトウェア配布システムを構成し、[再起動の設定] 動作を実行します。

## 関連トピック


[MED-V テクニカル リファレンス](technical-reference-for-med-v.md)

 

 





