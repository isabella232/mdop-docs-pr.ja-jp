---
title: 同じコンピューター上に App-v 4.6 と App-v 5.0 クライアントを展開する方法
description: 同じコンピューター上に App-v 4.6 と App-v 5.0 クライアントを展開する方法
ms.assetid: 5b7e27e4-4360-464c-b832-f1c7939e5485
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.date: 06/21/2016
ms.openlocfilehash: 38e77ce6ce6c0dba7c67f6c0dfa5c9e263e07e20
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814179"
---
# 同じコンピューター上に App-v 4.6 と App-v 5.0 クライアントを展開する方法

**注:** App-v 4.6 は、メインストリームサポートを終了しました。 次の例は、App-v 4.6 SP3 クライアントが既にインストールされていることを前提としています。

次の情報を使用して、App-v 5.0 クライアント (お勧めの、最新の Service Pack と修正プログラムを含む) と、同じコンピューター上の App-v 4.6 SP3 クライアントをインストールします。 サポートされているバージョン、要件、およびその他の計画情報については、「[以前のバージョンの app-v からの移行を計画](planning-for-migrating-from-a-previous-version-of-app-v.md)する」を参照してください。

**同じコンピューターに App-v 5.0 クライアントと App-v 4.6 クライアントを展開するには**

1.  App-v 4.6 バージョンのクライアントが実行されているコンピューターに、App-v 5.0 SP3 クライアントをインストールします。 最善の結果を得るために、利用可能なすべての更新プログラムを、App-v 5.0 SP3 クライアントにインストールすることをお勧めします。

2.  パッケージを段階的に変換または再シーケンスします。

    -   パッケージを変換するには、App-v 5.0 パッケージコンバーターを使用し、必要なパッケージを App-v 5.0 (**appv**) ファイル形式に変換します。

    -   パッケージの順序を変更するには、最善の結果を得るために、最新バージョンの Sequencer の使用を検討してください。

    パッケージの発行の詳細については、「[管理コンソールを使用してパッケージを公開する方法](how-to-publish-a-package-by-using-the-management-console-50.md)」を参照してください。

3.  クライアントコンピューターにパッケージを展開します。

4.  必要に応じて、拡張点を変換します。 詳しくは、次のリソースをご覧ください。

    -   [特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)

    -   [特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.0 パッケージに移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)

    -   [以前のバージョンの APP-V で作成されたパッケージを変換する方法](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)

5.  App-v 5.0 パッケージが正常に処理されたことをテストし、4.6 パッケージを削除します。 クライアントコンピューターのユーザーの状態を確認するには、[ユーザーエクスペリエンスの仮想化](https://technet.microsoft.com/library/dn458947.aspx)または他のユーザー環境管理ツールを使用することをお勧めします。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V の以前のバージョンからの移行計画](planning-for-migrating-from-a-previous-version-of-app-v.md)

[App-V 5.0 Sequencer および Client の展開](deploying-the-app-v-50-sequencer-and-client.md)

 

 





