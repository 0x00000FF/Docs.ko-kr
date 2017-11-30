---
title: "방법: 날짜 및 시간 값의 밀리초 표시"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DateTime.ToString method
- displaying date and time data
- time [.NET Framework], milliseconds
- dates [.NET Framework], milliseconds
- milliseconds [.NET Framework]
ms.assetid: ae1a0610-90b9-4877-8eb6-4e30bc5e00cf
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 260d202eb0a218a6657bc719e36da6f39138e54e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-display-milliseconds-in-date-and-time-values"></a>방법: 날짜 및 시간 값의 밀리초 표시
기본 날짜 및 시간 서식 지정 메서드에 같은 <xref:System.DateTime.ToString?displayProperty=nameWithType>, 시, 분 및 초의 시간 값을 포함 하지만 밀리초 구성 요소는 제외 합니다. 이 항목에서는 형식이 지정된 날짜 및 시간 문자열에 날짜 및 시간의 밀리초 구성 요소를 포함하는 방법을 보여 줍니다.  
  
### <a name="to-display-the-millisecond-component-of-a-datetime-value"></a>DateTime 값의 밀리초 구성 요소를 표시하려면  
  
1.  날짜의 문자열 표현에 대한 작업을 하는 경우에는 정적 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 메서드를 사용하여 해당 표현을 <xref:System.DateTime.Parse%28System.String%29?displayProperty=nameWithType> 또는 <xref:System.DateTimeOffset.Parse%28System.String%29?displayProperty=nameWithType> 값으로 변환합니다.  
  
2.  문자열 표현의 한 번의 밀리초 구성 요소를 추출 하려면 날짜 및 시간 값의 호출 <xref:System.DateTime.ToString%28System.String%29?displayProperty=nameWithType> 또는 <xref:System.DateTimeOffset.ToString%2A> 메서드와 패스는 `fff` 또는 `FFF` 단독 기타 사용자 지정 형식으로 또는 사용자 지정 형식 패턴이 으로 지정자는 `format` 매개 변수입니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 표시의 밀리초 구성 요소는 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 값을 콘솔만 하 고 긴 날짜 및 시간 문자열에 포함 합니다.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#1)]
 [!code-vb[Formatting.HowTo.Millisecond#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#1)]  
  
 `fff` 형식 패턴에서는 밀리초 값의 뒤에 0이 포함됩니다. `FFF` 형식 패턴에서는 표시되지 않습니다. 다음 예제에서 차이점을 보여 줍니다.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#2)]
 [!code-vb[Formatting.HowTo.Millisecond#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#2)]  
  
 날짜 및 시간의 밀리초 구성 요소를 포함하는 전체 사용자 지정 형식 지정자를 정의할 때 발생하는 문제는 응용 프로그램의 현재 문화권에서 사용되는 시간 요소의 정렬과 일치하지 않는 하드 코드된 형식이 정의될 수 있다는 것입니다. 날짜 중 하나를 검색 한 시간을 현재 문화권에 의해 정의 된 패턴을 표시 하는 것이 더 좋은 <xref:System.Globalization.DateTimeFormatInfo> 개체 및 시간 (밀리초)을 포함 하도록 수정 합니다. 이 방법도 예제에서 보여 줍니다. 현재 문화권의 전체 날짜 및 시간 패턴을 검색 된 <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType> 속성을 삽입 한 후 사용자 지정 패턴 `.ffff` 해당 초 패턴 뒤 합니다. 예제에서는 정규식을 사용하여 이 작업을 단일 메서드 호출에서 수행합니다.  
  
 사용자 지정 형식 지정자를 사용하여 밀리초가 아닌 초의 소수 자릿수를 표시할 수도 있습니다. 예를 들어 `f` 또는 `F` 사용자 지정 형식 지정자는 1/10초, `ff` 또는 `FF` 사용자 지정 형식 지정자는 1/100초, `ffff` 또는 `FFFF` 사용자 지정 형식 지정자는 1/10000초를 표시합니다. 반환된 문자열에서 밀리초의 소수 자릿수가 반올림되지 않고 잘립니다. 이 형식 지정자는 다음 예제에서 사용됩니다.  
  
 [!code-csharp[Formatting.HowTo.Millisecond#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.HowTo.Millisecond/cs/Millisecond.cs#3)]
 [!code-vb[Formatting.HowTo.Millisecond#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.HowTo.Millisecond/vb/Millisecond.vb#3)]  
  
> [!NOTE]
>  1/10000초, 1/100000초 등 1초의 매우 작은 소수 단위를 표시할 수 있습니다. 그러나 이러한 값은 의미가 없을 수 있습니다. 날짜 및 시간 값의 자릿수는 시스템 시계의 정밀도에 따라 달라집니다. Windows NT 3.5 이상에서 및 [!INCLUDE[windowsver](../../../includes/windowsver-md.md)] 운영 체제를 시계의 정밀도 약 10-15 밀리초입니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 Csc.exe 또는 vb.exe를 사용 하 여 명령줄에서 코드를 컴파일하십시오. 코드를 컴파일하려면 [!INCLUDE[vsprvs](../../../includes/vsprvs-md.md)], 콘솔 응용 프로그램 프로젝트 템플릿을에 배치 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Globalization.DateTimeFormatInfo>  
 [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
