---
title: テキスト エディターを使用して OSD ファイルを編集する方法
description: テキスト エディターを使用して OSD ファイルを編集する方法
author: dansimp
ms.assetid: f4263a1b-824f-49b9-8060-b8229c9d9960
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c83547b38cee7e91e8348689583e0542a88dab83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817444"
---
# <span data-ttu-id="08c70-103">テキスト エディターを使用して OSD ファイルを編集する方法</span><span class="sxs-lookup"><span data-stu-id="08c70-103">How to Edit an OSD File Using a Text Editor</span></span>


<span data-ttu-id="08c70-104">テキストエディターを使用して、開いているソフトウェア記述子 (OSD) ファイルを編集するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="08c70-104">Use the following procedure to edit an Open Software Descriptor (OSD) file by using a text editor.</span></span>

**<span data-ttu-id="08c70-105">テキストエディターを使用して OSD ファイルを編集するには</span><span class="sxs-lookup"><span data-stu-id="08c70-105">To edit an OSD file by using a text editor</span></span>**

1.  <span data-ttu-id="08c70-106">任意の XML または ASCII テキストエディター (Microsoft メモ帳など) を使用して OSD ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="08c70-106">Open the OSD file using any XML or ASCII text editor—for example, Microsoft Notepad.</span></span>

    <span data-ttu-id="08c70-107">**注** OSD ファイルを変更する前に、インストールディレクトリの XSD ファイルで規定されているスキーマを読みます。</span><span class="sxs-lookup"><span data-stu-id="08c70-107">**Note** Before modifying the OSD file, read the schema prescribed by the XSD file in the install directory.</span></span> <span data-ttu-id="08c70-108">このスキーマに従わないと、シーケンス処理されたアプリケーションが正常に起動できないというエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="08c70-108">Failing to follow this schema might introduce errors that prevent a sequenced application from starting successfully.</span></span>

     

2.  <span data-ttu-id="08c70-109">選択した XML または ASCII テキストエディターを使用して、指定されたスキーマと次のガイドラインに従って OSD ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="08c70-109">Edit the OSD file using your XML or ASCII text editor of choice, adhering to the prescribed schema and the following guidelines:</span></span>

    1.  <span data-ttu-id="08c70-110">名前付き要素が、softpkg root 要素内で入れ子になっていることを確認し &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="08c70-110">Ensure that named elements are nested within the &lt;SOFTPKG&gt; root element.</span></span>

    2.  <span data-ttu-id="08c70-111">要素名がすべて大文字であることを確認します。</span><span class="sxs-lookup"><span data-stu-id="08c70-111">Ensure that element names are in all uppercase letters.</span></span>

    3.  <span data-ttu-id="08c70-112">属性値は、大文字と小文字が区別されることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="08c70-112">Be aware that attribute values are case sensitive.</span></span>

    4.  <span data-ttu-id="08c70-113">「慎重に入力する」と入力して、XML の仕様を確認します。</span><span class="sxs-lookup"><span data-stu-id="08c70-113">Type carefully, and observe the XML specifications.</span></span>

## <span data-ttu-id="08c70-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="08c70-114">Related topics</span></span>


[<span data-ttu-id="08c70-115">[OSD] タブについて</span><span class="sxs-lookup"><span data-stu-id="08c70-115">About the OSD Tab</span></span>](about-the-osd-tab.md)

[<span data-ttu-id="08c70-116">OSD ファイルを編集する方法</span><span class="sxs-lookup"><span data-stu-id="08c70-116">How to Edit an OSD File</span></span>](how-to-edit-an-osd-file.md)

[<span data-ttu-id="08c70-117">OSD ファイルの要素</span><span class="sxs-lookup"><span data-stu-id="08c70-117">OSD File Elements</span></span>](osd-file-elements.md)

 

 





