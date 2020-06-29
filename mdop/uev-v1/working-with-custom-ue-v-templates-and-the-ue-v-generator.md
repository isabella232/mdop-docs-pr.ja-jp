---
title: カスタム UE-V テンプレートと UE-V Generator の操作
description: カスタム UE-V テンプレートと UE-V Generator の操作
author: dansimp
ms.assetid: 7bb2583a-b032-4800-9bf9-eb33528e1d0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: db5387254842bfdcf3898089bc12a8e929e3813a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823977"
---
# カスタム UE-V テンプレートと UE-V Generator の操作


ユーザーコンピューター間でアプリケーションをローミングするために、Microsoft User Experience Virtualization (UE-V) では、*設定場所テンプレート*が使用されます。 一部の設定場所テンプレートは、ユーザーエクスペリエンスの仮想化に含まれています。 また、UE-V Generator を使用して、カスタム設定の場所テンプレートを作成、編集、または検証することもできます。

UE-V Generator は、アプリケーションがその設定を保存する場所を検出し、キャプチャするために、アプリケーションを監視します。 監視対象のアプリケーションは、従来のアプリケーションである必要があります。 UE-V Generator は、次の種類のアプリケーションの設定場所テンプレートを作成できません。

-   仮想化されたアプリケーション

-   ターミナルサービスを通じて提供されるアプリケーション

-   Java アプリケーション

-   Windows 8 アプリケーション

## UE-V Generator を使用して UE-V 設定場所テンプレートを作成する


UE-V Generator を使って設定場所テンプレートを作成する方法について説明します。

[UE-V Generator を使用して UE-V 設定場所テンプレートを作成する](create-ue-v-settings-location-templates-with-the-ue-v-generator.md)

## UE-V Generator を使用して UE-V 設定場所テンプレートを編集する


UE-V Generator を使用して設定場所テンプレートを編集する方法について説明します。

[UE-V Generator を使用して UE-V 設定場所テンプレートを編集する](edit-ue-v-settings-location-templates-with-the-ue-v-generator.md)

## UE-V Generator を使用して UE-V 設定場所テンプレートを検証する


Ue-v generator を使用して、UE-V Generator の外部で変更された設定の場所テンプレートを検証する方法について説明します。

[UE-V Generator を使用して UE-V 設定場所テンプレートを検証する](validate-ue-v-settings-location-templates-with-ue-v-generator.md)

## <a href="" id="bkmk-standardnonstandardsettingslocations"></a>標準設定と非標準設定の場所


UE-V Generator は、アプリケーションが設定情報を格納するために使用する設定ファイルとレジストリ設定をどのように検索するかを特定するのに役立ちます。 UE-V Generator を使用して、標準の場所で設定をキャプチャするために、探索プロセスの一部としてアプリケーションを開くことができます。 標準的な場所には、次のようなものがあります。

-   **レジストリ設定**– HKEY の下にあるレジストリの場所 \ **_CURRENT \ _USER**

-   **アプリケーション設定ファイル**– \ \**ユーザー** \ \ [ユーザー名 \] に保存されているファイル \ \ **AppData**  \\  **ローミング**

UE-V Generator は、ユーザーのコンピューターまたは環境間で、一般的に保存されているアプリケーションソフトウェアファイルが適切にローミングしない場所を除外します。 UE-V Generator では、これらの場所は除外されます。 除外する場所は次のとおりです。

-   HKEY \ _CURRENT \ _USER のレジストリキーと、ログオンしたユーザーが値を書き込むことができないファイル

-   HKEY \ _CURRENT \ _USER のレジストリキーと、Windows オペレーティングシステムのコア機能に関連付けられているファイル

-   HKEY \ _LOCAL \ _MACHINE ハイブに含まれるすべてのレジストリキー (管理者権限が必要であり、設定には UAC ライセンスが必要な場合があります)

-   Program Files ディレクトリに保存されているファイル (管理者権限が必要であるため、UAC 契約を設定する必要がある場合)

-   ユーザー (\ \ \ [ユーザー名 \]) にあるファイル (ユーザー名 \ \)

-   % Systemroot% にある Windows オペレーティングシステムファイル (管理者権限が必要であるため、UAC 契約を設定する必要があります)

アプリケーションの設定をローミングするために、これらの場所に格納されているレジストリキーとファイルが必要な場合は、テンプレートの作成プロセス中に、除外された場所を設定の場所テンプレートに手動で追加することができます。

## この製品のその他のリソース


[UE-V 1.0 の操作](operations-for-ue-v-10.md)

[UE-V 1.0 の管理](administering-ue-v-10.md)

 

 





