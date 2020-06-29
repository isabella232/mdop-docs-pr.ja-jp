---
title: 特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法
description: 特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法
ms.assetid: dad25992-3c75-4b7d-b4c6-c2edf43baaea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: a17d9dad11092a4c8356983b70bea3c18da1be04
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813875"
---
# 特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法

*注:** App-V 4.6 はメインストリームサポートを終了しました。

ユーザー構成ファイルを使用して、App-v で作成したパッケージを移行するには、次の手順を使用します。

**パッケージを変換するには**

1. 変換するパッケージのユーザー構成ファイルを見つけます。 ポリシーを設定するには、 **Userconfiguration**セクションで次の更新を実行します。 **ManagingAuthority TakeoverExtensionPointsFrom46 = "true" PACKAGENAME = &lt; パッケージ ID &gt; **。

   ユーザー構成ファイルの例を次に示します。

   &lt;? xml バージョン = "1.0"?&gt;

   &lt;UserConfiguration PackageId = &lt; パッケージ ID &gt; DisplayName = &lt; パッケージの名前&gt;

   xmlns = " <https://schemas.microsoft.com/appv/2010/userconfiguration"&gt> ; &lt;ManagingAuthority TakeoverExtensionPointsFrom46 = "true"

   PackageName = &lt; パッケージ ID&gt;

   &lt;/UserConfiguration&gt;

2. App-v 5.0 パッケージを追加するには、管理者特権の PowerShell コマンドプロンプトで次のように入力します。

   PS &gt; **$Pkg = AppvClientPackage –** &lt; パッケージの場所へのパスパス&gt;

   PS &gt; **Publish-AppVClientPackage $Pkg-dynamicuserconfiguration** &lt; Path をユーザー構成ファイルに対して設定します。&gt;

3. FTAs またはショートカットを使用してアプリケーションを開きます。 アプリケーションは、App-v 5.0 を使って開く必要があります。

   App-v SP2 パッケージと変換された app-v 5.0 パッケージはユーザーに公開されますが、アプリケーションの FTAs とショートカットは、App-v 5.0 パッケージによって想定されています。

   App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.0 の操作](operations-for-app-v-50.md)

 

 





