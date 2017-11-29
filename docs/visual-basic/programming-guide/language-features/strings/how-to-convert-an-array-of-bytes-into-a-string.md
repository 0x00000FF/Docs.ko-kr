---
title: "방법: Visual Basic에서 바이트 배열을 문자열로 변환"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- string conversion [Visual Basic], arrays
- byte arrays [Visual Basic], converting to strings
- examples [Visual Basic], strings
- arrays [Visual Basic], converting to strings
ms.assetid: d0dc8317-9ab3-4324-99f7-3f5788c0e72a
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4133109ef334c7e87884deb7db963db3291da1d5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-convert-an-array-of-bytes-into-a-string-in-visual-basic"></a>방법: Visual Basic에서 바이트 배열을 문자열로 변환
이 항목에는 바이트 배열에서 바이트를 문자열로 변환 하는 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 사용 하 여이 예제는 <xref:System.Text.Encoding.GetString%2A> 의 메서드는 <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType> 인코딩 바이트 배열에서 모든 바이트를 문자열로 변환 하는 클래스입니다.  
  
 [!code-vb[VbVbalrStrings#72](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-to-convert-an-array-of-bytes-into-a-string_1.vb)]  
  
 바이트 배열을 문자열로 변환 하는 여러 인코딩 옵션 중에서 선택할 수 있습니다.  
  
-   <xref:System.Text.Encoding.ASCII%2A?displayProperty=nameWithType>: 집합은 ASCII (7 비트) 문자에 대 한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.BigEndianUnicode%2A?displayProperty=nameWithType>: Big endian 바이트 순서를 사용 하 여 utf-16 형식에 대 한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.Default%2A?displayProperty=nameWithType>: 시스템의 현재 ANSI 코드 페이지에 대 한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.Unicode%2A?displayProperty=nameWithType>: Little endian 바이트 순서를 사용 하 여 utf-16 형식에 대 한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.UTF32%2A?displayProperty=nameWithType>: Little endian 바이트 순서를 사용 하는 utf-32 형식에 대 한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.UTF7%2A?displayProperty=nameWithType>: Utf-7 형식에 대 한 인코딩을 가져옵니다.  
  
-   <xref:System.Text.Encoding.UTF8%2A?displayProperty=nameWithType>: Utf-8 형식에 대 한 인코딩을 가져옵니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Text.Encoding?displayProperty=nameWithType>  
 <xref:System.Text.Encoding.GetString%2A>  
 [방법: Visual Basic에서 바이트 배열을 문자열 변환](../../../../visual-basic/programming-guide/language-features/strings/how-to-convert-strings-into-an-array-of-bytes.md)
