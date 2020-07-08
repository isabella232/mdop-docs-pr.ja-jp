---
title: AGPM サービスを開始および停止する
description: AGPM サービスを開始および停止する
author: dansimp
ms.assetid: b9d26920-c439-4992-9a78-73e4fba8309d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2be1c2386bedd5888c0ed032479bf1237ce8289c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820217"
---
# AGPM サービスを開始および停止する


AGPM サービスは、セキュリティプロキシとして機能する Windows サービスであり、アーカイブと運用環境でのグループポリシーオブジェクト (Gpo) へのクライアントアクセスを管理します。

**重要** AGPM サービスを停止または無効にすると、AGPM クライアントがサーバー経由で Gpo の一覧表示や編集などの操作を実行できなくなります。

 

この手順を完了するには、AGPM サーバー (AGPM サービスがインストールされているコンピューター) へのアクセス権を持つユーザーアカウントが必要です。

**AGPM サービスを開始または停止するには**

1.  Microsoft Advanced グループポリシー管理サーバー (つまり、AGPM サービス) がインストールされているコンピューターで、[**スタート**] をクリックし、[**コントロールパネル**] をクリックして、[**管理ツール**] をクリックし、[**サービス**] をクリックします。

2.  サービスの一覧で、[ **AGPM サービス**] を右クリックし、[**開始**]、[**再起動**]、または [**停止**] を選択します。

    **注意** AGPM サービスの設定は、オペレーティングシステムの**管理ツール**と**サービス**を使って変更しないでください。 これにより、AGPM サービスが開始されないようにすることができます。

     

### その他の参照情報

-   [AGPM サービスの管理](managing-the-agpm-service-agpm30ops.md)

 

 





