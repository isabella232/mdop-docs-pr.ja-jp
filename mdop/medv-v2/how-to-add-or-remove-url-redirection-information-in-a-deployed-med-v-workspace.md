---
title: 展開された MED-V ワークスペースの URL リダイレクトの情報を追加または削除する方法
description: 展開された MED-V ワークスペースの URL リダイレクトの情報を追加または削除する方法
author: dansimp
ms.assetid: bf55848d-bf77-452e-aaa5-4dd4868ff5bd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: f0892b16bfc10e6b3f28fe99c51c2c5cedb73d7f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826444"
---
# 展開された MED-V ワークスペースの URL リダイレクトの情報を追加または削除する方法


展開された MED-V ワークスペースの URL リダイレクション情報を編集するには、グループポリシーを使ってシステムレジストリを更新することをお勧めします。 お勧めしませんが、更新された URL リダイレクション情報を使用して、MED-V ワークスペースを再構築および再展開することもできます。

通常、レジストリキーは次の場所にあります。

Computer¥¥ \ Key\ _LOCAL \ _MACHINE ¥¥¥¥¥¥¥¥¥ |

次の複数文字列値が存在する必要があります。 `RedirectUrls`

の値のデータ `RedirectUrls` は、 **Med-v ワークスペースパッケージャー**を使って med-v ワークスペースパッケージをビルドしたときに、リダイレクト用に指定したすべての url の一覧です。 詳細については、「 [Med-v ワークスペースパッケージを作成する](create-a-med-v-workspace-package.md)」を参照してください。

次のいずれかのタスクを実行して、URL リダイレクション情報を追加および削除できます。

-   [URL リダイレクションレジストリキーを編集して、グループポリシーを使用して展開する](#bkmk-editreg)

-   [URL リダイレクションテキストファイルを編集して、MED-V ワークスペースを再構築する](#bkmk-edittext)

<a href="" id="bkmk-editreg"></a>**グループポリシーを使用して URL リダイレクション情報を更新するには**

1.  という名前のレジストリキーの複数文字列値を編集し `RedirectUrls` ます。 この値は、通常、次の場所にあります。

    Computer¥¥ \ Key\ _LOCAL \ _MACHINE ¥¥¥¥¥¥¥¥¥ |

    レジストリキーに Url を追加する場合は、MED-V ワークスペースパッケージを作成するときに必要となりますが、1行あたりに1つの Url を入力します。 詳細については、「 [Med-v ワークスペースパッケージを作成する](create-a-med-v-workspace-package.md)」を参照してください。

2.  グループポリシーを使用して、更新されたレジストリキーを展開します。 グループポリシーの使用方法の詳細については、「[グループポリシーソフトウェアのインストール](https://go.microsoft.com/fwlink/?LinkId=195931)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=195931) 。

**注** URL リダイレクション情報を編集するこの方法は、MED-V のベストプラクティスです。

 

<a href="" id="bkmk-edittext"></a>**更新された URL テキストファイルを使用して、MED-V ワークスペースを再構築するには**

-   リダイレクトリストから Url を追加したり削除したりするもう1つの方法は、URL リダイレクションテキストファイルを更新し、それを使って新しい MED-V ワークスペースを構築することです。 次に、ESD システムなどの展開の標準的なプロセスを使用して、以前と同様に MED-V ワークスペースを再展開することができます。

    **重要** この方法では、URL リダイレクション情報を編集することはお勧めしません。 さらに、MED-V ワークスペースをエンタープライズに再展開する場合は、最初にセットアップをもう一度実行する必要があります。仮想マシンに保存されているデータはすべて失われます。

     

## 関連トピック


[URL のリダイレクトをテストする方法](how-to-test-url-redirection.md)

[MED-V ワークスペースに展開されたアプリケーションの管理](managing-applications-deployed-to-med-v-workspaces.md)

[MED-V ワークスペース パッケージを作成する](create-a-med-v-workspace-package.md)

 

 





