---
title: UE-V 2 .x のアプリケーションテンプレートスキーマリファレンス
description: UE-V 2 .x のアプリケーションテンプレートスキーマリファレンス
author: dansimp
ms.assetid: be8735a5-6a3e-4b1f-ba14-2a3bc3e5a8b6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 03ff6eabae68f07c23d5977f901e6a90e292c6ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827407"
---
# UE-V 2 .x のアプリケーションテンプレートスキーマリファレンス


Microsoft User Experience Virtualization (UE-V) 2.0、2.1、および 2.1 SP1 では、XML 設定の場所テンプレートを使用して、UE-V でキャプチャおよび適用されるデスクトップアプリケーションの設定と Windows 設定を定義します。 UE-V には、既定の設定場所テンプレートのセットが含まれています。 また、UE-V Generator を使用して、カスタム設定の場所テンプレートを作成することもできます。

高度なユーザーは、設定場所テンプレートの XML ファイルをカスタマイズできます。 このトピックでは、UE-V 2.1 (SP1) と2.0 の設定の場所テンプレートの XML 構造について詳しく説明し、これらのファイルを編集するためのガイダンスを示します。

## UE-V 2.1 および 2.1 SP1 アプリケーションテンプレートスキーマリファレンス


このセクションでは、UE-V 2.1 および 2.1 SP1 設定の場所テンプレートの XML 構造について詳しく説明し、このファイルを編集するためのガイダンスを提供します。

### このセクションの内容

