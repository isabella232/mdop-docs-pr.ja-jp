---
title: AGPM サーバーとアーカイブを移動する
description: AGPM サーバーとアーカイブを移動する
author: dansimp
ms.assetid: 9ec48d3a-c293-45f0-8939-32ccdc062303
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 61ad2eb6e0ea46eef89379894a99469254e0fd5e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822534"
---
# AGPM サーバーとアーカイブを移動する


AGPM サーバーとアーカイブがホストされているサーバーを置き換える場合は、AGPM サービスとアーカイブを移動する必要があります。 必要に応じて、AGPM サービスとアーカイブを個別に移動することができます。

**注**  
-   AGPM サーバーは、AGPM サービスと Microsoft Advanced Group Policy Management – Server がインストールされているコンピューターをホストするコンピューターです。

-   既定では、アーカイブは AGPM サーバー上でホストされますが、代わりに別のサーバーでホストするためのアーカイブパスを指定できます。

 

この手順を完了するには、Domain Admins グループのメンバーで、前の AGPM サーバーにアクセスできるユーザーアカウントが必要です。 さらに、この手順を完了するために、新しい AGPM サーバーで使用される AGPM サービスアカウントの資格情報を提供する必要があります。

**AGPM サービスとアーカイブを別のサーバーまたはサーバーに移動するには**

1.  アーカイブをバックアップします。 詳細については、「[アーカイブのバックアップを作成](back-up-the-archive-agpm40.md)する」を参照してください。

2.  AGPM サービスを移動します。

    1.  AGPM サービスを停止します。 詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service-agpm40.md)」を参照してください。

    2.  AGPM サービスをホストする新しいサーバーに Microsoft Advanced グループポリシー管理-Server をインストールします。 このプロセスでは、AGPM サーバーに対して、アーカイブの場所として新しいアーカイブパスを指定します。 詳細については、「 [Microsoft Advanced グループポリシー管理4.0 のステップバイステップガイド](https://go.microsoft.com/fwlink/?LinkId=153505)」 https://go.microsoft.com/fwlink/?LinkId=153505) ( [microsoft advanced group policy](https://go.microsoft.com/fwlink/?LinkId=156883) Management () の計画ガイド () を参照してください https://go.microsoft.com/fwlink/?LinkId=156883) 。

    3.  AGPM 管理者 (フルコントロール) は、新しい AGPM サーバーを使用するすべてのグループポリシー管理者に対して AGPM サーバー接続を構成し、古い AGPM サーバーへの接続を削除する必要があります。それ以外の場合、各グループポリシー管理者は、新しい AGPM サーバー接続を手動で構成し、コンピューター上の AGPM スナップインの古い AGPM サーバー接続を削除 詳細については、「 [AGPM サーバー接続を構成する](configure-agpm-server-connections-agpm40.md)」を参照してください。

        **注** ベストプラクティスとして、前の AGPM サーバーから Microsoft Advanced グループポリシー管理– Server をアンインストールする必要があります。 これにより、サーバー上で AGPM サービスが意図せずに再起動されることはなくなり、AGPM サーバーとの接続が残っている場合は混乱を招く可能性があります。

         

3.  アーカイブをホストする新しいサーバーにバックアップからアーカイブをコピーします。 詳細については、「[バックアップからアーカイブを復元する](restore-the-archive-from-a-backup-agpm40.md)」を参照してください。

    **重要** AGPM サービスを同時に移行せずに、アーカイブを移動した場合は、次の操作を行います。

    1.  AGPM サーバーに関連するアーカイブの新しい場所を指すようにアーカイブパスを変更する必要があります。 詳細については、「 [AGPM サービスを変更する](modify-the-agpm-service-agpm40.md)」を参照してください。

    2.  [ **Domain Delegation** ] タブでパスワードを再入力して確認する必要があります。詳細については、「[電子メールの通知を構成する](configure-e-mail-notification-agpm40.md)」を参照してください。

     

### その他の参照情報

-   [アーカイブをバックアップする](back-up-the-archive-agpm40.md)

-   [バックアップからアーカイブを復元する](restore-the-archive-from-a-backup-agpm40.md)

-   [AGPM サーバー接続を構成する](configure-agpm-server-connections-agpm40.md)

-   [AGPM サービスを変更する](modify-the-agpm-service-agpm40.md)

-   [Microsoft Advanced グループポリシー管理4.0 のステップバイステップガイド](https://go.microsoft.com/fwlink/?LinkId=153505)(https://go.microsoft.com/fwlink/?LinkId=153505)

-   [Microsoft Advanced グループポリシー管理の計画ガイド](https://go.microsoft.com/fwlink/?LinkId=156883)(https://go.microsoft.com/fwlink/?LinkId=156883)

-   [AGPM 管理者タスクの実行](performing-agpm-administrator-tasks-agpm40.md)

 

 





