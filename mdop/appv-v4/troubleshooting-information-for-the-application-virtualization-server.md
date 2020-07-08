---
title: Application Virtualization サーバーのトラブルシューティング情報
description: Application Virtualization サーバーのトラブルシューティング情報
author: dansimp
ms.assetid: e9d43d9b-84f2-4d1b-bb90-a13740151e0c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c98ad42a00e20900263d0598822a6381e2df1ef
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815187"
---
# Application Virtualization サーバーのトラブルシューティング情報


このトピックには、Application Virtualization (App-v) サーバーのさまざまな問題のトラブルシューティングに使用できる情報が含まれています。

## サーバーをインストールした後のセットアップログの警告メッセージ25017


インストール後、サーバーのセットアップログに次のメッセージが表示されることがあります。

*警告25017。 インストールプログラムで、サーバーの Active Directory マーカーオブジェクトを作成できませんでした。 インストールに使用したアカウントに、Active Directory または Active Directory への書き込みに必要な権限がない。*

App-v 管理またはストリーミングサーバーのインストーラーは、インストーラーを実行するために使用されたアカウントに適切な権限がある場合、サーバーがインストールされているコンピューターに対応する [Active Directory ドメインサービス (ADDS)] のコンピューターオブジェクトの下に、サービス接続ポイントエントリを作成します。 このエントリの作成に失敗しても、インストールが失敗することはありません。これは、製品の機能に影響を与えることはありません。 エラーの原因としては、インストールの実行に使用されたユーザーアカウントに、追加の書き込みに必要な権限がないことが考えられます。 アプリの追加には、ADDS でのアプリの登録は任意ですが、一元管理ツールを使用して、在庫や管理の目的でアプリ-V サーバーを見つけることができます。

## 関連トピック


[Application Virtualization サーバー](application-virtualization-server.md)

 

 





