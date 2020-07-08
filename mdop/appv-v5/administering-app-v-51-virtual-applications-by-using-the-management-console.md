---
title: 管理コンソールを使用した APP-V 5.1 仮想アプリケーションの管理
description: 管理コンソールを使用した APP-V 5.1 仮想アプリケーションの管理
author: dansimp
ms.assetid: a4d078aa-ec54-4fa4-9463-bfb3b971d724
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 63ec965519bedef08b09c961dc5d1c90e1d8d694
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814866"
---
# 管理コンソールを使用した APP-V 5.1 仮想アプリケーションの管理


Microsoft Application Virtualization (App-v) 5.1 management server を使って、環境内のパッケージ、接続グループ、およびパッケージアクセスを管理します。 サーバーは、アプリケーションアイコン、ショートカット、ファイルの種類の関連付けを、App-v 5.1 クライアントを実行する承認済みコンピューターに公開します。 1つまたは複数の管理サーバーは、通常、構成およびパッケージ情報用の共通データストアを共有します。

管理サーバーは Active Directory ドメインサービス (AD DS) グループを使用して、ユーザーの承認を管理し、データベースとデータストアを管理するための SQL Server がインストールされています。

管理サーバーではアプリケーションがオンデマンドでエンドユーザーにストリーミング配信されるため、これらのサーバーは、信頼性の高い高帯域幅の Lan を備えたシステム構成に最適です。 管理サーバーは、次のコンポーネントで構成されています。

-   管理サーバー-管理サーバーを使用して、パッケージと接続グループを管理します。

-   発行サーバー–公開サーバーを使用して、App-v 5.1 クライアントを実行しているコンピューターにパッケージを展開します。

-   管理データベース-管理データベースを使用して、パッケージアクセスを管理し、サーバーの同期を管理サーバーと公開します。

## 管理コンソールのタスク


App-v 5.1 管理コンソールで実行できる一般的なタスクは、次のとおりです。

-   [管理コンソールに接続する方法](how-to-connect-to-the-management-console-51.md)

-   [管理コンソールを使用してパッケージを追加またはアップグレードする方法](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md)

-   [管理コンソールを使用してパッケージへのアクセスを構成する方法](how-to-configure-access-to-packages-by-using-the-management-console-51.md)

-   [管理コンソールを使用してパッケージを公開する方法](how-to-publish-a-package-by-using-the-management-console-51.md)

-   [管理コンソールでパッケージを削除する方法](how-to-delete-a-package-in-the-management-console-51.md)

-   [管理コンソールを使用して管理者を追加または削除する方法](how-to-add-or-remove-an-administrator-by-using-the-management-console51.md)

-   [管理コンソールを使用して公開サーバーを登録および登録解除する方法](how-to-register-and-unregister-a-publishing-server-by-using-the-management-console51.md)

-   [APP-V 5.1 管理コンソールを使用してカスタム構成ファイルを作成する方法](how-to-create-a-custom-configuration-file-by-using-the-app-v-51-management-console.md)

-   [管理コンソールを使用してアクセス権限と構成を別のバージョンのパッケージに転送する方法](how-to-transfer-access-and-configurations-to-another-version-of-a-package-by-using-the-management-console51.md)

-   [管理コンソールを使用して特定の AD グループの仮想アプリケーションの拡張機能をカスタマイズする方法](how-to-customize-virtual-applications-extensions-for-a-specific-ad-group-by-using-the-management-console51.md)

-   [管理コンソールを使用してアプリケーションと既定の仮想アプリケーション拡張機能を表示して構成する方法](how-to-view-and-configure-applications-and-default-virtual-application-extensions-by-using-the-management-console-beta.md)

App-v 5.1 管理コンソールの主な要素は次のとおりです。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">[管理コンソール] タブ</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>[パッケージ] タブ</p></td>
<td align="left"><p>パッケージ <strong> </strong> を追加またはアップグレードするには、[パッケージ] タブを使います。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[接続グループ] タブ</p></td>
<td align="left"><p>[ <strong> 接続グループ] タブを使用して、 </strong> 接続グループを管理します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>[サーバー] タブ</p></td>
<td align="left"><p>[ <strong> サーバー </strong> ] タブを使って、新しいサーバーを登録します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[管理者] タブ</p></td>
<td align="left"><p>[ <strong> 管理者 </strong> ] タブを使用して、app-v 5.1 環境で管理者を登録、追加、または削除します。</p></td>
</tr>
</tbody>
</table>

 

**重要** Web 管理コンソールを開くブラウザーで JavaScript を有効にする必要があります。

 






## <a href="" id="other-resources-for-this-app-v-5-1-deployment-"></a>この App-v 5.1 の展開に関するその他のリソース


-   [Microsoft Application Virtualization 5.1 管理者ガイド](microsoft-application-virtualization-51-administrators-guide.md)

-   [APP-V 5.1 の操作](operations-for-app-v-51.md)

 

 





