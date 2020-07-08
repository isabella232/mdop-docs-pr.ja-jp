---
title: ユーザーの BitLocker 暗号化の除外を管理する方法
description: ユーザーの BitLocker 暗号化の除外を管理する方法
author: dansimp
ms.assetid: 1bfd9d66-6a9a-4d0e-b54a-e5a6627f5ada
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d5530701fd208d42dc1f6774fac11ee9ca2036b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825074"
---
# ユーザーの BitLocker 暗号化の除外を管理する方法


Microsoft BitLocker の管理と監視 (MBAM) を使用すると、ユーザーが必要としないユーザーがいる場合、またはドライブを暗号化しておく必要があるユーザーがいる場合に、除外して BitLocker 保護を管理することができます。

ユーザーに対して BitLocker 保護を適用除外するには、ユーザーに対して、除外を要求するために使用する連絡先の電話番号、web ページ、または郵送先住所をユーザーに提供するインフラストラクチャを作成する必要があります。 また、免除ユーザーは、明示的なユーザーのために特別に作成されたグループポリシーオブジェクトのセキュリティグループに追加される必要があります。 このセキュリティグループのメンバーがコンピューターにログオンすると、ユーザーのグループポリシー設定により、ユーザーは BitLocker 保護から除外されていることが示されます。 ユーザーのグループポリシー設定によってコンピューターのポリシーが上書きされ、コンピューターは BitLocker 暗号化から除外されたままになります。

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
<td align="left"><p>BitLocker 保護はコンピューターに適用されます</p></td>
<td align="left"><p>BitLocker 保護がコンピューターに適用されない</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ユーザの除外</strong></p></td>
<td align="left"><p>BitLocker 保護がコンピューターに適用されない</p></td>
<td align="left"><p>BitLocker 保護がコンピューターに適用されない</p></td>
</tr>
</tbody>
</table>

 

**ユーザーを BitLocker 暗号化から除外するには**

1.  BitLocker 暗号化要件からユーザーの除外を管理するために使用される ActiveDirectoryDomainServices セキュリティグループを作成します。

2.  Microsoft BitLocker の管理と監視のグループポリシーテンプレートを使用して、グループポリシーオブジェクトの設定を作成し、前の手順で作成した Active Directory グループに関連付けます。 ユーザーを適用しないためのポリシー設定は、 **userconfiguration¥管理 Templates\\Windows Components\\MDOP MBAM (BitLocker 管理)** の下にあります。

3.  BitLocker を適用除外されたユーザーのセキュリティグループを作成した後、このグループに、除外を要求しているユーザーの名前を追加します。 ユーザーが BitLocker によって制御されているコンピューターにログオンすると、MBAM クライアントはユーザーの適用除外ポリシー設定を確認し、ユーザーが BitLocker 除外セキュリティグループの一部であるかどうかに基づいて保護を中断します。

    **重要** 共有コンピューターのシナリオでは、ユーザーの例外を使用する場合は特別な考慮事項が必要です。 非適用ユーザーが適用除外ユーザーと共有しているコンピューターにログオンしている場合、そのコンピューターは暗号化されている可能性があります。

     

**ユーザーが BitLocker 暗号化の除外を要求できるようにするには**

1.  MBAM ポリシーテンプレートを使用してユーザーの免税ポリシーを構成した場合、ユーザーは MBAM クライアントを通じて BitLocker 保護から除外を要求できます。

2.  ユーザーが暗号化する必要があるコンピューターにログオンすると、コンピューターが暗号化されていることを知らせる通知が送信されます。 [除外を**要求**する] を選択し、**後**で選択して暗号化を延期するか、[**開始**] を選択して BitLocker 暗号化を受け入れます。

    **注** [**除外を要求**する] を選択すると、ユーザーの除外ポリシーで設定されている最長時間が経過するまで、BitLocker 保護を延期します。

     

3.  ユーザーが [**除外を要求**する] を選択すると、組織の BitLocker 管理グループに連絡するように指示する通知が表示されます。 ユーザーの免税ポリシーを構成する方法に応じて、ユーザーには次の1つ以上の連絡先メソッドが用意されています。

    -   電話番号

    -   Web ページの URL

    -   郵送先住所

    除外要求を受信した後、MBAM 管理者は、ユーザーを BitLocker の除外された Active Directory グループに追加することが適切であるかどうかを判断できます。

    **注** ユーザーが免税要求を送信すると、MBAM エージェントは、ユーザーに対して "一時的に除外" として報告し、次に、設定された日数が経過すると、コンピューターのコンプライアンスを再確認します。 MBAM 管理者が除外要求を拒否した場合、[除外要求] オプションは無効になり、ユーザーは除外を再度要求することはできなくなります。

     

## 関連トピック


[MBAM 2.0 機能の管理](administering-mbam-20-features-mbam-2.md)

 

 





