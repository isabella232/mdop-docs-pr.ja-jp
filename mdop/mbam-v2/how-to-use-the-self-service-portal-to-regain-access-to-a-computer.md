---
title: セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法
description: セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法
author: dansimp
ms.assetid: bcf095de-0237-4bb0-b450-da8fb6d6f3d0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4abcffcf35e09bd5e24f4715a38dca74518ba29e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826077"
---
# セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法


パスワードまたは PIN を忘れてしまったか、オペレーティングシステムファイルを変更したか、BIOS またはトラステッドプラットフォームモジュール (TPM) を変更したために、エンドユーザーが BitLocker によって Windows をロックアウトしている場合は、セルフサービスポータルを使用して、ヘルプデスクに支援を求めることなく、Windows にアクセスできます。

**注** IT 管理者が IIS セッション状態のタイムアウトを構成した場合、タイムアウトの前に60秒間のメッセージが表示されます。

 

**注** これらの手順は、エンドユーザーの観点から記述されます。

 

**セルフサービスポータルを使用してコンピューターへのアクセスを回復するには**

1.  "**回復**キー id" フィールドに、コンピューターの [bitlocker 回復] 画面に表示される32桁の bitlocker キー ID のうち、最小値の8を入力します。

    **注** 最初の8桁の数字が複数のキーと一致する場合は、回復キー ID のすべての32桁を入力する必要があることを示すメッセージが表示されます。

     

2.  [**理由**] フィールドで、回復キーの要求の理由を選択します。

3.  [**キーの取得**] をクリックします。 BitLocker 回復キーが "BitLocker 回復キー" フィールドに表示されます。

4.  コンピューターの [BitLocker 回復] 画面に48桁のコードを入力して、コンピューターへのアクセスを回復します。

## 関連トピック


[MBAM での BitLocker 管理の実行](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





