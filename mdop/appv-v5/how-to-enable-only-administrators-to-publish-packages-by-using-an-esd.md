---
title: ESD を使用して管理者のみが公開パッケージを有効にできるようにする方法
description: ESD を使用して管理者のみが公開パッケージを有効にできるようにする方法
author: dansimp
ms.assetid: 03367b26-83d5-4299-ad52-b9177b9cf9a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 341e86ca806c5acc736c78cf8072aab6fb4286df
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814107"
---
# ESD を使用して管理者のみが公開パッケージを有効にできるようにする方法


App-v 5.0 SP3 以降では、管理者 (エンドユーザー以外) だけがパッケージを公開または非公開にすることができるように、App-v クライアントを構成することができます。 以前のバージョンの App-v では、エンドユーザーがこれらのタスクを実行できないようにすることはできませんでした。

**管理者のみがパッケージの発行または発行を取り消すことができるようにするには**

1.  次のグループポリシーオブジェクトノードに移動します。

    **コンピューターの構成 &gt;ポリシー &gt; 管理用テンプレート &gt; システム &gt; アプリ-V の &gt; 公開**。

2.  [**管理者として発行する**] グループポリシーの設定を有効にします。

    または、PowerShell を使用してこの項目を設定するには、 [Powershell を使用してスタンドアロンコンピューターで実行されている app-v 5.0 パッケージを管理する方法](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)に関する説明を参照してください。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

 

 





