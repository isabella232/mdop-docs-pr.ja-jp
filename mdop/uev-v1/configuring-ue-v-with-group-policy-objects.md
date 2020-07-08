---
title: グループ ポリシー オブジェクトを使用した UE-V の構成
description: グループ ポリシー オブジェクトを使用した UE-V の構成
author: dansimp
ms.assetid: 5c9be706-a05f-4397-9a38-e6b73ebff1e5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7e479e6bef1a2b38cf822ffca19ed4220b0c59fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826697"
---
# グループ ポリシー オブジェクトを使用した UE-V の構成


一部の Microsoft User Experience Virtualization (UE-V) グループポリシー設定は、コンピューターに対して定義することができ、他のユーザーに対して定義することもできます。 UE-V agent 構成ポリシー設定は、コンピューターまたはユーザーに対して定義することができます。 UE-V グループポリシー ADMX ファイルのインストール方法については、「 [Ue-v グループポリシーの Admx テンプレートをインストール](installing-the-ue-v-group-policy-admx-templates.md)する」を参照してください。

UE-V 用に次のポリシー設定を構成できます。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>ポリシー設定名</strong></p></td>
<td align="left"><p><strong>ターゲット</strong></p></td>
<td align="left"><p><strong>ポリシー設定の説明</strong></p></td>
<td align="left"><p><strong>構成オプション</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>User Experience Virtualization (UE-V) を使用する</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このポリシー設定では、ユーザーエクスペリエンスの仮想化 (UE-V) を有効または無効にすることができます。</p></td>
<td align="left"><p>このポリシー設定を有効または無効にします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定の記憶域のパス</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このポリシー設定では、ユーザー設定を保存する場所を構成します。</p></td>
<td align="left"><p>汎用名前付け規則 (UNC) のパスと \Server\SettingsShare%username%. などの変数を指定します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定テンプレートカタログのパス</p></td>
<td align="left"><p>コンピューターのみ</p></td>
<td align="left"><p>このポリシー設定では、カスタム設定の場所テンプレートが保存されている場所を構成します。 このポリシー設定では、UE-V agent と共にインストールされた既定の Microsoft テンプレートをカタログで置き換えるかどうかも構成します。</p></td>
<td align="left"><p>\Server\TemplateShare やコンピューター上のフォルダーの場所など、汎用名前付け規則 (UNC) パスを指定します。</p>
<p></p>
<p>既定の Microsoft テンプレートを置き換えるには、このチェックボックスをオンにします。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>オフラインファイルを使わない</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このポリシー設定では、UE-V で Windows オフラインファイル機能を使用するかどうかを構成できます。 このポリシー設定では、ユーザー設定のインポートが延期された場合に通知を有効にすることもできます。</p></td>
<td align="left"><p>オフラインファイルを使用しないように UE-V Agent を構成するには、この設定を有効にします。</p>
<p></p>
<p>設定のインポートが延期された場合に通知を受け取るかどうかを指定します。</p>
<p></p>
<p>通知が表示されるまでの待ち時間 (秒単位) を指定します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>同期タイムアウト</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このポリシー設定では、コンピューターがリモート設定の場所からユーザー設定を取得するときにタイムアウトするまでの時間 (ミリ秒単位) を構成します。 リモート記憶域の場所が利用できない場合は、アプリケーションの起動がこのミリ秒単位で遅延します。</p></td>
<td align="left"><p>優先同期タイムアウト (ミリ秒単位) を指定します。 既定値は2000ミリ秒です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>パッケージサイズの警告しきい値</p></td>
<td align="left"><p>コンピューターとユーザー</p></td>
<td align="left"><p>このポリシー設定では、設定パッケージのファイルサイズが定義されたしきい値に達したときに報告するように UE-V agent を構成できます。</p></td>
<td align="left"><p>設定パッケージサイズの推奨しきい値を kb 単位で指定します。</p>
<p>既定では、UE-V agent にはパッケージファイルサイズのしきい値はありません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ローミングアプリケーションの設定</p></td>
<td align="left"><p>ユーザーのみ</p></td>
<td align="left"><p>このポリシー設定は、アプリケーションのユーザー設定のローミングを構成します。</p></td>
<td align="left"><p>コンピューター間でローミングする Windows の設定を選択します。</p>
<p>既定では、UE-V によって提供される設定テンプレートを持つアプリケーションのユーザー設定は、コンピューター間でローミングされます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows のローミングの設定</p></td>
<td align="left"><p>ユーザーのみ</p></td>
<td align="left"><p>このポリシー設定では、Windows の設定のローミングを構成します。</p></td>
<td align="left"><p>コンピューター間をローミングするアプリケーションを選択します。</p>
<p>既定では、Windows のテーマは同じオペレーティングシステムバージョンのコンピューター間でローミングされます。 Windows デスクトップの設定と簡単操作の設定はローミングされません。</p></td>
</tr>
</tbody>
</table>

 

**コンピューターのターゲットポリシーを構成するには**

1.  UE-V コンピューターのグループポリシーを管理するドメインコントローラーコンピューターで、グループポリシー管理コンソール (GPMC) または Advanced グループポリシー管理 (AGPM) を使用します。 [**コンピューターの構成**] に移動し、[**ポリシー**] を選択し、[**管理用テンプレート**] をクリックして、[ **Windows コンポーネント**] をクリックし、[ **Microsoft User Experience Virtualization**] を選びます。

2.  編集するポリシー設定を選びます。

**ユーザーを対象としたポリシーを構成するには**

1.  UE-V のグループポリシーを管理するドメインコントローラーコンピューター上のグループポリシー管理コンソール (MDOP) または高度なグループポリシー管理 (AGPM) ツールを使用します。 [**ユーザーの構成**] に移動し、[**ポリシー**] を選択し、[**管理用テンプレート**]、[ **Windows コンポーネント**]、[ **Microsoft User Experience Virtualization**] の順に選択します。

2.  編集したポリシー設定を選択します。

UE-V agent では、次の優先順位に従って同期が決定されます。

**UE-V の設定の優先順位**

1.  グループポリシーによって管理されるユーザーによる設定: これらの構成設定は、のグループポリシーによってレジストリキーに保存され `HKEY_CURRENT_USER\Software\Policies\Microsoft\Uev\Agent\Configuration` ます。

2.  グループポリシーによって管理されているコンピューターターゲット設定: これらの構成設定は、のグループポリシーによってレジストリキーに保存され `HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Uev\Agent\Configuration` ます。

3.  PowerShell または WMI を使用して現在のユーザーが定義した構成の設定。これらの構成設定は、次のレジストリの場所にある UE-V エージェントによって保存され `HKEY_CURRENT_USER\Software\Microsoft\Uev\Agent\Configuration` ます。

4.  PowerShell または WMI を使用してコンピューターに定義された構成の設定。 これらの構成設定は、の下にある UE-V エージェントによって保存され `HKEY_LOCAL_MACHINE \Software\Microsoft\Uev\Agent\Configuration` ます。

## 関連トピック


[UE-V 1.0 の管理](administering-ue-v-10.md)

[UE-V 1.0 の操作](operations-for-ue-v-10.md)

 

 





