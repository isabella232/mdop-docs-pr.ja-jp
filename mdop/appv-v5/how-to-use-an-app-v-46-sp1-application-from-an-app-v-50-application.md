---
ms.reviewer: ''
title: App-v 5.0 アプリケーションから app-v 4.6 アプリケーションを使用する方法
description: App-v 5.0 アプリケーションから app-v 4.6 アプリケーションを使用する方法
ms.assetid: 4e78cb32-9c8b-478e-ae8b-c474a7e42487
author: msfttracyp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 8b29e861b97d18e427f6a8247a1f731be2dc0889
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813643"
---
# App-v 5.0 アプリケーションから app-v 4.6 アプリケーションを使用する方法

*注:** App-V 4.6 はメインストリームサポートを終了しました。 以下は、App-v 4.6 SP3 パッケージに適用されます。

スタンドアロンクライアントで app-v 5.0 アプリケーションを使用して app-v 4.6 アプリケーションを実行するには、次の手順に従います。

**スタンドアロンクライアントでアプリケーションを実行するには**

1.  環境内で2つのアプリケーションを同時に開くことができます。 たとえば、Microsoft Outlook や Adobe Acrobat Reader などです。 Adobe Acrobat を使って作成されたメールの添付ファイルにアクセスできます。

2.  App-v 5.0 形式を使用して、パッケージを変換するか、いずれかのアプリケーション用の新しいパッケージを作成します。 パッケージの変換の詳細については、「[アプリ-v 4.6 パッケージから、特定のコンピューター上のすべてのユーザー用に、変換されたアプリ-v 5.0 パッケージに拡張ポイントを移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)」を参照してください。また、[特定のユーザーに対して、拡張ポイントを App-v 4.6 パッケージから App-v 5.0 に移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)を説明します。

3.  App-v 5.0 管理コンソールを使用して、パッケージを追加し、プロビジョニングします。 パッケージの追加とプロビジョニングの詳細については、「[管理コンソールを使用してパッケージを追加またはアップグレードする方法](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)」と「[管理コンソールを使用してパッケージへのアクセスを構成する方法](how-to-configure-access-to-packages-by-using-the-management-console-50.md)」を参照してください。

4.  変換されたアプリケーションは、App-v 5.0 を使って実行されるようになり、もう1つのアプリケーションを開くことができます。 たとえば、Microsoft Office パッケージを App-v 5.0 パッケージに変換しても、Adobe Acrobat が依然として App V 4.6 パッケージとして実行されている場合は、Microsoft Outlook を使用して Adobe Acrobat Reader の添付ファイルを開くことができます。

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.0 の操作](operations-for-app-v-50.md)

 

 








