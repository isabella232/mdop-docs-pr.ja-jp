---
title: 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法
description: 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法
author: dansimp
ms.assetid: 4ef823a5-3106-44c5-aecc-29edf69c2fbb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 7bac244804b46309a0e0a75cb3742dfe22e92e8f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813882"
---
# 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法


次の手順を使用して、展開構成ファイルを使用して、アプリ-V 4.6 パッケージから app-v 5.1 パッケージに拡張ポイントを移行します。

**注** この手順では、最新バージョンの App-v 4.6 が実行されていることを前提としています。  
次の手順では、App-v 5.1 management server は必要ありません。

 

**パッケージから展開構成ファイルを使用して、パッケージから変換された App-v 5.1 パッケージに拡張ポイントを移行するには**

1. 移行するパッケージの展開構成ファイルが含まれているディレクトリを見つけます。 ポリシーを設定するには、 **Userconfiguration**セクションに対して次の更新を行います。

   **ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PackageName = &lt; パッケージ ID&gt;**

   展開構成ファイルのコンテンツの例を次に示します。

   &lt;? xml バージョン = "1.0"?&gt;

   &lt;DeploymentConfiguration

   xmlns = " <https://schemas.microsoft.com/appv/2010/deploymentconfiguration> " PackageId = &lt; パッケージ ID &gt; DisplayName = &lt; 表示名&gt;

   &lt;コンピューターの \/&gt;

   &lt;UserConfiguration&gt;

   &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"

   PackageName = &lt; パッケージ ID&gt;

   &lt;/UserConfiguration&gt;

   &lt;/Deploymentconfiguration&gt;

2. App-v 5.1 パッケージを追加するには、管理者特権の PowerShell コマンドプロンプトで次のように入力します。

   PS &gt; **$pkg = AppvClientPackage** **–** &lt; パッケージロケーションの path path へのパスパスを &gt;  - **DynamicDeploymentConfiguration** &lt; 展開構成ファイルへのパスを指定します。&gt;

   PS &gt; **Publish-AppVClientPackage $pkg**

3. 移行をテストするには、関連する FTAs またはショートカットを使用して仮想アプリケーションを開きます。 アプリケーションが、App-v 5.1 で開かれます。 どちらの場合も、App-v 4.6 パッケージと変換された App-v 5.1 パッケージはユーザーに公開されますが、アプリケーションの FTAs とショートカットは、App-v 5.1 パッケージで想定されています。

   App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[APP-V 5.1 の操作](operations-for-app-v-51.md)

 

 





