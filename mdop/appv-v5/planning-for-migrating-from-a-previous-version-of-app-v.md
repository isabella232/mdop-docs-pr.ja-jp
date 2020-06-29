---
title: APP-V の以前のバージョンからの移行計画
description: APP-V の以前のバージョンからの移行計画
author: dansimp
ms.assetid: d4ca8f09-86fd-456f-8ec2-242ff94ae9a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 2242f58a29473e116506ec013b94a79d1bb814a6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813474"
---
# APP-V の以前のバージョンからの移行計画


以前のバージョンの App-v から App-v 5.0 に移行する方法については、次の情報を参照してください。

## 移行の要件


アップグレードを開始する前に、次の要件を確認してください。

-   App-v 4.6 SP2 より前のバージョンからアップグレードする場合は、まずバージョンアプリ-V 4.6 SP3 にアップグレードしてから、App-v 5.0 以降にアップグレードしてください。 このシナリオでは、最初に App-v クライアントをアップグレードし、次にサーバーコンポーネントをアップグレードします。
**注:** App-v 4.6 は、メインストリームサポートを終了しました。

-   App-v 5.0 は、App-v 5.0 を使って作成されたパッケージ、または App-v 5.0 (**appv**) 形式に変換されたパッケージのみをサポートします。

-   App-v 5.0 SP3 のみ: app-v Server を App-v 5.0 SP1 からアップグレードする場合は、手順については、「 [app-v 5.0 SP3 につい](about-app-v-50-sp3.md#bkmk-migrate-to-50sp3)て」を参照してください。

## App-v 4.6 を使って app-v 5.0 クライアントを同時に実行する


App-v 5.0 クライアントは、app-v 4.6 SP3 クライアントと同じコンピューターで同時に実行できます。

共存する App-v クライアントを実行する場合は、次のことができます。

-   両方のクライアントを実行している場合は、App-v 4.6 SP3 パッケージを App-v 5.0 形式に変換し、両方のパッケージを公開します。

-   変換されたパッケージの移行ポリシーを定義します。これにより、変換された App-v 5.0 パッケージでは、ファイルの種類の関連付けと、App-v 4.6 パッケージのショートカットが想定されます。

### サポートされている共存シナリオ

次の表は、サポートされている App-v の共存シナリオを示しています。 共存クライアントを実行している場合は、特定のリリースの最新の利用可能な更新プログラムをインストールすることをお勧めします。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 4.6 クライアントの種類</th>
<th align="left">App-v 5.0 クライアントの種類</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 4.6 SP3</p></td>
<td align="left"><p>App-v 5.0</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 4.6 SP3 RDS</p></td>
<td align="left"><p>App-v 5.0 RDS</p></td>
</tr>
</tbody>
</table>

 

### 共存クライアントを実行するための要件

共存クライアントを実行するには、次のことを行う必要があります。

-   App-v 5.0 クライアントをインストールする前に、app-v 4.6 クライアントをインストールします。

-   [**移行モードを有効にする**] グループポリシー設定を有効にします。これは、 **app-v** Client の [ &gt; **共存**] ノードにあります。 Admx テンプレートの展開を取得するには、「 [MDOP グループポリシー (admx) テンプレートをダウンロードして展開する方法](https://technet.microsoft.com/library/dn659707.aspx)」を参照してください。

### クライアントのダウンロードとドキュメント

次の表は、リリースに関する TechNet のドキュメントへのリンクを示しています。 App-v クライアントに関する TechNet ドキュメントは、特に指定がない限り、両方のクライアントに適用されます。

<table>
<colgroup>
<col width="33%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v のバージョン</th>
<th align="left">TechNet のドキュメントへのリンク</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 4.6 SP3</p></td>
<td align="left"><p><a href="https://technet.microsoft.com/library/dn511019.aspx" data-raw-source="[About Microsoft Application Virtualization 4.6 SP3](https://technet.microsoft.com/library/dn511019.aspx)">Microsoft Application Virtualization 4.6 SP3 について</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 5.0 SP3</p></td>
<td align="left"><p><a href="about-app-v-50-sp3.md" data-raw-source="[About Microsoft Application Virtualization 5.0 SP3](about-app-v-50-sp3.md)">Microsoft Application Virtualization 5.0 SP3 について</a></p></td>
</tr>
</tbody>
</table>

 

App-v 5.0 クライアントの共存を構成する方法の詳細については、以下を参照してください。

-   [同じコンピューター上に App-v 4.6 と App-v 5.0 クライアントを展開する方法](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)

-   [App-v 5.0 の共存と移行](https://technet.microsoft.com/windows/jj835811.aspx)

## <a href="" id="converting--previous-version--packages-using-the-package-converter-"></a>パッケージコンバーターを使用した "以前のバージョン" パッケージの変換


App-v 4.6 SP3 以前のバージョンを使用して作成されたパッケージを App-v 5.0 に移行する前に、次の要件を確認してください。

-   パッケージを**appv**ファイル形式に変換する必要があります。

-   パッケージコンバーターは、App-v 4.5 以降を使って作成されたパッケージの直接変換のみをサポートしています。 以前のバージョンを使用して作成されたパッケージに対してパッケージコンバーターを使用するには、パッケージをアップグレードするために、アプリ-V 4.5 以降の sequencer を使用する必要があります。その後、パッケージの変換を実行できます。

パッケージコンバーターを使ったパッケージの変換について詳しくは、「[以前のバージョンの app-v で作成されたパッケージを変換する方法](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)」をご覧ください。 ファイルを変換した後は、App-v 5.0 クライアントを実行するターゲットコンピューターに展開することができます。






## 関連トピック


[App-V の展開計画](planning-to-deploy-app-v.md)

 

 





