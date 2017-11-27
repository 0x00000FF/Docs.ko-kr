---
title: "&lt;반환&gt; (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6130a6fabe450900fe19ef4d361654508f907ea
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="ltreturnsgt-visual-basic"></a><span data-ttu-id="90def-102">&lt;반환&gt; (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="90def-102">&lt;returns&gt; (Visual Basic)</span></span>
<span data-ttu-id="90def-103">속성 또는 함수 반환 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="90def-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90def-104">구문</span><span class="sxs-lookup"><span data-stu-id="90def-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a><span data-ttu-id="90def-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="90def-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="90def-106">반환 값에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="90def-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="90def-107">설명</span><span class="sxs-lookup"><span data-stu-id="90def-107">Remarks</span></span>  
 <span data-ttu-id="90def-108">사용 하 여는 `<returns>` 반환 값을 설명 하는 메서드 선언에 대 한 설명에는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="90def-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="90def-109">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="90def-109">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="90def-110">예제</span><span class="sxs-lookup"><span data-stu-id="90def-110">Example</span></span>  
 <span data-ttu-id="90def-111">사용 하 여이 예제는 `<returns>` 기능을 설명 하기 위한 태그는 `DoesRecordExist` 함수에서 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="90def-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](../../../visual-basic/language-reference/xmldoc/codesnippet/VisualBasic/returns_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="90def-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="90def-112">See Also</span></span>  
 [<span data-ttu-id="90def-113">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="90def-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)
