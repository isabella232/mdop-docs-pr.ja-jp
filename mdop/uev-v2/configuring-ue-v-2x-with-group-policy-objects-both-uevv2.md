---
title: グループポリシーオブジェクトを使用して UE-V 2. x を構成する
description: グループポリシーオブジェクトを使用して UE-V 2. x を構成する
author: dansimp
ms.assetid: 2bb55834-26ee-4f19-9860-dfdf3c797143
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bdff63b948752b9bec83e77e275f1cb20a384463
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824424"
---
# グループポリシーオブジェクトを使用して UE-V 2. x を構成する


一部の Microsoft User Experience Virtualization (UE-V) 2.0、2.1、2.1 SP1 グループポリシー設定は、コンピューターに対して定義することができ、その他のグループポリシー設定をユーザーに対して定義することもできます。 UE-V グループポリシー ADMX ファイルをインストールする方法については、「 [ue-v 2 グループポリシーの Admx テンプレートのインストール](https://technet.microsoft.com/library/dn458891.aspx#admx)」を参照してください。

UE-V 用に次のポリシー設定を構成できます。

**グループ ポリシー設定**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">グループポリシー設定の名前</th>
<th align="left">ターゲット</th>
<th align="left">グループポリシーの設定の説明</th>
<th align="left">構成オプション</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>連絡するリンクテキスト</p></td>
<td align="left"><p>コンピューターのみ</p></td>
<td align="left"><p>このグループポリシー設定では、会社設定センターの [連絡先 IT URL] ハイパーリンクのテキストを指定します。</p></td>
<td align="left"><p>このグループポリシー設定を有効にした場合、[会社設定センター] の URL へのリンクに、指定したテキストが表示されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>お問い合わせ先の URL</p></td>
<td align="left"><p>コンピューターのみ</p></td>
<td align="left"><p>このグループポリシー設定では、会社設定センターの [連絡先 IT] リンクの URL を指定します。</p></td>
<td align="left"><p>この設定を有効にした場合、会社設定センターでは、指定した URL へのリンクが表示されます。 Link は、HTTP や mailto などの標準プロトコルのいずれでもかまいません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同期プロバイダーを使用しない</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループポリシー設定を使用すると、UE-V が同期プロバイダー機能を使用するかどうかを構成できます。 このポリシー設定では、ユーザー設定のインポートが延期された場合に通知を表示することもできます。</p></td>
<td align="left"><p>この設定を有効にして、UE-V Agent が同期プロバイダーを使用しないように設定します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>初めて使用するときの通知</p></td>
<td align="left"><p>コンピューターのみ</p></td>
<td align="left"><p>このグループポリシー設定では、UE-V の場合に表示される通知領域の通知を有効にします。</p>
<p>エージェントは初めて実行されます。</p></td>
<td align="left"><p>既定値は有効です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows のローミングの設定</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループポリシー設定では、Windows 設定の同期を構成します。</p></td>
<td align="left"><p>コンピューター間で同期する Windows の設定を選択します。</p>
<p>既定では、Windows のテーマ、デスクトップの設定、および簡単操作の設定は、同じオペレーティングシステムバージョンのコンピューター間で設定を同期します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定パッケージサイズの警告しきい値</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループポリシー設定では、設定パッケージのファイルサイズが定義されたしきい値に達したときに報告するように UE-V Agent を構成できます。</p></td>
<td align="left"><p>設定パッケージサイズの優先しきい値をキロバイト (KB) で指定します。</p>
<p>既定では、UE-V Agent にはパッケージファイルサイズのしきい値はありません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定の記憶域のパス</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループポリシー設定では、ユーザー設定を保存する場所を構成します。</p></td>
<td align="left"><p>汎用名前付け規則 (UNC) のパスと \Server\SettingsShare%username%. などの変数を入力します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定テンプレートカタログのパス</p></td>
<td align="left"><p>コンピューターのみ</p></td>
<td align="left"><p>このグループポリシー設定では、カスタム設定の場所テンプレートが保存されている場所を構成します。 このポリシー設定では、UE-V Agent と共にインストールされた既定の Microsoft テンプレートの代わりにカタログを使用するかどうかも構成します。</p></td>
<td align="left"><p>\Server\TemplateShare やコンピューター上のフォルダーの場所など、汎用名前付け規則 (UNC) パスを入力します。</p>
<p>既定の Microsoft テンプレートを置き換えるには、このチェックボックスをオンにします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>従量制課金接続で設定を同期する</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループポリシー設定では、UE-V が従量制課金接続で設定を同期するかどうかを定義します。</p></td>
<td align="left"><p>既定では、UE-V Agent で従量制課金接続で設定を同期しません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ローミング中の従量制課金接続で設定を同期する</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループポリシー設定では、データ接続がローミングモードの場合など、自宅のプロバイダーネットワーク以外の従量制課金接続で、UE-V が設定を同期するかどうかを定義します。</p></td>
<td align="left"><p>既定では、UE-V は、従量制課金接続の設定をローミングモードでは同期しません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同期タイムアウト</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループポリシー設定では、コンピューターがリモート設定の場所からユーザー設定を取得したときにタイムアウトするまでの時間 (ミリ秒単位) を構成します。 リモート記憶域の場所が利用できず、ユーザーが同期プロバイダーを使用していない場合は、アプリケーションの開始がこのミリ秒単位で遅延します。</p></td>
<td align="left"><p>優先同期のタイムアウト (ミリ秒単位) を指定します。 既定値は2000ミリ秒です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>トレイアイコン</p></td>
<td align="left"><p>コンピューターのみ</p></td>
<td align="left"><p>このグループポリシー設定では、User Experience Virtualization (UE-V) トレイアイコンを有効にします。</p></td>
<td align="left"><p>既定値は有効です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>User Experience Virtualization (UE-V) を使用する</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループポリシー設定では、User Experience Virtualization (UE-V) を有効または無効にすることができます。</p></td>
<td align="left"><p>このグループポリシー設定を有効または無効にします。</p></td>
</tr>
</tbody>
</table>

 

**注** さらに、グループポリシー設定は、多くのデスクトップアプリケーションや Windows アプリで利用できます。 これらの設定を使って、特定のアプリケーションの設定の同期を有効または無効にすることができます。

 

**Windows アプリのグループポリシー設定**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">グループポリシー設定の名前</th>
<th align="left">ターゲット</th>
<th align="left">グループポリシーの設定の説明</th>
<th align="left">構成オプション</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows アプリを同期しない</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループポリシー設定では、UE-V Agent で Windows アプリの設定を同期するかどうかを定義します。</p></td>
<td align="left"><p>既定では、Windows アプリを同期します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows アプリの一覧</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>この設定では、Windows アプリとその状態のファミリーパッケージ名が一覧表示されます。これは、UE-V がアプリの設定を同期するかどうかを明示的に示しています。</p></td>
<td align="left"><p>この設定を使って、他のすべての Windows アプリの設定が同期されている場合でも、アプリの設定を UE-V で同期させないように指定できます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>一覧にない Windows アプリを同期する</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループポリシー設定では、windows アプリリストに明示的に記載されていない Windows アプリ用の UE-V Agent の既定の設定同期動作を定義します。</p></td>
<td align="left"><p>既定では、UE-V Agent は Windows アプリリストに含まれている Windows アプリの設定のみを同期します。</p></td>
</tr>
</tbody>
</table>

 

Windows アプリの同期の詳細については、「 [Windows アプリの一覧](https://technet.microsoft.com/library/dn458925.aspx#win8applist)」を参照してください。

**コンピューターの対象となるグループポリシー設定を構成するには**

1.  UE-V コンピューターのグループポリシー設定を管理するドメインコントローラーとして機能するコンピューターで、グループポリシー管理コンソール (GPMC) または Advanced グループポリシー管理 (AGPM) を使用します。 [**コンピューターの構成**] に移動し、[**ポリシー**] を選択し、[**管理用テンプレート**] をクリックして、[ **Windows コンポーネント**] をクリックし、[ **Microsoft User Experience Virtualization**] を選びます。

2.  編集するグループポリシー設定を選びます。

**ユーザーを対象としたグループポリシー設定を構成するには**

1.  ドメインコントローラーコンピューターの Microsoft デスクトップ最適化パック (MDOP) でグループポリシー管理コンソール (GPMC) または Advanced グループポリシー管理 (AGPM) ツールを使って、UE-V のグループポリシー設定を管理します。 [**ユーザーの構成**] に移動し、[**ポリシー**] を選択し、[**管理用テンプレート**]、[ **Windows コンポーネント**]、[ **Microsoft User Experience Virtualization**] の順に選択します。

2.  [編集済みのグループポリシー] 設定を選択します。

UE-V Agent では、次の優先順位に従って同期が決定されます。

**UE-V の設定の優先順位**

1.  グループポリシー設定によって管理されるユーザーを対象とした設定-これらの構成設定は、のグループポリシーによってレジストリキーに保存され `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` ます。

2.  グループポリシー設定によって管理されるコンピューターターゲット設定-これらの構成設定は、のグループポリシーによってレジストリキーに保存され `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` ます。

3.  Windows PowerShell または Windows management Instrumentation (WMI) を使用して、現在のユーザーによって定義された構成設定: これらの構成設定は、次のレジストリの場所にある UE-V エージェントによって保存さ `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` れます。

4.  Windows PowerShell または WMI を使用して、コンピューターに対して定義されている構成設定。 この構成設定は、次のレジストリの場所にある UE-V エージェントによって保存さ `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration` れます。

    **Ue-v のご提案をお寄せ**ください。 [ここで](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)候補を追加または投票してください。 **Ue-v の問題が発生した場合** Ue-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)を使用します。

## 関連トピック


[UE-V 2. x の管理](administering-ue-v-2x-new-uevv2.md)

[UE-V 2.x の構成を管理する](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 





