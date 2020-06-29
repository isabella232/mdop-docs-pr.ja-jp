---
title: サーバー管理コンソールアプリケーションの仮想化システムノード
description: サーバー管理コンソールアプリケーションの仮想化システムノード
author: dansimp
ms.assetid: 9450832e-335c-41e7-af24-fddb8ffc327c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51256ee7e96a97016e73dc79c87e4d422198cfb3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815444"
---
# サーバー管理コンソール: Application Virtualization システム ノード


Application Virtualization システムノードは、**スコープ**ウィンドウのトップレベルノードです。 このノードには、本体が現在制御しているサーバーの名前が表示されます。または、コンソールがローカルコンピューターに接続されている場合は、ローカルコンピューターの名前 (名前によって接続されている場合) または "local" を表示します。 Application Virtualization システムノードから、別のコンピューターに接続するか、別の資格情報を使用して現在のコンピューターに接続することができます。

Application Virtualization システムノードを右クリックすると、次の要素が表示されます。

<a href="" id="configure-connection"></a>**接続を構成する**  
このダイアログボックスでは、次の設定を変更できます。

- [ **Web Service Host Name**]: 接続するアプリケーションの仮想化システムの名前を入力できます。または、 **localhost**を入力してローカルコンピューターに接続します。

- [**セキュリティで保護された接続を使用**]: セキュリティで保護された接続でサーバーに接続する場合に選択します。

- [ **Port (ポート**): 接続に使用するポート番号を入力することができます。 80は既定の標準ポート番号で、443は既定のセキュリティで保護されたポート番号です。

- [**現在の Windows アカウントを使う**]: 現在の windows アカウントの資格情報を使用する場合に選択します。

- [ **Windows アカウントの指定**]: 別のユーザーとしてサーバーに接続する場合に選択します。

- [ **Name (名前**) *DOMAIN\\username*または username@domain のいずれかの形式を使用して、新しいユーザーの名前を入力することができ <em> </em> ます。

- [ **Password (パスワード**): 新しいユーザーに対応するパスワードを入力できます。

<a href="" id="system-options"></a>**システムオプション**  
このダイアログボックスの次のタブで、関連付けられている設定を変更できます。

-   **[全般] タブ**: OSD およびアイコンファイルが保存されている**既定のコンテンツパス**を指定できます。

-   **[データベース] タブ**: データベースの最大**サイズ**と**利用履歴**を指定できます。

<a href="" id="view"></a>**View**  
Application Virtualization Server 管理コンソールの外観を変更します。 本体の表示を変更する方法については、Microsoft 管理コンソールのヘルプファイルを参照してください。

<a href="" id="new-window-from-here"></a>**ここから新しいウィンドウ**  
新しい管理コンソールウィンドウを開きます。

<a href="" id="export-list"></a>**エクスポートリスト**  
**結果**ペインの内容を含むタブ区切りのテキストファイルを作成します。 この項目は、作成するテキストファイルの場所を指定する、標準の [**ファイルの保存**] ダイアログボックスを表示します。

<a href="" id="help"></a>**ヘルプ**  
管理コンソールのヘルプファイルを開始します。

## 関連トピック


[Application Virtualization サーバー管理コンソール リファレンス](application-virtualization-server-management-console-reference.md)

 

 





