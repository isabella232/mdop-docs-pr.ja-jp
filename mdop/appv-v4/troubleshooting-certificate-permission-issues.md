---
title: 証明書のアクセス許可の問題のトラブルシューティング
description: 証明書のアクセス許可の問題のトラブルシューティング
author: dansimp
ms.assetid: 06b8cbbc-93fd-44aa-af39-2d780792d3c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 728c35b9f51c8f2e18db8acd63708c70bb5d3100
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815207"
---
# 証明書のアクセス許可の問題のトラブルシューティング


App-v 4.5 をインストールした後、秘密キーがネットワークサービス用の適切な ACL で構成されていない場合、イベントが NT イベントログに記録され、エントリがファイルに格納され `Sft-server.log` ます。

## エラーメッセージ


### Windows Server2003

イベント ID 36870 — SSL サーバー資格情報の秘密キーにアクセスしようとしたときに重大なエラーが発生しました。 暗号化モジュールから返されるエラーコードは0x80090016 です。

### Windows Server2008

イベント ID 36870 — SSL サーバー資格情報の秘密キーにアクセスしようとしたときに重大なエラーが発生しました。 暗号化モジュールから返されるエラーコードは0x8009030d です。

## Sft-server


ディレクトリにあるファイルには、次のエラーが表示され `sft-server.log` `%ProgramFiles%\Microsoft System Center App Virt Management Server\App Virt Management Server\logs` ます。

証明書を読み込めませんでした。 エラーコード \ [-2146893043 \]。 ネットワークサービスアカウントに、証明書とそれに対応する秘密キーファイルへの適切なアクセス権があることを確認します。

 

 





