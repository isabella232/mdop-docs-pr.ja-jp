---
title: セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法
description: セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法
author: dansimp
ms.assetid: 3c24b13a-d1b1-4763-8ac0-0b2db46267e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cde9c71a957a5270d69aa8388455895f1cb2432b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826704"
---
# セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法


セルフサービスポータルは、IT 管理者が Microsoft BitLocker の管理と監視 (MBAM) 2.5 の展開の一部として構成した web サイトです。 この web サイトでは、エンドユーザーが Windows をロックした状態で、自分のコンピューターに個別にアクセスできるようにします。 セルフサービスポータルでは、ヘルプデスクスタッフの支援は必要ありません。

次の手順は、エンドユーザーの観点から記述されていますが、IT 管理者が理解している場合に役立つ可能性があります。

**重要** エンドユーザーは、セルフサービスポータルを使用してキーを回復するために、少なくとも1回は (リモートではなく) コンピューターに物理的にログオンしている必要があります。 それ以外の場合は、ヘルプデスクポータルを使用してキーの回復を行う必要があります。

 

エンドユーザーが次の場合に、ロックアウトが発生する可能性があります。

-   パスワードまたは PIN を忘れた場合

-   オペレーティングシステムのファイル、BIOS、またはトラステッドプラットフォームモジュール (TPM) を変更する

**注** IT 管理者が IIS セッション状態のタイムアウトを構成した場合、タイムアウトの前に、セルフサービスポータルの60秒間にメッセージが表示されます。

 

**セルフサービスポータルを使用してコンピューターへのアクセスを回復するには**

1.  "**回復**キー id" フィールドに、コンピューターの [bitlocker 回復] 画面に表示される32桁の bitlocker キー ID のうち、最小値の8を入力します。 最初の8桁の数字が複数のキーと一致する場合は、回復キー ID のすべての32桁を入力する必要があることを示すメッセージが表示されます。

2.  [**理由**] フィールドで、回復キーの要求の理由を選択します。

3.  [**キーの取得**] をクリックします。 Bitlocker 回復キーが [ **Bitlocker 回復キー** ] フィールドに表示されます。

4.  コンピューターの [BitLocker 回復] 画面に48桁のコードを入力して、コンピューターへのアクセスを回復します。



## 関連トピック


[MBAM 2.5 での BitLocker 管理の実行](performing-bitlocker-management-with-mbam-25.md)

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。
 





