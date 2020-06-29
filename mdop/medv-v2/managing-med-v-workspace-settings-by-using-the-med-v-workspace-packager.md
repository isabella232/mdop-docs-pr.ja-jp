---
title: MED-V ワークスペース パッケージ ツールを使用した MED-V ワークスペースの設定の管理
description: MED-V ワークスペース パッケージ ツールを使用した MED-V ワークスペースの設定の管理
author: dansimp
ms.assetid: e4b2c516-b9f8-44f9-9eae-caac6c2af3e7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9905c8da0f1f0678cce9587296526e8f04493c20
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826124"
---
# MED-V ワークスペース パッケージ ツールを使用した MED-V ワークスペースの設定の管理


MED-V ワークスペースパッケージャーを使って、MED-V ワークスペースの特定の設定を管理できます。

**MED-V ワークスペースで設定を管理するには**

1. **Med-v ワークスペースのパッケージャー**を開くには、 **[スタート**]、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v workspace パッケージャー**] の順にクリックします。

2. **Med-v ワークスペースパッケージャー**のメインパネルで、[**設定の管理**] をクリックします。

3. [**設定の管理**] ウィンドウで、次のような med-v のワークスペース設定を構成できます。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong>MED-V ワークスペースを開始する</strong></p></td>
   <td align="left"><p>ユーザーのログオン時に MED-V workspace を起動するか、最初に使用するか、またはエンドユーザーが MED-V ワークスペースを開始するタイミングを決定できるようにするかを選択します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p>MED-V ワークスペースは、エンドユーザーがログオンしている場合、または、公開されたアプリケーションを開く場合や、リダイレクトが必要な URL を入力する場合など、MED-V が必要な操作を最初に実行するときに、次の2つの方法のいずれかで開始されます。</p>
   <p>エンドユーザー向けにこの設定を定義するか、または MED-V の開始方法をエンドユーザーが制御できるようにすることができます。</p>
   <div class="alert">
   <strong>注</strong><br/><p>エンドユーザーによって決定されたことを指定した場合、そのユーザーが遭遇する既定の動作は、ログオン時に MED-V ワークスペースが開始されることです。 既定の設定を変更するには、通知領域の MED-V アイコンを右クリックし、[Med-v] の [ユーザー設定] を選び <strong> </strong> ます。 エンドユーザーに対してこの設定を定義した場合は、MED-V の開始方法を変更することはできません。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>ネットワーク</strong></p></td>
   <td align="left"><p>[ <strong> ネットワーク設定] で [共有] または [ブリッジ] を選択し </strong> <strong> </strong> ます。 既定値は [共有されてい <strong> </strong> ます。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p><strong>共有 </strong> - Med-v workspace は、ネットワークアドレス変換 (NAT) を使って、発信トラフィック用にホスト&#39;s IP を共有します。</p>
   <p><strong>つなぎ </strong> - ます。 med-v ワークスペースには独自のネットワークアドレスがあり、通常は DHCP 経由で取得します。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>資格情報を保存する</strong></p></td>
   <td align="left"><p>エンドユーザーの資格情報を保存するかどうかを選択します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p></p></td>
   <td align="left"><p>既定の動作では、資格情報の保存機能が無効になっているため、ユーザーがログオンするたびにエンドユーザーの認証を行う必要があります。</p>
   <div class="alert">
   <strong>重要</strong><br/><p>エンドユーザーの資格情報をキャッシュすると、ユーザーエクスペリエンスが最大限に向上しますが、そのリスクについて注意する必要があります。</p>
   <p>エンドユーザーのドメイン資格情報は、Windows Credential Manager の元に戻す形式で格納されます。 攻撃者は、パスワードを取得してユーザーの資格情報にアクセスできるプログラムを作成する可能性があります。 このリスクを軽減するには、エンドユーザーの資格情報の保存を無効にする必要があります。</p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



4. [**名前を付けて保存**] をクリックします。 指定したフォルダーの更新された設定を保存します。 MED-V は、更新された設定を含むレジストリファイルを作成します。 グループポリシーを使用して、更新されたレジストリファイルを展開します。 グループポリシーの使用方法の詳細については、「[グループポリシーソフトウェアのインストール](https://go.microsoft.com/fwlink/?LinkId=195931)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=195931) 。

   また、指定されたフォルダーに Windows PowerShell スクリプトを作成します。このスクリプトは、この更新されたレジストリファイルを再作成するために使用できます。

## 関連トピック


[MED-V ワークスペースの構成設定の管理](managing-med-v-workspace-configuration-settings.md)

[MED-V ワークスペースの設定を管理する](manage-med-v-workspace-settings.md)









