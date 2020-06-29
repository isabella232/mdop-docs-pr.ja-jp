---
title: 高度なグループ ポリシーの管理のトラブルシューティング
description: 高度なグループ ポリシーの管理のトラブルシューティング
author: dansimp
ms.assetid: f7ece97c-e9f8-4b18-8c7a-a615c98d5c60
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4815378a17a7c083501cfd7772e62415ec285237
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820177"
---
# 高度なグループ ポリシーの管理のトラブルシューティング


このセクションでは、高度なグループポリシー管理 (AGPM) を使用してグループポリシーオブジェクト (Gpo) を管理するときに発生する可能性がある一般的な問題について説明します。 ここに記載されていない問題を診断するには、AGPM 管理者 (フルコントロール) でログとトレースを使用すると便利な場合があります。 詳細については、「[ログとトレースを構成する](configure-logging-and-tracing-agpm30ops.md)」を参照してください。

**注**  
-   GPO の以前のバージョンにロールバックするときに問題が発生した場合は、「[以前のバージョンの gpo にロールバックする](roll-back-to-a-previous-version-of-a-gpo-agpm30ops.md)」を参照してください。

-   バックアップから完全なアーカイブを復元して、障害から回復する方法については、「[バックアップからアーカイブを復元](restore-the-archive-from-a-backup.md)する」を参照してください。

 

## どのような問題が発生していますか?


