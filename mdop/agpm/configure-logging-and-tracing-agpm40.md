---
title: ログとトレースを構成する
description: ログとトレースを構成する
author: dansimp
ms.assetid: 2418cb6a-7189-4080-8fe2-9c8d47dec62c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bfc56d418ae83cbc5db24246bfac057305629df7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818967"
---
# ログとトレースを構成する


管理用テンプレートを使用して、オプションのログとトレースを一元的に構成できます。 これは、高度なグループポリシー管理 (AGPM) に関連した問題を診断するときに役立ちます。

AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、これらの手順で使用するグループポリシーオブジェクト (GPO) を作成した承認者のユーザーアカウント、または AGPM で必要なアクセス許可を持つユーザーアカウントは、これらの手順を完了するために必要です。 さらに、agpm サーバーへのアクセス権を持つユーザーアカウントは、AGPM サーバーでログを開始するために必要です。 詳細については、このトピックの「その他の考慮事項」を参照してください。

**AGPM のログとトレースを構成するには**

1.  [**グループポリシー管理コンソール**] ツリーで、ログとトレースを有効にするすべてのグループポリシー管理者に適用される GPO を編集します。 詳細については、「 [GPO を編集する](editing-a-gpo-agpm40.md)」を参照してください。

2.  [**グループポリシー管理エディター** ] ウィンドウで、[**コンピューターの構成**]、[**ポリシー**]、[**管理用テンプレート**]、[Windows コンポーネント]、[ **AGPM**] の**各項目**をクリックします。

3.  詳細ウィンドウで、[ **AGPM: ログを構成する**] をダブルクリックします。

4.  [**プロパティ**] ウィンドウで、[**有効**] をクリックし、ログに記録する詳細レベルを構成します。

5.  **[OK]** をクリックします。

6.  [**グループポリシー管理エディター** ] ウィンドウを閉じます。 (詳細については、「 [GPO の展開](deploy-a-gpo-agpm40.md)」を参照してください)。グループポリシーが更新された後、agpm サービスを再起動して、AGPM サーバーでのログの開始、変更、停止を行う必要があります。 グループポリシー管理者は、GPMC を閉じて再起動し、コンピューターのログの開始、変更、または停止を行う必要があります。

    **トレースファイルの場所**:

    -   クライアント:%LocalAppData%\\Microsoft\\AGPM\\agpm.log

    -   サーバー:%ProgramData%\\Microsoft\\AGPM\\agpmserv.log

### その他の考慮事項

-   AGPM のログとトレースを構成するには、GPO の編集と展開が可能である必要があります。 詳細については、「 [gpo を編集](editing-a-gpo-agpm40.md)する」と「 [gpo を展開](deploy-a-gpo-agpm40.md)する」を参照してください。

### その他の参照情報

-   [高度なグループ ポリシーの管理の構成](configuring-advanced-group-policy-management-agpm40.md)

 

 





