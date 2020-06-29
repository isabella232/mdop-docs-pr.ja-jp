---
title: リモート コンピューターに公開サーバーをインストールする方法
description: リモート コンピューターに公開サーバーをインストールする方法
author: dansimp
ms.assetid: 37970706-54ff-4799-9485-b9b49fd50f37
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9d711fa51ade856b3ac5880ba60a19315c358734
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813995"
---
# リモート コンピューターに公開サーバーをインストールする方法


公開サーバーを別のコンピューターにインストールするには、次の手順を使用します。 次の手順を実行する前に、データベースと管理サーバーが利用可能であることを確認してください。

**公開サーバーを別のコンピューターにインストールするには**

1. アプリをインストールするコンピューターに、App-v 5.0 サーバーのインストールファイルをコピーします。 App-v 5.0 server のインストールを開始するには、右クリックして、管理者として**appv\_server\_setup.exe**を実行します。 **[インストール]** をクリックします。

2. [はじめ**に] ページで**、ライセンス条項を確認して同意し、[**次へ**] をクリックします。

3. [ **Microsoft update を使用してコンピューターをセキュリティで保護し**、最新の状態に維持する] ページで、microsoft update を有効にするには、[**更新プログラムをチェックするときに Microsoft update を使用する (推奨)** ] を選択します。 Microsoft 更新プログラムを無効にするには、[ **Microsoft Update を使用しない**] を選択します。 **[次へ]** をクリックします。

4. [**機能の選択**] ページで、[**発行サーバー** ] チェックボックスをオンにし、[**次へ**] をクリックします。

5. [**インストール場所**] ページで、既定の場所をそのまま使用し、[**次へ**] をクリックします。

6. [**発行サーバー構成の構成**] ページで、次の項目を指定します。

   -   発行サーバーが接続する管理サービスの URL です。 たとえば、と **http://ManagementServerName:12345** します。

   -   発行サービスに使用する web サイト名を指定します。 カスタム名を指定していない場合は、既定値をそのまま使用します。

   -   **ポートバインディング**には、 **54321**などの app-v 5.0 で使用される一意のポート番号を指定します。

7. [**インストールの準備ができ**ました] ページで、[**インストール**] をクリックします。

8. インストールが完了したら、発行サーバーを管理サーバーに登録する必要があります。 App-v 5.0 管理コンソールで、次の手順を使用してサーバーを登録します。

   1.  App-v 5.0 management server コンソールを開きます。

   2.  左側のウィンドウで、[**サーバー**] を選び、[**新しいサーバーの登録**] を選びます。

   3.  このサーバーの名前と説明を入力し (必要な場合)、[**追加**] をクリックします。

9. 発行サーバーが正常に実行されているかどうかを確認するには、パッケージを管理サーバーにインポートし、パッケージを AD グループに entitle して、パッケージを公開する必要があります。 インターネットブラウザーを使用して、次の URL を開き <strong> http://publishingserver:pubport </strong> ます。 サーバーが正常に実行されている場合は、次のような情報が表示されます。

   ```xml
   <Publishing Protocol="1.0">
     <Packages>
       <Package PackageId="28115343-06e2-44dc-a327-3a0b9b868bda" VersionId="5d03c08f-51dc-4026-8cf9-15ebe3d65a72" PackageUrl="\\server\share\file.appv" />
     </Packages>
     <NoGroup>
       <Package PackageId="28115343-06e2-44dc-a327-3a0b9b868bda" />
     </NoGroup>
   </Publishing>
   ```

   App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.0 の展開](deploying-app-v-50.md)

 

 





