---
title: My.Request 개체 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.MyWebExtension.Request
- My.Request
helpviewer_keywords:
- My.Request object
ms.assetid: 93d5f0e2-6b60-4a2c-8652-d90216f6ad10
ms.openlocfilehash: 7a4e292968cf1d30977b8cacdc8f77152e5cc770
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200964"
---
# <a name="myrequest-object"></a>My.Request 개체
요청된 페이지에 대한 <xref:System.Web.HttpRequest> 개체를 가져옵니다.  
  
## <a name="remarks"></a>설명  
 `My.Request` 개체에는 현재 HTTP 요청에 대한 정보가 포함됩니다.  
  
 `My.Request` 개체는 ASP.NET 애플리케이션에만 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서 헤더 컬렉션을 가져옵니다 합니다 `My.Request` 사용 하 여 개체를 `My.Response` ASP.NET 페이지에 쓸 개체입니다.  
  
 [!code-vb[VbVbalrMyWeb#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyWeb/VB/Default.aspx#1)]  
  
## <a name="see-also"></a>참고자료
- <xref:System.Web.HttpRequest>
- [My.Response 개체](../../../visual-basic/language-reference/objects/my-response-object.md)
