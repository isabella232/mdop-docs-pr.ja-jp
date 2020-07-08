---
title: MED-V クライアントと MED-V 管理コンソールをインストールする方法
description: MED-V クライアントと MED-V 管理コンソールをインストールする方法
author: dansimp
ms.assetid: 8a5f3010-3a50-487e-99d8-e352e5cb51c6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 24a486cc7cf5534171f80b08dc93742e03cd4a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826984"
---
# MED-V クライアントと MED-V 管理コンソールをインストールする方法


Client.msi パッケージには、次の MED-V コンポーネントが含まれています。

-   Med-v クライアント-med-v ワークスペースを実行するためにクライアントコンピューターにインストールする必要がある MED-V ソフトウェア。

-   MED-V 管理コンソール—管理者が、イメージ、MED-V ワークスペース、ポリシーを作成および管理するために使用できる管理ツールです。

MED-V 管理コンソールと MED-V クライアントは、どちらも MED-V の client.msi パッケージからインストールされます。 ただし、MED-V クライアントは、インストール中に [ **Med-v management application をインストール**する] チェックボックスをオフにすることによって、med-v 管理コンソールなしで個別にインストールすることができます。

**注**  
MED-V クライアントと MED-V の管理コンソールは、Windows 7、Windows Vista、Windows XP ベースのコンピューターにのみインストールできます。 サーバー製品にインストールすることはできません。



**注**  
Windows **runas**コマンドを使用して、med-v クライアントをインストールしないでください。



**MED-V クライアントをインストールするには**

1.  ローカルコンピューターのローカル管理者の権限を持つユーザーとしてログインします。

2.  MED-V パッケージを実行します。

    MED-V パッケージは*MED-V\_x.msi*と呼ばれます。ここで、 *x*はバージョン番号です。

    たとえば、 *MED-V\_1.0.65.msi*とします。

3.  **InstallShield ウィザード**の [ようこそ] 画面が表示されたら、[**次へ**] をクリックします。

4.  [**使用**許諾契約書] 画面で、使用許諾契約書を読み、[**使用許諾契約書に同意**します] をクリックして、[**次へ**] をクリックします。

    [**インポート先のフォルダー** ] 画面が表示され、既定のインストールフォルダーが表示されます。

    既定のインストールフォルダーは、オペレーティングシステムがインストールされているディレクトリです。

    -   MED-V をインストールする必要があるフォルダーを変更するには、[**変更**] をクリックし、既存のフォルダーを参照します。

5.  **[次へ]** をクリックします。

6.  [ **Med-v の設定**] 画面で、次のように med-v のインストールを構成します。

    -   [ **Med-v management application をインストール**する] チェックボックスをオンにして、管理コンポーネントをインストールに含めます。

        **注**  
        エンタープライズデスクトップ仮想化の管理者は、MED-V 管理アプリケーションをインストールする必要があります。 このアプリケーションは、デスクトップイメージと MED-V のワークスペースを構成するために必要です。



~~~
-   Select the **Load MED-V when Windows starts** check box to start MED-V automatically on startup.

-   Select the **Add a MED-V shortcut to my desktop** check box to create a MED-V shortcut on your desktop.

-   In the **Server address** field, type the server address.

-   In the **Server port** field, type the server's port.

-   Select the **Server requires encrypted connections (https)** check box to work with https.

-   The default virtual machine images folder is displayed. The default installation folder is *%systemdrive%\\MED-V Images\\*. To change the folder where MED-V should be installed, click **Change**, and browse to an existing folder.
~~~

7. **[次へ]** をクリックします。

8. [**プログラムをインストールする準備ができ**ました] 画面で、[**インストール**] をクリックします。

   MED-V クライアントのインストールが開始されます。 これには数分かかることがあり、画面にテキストが表示されないことがあります。 インストール中に、いくつかの進行状況画面が表示されます。 メッセージが表示されたら、表示される指示に従います。

   インストールが正常に完了すると、 **InstallShield ウィザード**の [完了] 画面が表示されます。

9. [**完了**] をクリックしてウィザードを閉じます。

## 関連トピック


[サポートされる構成](supported-configurationsmedv-orientation.md)

[インストールとアップグレードのチェックリスト](installation-and-upgrade-checklists.md)









