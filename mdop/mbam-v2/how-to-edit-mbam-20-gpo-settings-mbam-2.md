---
title: MBAM 2.0 GPO 設定を編集する方法
description: MBAM 2.0 GPO 設定を編集する方法
author: dansimp
ms.assetid: f5ffa93d-b4d2-4317-8a1c-7d2be0264fe3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aaf7c7aab4baba66513edbfa2489fbe53c97dda8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824087"
---
# MBAM 2.0 GPO 設定を編集する方法


Microsoft BitLocker の管理と監視 (MBAM) を正常に展開するには、まず Microsoft BitLocker の管理と監視の実装で使用するグループポリシーを決定する必要があります。 使用可能なさまざまなポリシーの詳細については、「 [MBAM 2.0 グループポリシーの要件](planning-for-mbam-20-group-policy-requirements-mbam-2.md)」を参照してください。 使用するポリシーを決定したら、MBAM のポリシー設定が含まれている1つ以上のグループポリシーオブジェクト (GPO) を変更する必要があります。

次の手順を使用して、組織のクライアントコンピューターの BitLocker 暗号化を MBAM で管理できるように、基本的な推奨される GPO 設定を構成することができます。

**MBAM クライアント GPO 設定を編集するには**

1.  MBAM グループポリシーテンプレートがインストールされているコンピューターで、MBAM サービスが有効になっていることを確認します。

2.  MBAM グループポリシーテンプレートがインストールされているコンピューターで、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) の MDOP 製品を使用して、[**コンピューターの構成**]、[**ポリシー**]、[**管理用テンプレート**]、[ **Windows コンポーネント**] の順にクリックし、[ **MDOP (BitLocker 管理)**] をクリックします。

3.  クライアントコンピューターで MBAM クライアントサービスを有効にするために必要なグループポリシーオブジェクト設定を編集します。 次の表のポリシーごとに、[**ポリシー] グループ**を選択し、**ポリシー**をクリックして、**設定**を構成します。

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">ポリシーグループ</th>
    <th align="left">ポリシー</th>
    <th align="left">設定</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>クライアントの管理</p></td>
    <td align="left"><p>MBAM サービスを設定する</p></td>
    <td align="left"><p>有効。 <strong>Mbam Recovery と Hardware service のエンドポイントを設定 </strong> し、 <strong> 保存する BitLocker 回復情報を選択し </strong> ます。 <strong>Mbam コンプライアンスサービスのエンドポイント </strong> を設定し、状態レポートの頻度 (分) を入力します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>オペレーティングシステムドライブ</p></td>
    <td align="left"><p>オペレーティングシステムドライブの暗号化の設定</p></td>
    <td align="left"><p>有効。 <strong>オペレーティングシステムドライブの [プロテクター] を設定 </strong> します。 オペレーティングシステムドライブのデータを MBAMKey Recovery サーバーに保存するために必要です。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>リムーバブルドライブ</p></td>
    <td align="left"><p>リムーバブルドライブでの BitLocker の使用を制御する</p></td>
    <td align="left"><p>有効。 MBAM キー回復サーバーにリムーバブルドライブのデータを保存する場合に必要です。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>固定ドライブ</p></td>
    <td align="left"><p>固定ドライブでの BitLocker の使用を制御する</p></td>
    <td align="left"><p>有効。 MBAM キー回復サーバーに固定ドライブのデータを保存する場合は必須です。</p>
    <p><strong>BitLocker で保護されたドライブをどのように回復 </strong> して、データ回復エージェントを許可するかを選択し <strong> </strong> ます。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Important**  
Depending on the policies that your organization decides to deploy, you may have to configure additional policies. See [Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md) for Group Policy configuration details for all of the available MBAM GPO policy options.
~~~



## 関連トピック


[MBAM 2.0 グループ ポリシー オブジェクトの展開](deploying-mbam-20-group-policy-objects-mbam-2.md)









