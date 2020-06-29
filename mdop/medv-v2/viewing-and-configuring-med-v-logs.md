---
title: MED-V ログの表示と構成
description: MED-V ログの表示と構成
author: dansimp
ms.assetid: a15537ce-981d-4f55-9c3c-e7fbf94b8fe5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7984cec072827136db9ea52a535c0ea44c6bc2c3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823727"
---
# MED-V ログの表示と構成


MED-V の問題と問題のトラブルシューティングを行うときに、MED-V イベントログにアクセスすることが必要になることがあります。 ホストコンピューターとゲスト仮想マシンのイベントビューアーは、MED-V 管理ツールキットを使って開くことができます。 Med-v 管理ツールキットを使用して、MED-V イベントログで MED-V イベントを報告するログレベルを設定することもできます。

MED-V 管理ツールキットを開く方法の詳細については、「[管理ツールキットを使用した med-v のトラブルシューティング](troubleshooting-med-v-by-using-the-administration-toolkit.md)」を参照してください。

## MED-V イベントログの表示


[ **Med-v 管理ツールキット**] ウィンドウで、[ **host Events** ] をクリックして、ホストコンピューターのイベントビューアーを開きます。 または、[**ゲストイベント**] をクリックして、ゲスト仮想マシンのイベントビューアーを開きます。

イベントビューアーには、MED-V を展開または管理するときに発生する可能性がある問題のトラブルシューティングに使用できる、対応するイベントログが表示されます。 既定では、エラーと警告のみが表示されます。 特定のイベント Id とメッセージの詳細については、「 [Med-v イベントログのメッセージ](med-v-event-log-messages.md)」を参照してください。

**注** エンドユーザーが管理者権限を持っている場合にのみ、イベントログファイルをゲストに保存することができます。

 

### ホストコンピューターでイベントビューアーを手動で開くには

1.  [**スタート**] をクリックし、[**コントロールパネル**] をクリックして、[**管理ツール**] をクリックします。

2.  [**イベントビューアー**] をダブルクリックし、[**アプリケーションとサービスログ**] をクリックします。

3.  [ **MEDV**] をダブルクリックします。

## MED-V イベントログの構成


Med-v のイベントログレベルを指定するには、MED-V 管理ツールキットの対応するオプションボタンを選択します。 イベントログには、エラーのみ、エラーと警告、エラー、警告、情報メッセージを含めるかどうかを決めることができます。 指定されたイベントログレベルは、ホストコンピューターとゲスト仮想マシンの両方に対して設定されます。

また、EventLogLevel registry 値を編集して、イベントログレベルを指定することもできます。 詳細については、「 [Med-v ワークスペース構成の設定を管理する](managing-med-v-workspace-configuration-settings.md)」を参照してください。

**注** **Med-v 管理ツールキット**ウィンドウで指定したレベルは、将来の med-v イベントログに適用されます。 すべてのエラー、警告、情報メッセージを取得するようにレベルを設定した場合、イベントログの入力が速くなり、古いイベントが削除されます。

 

## 関連トピック


[MED-V ワークスペースの再開とリセット](restarting-and-resetting-a-med-v-workspace.md)

[MED-V ワークスペースの構成の表示](viewing-med-v-workspace-configurations.md)

 

 





