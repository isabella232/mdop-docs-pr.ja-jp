---
title: User Experience Virtualization 1.0 について
description: User Experience Virtualization 1.0 について
author: dansimp
ms.assetid: 3758b100-35a8-4e10-ac08-f583fb8ddbd9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6010f9c4ebc260eec0324fb880dc2c92fd675130
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822714"
---
# User Experience Virtualization 1.0 について


Microsoft User Experience Virtualization (UE-V) は、ユーザーによって行われた変更をアプリケーションの設定と Windows オペレーティングシステムの設定に対して監視します。 ユーザー設定は、設定の保存場所にキャプチャされ、中央に配置されます。 これらの設定は、デスクトップコンピューター、ノート pc、仮想デスクトップインフラストラクチャ (VDI) セッションなど、ユーザーによってアクセスされるさまざまなコンピューターに適用することができます。

ユーザーエクスペリエンスの仮想化では、設定場所テンプレートを使用して、ユーザーコンピューター上のどのアプリケーションと Windows 設定を監視および一元管理するかを指定します。 設定場所テンプレートは、各アプリケーションまたはオペレーティングシステムの設定に関連付けられているファイルとレジストリの場所を指定する XML ファイルです。 このテンプレートには、設定の値は含まれていません。これには、監視される設定の場所のみが含まれます。

ユーザーがコンピューターを操作している場合は、アプリケーションの設定と Windows 設定が UE-V によって監視されます。 アプリケーション設定の値は、ユーザーがアプリケーションを閉じたときに、設定ストレージサーバーに格納されます。 Windows 設定の値は、ユーザーがログオフするとき、コンピューターがロックされているとき、またはコンピューターからリモートで接続を解除したときに保存されます。

管理者は、UE-V 設定の場所テンプレートを作成して、どのエンタープライズアプリケーション設定をローミングするかを指定できます。 UE-V には、一部の Microsoft アプリケーションや Windows 設定用の設定場所テンプレートのセットが含まれています。 UE-V の既定のアプリケーションと設定の一覧については、「 [ue-v 1.0 を使用して同期するアプリケーションを計画](planning-which-applications-to-synchronize-with-ue-v-10.md)する」を参照してください。

## UEV 1.0 リリースノート


詳細と、ドキュメントに組み込まれていない最新ニュースについては、「 [Microsoft User Experience Virtualization (ue-v) 1.0 のリリースノート](microsoft-user-experience-virtualization--ue-v--10-release-notes.md)」を参照してください。

## 関連トピック


[User Experience Virtualization 1.0 の概要](getting-started-with-user-experience-virtualization-10.md)

[Microsoft User Experience Virtualization (UE-V) 1.0](index.md)

[UE-V 1.0 のアーキテクチャの概要](high-level-architecture-for-ue-v-10.md)

 

 





