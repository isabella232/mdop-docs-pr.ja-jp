---
title: UE-V 1.0 のカスタム テンプレートの展開計画
description: UE-V 1.0 のカスタム テンプレートの展開計画
author: dansimp
ms.assetid: be76fc9a-31ca-4290-af11-7640dcb87d50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5d17f058bff452f88003ab4488daa7afa846f688
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821194"
---
# UE-V 1.0 のカスタム テンプレートの展開計画


Microsoft User Experience Virtualization (UE-V) では、UE-V でキャプチャおよび適用される設定を定義する設定場所テンプレート (XML ファイル) が使用されます。 UE-V Generator を使って、既定の UE-V テンプレートに含まれているアプリケーション以外のアプリケーションの設定をユーザーがローミングできるように、カスタム設定の場所テンプレートを作成できます。 カスタムテンプレートをテストして、アプリケーションの設定がテスト環境で正しくローミングされていることを確認したら、これらの設定場所テンプレートをエンタープライズ内のコンピューターに展開することができます。

カスタム設定の場所テンプレートは、エンタープライズソフトウェア配布 (ESD) などの既存の展開インフラストラクチャと共に、グループポリシーの基本設定を使って、または UE-V 設定テンプレートカタログを構成することによって展開できます。 ESD またはグループポリシーを使用して展開されるテンプレートは、UE-V WMI または PowerShell で登録する必要があります。

## 設定テンプレートカタログ


ユーザーエクスペリエンスの仮想化設定テンプレートカタログは、カスタム設定の場所テンプレートをすべて保存する、UE-V のコンピューター上のフォルダーパスまたはサーバーメッセージブロック (SMB) ネットワーク共有です。 UE-V agent は、新しいまたは更新されたテンプレートをこの場所から取得します。 UE-V agent は、1日に1回この場所をチェックし、このフォルダー内のテンプレートに基づいて同期動作を更新します。 前回フォルダーがチェックされてからこのフォルダーに追加または更新されたテンプレートは、UE-V agent によって登録されます。 UE-V agent deregisters テンプレートはこのフォルダーから削除されます。 既定では、テンプレートは1日に1回、午前3:30 時に登録および登録解除されます。 タスクスケジューラによるローカル時刻。 UE-V のタスクの詳細については、「 [ue-v のスケジュールされたタスクの頻度を変更する](changing-the-frequency-of-ue-v-scheduled-tasks.md)」を参照してください。

[Install] コマンドラインオプション、グループポリシー、WMI、または PowerShell を使用して、設定テンプレートカタログのパスを構成できます。 設定テンプレートカタログパスに保存されているテンプレートは、スケジュールされたタスクによって自動的に登録および登録解除されます。 必要に応じて、このスケジュールされたタスクをカスタマイズできます。

## 既定の Microsoft テンプレートを置き換える


UE-V agent は、一般的な Microsoft アプリケーションと Windows 設定用の設定場所テンプレートの既定のグループをインストールします。 エンタープライズでこれらのテンプレートのカスタマイズバージョンが必要な場合、UE-V agent は設定テンプレートカタログを使用するように構成することができます。次に、既定の Microsoft テンプレートを置き換える必要があります。

UE-V agent のインストール中に、コマンドラインパラメーターを使用して、 `RegisterMSTemplates` 既定の Microsoft テンプレートの登録を無効にすることができます。 UE-V パラメーターの設定方法の詳細については、「 [Ue-v 構成メソッドの計画](planning-for-ue-v-configuration-methods.md)」を参照してください。

グループポリシーを使用して設定テンプレートカタログのパスを構成する場合は、既定の Microsoft テンプレートを置き換えるかどうかを選ぶことができます。 既定の Microsoft テンプレートを置き換えるようにポリシー設定を構成した場合、UE-V agent によってインストールされたすべての既定の Microsoft テンプレートはコンピューターから削除され、設定テンプレートカタログに含まれているテンプレートのみが使用されます。 既定の Microsoft テンプレートを上書きするには、UE-V Agent 構成設定を `RegisterMSTemplates` true に設定する必要があります。

**注** 有効にした後にこのポリシー設定を無効にした場合、UE-V agent では既定の Microsoft テンプレートは復元されません。

 

既定の Microsoft テンプレートと同じ ID を使用するように設定テンプレートカタログにカスタマイズされたテンプレートがあり、UE-V agent が既定の Microsoft テンプレートと置き換えるように構成されていない場合、カタログ内の Microsoft テンプレートは無視されます。

また、UE-V PowerShell 機能を使用して、既定のテンプレートを置き換えることもできます。 既定の Microsoft テンプレートを PowerShell で置き換えるには、既定の Microsoft テンプレートの登録を解除し、カスタマイズされたテンプレートを登録します。

**注** 新しい設定テンプレートがアプリケーションに展開されている場合でも、古い設定パッケージは設定の保存場所に残ります。 これらのパッケージはエージェントによって読み取られることはありませんが、自動的に削除されることはありません。

 

## 関連トピック


[UE-V 1.0 の計画](planning-for-ue-v-10.md)

[UE-V 1.0 を使用して同期するアプリケーションの計画](planning-which-applications-to-synchronize-with-ue-v-10.md)

[UE-V の構成方法の計画](planning-for-ue-v-configuration-methods.md)

カスタムテンプレートの展開を計画する
 

 





