---
title: <typeparam> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: d7fb980545a532e39310ea3e9d663a2b5a81a006
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56968454"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="df4b2-102">\<typeparam > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="df4b2-102">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="df4b2-103">형식 매개 변수 이름 및 설명을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="df4b2-103">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="df4b2-104">구문</span><span class="sxs-lookup"><span data-stu-id="df4b2-104">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="df4b2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="df4b2-105">Parameters</span></span>  
 `name`  
 <span data-ttu-id="df4b2-106">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="df4b2-106">The name of the type parameter.</span></span> <span data-ttu-id="df4b2-107">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="df4b2-107">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="df4b2-108">형식 매개 변수의 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="df4b2-108">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="df4b2-109">설명</span><span class="sxs-lookup"><span data-stu-id="df4b2-109">Remarks</span></span>  
 <span data-ttu-id="df4b2-110">사용 하 여를 `<typeparam>` 태그의 주석에 제네릭 형식 또는 제네릭 멤버 선언은 형식 매개 변수 중 하나를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="df4b2-110">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="df4b2-111">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="df4b2-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="df4b2-112">예제</span><span class="sxs-lookup"><span data-stu-id="df4b2-112">Example</span></span>  
 <span data-ttu-id="df4b2-113">이 예제에서는 합니다 `<typeparam>` 설명 하는 태그를 `id` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="df4b2-113">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="df4b2-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="df4b2-114">See also</span></span>
- [<span data-ttu-id="df4b2-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="df4b2-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
