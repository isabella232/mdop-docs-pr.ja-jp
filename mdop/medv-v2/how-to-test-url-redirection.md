---
title: URL のリダイレクトをテストする方法
description: URL のリダイレクトをテストする方法
author: dansimp
ms.assetid: 38d80088-da1d-4098-b27e-76f9e78f81dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: d964cf9d0114d3085d7e8952eebc82486b7b76cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824447"
---
# URL のリダイレクトをテストする方法


初回のセットアップが完了した後、次のタスクを実行することで、URL リダイレクション機能が予期したとおりに動作していることを確認できます。

**重要** URL リダイレクションが適切に機能するには、MED-V ホストエージェントが実行されている必要があります。

<a href="" id="bkmk-urlredir"></a>**URL リダイレクションをテストするには**

1.  ホストコンピューターで Internet Explorer ブラウザーを開き、リダイレクト用に指定した URL を入力します。

2.  ゲスト仮想マシンの Internet Explorer で web ページが開かれていることを確認します。

3.  テストする URL ごとに、この手順を繰り返します。

**URL を追加または削除できることをテストするには**

1.  MED-V ワークスペースの URL を追加または削除します。

    MED-V ワークスペースでのリダイレクトの Url の追加と削除の詳細については、「 [MED-V Url リダイレクションを管理](manage-med-v-url-redirection.md)する」を参照してください。

2.  リダイレクトリストに URL を追加した場合は、「 [Url リダイレクションをテストする](#bkmk-urlredir)」の手順を繰り返して、新しい url が意図したようにリダイレクトされることを確認します。

3.  リダイレクトリストから URL を削除した場合は、次の手順に従って削除されていることを確認します。

    1.  ホストコンピューターで Internet Explorer ブラウザーを開き、[リダイレクション] の一覧から削除した URL を入力します。

    2.  ゲストの仮想マシンではなく、ホストコンピューターの Internet Explorer で web ページが開かれていることを確認します。

        **注** URL リダイレクションの変更が行われるまでに数秒かかる場合があります。

**注** URL リダイレクション設定を確認するときに問題が発生した場合は、「[操作のトラブルシューティング](operations-troubleshooting-medv2.md)」を参照してください。

MED-V ワークスペースで URL リダイレクションのテストが完了したら、他の構成をテストして、意図したとおりに機能するかどうかを確認できます。

MED-V ワークスペースパッケージのテストが完了し、意図したとおりに機能していることを確認したら、MED-V ワークスペースを企業に展開できます。

## 関連トピック

[アプリケーションの公開をテストする方法](how-to-test-application-publishing.md)

[初回使用時のセットアップの設定を確認する方法](how-to-verify-first-time-setup-settings.md)

[MED-V ワークスペース パッケージの展開](deploying-the-med-v-workspace-package.md)

 

 





