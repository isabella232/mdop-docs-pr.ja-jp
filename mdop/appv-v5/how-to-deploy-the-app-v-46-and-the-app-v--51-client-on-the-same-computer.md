---
title: 同じコンピューター上に App-v 4.6 と App-v 5.1 クライアントを展開する方法
description: 同じコンピューター上に App-v 4.6 と App-v 5.1 クライアントを展開する方法
ms.assetid: 498d50c7-f13d-4fbb-8ea1-b959ade26fdf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 354db96223e623a7cd0416cb49ad67eb4d8f7162
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814171"
---
# 同じコンピューター上に App-v 4.6 と App-v 5.1 クライアントを展開する方法

**注:** App-v 4.6 は、メインストリームサポートを終了しました。

Microsoft Application Virtualization (App-v) 5.1 クライアントをインストールするには、次の情報を使用します (推奨されるのは、最新の Service Pack およびホットフィックスを使用します)。また、同じコンピューター上の app-v 4.6 SP2 クライアントまたは app-v 4.6 S3 クライアントをインストールする場合もあります。 サポートされているバージョン、要件、およびその他の計画情報については、「[以前のバージョンの app-v からの移行を計画](planning-for-migrating-from-a-previous-version-of-app-v51.md)する」を参照してください。

**同じコンピューターに App-v 5.1 クライアントと App-v 4.6 クライアントを展開するには**

1.  App-v 4.6 を実行しているコンピューターに、次のバージョンの App-v クライアントをインストールします。

    -   [Microsoft Application Virtualization 4.6 Service Pack 3](https://www.microsoft.com/download/details.aspx?id=41187)

2.  App-v 4.6 SP3 バージョンのクライアントを実行しているコンピューターに、App-v 5.1 クライアントをインストールします。 最善の結果を得るために、利用可能なすべての更新プログラムを、App-v 5.1 クライアントにインストールすることをお勧めします。

3.  パッケージを段階的に変換または再シーケンスします。

    -   パッケージを変換するには、App-v 5.1 パッケージコンバーターを使用し、必要なパッケージを App-v 5.1 (**appv**) ファイル形式に変換します。

    -   パッケージの順序を変更するには、最善の結果を得るために、最新バージョンの Sequencer の使用を検討してください。

    パッケージの発行の詳細については、「[管理コンソールを使用してパッケージを公開する方法](how-to-publish-a-package-by-using-the-management-console-51.md)」を参照してください。

4.  クライアントコンピューターにパッケージを展開します。

5.  必要に応じて、拡張点を変換します。 詳しくは、次のリソースをご覧ください。

    -   [特定のコンピューター上の全ユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)

    -   [特定のユーザーの拡張ポイントを App-V 4.6 パッケージから変換済み App-V 5.1 パッケージに移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)

    -   [以前のバージョンの APP-V で作成されたパッケージを変換する方法](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md)

6.  App-v 5.1 パッケージが正常に処理されたことをテストし、4.6 パッケージを削除します。 クライアントコンピューターのユーザーの状態を確認するには、[ユーザーエクスペリエンスの仮想化](https://technet.microsoft.com/library/dn458947.aspx)または他のユーザー環境管理ツールを使用することをお勧めします。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V の以前のバージョンからの移行計画](planning-for-migrating-from-a-previous-version-of-app-v51.md)

[App-V 5.1 Sequencer および Client の展開](deploying-the-app-v-51-sequencer-and-client.md)

 

 





