---
title: 管理コンソールを使用してパッケージを公開する方法
description: 管理コンソールを使用してパッケージを公開する方法
author: dansimp
ms.assetid: e34d2bcf-15ac-4a75-9dc8-79380b36a25f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b0783a05f658da5e93603e26dc7e9581d26b81f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813770"
---
# 管理コンソールを使用してパッケージを公開する方法


次の手順を使用して、App-v 5.1 パッケージを公開します。 パッケージを公開すると、App-v 5.1 クライアントを実行しているコンピューターでは、そのパッケージ内のアプリケーションにアクセスして実行できます。

**注** 管理者のみがパッケージを公開または非公開にする機能を有効にする機能 (以下で説明) は、App-v 5.0 SP3 以降でサポートされています。

 

**App-v 5.1 パッケージを発行するには**

1.  App V 5.1 管理コンソールで、 公開するパッケージの名前をクリックまたは右クリックします。 **[公開]** を選びます。

2.  [**状態**] 列を確認して、パッケージが公開されていることを確認し、使用できるようになりました。 パッケージが使用可能な場合は、[**発行済み**] 状態が表示されます。

    パッケージが正常に公開されていない場合は、[**非公開**] という状態が表示され、パッケージが使用できない理由を説明するエラーテキストが表示されます。

**管理者のみがパッケージの発行または発行を取り消すことができるようにするには**

1.  次のグループポリシーオブジェクトノードに移動します。

    **コンピューターの構成 &gt;ポリシー &gt; 管理用テンプレート &gt; システム &gt; アプリ-V の &gt; 公開**。

2.  [**管理者として発行する**] グループポリシーの設定を有効にします。

    または、PowerShell を使用してこの項目を設定するには、 [Powershell を使用してスタンドアロンコンピューターで実行されている app-v 5.1 パッケージを管理する方法](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)に関する説明を参照してください。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.1 の操作](operations-for-app-v-51.md)

[管理コンソールを使用してパッケージへのアクセスを構成する方法](how-to-configure-access-to-packages-by-using-the-management-console-51.md)

 

 





