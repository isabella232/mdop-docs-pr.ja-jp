---
title: mof ファイルを作成または編集する方法
description: mof ファイルを作成または編集する方法
author: dansimp
ms.assetid: 4d19d707-b90f-4057-a6e9-e4221a607190
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5f59e9133dd25ecf45d16a5cb704d6ea00923d9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825324"
---
# mof ファイルを作成または編集する方法


構成マネージャーを使用して Microsoft BitLocker 管理と監視 (MBAM) をインストールするには、構成の .mof ファイルを編集する必要があります。 また、使用している Configuration Manager のバージョンに応じて、Sms \ _def ファイルを編集するか作成する必要があります。

## Configuration.mof ファイルを編集する


MBAM Configuration Manager レポートでクライアントコンピューターが BitLocker のコンプライアンスの詳細を報告できるようにするには、Microsoft System Center Configuration Manager 2007 と SystemCenter2012 ConfigurationManager の構成の .mof ファイルを編集する必要があります。

[Configuration.mof ファイルを編集する](edit-the-configurationmof-file.md)

## <a href="" id="create-or-edit-the-sms-def-mof-file"></a>Sms \ _def ファイルを作成または編集する


MBAM Configuration Manager のレポートでクライアントコンピューターが BitLocker の準拠の詳細を報告できるようにするには、Sms \ _def .mof ファイルを作成または編集する必要があります。 Configuration Manager 2007 では、ファイルが既に存在するため、既存のファイルを編集することはできますが、上書きする必要はありません。 SystemCenter2012 ConfigurationManager を使用している場合は、ファイルを作成する必要があります。

[Sms \ _def ファイルを作成または編集する](create-or-edit-the-sms-defmof-file.md)

## 関連トピック


[Configuration Manager による MBAM の展開](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





