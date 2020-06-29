---
title: Management Server のインストール後のセキュリティを構成する方法
description: Management Server のインストール後のセキュリティを構成する方法
author: dansimp
ms.assetid: 71979fa6-3d0b-4a8b-994e-cb728d013090
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 521e72ead78055a7d3261664ccb75d454c22e622
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817937"
---
# Management Server のインストール後のセキュリティを構成する方法


App-v 管理コンソールを使用して証明書を追加し、セキュリティを強化するために App-v Management Server を構成します。 次の手順を使用して、セキュリティのインストール後の構成を行うことができます。

**管理サーバーのセキュリティのインストール後に構成するには**

1.  App-v 管理コンソールを開き、App-v 管理者の権限を持つ**管理サービス**に接続します。

2.  サーバーを展開し、[**サーバーグループ**] を展開して、管理サーバーが登録されている適切なサーバーグループを選びます。

3.  管理サーバーオブジェクトを右クリックし、[**プロパティ**] を選択します。

4.  [**ポート**] タブで、[**サーバー証明書**] をクリックし、ウィザードを完了して適切にプロビジョニングされた証明書を選びます。

    **注** ウィザードに証明書が表示されない場合は、証明書がプロビジョニングされていないか、証明書が App-v の要件を満たしていることを意味します。

     

5.  [**次へ**] をクリックして、[**証明書へようこそ] ウィザード**のページに進みます。

6.  [**利用可能な証明書**] 画面で適切な証明書を選択します。

7.  **[完了]** をクリックします。

8.  ウィザードが完了したら、利用可能なリッスンポートとして**RTSP**をクリアします。 これにより、セキュリティで保護されていない通信チャネルを介して接続が行われるのを防ぐことができます。

9.  [**適用**] をクリックして、 **Microsoft 仮想アプリケーションサーバー**サービスを再起動します。 このタスクを実行するには、サービスの MMC スナップインを使用します。

## 関連トピック


[Streaming Server のインストール後のセキュリティを構成する方法](how-to-configure-streaming-server-security-post-installation.md)

[証明書のアクセス許可の問題のトラブルシューティング](troubleshooting-certificate-permission-issues.md)

 

 





