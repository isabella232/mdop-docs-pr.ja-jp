---
title: Microsoft Advanced Group Policy Management (AGPM) 4.0 リリース ノート
description: Microsoft Advanced Group Policy Management (AGPM) 4.0 リリース ノート
author: dansimp
ms.assetid: 44c19e61-c8e8-48aa-a2c2-20396d14d5bb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c4a279893d4da4121e422af99e7c1708a0126b4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820394"
---
# Microsoft Advanced Group Policy Management (AGPM) 4.0 リリース ノート


2009 年 10 月

## Microsoft Advanced グループポリシー管理4.0 について


Microsoft Advanced グループポリシー管理 (AGPM) 4.0 は、グループポリシー管理コンソール (GPMC) の機能を拡張します。 AGPM は、グループポリシーオブジェクト (Gpo) の包括的な変更管理と改善された管理を提供します。

次のドキュメントは、AGPM 4.0 を使い始めるときに役立ちます。

-   AGPM の機能の概要については、「 [Microsoft Advanced グループポリシー管理の概要](https://go.microsoft.com/fwlink/?LinkID=162671)(」を参照してください https://go.microsoft.com/fwlink/?LinkID=162671) 。

-   Agpm 4.0 と AGPM 3.0 との違いについては、「AGPM 4.0 () の[新機能](https://go.microsoft.com/fwlink/?LinkId=160058)」を参照してください https://go.microsoft.com/fwlink/?LinkId=160058) 。

-   使用している環境に対して AGPM 4.0、AGPM 3.0、または AGPM 2.5 が適切であるかどうかを判断する方法については、「[インストールする agpm のバージョン](https://go.microsoft.com/fwlink/?LinkId=145981)() を選択する」を参照してください https://go.microsoft.com/fwlink/?LinkId=145981) 。

-   Agpm と agpm を使用するためのサンプルシナリオのインストール方法についての基本的なガイダンスについては、「 [Microsoft Advanced Group Policy Management 4.0 () のステップバイステップガイド](https://go.microsoft.com/fwlink/?LinkID=153505)」を参照してください https://go.microsoft.com/fwlink/?LinkID=153505) 。 このガイドは、主に、評価と初回ユーザーに役立つように設計されています。

-   以前のバージョンの AGPM からアップグレードする方法や、組織での AGPM の展開を計画する方法についての詳細なガイダンスについては、 [Microsoft Advanced グループポリシー管理 4.0 () の計画ガイド](https://go.microsoft.com/fwlink/?LinkID=156883)をご覧ください https://go.microsoft.com/fwlink/?LinkID=156883) 。

-   AGPM を使って特定のタスクを実行する方法については、「高度なグループポリシー管理4.0 のヘルプ」を参照してください。これは、 [AGPM 4.0 () の操作ガイド](https://go.microsoft.com/fwlink/?LinkId=159872)として TechNet でも利用でき https://go.microsoft.com/fwlink/?LinkId=159872) ます。

## 詳細情報


AGPM の詳細については、次を参照してください。

-   [高度なグループポリシー管理の TechNet ライブラリ](https://go.microsoft.com/fwlink/?LinkID=146846)(https://go.microsoft.com/fwlink/?LinkID=146846)

-   [Microsoft デスクトップ最適化パックの TechCenter](https://go.microsoft.com/fwlink/?LinkId=159870) (https://www.microsoft.com/technet/mdop)

-   [グループポリシー TechCenter](https://go.microsoft.com/fwlink/?LinkId=145531) (https://www.microsoft.com/gp)

## フィードバックの提供


AGPM に関するフィードバックや質問は、[グループポリシーフォーラム](https://go.microsoft.com/fwlink/?LinkId=145532)() に投稿でき https://go.microsoft.com/fwlink/?LinkId=145532) ます。

## AGPM 4.0 の既知の問題


### [運用からインポート] コマンドでチェックアウトされた GPO に設定がインポートされない

運用環境で GPO を編集する場合は、オフラインアーカイブの gpo を更新するために、その gpo を運用環境からインポートする必要があります。 [**運用サイトからのインポート**] コマンドは、編集が完了する前に最終的な運用バックアップを実行できるようにすることを目的としています。これにより、必要に応じて、運用バックアップにロールバックすることができます。

[**運用からのインポート**] コマンドを実行したときに、gpo がチェックアウトされている場合、本番の変更は GPO のチェックアウトされたバージョンには反映されません。 ただし、インポートされたバージョンの GPO は、そのバージョンが編集できない場合でも、GPO の履歴に追加されます。 GPO がチェックインされると、そのバージョンはアーカイブのインポートされたバージョンに優先しますが、どちらも GPO の履歴で利用できます。

**回避策:** 運用からインポートする前に、GPO がチェックインされていることを確認します。 GPO をインポートする前にチェックインしていなかった場合は、[**チェックアウトの取り消し**] コマンドを使用して変更を破棄し、運用からインポートした gpo のバージョンにロールバックすることができます。

### 複数のサイトの Active Directory トポロジを使用している環境では、チェックアウトされている Gpo を数分編集できない

AGPM は、クライアント/サーバーモデルを使います。 AGPM サーバーと AGPM クライアントはそれぞれ、グループポリシー操作の最も近いドメインコントローラーを決定します。 AGPM クライアントを使って GPO をチェックアウトすると、実際には、オフラインアーカイブから SYSVOL フォルダーの一時フォルダーに GPO をチェックインする AGPM サーバーです。

AGPM サーバーと AGPM クライアントが別のサイトにある場合、SYSVOL の複製の待機時間のために、ローカルサイトのドメインコントローラーに、いくつかの時間、または最大30分の間、一時的にチェックアウトされた GPO が存在しないことがあります。 この状況では、チェックアウトされた GPO の SYSVOL レプリケーションが発生するまで、AGPM クライアントで GPMC を使ってチェックアウトされた GPO を編集することはできません。

**回避策:** ベストプラクティスとして、接続先の AGPM サーバーと同じサイトに AGPM クライアントを配置する必要があります。これは、チェックアウトされた GPO を編集する前に、SYSVOL のレプリケーションが実行されるのを待つ必要がないためです。

### アカウントにアーカイブへのアクセス許可が付与されていない場合、AGPM でバックアップの制限を読み取ることはできません。

AGPM クライアントで、AGPM アーカイブへの権限が委任されていないアカウントを使用してログオンする場合は、グループポリシー管理コンソール (GPMC) を起動し、[**制御の変更**] をクリックすると、次のエラーが表示されます。

``` syntax
Failed to read backup purge limit for this domain. 

The following error occurred: 
You do not have sufficient permissions to perform this operation. 
Microsoft.Agpm.AccessDeniedException (80070005)
```

**回避策:** AGPM 管理者 (フルコントロール) に連絡して、アカウントの AGPM へのアクセスを委任するように依頼します。 AGPM 管理者の場合は、AGPM 管理者ロールが割り当てられているアカウントを使用してログオンし、追加のアカウントへのアクセスを委任できるようにします。 詳細については、「AGPM ヘルプ」の「アーカイブへのドメインレベルのアクセスを委任する」を参照してください。

## リリースノートの著作権情報


このドキュメントに記載されている情報 (URL などのインターネット Web サイトへの参照を含む) は、予告なしに変更される可能性があり、情報提供のみを目的として提供されます。 このドキュメントを使用することによるすべてのリスクは、ユーザーにはとどまりません。 Microsoft Corporation は、明示的または黙示を問わず、いかなる保証も行いません。 ここで例示した会社、組織、製品、人物、イベントの例は架空のものです。 実際の会社、組織、製品、人物、またはイベントとの関係はありません。また、推定する必要があります。 お客様ご自身の責任において、適用されるすべての著作権関連法規に従ったご使用をお願いします。 このドキュメントのいかなる部分も、米国 Microsoft Corporation の書面による許諾を受けることなく、検索システムに複製、格納、導入したり、その目的を問わず、いかなる形態や手段であっても、転送することは禁じられています。ここでいう手段とは、電子的、機械的、複写、録音など、すべての手段を含みます。ただしこれは、著作権法上のお客様の権利を制限するものではありません。

Microsoft は、このドキュメントに記載されている内容に関して、特許、特許申請、商標、著作権、またはその他の知的財産権を有する場合があります。 Microsoft による使用許諾契約書によって明示的に許可されている場合を除き、このドキュメントの提供によって、これらの特許権、商標、著作権、またはその他の知的財産権のライセンスが貴社に供与されることはありません。



Microsoft、MS-DOS、Windows、WindowsServer、Windows Vista は、U.S.A. やその他の国において、マイクロソフトコーポレーションの登録商標または商標です。

ここに記載されている実際の会社と製品の名前は、各所有者の商標である場合があります。

 

 





