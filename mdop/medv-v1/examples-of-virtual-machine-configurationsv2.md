---
title: 仮想マシンの構成の例
description: 仮想マシンの構成の例
author: dansimp
ms.assetid: 5937601e-41ab-4ca2-8fa1-3c9154710cd6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b9fc7b1f88b2b30ea149fe73a387826fdbb2a66
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824587"
---
# 仮想マシンの構成の例


次に、一般的な仮想マシン構成の例を示します。1つは永続的な MED-V ワークスペース、もう1つは revertible MED ワークスペースです。

**注** 以下の例は、すべての環境での使用を目的としていません。 環境に合わせて構成を調整します。

 

**永続的な MED-V ワークスペースで一般的なドメインのセットアップを構成するには**

1.  基本イメージで Sysprep を構成して、一意の SID を作成します。 詳細については、「 [med-v 用の仮想 PC イメージの作成](creating-a-virtual-pc-image-for-med-v.md#bkmk-howtoconfiguresysprepformedvimages)」を参照してください。

2.  [ **Vm のセットアップ**] タブで、[ **Vm セットアップの実行**] チェックボックスをオンにします。

3.  [ **VM コンピューター名パターン**] セクションで、コンピューターイメージ名のパターンを構成します。 詳細については、「 [VM コンピューター名パターンプロパティを構成する方法](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)」を参照してください。

4.  [**スクリプトエディター**] をクリックし、[ **VM セットアップスクリプトエディター** ] ダイアログボックスで、次の操作を構成します。

    1.  **コンピューターの名前を変更する**

    2.  **Windows を再起動する**

    3.  **接続を確認する**

    4.  **ドメインに参加する**

    5.  **自動ログオンを無効にする**

    詳細については、「[スクリプト操作を設定する方法](how-to-set-up-script-actions.md)」を参照してください。

5.  [**ポリシー** ] メニューで、[**コミット**] をクリックします。

**Revertible ワークスペースでの一般的なセットアップを構成するには**

1.  [ **Vm のセットアップ**] タブで、[**コンピューター名パターンに基づいて vm の名前を変更**する] チェックボックスをオンにします。

2.  [ **VM コンピューター名パターン**] セクションで、コンピューターイメージ名のパターンを構成します。 詳細については、「 [VM コンピューター名パターンプロパティを構成する方法](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)」を参照してください。

3.  [**ポリシー** ] メニューで、[**コミット**] をクリックします。

## 関連トピック


[MED-V ワークスペースの仮想マシンのセットアップを構成する方法](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspacemedvv2.md)

[VM のコンピューター名パターンのプロパティを構成する方法](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)

[スクリプトのアクションを設定する方法](how-to-set-up-script-actions.md)

 

 





