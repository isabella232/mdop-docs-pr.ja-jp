---
title: AGPM の技術概要
description: AGPM の技術概要
author: dansimp
ms.assetid: 36bc0ab5-f752-474c-8559-721ea95169c2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0cc635f46c2aabb0c9fa1f472a258a3e65a07b55
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818297"
---
# AGPM の技術概要


Microsoft Advanced グループポリシー管理 (AGPM) は、クライアント/サーバーアプリケーションです。 AGPM サーバーは、サーバーのファイルシステムで作成されたアーカイブに、グループポリシーオブジェクト (Gpo) をオフラインで保存します。 グループポリシー管理者は、グループポリシー管理コンソール (GPMC) 用の AGPM スナップインを使用して、アーカイブをホストしているサーバー上の Gpo を操作します。 AGPM と関連アイテムの要素、ファイルシステムへの Gpo の格納方法、および各ユーザーロールで利用可能なアクセス許可を制御することによって、AGPM によるグループポリシー管理者の効率性を向上させることができます。

## 用語


次に、基本的な AGPM 用語について説明します。

-   **AGPM クライアント:** グループポリシー管理コンソール (GPMC) で AGPM スナップインを実行し、グループポリシー管理者が Gpo を管理するコンピューター。

-   **AGPM スナップイン:** AGPM クライアントにインストールされている AGPM のソフトウェアコンポーネントであり、Gpo を管理できるようにします。

-   **AGPM サーバー:** AGPM サービスを実行してアーカイブを管理するサーバー。 各 AGPM サーバーは1つのアーカイブしか管理できませんが、1つの AGPM サーバーは1つのアーカイブの複数のドメインのアーカイブデータを管理できます。 アーカイブは、AGPM サーバー以外のコンピューターでホストすることができます。

-   **AGPM サービス:** サービスとして AGPM サーバー上で実行される AGPM のソフトウェアコンポーネントです。 このサービスは、アーカイブおよびそのフォレストの運用環境での Gpo を管理します。

-   **アーカイブ:** AGPM では、関連付けられている AGPM サーバーが管理している Gpo を含む、各 Gpo の履歴に加えて、それらの管理された Gpo を含む中央ストアです。 これには、各 GPO の以前の制御バージョンがすべて含まれます。 アーカイブは、アーカイブインデックスファイルと関連アーカイブデータで構成され、複数のドメインに Gpo のデータが含まれる場合があります。 アーカイブは、AGPM サーバー以外のコンピューターでホストすることができます。

-   制御された**GPO:** AGPM によって管理されている GPO。 AGPM は、アーカイブに保存される、管理された Gpo の履歴と権限を管理します。

-   **非制御 GPO:** ドメインの運用環境での GPO であり、AGPM で管理されません。

## AGPM のインストール、作成、および影響


AGPM サーバーでは、AGPM セットアッププログラムは AGPM サービスをインストールします。 AGPM では、Active Directory®ディレクトリサービスまたはスキーマは変更されません。 既定では、AGPM サーバープログラムファイルは、% program files% ¥にインストールされています。 必要に応じて、AGPM サービスをドメインコントローラーにインストールできます。ただし、メンバーサーバーに AGPM サービスをインストールすることをお勧めします。

AGPM クライアントでは、AGPM セットアッププログラムは、AGPM スナップインをインストールし、GPMC に表示される各ドメインに**変更制御**フォルダーを追加します。 既定では、AGPM クライアントプログラムファイルは、% program files% ¥ \ agpm¥にインストールされます。

表1では、AGPM によってインストールまたは作成される項目、および AGPM 操作に影響を与えるオペレーティングシステムの部分について説明します。

