---
title: UE-V 1.0 の UE-V 設定場所テンプレートの展開
description: UE-V 1.0 の UE-V 設定場所テンプレートの展開
author: dansimp
ms.assetid: 7e0cc553-14f7-40fa-828a-281c8d2d1934
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b276fb9d6c0b3749f9818483869dfe98bbc147c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827124"
---
# UE-V 1.0 の UE-V 設定場所テンプレートの展開


Microsoft User Experience Virtualization (UE-V) では、ユーザーエクスペリエンスの仮想化によってキャプチャおよび適用される設定を定義する設定場所テンプレート (XML ファイル) を使用します。 UE-V には、標準テンプレートのセット、および、カスタム設定の場所テンプレートを作成できる、UE-V Generator のツールが含まれています。 設定場所テンプレートを作成したら、テスト環境でアプリケーション設定が正しく移動されるようにテストする必要があります。 次に、エンタープライズ内のコンピューターに設定場所テンプレートを安全に展開できます。

設定場所テンプレートは、エンタープライズソフトウェア配布 (ESD)、グループポリシー設定、または UE-V 設定テンプレートカタログを使って展開できます。 ESD またはグループポリシーを使用して展開されるテンプレートは、UE-V WMI または PowerShell を使って登録する必要があります。 設定テンプレートカタログの場所に保存されているテンプレートは、UE-V agent によって自動的に登録されます。

## 設定テンプレートカタログのパスを使用して設定場所テンプレートを展開する


UE-V の設定の場所テンプレートカタログのパスは、次のメソッドを使用して定義できます。グループポリシー、エージェントインストールのコマンドラインパラメーター、WMI、または PowerShell。 テンプレートカタログのパスを定義した後、UE-V agent はこの場所から新しいまたは更新されたテンプレートを取得します。 UE-V agent は、1日に1回この場所をチェックし、このフォルダー内のテンプレートに基づいて同期動作を更新します。 前回のチェック後にこのフォルダーで追加または更新されたテンプレートは、UE-V agent によって登録されます。 UE-V agent では、このフォルダーから削除されたテンプレートの登録を解除することもできます。 テンプレートは、タスクスケジューラによって1日に登録および登録解除されます。

**設定テンプレートカタログパスを使用して UE-V 設定の場所テンプレートを展開するには**

1.  設定テンプレートカタログとして定義されている [ネットワーク共有] フォルダーに移動します。

2.  設定テンプレートカタログの設定場所テンプレートを追加、削除、または更新して、UE-V を搭載したコンピューターに必要な UE-V agent テンプレートの構成を反映させます。

3.  コンピューター上のテンプレートは、設定テンプレートカタログの変更に基づいて毎日更新されます。

4.  昇格したコマンドプロンプトを開き、 **% program file% ¥ Microsoft User Experience Virtualization \ \ agent \ \ &lt; x86 または &gt; x64**に移動して、ue-v エージェントを実行しているコンピューター上でテンプレートを手動で更新するには、 **ApplySettingsTemplateCatalog.exe**を実行します。

## 関連トピック


[Microsoft User Experience Virtualization (UE-V) 1.0](index.md)

[UE-V 1.0 の展開](deploying-ue-v-10.md)

[UE-V 1.0 を使用して同期するアプリケーションの計画](planning-which-applications-to-synchronize-with-ue-v-10.md)

 

 





