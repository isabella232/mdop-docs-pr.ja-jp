---
title: クライアントで仮想アプリケーションを公開する方法
description: クライアントで仮想アプリケーションを公開する方法
author: dansimp
ms.assetid: 90af843e-b5b3-4a71-a3a1-fa5f4c087f28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5585f82150db69929ccedbee3aecab969c5e7dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816874"
---
# クライアントで仮想アプリケーションを公開する方法


電子ソフトウェア配布システムを使用してアプリケーションの仮想化を展開する場合は、次のいずれかの手順を使用して、アプリケーションパッケージをユーザーに公開することができます。

**スタンドアロンの Windows インストーラーファイルを使用してパッケージを発行するには**

1.  *Requireauthorizationifcached*パラメーターを 0 (ゼロ) に設定してクライアントをインストールする必要があります。 このパラメーターの設定の詳細については、「 [Application Virtualization クライアントインストーラーのコマンドラインパラメーター](application-virtualization-client-installer-command-line-parameters.md) 」を参照してください。

2.  Windows Installer ファイルと SFT ファイルをターゲットコンピューター上の同じフォルダーにコピーします。

3.  コンピューターで次のコマンドを実行します。

    `Msiexec.exe /I "packagename.msi" /q`

**Windows インストーラーとパッケージマニフェストを使ってパッケージを発行するには**

1.  ターゲットコンピューターと SFT ファイルを、ストリーミングサーバー上のコンテンツ共有にコピーします。

2.  各ユーザーのコンピューターで、次のコマンドを実行します。

    `Msiexec.exe /I "\\pathtomsi\packagename.msi" MODE=STREAMING  OVERRIDEURL="\\\\server\\share\\package.sft" LOAD=TRUE /q`

    **重要** OVERRIDEURL の場合、バックスラッシュ文字の前にバックスラッシュを使用してエスケープするか、上書き URL パスが正しく解析されないようにしてください。 また、値がファイルへのパスである場合を除き、プロパティと値は大文字で入力する必要があります。

     

**SFTMIME を使用してパッケージを発行するには**

-   コンピューター上のすべてのユーザーに対してアプリケーションを公開する方法の例については、ユーザーのコンピューターで次のコマンドを実行します。

    `SFTMIME ADD PACKAGE:package-name /MANIFEST manifest-path                                 [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

    このようなその他の SFTMIME コマンドの詳細については、「 [Sftmime コマンドのリファレンス](sftmime--command-reference.md)」を参照してください。

## 関連トピック


[公開方法の選択](determine-your-publishing-method.md)

[電子ソフトウェア配布ベースのシナリオ](electronic-software-distribution-based-scenario.md)

[SFTMIME コマンドリファレンス](sftmime--command-reference.md)

[Application Virtualization Client のスタンドアロン配信シナリオ](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