**表 1: AGPM によってインストール、作成、または影響を受ける項目**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">項目</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AGPM サービス</p></td>
<td align="left"><p>AGPM サービスは AGPM サーバー上で実行されます。 サービスは、オフライン Gpo を含むアーカイブを管理し、運用環境では制御された Gpo を管理します。 AGPM サービスの既定の構成は次のとおりです。</p>
<ul>
<li><p><strong>サービス名: </strong> AGPM サービス</p></li>
<li><p><strong>表示名: </strong> AGPM サービス</p></li>
<li><p><strong>実行可能ファイルへのパス: </strong> % ProgramFiles% \Microsoft\AGPM\Server\Agpm.exe</p></li>
<li><p><strong>スタートアップ: </strong> 自動</p></li>
<li><p><strong>ログオン: </strong> Agpm サーバーのインストール中に指定された Agpm サービスアカウント。 <strong> コントロールパネルの [プログラムと機能] を使って変更でき </strong> <strong> </strong> ます。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>AGPM アーカイブ</p></td>
<td align="left"><p>既定では、AGPM は、AGPM サーバー上の%ProgramData%\Microsoft\AGPM にアーカイブを作成します。 アーカイブには、オフライン Gpo 用の記憶域が用意されています。また、各 GPO の複数のバージョンを格納することもできます。 パッケージ内の Gpo に対して AGPM が行う変更は、AGPM 管理者または承認者が GPO を運用環境に展開し、GPO を組織単位 (OU) にリンクするまで、運用環境に影響を与えません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows ファイアウォール</p></td>
<td align="left"><p>インストール時に、AGPM は、agpm クライアントが AGPM サーバーと通信するための受信 Windows ファイアウォール規則を有効にします。 Windows ファイアウォールの既定の規則は次のとおりです。</p>
<ul>
<li><p><strong>Name: </strong> AGPM サービス</p></li>
<li><p><strong>アクション: </strong> 接続を許可する</p></li>
<li><p><strong>プログラム: </strong> 指定した条件を満たすすべてのプログラム</p></li>
<li><p><strong>プロトコルの種類: </strong> TCP</p></li>
<li><p><strong>ローカルポート: </strong> 4600</p></li>
<li><p><strong>リモートポート: </strong> すべてのポート</p></li>
<li><p><strong>ローカル IP アドレス: </strong> Any</p></li>
<li><p><strong>リモート IP アドレス: </strong> Any</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>メールサーバー</p></td>
<td align="left"><p>AGPM は、Simple Mail Transfer Protocol (SMTP) を使って、[Domain Delegation] タブで構成されたアドレスに電子メール要求を送信し <strong> </strong> ます。たとえば、新しい GPO を作成するようにエディターから要求があった場合、AGPM は [Domain Delegation] タブで指定された各電子メールアドレスに通知し <strong> </strong> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AGPM スナップイン</p></td>
<td align="left"><p>GPMC の AGPM スナップインは、AGPM クライアントで実行され、グループポリシー管理者が Gpo を管理するために使用されます。 スナップインは、GPMC の <strong> 各ドメインの変更制御フォルダーとして表示され </strong> ます。</p></td>
</tr>
</tbody>
</table>

 

### その他の参照情報

