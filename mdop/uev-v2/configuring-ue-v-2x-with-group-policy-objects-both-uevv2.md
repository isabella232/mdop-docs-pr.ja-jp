---
title: グループ ポリシー オブジェクトを使用した UE-V 2.x の構成
description: グループ ポリシー オブジェクトを使用した UE-V 2.x の構成
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
ms.openlocfilehash: b6c9636df36a53cbf65bf1904965f2809484b99c
ms.sourcegitcommit: bdc377477a8cc9e973fbcdd67c2f07b882c5d61e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "11494062"
---
# <a name="configuring-ue-v-2x-with-group-policy-objects"></a>グループ ポリシー オブジェクトを使用した UE-V 2.x の構成


一部の Microsoft User Experience Virtualization (UE-V) 2.0、2.1、および 2.1 SP1 グループ ポリシー設定はコンピューターに対して定義し、他のグループ ポリシー設定はユーザーに対して定義できます。 UE-V グループ ポリシー ADMX ファイルをインストールする方法については [、「INSTALLING THE UE-V 2 Group Policy ADMX Templates」を参照してください](https://technet.microsoft.com/library/dn458891.aspx#admx)。

次のポリシー設定は、UE-V 用に構成できます。

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
<th align="left">グループ ポリシーの設定名</th>
<th align="left">ターゲット</th>
<th align="left">グループ ポリシー設定の説明</th>
<th align="left">構成オプション</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>同期方法の構成</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループ ポリシー設定を使用すると、User Experience Virtualization (UE-V) が同期プロバイダー機能を使用するかどうかを構成できます。 このポリシー設定では、ユーザー設定のインポートが遅れたときに通知を表示することもできます。</p></td>
<td align="left"><p>同期プロバイダーを使用しない、または外部同期エンジンを使用する UE-V エージェントを構成するには、この設定を有効にします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>IT リンク テキストに問い合わせ</p></td>
<td align="left"><p>コンピューターのみ</p></td>
<td align="left"><p>このグループ ポリシー設定では、会社設定センターの [連絡先の IT URL] ハイパーリンクのテキストを指定します。</p></td>
<td align="left"><p>このグループ ポリシー設定を有効にすると、会社設定センターは、連絡先 IT URL へのリンクに指定されたテキストを表示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>IT URL に問い合わせ</p></td>
<td align="left"><p>コンピューターのみ</p></td>
<td align="left"><p>このグループ ポリシー設定では、会社設定センターの [連絡先 IT] リンクの URL を指定します。</p></td>
<td align="left"><p>この設定を有効にした場合、会社設定センターは、指定した URL への IT テキスト リンクに連絡します。 リンクには、HTTP や mailto などの標準プロトコルを指定できます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>初回使用通知</p></td>
<td align="left"><p>コンピューターのみ</p></td>
<td align="left"><p>このグループ ポリシー設定では、UE-V が表示される通知領域で通知を有効にします。</p>
<p>エージェントが初めて実行されます。</p></td>
<td align="left"><p>既定値は有効です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同期前に設定の保存場所に ping を実行する</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このポリシー設定では、接続を確認するために設定を同期する前に、UE-V 同期プロバイダーの構成で設定ストレージ パスに ping を実行できます。</p></td>
<td align="left"><p>このグループ ポリシー設定を有効または無効にします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定パッケージのサイズの警告のしきい値</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループ ポリシー設定では、設定パッケージ のファイル サイズが定義されたしきい値に達したときに報告する UE-V エージェントを構成できます。</p></td>
<td align="left"><p>設定パッケージサイズの優先しきい値をキロバイト (KB) で指定します。</p>
<p>既定では、UE-V エージェントにはパッケージ ファイル サイズのしきい値が設定されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定ストレージ パス</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループ ポリシー設定は、ユーザー設定の保存場所を構成します。</p></td>
<td align="left"><p>汎用名前付け規則 (UNC) パスと、\Server\SettingsShare%username% などの変数を入力します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定テンプレート のカタログ パス</p></td>
<td align="left"><p>コンピューターのみ</p></td>
<td align="left"><p>このグループ ポリシー設定は、カスタム設定の場所テンプレートの格納場所を構成します。 このポリシー設定では、カタログを使用して、UE-V エージェントにインストールされている既定の Microsoft テンプレートを置き換えるかどうかを構成します。</p></td>
<td align="left"><p>\Server\TemplateShare などの汎用名前付け規則 (UNC) パス、またはコンピューター上のフォルダーの場所を入力します。</p>
<p>既定の Microsoft テンプレートを置き換えるチェック ボックスをオンにします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>メーター接続を使用して設定を同期する</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループ ポリシー設定は、UE-V がメーター接続を使用して設定を同期するかどうかを定義します。</p></td>
<td align="left"><p>既定では、UE-V エージェントは、メーター接続を使用して設定を同期されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ローミング時でも、メーター接続を使用して設定を同期する</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループ ポリシー設定では、データ接続がローミング モードの場合など、ホーム プロバイダー ネットワークの外部のメーター接続で UE-V が設定を同期するかどうかを定義します。</p></td>
<td align="left"><p>既定では、UE-V はローミング モードの場合、メーター接続を使用して設定を同期しません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同期タイムアウト</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループ ポリシー設定は、リモート設定の場所からユーザー設定を取得するときに、コンピューターがタイムアウトするまでに待機するミリ秒数を構成します。 リモート ストレージの場所が使用できなくなった場合、ユーザーが同期プロバイダーを使用しない場合、アプリケーションの開始は、この数ミリ秒遅れになります。</p></td>
<td align="left"><p>優先する同期タイムアウトをミリ秒単位で指定します。 既定値は 2000 ミリ秒です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows の設定を同期する </p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループ ポリシー設定は、Windows 設定の同期を構成します。</p></td>
<td align="left"><p>コンピューター間で同期する Windows 設定を選択します。</p>
<p>既定では、Windows テーマ、デスクトップ設定、および簡単操作設定は、同じオペレーティング システム バージョンのコンピューター間で設定を同期します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>トレイ アイコン</p></td>
<td align="left"><p>コンピューターのみ</p></td>
<td align="left"><p>このグループ ポリシー設定では、UE-V トレイ アイコンを有効にします。</p></td>
<td align="left"><p>既定値は有効です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ユーザー エクスペリエンス仮想化の使用 (UE-V)</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループ ポリシー設定では、UE-V を有効または無効にできます。</p></td>
<td align="left"><p>このグループ ポリシー設定を有効または無効にします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>VDI 構成</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このポリシー設定は、プールされた VDI 環境で実行されているコンピューターの UE-V ロールバック情報の同期を構成します。 このポリシーを有効にすると、UE-V ロールバック状態がログアウト時の設定ストレージの場所にコピーされ、ログイン時に復元されます。</p></td>
<td align="left"><p>このグループ ポリシー設定を有効または無効にします。</p></td>
</tr>
</tbody>
</table>

 

**備考**  
さらに、グループ ポリシー設定は、多くのデスクトップ アプリケーションおよび Windows アプリで使用できます。 これらの設定を使用して、特定のアプリケーションの設定の同期を有効または無効にできます。

 

**Windows App グループ ポリシーの設定**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">グループ ポリシーの設定名</th>
<th align="left">ターゲット</th>
<th align="left">グループ ポリシー設定の説明</th>
<th align="left">構成オプション</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows アプリを同期しない</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループ ポリシー設定は、UE-V エージェントが Windows アプリの設定を同期するかどうかを定義します。</p></td>
<td align="left"><p>既定では、Windows アプリを同期します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows アプリの一覧</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>この設定では、Windows アプリのファミリ パッケージ名を一覧表示し、UE-V がアプリの設定を同期するかどうかを明示的に示します。</p></td>
<td align="left"><p>この設定を使用すると、他のすべての Windows アプリの設定が同期されている場合でも、アプリの設定が UE-V によって同期されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>リストに登録されていない Windows アプリの同期</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このグループ ポリシー設定は、Windows アプリの一覧に明示的に一覧表示されていない WINDOWS アプリの UE-V エージェントの既定の設定同期動作を定義します。</p></td>
<td align="left"><p>既定では、UE-V エージェントは、Windows アプリリストに含まれる Windows アプリの設定のみを同期します。</p></td>
</tr>
</tbody>
</table>

 

Windows アプリの同期の詳細については、「Windows App [List」を参照してください](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。

**コンピューターを対象としたグループ ポリシー設定を構成するには**

1.  UE-V コンピューターのグループ ポリシー設定を管理するには、ドメイン コントローラーとして機能するコンピューターのグループ ポリシー管理コンソール (GPMC) または Advanced Group Policy Management (AGPM) を使用します。 [コンピューターの**構成] に移動**し、[******ポリシー]** を選択し、[管理用テンプレート] を選択し **、[Windows コンポーネント**] をクリックして、[Microsoft ユーザー エクスペリエンス仮想化]**を選択します**。

2.  編集するグループ ポリシー設定を選択します。

**ユーザーが対象とするグループ ポリシー設定を構成するには**

1.  UE-V のグループ ポリシー設定を管理するには、ドメイン コントローラー コンピューターの Microsoft デスクトップ最適化パック (MDOP) のグループ ポリシー管理コンソール (GPMC) またはグループ ポリシー管理 (AGPM) ツールを使用します。 [ユーザー構成 **] に移動**し **、[ポリシー]** を選択し、[管理用テンプレート] を選択し **、[Windows コンポーネント**] をクリックし、[Microsoft ユーザー エクスペリエンス仮想化]**を選択します**。 ****

2.  編集したグループ ポリシー設定を選択します。

UE-V エージェントは、次の優先順位を使用して同期を決定します。

**UE-V 設定の優先順位**

1.  グループ ポリシー設定によって管理されるユーザーを対象とした設定 - これらの構成設定は、[グループ ポリシー] の下の [レジストリ キー] に格納されます `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` 。

2.  グループ ポリシー設定によって管理されるコンピューターを対象とした設定 - これらの構成設定は、[グループ ポリシー] の下の [レジストリ キー] に格納されます `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` 。

3.  Windows PowerShell または Windows 管理インストルメンテーション (WMI) を使用して現在のユーザーによって定義される構成設定 - これらの構成設定は、次のレジストリの場所に UE-V エージェントによって保存 `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` されます。

4.  ユーザーまたは WMI を使用してコンピューターに対Windows PowerShell構成設定。 これらの構成設定は、次のレジストリの場所に UE-V エージェントによって保存されます `HKEY_LOCAL_MACHINE\Software\Microsoft\Uev\Agent\Configuration` 。

    **UE-V の提案を受け取った** ここで提案を追加または投票 [します](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)。 **UE-V の問題が発生しましたか**? [UE-V TechNet フォーラムを使用します](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。

## <a name="related-topics"></a>関連トピック


[UE-V 2.x の管理](administering-ue-v-2x-new-uevv2.md)

[UE-V 2.x の構成を管理する](manage-configurations-for-ue-v-2x-new-uevv2.md)

 

 
