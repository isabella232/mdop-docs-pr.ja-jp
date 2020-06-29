---
title: MED-V 1.0 SP1 アップグレードのチェックリスト
description: MED-V 1.0 SP1 アップグレードのチェックリスト
author: dansimp
ms.assetid: 1a462b37-8c7a-4826-9175-0b1b701d345b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9c418eff8dfb6146204d7d9212d42e49db000fb1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827267"
---
# MED-V 1.0 SP1 アップグレードのチェックリスト


Microsoft Enterprise デスクトップ仮想化 (MED-V) 1.0 から MED-V 1.0 Service Pack1 (SP1) にアップグレードするには、クライアントをアップグレードする必要があります。 サーバーは、必要に応じてアップグレードすることができます。

## サーバーのアップグレード


**MED-V 1.0 サーバーを MED-V 1.0 SP1 にアップグレードするには**

1.  * &lt; InstallDir &gt; /Servers/configurationserver*ディレクトリにある次のファイルをバックアップします。

    -   OrganizationalPolicy.XML

    -   ClientPolicy.XML

    -   WorkspaceKeys.XML

2.  * &lt; InstallDir &gt; /Servers/ServerSettings.xml*ファイルをバックアップします。

3.  MED-V 1.0 サーバーをアンインストールします。

4.  MED-V 1.0 SP1 サーバーをインストールします。

5.  バックアップファイルを適切なディレクトリに復元します。

6.  MED-V server サービスを再起動します。

**注** サーバーの構成が既定から変更されている場合は、ファイルが別の場所に保存されている可能性があります。

 

## クライアントアップグレード


Med-v 1.0 クライアントを MED-V 1.0 SP1 にアップグレードするには、med-v ファイルを med-v 1.0 クライアントにインストールします。 クライアントと MED-V は自動的にアップグレードされます。

 

 





