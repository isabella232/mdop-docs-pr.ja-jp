---
title: ユーザーの BitLocker 暗号化の除外を管理する方法
description: ユーザーの BitLocker 暗号化の除外を管理する方法
author: dansimp
ms.assetid: 48d69721-504f-4524-8a04-b9ce213ac9b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c3d70558a65c3288174413d6c36cc9c77bc9eaa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812963"
---
# ユーザーの BitLocker 暗号化の除外を管理する方法


Microsoft BitLocker の管理と監視 (MBAM) を使って、不要なユーザーまたはドライブを暗号化する必要がないユーザーを除外することで、BitLocker 保護を管理することができます。

ユーザーを BitLocker による保護から除外するには、まず、そのような例外をサポートするためのインフラストラクチャを組織で作成する必要があります。 サポートインフラストラクチャには、除外を要求するための連絡先の電話番号、web ページ、またはメールアドレスを含めることができます。 また、すべての適用除外ユーザーは、特定のユーザーに対して特別に作成されたグループポリシーのセキュリティグループに追加される必要があります。 このセキュリティグループのメンバーがコンピューターにログオンすると、ユーザーグループポリシーには、ユーザーが BitLocker 保護から除外されていることが示されます。 ユーザーポリシーによってコンピューターのポリシーが上書きされ、コンピューターは BitLocker 暗号化から除外されたままになります。

**注** コンピューターが既に BitLocker で保護されている場合は、ユーザーの除外ポリシーには影響ありません。

 

次の表は、適用除外の設定に基づいて、BitLocker の保護を適用する方法を示しています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ユーザーの状態</th>
<th align="left">除外されていないコンピューター</th>
<th align="left">コンピューターの免税</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>ユーザーは免税されません</strong></p></td>
<td align="left"><p>BitLocker 保護はコンピューターに適用されます。</p></td>
<td align="left"><p>BitLocker 保護はコンピューターに適用されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ユーザの除外</strong></p></td>
<td align="left"><p>BitLocker 保護はコンピューターに適用されません。</p></td>
<td align="left"><p>BitLocker 保護はコンピューターに適用されません。</p></td>
</tr>
</tbody>
</table>

 

**ユーザーを BitLocker 暗号化から除外するには**

1.  ActiveDirectoryDomainServices セキュリティグループを作成して、BitLocker 暗号化からユーザーの除外を管理するために使用されます。

2.  MBAM グループポリシーテンプレートを使用して、グループポリシーオブジェクトの設定を作成します。 グループポリシーオブジェクトを、前の手順で作成した Active Directory グループに関連付けます。 ユーザーが BitLocker 暗号化の除外を要求できるようにするために必要なポリシー設定の詳細については、「 [MBAM 1.0 グループポリシーの要件を計画](planning-for-mbam-10-group-policy-requirements.md)する」の「ユーザーの免税ポリシーを構成する」を参照してください。

3.  BitLocker を適用除外されたユーザーのセキュリティグループを作成した後、このグループに、除外を要求しているユーザーの名前を追加します。 ユーザーが BitLocker によって制御されているコンピューターにログオンすると、MBAM クライアントはユーザーの免税ポリシー設定を確認し、ユーザーが BitLocker の除外セキュリティグループの一部であるかどうかに基づいて保護を中断します。

    **注** 共有コンピューターのシナリオでは、ユーザーの除外について特に考慮する必要があります。 非適用ユーザーが適用除外ユーザーと共有しているコンピューターにログオンしている場合、そのコンピューターは暗号化されている可能性があります。

     

**ユーザーが BitLocker 暗号化から除外を要求できるようにするには**

1.  MBAM ポリシーテンプレートを使用してユーザーの除外ポリシーを構成した後、ユーザーは MBAM クライアントを介して BitLocker 保護から除外を要求することができます。

2.  MBAM Hardware Compatibility リストと**互換性**があるとマークされているコンピューターにユーザーがログオンすると、コンピューターが暗号化されていることを知らせる通知がユーザーに表示されます。 ユーザーは [**除外を要求**する] を選択し、**後**で選択して暗号化を延期するか、[**開始**] を選択して BitLocker 暗号化を受け入れます。

    **注** [**除外を要求**する] を選択すると、ユーザーの除外ポリシーで設定されている最長時間が経過するまで、BitLocker の保護が延期されます。

     

3.  ユーザーが [**除外の要求**] を選択すると、組織の BitLocker 管理グループに連絡するようにユーザーに通知されます。 ユーザーの免税ポリシーを構成する方法に応じて、ユーザーには次の1つ以上の連絡先メソッドが用意されています。

    -   電話番号

    -   Web ページの URL

    -   郵送先住所

    要求の提出後、MBAM 管理者は、BitLocker の除外可能な Active Directory グループにユーザーを追加することが適切であるかどうかを判断できます。

    **注** ユーザーの適用除外ポリシーの [延期時間] の有効期限が切れた後は、暗号化ポリシーに適用除外を要求するオプションがユーザーに表示されなくなります。 この時点で、ユーザーは、BitLocker 保護から適用除外を受け取るために、MBAM 管理者に直接連絡する必要があります。

     

## 関連トピック


[MBAM 1.0 機能の管理](administering-mbam-10-features.md)

 

 





