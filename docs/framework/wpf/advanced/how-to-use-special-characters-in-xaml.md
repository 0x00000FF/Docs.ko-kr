---
title: '방법: XAML의 특수 문자 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- Unicode UTF-8 file format
- UTF-8 file format
- characters [WPF], special
- typography [WPF], special characters
- special characters [WPF]
ms.assetid: a57776d1-f353-4794-afa0-bfa3c712ed1c
ms.openlocfilehash: 61ee38319b2f0aa46690fb063f6ffe6612f993ad
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918444"
---
# <a name="how-to-use-special-characters-in-xaml"></a><span data-ttu-id="a8074-102">방법: XAML의 특수 문자 사용</span><span class="sxs-lookup"><span data-stu-id="a8074-102">How to: Use Special Characters in XAML</span></span>
<span data-ttu-id="a8074-103">에서 [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] 만든 태그 파일은 자동으로 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] utf-8 파일 형식으로 저장 됩니다. 즉, 대부분의 특수 문자 (예: 악센트 표시)가 올바르게 인코딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="a8074-103">Markup files that are created in [!INCLUDE[TLA#tla_visualstu](../../../../includes/tlasharptla-visualstu-md.md)] are automatically saved in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format, which means that most special characters, such as accent marks, are encoded correctly.</span></span> <span data-ttu-id="a8074-104">그러나 다르게 처리되는 일반적으로 사용되는 특수 문자 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8074-104">However, there is a set of commonly-used special characters that are handled differently.</span></span> <span data-ttu-id="a8074-105">이러한 특수 문자는 [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] 인코딩에 대 한 표준을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="a8074-105">These special characters follow the [!INCLUDE[TLA#tla_w3c](../../../../includes/tlasharptla-w3c-md.md)] [!INCLUDE[TL A#tla_xml](../../../../includes/tlasharptla-xml-md.md)] standard for encoding.</span></span>  
  
 <span data-ttu-id="a8074-106">다음 표는 이 특수 문자 집합을 인코딩하는 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8074-106">The following table shows the syntax for encoding this set of special characters:</span></span>  
  
|<span data-ttu-id="a8074-107">문자</span><span class="sxs-lookup"><span data-stu-id="a8074-107">Character</span></span>|<span data-ttu-id="a8074-108">구문</span><span class="sxs-lookup"><span data-stu-id="a8074-108">Syntax</span></span>|<span data-ttu-id="a8074-109">Description</span><span class="sxs-lookup"><span data-stu-id="a8074-109">Description</span></span>|  
|---------------|------------|-----------------|  
|<|`&lt;`|<span data-ttu-id="a8074-110">보다 작음 기호</span><span class="sxs-lookup"><span data-stu-id="a8074-110">Less than symbol.</span></span>|  
|>|`&gt;`|<span data-ttu-id="a8074-111">보다 큼 기호</span><span class="sxs-lookup"><span data-stu-id="a8074-111">Greater than sign.</span></span>|  
|&|`&amp;`|<span data-ttu-id="a8074-112">앰퍼샌드 기호</span><span class="sxs-lookup"><span data-stu-id="a8074-112">Ampersand symbol.</span></span>|  
|<span data-ttu-id="a8074-113">"</span><span class="sxs-lookup"><span data-stu-id="a8074-113">"</span></span>|`&quot;`|<span data-ttu-id="a8074-114">큰따옴표 기호</span><span class="sxs-lookup"><span data-stu-id="a8074-114">Double quote symbol.</span></span>|  
  
> [!NOTE]
> <span data-ttu-id="a8074-115">Windows 메모장과 같은 텍스트 편집기를 사용 하 여 태그 파일을 만드는 경우 인코드된 특수 문자를 유지 하기 위해 파일을 [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] utf-8 파일 형식으로 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8074-115">If you create a markup file using a text editor, such as Windows Notepad, you must save the file in the [!INCLUDE[TLA#tla_unicode](../../../../includes/tlasharptla-unicode-md.md)] UTF-8 file format in order to preserve any encoded special characters.</span></span>  
  
 <span data-ttu-id="a8074-116">다음 예제에서는 태그를 만들 때 텍스트에 특수 문자를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a8074-116">The following example shows how you can use special characters in text when creating markup.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a8074-117">예제</span><span class="sxs-lookup"><span data-stu-id="a8074-117">Example</span></span>  
 [!code-xaml[SpecialCharsSnippets#SpecialCharsSnippet1](~/samples/snippets/csharp/VS_Snippets_Wpf/SpecialCharsSnippets/CS/Window1.xaml#specialcharssnippet1)]