-   [アーカイブにアクセスできません](#bkmk-access-an-archive)

-   [GPO の状態は、グループポリシーの管理者によって異なります。](#bkmk-state-varies)

-   [AGPM サーバー接続を変更できません](#bkmk-modify-archive-location)

-   [既定のテンプレートを変更できない、または Gpo の表示、作成、編集、名前の変更、展開、または削除を行うことができない](#bkmk-perform-task)

-   [特定の GPO 名を使用できない](#bkmk-use-particular-name)

-   [AGPM メール通知を受信できない](#bkmk-email)

-   [AGPM サービスでポート4600を使用できない](#bkmk-port)

-   [AGPM サービスは開始されません。](#bkmk-not-start)

-   [グループポリシーソフトウェアのインストールでソフトウェアのインストールに失敗する](#bkmk-software-installation)

-   [新しい AGPM サーバーにアーカイブを復元したときにエラーが発生しました](#bkmk-error-on-restore)

### <a href="" id="bkmk-access-an-archive"></a>アーカイブにアクセスできません

-   **原因**: アーカイブ用の正しいサーバーとポートを選択していません。

-   **解決方法**:

    -   AGPM 管理者の場合: 「 [Agpm サーバー接続を構成](configure-agpm-server-connections-agpm30ops.md)する」を参照してください。

    -   AGPM 管理者ではない場合: agpm 管理者からの AGPM サーバーの接続の詳細を要求します。 「 [AGPM サーバー接続を構成する](configure-an-agpm-server-connection-reviewer-agpm30ops.md)」をご覧ください。

-   **原因**: AGPM サービスが実行されていません。

-   **解決方法**:

    -   AGPM 管理者の場合: AGPM サービスを開始します。 詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service-agpm30ops.md)」を参照してください。

    -   AGPM 管理者ではない場合: AGPM 管理者に問い合わせてください。

### <a href="" id="bkmk-state-varies"></a>GPO の状態は、グループポリシーの管理者によって異なります。

-   **原因**: グループポリシーの管理者が、同じアーカイブに対して異なる AGPM サーバーを選択しています。

-   **解決方法**:

    -   AGPM 管理者の場合: 「 [Agpm サーバー接続を構成](configure-agpm-server-connections-agpm30ops.md)する」を参照してください。

    -   AGPM 管理者ではない場合: agpm 管理者からの AGPM サーバーの接続の詳細を要求します。 「 [AGPM サーバー接続を構成する](configure-an-agpm-server-connection-reviewer-agpm30ops.md)」をご覧ください。

### <a href="" id="bkmk-modify-archive-location"></a>AGPM サーバー接続を変更できません

-   **原因**: [ **AGPM サーバー** ] タブの設定が利用できない場合、Agpm サーバーは管理用テンプレートを使用して一元的に構成されています。

-   **解決方法**:

    -   AGPM 管理者の場合: [ **Agpm サーバー** ] タブの設定を使用できない場合は、「 [agpm サーバー接続を構成](configure-agpm-server-connections-agpm30ops.md)する」を参照してください。

    -   AGPM 管理者ではない場合: [ **Agpm サーバー** ] タブの設定を使用できない場合は、agpm サーバーを変更する必要はありません。

### <a href="" id="bkmk-perform-task"></a>既定のテンプレートを変更できない、または Gpo の表示、作成、編集、名前の変更、展開、または削除を行うことができない

-   **原因**: タスクを実行するのに必要な権限を持つ役割が割り当てられていません。

-   **解決方法**:

    -   AGPM 管理者の場合: アーカイブ[へのドメインレベルのアクセスを委任](delegate-domain-level-access-to-the-archive-agpm30ops.md)し、[アーカイブ内の個々の GPO へのアクセスを委任](delegate-access-to-an-individual-gpo-in-the-archive-agpm30ops.md)します。 AGPM 権限は、現在アーカイブ内のすべての Gpo にドメインから伝播されます。 タスクを実行できるロールと、タスクを実行するために必要な権限の詳細については、そのタスクのヘルプを参照してください。

    -   AGPM 管理者ではない場合に、追加の役割または権限が必要な場合は、AGPM 管理者に問い合わせてください。 エディターを使用している場合、GPO の作成、GPO の展開、または本番環境からの GPO の削除のプロセスを開始することはできますが、承認者または AGPM 管理者が要求を承認する必要があります。

### <a href="" id="bkmk-use-particular-name"></a>特定の GPO 名を使用できない

-   **原因**: gpo 名が既に使われているか、gpo を一覧表示する権限がありません。

-   **解決方法**:

    -   [**コントロール**]、[**非コントロール**]、または [**保留中**] タブに GPO 名が表示される場合は、別の名前を選択します。 展開された GPO の名前が変更されているが、まだ再配置されていない場合は、実稼働環境では、古い名前の下に表示されます。 そのため、古い名前はまだ使用されています。 GPO を再展開して、運用環境での名前を更新し、別の GPO で使用するためにその名前を解放します。

    -   [**コントロール**]、[**非コントロール**]、または [**保留中**] タブに gpo 名が表示されない場合は、gpo を一覧表示するアクセス許可がない可能性があります。 許可を要求するには、AGPM 管理者に問い合わせてください。

### <a href="" id="bkmk-email"></a>AGPM メール通知を受信できない

-   **原因**: 有効な SMTP メールサーバーとメールアドレスが指定されていないか、電子メール通知を生成する操作が実行されていません。

-   **解決方法**:

    -   Agpm 管理者の場合: agpm によって送信される保留中のアクションに関する電子メール通知の場合、AGPM 管理者は、[**ドメイン委任**] タブで承認者の有効な SMTP メールサーバーとメールアドレスを指定する必要があります。詳細については、「[電子メールの通知を構成する](configure-e-mail-notification-agpm30ops.md)」を参照してください。

    -   メール通知が生成されるのは、編集者、または GPO の作成、展開、または削除に必要なアクセス許可を持っていない他のグループポリシー管理者が、いずれかのアクションの要求を送信した場合にのみ生成されます。 リクエストの承認または拒否に関する自動通知はありません。

### <a href="" id="bkmk-port"></a>AGPM サービスでポート4600を使用できない

-   **原因**: 既定では、AGPM サービスがリッスンするポートは、ポート4600です。

-   **解決方法**: ポート4600が agpm サービスで利用できない場合は、agpm サーバーのポート構成を別のポートを使用するように変更してから、agpm クライアントの agpm サーバー接続でポートを更新します。 詳細については、「 [AGPM サービスを変更する](modify-the-agpm-service-agpm30ops.md)」を参照してください。

### <a href="" id="bkmk-not-start"></a>AGPM サービスは開始されません。

-   **原因**:**管理ツール**と**サービス**の下にあるオペレーティングシステムで AGPM サービスの設定を変更しました。

-   **解決策**: コントロールパネルの [**プログラムと機能**] で、 **Microsoft Advanced グループポリシー管理**の設定を変更します。 詳細については、「 [AGPM サービスを変更する](modify-the-agpm-service-agpm30ops.md)」を参照してください。

### <a href="" id="bkmk-software-installation"></a>グループポリシーソフトウェアのインストールでソフトウェアのインストールに失敗する

-   **原因**: AGPM は、グループポリシーソフトウェアインストールパッケージの整合性を維持します。 Gpo はオフラインで編集されますが、キャッシュされたクライアント情報に加えて、パッケージ間のリンクは保持されます。 これは仕様です。

-   **解決策**: AGPM を使用してオフラインで gpo を編集する場合は、チェックアウトしたコピーではなく、展開された gpo を参照するように、別の gpo 内のパッケージのグループポリシーソフトウェアのインストールアップグレードを構成します。 エディターは、展開された GPO の**読み取り**アクセス許可を持っている必要があります。

### <a href="" id="bkmk-error-on-restore"></a>新しい AGPM サーバーにアーカイブを復元したときにエラーが発生しました

-   **原因**: セキュリティ上の理由から、[ **Domain Delegation** ] タブで入力したパスワードを保護する暗号化によって、アーカイブが別のコンピューターに移動された場合、パスワードが失敗します。

-   **解決策**: [ **Domain Delegation** ] タブでパスワードを再入力して確認します。詳細については、「[電子メールの通知を構成する](configure-e-mail-notification-agpm30ops.md)」を参照してください。

 

 





