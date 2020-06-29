---
title: システム使用率レポート
description: システム使用率レポート
author: dansimp
ms.assetid: 4d490d15-2d1f-4f2c-99bb-0685447c0672
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe7ff547d969c63ace234104c3e6b7146da2c113
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815254"
---
# システム使用率レポート


システム使用率レポートを使用して、システムの毎日の合計使用量をグラフ化します。 このレポートを使って、Application Virtualization システムの負荷を確認できます。

このレポートでは、指定したサーバーまたはサーバーグループのレポート期間中の時間経過による使用状況を追跡します。

システム使用率レポートには、次のシステム使用状況もグラフで示します。

-   曜日による使用

-   1日の時間単位の使用

システム使用率レポートには、特定のユーザーに対するシステム全体の使用状況と合計セッション数の概要も表示されます。

レポートを作成するときに、レポートの実行時にデータを収集するために使用されるパラメーターを指定します。

レポートは自動的には実行されません。出力データを生成するには、明示的に実行する必要があります。 このレポートを実行するのにかかる時間の長さは、データストアで収集されたデータの量によって決まります。

レポートを実行し、出力が Application Virtualization Server 管理コンソールに表示されたら、次の形式でレポートをエクスポートできます。

-   Adobe Acrobat (PDF)

-   Microsoft Office Excel

**注** システムの使用状況レポートでデータを表示するには、クライアントから報告された App-v server 名が既定のサーバーグループに含まれている必要があります。 たとえば、ネットワークロードバランサー (NLB) で複数のサーバーを使用している場合、[既定のサーバー] グループに NLB クラスター名を追加する必要があります。

 

## 関連トピック


[レポートを作成する方法](how-to-create-a-reportserver.md)

[レポートを削除する方法](how-to-delete-a-reportserver.md)

[レポートをエクスポートする方法](how-to-export-a-reportserver.md)

[レポートを印刷する方法](how-to-print-a-reportserver.md)

[レポートを実行する方法](how-to-run-a-reportserver.md)

 

 





