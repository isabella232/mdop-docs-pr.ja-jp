---
title: AGPM サービスがリッスンするポートを変更する
description: AGPM サービスがリッスンするポートを変更する
author: dansimp
ms.assetid: a82c6873-e916-4a04-b263-aa612cd6956b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2af79ecb9bd05acbc55083163903ae14ab44d06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820487"
---
# AGPM サービスがリッスンするポートを変更する


AGPM サービスは、セキュリティプロキシとして機能する Windows サービスであり、アーカイブと運用環境でのグループポリシーオブジェクト (Gpo) へのクライアントアクセスを管理します。 既定では、AGPM サービスはポート4600をリッスンします。 このポートを変更するには、各アーカイブの高度なグループポリシー管理 (AGPM) アーカイブインデックスファイルを変更します。

**注** AGPM サービスがリッスンするポートを変更する前に、AGPM アーカイブインデックスファイル (gpostate.xml) をバックアップすることをお勧めします。 このファイルは、高度なグループポリシー管理サーバーのインストール中にアーカイブパスとして入力されたフォルダーにあります。 既定では、このファイルの場所は、AGPM サーバー上の% CommonAppData% \\Microsoft\\AGPM\\gpostate.xml です。 どのコンピューターでアーカイブをホストしているのかがわからない場合は、アーカイブパスを変更する手順に従って、現在のアーカイブパスを表示できます。 詳細については、「[アーカイブパスを変更](modify-the-archive-path.md)する」を参照してください。

 

この手順を完了するには、AGPM サーバー (AGPM サービスがインストールされているコンピューター) とアーカイブインデックスファイルへのアクセス権を持つユーザーアカウントが必要です。

**AGPM サービスがリッスンするポートを変更するには**

1.  アーカイブをホストしているコンピューターで、アーカイブインデックスファイル (gpostate.xml) をテキストエディターで開きます。

2.  ファイルで、 **agpm: port = "4600"** を検索します。

3.  AGPM サービスがリッスンする必要があるポートに**4600**を置き換えます。次に、ファイルを保存して閉じます。

4.  AGPM サーバーで、AGPM サービスを再起動します。 (詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service.md)」を参照してください)。

5.  各グループポリシー管理者の AGPM サーバー接続のポートを変更します。 詳細については、「 [AGPM サーバー接続を構成する](configure-the-agpm-server-connection.md)」を参照してください。

6.  各アーカイブと AGPM サーバーに対してこの手順を繰り返します。

### その他の参照情報

-   [AGPM サービスの管理](managing-the-agpm-service.md)

 

 





