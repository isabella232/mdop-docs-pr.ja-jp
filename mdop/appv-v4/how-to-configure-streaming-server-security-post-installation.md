---
title: Streaming Server のインストール後のセキュリティを構成する方法
description: Streaming Server のインストール後のセキュリティを構成する方法
author: dansimp
ms.assetid: 9bde3677-d1aa-4dcc-904e-bb49a268d748
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e1945b38da5dd50c0bd2fb0c741bd92012e78586
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817904"
---
# Streaming Server のインストール後のセキュリティを構成する方法


レジストリを使用してセキュリティを強化するように、App-v ストリーミングサーバーを構成します。 App-v 管理サーバーの場合と同様に、証明書は、次のインストール後の手順を完了する前に、サーバー認証用の正しい EKU 識別子を使用して適切にプロビジョニングされる必要があります。

**ストリーミングサーバーのセキュリティのインストール後に構成するには**

1.  MMC を作成して、**証明書**スナップインを追加し、[**ローカルコンピューター証明書ストア**] を選びます。

2.  コンピューターの**個人**証明書を開き、app-v 用にプロビジョニングされた証明書を開きます。

3.  [**詳細**] タブで、拇印までスクロールダウンし、[詳細] ウィンドウでハッシュをコピーします。

4.  レジストリエディターを開き、に移動し `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server` ます。

5.  `X509CertHash`値を編集し、[値] フィールドに拇印ハッシュを貼り付けて、すべてのスペースを削除します。 [ **OK]** をクリックして編集を承諾します。

6.  レジストリエディターで、に移動 `HKLM\Software\Microsoft\SoftGrid\4.5\Distribution server\RtspsPorts` します。

7.  "322" という名前の新しい**DWORD**値を作成し、その10進数を322または142として16進数値として入力します。

8.  ストリーミングサービスを再起動します。

## 関連トピック


[Management Server のインストール後のセキュリティを構成する方法](how-to-configure-management-server-security-post-installation.md)

[証明書のアクセス許可の問題のトラブルシューティング](troubleshooting-certificate-permission-issues.md)

 

 





