---
title: '방법: XAML에서 특수 문자 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: 18934e06f45ca4b88f48bce8a310a07b460a5f53
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57377965"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="b20d8-102">방법: XAML에서 특수 문자 사용</span><span class="sxs-lookup"><span data-stu-id="b20d8-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="b20d8-103">마크업 파일에서 만든 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 에 자동으로 저장 됩니다는 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] utf-8 파일 형식 이므로 악센트 부호와 같은 대부분의 특수 문자가 올바르게 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="b20d8-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="b20d8-104">그러나 다르게 처리되는 일반적으로 사용되는 특수 문자 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b20d8-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="b20d8-105">이러한 특수 문자에 따라 합니다 [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 인코딩 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="b20d8-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="b20d8-106">다음 표는 이 특수 문자 집합을 인코딩하는 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b20d8-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="b20d8-107">문자</span><span class="sxs-lookup"><span data-stu-id="b20d8-107">Character</span></span>|<span data-ttu-id="b20d8-108">구문</span><span class="sxs-lookup"><span data-stu-id="b20d8-108">Syntax</span></span>|<span data-ttu-id="b20d8-109">설명</span><span class="sxs-lookup"><span data-stu-id="b20d8-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="b20d8-110">보다 작음 기호</span><span class="sxs-lookup"><span data-stu-id="b20d8-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="b20d8-111">보다 큼 기호</span><span class="sxs-lookup"><span data-stu-id="b20d8-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="b20d8-112">앰퍼샌드 기호</span><span class="sxs-lookup"><span data-stu-id="b20d8-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="b20d8-113">"</span><span class="sxs-lookup"><span data-stu-id="b20d8-113">"</span></span>|`&quot;`|<span data-ttu-id="b20d8-114">큰따옴표 기호</span><span class="sxs-lookup"><span data-stu-id="b20d8-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="b20d8-115">파일을 만드는 경우는 태그 텍스트를 사용 하 여 편집기와 같은 [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] 메모장에서 파일을 저장 해야 합니다 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] 인코딩된 특수 문자를 보존 하려면 utf-8 파일 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b20d8-115">If you create a markup file using a text editor, such as [!INCLUDE[TLA#tla_mswin](../../../../includes/tlasharptla-mswin-md.md)] Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="b20d8-116">다음 예제에서는 태그를 만들 때 텍스트에 특수 문자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b20d8-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b20d8-117">예제</span><span class="sxs-lookup"><span data-stu-id="b20d8-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
