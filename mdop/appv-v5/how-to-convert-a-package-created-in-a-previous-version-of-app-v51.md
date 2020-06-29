---
title: 以前のバージョンの APP-V で作成されたパッケージを変換する方法
description: 以前のバージョンの APP-V で作成されたパッケージを変換する方法
author: dansimp
ms.assetid: 3366d399-2891-491d-8de1-f8cfdf39bbab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 402e64e3bdbc55eea1edb91d070bb7ebb11c912b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814355"
---
# 以前のバージョンの APP-V で作成されたパッケージを変換する方法


パッケージコンバーターユーティリティを使用して、以前のバージョンの App-v で作成された仮想アプリケーションパッケージをアップグレードすることができます。

**注**  
64ビットアーキテクチャを搭載したコンピューターを実行している場合は、x86 バージョンの PowerShell を使用する必要があります。



パッケージコンバーターは、アプリ-V 4.5 sequencer またはそれ以降のバージョンを使って作成されたパッケージのみ、直接変換できます。 App-v 4.5 より前のバージョンを使って作成されたパッケージは、変換する前に、App-v 4.5 または App-v 4.6 形式にアップグレードする必要があります。

次の情報は、既存の仮想アプリケーションパッケージを変換する方向を示しています。

**重要**  
パッケージの食ファイルをセキュリティで保護された場所とディレクトリに常に保存するようにパッケージコンバーターを構成する必要があります。 セキュリティで保護された場所には、管理者のみがアクセスできます。 さらに、パッケージを展開するときは、安全な場所にパッケージを保存するか、変換処理中に他のユーザーがログインすることを許可されていることを確認する必要があります。



**App-v 4.6 のインストールフォルダーが仮想ファイルシステムルートにリダイレクトされます**

パッケージを App-v 4.6 から5.1 に変換する場合、App-v 5.1 パッケージは、4.6 パッケージを作成するときに必要だったハードコードされたドライブにアクセスできます。 ドライブ文字は、4.6 の優先順位のコンピューターでインストールドライブとして選択したドライブになります。 (既定のドライブ文字は Q:\\.)

App-v 5.1 より前のバージョンでは、4.6 のルートフォルダーは認識されず、App-v 5.0 パッケージでアクセスできませんでした。 この時点で、アプリ5.1 からの完全なパスを使用して、ハードコーディングされたファイルにアクセスしたり、プログラムによってプログラムによって4.6 ファイルをプログラムで列挙したりできます。

**技術的な詳細:** App-v 5.1 パッケージコンバーターによって、Filesystem 要素の FilesystemMetadata.xml ファイルに、App-v 4.6 インストールルートフォルダーと短いフォルダー名が保存されます。 App-v 5.1 クライアントで仮想プロセスが作成されると、アプリ-V 4.6 インストールルートから仮想ファイルシステムのルートへの要求がマップされます。

**開始するには**

1.  環境内のコンピューターに app-v Sequencer をインストールします。 Sequencer のインストール方法については、「 [sequencer をインストールする方法](how-to-install-the-sequencer-51beta-gb18030.md)」を参照してください。

2.  

    次のコマンドレットを使用できます。

    -   AppvLegacyPackage –このコマンドレットは、パッケージを確認するように設計されています。 このアプリは **、見つからない**ファイル、無効なソース、 **.osd**ファイルエラー、または無効なパッケージバージョンなど、パッケージに関連するすべてのエラーに関する情報を返します。 このコマンドレットは、 **sft**ファイルを解析したり、詳細な検証を実行したりしません。 このコマンドレットのオプションと基本的な機能の詳細については、PowerShell cmdline を使用して「」と入力 `Test-AppvLegacyPackage -?` します。

    -   ConvertFrom-AppvLegacyPackage –既存のパッケージを変換するには、を入力 `ConvertFrom-AppvLegacyPackage c:\contentStore c:\convertedPackages` します。 このコマンドは、 `c:\contentStore` 既存のパッケージの場所を表します。これは、生成された `c:\convertedPackages` app-v 5.1 仮想アプリケーションパッケージファイルが保存される出力ディレクトリです。 既定では、新しい名前を指定しない場合は、古いパッケージ名が App-v 5.1 ファイル名として使われます。

        さらに、パッケージコンバーターは、パッケージをストリームフォールトに設定することによって、app-v 5.1 でパッケージのパフォーマンスを最適化します。  これはプライマリ機能ブロックよりもパフォーマンスが高く、パッケージを完全にダウンロードできます。 フラグ**Downloadfullpackageonfirstlaunch**を使用すると、パッケージを変換して、既定でパッケージが完全にダウンロードされるように設定することができます。

        **注**  
        出力ディレクトリを指定する前に、出力ディレクトリを作成する必要があります。



~~~
**Advanced Conversion Tips**

-   Piping - PowerShell supports piping. Piping allows you to call `dir c:\contentStore\myPackage | Test-AppvLegacyPackage`. In this example, the directory object that represents `myPackage` will be given as input to the `Test-AppvLegacyPackage` command and bound to the `-Source` parameter. Piping like this is especially useful when you want to batch commands together; for example, `dir .\ | Test-AppvLegacyPackage | ConvertFrom-AppvLegacyAppvPackage -Target .\ConvertedPackages`. This piped command would test the packages and then pass those objects on to actually be converted. You can also apply a filter on packages without errors or only specify a directory which contains an **.sprj** file or pipe them to another cmdlet that adds the filtered package to the server or publishes them to the App-V 5.1 client.

-   Batching - The PowerShell command enables batching. More specifically, the cmdlets support taking a string\[\] object for the `-Source` parameter which represents a list of directory paths. This allows you to enter `$packages = dir c:\contentStore` and then call `ConvertFrom-AppvLegacyAppvPackage-Source $packages -Target c:\ConvertedPackages` or to use piping and call `dir c:\ContentStore | ConvertFrom-AppvLegacyAppvPackage -Target C:\ConvertedPackages`.

-   Other functionality - PowerShell has other built-in functionality for features such as aliases, piping, lazy-binding, .NET object, and many others. All of these are usable in PowerShell and can help you create advanced scenarios for the Package Converter.

**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 関連トピック


[APP-V 5.1 の操作](operations-for-app-v-51.md)









