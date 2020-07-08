---
title: パッケージを追加する方法
description: パッケージを追加する方法
author: dansimp
ms.assetid: 5407fdbe-e658-44f6-a9b8-a566b81dedce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c580d7d131017c52e278adda0208ffcb2e86ccf2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821397"
---
# パッケージを追加する方法


次のような方法で、Application Virtualization Server 管理コンソールからパッケージを追加できます。

-   プロセス内でパッケージを自動的に作成するアプリケーションをインポートします。

-   パッケージを手動で追加します。

アプリケーションを手動で追加するのではなく、インポートすることをお勧めします。 アプリケーションのインポートの詳細については、「[アプリケーションをインポートする方法](how-to-import-an-applicationserver.md)」を参照してください。

**パッケージを手動で追加するには**

1.  Application Virtualization Server 管理コンソールで、左側のウィンドウで [**パッケージ**] ノードを右クリックし、[**新しいパッケージ**] を選びます。

2.  [**新しいパッケージ**] ダイアログボックスで、[**パッケージ名**] フィールドに名前を入力します。

3.  [**パッケージファイルの完全なパス**] フィールドでパス名を参照するか、または入力します。 これは、SFT ファイルである必要があります。

    **注** SFT ファイルを参照している場合は、ローカルパス (たとえば、c/c ¥¥ \ _Apps \\ _App \ _Server \\ コンテンツ) をサーバーの静的ホスト名または IP アドレスに置き換えます。 変数 *% SFT \ _SOFTGRIDSERVER%* を使用するには、クライアントごとのコンピューター構成が必要です。

    仮想アプリケーションサーバーを参照するダイアログボックスでは、ユーザーがアクセスできる、サーバーの静的ホスト名や IP アドレスなどのネットワークの場所を使用する必要があります。 アプリケーションの Open Software Descriptor (OSD) ファイルでは、placeholder 変数 *% SFT \ _SOFTGRIDSERER%* をサーバーの静的ホスト名または IP アドレスに置き換えることができます。 Placeholder 変数から脱退する場合は、そのサーバーにアクセスする各クライアントコンピューターでこの変数を設定する必要があります。 ユーザーまたはシステム変数を、SFT \ _SOFTGRIDSERVER の各コンピューターで設定します。 変数の値は、サーバーの静的ホスト名または IP アドレスである必要があります。 変数を設定する場合は、クライアントセッションを終了し、Microsoft Windows にログアウトしてから、Microsoft Windows にもう一度ログインして、セッションが実行されていて、変数が設定されていた各コンピューターでセッションを再起動します。

     

4.  **[次へ]** をクリックします。

5.  [**概要**] ダイアログボックスにファイルの場所が表示され、ファイルをまだ保存していない場合は、その場所にファイルをコピーするように求められます。 情報を確認したら、[**完了**] をクリックします。

    **注** リモートサーバー上でアプリケーションを管理している場合は、次のダイアログボックスで、サーバーのコンテンツルートを基準としたファイルのパスのみを入力します。

     

## 関連トピック


[アプリケーションをインポートする方法](how-to-import-an-applicationserver.md)

[サーバー管理コンソールでパッケージを管理する方法](how-to-manage-packages-in-the-server-management-console.md)

 

 





