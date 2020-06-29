---
title: Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件
description: Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件
author: dansimp
ms.assetid: 74180d8d-7b0f-460f-b301-53595cde8381
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dd9b89e1a1383997d6ebc92f8e034fbf2945823f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812563"
---
# Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件


System Center Configuration Manager の統合機能を使用して Microsoft BitLocker 管理および監視 (MBAM) 2.5 をインストールしている場合は、このトピックで説明されている前提条件と、[スタンドアロンおよび Configuration manager の統合トポロジに関する Mbam 2.5 サーバーの前提条件](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)に加えて、このトピックで説明する前提条件を完了する必要があります。 また、構成マネージャーの統合トポロジに必要な .mof ファイルを作成または変更する必要があります。

## Configuration Manager 統合機能の前提条件


System Center Configuration Manager の統合トポロジで MBAM を構成する場合は、構成マネージャーに必要なその他の前提条件を完了する必要があります。

[Configuration Manager 統合機能の前提条件](prerequisites-for-the-configuration-manager-integration-feature.md)

## 構成の .mof ファイルを編集する


MBAM Configuration Manager レポートでクライアントコンピューターが BitLocker のコンプライアンスの詳細を報告できるようにするには、SystemCenter2012 ConfigurationManager と Microsoft System Center Configuration Manager 2007 用の構成の .mof ファイルを編集する必要があります。

[Configuration.mof ファイルを編集する](edit-the-configurationmof-file-mbam-25.md)

## <a href="" id="create-or-edit-the-sms-def-mof-file"></a>Sms \ _def ファイルを作成または編集する


MBAM Configuration Manager のレポートでクライアントコンピューターが BitLocker の準拠の詳細を報告できるようにするには、Sms \ _def .mof ファイルを作成または編集する必要があります。 SystemCenter2012 ConfigurationManager を使用している場合は、ファイルを作成する必要があります。 Configuration Manager 2007 では、ファイルが既に存在するため、既存のファイルを編集することはできますが、上書きする必要はありません。

[Sms \ _def ファイルを作成または編集する](create-or-edit-the-sms-defmof-file-mbam-25.md)


## 関連トピック


[MBAM 2.5 に対応する環境の準備](preparing-your-environment-for-mbam-25.md)

[MBAM 2.5 がサポートされる構成](mbam-25-supported-configurations.md)

[MBAM 2.5 の展開計画](planning-to-deploy-mbam-25.md)

 

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。




