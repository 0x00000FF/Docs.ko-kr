---
title: '방법: 포함된 리소스에서 표준 시간대 복원'
ms.date: 04/10/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- time zones [.NET Framework], deserializing
- time zones [.NET Framework], restoring
ms.assetid: 6b7b4de9-da07-47e3-8f4c-823f81798ee7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99d38b336b5e655dd1c96682eec90c5fbe8469d6
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2018
ms.locfileid: "44262726"
---
# <a name="how-to-restore-time-zones-from-an-embedded-resource"></a>방법: 포함된 리소스에서 표준 시간대 복원

이 항목에서는 리소스 파일에 저장 된 표준 시간대를 복원 하는 방법을 설명 합니다. 정보 및 표준 시간대 저장 하는 방법에 대 한 지침을 참조 하세요 [방법: 포함된 리소스에 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)합니다.

### <a name="to-deserialize-a-timezoneinfo-object-from-an-embedded-resource"></a>포함된 리소스에서 TimeZoneInfo 개체를 deserialize 하는 데

1. 검색할 표준 시간대를 없는 경우 사용자 지정 표준 시간대를 사용 하 여이 인스턴스화하 려는 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 메서드.

2. 인스턴스화하는 <xref:System.Resources.ResourceManager> 포함된 리소스 파일 및 리소스 파일을 포함 하는 어셈블리에 대 한 참조는 정규화 된 이름을 전달 하 여 개체입니다.

   포함된 리소스 파일의 정규화 된 이름을 확인할 수 없으면, 사용 된 [Ildasm.exe (IL 디스어셈블러)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) 어셈블리의 매니페스트를 검사할 합니다. `.mresource` 항목 리소스를 식별 합니다. 예제에서는 리소스의 정규화 된 이름은 `SerializeTimeZoneData.SerializedTimeZones`합니다.

   리소스 파일, 표준 시간대 인스턴스화 코드를 포함 하는 동일한 어셈블리에 포함 되어 있는 경우 호출 하 여이에 대 한 참조를 검색할 수 있습니다 합니다 `static` (`Shared` Visual basic에서) <xref:System.Reflection.Assembly.GetExecutingAssembly%2A> 메서드.

3. 경우에 대 한 호출을 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 메서드가 실패 하면 사용자 지정 표준 시간대를 인스턴스화할 경우 호출 하 여 serialize 된 표준 시간대를 포함 하는 문자열을 검색 하거나는 <xref:System.Resources.ResourceManager.GetString%2A?displayProperty=nameWithType> 메서드.

4. 호출 하 여 표준 시간대 데이터를 deserialize 합니다 <xref:System.TimeZoneInfo.FromSerializedString%2A> 메서드.

## <a name="example"></a>예제

다음 예제에서는 deserialize를 <xref:System.TimeZoneInfo> 포함 된.NET XML 리소스 파일에 저장 된 개체입니다.

[!code-csharp[TimeZone2.Serialization#3](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#3)]
[!code-vb[TimeZone2.Serialization#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#3)]

이 코드 되도록 예외 처리를 보여 줍니다.는 <xref:System.TimeZoneInfo> 응용 프로그램에 필요한 개체가 있습니다. 인스턴스화하는 먼저 시도 <xref:System.TimeZoneInfo> 를 사용 하 여 레지스트리를 검색 하 여 개체를 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 메서드. 표준 시간대를 인스턴스화할 수 없는 경우 코드에서 포함된 리소스 파일을 검색 합니다.

때문에 사용자 지정 표준 시간대에 대 한 데이터 (표준 시간대를 사용 하 여 인스턴스화된를 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드) 저장 되지 않습니다 레지스트리에 코드를 호출 하지 않습니다는 <xref:System.TimeZoneInfo.FindSystemTimeZoneById%2A> 파머, 남극 대륙에 대 한 표준 시간대를 인스턴스화하. 대신 곧바로 포함된 리소스 파일을 호출 하기 전에 해당 표준 시간대의 데이터를 포함 하는 문자열을 검색 하 여 <xref:System.TimeZoneInfo.FromSerializedString%2A> 메서드.

## <a name="compiling-the-code"></a>코드 컴파일

이 예제에는 다음 사항이 필요합니다.

* System.Windows.Forms.dll System.Core.dll에 대 한 참조는 프로젝트에 추가할 수 있습니다.

* 다음 네임 스페이스를 가져와야 합니다.

  [!code-csharp[TimeZone2.Serialization#2](../../../samples/snippets/csharp/VS_Snippets_CLR/TimeZone2.Serialization/cs/SerializeTimeZoneData.cs#2)]
  [!code-vb[TimeZone2.Serialization#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/TimeZone2.Serialization/vb/SerializeTimeZoneData.vb#2)]

## <a name="see-also"></a>참고자료

* [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
* [표준 시간대 개요](../../../docs/standard/datetime/time-zone-overview.md)
* [방법: 포함 리소스에 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md)
