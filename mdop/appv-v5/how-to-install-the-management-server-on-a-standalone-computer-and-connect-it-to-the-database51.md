---
title: スタンドアロン コンピューターに管理サーバーをインストールしてデータベースに接続する方法
description: スタンドアロン コンピューターに管理サーバーをインストールしてデータベースに接続する方法
author: dansimp
ms.assetid: 3f83c335-d976-4abd-b8f8-d7f5e50b4318
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f2cce96f914f65e7432b5ed9e7c5ecb1a6306990
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814011"
---
# スタンドアロン コンピューターに管理サーバーをインストールしてデータベースに接続する方法


次の手順を使用して、管理サーバーをスタンドアロンコンピューターにインストールし、データベースに接続します。

**スタンドアロンコンピューターに管理サーバーをインストールしてデータベースに接続するには**

1.  アプリをインストールするコンピューターに、App-v 5.1 サーバーのインストールファイルをコピーします。 App-v 5.1 server のインストールを開始するには、右クリックして、管理者として**appv\_server\_setup.exe**を実行します。 **[インストール]** をクリックします。

2.  [はじめ**に] ページで**、ライセンス条項を確認して同意し、[**次へ**] をクリックします。

3.  [ **Microsoft update を使用してコンピューターをセキュリティで保護し**、最新の状態に維持する] ページで、microsoft update を有効にするには、[**更新プログラムをチェックするときに Microsoft update を使用する (推奨)** ] を選択します。 Microsoft 更新プログラムを無効にするには、[ **Microsoft Update を使用しない**] を選択します。 **[次へ]** をクリックします。

4.  [**機能の選択**] ページで、[**管理サーバー** ] チェックボックスをオンにし、[**次へ**] をクリックします。

5.  [**インストール場所**] ページで、既定の場所をそのまま使用し、[**次へ**] をクリックします。

6.  [**既存の管理データベースの構成**] ページで、[**リモート Sql Server を使用**する] を選び、Microsoft sql sql を実行しているコンピューターのコンピューター名 ( **SqlServerMachine**など) を入力します。

    **注**  
    Microsoft SQL Server が同じサーバーに展開されている場合は、[**ローカル Sql server を使用する**] を選びます。



~~~
For the SQL Server Instance, select **Use the default instance**. If you are using a custom Microsoft SQL Server instance, you must select **Use a custom instance** and then type the name of the instance.

Specify the **SQL Server Database name** that this management server will use, for example **AppvManagement**.
~~~

7. [ **Management Server 構成の構成**] ページで、管理コンソールに接続する AD グループまたはアカウント (たとえば、 **MyDomain\\MyUser**や**MyDomain\\AdminGroup**) を指定します。 指定したアカウントまたは広告グループは、管理コンソールを使用してサーバーを管理することができます。 インストール後に管理コンソールを使用して、ユーザーまたはグループを追加することができます。

   管理サービスに使用する**Web サイト名**を指定します。 カスタム名を指定していない場合は、既定値をそのまま使用します。 ポートの**バインド**で、使用する一意のポート番号を指定します (例**12345**)。

8. **[インストール]** をクリックします。

9. セットアップが正常に完了したことを確認するには、web ブラウザーを開いて、次の URL を入力し http://managementserver:portnumber/Console ます。 インストールに成功した場合は、エラーメッセージや警告が表示されることなく、**管理コンソール**が表示されます。

   App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.1 の展開](deploying-app-v-51.md)









