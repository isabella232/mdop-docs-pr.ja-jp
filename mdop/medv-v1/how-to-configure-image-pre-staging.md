---
title: イメージの事前ステージングを構成する方法
description: イメージの事前ステージングを構成する方法
author: dansimp
ms.assetid: 92781b5a-208f-45a4-a078-ee90cf9efd9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38ddb7a69845aa4dbcb9cbd16b84dedc04438732
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826407"
---
# イメージの事前ステージングを構成する方法


**注** イメージの事前ステージングは、最初のイメージのダウンロードにのみ役立ちます。 イメージの更新には対応していません。

 

## イメージの事前ステージングを構成する方法


**イメージの事前ステージングを構成するには**

1.  クライアントコンピューターのイメージストアディレクトリで、ステージング用のイメージ用のフォルダーを作成し、そのフォルダーに「 *MED*」の画像という名前を指定します。

    **注** このフォルダーは、 *Med-v イメージ*と呼ばれる必要があります。

     

2.  [MED-V Images] フォルダー内で、サブフォルダーを作成し、 *PrestagedImages*という名前を指定します。

    **注** このフォルダーは、 *PrestagedImages*という名前である必要があります。

     

3.  [ *Med-v Images* ] フォルダーにアクセス制御リスト (ACL) セキュリティを適用するには、次の ACL を設定します。

    **NT AUTHORITY\\Authenticated ユーザー: (OI) (CI) (特殊アクセス:)**

                                             **READ\_CONTROL**

                                    **SYNCHRONIZE**

                                    **FILE\_GENERIC\_READ**

                                    **FILE\_READ\_DATA**

    **                                 ファイル \ _APPEND \ _DATA**

                                    **FILE\_READ\_EA**

                                    **FILE\_READ\_ATTRIBUTES**

    **NT AUTHORITY\\SYSTEM: (OI) (CI) F**

    **BUILTIN\\Administrators: (OI) (CI) F**

    **注** [ *Hyper-v Images* ] フォルダーに ACL セキュリティを適用することをお勧めします。

     

4.  *PrestagedImages*フォルダーに acl セキュリティを適用するには、次の acl を設定します。

    **NT AUTHORITY\\Authenticated ユーザー: (OI) (CI) (特殊アクセス:)**

    **\ _CONTROL の読み取り**

    **処理**

    **ファイル \ _GENERIC \ _READ**

    **ファイル \ _READ \ _DATA**

    **ファイル \ _READ \ _EA**

    **ファイル \ _READ \ _ATTRIBUTES**

    **NT AUTHORITY\\SYSTEM: (OI) (CI) F**

    **BUILTIN\\Administrators: (OI) (CI) F**

    **注** ACL セキュリティを*PrestagedImages*フォルダーに適用することをお勧めします。

     

5.  画像ファイル (CKM ファイルとインデックスファイル) を*PrestagedImages*フォルダーにプッシュします。

    **注** イメージファイルが事前ステージフォルダーにプッシュされたら、データ整合性チェックを実行して、ファイルを読み取り専用としてマークすることをお勧めします。

     

6.  MED-V クライアントインストールに次のパラメーターを追加します。 *Client.MSI VMSFOLDER = "C:\\MED-V Images"*。

## プレステージの場所を更新する方法


**プレステージの位置情報を更新するには**

1.  レジストリキー *PrestagedImagesPath*は、既定の画像の場所をポイントします。 次のディレクトリにあります。

    -   X86 での場合- `KEY_LOCAL_MACHINE\SOFTWARE\Kidaro`

    -   X64- `HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432node`

2.  画像が別の場所にある場合は、パスを変更します。

 

 





