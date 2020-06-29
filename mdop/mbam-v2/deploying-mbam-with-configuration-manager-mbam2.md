---
title: Configuration Manager による MBAM の展開
description: Configuration Manager による MBAM の展開
author: dansimp
ms.assetid: 89d03e29-457a-471d-b893-e0b74a83ec50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c6cffc1cf51a26aeaa94fcb265199c19f0f34abe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823454"
---
# Configuration Manager による MBAM の展開


次の手順では、「はじめに」「[構成マネージャーでの MBAM の使用](getting-started---using-mbam-with-configuration-manager.md)」で説明されている推奨構成を使用して、Microsoft System Center Configuration manager 2007 または MicrosoftSystemCenter2012 ConfigurationManager を使用して Microsoft BitLocker 管理と監視 (mbam) を展開する方法について説明します。 推奨される構成は、1つ以上の Microsoft BitLocker 管理および監視サーバーに管理機能と監視機能をインストールし、Microsoft System Center Configuration Manager 2007 または MicrosoftSystemCenter2012 ConfigurationManager を別のサーバーにインストールすることです。

インストールを始める前に、「 [Configuration manager を使用して MBAM を展開する](planning-to-deploy-mbam-with-configuration-manager-2.md)ための計画を確認する」を参照して、mbam を configuration manager にインストールするための前提条件とハードウェアおよびソフトウェア要件を満たしていることを確認します。

Configuration Manager のトポロジで MBAM を再インストールする必要がある場合は、最初に特定の Configuration Manager オブジェクトを削除する必要があります。 詳細については、[サポート技術](https://go.microsoft.com/fwlink/?LinkId=286306)情報の記事を参照してください。

MBAM を Configuration Manager にインストールする手順は、次のカテゴリに分類されます。 各カテゴリの手順を実行して、インストールを完了します。

## mof ファイルを作成または編集する方法


MBAM Configuration Manager レポートでクライアントコンピューターが BitLocker のコンプライアンスの詳細を報告できるようにするには、**構成**マネージャーのバージョンに応じて、Sms \ _def ファイルを編集または作成する必要があります ()。

[mof ファイルを作成または編集する方法](how-to-create-or-edit-the-mof-files.md)

## Configuration Manager と共に MBAM をインストールする方法


このセクションでは、次のものをインストールするための手順について説明します。 MBAM Configuration Manager サーバーデータベースサーバー上の回復データベースと監査データベース管理/監視サーバーのサーバー機能の管理と監視を行います。

[Configuration Manager と共に MBAM をインストールする方法](how-to-install-mbam-with-configuration-manager.md)

## Configuration Manager サーバーで MBAM サーバー機能のインストールを検証する方法


Microsoft BitLocker の管理と監視のインストールが完了したら、インストールによって Configuration Manager サーバーに必要なすべての MBAM 機能が正しく設定されていることを確認します。

[Configuration Manager で MBAM のインストールを検証する方法](how-to-validate-the-mbam-installation-with-configuration-manager.md)

## 関連トピック


[MBAM と Configuration Manager の使用](using-mbam-with-configuration-manager.md)

 

 





