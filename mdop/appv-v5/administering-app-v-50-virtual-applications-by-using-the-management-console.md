---
title: 管理コンソールを使用した APP-V 5.0 仮想アプリケーションの管理
description: 管理コンソールを使用した APP-V 5.0 仮想アプリケーションの管理
author: dansimp
ms.assetid: e9280dbd-782b-493a-b495-daab25247795
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 10/03/2016
ms.openlocfilehash: 7a71f7c0fd82f8ef9d1efd5b978591b6838a648a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814867"
---
# 管理コンソールを使用した APP-V 5.0 仮想アプリケーションの管理


Microsoft Application Virtualization (App-v) 5.0 management server を使って、環境内のパッケージ、接続グループ、およびパッケージアクセスを管理します。 サーバーは、アプリケーションアイコン、ショートカット、ファイルの種類の関連付けを、App-v 5.0 クライアントを実行する承認済みコンピューターに公開します。 1つまたは複数の管理サーバーは、通常、構成およびパッケージ情報用の共通データストアを共有します。

管理サーバーは Active Directory ドメインサービス (AD DS) グループを使用して、ユーザーの承認を管理し、データベースとデータストアを管理するための SQL Server がインストールされています。

管理サーバーではアプリケーションがオンデマンドでエンドユーザーにストリーミング配信されるため、これらのサーバーは、信頼性の高い高帯域幅の Lan を備えたシステム構成に最適です。 管理サーバーは、次のコンポーネントで構成されています。

-   管理サーバー-管理サーバーを使用して、パッケージと接続グループを管理します。

-   発行サーバー–公開サーバーを使用して、App-v 5.0 クライアントを実行しているコンピューターにパッケージを展開します。

-   管理データベース-管理データベースを使用して、パッケージアクセスを管理し、サーバーの同期を管理サーバーと公開します。

## 管理コンソールのタスク


App-v 5.0 管理コンソールで実行できる一般的なタスクは、次のとおりです。

-   [管理コンソールに接続する方法](how-to-connect-to-the-management-console-beta.md)

-   [管理コンソールを使用してパッケージを追加またはアップグレードする方法](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)

-   [管理コンソールを使用してパッケージへのアクセスを構成する方法](how-to-configure-access-to-packages-by-using-the-management-console-50.md)

-   [管理コンソールを使用してパッケージを公開する方法](how-to-publish-a-package-by-using-the-management-console-50.md)

-   [管理コンソールでパッケージを削除する方法](how-to-delete-a-package-in-the-management-console-beta.md)

-   [管理コンソールを使用して管理者を追加または削除する方法](how-to-add-or-remove-an-administrator-by-using-the-management-console.md)

-   [管理コンソールを使用して公開サーバーを登録および登録解除する方法](how-to-register-and-unregister-a-publishing-server-by-using-the-management-console.md)

-   [APP-V 5.0 管理コンソールを使用してカスタム構成ファイルを作成する方法](how-to-create-a-custom-configuration-file-by-using-the-app-v-50-management-console.md)

-   [管理コンソールを使用してアクセス権限と構成を別のバージョンのパッケージに転送する方法](how-to-transfer-access-and-configurations-to-another-version-of-a-package-by-using-the-management-console.md)

-   [管理コンソールを使用して特定の AD グループの仮想アプリケーションの拡張機能をカスタマイズする方法](how-to-customize-virtual-applications-extensions-for-a-specific-ad-group-by-using-the-management-console.md)

-   [管理コンソールでアプリケーションと既定の仮想アプリケーションの拡張機能を構成する](configure-applications-and-default-virtual-application-extensions-in-management-console.md)

App-v 5.0 管理コンソールの主な要素は次のとおりです。

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
<td align="left"><p>概要</p></td>
<td align="left"><p></p>
<ul>
<li><p><strong>App-v </strong> - 5.0 sequencer の使用に関する一般的な情報を確認するには、このオプションを選択します。</p></li>
<li><p><strong>[アプリケーションパッケージライブラリ </strong> ]: <strong> 管理コンソールの [パッケージ] ページを開くには、このオプションを選択し </strong> ます。 このページを使用して、サーバーに追加されたパッケージを確認します。 また、接続グループを管理することも、パッケージを追加またはアップグレードすることもできます。</p></li>
<li><p><strong></strong>[サーバー]: <strong> 管理コンソールの [サーバー] ページを開くには、このオプションを選択し </strong> ます。 このページを使用して、App-v 5.0 インフラストラクチャに登録されているサーバーの一覧を確認します。</p></li>
<li><p><strong>クライアント </strong> – app-v 5.0 クライアントに関する一般的な情報を確認するには、このオプションを選択します。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>[パッケージ] タブ</p></td>
<td align="left"><p>パッケージ <strong> </strong> を追加またはアップグレードするには、[パッケージ] タブを使います。 [接続グループ] をクリックして、接続グループを管理することもでき <strong> </strong> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>[サーバー] タブ</p></td>
<td align="left"><p>[ <strong> サーバー </strong> ] タブを使って、新しいサーバーを登録します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[管理者] タブ</p></td>
<td align="left"><p>[ <strong> 管理者 </strong> ] タブを使用して、app-v 5.0 環境で管理者を登録、追加、または削除します。</p></td>
</tr>
</tbody>
</table>

 






## <a href="" id="other-resources-for-this-app-v-5-0-deployment-"></a>この App-v 5.0 の展開に関するその他のリソース


-   [Microsoft Application Virtualization 5.0 管理者ガイド](microsoft-application-virtualization-50-administrators-guide.md)

-   [APP-V 5.0 の操作](operations-for-app-v-50.md)

 

 





