---
title: 接続グループ ファイルについて
description: 接続グループ ファイルについて
author: dansimp
ms.assetid: 1f4df515-f5f6-4b58-91a8-c71598cb3ea4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31ef9dc9c4465ed8f261b73518348c05ceb78d15
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814930"
---
# 接続グループ ファイルについて


**このトピックの内容は以下のとおりです。**

-   [接続グループファイルの目的と場所](#bkmk-cg-purpose-loc)

-   [接続グループの XML ファイルの構造](#bkmk-define-cg-5-0sp3)

-   [接続グループ内のパッケージの優先度を設定する](#bkmk-config-pkg-priority-incg)

-   [サポートされている仮想アプリケーション接続構成](#bkmk-va-conn-configs)

## <a href="" id="bkmk-cg-purpose-loc"></a>接続グループファイルの目的と場所


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>接続グループの目的</p></td>
<td align="left"><p>接続グループは、パッケージをグループ化して、それらのパッケージ内のアプリケーションが相互に対話できる仮想環境を作成できるようにするアプリ V の機能です。</p>
<p>例: Microsoft Office でプラグインを使用する場合。 プラグインを含むパッケージを作成して、Office を含む別のパッケージを作成し、両方のパッケージを接続グループに追加して、これらのプラグインを使用できるようにすることができます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>接続グループファイルのしくみ</p></td>
<td align="left"><p>App-v 5.1 接続グループファイルを適用すると、ファイルで列挙されるパッケージは、実行時に1つの仮想環境に結合されます。 Microsoft Application Virtualization (App-v) 5.1 接続グループファイルを使用して、既存のアプリ-V 5.1 接続グループを構成します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ファイルパスの例</p></td>
<td align="left"><p>%APPDATA%\Microsoft\AppV\Client\Catalog\PackageGroups {6CCC7575-162E-4152-9407-ED411DA138F4} {4D1E16E1-8EF8-41ED D5-8910a8524d96}。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-define-cg-5-0sp3"></a>接続グループの XML ファイルの構造


**このセクションの内容:**

-   [接続グループを定義するパラメーター](#bkmk-params-define-cg)

-   [接続グループ内のパッケージを定義するパラメーター](#bkmk-params-define-pkgs-incg)

-   [App-v の例: 接続グループの XML ファイル](#bkmk-50sp3-exp-cg-xml)

-   [App-v 5.0 ~ app-v 5.0 SP2 のサンプル接続グループの XML ファイル](#bkmk-50thru50sp2-exp-cg-xm)

### <a href="" id="bkmk-params-define-cg"></a>接続グループを定義するパラメーター

次の表では、パッケージではなく、接続グループ自体を定義する XML ファイルのパラメーターについて説明します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">フィールド</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>スキーマ名</p></td>
<td align="left"><p>スキーマの名前。</p>
<p><strong></strong>この表で説明されている新しい "optional packages" と "use any" 機能を使用する場合は、この XML ファイルで次のスキーマを指定する必要があります。5.0</p>
<p><code>xmlns=&quot;<a href="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot" data-raw-source="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot">https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&quot</a>;</code></p></td>
</tr>
<tr class="even">
<td align="left"><p>AppConnectionGroupId</p></td>
<td align="left"><p>この接続グループの一意の GUID 識別子。 接続グループの状態は、この識別子に関連付けられています。 この識別子は、接続グループを作成するときにのみ指定します。</p>
<p>新しい GUID を作成するには、次のように入力 <strong>[Guid]::NewGuid()</strong> します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>VersionId</p></td>
<td align="left"><p>このバージョンの接続グループのバージョン GUID 識別子。</p>
<p>接続グループを更新する場合 (たとえば、新しいパッケージを追加または更新する場合) は、新しいバージョンを反映するようにバージョン GUID を更新する必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DisplayName</p></td>
<td align="left"><p>接続グループの表示名。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Priority</p></td>
<td align="left"><p>接続グループのオプションの priority フィールド。</p>
<p><strong>"0" </strong> - は、最も優先度の高い値を示します。</p>
<p>優先度は必須ですが、構成されていない場合は、使用する正しい接続グループが判断できないため、パッケージは失敗します。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-params-define-pkgs-incg"></a>接続グループ内のパッケージを定義するパラメーター

接続グループ &lt; の &gt; XML ファイルの [パッケージ] セクションで、次の表に示すように、各パッケージの一意のパッケージ識別子とバージョン識別子を指定して、接続グループにメンバーパッケージを一覧表示します。 一覧の最初のパッケージの優先順位が最も高くなります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">フィールド</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>PackageId</p></td>
<td align="left"><p>このパッケージの一意の GUID 識別子。 この GUID は、パッケージの新しいバージョンが公開されたときには変更されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>VersionId</p></td>
<td align="left"><p>パッケージのバージョンを表す一意の GUID 識別子。</p>
<p><strong>App-v 5.0 SP3 での開始に適用 </strong> される機能: <strong> パッケージバージョンに "*" を指定した場合 </strong> 、利用可能な最新のパッケージバージョンの GUID が動的に挿入されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>IsOptional</p></td>
<td align="left"><p><strong>App-V 5.0 SP3 </strong> : パラメーターを使用すると、接続グループ内でパッケージをオプションにすることができます。 有効なエントリは次のとおりです。</p>
<ul>
<li><p><strong>"true" </strong> –パッケージは接続グループでオプションです</p></li>
<li><p><strong>"false" </strong> –パッケージは接続グループで必要</p></li>
</ul>
<p><a href="how-to-use-optional-packages-in-connection-groups51.md" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups51.md)">接続グループでオプションパッケージを使用する方法について説明し </a> ます。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-50sp3-exp-cg-xml"></a>App-v の例: 接続グループの XML ファイル

次の例の接続グループ XML ファイルは、前の表のフィールドの例を示しています。また、アプリ-V 5.0 SP3 で開始される新しいアイテムを強調表示しています。

```XML
<?xml version="1.0" encoding="UTF-16">
<appv:AppConnectionGroup 
  xmlns="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"
  xmlns:appv="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"  
  AppConnectionGroupId="61BE9B14-D2B4-41CE-A6E3-A1B658DE7000"
  VersionId="E6B6AA57-F2A7-49C9-ADF8-F2B5B3C8A42F"
  Priority="0"  
  DisplayName="Sample Connection Group">
  <appv:Packages>    
    <appv:Package
      PackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"
      VersionId="*"
      IsOptional="true"    
    />
    <appv:Package
      PackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"
      VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"
      IsOptional="false"    
    />  
  </appv:Packages>
</appv:AppConnectionGroup>
```

### <a href="" id="bkmk-50thru50sp2-exp-cg-xm"></a>App-v 5.0 ~ app-v 5.0 SP2 のサンプル接続グループの XML ファイル

次の例の接続グループ XML ファイルは、app-v 5.0 SP2 経由で app-v 5.0 に適用されます。 前の表のフィールドの例を示していますが、上記で説明した変更は、App-v 5.0 SP3 では除外されています。

```XML
<?xml version="1.0" encoding="UTF-16">
<appv:AppConnectionGroup
  xmlns="https://schemas.microsoft.com/appv/2010/virtualapplicationconnectiongroup"
  xmlns:appv="https://schemas.microsoft.com/appv/2010/virtualapplicationconnectiongroup"
  AppConnectionGroupId="61BE9B14-D2B4-41CE-A6E3-A1B658DE7000"
  VersionId="E6B6AA57-F2A7-49C9-ADF8-F2B5B3C8A42F"
  Priority="0"
  DisplayName="Sample Connection Group">
  <appv:Packages>
    <appv:Package
      PackageId="1DC709C8-309F-4AB4-BD47-F75926D04276"
      VersionId="C7DF4F63-5288-439C-ACEF-EF06BF401EC5"
    />
    <appv:Package
     PackageId="04220DCA-EE77-42BE-A9F5-96FD8E8593F2"
     VersionId="E15EFFE9-043D-4C01-BC52-AD2BD1E8BAFA"
   />
 </appv:Packages>
<appv:AppConnectionGroup>
```

## <a href="" id="bkmk-config-pkg-priority-incg"></a>接続グループ内のパッケージの優先度を設定する


パッケージの優先順位は、パッケージの一覧順序で構成されます。 ドキュメント内の最初のパッケージの優先順位が最も高くなります。 リスト内の後続のパッケージの優先度が降順になります。

パッケージの優先順位は、仮想環境の初期化中に、それ以外の不可避リソースの競合を解決するために使用されます。 たとえば、同じ仮想環境で開かれている2つのパッケージが同じレジストリ DWORD 値を定義している場合、最も優先順位の高いパッケージでは、設定されている値が決定されます。

次の方法を使用して、接続グループファイルを使用して各接続グループを構成することができます。

-   接続グループの実行時の優先順位を指定します。 App-v 管理コンソールを使用して優先順位を編集するには、接続グループをクリックし、[**編集**] をクリックします。

    **注** 優先度は、パッケージが複数の接続グループに関連付けられている場合にのみ必要です。

     

-   接続グループ内でパッケージの優先順位を指定します。

[優先度] フィールドは、実行中の仮想アプリケーションがネイティブのアプリケーション要求 (Microsoft Windows エクスプローラーなど) から開始されるときに必要です。 App-v クライアントは、優先順位を使って、アプリケーションが実行する必要がある接続グループの仮想環境を決定します。 この状況は、仮想アプリケーションが複数の接続グループに含まれている場合に発生します。

仮想アプリケーションを別の仮想アプリケーションで開いた場合、元の仮想アプリケーションの仮想環境が使用されます。 この場合、[優先度] フィールドは使用されません。

**例:**

仮想アプリケーション Microsoft Outlook は、仮想環境**XYZ**で実行されています。 添付されている Microsoft word 文書を開くと、仮想環境**XYZ**で、microsoft word に関連付けられている接続グループまたは実行時の優先順位に関係なく、仮想化されたバージョンの microsoft word が開きます。

## <a href="" id="bkmk-va-conn-configs"></a>サポートされている仮想アプリケーション接続構成


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">構成</th>
<th align="left">シナリオ例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>を. exe ファイルとプラグイン (.dll)</p></td>
<td align="left"><ul>
<li><p>Microsoft Office をすべてのユーザーに配布しますが、ユーザーのサブセットのみに Microsoft Excel プラグインを配布します。</p></li>
<li><p>適切なユーザーの接続グループを有効にします。</p></li>
<li><p>必要に応じて各パッケージを個別に更新します。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>を. exe ファイルとミドルウェアアプリケーション</p></td>
<td align="left"><ul>
<li><p>アプリケーションにはミドルウェアアプリケーションが必要です。または、すべてが同じミドルウェアランタイムバージョンに依存している複数のアプリケーションが必要です。</p></li>
<li><p>1つまたは複数のアプリケーションが必要なすべてのコンピューターは、アプリケーションとミドルウェアアプリケーションのランタイムとの接続グループを受け取ります。</p></li>
<li><p>必要に応じて、複数のミドルウェアアプリケーションを1つの接続グループにまとめることができます。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">例</th>
<th align="left">説明の例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>財務部門の仮想アプリケーション接続グループ</p></td>
<td align="left"><ul>
<li><p>ミドルウェアアプリケーション1</p></li>
<li><p>ミドルウェアアプリケーション2</p></li>
<li><p>ミドルウェアアプリケーション3</p></li>
<li><p>ミドルウェアアプリケーションランタイム</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>人事部の仮想アプリケーション接続グループ</p></td>
<td align="left"><ul>
<li><p>ミドルウェアアプリケーション5</p></li>
<li><p>ミドルウェアアプリケーション6</p></li>
<li><p>ミドルウェアアプリケーションランタイム</p></li>
</ul></td>
</tr>
</tbody>
</table>
<p> </p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>を. exe ファイルと .exe ファイル</p></td>
<td align="left"><p>別のアプリケーションに依存するアプリケーションを使用していて、運用効率、ライセンスの制限、またはロールアウトのタイムラインのために、パッケージを分離させたい。</p>
<p><strong>例:</strong></p>
<p>Microsoft Lync 2010 を展開する場合は、次の3つのパッケージを使用できます。</p>
<ul>
<li><p>Microsoft 表紙</p></li>
<li><p>Microsoft Communicator2007</p></li>
<li><p>Microsoft Lync2010</p></li>
</ul>
<p>次の接続グループを使用して展開を管理できます。</p>
<ul>
<li><p>Microsoft 表紙と Microsoft Communicator2007</p></li>
<li><p>Microsoft 表紙と Microsoft Lync2010</p></li>
</ul>
<p>展開が完了したら、新しい Microsoft 表紙 + Microsoft Lync2010 パッケージを1つ作成するか、別のパッケージとして保持して維持し、接続グループを使用して展開することができます。</p></td>
</tr>
</tbody>
</table>

 






## 関連トピック


[接続グループの管理](managing-connection-groups51.md)

 

 





