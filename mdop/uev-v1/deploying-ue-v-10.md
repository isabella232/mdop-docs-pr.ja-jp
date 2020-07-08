---
title: UE-V 1.0 の展開
description: UE-V 1.0 の展開
author: dansimp
ms.assetid: 519598bb-8c81-4af7-bee7-357696bff880
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1a1c515f9be950d8ca7b0a199344d34f7852073d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827147"
---
# UE-V 1.0 の展開


Microsoft User Experience Virtualization (UE-V) でサポートされている展開構成は多数あります。 このセクションでは、展開のさまざまな段階で完了する必要があるタスクを正常に実行するための一般的な情報と段階的な手順について説明します。

## UE-V の展開情報


UE-V の展開では、ネットワーク共有上の設定の保存場所と、設定を同期するすべてのコンピューターに UE-V エージェントがインストールされている必要があります。 UE-V のグループポリシーテンプレートを使用して、UE-V の設定を管理できます。 次のトピックでは、これらの機能を展開する方法について説明します。

[UE-V 1.0 の設定の保存場所の展開](deploying-the-settings-storage-location-for-ue-v-10.md)

すべての UE-V 展開では、同期された設定値を含む設定パッケージが配置されている設定の保存場所が必要です。

[UE-V エージェントの展開](deploying-the-ue-v-agent.md)

UE-V を使用して設定を同期するには、コンピューターで UE-V エージェントをインストールして実行している必要があります。

[UE-V グループ ポリシー ADMX テンプレートのインストール](installing-the-ue-v-group-policy-admx-templates.md)

UE-V の構成および標準の UE-V 構成を展開する前に、グループポリシーを使って UE-V の設定を事前に構成することができます。

## カスタムテンプレートの展開に関する展開情報


基幹業務アプリケーションなど、UE-V に含まれている Microsoft アプリケーション以外のアプリケーションのカスタム設定場所テンプレートの作成を計画している場合は、設定テンプレートカタログを展開することができます。これらのテンプレートを作成するには、UE-V Generator をインストールする必要があります。 詳細については、「 [ue-v 1.0 向けのカスタムテンプレートの展開を計画](planning-for-custom-template-deployment-for-ue-v-10.md)する」を参照してください。

[UE-V Generator のインストール](installing-the-ue-v-generator.md)

UE-V Generator を使って、既定のアプリケーション以外のアプリケーションの設定を同期できるように、カスタム設定の場所テンプレートを作成、編集、検証します。

[UE-V 1.0 の設定テンプレート カタログの展開](deploying-the-settings-template-catalog-for-ue-v-10.md)

UE-V Agent の既定のアプリケーション以外のアプリケーションをサポートするためにカスタム設定の場所テンプレートを展開する必要がある場合は、設定テンプレートカタログを構成して保存する必要があります。

[UE-V 1.0 の UE-V 設定場所テンプレートの展開](deploying-ue-v-settings-location-templates-for-ue-v-10.md)

UE-V Agent で既定のアプリケーション以外のアプリケーションを同期する必要がある場合は、UE-V Generator を使用して作成されたカスタム設定の場所テンプレートを、UE-V 設定テンプレートカタログに配布できます。

**注** カスタムテンプレートを展開するには、設定テンプレートカタログが必要です。 既定の Microsoft アプリケーションテンプレートは、UE-V エージェントと共に展開されます。

 

## この製品のトピック


[Microsoft User Experience Virtualization (UE-V) 1.0](index.md)

[User Experience Virtualization 1.0 の概要](getting-started-with-user-experience-virtualization-10.md)

[UE-V 1.0 の計画](planning-for-ue-v-10.md)

[UE-V 1.0 の操作](operations-for-ue-v-10.md)

[UE-V 1.0 のトラブルシューティング](troubleshooting-ue-v-10.md)

 

 





