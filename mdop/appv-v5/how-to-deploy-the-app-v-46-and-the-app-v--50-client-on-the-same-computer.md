---
title: App-V 4.6 と App-V 5.0 クライアントを同じコンピューターに展開する方法
description: App-V 4.6 と App-V 5.0 クライアントを同じコンピューターに展開する方法
ms.assetid: 5b7e27e4-4360-464c-b832-f1c7939e5485
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.date: 06/21/2016
ms.prod: w10
ms.openlocfilehash: f10f3d159c4724f3b486215b1169825bb029316d
ms.sourcegitcommit: 0132cd232b9c030820d95d91b71c4def0184400a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2021
ms.locfileid: "11907230"
---
# <a name="how-to-deploy-the-app-v-46-and-the-app-v-50-client-on-the-same-computer"></a>App-V 4.6 と App-V 5.0 クライアントを同じコンピューターに展開する方法

**注:** App-V 4.6 がメインストリーム サポートを終了しました。 以下は、App-V 4.6 SP3 クライアントが既にインストールされていることを前提とします。

次の情報を使用して、App-V 5.0 クライアント (できれば、最新のサービス パックと修正プログラムを使用) と App-V 4.6 SP3 クライアントを同じコンピューターにインストールします。 サポートされているバージョン、要件、その他の計画情報については、「Planning for Migrating from a Previous Version [of App-V」を参照してください](planning-for-migrating-from-a-previous-version-of-app-v.md)。

**App-V 5.0 クライアントと App-V 4.6 クライアントを同じコンピューターに展開するには**

1.  App-V 4.6 バージョンのクライアントを実行しているコンピューターに App-V 5.0 SP3 クライアントをインストールします。 最適な結果を得る場合は、App-V 5.0 SP3 クライアントに利用可能なすべての更新プログラムをインストールすることをお勧めします。

2.  パッケージを徐々に変換または再シーケンスします。

    -   パッケージを変換するには、App-V 5.0 パッケージ コンバータを使用し、必要なパッケージを App-V 5.0 (**.appv**) ファイル形式に変換します。

    -   パッケージを再シーケンスするには、最新バージョンの Sequencer を使用して最適な結果を得る方法を検討してください。

    パッケージの発行の詳細については、「管理コンソールを使用してパッケージを発行する方法 [」を参照してください](how-to-publish-a-package-by-using-the-management-console-50.md)。

3.  クライアント コンピューターにパッケージを展開します。

4.  必要に応じて、拡張ポイントを変換します。 詳しくは、次のリソースを参照してください。

    -   [特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)

    -   [特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)

    -   [以前のバージョンの APP-V で作成されたパッケージを変換する方法](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)

5.  App-V 5.0 パッケージが成功したとテストし、4.6 パッケージを削除します。 クライアント コンピューターのユーザー状態を確認するには、User [Experience Virtualization](https://technet.microsoft.com/library/dn458947.aspx) または別のユーザー環境管理ツールを使用することをお勧めします。

    **App-V の提案を受け取った** ここで提案を追加または投票 [します](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)。 **App-V の問題が発生しましたか?** [App-V TechNet フォーラムを使用します](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## <a name="related-topics"></a>関連トピック


[APP-V の以前のバージョンからの移行計画](planning-for-migrating-from-a-previous-version-of-app-v.md)

[App-V 5.0 Sequencer および Client の展開](deploying-the-app-v-50-sequencer-and-client.md)

 

 





