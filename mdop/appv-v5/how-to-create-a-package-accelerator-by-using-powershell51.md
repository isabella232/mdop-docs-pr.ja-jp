---
title: PowerShell を使用してパッケージ アクセラレータを作成する方法
description: PowerShell を使用してパッケージ アクセラレータを作成する方法
author: dansimp
ms.assetid: 0cb98394-4477-4193-8c5f-1c1773c7263a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 347572343cff058a7494574035464d66c4d61be4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814282"
---
# PowerShell を使用してパッケージ アクセラレータを作成する方法


アプリ-V 5.1 パッケージアクセラレータは、大規模で複雑なアプリケーションを自動的に処理します。 さらに、App-v 5.1 パッケージアクセラレータを適用するときに、仮想化されたパッケージを作成するためにアプリケーションを手動でインストールする必要はありません。

**パッケージアクセラレータを作成するには**

1.  App-v 5.1 sequencer をインストールします。 Sequencer のインストールの詳細について[は、「sequencer をインストールする方法」を](how-to-install-the-sequencer-51beta-gb18030.md)参照してください。

2.  PowerShell 本体を開くには、[**開始**] をクリックし、「 **powershell**」と入力します。 **[Windows PowerShell]** を右クリックし、**[管理者として実行]** を選択します。 **AppvPackageAccelerator**コマンドレットを使用します。

3.  パッケージアクセラレータを作成するには、accelerator パッケージを使って、アクセラレータの作成元、インストールメディアまたはインストールファイル、必要に応じて読み取り専用ファイルを作成して使用する必要があります。 パッケージアクセラレータコマンドレットを使うには、次のパラメーターが必要です。

    -   [インストールされている**ファイルのパス**-アプリケーションのインストールパスを指定してください。

    -   **インストーラ**–アプリケーションインストーラメディアへのパスを指定します。

    -   **InputPackagePath** – appv パッケージへのパスを指定します。

    -   **Path** –パッケージの出力ディレクトリを指定します。

    次の例は、app-v パッケージとインストールメディアを使ってパッケージアクセラレータを作成する方法を示しています。

    **AppvPackageAccelerator-InputPackagePath path: &lt; app-v ファイルへのパス &gt; -インストーラーの &lt; 実行可能ファイルへのインストーラーパス- &gt; &lt; 出力パスの path ディレクトリ&gt;**

    **AppvPackageAccelerator**コマンドレットで使用できる追加のオプションパラメーターは、次の一覧に表示されます。

    -   **AcceleratorDescriptionFile** -ユーザーが作成したパッケージアクセラレータ命令へのパスを指定します。 パッケージアクセラレータの手順は、パッケージアクセラレータを使用して作成されたパッケージと共にパッケージ化される **.txt**または **.rtf**の説明ファイルです。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[PowerShell を使用した App-V 5.1 の管理](administering-app-v-51-by-using-powershell.md)

 

 





