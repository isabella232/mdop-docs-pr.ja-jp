---
title: Application Virtualization システムに接続する方法
description: Application Virtualization システムに接続する方法
author: dansimp
ms.assetid: ac38216c-5464-4c0b-a4d3-3949ba6358ac
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 30d60e187e1b7595fd0dce6641fa027a1df68f3d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817714"
---
# Application Virtualization システムに接続する方法


管理コンソールを使用して、アプリケーション、ファイルの種類の関連付け、パッケージ、アプリケーションライセンス、サーバーグループ、プロバイダーポリシー、管理者を管理するには、application Virtualization Server 管理コンソールをアプリケーションの仮想化システムに接続する必要があります。 次の手順では、本体をアプリケーションの仮想化システムに接続するために必要な手順について説明します。

**アプリケーションの仮想化システムに接続するには**

1. **スコープ**ウィンドウで [Application virtualization system] ノードを右クリックし、ポップアップメニューから [**アプリケーション仮想化システムに接続する**] を選択します。

   **注**  
   Application Virtualization server の管理には、Application Virtualization 管理コンソール、管理 Web サービス、SQL データストアという3つのコンポーネントがあります。 これらのコンポーネントが複数の物理マシンに分散されている場合は、コンポーネントがシステム間で通信するためのセキュリティを適切に構成する必要があります。 詳細については、次のマニュアルと記事を参照してください。

   [委任に対して信頼されるようにサーバーを構成する方法](https://go.microsoft.com/fwlink/?LinkID=166682)(https://go.microsoft.com/fwlink/?LinkID=166682)

   [Application Virtualization システムの計画と展開ガイド](https://go.microsoft.com/fwlink/?LinkID=122063)(https://go.microsoft.com/fwlink/?LinkID=122063)

   [Application Virtualization システムの運用ガイド](https://go.microsoft.com/fwlink/?LinkID=133129)(https://go.microsoft.com/fwlink/?LinkID=133129)

   Microsoft サポート技術情報の[記事 930472](https://go.microsoft.com/fwlink/?LinkId=114647) (https://go.microsoft.com/fwlink/?LinkId=114647)

   Microsoft サポート技術情報の[記事 930565](https://go.microsoft.com/fwlink/?LinkId=114648) (https://go.microsoft.com/fwlink/?LinkId=114648)

     

2. [**アプリケーション仮想化システムに接続**します] ダイアログボックスのフィールドに入力します。

   1. [ **Web Service Host Name**]: 接続するアプリケーションの仮想化システムの名前を入力するか、ローカルサーバーに接続するには**localhost**を入力します。

   2. [**セキュリティで保護さ**れた接続を使用する]: セキュリティで保護された接続でサーバーに接続する場合は、このチェックボックスをオンにします。

   3. [ **Port (ポート**) 数-接続に使用するポート番号を入力します。 **80**は既定の標準ポート番号で、 **443**はセキュリティで保護されたポート番号です。

   4. [**現在の Windows アカウントを使用**する] —現在の windows アカウントの資格情報を使用する場合は、このラジオボタンを選択します。

   5. [ **Windows アカウントの指定**]: 別のユーザーとしてサーバーに接続する場合は、このラジオボタンを選択します。

   6. **名前**: *DOMAIN\\username*または username@domain のいずれかの形式を使用して、新しいユーザーの名前を入力し <em> </em> ます。

   7. [ **Password (パスワード**) 新しいユーザーに対応するパスワードを入力します。

3. **[OK]** をクリックします。

## 関連トピック


[Application Virtualization サーバー管理コンソールで管理タスクを実行する方法](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

 

 





