---
title: "방법: 바이트 배열을 정수로 변환(C# 프로그래밍 가이드) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "바이트 배열[C#], int로 변환"
  - "변환[C#], 바이트 배열을 int로"
ms.assetid: d6ac20e2-448e-4aea-99b9-faf04c6f1e79
caps.latest.revision: 18
caps.handback.revision: 18
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 방법: 바이트 배열을 정수로 변환(C# 프로그래밍 가이드)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

이 예제에서는 <xref:System.BitConverter> 클래스를 사용하여 바이트 배열을 [int](../../../csharp/language-reference/keywords/int.md)로 변환하고 다시 바이트 배열로 변환하는 방법을 보여 줍니다.  예를 들어 네트워크에서 바이트를 읽은 후에는 바이트에서 기본 제공 데이터 형식으로 변환해야 할 수 있습니다.  다음 표에는 예제의 [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False) 메서드 외에 바이트 배열의 바이트를 다른 기본 제공 형식으로 변환하는 <xref:System.BitConverter> 클래스의 메서드가 나열되어 있습니다.  
  
|반환된 형식|메서드|  
|------------|---------|  
|`bool`|[ToBoolean\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToBoolean(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`char`|[ToChar\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToChar(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`double`|[ToDouble\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToDouble(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`short`|[ToInt16\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt16(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`int`|[ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`long`|[ToInt64\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt64(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`float`|[ToSingle\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToSingle(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`ushort`|[ToUInt16\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt16(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`uint`|[ToUInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
|`ulong`|[ToUInt64\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToUInt64(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)|  
  
## 예제  
 이 예제에서는 바이트 배열을 초기화하고 컴퓨터 아키텍처가 little\-endian인 경우 배열의 순서를 반대로, 즉 최하위 바이트가 먼저 저장되는 순서로 바꾼 다음 [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False) 메서드를 호출하여 배열의 4바이트를 `int`로 변환합니다.  [ToInt32\(Byte\[\], Int32\)](assetId:///M:System.BitConverter.ToInt32(System.Byte[],System.Int32)?qualifyHint=False&autoUpgrade=False)의 두 번째 인수는 바이트 배열의 시작 인덱스를 지정합니다.  
  
> [!NOTE]
>  출력은 컴퓨터 아키텍처의 endianess에 따라 달라질 수 있습니다.  
  
 [!code-cs[csProgGuideTypes#22](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_1.cs)]  
  
## 예제  
 다음 예제에서는 <xref:System.BitConverter> 클래스의 <xref:System.BitConverter.GetBytes%28System.Int32%29> 메서드를 호출하여 `int`를 바이트 배열로 변환합니다.  
  
> [!NOTE]
>  출력은 컴퓨터 아키텍처의 endianess에 따라 달라질 수 있습니다.  
  
 [!code-cs[csProgGuideTypes#23](../../../csharp/programming-guide/nullable-types/codesnippet/CSharp/how-to-convert-a-byte-array-to-an-int_2.cs)]  
  
## 참고 항목  
 <xref:System.BitConverter>   
 <xref:System.BitConverter.IsLittleEndian>   
 [형식](../../../visual-basic/reference/command-line-compiler/index.md)