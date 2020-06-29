---
title: バックアップからアーカイブを復元する
description: バックアップからアーカイブを復元する
author: dansimp
ms.assetid: 49666337-d72c-4e44-99e4-9eb59b2355a9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b00d2e5e612e2ac43f965e4adf6175e2fd159007
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818364"
---
# バックアップからアーカイブを復元する


障害が発生して、高度なグループポリシー管理 (AGPM) のアーカイブが破損した場合、または破棄された場合、AGPM 管理者 (フルコントロール) では、事前に準備されているバックアップコピーからアーカイブを復元することができます。また、運用環境では、アーカイブ内にないグループポリシーオブジェクト (Gpo) をインポートします アーカイブバックアップを別のサーバーに復元する方法について詳しくは、「 [AGPM サーバーとアーカイブの移動](move-the-agpm-server-and-the-archive.md)」をご覧ください。

この手順を完了するには、AGPM サーバー (AGPM サービスがインストールされているコンピューター) とアーカイブが含まれているフォルダーへのアクセス権を持つユーザーアカウントが必要です。

**バックアップからアーカイブを復元するには**

1.  AGPM サービスを停止します。 詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service-agpm30ops.md)」を参照してください。

2.  既存のアーカイブを削除します。 既定では、[アーカイブ] フォルダーは [\ programdata% ¥] と表示されますが、Microsoft Advanced グループポリシー管理をインストールした AGPM 管理者は、セットアップ時に別の場所を入力した可能性があります。

3.  アーカイブパス、AGPM サービスアカウント、アーカイブ所有者、リッスンポートを構成して、アーカイブフォルダーを再作成します。 元のインストール時に使用したものと同じ値を使用する必要はありません。 詳細については、「 [AGPM サービスを変更する](modify-the-agpm-service-agpm30ops.md)」を参照してください。

4.  アーカイブバックアップの内容を [アーカイブ] フォルダーにコピーし、サブフォルダーとファイルをコピーして、各サブフォルダーとファイルがアーカイブフォルダーのアクセス許可を継承するようにします。 [アーカイブ] フォルダーを上書きしないように注意してください。

5.  アーカイブバックアップ内の GPO が運用環境のその GPO のコピーよりも最新であるかどうかがわからない場合は、差分レポートを生成し、その設定を比較します。 詳細については、「 [gpo、gpo のバージョン、またはテンプレートの違い](identify-differences-between-gpos-gpo-versions-or-templates-agpm30ops.md)を確認する」を参照してください。

6.  AGPM サービスを再起動します。 詳細については、「 [AGPM サービスの開始と停止](start-and-stop-the-agpm-service-agpm30ops.md)」を参照してください。

### その他の参照情報

-   [アーカイブをバックアップする](back-up-the-archive.md)

-   [AGPM サーバーとアーカイブを移動する](move-the-agpm-server-and-the-archive.md)

-   [アーカイブの管理](managing-the-archive.md)

 

 