AGPM によってインストールされるファイルについて詳しくは、 [agpm の計画ガイド](https://go.microsoft.com/fwlink/?LinkId=160060)をご覧ください。

## アーカイブ


既定では、AGPM サーバーのインストールプロセスによって、% programdata% ¥¥のローカルハードディスク上のアーカイブが作成されます。 ただし、インストール中にパスを変更したり、AGPM サーバー以外のサーバーにアーカイブを作成したりすることもできます。

アーカイブには、アーカイブに含まれる各 GPO の各バージョンのサブフォルダーが含まれます。 各サブフォルダーの名前は、その GPO のバージョンを識別する GUID です。

gpostate.xml ファイルには、アーカイブ内の各 GPO の状態が記録されます。 ファイルは、アーカイブの内容を説明するマニフェストです。 たとえば、GPO には多くのバージョンがあり、各バージョンはアーカイブ内の独自のサブフォルダーにあります。 gpostate.xml ファイルには、1つの GPO の異なるバージョンが含まれるサブフォルダーが示されます。 さらに、GPO テンプレートにはアーカイブ内のサブフォルダーがあります gpostate.xml が、これはテンプレートであり、管理されている Gpo ではないことを示しています。 同様に、グループポリシーの管理者が Gpo を削除するときに、AGPM は、**ごみ箱**の gpostate.xml 状態を変更しますが、実際には、gpo のサブフォルダーはアーカイブから削除されないことを示します。

**注意** gpostate.xml またはアーカイブに含まれている Gpo を手動で編集しないでください。 この情報は、AGPM アーカイブの理解を深めるためにのみ提供されます。 代わりに、AGPM スナップインを使って Gpo を変更します。

 

AGPM によってアーカイブが作成されると、システム、管理者、agpm サービスアカウント (AGPM サーバーのセットアップで指定) へのフルコントロールが与えられます。 Agpm サービスアカウントは、ログオンしているユーザーの代わりにすべての操作を実行するため、AGPM スナップインの AGPM ユーザーインターフェイスを使用してアクセス許可を変更しても、アーカイブのアクセス許可は変更されません。

### その他の参照情報

アーカイブのバックアップ方法、バックアップからアーカイブを復元する方法、または AGPM サーバーとアーカイブの両方を移動する方法については、「[操作ガイド (agpm の操作ガイド](https://go.microsoft.com/fwlink/?LinkId=160061))」の「Agpm 管理者のタスクを実行する」セクションを参照してください。

## 役割とアクセス許可


役割によって委任が簡単になります。 グループポリシー管理者に対して詳細なアクセス許可を割り当てる代わりに、AGPM 管理者は、その役割に関連する作業を実行できるように、次の4つの役割のいずれかをグループポリシー管理者に割り当てることができます。

-   **AGPM 管理者:** グループポリシー管理者は、AGPM 管理者 (フルコントロール) の役割を割り当てて、AGPM 内の任意のタスクを実行できます。 AGPM 管理者は、ドメイン全体のオプションを構成し、他のグループポリシー管理者にアクセス許可を委任することができます。

-   **承認者:** グループポリシー管理者は、承認者の役割を割り当てた Gpo をドメインの運用環境に展開できます。 承認者は、Gpo を作成および削除し、編集者から要求を承認または拒否することもできます。 承認者は、ドメイン内の Gpo の一覧を表示したり、Gpo のポリシー設定を表示したり、GPO のポリシー設定のレポートを作成して表示したりすることができます。 編集者の役割が割り当てられている場合を除き、Gpo のポリシー設定を編集することはできません。

-   **エディター:** グループポリシー管理者は、ドメイン内の Gpo の一覧を表示したり、Gpo のポリシー設定を表示したり、gpo のポリシー設定を編集したり、GPO のポリシー設定のレポートを作成して表示したりすることができます。 管理者は、承認者の役割も割り当てられていない限り、Gpo の作成、展開、削除を行うことはできません。 ただし、Gpo の作成、展開、または削除を要求することができます。

-   **校閲者:** グループポリシー管理者は、レビュー担当者の役割を割り当てることで、ドメイン内の Gpo の一覧を表示したり、GPO のポリシー設定のレポートを作成して表示したりできます。 編集者の役割も割り当てられている場合を除き、GPO のポリシー設定を編集することはできません。

Agpm は、agpm 管理者に対して、AGPM スナップインを使用して、ロールよりも詳細なレベルでアクセス許可を構成できる柔軟性を提供します。 表2に、これらのアクセス許可について説明します。既定では、各役割に付与されるアクセス許可を示しています。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">許可</th>
<th align="left">説明</th>
<th align="left">AGPM 管理者</th>
<th align="left">承認者</th>
<th align="left">エディター</th>
<th align="left">担当者</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>フルコントロール</strong></p></td>
<td align="left"><p>すべての権限を持つ。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>GPO を作成する</strong></p></td>
<td align="left"><p>ドメインで Gpo を作成します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>リストの内容</strong></p></td>
<td align="left"><p>ドメイン内の Gpo を一覧表示します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>設定の読み取り</strong></p></td>
<td align="left"><p>GPO 内のポリシー設定を確認します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>設定を編集する</strong></p></td>
<td align="left"><p>GPO のポリシー設定を変更します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p></p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>GPO を削除する</strong></p></td>
<td align="left"><p>GPO を削除します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>セキュリティを変更する</strong></p></td>
<td align="left"><p>ドメインレベルのアクセスを委任したり、1つの GPO へのアクセスを委任したり、運用環境へのアクセスを委任したりすることができます。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>GPO の展開</strong></p></td>
<td align="left"><p>アーカイブから実稼働環境に GPO を展開します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>テンプレートを作成する</strong></p></td>
<td align="left"><p>AGPM で GPO テンプレートを作成します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p></p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>オプションの変更</strong></p></td>
<td align="left"><p>AGPM メールの通知を構成し、アーカイブに保存されている GPO のバージョンを制限します。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>GPO をエクスポートする</strong></p></td>
<td align="left"><p>GPO をファイルにエクスポートします。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p></p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>GPO をインポートする</strong></p></td>
<td align="left"><p>ファイルから GPO をインポートします。</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p></p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

**注** 
**Gpo のエクスポート**と**gpo のインポート**のアクセス許可は、AGPM 3.0 または2.5 では利用できません。

ドメインの運用環境で Gpo へのアクセスを委任する機能と、保存されている GPO バージョンの数を制限する機能は、AGPM 2.5 では使用できません。

 

### その他の参照情報

グループポリシー管理者が特定の役割を割り当てた、または特定のタスクを実行するために必要なアクセス許可について、実行できるタスクの詳細については、「 [AGPM の操作ガイド](https://go.microsoft.com/fwlink/?LinkId=160061)」を参照してください。

 

 