-   [XML 宣言とエンコード属性](#xml21)

-   [名前空間とルート要素](#namespace21)

-   [データ型](#data21)

-   [Name 要素](#name21)

-   [ID 要素](#id21)

-   [Version 要素](#version21)

-   [作成要素](#author21)

-   [プロセスとプロセス要素](#processes21)

-   [Application 要素](#application21)

-   [共通要素](#common21)

-   [SettingsLocationTemplate 要素](#settingslocationtemplate21)

-   [付録: SettingsLocationTemplate .xsd](#appendix21)

### <a href="" id="xml21"></a>XML 宣言とエンコード属性

**必須: True**

**種類: 文字列**

XML 宣言では、XML バージョン1.0 属性 ( &lt; ? XML バージョン = "1.0") を指定する必要があり &gt; ます。 UE-V Generator によって作成された設定場所テンプレートは、UTF-8 エンコードで保存されます。ただし、エンコードは明示的に指定されません。 ベストプラクティスとして、この要素に encoding = "UTF-8" 属性を含めることをお勧めします。 製品に含まれているすべてのテンプレートにもこのタグが指定されています (Virtualization\\Templates では、Microsoft User Experience のドキュメントを参照してください)。 以下に例を示します。

`<?xml version="1.0" encoding="UTF-8"?>`

### <a href="" id="namespace21"></a>名前空間とルート要素

**必須: True**

**種類: 文字列**

UE-V は、 https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate すべてのアプリケーションの名前空間を使います。 SettingsLocationTemplate はルート要素であり、他のすべての要素が含まれます。 このタグを使用して、すべてのテンプレートの参照設定の場所テンプレート:

`<SettingsLocationTemplate xmlns='https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate'>`

### <a href="" id="data21"></a>データ型

UE-V アプリケーションテンプレートスキーマのデータ型を次に示します。

<a href="" id="guid"></a>**GUID**GUID は、標準のグローバル一意識別子の正規表現として "\ \ {\ [a-z-9 \]- {8} \ [a-fa-9 \]-\ [-] {4} [A-z-f0-9 \]-\ [a------ {4} {4} \]-\ [a- {12} ---------\] これは、既知のフォルダーの書式を確認するために、filesetting¥ root¥ knownfolder 要素で使われます。

<a href="" id="filenamestring"></a>**FilenameString**FilenameString は、監視されるプロセスのファイル名を指します。 この値は、regex \ [^ \ \ \ \ \ \ \ \ \ * \ \ | \ \ \ * \ \ | &lt; &gt; ) で制限されています。/: \] + (つまり、バックスラッシュ文字、アスタリスクまたは疑問符のワイルドカード文字、パイプ文字、不等号、スラッシュ、またはコロン文字) が含まれている可能性があります。

<a href="" id="idstring"></a>**Idstring**IDString は、アプリケーション要素の ID 値、SettingsLocationTemplate、共通要素を参照します (共通の設定を共有するアプリケーションスイートを記述するために使用されます)。 FilenameString と同じ regex で制限されています (\ [^] \ \ \ \ \ \ \ \ * \ \ | \ \ \ * \ \ | &lt; &gt; )/:\]+).

<a href="" id="templateversion"></a>**テンプレートのバージョン**TemplateVersion は、設定場所テンプレートのリビジョンを記述するために使用される整数値です。 この値の範囲は 0 ~ 2147483647 です。

<a href="" id="empty"></a>**空**Empty は null 値を参照します。 これは、監視するプロセスがないことを示すために、Process\\ shellprocess で使われます。 この値は、どのアプリケーションテンプレートでも使うことはできません。

<a href="" id="author"></a>**作成者**作成者データ型は、テンプレートの作成者を識別する複雑な型です。 これには、**名前**と**メール**という2つの子要素が含まれています。 Author データ型では、Email 要素が省略可能である間、Name 要素は必須です。 この型については、SettingsLocationTemplate 要素の詳細について説明します。

<a href="" id="range"></a>**範囲**Range は、**最小値**と**最大値**の2つの子要素で構成される integer クラスを定義します。 このデータ型は、ProcessVersion データ型に実装されます。 指定する場合は、最小値と最大値の両方が含まれている必要があります。

<a href="" id="processversion"></a>**Processversion**ProcessVersion は、4つの子要素を持つ型 ( **Major**、 **Minor**、 **Build**、および**Patch**) を定義します。 このデータ型は、プロセス要素によって ProductVersion と FileVersion 値を設定するために使われます。 この型のデータは、範囲値です。 主要な子要素は必須であり、他の要素は省略可能です。

<a href="" id="architecture"></a>**アーキテクチャ**アーキテクチャでは、 **Win32**と**Win64**の2つの値を列挙します。 これらの値は、プロセスアーキテクチャを指定するために使用されます。

<a href="" id="process"></a>**プロセス**プロセスデータ型は、UE-V で監視されるプロセスを記述するために使用されるコンテナーです。 これには、**ファイル名**、**アーキテクチャ**、**商品名**、 **filedescription**、 **productversion**、 **FileVersion**という6つの子要素が含まれています。 この表では、各要素のデータ型について詳しく説明します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>要素</strong></p></td>
<td align="left"><p><strong>データ型</strong></p></td>
<td align="left"><p><strong>Mandatory</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>ル</p></td>
<td align="left"><p>FilenameString</p></td>
<td align="left"><p>True</p></td>
</tr>
<tr class="odd">
<td align="left"><p>アーキテクチャ</p></td>
<td align="left"><p>アーキテクチャ</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>ProductName</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ファイルの説明</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>ProductVersion</p></td>
<td align="left"><p>ProcessVersion</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FileVersion</p></td>
<td align="left"><p>ProcessVersion</p></td>
<td align="left"><p>False</p></td>
</tr>
</tbody>
</table>

 

<a href="" id="processes"></a>**プロセス**プロセスデータ型は、1つ以上のプロセス要素のコレクションのコンテナーを表します。 次の2つの子要素がプロセスシーケンスの種類でサポートされています。**プロセス**と**shellprocess**。 プロセスは、Process 型の要素であり、ShellProcess はデータ型が空であることを示します。 シーケンスで少なくとも1つの項目を識別する必要があります。

<a href="" id="path"></a>**Path**Path は、レジストリとファイルのパスを参照するために、RegistrySetting と FileSetting で消費されます。 この要素は、 **Recursive**と**DeleteIfNotFound**の2つのオプション属性をサポートします。 どちらの値も default = "False" に設定されています。

Recursive は、パスとすべてのサブフォルダーがファイル設定に含まれていること、またはすべての子レジストリキーがレジストリ設定に含まれていることを示します。 どちらの場合も、キャプチャされたデータには、現在のレベルのすべての項目が含まれます。 FileSettings オブジェクトの場合、指定したフォルダー内のすべてのファイルは、UE-V によってキャプチャされるデータに含まれますが、フォルダーは含まれません。 レジストリパスの場合、現在のパスにあるすべての値がキャプチャされますが、子レジストリキーはキャプチャされません。 どちらの場合も、大量のデータセットまたは多数の項目をキャプチャしないように注意する必要があります。

DeleteIfNotFound 属性は、ユーザー設定の記憶域のパスデータから設定を削除します。 これは、パッケージからこれらの設定を削除すると、設定の記憶域パスファイルサーバーに大量のディスク領域が保存される可能性がある場合に適しています。

<a href="" id="filemask"></a>**Filemask**FileMask Path で定義されているフォルダーに対して、特定の種類のファイルのみを指定します。 たとえば、Path `C:\users\username\files` とファイルが含まれている可能性があり `*.txt` ます。テキストファイルのみを含めることもできます。

<a href="" id="registrysetting"></a>**Registrysetting**RegistrySetting は、レジストリキーと値のコンテナーと、UE-V エージェントの一部に関連する目的の動作を表します。 4つの子要素は、 **path**、 **Name**、 **Exclude**、および値の**パス**と**名前**のシーケンスで構成されます。

<a href="" id="filesetting"></a>**Filesetting**FileSetting には、ファイルとファイルのパスに関連付けられたパラメーターが含まれています。 4つの子要素 (**ルート**、 **Path**、 **filemask**、**除外**) が定義されています。 Root は必須で、他のオプションは省略可能です。

<a href="" id="settings"></a>**設定**設定は、特定のテンプレートに適用されるすべての設定のコンテナーです。 これには、前に説明したレジストリ、File、SystemParameter、および CustomAction の各設定のインスタンスが含まれています。 さらに、次の子要素も含めることができます。これには、次のような動作があります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>要素</strong></p></td>
<td align="left"><p><strong>説明</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>非同期</p></td>
<td align="left"><p>非同期設定パッケージは、アプリケーションの起動をブロックせずに適用されるため、設定が適用されている間、アプリケーションは実行を開始できます。 これは、SystemParameterSetting など、API を通じて非同期的に適用できる設定に役立ち <code>get/set</code> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PreventOverlappingSynchronization</p></td>
<td align="left"><p>既定では、UE-V は、テンプレートを使用するアプリケーションの最後のインスタンスが閉じられている場合にのみ、アプリケーションの設定を保存します。 この要素が "false" に設定されている場合、アプリケーションの他のインスタンスが実行されている場合でも、UE-V は設定をエクスポートします。 適したテンプレート– UE-V に同梱されている共通要素セクションが含まれている場合は、このフラグを使って共有設定をアプリケーションの終了時に常にエクスポートし、最後のインスタンスが閉じられるまでは、アプリケーション固有の設定がエクスポートされないようにします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Always Applysettings</p></td>
<td align="left"><p>(2.1 で導入されました)</p>
<p>このパラメーターを指定すると、パッケージとアプリケーションの現在の状態の違いがない場合でも、インポートした設定パッケージが強制的に適用されます。 このパラメーターは、設定のインポート速度が遅くなる可能性があるため、特別な場合にのみ使用してください。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="name21"></a>Name 要素

**必須: True**

**種類: 文字列**

[名前] 設定場所テンプレートの一意の名前を指定します。 これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。 一般的に、バージョン情報を参照することは避けてください。これは、ProductVersion 要素から objected することができます。 たとえば、ではなく、を指定し `<Name>My Application</Name>` `<Name>My Application 1.1</Name>` ます。

**注** UE-V は外部の Dtd を参照しないため、設定場所テンプレートで名前付きエンティティを使うことはできません。 たとえば、登録されて &reg; いる商標記号®の参照には使用しないでください。 代わりに、このような種類の特殊文字 (®文字の & \ #174 など) を含める場合は、標準の番号付き参照を使います。 この規則は、このドキュメント内のすべての文字列値に適用されます。

<http://www.w3.org/TR/xhtml1/dtds.html>文字エンティティの完全な一覧については、を参照してください。 UTF-8 でエンコードされたドキュメントには、Unicode 文字が直接含まれている場合があります。 UE-V Generator を使用してテンプレートを保存すると、文字エンティティが自動的に Unicode 表現に変換されます。

 

### <a href="" id="id21"></a>ID 要素

**必須: True**

**種類: 文字列**

ID は、特定のテンプレートの一意の識別子を入力します。 このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります (たとえば、Get-UevTemplate と Get-UevTemplateProgram PowerShell コマンドレットの出力を参照してください)。 慣例により、このタグにはスペースを含めないでください。これによってスクリプトが簡素化されます。 この要素には、やなどのテンプレートを簡単に識別できるように、アプリのバージョン番号を指定する必要があり `<ID>MicrosoftCalculator6</ID>` `<ID>MicrosoftOffice2010Win64</ID>` ます。

### <a href="" id="version21"></a>Version 要素

**必須: True**

**種類: Integer**

**最小値: 0**

**最大値: 2147483647**

[バージョン] は、変更の管理追跡用の設定場所テンプレートのバージョンを示します。 UE-V Generator は、テンプレートが保存されるたびに、この数値を1つずつ自動的にインクリメントします。 このフィールドは整数である必要があることに注意してください。小数点以下の値 `<Version>2.5</Version>` は使用できません。

**ヒント:** XML コメントタグを使用して、バージョンの変更に関するメモを保存でき `<!-- -->` ます。たとえば、次のようになります。

```xml
  <!--
     Version History

     Version 1 Jul 05, 2012 Initial template created by Generator - Denise@Contoso.com
     Version 2 Jul 31, 2012 Added support for app.exe v2.1.3 - Mark@Contoso.com
     Version 3 Jan 01, 2013 Added font settings support - Mark@Contoso.com
     Version 4 Jan 31, 2013 Added support for plugin settings - Tony@Contoso.com
   -->
  <Version>4</Version>
```

**重要** この値は、次のような場合に、既存のテンプレートに新しいバージョンのテンプレートを適用する必要があるかどうかを確認するために照会されます。

-   スケジュールされたテンプレートの自動更新タスクの実行時

-   更新プログラム UevTemplate PowerShell コマンドレットが実行されるとき

-   WMI 経由で microsoft\\uev: SettingsLocationTemplate Update メソッドが呼び出された場合

 

### <a href="" id="author21"></a>作成要素

**必須: False**

**種類: 文字列**

[作成者] は、設定場所テンプレートの作成者を指定します。 2つのオプションの子要素がサポートされています。**名前**と**メール** どちらの属性も省略可能ですが、メールの子要素が指定されている場合は、Name 要素と共に指定する必要があります。 [Author] は、設定場所テンプレートの連絡先の完全な名前を示し、メールは作成者のメールアドレスを参照する必要があります。 この情報は、一般に公開されるテンプレート ( [Ue-v テンプレートギャラリー](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V)など) に含めることをお勧めします。

### <a href="" id="processes21"></a>プロセスとプロセス要素

**必須: True**

**Type: Element**

プロセスには、少なくとも1つの要素が含まれます。これには、 `<Process>` **ファイル名**、**アーキテクチャ**、**商品名**、 **filedescription**、 **productversion**、 **FileVersion**という子要素が含まれています。 ファイル名の子要素は必須であり、他の項目は省略可能です。 完全に入力された要素には、次の例のようなタグが含まれています。

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <Architecture>Win64</Architecture>
  <ProductName> MyApplication </ProductName>
  <FileDescription>MyApplication.exe</FileDescription>
  <ProductVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </FileVersion>
</Process>
```

### ル

**必須: True**

**種類: 文字列**

Filename は、ファイルシステムに表示される実行可能ファイルの実際のファイル名を指します。 この要素は、テンプレートがプロセスに適用されるかどうかを評価するために UE-V が使う主要な条件を指定します。 この要素は、設定場所テンプレート XML で指定する必要があります。

有効なファイル名は、正規表現 \ [^] \ \ \ \ \ \ \ * \ \ | \ \ \ * \ \ | &lt; &gt;/: \] +、つまり、バックスラッシュ文字、アスタリスクまたは疑問符のワイルドカード文字、パイプ文字、不等号、スラッシュ、またはコロン (\ \?) が含まれていない可能性があります。 \* |&lt; &gt; /または: 文字)。

**ヒント:** この regex に対して文字列をテストするには、PowerShell コマンドウィンドウを使って、実行可能ファイルの名前を**ファイル**名に置き換えます。

`"YourFileName.exe" -match  "[\\\?\*\|<>/:]+"`

値が**True**の場合は、文字列に不正な文字が含まれていることを示します。 次に、不正な値の例をいくつか示します。

-   \\\\server\\share\\program.exe

-   プログラム \ * .exe

-   Pro? ram.exe

-   プログラム &lt; 1 &gt; . .exe

**注** UE-V Generator は、指定された文字より大きい文字と小さい文字をそれぞれエンコードし &gt; &lt; ます。

 

まれに、ファイル名の値に .exe 拡張子が含まれているとは限りませんが、値の一部として指定する必要があります。 たとえば、 `<Filename>MyApplictication.exe</Filename>` の代わりにを指定する必要があり `<Filename>MyApplictication</Filename>` ます。 実行可能ファイルの実際の名前が "MyApplication.exe" の場合、2番目の例では、テンプレートはプロセスに適用されません。

### アーキテクチャ

**必須: False**

**Type: Architecture (文字列)**

アーキテクチャとは、ターゲットの実行可能ファイルがコンパイルされたプロセッサアーキテクチャを指します。 有効な値は、32ビットアプリケーションまたは64ビットアプリケーション用の Win64 の Win32 です。 存在する場合、このタグは、設定場所テンプレートを特定のアプリケーションアーキテクチャに適用することを制限します。 この例については、UE-V に含まれる% programfiles% ¥ Microsoft User Experience Virtualization\\templates\\ MicrosoftOffice2010Win32.xml と MicrosoftOffice2010Win64.xml ファイルを比較します。 これは、異なるバージョンの実行可能ファイル間で相対パスが変更された場合、またはプロセッサアーキテクチャを切り替えるときに設定が追加または削除された場合に役立ちます。

この要素が存在しない場合、設定場所テンプレートはプロセスのアーキテクチャを無視し、ファイル名とその他の属性が適用されている場合、32と64ビットの両方のプロセスに適用されます。

**注** UE-V は、このバージョンの ARM プロセッサをサポートしていません。

 

### ProductName

**必須: False**

**種類: 文字列**

ProductName は、管理目的またはレポート用に製品を識別するために使用されるオプションの要素です。 ProductName はファイル名とは異なり、その値に対する正規表現の制限はありません。 これにより、実行可能ファイル名が明確でない可能性のあるプロセスの説明をより簡単に理解できます。 以下に例を示します。

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <ProductName>My Application 6.x by Contoso.com</ProductName>
  <ProductVersion>
    <Major Minimum="6" Maximum="6" />
  </ProductVersion>
</Process>
```

### ファイルの説明

**必須: False**

**種類: 文字列**

FileDescription は、実行可能ファイルの管理の説明を可能にするオプションのタグです。 これは無料のテキストフィールドであり、実行可能ファイルの機能を識別する必要があるソフトウェアパッケージ内の複数の実行可能ファイルを区別するのに役立ちます。

たとえば、次に示すように、適したアプリケーションでは、2つの実行可能ファイル (MyApplication.exe と MyApplicationHelper.exe) の機能についての通知を表示すると便利な場合があります。

```xml
<Processes>
  <Process>
    <Filename>MyApplication.exe</Filename>
    <FileDescription>My Application Main Engine</ FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
  <Process>
    <Filename>MyApplicationHelper.exe</Filename>
    <FileDescription>My Application Background Process Executable</FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
</Processes>
```

### ProductVersion

**必須: False**

**種類: 文字列**

ProductVersion は、ファイルのメジャーバージョンとマイナー製品バージョン、およびビルドとパッチレベルを指します。 ProductVersion は省略可能な要素ですが、指定する場合は、少なくとも主要な子要素が含まれている必要があります。 この値は、最小値の "X" 最大値 = "Y" (X と Y は整数) の範囲を表す必要があります。 最小値と最大値は同じにすることができます。

製品とファイルのバージョンの要素が指定されていない可能性があります。 これにより、テンプレートは "バージョンに依存しない" という意味になります。つまり、指定した実行可能ファイルのすべてのバージョンにテンプレートが適用されます。

**例 1:**

製品バージョン: 1.0 は、UE-V Generator で指定されている次の XML を生成します。

```xml
<ProductVersion>
  <Major Minimum="1" Maximum="1" />
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

**例 2:**

ファイルバージョン: UE-V Generator で指定された5.0.2.1000 は、次の XML を生成します。

```xml
<FileVersion>
  <Major Minimum="5" Maximum="5" />
  <Minor Minimum="0" Maximum="0" />
  <Build Minimum="2" Maximum="2" />
  <Patch Minimum="1000" Maximum="1000" />
</FileVersion>
```

**間違った例1–不完全な範囲:**

最小属性のみが存在します。 範囲には最大値も含める必要があります。

```xml
<ProductVersion>
  <Major Minimum="2" />
</ProductVersion>
```

**間違った例2–主要要素のない Minor:**

Minor 要素のみが存在します。 メジャーも含める必要があります。

```xml
<ProductVersion>
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

### FileVersion

**必須: False**

**種類: 文字列**

FileVersion は、公開されたアプリケーションのリリースバージョンと、コンポーネント実行可能ファイルの内部ビルドの詳細を区別します。 ほとんどの商用アプリケーションでは、これらの番号は同じです。 実際には、ファイルの製品バージョンはファイルの一般的なバージョン id を示していますが、ファイルバージョンはファイルの特定のビルドを示します (修正プログラムや更新プログラムの場合など)。 これにより、検出ロジックを壊すことなくファイルを一意に識別できます。

特定の実行可能ファイルの製品バージョンとファイルバージョンを確認するには、Windows エクスプローラーでファイルを右クリックし、[プロパティ] を選択して、[詳細] タブをクリックします。

アプリケーションの FileVersion 要素を含めることで、細かい微調整による検出ロジックを行うことができますが、ほとんどのアプリケーションには必要ありません。 ProductVersion 要素の設定が最初にチェックされ、次に FileVersion がチェックされます。 より限定的な設定が適用されます。

FileVersion の子要素と構文規則は、ProductVersion バージョンと同じです。

```xml
<Process>
  <Filename>MSACCESS.EXE</Filename>
  <Architecture>Win32</Architecture>
  <ProductVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </FileVersion>
</Process>
```

### <a href="" id="application21"></a>Application 要素

アプリケーションは、特定のアプリケーションに適用される設定のコンテナーです。 これは、次のフィールド/型のコレクションです。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>フィールド/型</strong></p></td>
<td align="left"><p><strong>説明</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Name (名前)</p></td>
<td align="left"><p>設定場所テンプレートの一意の名前を指定します。 これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。 詳細については、「名前」を参照してください <a href="#name21" data-raw-source="[Name](#name21)"> </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ID</p></td>
<td align="left"><p>特定のテンプレートの一意の識別子を設定します。 このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります。 詳細については、「ID」を参照してください <a href="#id21" data-raw-source="[ID](#id21)"> </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>説明</p></td>
<td align="left"><p>テンプレートの説明 (省略可能)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI に表示されるオプションの名前。言語ロケールによってローカライズされます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>言語ロケールによってローカライズされた省略可能なテンプレートの説明です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>バージョン</p></td>
<td align="left"><p>変更の管理追跡用の設定場所テンプレートのバージョンを示します。 詳細については、「バージョン」を参照してください <a href="#version21" data-raw-source="[Version](#version21)"> </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeferToMSAccount</p></td>
<td align="left"><p>このテンプレートが Microsoft アカウントと組み合わせて有効になっているかどうかを制御します。 コンピューター上のユーザーに対して MSA の同期が有効になっている場合、このテンプレートは自動的に無効になります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeferToOffice365</p></td>
<td align="left"><p>MSA の場合と同様に、このテンプレートを Office365 と組み合わせて有効にするかどうかを制御します。 設定の同期に Office 365 が使用されている場合、このテンプレートは自動的に無効になります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>FixedProfile (2.1 で導入)</p></td>
<td align="left"><p>このテンプレートは、この要素内で指定されたプロファイルにのみ関連付けることができます。また、WMI または PowerShell を使用して変更することはできません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>プロセス</p></td>
<td align="left"><p>1つ以上のプロセス要素のコレクションのコンテナー。 詳細については、「プロセス」を参照してください <a href="#processes21" data-raw-source="[Processes](#processes21)"> </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定</p></td>
<td align="left"><p>特定のテンプレートに適用されるすべての設定のコンテナー。 これには、Registry、File、SystemParameter、および CustomAction の各設定のインスタンスが含まれます。 詳細については、「 <strong> </strong> データ型の設定」を参照してください <a href="#data21" data-raw-source="[Data types](#data21)"> </a> 。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="common21"></a>共通要素

Common は Application 要素と似ていますが、常に、2つ以上のアプリケーション要素に関連付けられます。 共通セクションは、これらのアプリケーションインスタンス間で共有される一連の設定を表します。 これは、次のフィールド/型のコレクションです。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>フィールド/型</strong></p></td>
<td align="left"><p><strong>説明</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Name (名前)</p></td>
<td align="left"><p>設定場所テンプレートの一意の名前を指定します。 これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。 詳細については、「名前」を参照してください <a href="#name21" data-raw-source="[Name](#name21)"> </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ID</p></td>
<td align="left"><p>特定のテンプレートの一意の識別子を設定します。 このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります。 詳細については、「ID」を参照してください <a href="#id21" data-raw-source="[ID](#id21)"> </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>説明</p></td>
<td align="left"><p>テンプレートの説明 (省略可能)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI に表示されるオプションの名前。言語ロケールによってローカライズされます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>言語ロケールによってローカライズされた省略可能なテンプレートの説明です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>バージョン</p></td>
<td align="left"><p>変更の管理追跡用の設定場所テンプレートのバージョンを示します。 詳細については、「バージョン」を参照してください <a href="#version21" data-raw-source="[Version](#version21)"> </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeferToMSAccount</p></td>
<td align="left"><p>このテンプレートが Microsoft アカウントと組み合わせて有効になっているかどうかを制御します。 コンピューター上のユーザーに対して MSA の同期が有効になっている場合、このテンプレートは自動的に無効になります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeferToOffice365</p></td>
<td align="left"><p>MSA の場合と同様に、このテンプレートを Office365 と組み合わせて有効にするかどうかを制御します。 設定の同期に Office 365 が使用されている場合、このテンプレートは自動的に無効になります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>FixedProfile (2.1 で導入)</p></td>
<td align="left"><p>このテンプレートは、この要素内で指定されたプロファイルにのみ関連付けることができます。また、WMI または PowerShell を使用して変更することはできません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定</p></td>
<td align="left"><p>特定のテンプレートに適用されるすべての設定のコンテナー。 これには、Registry、File、SystemParameter、および CustomAction の各設定のインスタンスが含まれます。 詳細については、「 <strong> </strong> データ型の設定」を参照してください <a href="#data21" data-raw-source="[Data types](#data21)"> </a> 。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="settingslocationtemplate21"></a>SettingsLocationTemplate 要素

この要素は、1つのアプリケーションまたは一連のアプリケーションの設定を定義します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>フィールド/型</strong></p></td>
<td align="left"><p><strong>説明</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>Name (名前)</p></td>
<td align="left"><p>設定場所テンプレートの一意の名前を指定します。 これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。 詳細については、「名前」を参照してください <a href="#name21" data-raw-source="[Name](#name21)"> </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ID</p></td>
<td align="left"><p>特定のテンプレートの一意の識別子を設定します。 このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります。 詳細については、「ID」を参照してください <a href="#id21" data-raw-source="[ID](#id21)"> </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>説明</p></td>
<td align="left"><p>テンプレートの説明 (省略可能)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI に表示されるオプションの名前。言語ロケールによってローカライズされます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>言語ロケールによってローカライズされた省略可能なテンプレートの説明です。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="appendix21"></a>付録: SettingsLocationTemplate .xsd

次に示すのは、要素、子要素、属性、パラメーターが表示された SettingsLocationTemplate です。

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="UevSettingsLocationTemplate"
  targetNamespace="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  elementFormDefault="qualified"
  xmlns="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  xmlns:mstns="https://schemas.microsoft.com/UserExperienceVirtualization/2013A/SettingsLocationTemplate"
  xmlns:xs="http://www.w3.org/2001/XMLSchema">

    <xs:simpleType name="Guid">
        <xs:restriction base="xs:string">
            <xs:pattern value="\{[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}\}" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="FilenameString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:]+" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="IDString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="CompositeIDString">
        <xs:restriction base="xs:string">
            <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+([.][^\\\?\*\|&lt;&gt;/:.]+)?" />
        </xs:restriction>
    </xs:simpleType>

    <xs:simpleType name="TemplateVersion">
        <xs:restriction base="xs:integer">
            <xs:minInclusive value="0" />
            <xs:maxInclusive value="2147483647" />
        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Empty">
        <xs:sequence/>
    </xs:complexType>

    <xs:complexType name="LocalizedString">
        <xs:simpleContent>
            <xs:extension base="xs:string">
                <xs:attribute name="Locale" type="xs:string" use="required"/>
            </xs:extension>
        </xs:simpleContent>
    </xs:complexType>

    <xs:complexType name="LocalizedName">
        <xs:sequence>
            <xs:element name="Name" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="LocalizedDescription">
        <xs:sequence>
            <xs:element name="Description" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="ReplacedTemplates">
      <xs:sequence>
        <xs:element name="ID" type="CompositeIDString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Author">
        <xs:all>
            <xs:element name="Name" type="xs:string" minOccurs="1" />
            <xs:element name="Email" type="xs:string" minOccurs="0" />
        </xs:all>
    </xs:complexType>

    <xs:complexType name="Range">
        <xs:attribute name="Minimum" type="xs:integer" use="required"/>
        <xs:attribute name="Maximum" type="xs:integer" use="required"/>
    </xs:complexType>

    <xs:complexType name="ProcessVersion">
        <xs:sequence>
            <xs:element name="Major" type="Range" minOccurs="1" />
            <xs:element name="Minor" type="Range" minOccurs="0" />
            <xs:element name="Build" type="Range" minOccurs="0" />
            <xs:element name="Patch" type="Range" minOccurs="0" />
        </xs:sequence>
    </xs:complexType>

    <xs:simpleType name="Architecture">
        <xs:restriction base="xs:string">
            <xs:enumeration value="Win32"/>
            <xs:enumeration value="Win64"/>
        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Process">
        <xs:sequence>
            <xs:element name="Filename" type="FilenameString" minOccurs="1" />
            <xs:element name="Architecture" type="Architecture" minOccurs="0" />
            <xs:element name="ProductName" type="xs:string" minOccurs="0" />
            <xs:element name="FileDescription" type="xs:string" minOccurs="0" />
            <xs:element name="ProductVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
            <xs:element name="FileVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Processes">
        <xs:sequence>
            <xs:choice minOccurs="1">
                <xs:element name="Process" type="Process" />
                <xs:element name="ShellProcess" type="Empty" />
            </xs:choice>
            <xs:element name="Process" type="Process" minOccurs="0" maxOccurs="unbounded" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Path">
        <xs:simpleContent>
            <xs:extension base="xs:string">
                <xs:attribute name="Recursive" type="xs:boolean" default="false"/>
                <xs:attribute name="DeleteIfNotFound" type="xs:boolean" default="false"/>
            </xs:extension>
        </xs:simpleContent>
    </xs:complexType>

    <xs:complexType name="RegistrySetting">
        <xs:sequence>
            <xs:element name="Path" type="Path" />
            <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
            <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                    <xs:sequence>
                        <xs:element name="Path" type="Path" minOccurs="0" />
                        <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
                    </xs:sequence>
                </xs:complexType>
            </xs:element>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="FileSetting">
        <xs:sequence>

            <xs:element name="Root">
                <xs:complexType>
                    <xs:choice>
                        <xs:element name="KnownFolder" type="Guid" />
                        <xs:element name="RegistryEntry" type="xs:string" />
                        <xs:element name="EnvironmentVariable" type="xs:string" />
                    </xs:choice>
                </xs:complexType>
            </xs:element>

            <xs:element name="Path" minOccurs="0" type="Path" />
            <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>

            <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
                <xs:complexType>
                    <xs:sequence>
                        <xs:element name="Path" type="Path" minOccurs="0" />
                        <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
                    </xs:sequence>
                </xs:complexType>
            </xs:element>

        </xs:sequence>
    </xs:complexType>

    <xs:simpleType name="CustomActionSetting">
        <xs:restriction base="xs:anyURI"/>
    </xs:simpleType>

    <xs:simpleType name="SystemParameterSetting">
        <xs:restriction base="xs:string">

            <!-- Accessibility parameters -->
            <xs:enumeration value="AccessTimeout"/>
            <xs:enumeration value="AudioDescription"/>
            <xs:enumeration value="ClientAreaAnimation"/>
            <xs:enumeration value="DisableOverlappedContent"/>
            <xs:enumeration value="FilterKeys"/>
            <xs:enumeration value="FocusBorderHeight"/>
            <xs:enumeration value="FocusBorderWidth"/>
            <xs:enumeration value="HighContrast"/>
            <xs:enumeration value="MessageDuration"/>
            <xs:enumeration value="MouseClickLock"/>
            <xs:enumeration value="MouseClickLockTime"/>
            <xs:enumeration value="MouseKeys"/>
            <xs:enumeration value="MouseSonar"/>
            <xs:enumeration value="MouseVanish"/>
            <xs:enumeration value="ScreenReader"/>
            <xs:enumeration value="ShowSounds"/>
            <xs:enumeration value="SoundSentry"/>
            <xs:enumeration value="StickyKeys"/>
            <xs:enumeration value="ToggleKeys"/>

            <!-- Input parameters -->
            <xs:enumeration value="Beep"/>
            <xs:enumeration value="BlockSendInputResets"/>
            <xs:enumeration value="DefaultInputLang"/>
            <xs:enumeration value="DoubleClickTime"/>
            <xs:enumeration value="DoubleClkHeight"/>
            <xs:enumeration value="DoubleClkWidth"/>
            <xs:enumeration value="KeyboardCues"/>
            <xs:enumeration value="KeyboardDelay"/>
            <xs:enumeration value="KeyboardPref"/>
            <xs:enumeration value="KeyboardSpeed"/>
            <xs:enumeration value="Mouse"/>
            <xs:enumeration value="MouseButtonSwap"/>
            <xs:enumeration value="MouseHoverHeight"/>
            <xs:enumeration value="MouseHoverTime"/>
            <xs:enumeration value="MouseHoverWidth"/>
            <xs:enumeration value="MouseSpeed"/>
            <xs:enumeration value="MouseTrails"/>
            <xs:enumeration value="SnapToDefButton"/>
            <xs:enumeration value="WheelScrollChars"/>
            <xs:enumeration value="WheelScrollLines"/>

            <!-- Desktop parameters (limited subset) -->
            <xs:enumeration value="DeskWallpaper"/>
            <xs:enumeration value="DesktopColor"/>

        </xs:restriction>
    </xs:simpleType>

    <xs:complexType name="Settings">
        <xs:sequence>
            <xs:element name="Asynchronous" type="xs:boolean" minOccurs="0" />
            <xs:element name="PreventOverlappingSynchronization" type="xs:boolean" minOccurs="0" />
            <xs:element name="AlwaysApplySettings" type="xs:boolean" minOccurs="0" />
            <xs:choice minOccurs="0" maxOccurs="unbounded">
                <xs:element name="Registry" type="RegistrySetting" />
                <xs:element name="File" type="FileSetting" />
                <xs:element name="SystemParameter" type="SystemParameterSetting" />
                <xs:element name="CustomAction" type="CustomActionSetting" />
            </xs:choice>
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Common">
        <xs:sequence>
            <xs:element name="Name" type="xs:string" />
            <xs:element name="ID" type="IDString" />
            <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
            <xs:element name="Description" type="xs:string" minOccurs="0" />
            <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
            <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
            <xs:element name="Version" type="xs:integer" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
            <xs:element name="Settings" type="Settings" />
        </xs:sequence>
    </xs:complexType>

    <xs:complexType name="Application">
        <xs:sequence>
            <xs:element name="Name" type="xs:string" />
            <xs:element name="ID" type="IDString" />
            <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
            <xs:element name="Description" type="xs:string" minOccurs="0" />
            <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
            <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
            <xs:element name="Version" type="xs:integer" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
            <xs:element name="Processes" type="Processes" />
            <xs:element name="Settings" type="Settings" />
        </xs:sequence>
    </xs:complexType>


    <xs:element name="SettingsLocationTemplate">
        <xs:complexType>
            <xs:sequence>

                <xs:element name="Name" type="xs:string" />
                <xs:element name="ID" type="IDString" />
                <xs:element name="Description" type="xs:string" minOccurs="0" />
                <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
                <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />

                <xs:choice>

                    <!-- Single application -->
                    <xs:sequence>
                        <xs:element name="ReplacedTemplates" type="ReplacedTemplates" minOccurs="0" />
                        <xs:element name="Version" type="TemplateVersion" />
                        <xs:element name="Author" type="Author" minOccurs="0" />
                        <xs:element name="FixedProfile" type="xs:string"  minOccurs="0" />
                        <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
                        <xs:element name="DeferToOffice365" type="Empty" minOccurs="0" />
                        <xs:element name="Processes" type="Processes" />
                        <xs:element name="Settings" type="Settings" />
                    </xs:sequence>

                    <!-- Suite of applications -->
                    <xs:sequence>
                        <xs:element name="ManageSuiteOnly" type="xs:boolean" minOccurs="0" />
                        <xs:element name="Author" type="Author" minOccurs="0" />
                        <xs:element name="FixedProfile" type="xs:string"  minOccurs="0" />
                        <xs:element name="Common" type="Common" />
                        <xs:element name="Application" type="Application" minOccurs="2" maxOccurs="unbounded" />
                    </xs:sequence>

                </xs:choice>

            </xs:sequence>
        </xs:complexType>
    </xs:element>
    <!-- SettingsLocationTemplate -->

</xs:schema>
```

## UE-V 2.0 アプリケーションテンプレートのスキーマリファレンス


このセクションでは、UE-V 2.0 設定の場所テンプレートの XML 構造について詳しく説明し、このファイルの編集に関するガイダンスを提供します。

### このセクションの内容

-   [XML 宣言とエンコード属性](#xml)

-   [名前空間とルート要素](#namespace)

-   [データ型](#data)

-   [Name 要素](#name)

-   [ID 要素](#id)

-   [Version 要素](#version)

-   [作成要素](#author)

-   [プロセスとプロセス要素](#processes)

-   [Application 要素](#application)

-   [共通要素](#common)

-   [SettingsLocationTemplate 要素](#settingslocationtemplate)

-   [付録: SettingsLocationTemplate .xsd](#appendix)

### <a href="" id="xml"></a>XML 宣言とエンコード属性

**必須: True**

**種類: 文字列**

XML 宣言では、XML バージョン1.0 属性 ( &lt; ? XML バージョン = "1.0") を指定する必要があり &gt; ます。 UE-V Generator によって作成された設定場所テンプレートは、UTF-8 エンコードで保存されます。ただし、エンコードは明示的に指定されません。 ベストプラクティスとして、この要素に encoding = "UTF-8" 属性を含めることをお勧めします。 製品に含まれているすべてのテンプレートにもこのタグが指定されています (Virtualization\\Templates では、Microsoft User Experience のドキュメントを参照してください)。 以下に例を示します。

`<?xml version="1.0" encoding="UTF-8"?>`

### <a href="" id="namespace"></a>名前空間とルート要素

**必須: True**

**種類: 文字列**

UE-V は、 https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate すべてのアプリケーションの名前空間を使います。 SettingsLocationTemplate はルート要素であり、他のすべての要素が含まれます。 このタグを使用して、すべてのテンプレートの参照設定の場所テンプレート:

`<SettingsLocationTemplate xmlns='https://schemas.microsoft.com/UserExperienceVirtualization/2012/SettingsLocationTemplate'>`

### <a href="" id="data"></a>データ型

UE-V アプリケーションテンプレートスキーマのデータ型を次に示します。

<a href="" id="guid"></a>**GUID**GUID は、標準のグローバル一意識別子の正規表現として "\ \ {\ [a-z-9 \]- {8} \ [a-fa-9 \]-\ [-] {4} [A-z-f0-9 \]-\ [a------ {4} {4} \]-\ [a- {12} ---------\] これは、既知のフォルダーの書式を確認するために、filesetting¥ root¥ knownfolder 要素で使われます。

<a href="" id="filenamestring"></a>**FilenameString**FilenameString は、監視されるプロセスのファイル名を指します。 この値は、regex \ [^ \ \ \ \ \ \ \ \ \ * \ \ | \ \ \ * \ \ | &lt; &gt; ) で制限されています。/: \] + (つまり、バックスラッシュ文字、アスタリスクまたは疑問符のワイルドカード文字、パイプ文字、不等号、スラッシュ、またはコロン文字) が含まれている可能性があります。

<a href="" id="idstring"></a>**Idstring**IDString は、アプリケーション要素の ID 値、SettingsLocationTemplate、共通要素を参照します (共通の設定を共有するアプリケーションスイートを記述するために使用されます)。 FilenameString と同じ regex で制限されています (\ [^] \ \ \ \ \ \ \ \ * \ \ | \ \ \ * \ \ | &lt; &gt; )/:\]+).

<a href="" id="templateversion"></a>**テンプレートのバージョン**TemplateVersion は、設定場所テンプレートのリビジョンを記述するために使用される整数値です。 この値の範囲は 0 ~ 2147483647 です。

<a href="" id="empty"></a>**空**Empty は null 値を参照します。 これは、監視するプロセスがないことを示すために、Process\\ shellprocess で使われます。 この値は、どのアプリケーションテンプレートでも使うことはできません。

<a href="" id="author"></a>**作成者**作成者データ型は、テンプレートの作成者を識別する複雑な型です。 これには、**名前**と**メール**という2つの子要素が含まれています。 Author データ型では、Email 要素が省略可能である間、Name 要素は必須です。 この型については、SettingsLocationTemplate 要素の詳細について説明します。

<a href="" id="range"></a>**範囲**Range は、**最小値**と**最大値**の2つの子要素で構成される integer クラスを定義します。 このデータ型は、ProcessVersion データ型に実装されます。 指定する場合は、最小値と最大値の両方が含まれている必要があります。

<a href="" id="processversion"></a>**Processversion**ProcessVersion は、4つの子要素を持つ型 ( **Major**、 **Minor**、 **Build**、および**Patch**) を定義します。 このデータ型は、プロセス要素によって ProductVersion と FileVersion 値を設定するために使われます。 この型のデータは、範囲値です。 主要な子要素は必須であり、他の要素は省略可能です。

<a href="" id="architecture"></a>**アーキテクチャ**アーキテクチャでは、 **Win32**と**Win64**の2つの値を列挙します。 これらの値は、プロセスアーキテクチャを指定するために使用されます。

<a href="" id="process"></a>**プロセス**プロセスデータ型は、UE-V で監視されるプロセスを記述するために使用されるコンテナーです。 これには、**ファイル名**、**アーキテクチャ**、**商品名**、 **filedescription**、 **productversion**、 **FileVersion**という6つの子要素が含まれています。 この表では、各要素のデータ型について詳しく説明します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">要素</th>
<th align="left">データ型</th>
<th align="left">Mandatory</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ル</p></td>
<td align="left"><p>FilenameString</p></td>
<td align="left"><p>True</p></td>
</tr>
<tr class="even">
<td align="left"><p>アーキテクチャ</p></td>
<td align="left"><p>アーキテクチャ</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ProductName</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>ファイルの説明</p></td>
<td align="left"><p>String</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ProductVersion</p></td>
<td align="left"><p>ProcessVersion</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>FileVersion</p></td>
<td align="left"><p>ProcessVersion</p></td>
<td align="left"><p>False</p></td>
</tr>
</tbody>
</table>

 

<a href="" id="processes"></a>**プロセス**プロセスデータ型は、1つ以上のプロセス要素のコレクションのコンテナーを表します。 次の2つの子要素がプロセスシーケンスの種類でサポートされています。**プロセス**と**shellprocess**。 プロセスは、Process 型の要素であり、ShellProcess はデータ型が空であることを示します。 シーケンスで少なくとも1つの項目を識別する必要があります。

<a href="" id="path"></a>**Path**Path は、レジストリとファイルのパスを参照するために、RegistrySetting と FileSetting で消費されます。 この要素は、 **Recursive**と**DeleteIfNotFound**の2つのオプション属性をサポートします。 どちらの値も default = "False" に設定されています。

Recursive は、パスとすべてのサブフォルダーがファイル設定に含まれていること、またはすべての子レジストリキーがレジストリ設定に含まれていることを示します。 どちらの場合も、キャプチャされたデータには、現在のレベルのすべての項目が含まれます。 FileSettings オブジェクトの場合、指定したフォルダー内のすべてのファイルは、UE-V によってキャプチャされるデータに含まれますが、フォルダーは含まれません。 レジストリパスの場合、現在のパスにあるすべての値がキャプチャされますが、子レジストリキーはキャプチャされません。 どちらの場合も、大量のデータセットまたは多数の項目をキャプチャしないように注意する必要があります。

DeleteIfNotFound 属性は、ユーザー設定の記憶域のパスデータから設定を削除します。 これは、パッケージからこれらの設定を削除すると、設定の記憶域パスファイルサーバーに大量のディスク領域が保存される可能性がある場合に適しています。

<a href="" id="filemask"></a>**Filemask**FileMask Path で定義されているフォルダーに対して、特定の種類のファイルのみを指定します。 たとえば、Path `C:\users\username\files` とファイルが含まれている可能性があり `*.txt` ます。テキストファイルのみを含めることもできます。

<a href="" id="registrysetting"></a>**Registrysetting**RegistrySetting は、レジストリキーと値のコンテナーと、UE-V エージェントの一部に関連する目的の動作を表します。 4つの子要素は、 **path**、 **Name**、 **Exclude**、および値の**パス**と**名前**のシーケンスで構成されます。

<a href="" id="filesetting"></a>**Filesetting**FileSetting には、ファイルとファイルのパスに関連付けられたパラメーターが含まれています。 4つの子要素 (**ルート**、 **Path**、 **filemask**、**除外**) が定義されています。 Root は必須で、他のオプションは省略可能です。

<a href="" id="settings"></a>**設定**設定は、特定のテンプレートに適用されるすべての設定のコンテナーです。 これには、前に説明したレジストリ、File、SystemParameter、および CustomAction の各設定のインスタンスが含まれています。 さらに、次の子要素も含めることができます。これには、次のような動作があります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">要素</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>非同期</p></td>
<td align="left"><p>非同期設定パッケージは、アプリケーションの起動をブロックせずに適用されるため、設定が適用されている間、アプリケーションは実行を開始できます。 これは、SystemParameterSetting など、API を通じて非同期的に適用できる設定に役立ち <code>get/set</code> ます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PreventOverlappingSynchronization</p></td>
<td align="left"><p>既定では、UE-V は、テンプレートを使用するアプリケーションの最後のインスタンスが閉じられている場合にのみ、アプリケーションの設定を保存します。 この要素が "false" に設定されている場合、アプリケーションの他のインスタンスが実行されている場合でも、UE-V は設定をエクスポートします。 適したテンプレート– UE-V に同梱されている共通要素セクションが含まれている場合は、このフラグを使って共有設定をアプリケーションの終了時に常にエクスポートし、最後のインスタンスが閉じられるまでは、アプリケーション固有の設定がエクスポートされないようにします。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="name"></a>Name 要素

**必須: True**

**種類: 文字列**

[名前] 設定場所テンプレートの一意の名前を指定します。 これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。 一般的に、バージョン情報を参照することは避けてください。これは、ProductVersion 要素から objected することができます。 たとえば、ではなく、を指定し `<Name>My Application</Name>` `<Name>My Application 1.1</Name>` ます。

**注** UE-V は外部の Dtd を参照しないため、設定場所テンプレートで名前付きエンティティを使うことはできません。 たとえば、登録されて &reg; いる商標記号®の参照には使用しないでください。 代わりに、このような種類の特殊文字 (®文字の & \ #174 など) を含める場合は、標準の番号付き参照を使います。 この規則は、このドキュメント内のすべての文字列値に適用されます。

<http://www.w3.org/TR/xhtml1/dtds.html>文字エンティティの完全な一覧については、を参照してください。 UTF-8 でエンコードされたドキュメントには、Unicode 文字が直接含まれている場合があります。 UE-V Generator を使用してテンプレートを保存すると、文字エンティティが自動的に Unicode 表現に変換されます。

 

### <a href="" id="id"></a>ID 要素

**必須: True**

**種類: 文字列**

ID は、特定のテンプレートの一意の識別子を入力します。 このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります (たとえば、Get-UevTemplate と Get-UevTemplateProgram PowerShell コマンドレットの出力を参照してください)。 慣例により、このタグにはスペースを含めないでください。これによってスクリプトが簡素化されます。 この要素には、やなどのテンプレートを簡単に識別できるように、アプリのバージョン番号を指定する必要があり `<ID>MicrosoftCalculator6</ID>` `<ID>MicrosoftOffice2010Win64</ID>` ます。

### <a href="" id="version"></a>Version 要素

**必須: True**

**種類: Integer**

**最小値: 0**

**最大値: 2147483647**

[バージョン] は、変更の管理追跡用の設定場所テンプレートのバージョンを示します。 UE-V Generator は、テンプレートが保存されるたびに、この数値を1つずつ自動的にインクリメントします。 このフィールドは整数である必要があることに注意してください。小数点以下の値 `<Version>2.5</Version>` は使用できません。

**ヒント:** XML コメントタグを使用して、バージョンの変更に関するメモを保存でき `<!-- -->` ます。たとえば、次のようになります。

```xml
<!--
    Version History

    Version 1 Jul 05, 2012 Initial template created by Generator - Denise@Contoso.com
    Version 2 Jul 31, 2012 Added support for app.exe v2.1.3 - Mark@Contoso.com
    Version 3 Jan 01, 2013 Added font settings support - Mark@Contoso.com
    Version 4 Jan 31, 2013 Added support for plugin settings - Tony@Contoso.com
  -->
<Version>4</Version>
```

**重要** この値は、次のような場合に、既存のテンプレートに新しいバージョンのテンプレートを適用する必要があるかどうかを確認するために照会されます。

-   スケジュールされたテンプレートの自動更新タスクの実行時

-   更新プログラム UevTemplate PowerShell コマンドレットが実行されるとき

-   WMI 経由で microsoft\\uev: SettingsLocationTemplate Update メソッドが呼び出された場合

 

### <a href="" id="author"></a>作成要素

**必須: False**

**種類: 文字列**

[作成者] は、設定場所テンプレートの作成者を指定します。 2つのオプションの子要素がサポートされています。**名前**と**メール** どちらの属性も省略可能ですが、メールの子要素が指定されている場合は、Name 要素と共に指定する必要があります。 [Author] は、設定場所テンプレートの連絡先の完全な名前を示し、メールは作成者のメールアドレスを参照する必要があります。 この情報は、一般に公開されるテンプレート ( [Ue-v テンプレートギャラリー](https://gallery.technet.microsoft.com/site/search?f%5B0%5D.Type=RootCategory&f%5B0%5D.Value=UE-V)など) に含めることをお勧めします。

### <a href="" id="processes"></a>プロセスとプロセス要素

**必須: True**

**Type: Element**

プロセスには、少なくとも1つの要素が含まれます。これには、 `<Process>` **ファイル名**、**アーキテクチャ**、**商品名**、 **filedescription**、 **productversion**、 **FileVersion**という子要素が含まれています。 ファイル名の子要素は必須であり、他の項目は省略可能です。 完全に入力された要素には、次の例のようなタグが含まれています。

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <Architecture>Win64</Architecture>
  <ProductName> MyApplication </ProductName>
  <FileDescription>MyApplication.exe</FileDescription>
  <ProductVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="2" Maximum="2" />
    <Minor Minimum="0" Maximum="0" />
    <Build Minimum="0" Maximum="0" />
    <Patch Minimum="5" Maximum="5" />
  </FileVersion>
</Process>
```

### ル

**必須: True**

**種類: 文字列**

Filename は、ファイルシステムに表示される実行可能ファイルの実際のファイル名を指します。 この要素は、テンプレートがプロセスに適用されるかどうかを評価するために UE-V が使う主要な条件を指定します。 この要素は、設定場所テンプレート XML で指定する必要があります。

有効なファイル名は、正規表現 \ [^] \ \ \ \ \ \ \ * \ \ | \ \ \ * \ \ | &lt; &gt;/: \] +、つまり、バックスラッシュ文字、アスタリスクまたは疑問符のワイルドカード文字、パイプ文字、不等号、スラッシュ、またはコロン (\ \?) が含まれていない可能性があります。 \* |&lt; &gt; /または: 文字)。

**ヒント:** この regex に対して文字列をテストするには、PowerShell コマンドウィンドウを使って、実行可能ファイルの名前を**ファイル**名に置き換えます。

`"YourFileName.exe" -match  "[\\\?\*\|<>/:]+"`

値が**True**の場合は、文字列に不正な文字が含まれていることを示します。 次に、不正な値の例をいくつか示します。

-   \\\\server\\share\\program.exe

-   プログラム \ * .exe

-   Pro? ram.exe

-   プログラム &lt; 1 &gt; . .exe

**注** UE-V Generator は、指定された文字より大きい文字と小さい文字をそれぞれエンコードし &gt; &lt; ます。

 

まれに、ファイル名の値に .exe 拡張子が含まれているとは限りませんが、値の一部として指定する必要があります。 たとえば、 `<Filename>MyApplictication.exe</Filename>` の代わりにを指定する必要があり `<Filename>MyApplictication</Filename>` ます。 実行可能ファイルの実際の名前が "MyApplication.exe" の場合、2番目の例では、テンプレートはプロセスに適用されません。

### アーキテクチャ

**必須: False**

**Type: Architecture (文字列)**

アーキテクチャとは、ターゲットの実行可能ファイルがコンパイルされたプロセッサアーキテクチャを指します。 有効な値は、32ビットアプリケーションまたは64ビットアプリケーション用の Win64 の Win32 です。 存在する場合、このタグは、設定場所テンプレートを特定のアプリケーションアーキテクチャに適用することを制限します。 この例については、UE-V に含まれる% programfiles% ¥ Microsoft User Experience Virtualization\\templates\\ MicrosoftOffice2010Win32.xml と MicrosoftOffice2010Win64.xml ファイルを比較します。 これは、異なるバージョンの実行可能ファイル間で相対パスが変更された場合、またはプロセッサアーキテクチャを切り替えるときに設定が追加または削除された場合に役立ちます。

この要素が存在しない場合、設定場所テンプレートはプロセスのアーキテクチャを無視し、ファイル名とその他の属性が適用されている場合、32と64ビットの両方のプロセスに適用されます。

**注** UE-V は、このバージョンの ARM プロセッサをサポートしていません。

 

### ProductName

**必須: False**

**種類: 文字列**

ProductName は、管理目的またはレポート用に製品を識別するために使用されるオプションの要素です。 ProductName はファイル名とは異なり、その値に対する正規表現の制限はありません。 これにより、実行可能ファイル名が明確でない可能性のあるプロセスの説明をより簡単に理解できます。 以下に例を示します。

```xml
<Process>
  <Filename>MyApplication.exe</Filename>
  <ProductName>My Application 6.x by Contoso.com</ProductName>
  <ProductVersion>
    <Major Minimum="6" Maximum="6" />
  </ProductVersion>
</Process>
```

### ファイルの説明

**必須: False**

**種類: 文字列**

FileDescription は、実行可能ファイルの管理の説明を可能にするオプションのタグです。 これは無料のテキストフィールドであり、実行可能ファイルの機能を識別する必要があるソフトウェアパッケージ内の複数の実行可能ファイルを区別するのに役立ちます。

たとえば、次に示すように、適したアプリケーションでは、2つの実行可能ファイル (MyApplication.exe と MyApplicationHelper.exe) の機能についての通知を表示すると便利な場合があります。

```xml
<Processes>
  <Process>
    <Filename>MyApplication.exe</Filename>
    <FileDescription>My Application Main Engine</ FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
  <Process>
    <Filename>MyApplicationHelper.exe</Filename>
    <FileDescription>My Application Background Process Executable</FileDescription>
    <ProductVersion>
      <Major Minimum="6" Maximum="6" />
    </ProductVersion>
  </Process>
</Processes>
```

### ProductVersion

**必須: False**

**種類: 文字列**

ProductVersion は、ファイルのメジャーバージョンとマイナー製品バージョン、およびビルドとパッチレベルを指します。 ProductVersion は省略可能な要素ですが、指定する場合は、少なくとも主要な子要素が含まれている必要があります。 この値は、最小値の "X" 最大値 = "Y" (X と Y は整数) の範囲を表す必要があります。 最小値と最大値は同じにすることができます。

製品とファイルのバージョンの要素が指定されていない可能性があります。 これにより、テンプレートは "バージョンに依存しない" という意味になります。つまり、指定した実行可能ファイルのすべてのバージョンにテンプレートが適用されます。

**例 1:**

製品バージョン: 1.0 は、UE-V Generator で指定されている次の XML を生成します。

```xml
<ProductVersion>
  <Major Minimum="1" Maximum="1" />
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

**例 2:**

ファイルバージョン: UE-V Generator で指定された5.0.2.1000 は、次の XML を生成します。

```xml
<FileVersion>
  <Major Minimum="5" Maximum="5" />
  <Minor Minimum="0" Maximum="0" />
  <Build Minimum="2" Maximum="2" />
  <Patch Minimum="1000" Maximum="1000" />
</FileVersion>
```

**間違った例1–不完全な範囲:**

最小属性のみが存在します。 範囲には最大値も含める必要があります。

```xml
<ProductVersion>
  <Major Minimum="2" />
</ProductVersion>
```

**間違った例2–主要要素のない Minor:**

Minor 要素のみが存在します。 メジャーも含める必要があります。

```xml
<ProductVersion>
  <Minor Minimum="0" Maximum="0" />
</ProductVersion>
```

### FileVersion

**必須: False**

**種類: 文字列**

FileVersion は、公開されたアプリケーションのリリースバージョンと、コンポーネント実行可能ファイルの内部ビルドの詳細を区別します。 ほとんどの商用アプリケーションでは、これらの番号は同じです。 実際には、ファイルの製品バージョンはファイルの一般的なバージョン id を示していますが、ファイルバージョンはファイルの特定のビルドを示します (修正プログラムや更新プログラムの場合など)。 これにより、検出ロジックを壊すことなくファイルを一意に識別できます。

特定の実行可能ファイルの製品バージョンとファイルバージョンを確認するには、Windows エクスプローラーでファイルを右クリックし、[プロパティ] を選択して、[詳細] タブをクリックします。

アプリケーションの FileVersion 要素を含めることで、細かい微調整による検出ロジックを行うことができますが、ほとんどのアプリケーションには必要ありません。 ProductVersion 要素の設定が最初にチェックされ、次に FileVersion がチェックされます。 より限定的な設定が適用されます。

FileVersion の子要素と構文規則は、ProductVersion バージョンと同じです。

```xml
<Process>
  <Filename>MSACCESS.EXE</Filename>
  <Architecture>Win32</Architecture>
  <ProductVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </ProductVersion>
  <FileVersion>
    <Major Minimum="14" Maximum="14" />
    <Minor Minimum="0" Maximum="0" />
  </FileVersion>
</Process>
```

### <a href="" id="application"></a>Application 要素

アプリケーションは、特定のアプリケーションに適用される設定のコンテナーです。 これは、次のフィールド/型のコレクションです。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">フィールド/型</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Name (名前)</p></td>
<td align="left"><p>設定場所テンプレートの一意の名前を指定します。 これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。 詳細については、「名前」を参照してください <a href="#name" data-raw-source="[Name](#name)"> </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ID</p></td>
<td align="left"><p>特定のテンプレートの一意の識別子を設定します。 このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります。 詳細については、「ID」を参照してください <a href="#id" data-raw-source="[ID](#id)"> </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>説明</p></td>
<td align="left"><p>テンプレートの説明 (省略可能)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI に表示されるオプションの名前。言語ロケールによってローカライズされます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>言語ロケールによってローカライズされた省略可能なテンプレートの説明です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>バージョン</p></td>
<td align="left"><p>変更の管理追跡用の設定場所テンプレートのバージョンを示します。 詳細については、「バージョン」を参照してください <a href="#version" data-raw-source="[Version](#version)"> </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeferToMSAccount</p></td>
<td align="left"><p>このテンプレートが Microsoft アカウントと組み合わせて有効になっているかどうかを制御します。 コンピューター上のユーザーに対して MSA の同期が有効になっている場合、このテンプレートは自動的に無効になります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeferToOffice365</p></td>
<td align="left"><p>MSA の場合と同様に、このテンプレートを Office365 と組み合わせて有効にするかどうかを制御します。 設定の同期に Office 365 が使用されている場合、このテンプレートは自動的に無効になります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>プロセス</p></td>
<td align="left"><p>1つ以上のプロセス要素のコレクションのコンテナー。 詳細については、「プロセス」を参照してください <a href="#processes" data-raw-source="[Processes](#processes)"> </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定</p></td>
<td align="left"><p>特定のテンプレートに適用されるすべての設定のコンテナー。 これには、Registry、File、SystemParameter、および CustomAction の各設定のインスタンスが含まれます。 詳細については、「 <strong> </strong> データ型の設定」を参照してください <a href="#data" data-raw-source="[Data types](#data)"> </a> 。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="common"></a>共通要素

Common は Application 要素と似ていますが、常に、2つ以上のアプリケーション要素に関連付けられます。 共通セクションは、これらのアプリケーションインスタンス間で共有される一連の設定を表します。 これは、次のフィールド/型のコレクションです。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">フィールド/型</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Name (名前)</p></td>
<td align="left"><p>設定場所テンプレートの一意の名前を指定します。 これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。 詳細については、「名前」を参照してください <a href="#name" data-raw-source="[Name](#name)"> </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ID</p></td>
<td align="left"><p>特定のテンプレートの一意の識別子を設定します。 このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります。 詳細については、「ID」を参照してください <a href="#id" data-raw-source="[ID](#id)"> </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>説明</p></td>
<td align="left"><p>テンプレートの説明 (省略可能)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI に表示されるオプションの名前。言語ロケールによってローカライズされます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>言語ロケールによってローカライズされた省略可能なテンプレートの説明です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>バージョン</p></td>
<td align="left"><p>変更の管理追跡用の設定場所テンプレートのバージョンを示します。 詳細については、「バージョン」を参照してください <a href="#version" data-raw-source="[Version](#version)"> </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DeferToMSAccount</p></td>
<td align="left"><p>このテンプレートが Microsoft アカウントと組み合わせて有効になっているかどうかを制御します。 コンピューター上のユーザーに対して MSA の同期が有効になっている場合、このテンプレートは自動的に無効になります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeferToOffice365</p></td>
<td align="left"><p>MSA の場合と同様に、このテンプレートを Office365 と組み合わせて有効にするかどうかを制御します。 設定の同期に Office 365 が使用されている場合、このテンプレートは自動的に無効になります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定</p></td>
<td align="left"><p>特定のテンプレートに適用されるすべての設定のコンテナー。 これには、Registry、File、SystemParameter、および CustomAction の各設定のインスタンスが含まれます。 詳細については、「 <strong> </strong> データ型の設定」を参照してください <a href="#data" data-raw-source="[Data types](#data)"> </a> 。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="settingslocationtemplate"></a>SettingsLocationTemplate 要素

この要素は、1つのアプリケーションまたは一連のアプリケーションの設定を定義します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">フィールド/型</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Name (名前)</p></td>
<td align="left"><p>設定場所テンプレートの一意の名前を指定します。 これは、WMI、PowerShell、イベントビューアー、デバッグログでテンプレートを参照するときに表示するために使われます。 詳細については、「名前」を参照してください <a href="#name" data-raw-source="[Name](#name)"> </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ID</p></td>
<td align="left"><p>特定のテンプレートの一意の識別子を設定します。 このタグは、UE-V Agent が実行時にテンプレートを参照するために使用するプライマリ識別子になります。 詳細については、「ID」を参照してください <a href="#id" data-raw-source="[ID](#id)"> </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>説明</p></td>
<td align="left"><p>テンプレートの説明 (省略可能)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LocalizedNames</p></td>
<td align="left"><p>UI に表示されるオプションの名前。言語ロケールによってローカライズされます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocalizedDescriptions</p></td>
<td align="left"><p>言語ロケールによってローカライズされた省略可能なテンプレートの説明です。</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="appendix"></a>付録: SettingsLocationTemplate .xsd

次に示すのは、要素、子要素、属性、パラメーターが表示された SettingsLocationTemplate です。

```xml
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="UevSettingsLocationTemplate"
  targetNamespace="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  elementFormDefault="qualified"
  xmlns="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  xmlns:mstns="https://schemas.microsoft.com/UserExperienceVirtualization/2013/SettingsLocationTemplate"
  xmlns:xs="http://www.w3.org/2001/XMLSchema">

  <xs:simpleType name="Guid">
    <xs:restriction base="xs:string">
      <xs:pattern value="\{[a-fA-F0-9]{8}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{4}-[a-fA-F0-9]{12}\}" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="FilenameString">
    <xs:restriction base="xs:string">
      <xs:pattern value="[^\\\?\*\|&lt;&gt;/:]+" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="IDString">
    <xs:restriction base="xs:string">
      <xs:pattern value="[^\\\?\*\|&lt;&gt;/:.]+" />
    </xs:restriction>
  </xs:simpleType>

  <xs:simpleType name="TemplateVersion">
    <xs:restriction base="xs:integer">
      <xs:minInclusive value="0" />
      <xs:maxInclusive value="2147483647" />
    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Empty">
    <xs:sequence/>
  </xs:complexType>

  <xs:complexType name="LocalizedString">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="Locale" type="xs:string" use="required"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>

  <xs:complexType name="LocalizedName">
    <xs:sequence>
      <xs:element name="Name" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="LocalizedDescription">
    <xs:sequence>
      <xs:element name="Description" type="LocalizedString" minOccurs="1" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Author">
    <xs:all>
      <xs:element name="Name" type="xs:string" minOccurs="1" />
      <xs:element name="Email" type="xs:string" minOccurs="0" />
    </xs:all>
  </xs:complexType>

  <xs:complexType name="Range">
    <xs:attribute name="Minimum" type="xs:integer" use="required"/>
    <xs:attribute name="Maximum" type="xs:integer" use="required"/>
  </xs:complexType>

  <xs:complexType name="ProcessVersion">
    <xs:sequence>
      <xs:element name="Major" type="Range" minOccurs="1" />
      <xs:element name="Minor" type="Range" minOccurs="0" />
      <xs:element name="Build" type="Range" minOccurs="0" />
      <xs:element name="Patch" type="Range" minOccurs="0" />
    </xs:sequence>
  </xs:complexType>

  <xs:simpleType name="Architecture">
    <xs:restriction base="xs:string">
      <xs:enumeration value="Win32"/>
      <xs:enumeration value="Win64"/>
    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Process">
    <xs:sequence>
      <xs:element name="Filename" type="FilenameString" minOccurs="1" />
      <xs:element name="Architecture" type="Architecture" minOccurs="0" />
      <xs:element name="ProductName" type="xs:string" minOccurs="0" />
      <xs:element name="FileDescription" type="xs:string" minOccurs="0" />
      <xs:element name="ProductVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
      <xs:element name="FileVersion" type="ProcessVersion" minOccurs="0" maxOccurs="unbounded"/>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Processes">
    <xs:sequence>
      <xs:choice minOccurs="1">
        <xs:element name="Process" type="Process" />
        <xs:element name="ShellProcess" type="Empty" />
      </xs:choice>
      <xs:element name="Process" type="Process" minOccurs="0" maxOccurs="unbounded" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Path">
    <xs:simpleContent>
      <xs:extension base="xs:string">
        <xs:attribute name="Recursive" type="xs:boolean" default="false"/>
        <xs:attribute name="DeleteIfNotFound" type="xs:boolean" default="false"/>
      </xs:extension>
    </xs:simpleContent>
  </xs:complexType>

  <xs:complexType name="RegistrySetting">
    <xs:sequence>
      <xs:element name="Path" type="Path" />
      <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
      <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="Path" type="Path" minOccurs="0" />
            <xs:element name="Name" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
          </xs:sequence>
        </xs:complexType>
      </xs:element>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="FileSetting">
    <xs:sequence>

      <xs:element name="Root">
        <xs:complexType>
          <xs:choice>
            <xs:element name="KnownFolder" type="Guid" />
            <xs:element name="RegistryEntry" type="xs:string" />
            <xs:element name="EnvironmentVariable" type="xs:string" />
          </xs:choice>
        </xs:complexType>
      </xs:element>

      <xs:element name="Path" minOccurs="0" type="Path" />
      <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded"/>

      <xs:element name="Exclude" minOccurs="0" maxOccurs="unbounded">
        <xs:complexType>
          <xs:sequence>
            <xs:element name="Path" type="Path" minOccurs="0" />
            <xs:element name="FileMask" type="xs:string" minOccurs="0" maxOccurs="unbounded" />
          </xs:sequence>
        </xs:complexType>
      </xs:element>

    </xs:sequence>
  </xs:complexType>

  <xs:simpleType name="SystemParameterSetting">
    <xs:restriction base="xs:string">

      <!-- Accessibility parameters -->
      <xs:enumeration value="AccessTimeout"/>
      <xs:enumeration value="AudioDescription"/>
      <xs:enumeration value="ClientAreaAnimation"/>
      <xs:enumeration value="DisableOverlappedContent"/>
      <xs:enumeration value="FilterKeys"/>
      <xs:enumeration value="FocusBorderHeight"/>
      <xs:enumeration value="FocusBorderWidth"/>
      <xs:enumeration value="HighContrast"/>
      <xs:enumeration value="MessageDuration"/>
      <xs:enumeration value="MouseClickLock"/>
      <xs:enumeration value="MouseClickLockTime"/>
      <xs:enumeration value="MouseKeys"/>
      <xs:enumeration value="MouseSonar"/>
      <xs:enumeration value="MouseVanish"/>
      <xs:enumeration value="ScreenReader"/>
      <xs:enumeration value="ShowSounds"/>
      <xs:enumeration value="SoundSentry"/>
      <xs:enumeration value="StickyKeys"/>
      <xs:enumeration value="ToggleKeys"/>

      <!-- Input parameters -->
      <xs:enumeration value="Beep"/>
      <xs:enumeration value="BlockSendInputResets"/>
      <xs:enumeration value="DefaultInputLang"/>
      <xs:enumeration value="DoubleClickTime"/>
      <xs:enumeration value="DoubleClkHeight"/>
      <xs:enumeration value="DoubleClkWidth"/>
      <xs:enumeration value="KeyboardCues"/>
      <xs:enumeration value="KeyboardDelay"/>
      <xs:enumeration value="KeyboardPref"/>
      <xs:enumeration value="KeyboardSpeed"/>
      <xs:enumeration value="Mouse"/>
      <xs:enumeration value="MouseButtonSwap"/>
      <xs:enumeration value="MouseHoverHeight"/>
      <xs:enumeration value="MouseHoverTime"/>
      <xs:enumeration value="MouseHoverWidth"/>
      <xs:enumeration value="MouseSpeed"/>
      <xs:enumeration value="MouseTrails"/>
      <xs:enumeration value="SnapToDefButton"/>
      <xs:enumeration value="WheelScrollChars"/>
      <xs:enumeration value="WheelScrollLines"/>

      <!-- Desktop parameters (limited subset) -->
      <xs:enumeration value="DeskWallpaper"/>
      <xs:enumeration value="DesktopColor"/>

    </xs:restriction>
  </xs:simpleType>

  <xs:complexType name="Settings">
    <xs:sequence>
      <xs:element name="Asynchronous" type="xs:boolean" minOccurs="0" />
      <xs:element name="PreventOverlappingSynchronization" type="xs:boolean" minOccurs="0" />
      <xs:choice minOccurs="0" maxOccurs="unbounded">
        <xs:element name="Registry" type="RegistrySetting" />
        <xs:element name="File" type="FileSetting" />
        <xs:element name="SystemParameter" type="SystemParameterSetting" />
      </xs:choice>
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Common">
    <xs:sequence>
      <xs:element name="Name" type="xs:string" />
      <xs:element name="ID" type="IDString" />
      <xs:element name="Description" type="xs:string" minOccurs="0" />
      <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
      <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
      <xs:element name="Version" type="xs:integer" />
      <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
      <xs:element name="Settings" type="Settings" />
    </xs:sequence>
  </xs:complexType>

  <xs:complexType name="Application">
    <xs:sequence>
      <xs:element name="Name" type="xs:string" />
      <xs:element name="ID" type="IDString" />
      <xs:element name="Description" type="xs:string" minOccurs="0" />
      <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
      <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />
      <xs:element name="Version" type="xs:integer" />
      <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
      <xs:element name="Processes" type="Processes" />
      <xs:element name="Settings" type="Settings" />
    </xs:sequence>
  </xs:complexType>


  <xs:element name="SettingsLocationTemplate">
    <xs:complexType>
      <xs:sequence>

        <xs:element name="Name" type="xs:string" />
        <xs:element name="ID" type="IDString" />
        <xs:element name="Description" type="xs:string" minOccurs="0" />
        <xs:element name="LocalizedNames" type="LocalizedName" minOccurs="0" />
        <xs:element name="LocalizedDescriptions" type="LocalizedDescription" minOccurs="0" />

        <xs:choice>

          <!-- Single application -->
          <xs:sequence>
            <xs:element name="Version" type="TemplateVersion" />
            <xs:element name="Author" type="Author" minOccurs="0" />
            <xs:element name="DeferToMSAccount" type="Empty"  minOccurs="0" />
            <xs:element name="Processes" type="Processes" />
            <xs:element name="Settings" type="Settings" />
          </xs:sequence>

          <!-- Suite of applications -->
          <xs:sequence>
            <xs:element name="ManageSuiteOnly" type="xs:boolean" minOccurs="0" />
            <xs:element name="Author" type="Author" minOccurs="0" />
            <xs:element name="Common" type="Common" />
            <xs:element name="Application" type="Application" minOccurs="2" maxOccurs="unbounded" />
          </xs:sequence>

        </xs:choice>

      </xs:sequence>
    </xs:complexType>
  </xs:element>
  <!-- SettingsLocationTemplate -->

</xs:schema>
```






## 関連トピック


[カスタム ue-v (ue-v) テンプレートと UE-V Generator を使って作業する](working-with-custom-ue-v-2x-templates-and-the-ue-v-2x-generator-new-uevv2.md)

[UE-V 2.x のテクニカル リファレンス](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





