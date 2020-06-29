---
title: MED-V ワークスペース ポリシーの構成
description: MED-V ワークスペース ポリシーの構成
author: dansimp
ms.assetid: 0eaed981-cbf3-4b16-a4b7-4705c5705dc7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 84bdae38b1c801e2c2be2a3dd1d12dd2ca7d932d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824857"
---
# MED-V ワークスペース ポリシーの構成


MED-V ワークスペースポリシーは、仮想化された環境やアプリケーションがホストコンピューターで実行する方法を定義する、構成可能な設定のグループです。 このセクションのトピックでは、MED-V ワークスペースポリシーのすべての構成可能な設定について説明し、これらの設定が MED-V ワークスペースに与える影響についても説明します。

次の MED-V ワークスペースの種類を使用できます。

-   **Persistent**: 永続的な med-v ワークスペースでは、ユーザーが med-v ワークスペースに対して行ったすべての変更と追加が、セッション間の med-v ワークスペースに保存されます。 さらに、永続的な MED-V ワークスペースは、通常、ドメイン環境で使用されます。

-   **Revertible**: Revertible MED ワークスペースでは、各セッションの完了時 (つまり、med-v ワークスペースが停止されたとき) に、med-v ワークスペースは展開時に元の状態に戻ります。 ユーザーが行った変更や追加は、セッション間の MED-V ワークスペースに保存されません。 Revertible MED ワークスペースは、ドメイン環境では使用できません。

ポリシーがユーザーに展開された後に、med-v ワークスペースの種類を再構成することは推奨されないため、MED-V ワークスペースを展開する前に作成している MED-V ワークスペースの種類を決定することが重要です。

**注** ポリシーを構成するときに、入力されていない必須フィールドの横に警告記号が表示されます。 必須フィールドが入力されていない場合は、その記号もタブに表示されます。

 

## このセクションの内容


<a href="" id="how-to-apply-general-settings-to-a-med-v-workspace"></a>[MED-V ワークスペースに全般設定を適用する方法](how-to-apply-general-settings-to-a-med-v-workspace.md)  
MED-V ワークスペースの全般的な設定と、それらをポリシーに適用する方法について説明します。

<a href="" id="how-to-apply-virtual-machine-settings-to-a-med-v-workspace"></a>[MED-V ワークスペースに仮想マシンの設定を適用する方法](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md)  
MED-V ワークスペースの仮想マシン設定と、それらをポリシーに適用する方法について説明します。

<a href="" id="how-to-configure-a-domain-user-or-group"></a>[ドメイン ユーザーまたはグループを構成する方法](how-to-configure-a-domain-user-or-groupmedvv2.md)  
ドメインユーザーとグループを構成する方法について説明します。

<a href="" id="how-to-configure-published-applications"></a>[公開されたアプリケーションを構成する方法](how-to-configure-published-applicationsmedvv2.md)  
公開されているアプリケーションとメニューと、それらをポリシーに適用する方法について説明します。

<a href="" id="how-to-configure-web-settings-for-a-med-v-workspace"></a>[MED-V ワークスペースの Web 設定を構成する方法](how-to-configure-web-settings-for-a-med-v-workspace.md)  
MED-V ワークスペースで利用可能な Web 設定と、それらをポリシーに適用する方法について説明します。

<a href="" id="how-to-configure-the-virtual-machine-setup-for-a-med-v-workspace"></a>[MED-V ワークスペースの仮想マシンのセットアップを構成する方法](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspace.md)  
MED-V ワークスペースの仮想マシンのセットアップと、それをポリシーに適用する方法について説明します。

<a href="" id="how-to-apply-network-settings-to-a-med-v-workspace"></a>[MED-V ワークスペースにネットワーク設定を適用する方法](how-to-apply-network-settings-to-a-med-v-workspace.md)  
MED-V ワークスペースのネットワーク設定と、それらをポリシーに適用する方法について説明します。

<a href="" id="how-to-apply-performance-settings-to-a-med-v-workspace"></a>[MED-V ワークスペースにパフォーマンス設定を適用する方法](how-to-apply-performance-settings-to-a-med-v-workspace.md)  
MED-V ワークスペースのパフォーマンス設定と、それらをポリシーに適用する方法について説明します。

<a href="" id="how-to-import-and-export-a-policy"></a>[ポリシーをインポートおよびエクスポートする方法](how-to-import-and-export-a-policy.md)  
ポリシーをインポートおよびエクスポートする方法について説明します。

 

 





