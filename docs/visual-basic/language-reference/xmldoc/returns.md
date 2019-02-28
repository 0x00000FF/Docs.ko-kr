---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 96b9754332b7b9c6c7823aecab6a93b0aa7ffd21
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975461"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="5d765-102">\<반환 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d765-102">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="5d765-103">함수 또는 속성의 반환 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d765-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d765-104">구문</span><span class="sxs-lookup"><span data-stu-id="5d765-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5d765-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5d765-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="5d765-106">반환 값에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="5d765-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5d765-107">설명</span><span class="sxs-lookup"><span data-stu-id="5d765-107">Remarks</span></span>  
 <span data-ttu-id="5d765-108">사용 된 `<returns>` 반환 값을 설명 하는 메서드 선언의 주석에서 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="5d765-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="5d765-109">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5d765-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5d765-110">예제</span><span class="sxs-lookup"><span data-stu-id="5d765-110">Example</span></span>  
 <span data-ttu-id="5d765-111">이 예제에서는 합니다 `<returns>` 기능을 설명 하는 태그를 `DoesRecordExist` 함수에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d765-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="5d765-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d765-112">See also</span></span>
- [<span data-ttu-id="5d765-113">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="5d765-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
