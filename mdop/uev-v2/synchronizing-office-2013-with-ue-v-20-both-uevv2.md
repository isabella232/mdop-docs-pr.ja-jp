---
title: Office 2013 と UE-V 2.0 を同期する
description: Office 2013 と UE-V 2.0 を同期する
author: dansimp
ms.assetid: c46feb6d-28a8-4799-888d-053531dc5842
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c9b079d3f21e6ced689fa2101f5321fa9b1406c8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826887"
---
# Office 2013 と UE-V 2.0 を同期する


Microsoft User Experience Virtualization (UE-V) 2.0 では、UE-V テンプレートギャラリーから利用可能なテンプレートを使用して、Microsoft Office 2013 アプリケーション設定の同期がサポートされています。 Office 2013 Professional Plus の UE-V 5.0 および App-v SP2 のサポートでは、任意の UE-V 対応デバイスまたは仮想化デスクトップから、Office 2013 の仮想化されたインスタンスと同じ操作を行うことができます。

Office 2013 の UE-V アプリケーション設定のサポートを有効にするには、 [Microsoft User Experience Virtualization (ue-v) 2 テンプレートギャラリー](https://go.microsoft.com/fwlink/p/?LinkId=246589)からオフィシャルバージョンの ue-v Office 2013 テンプレートをダウンロードできます。 このリソースは、Microsoft が作成した UE-V の設定場所テンプレートと、コミュニティで開発された設定場所テンプレートを提供します。

## UE-V での Microsoft Office のサポート


UE-V 1.0 および UE-V 2 には、Microsoft Office 2010 の設定場所テンプレートが含まれています。 これらのテンプレートは、UE-V Agent のインストールプロセスの一部として配布および登録されます。 これらのテンプレートは、ユーザーの Office エクスペリエンスをデバイス間で同期するのに役立ちます。 Office 2013 用の UE-V テンプレートは、Office 2010 のテンプレートについてよく似た設定エクスペリエンスを提供します。 Office 365 のエクスペリエンスによってローミングされた Microsoft Office 2013 の設定は、これらの設定に含まれていません。 Office 365 固有の設定のリストについては、「 [office 2013 のユーザーとローミングの設定の概要](https://go.microsoft.com/fwlink/p/?LinkId=391220)」を参照してください。

## 同期された Office 2013 の設定


次の表には、UE-V での Office 2013 サポートの詳細情報が含まれています。

### サポートされている Microsoft Office の UE-V テンプレート

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Office 2013 テンプレート (ue-v ギャラリーで利用可能な UE-V 2.0):</th>
<th align="left">Office 2010 テンプレート (UE-V 1.0 &amp; 1.0 SP1):</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MicrosoftOffice2013Win32.xml</p>
<p>MicrosoftOffice2013Win64.xml</p>
<p>MicrosoftLync2013Win32.xml</p>
<p>MicrosoftLync2013Win64.xml</p></td>
<td align="left"><p>MicrosoftOffice2010Win32.xml</p>
<p>MicrosoftOffice2010Win64.xml</p>
<p>MicrosoftLync2010.xml</p>
<p></p></td>
</tr>
</tbody>
</table>

 

### UE-V テンプレートでサポートされている Microsoft Office アプリケーション

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Access 2013</p>
<p>Microsoft Lync 2013</p>
<p>Microsoft Excel 2013</p>
<p>Microsoft InfoPath 2013</p>
<p>Microsoft OneNote 2013</p>
<p>Microsoft Outlook 2013</p>
<p>Microsoft PowerPoint 2013</p>
<p>Microsoft Project 2013</p>
<p>Microsoft Publisher 2013</p>
<p>Microsoft SharePoint Designer 2013</p>
<p>Microsoft Visio 2013</p>
<p>Microsoft Word 2013</p>
<p>Microsoft Office アップロードマネージャー</p></td>
<td align="left"><p>Microsoft Access 2010</p>
<p>Microsoft Lync 2010</p>
<p>Microsoft Excel 2010</p>
<p>Microsoft InfoPath 2010</p>
<p>Microsoft OneNote 2010</p>
<p>Microsoft Outlook 2010</p>
<p>Microsoft PowerPoint 2010</p>
<p>Microsoft Project 2010</p>
<p>Microsoft Publisher 2010</p>
<p>Microsoft SharePoint Designer 2010</p>
<p>Microsoft Visio 2010</p>
<p>Microsoft Word 2010</p>
<p></p></td>
</tr>
</tbody>
</table>

 

## Office 2013 テンプレートの展開


次のメソッドを使用して、UE-V 設定の場所テンプレートを展開できます。

-   **PowerShell を使用**してテンプレートを登録しています。 Windows PowerShell を使用してコンピューターを管理する場合は、次の Windows PowerShell コマンドを管理者として開いて、この設定場所テンプレートを登録します。

    ``` syntax
    Register-UevTemplate -Path <Path_to_Template>
    ```

    UE-V と Windows PowerShell を使用した詳細については、「 [Windows powershell と WMI を使った ue-v の設定の場所テンプレートの管理](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)」を参照してください。

-   テンプレート**カタログパスを使用**してテンプレートを登録しています。 ユーザーのコンピューター上のテンプレートを管理するために設定テンプレートカタログパスを使用している場合は、Office 2013 テンプレートを UE-V Agent で定義されているフォルダーにコピーします。 次に、テンプレートの自動更新 (ApplySettingsCatalog.exe) スケジュールされたタスクが実行されたときに、設定場所テンプレートがデバイスに登録されます。 詳細については、「 [ue-v 2 用の設定テンプレートカタログの展開](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)」を参照してください。

-   **Configuration Manager を使用**してテンプレートを登録しています。 Configuration Manager を使用して UE-V 設定ストレージテンプレートを管理している場合は、テンプレートベースライン CAB を再作成し、それを Configuration Manager にインポートして、ベースラインをクライアントに展開します。 詳細については、 [System Center 2012 構成パックの Microsoft User Experience Virtualization 2](https://go.microsoft.com/fwlink/?LinkId=317263)のドキュメントに記載されているガイダンスを参照してください。






 

 





