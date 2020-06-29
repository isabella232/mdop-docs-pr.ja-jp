---
title: クライアントのイベント ログ
description: クライアントのイベント ログ
author: dansimp
ms.assetid: d5c2f270-db6a-45f1-8557-8c6fb28fd568
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7324d07bf018944fcbe24168bba2e9abea9cea41
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824194"
---
# クライアントのイベント ログ

MBAM クライアントイベントログは、イベントビューアー (アプリケーションとサービスログ) にあります。 Microsoft – Windows – MBAM 操作のパス。
次の表は、MBAM クライアントで発生する可能性のあるイベント Id を示しています。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">イベント ID</th>
<th align="left">チャネル</th>
<th align="left">イベントの記号</th>
<th align="left">メッセージ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>件</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>Volumeenactの成功</p></td>
<td align="left"><p>MBAM ポリシーが正常に適用されました。</p></td>
</tr>
<tr class="even">
<td align="left"><p>両面</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>Volumeenactのエラー</p></td>
<td align="left"><p>MBAM ポリシーの適用中にエラーが発生しました。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>-</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>Transferstatusdatasucの場合</p></td>
<td align="left"><p>暗号化の状態データが正常に送信されました。</p></td>
</tr>
<tr class="even">
<td align="left"><p>4d</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>TransferStatusDataFailed</p></td>
<td align="left"><p>暗号化状態データの送信中にエラーが発生しました。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>個</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>SystemVolumeNotFound</p></td>
<td align="left"><p>システムボリュームがありません。 オペレーティングシステムドライブを暗号化するには、SystemVolume が必要です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ファイブ</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>TPMNotFound</p></td>
<td align="left"><p>TPM ハードウェアがありません。 Tpm は、任意の TPM プロテクターでオペレーティングシステムドライブを暗号化するために必要です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>常用</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>MachineHWExempted</p></td>
<td align="left"><p>コンピューターは暗号化から除外されます。 マシンのハードウェア状態: 除外</p></td>
</tr>
<tr class="even">
<td align="left"><p>折り</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>MachineHWUnknown</p></td>
<td align="left"><p>コンピューターは暗号化から除外されます。 マシンのハードウェア状態: 不明</p></td>
</tr>
<tr class="odd">
<td align="left"><p>以内</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>HWCheckFailed</p></td>
<td align="left"><p>ハードウェアの除外チェックに失敗しました。</p></td>
</tr>
<tr class="even">
<td align="left"><p>14</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>Userisex</p></td>
<td align="left"><p>ユーザーは暗号化されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>14</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>UserIsWaiting</p></td>
<td align="left"><p>ユーザーが除外を要求しました。</p></td>
</tr>
<tr class="even">
<td align="left"><p>マート</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>UserExemptionCheckFailed</p></td>
<td align="left"><p>ユーザーの除外チェックに失敗しました。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>16</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>UserPostponed</p></td>
<td align="left"><p>ユーザーが暗号化処理を延期した。</p></td>
</tr>
<tr class="even">
<td align="left"><p>17</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>TPMInitializationFailed</p></td>
<td align="left"><p>TPM の初期化に失敗しました。 ユーザーが BIOS の変更を拒否しました。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>才</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>CoreServiceDown</p></td>
<td align="left"><p>MBAM Recovery およびハードウェアサービスに接続できません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>#</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>CoreServiceUp</p></td>
<td align="left"><p>MBAM Recovery とハードウェアサービスに正常に接続されました。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>超える</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>ポリシーの不一致</p></td>
<td align="left"><p>MBAM ポリシーが競合しているか、破損しています。</p></td>
</tr>
<tr class="even">
<td align="left"><p>2004</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>競合している Osvolumepolicies</p></td>
<td align="left"><p>OS のボリューム暗号化ポリシーが競合していることを検出しました。 OS ドライブプロテクターに関連する BitLocker および MBAM ポリシーを確認します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>22</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>すべての Fddvolumeポリシーの競合</p></td>
<td align="left"><p>データドライブのボリューム暗号化ポリシーが競合していることを検出しました。 FDD drive プロテクターに関連する BitLocker および MBAM ポリシーを確認します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>日</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>暗号化 Dra</p></td>
<td align="left"><p>暗号化中にエラーが発生しました。 Windows 8.1 以前のコンピューターでは、FIPS モードでデータ回復エージェント (DRA) プロテクターが必要です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>日</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>TpmOwnerAuthEscrowed</p></td>
<td align="left"><p>TPM OwnerAuth が預託たりされました。</p></td>
</tr>
<tr class="even">
<td align="left"><p>29</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>RecoveryKeyEscrowed</p></td>
<td align="left"><p>ボリュームの BitLocker 回復キーが預託たりされました。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>求める</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>RecoveryKeyReset</p></td>
<td align="left"><p>ボリュームの BitLocker 回復キーが更新されました。</p></td>
</tr>
<tr class="even">
<td align="left"><p>31</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>EnforcePolicyDateSet</p></td>
<td align="left"><p>ボリュームの [ポリシーの日付を適用] の <em> &lt; 日付 &gt; </em> が設定されている</p></td>
</tr>
<tr class="odd">
<td align="left"><p>32</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>EnforcePolicyDateCleared</p></td>
<td align="left"><p>ボリュームの [ポリシーの日付を適用] の日付 <em> &lt; &gt; </em> が消去されました。</p></td>
</tr>
<tr class="even">
<td align="left"><p>33</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>TpmLockOutResetSucceeded</p></td>
<td align="left"><p>TPM ロックアウトが正常にリセットされました。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>34</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>TpmLockOutResetFailed</p></td>
<td align="left"><p>TPM ロックアウトのリセットに失敗しました。</p></td>
</tr>
<tr class="even">
<td align="left"><p>35</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>TpmOwnerAuthRetrievalSucceeded</p></td>
<td align="left"><p>MBAM サービスから TPM OwnerAuth が正常に取得されました。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>36</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>TpmOwnerAuthRetrievalFailed</p></td>
<td align="left"><p>MBAM サービスから TPM OwnerAuth を取得できませんでした。</p></td>
</tr>
<tr class="even">
<td align="left"><p>37</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>の使い方に失敗しました</p></td>
<td align="left"><p>WMI プロバイダーの DLL 検索パスを更新できませんでした。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>38</p></td>
<td align="left"><p>管理者</p></td>
<td align="left"><p>TimedOutWaitingForWmiProvider</p></td>
<td align="left"><p>エージェントの停止-MBAM WMI プロバイダーインスタンスを待機しています。</p></td>
</tr>
<tr class="even">
<td align="left"><p>39</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>RemovableDriveMounted</p></td>
<td align="left"><p>リムーバブルドライブがマウントされました。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>40</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>Removableドライブのマウント解除</p></td>
<td align="left"><p>リムーバブルドライブがアンマウントされました。</p></td>
</tr>
<tr class="even">
<td align="left"><p>41</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>失敗した通信に到達可能</p></td>
<td align="left"><p>MBAM 回復およびハードウェアサービスのブロックに接続できない場合、MBAM ポリシーはボリュームに正常に適用されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>42</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>FailedToEnactLockedVolume</p></td>
<td align="left"><p>ロックされているボリューム状態では、MBAM ポリシーがボリュームに正常に適用されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>43</p></td>
<td align="left"><p>実施</p></td>
<td align="left"><p>Transferstatusdatafのアクセス到達可能</p></td>
<td align="left"><p>MBAM コンプライアンスとステータスサービスへの接続に失敗したため、暗号化状態データの転送ができませんでした。</p></td>
</tr>
</tbody>
</table>

 


## 関連トピック
[MBAM 2.5 テクニカル リファレンス](technical-reference-for-mbam-25.md)

[サーバーのイベント ログ](server-event-logs.md)

 


## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





