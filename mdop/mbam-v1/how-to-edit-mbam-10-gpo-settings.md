---
title: MBAM 1.0 GPO 設定を編集する方法
description: MBAM 1.0 GPO 設定を編集する方法
author: dansimp
ms.assetid: 03d12fbc-4302-43fc-9b38-440607d778a1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 824fbc2fe0d8f2b00c32de177733e4e327cf4d44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824284"
---
# MBAM 1.0 GPO 設定を編集する方法


Microsoft BitLocker の管理と監視 (MBAM) を正常に展開するには、まず Microsoft BitLocker の管理と監視の実装で使用するグループポリシーを決定する必要があります。 利用可能なさまざまなポリシーの詳細については、「 [MBAM 1.0 グループポリシーの要件の計画](planning-for-mbam-10-group-policy-requirements.md)」を参照してください。 使用するポリシーを決定したら、MBAM ポリシー設定が含まれている1つまたは複数のグループポリシーオブジェクト (GPO) を変更する必要があります。

次の手順では、推奨される基本的なグループポリシーオブジェクト (GPO) 設定を構成して、MBAM で組織のクライアントコンピューターの BitLocker 暗号化を管理できるようにする方法について説明します。

**MBAM クライアント GPO 設定を編集するには**

1.  MBAM グループポリシーテンプレートがインストールされているコンピューターで、MBAM サービスが有効になっていることを確認します。

2.  グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) MDOP 製品を使用して、次の操作を行います。 [**コンピューターの構成**]、[**ポリシー**]、[**管理用テンプレート**] の順にクリックし、[ **Windows コンポーネント**] をクリックして、[ **MDOP (BitLocker 管理)**] をクリックします。

3.  クライアントコンピューターで MBAM クライアントサービスを有効にするために必要なグループポリシーオブジェクト設定を編集します。 次の表のポリシーごとに、[**ポリシーグループ**] を選択し、**ポリシー**をクリックして、**設定**を構成します。

    ポリシーグループ

    ポリシー

    設定

    クライアントの管理

    MBAM サービスを設定する

    有効。 **Mbam Recovery と Hardware service のエンドポイント**を設定し、**保存する BitLocker 回復情報を選択**します。

    **Mbam コンプライアンスサービスのエンドポイント**を設定し、**状態レポートの頻度 (分) を入力**します。

    ハードウェアの互換性のチェックを許可する

    無効になります。 このポリシーは既定で有効になっていますが、基本的な MBAM の実装では必要ありません。

    オペレーティングシステムドライブ

    オペレーティングシステムドライブの暗号化の設定

    有効。 **オペレーティングシステムドライブの [プロテクター] を**設定します。 この操作は、オペレーティングシステムドライブのデータを MBAM キー回復サーバーに保存するために必要です。

    リムーバブルドライブ

    リムーバブルドライブでの BitLocker の使用を制御する

    有効。 MBAM キー回復サーバーにリムーバブルドライブのデータを保存する場合は、この操作が必要です。

    固定ドライブ

    固定ドライブでの BitLocker の使用を制御する

    有効。 MBAM キー回復サーバーに固定ドライブのデータを保存する場合は、この操作が必要です。

    **BitLocker で保護されたドライブをどのように回復**して、**データ回復エージェントを許可**するかを選択します。



~~~
**Important**  
Depending on the policies that your organization decides to deploy, you may have to configure additional policies. See [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md) for Group Policy configuration details for all of the available MBAM GPO policy options.
~~~



## 関連トピック


[MBAM 1.0 グループ ポリシー オブジェクトの展開](deploying-mbam-10-group-policy-objects.md)









