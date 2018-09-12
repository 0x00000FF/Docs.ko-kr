---
title: 표준 시간대 개요
ms.date: 04/10/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- time zones [.NET Framework], about time zones
- transition time [.NET Framework]
- TimeZoneInfo class, about TimeZoneInfo class
- time zones [.NET Framework], creating
- invalid time [.NET Framework]
- fixed rule [.NET Framework]
- ambiguous time [.NET Framework]
- floating rule [.NET Framework]
- daylight saving time [.NET Framework]
- adjustment rule [.NET Framework]
- time zones [.NET Framework], terminology
ms.assetid: c4b7ed01-5e38-4959-a3b6-ef9765d6ccf1
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0eb24c7c4f2c60a9c16d903ab1e845b058e280f7
ms.sourcegitcommit: ba5c189bf44d44204a3e8838e59ec378a62d82f3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2018
ms.locfileid: "44710037"
---
# <a name="time-zone-overview"></a>표준 시간대 개요

<xref:System.TimeZoneInfo> 클래스 표준 시간대 인식 응용 프로그램을 만드는 과정을 간소화 합니다. <xref:System.TimeZone> 클래스는 현지 표준 시간대와 utc (협정 세계시) 작업을 지원 합니다. <xref:System.TimeZoneInfo> 클래스 정보에 대 한 표준 시간대 뿐만 레지스트리에서 미리 정의 된 이러한 영역의 모두 지원 합니다. 사용할 수도 있습니다 <xref:System.TimeZoneInfo> 시스템에 해당 정보가 없는 사용자 지정 표준 시간대를 정의 합니다.

## <a name="time-zone-essentials"></a>표준 시간대 essentials

표준 시간대는 동일한 시간이 사용되는 지리적 영역입니다. 항상 그렇지는 않지만 일반적으로 인접한 표준 시간대는 1시간 간격입니다. 전세계 표준 시간대의 시간은 UTC(협정 세계시) 오프셋으로 표현할 수 있습니다.

전세계 표준 시간대는 대부분 일광 절약 시간을 지원합니다. 일광 절약 시간제는 봄이나 초기 여름에 시간을 한 시간 앞으로 이동하고 늦은 여름이나 가을에 일반(또는 표준) 시간으로 돌아와서 일광 시간을 극대화하려고 합니다. 표준 시간 간의 이러한 변경 내용은 조정 규칙으로 알려져 있습니다.

특정 표준 시간대의 일광 절약 시간 간의 전환은 고정 또는 부동 조정 규칙에서 정의될 수 있습니다. 고정 조정 규칙은 일광 절약 시간 간의 전환이 매년 발생하는 특정 날짜를 설정합니다. 예를 들어, 매년 10월 25일에 발생하는 일광 절약 시간에서 표준 시간으로의 전환은 고정 조정 규칙을 따릅니다. 보다 일반적인 규칙은 유동 조정 규칙으로, 일광 절약 시간 간의 전환에 대한 특정 월, 주, 날짜를 설정합니다. 예를 들어 3월의 세 번째 일요일에 발생하는 표준 시간에서 일광 절약 시간으로의 전환은 부동 조정 규칙을 따릅니다.

조정 규칙을 지원하는 표준 시간대의 경우 일광 절약 시간제 간의 전환으로 인해 잘못된 시간과 모호한 시간이라는 두 가지 예외적인 시간이 생성됩니다. 잘못된 시간은 표준 시간에서 일광 절약 시간으로의 전환에서 만든 존재하지 않는 시간입니다. 예를 들어 특정 일의 오전 2시에 이 전환이 발생하고 시간이 오전 3시로 변경되면 오전 2시와 오전 2시 59분 99초 사이의 시간 간격은 잘못되었습니다. 모호한 시간은 단일 표준 시간대에서 두 개의 서로 다른 시간에 매핑될 수 있는 시간입니다. 일광 절약 시간에서 표준 시간으로의 전환에서 생성됩니다. 예를 들어 특정 일의 오전 2시에 이 전환이 발생하고 시간이 오전 1시로 변경되면 오전 1시와 오전 1시 59분 99초 사이의 각 시간 간격은 표준 시간이나 일광 절약 시간으로 해석될 수 있습니다.

## <a name="time-zone-terminology"></a>표준 시간대 용어

다음 테이블에서는 표준 시간대를 사용하고 표준 시간대 인식 응용 프로그램을 개발할 때 일반적으로 사용되는 용어를 정의합니다.

| 용어            | 정의 |
| --------------- | ---------- |
| 조정 규칙 | 표준 시간에서 일광 절약 시간으로의 전환 및 일광 절약 시간에서 표준 시간으로의 전환이 발생하는 시기를 정의하는 규칙입니다. 각 조정 규칙에 규칙 진행에서 하는 경우 정의 하는 시작 및 종료 날짜 (예를 들어 조정 규칙은 1986 년 1 월 1을, 2006 년 12 월 31 일에 진행에서), 델타 (기간 중 응용 프로그램의 결과로 표준 시간 변경 e 조정 규칙) 및 조정 기간 중에 발생 하는 전환 시간과 특정 날짜에 대 한 정보입니다. 전환은 고정 규칙 또는 유동 규칙을 따르면 됩니다. |
| 모호한 시간  | 단일 표준 시간대에서 두 개의 서로 다른 시간에 매핑될 수 있는 시간입니다. 표준 시간대의 일광 절약 시간에서 표준 시간으로 전환하는 것과 같이 클록 시간을 뒤로 조정하는 경우 발생합니다. 예를 들어 특정 일의 오전 2시에 이 전환이 발생하고 시간이 오전 1시로 변경되면 오전 1시와 오전 1시 59분 99초 사이의 각 시간 간격은 표준 시간이나 일광 절약 시간으로 해석될 수 있습니다. |
| 고정 규칙      | 조정 규칙은 일광 절약 시간 간의 전환에 대한 특정 날짜를 설정합니다. 예를 들어, 매년 10월 25일에 발생하는 일광 절약 시간에서 표준 시간으로의 전환은 고정 조정 규칙을 따릅니다. |
| 유동 규칙   | 조정 규칙은 일광 절약 시간 간의 전환에 대한 특정 월, 주, 날짜를 설정합니다. 예를 들어 3월의 세 번째 일요일에 발생하는 표준 시간에서 일광 절약 시간으로의 전환은 부동 조정 규칙을 따릅니다. |
| 잘못된 형식    | 표준 시간에서 일광 절약 시간으로의 전환 아티팩트인 존재하지 않는 시간입니다. 표준 시간대의 표준 시간에서 일광 절약 시간으로 전환하는 것과 같이 클록 시간을 앞으로 조정하는 경우 발생합니다. 예를 들어 특정 일의 오전 2시에 이 전환이 발생하고 시간이 오전 3시로 변경되면 오전 2시와 오전 2시 59분 99초 사이의 시간 간격은 잘못되었습니다. |
| 전환 시간 | 특정 표준 시간대에서 일광 절약 시간제를 표준 시간으로 변경하거나 그 반대의 경우와 같은 특정 시간 변경에 대한 정보입니다. |

## <a name="time-zones-and-the-timezoneinfo-class"></a>표준 시간대 및 TimeZoneInfo 클래스

.NET에서는 <xref:System.TimeZoneInfo> 개체는 표준 시간대를 나타냅니다. 합니다 <xref:System.TimeZoneInfo> 클래스에 포함을 <xref:System.TimeZoneInfo.GetAdjustmentRules%2A> 배열을 반환 하는 메서드 <xref:System.TimeZoneInfo.AdjustmentRule> 개체입니다. 이 배열의 각 요소는 특정 기간에 대 한 일광 절약 시간 간의 전환에 대 한 정보를 제공 합니다. (일광 절약 시간제를 지원 하지 않는 시간 영역에 대 한 메서드는 빈 배열을 반환 합니다.) 각 <xref:System.TimeZoneInfo.AdjustmentRule> 개체에는 <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionStart%2A> 및 <xref:System.TimeZoneInfo.AdjustmentRule.DaylightTransitionEnd%2A> 일광 절약 시간 간의 전환의 시간과 특정 날짜를 정의 하는 속성입니다. <xref:System.TimeZoneInfo.TransitionTime.IsFixedDateRule%2A> 속성 해당 전환은 고정 또는 부동 여부를 나타냅니다.

.NET은 Windows 운영 체제에서 제공 하 고 레지스트리에 저장 된 표준 시간대 정보에 의존 합니다. 수가 지구의 표준 시간대로 인해 일부 기존 시간대 레지스트리에 표시 됩니다. 또한 레지스트리는 동적 구조 이기 때문에 미리 정의 된 표준 시간대에 추가 하거나 제거할 수에서. 마지막으로 레지스트리에 반드시 하므로 기록 표준 시간대 데이터가 없습니다. 예를 들어, Windows XP에서 레지스트리는 단일 집합이 시간대 조정에 대 한 데이터를 포함합니다. Windows Vista 동적 표준 시간대 데이터, 즉 단일 표준 시간대 수 년의 특정 간격에 적용 되는 여러 조정 규칙을 지원 합니다. 그러나 Windows Vista 레지스트리 및 지원 일광 절약 시간에 정의 된 대부분의 표준 시간대 하나 이상의 미리 정의 된 조정 규칙을 갖습니다.

종속성을 <xref:System.TimeZoneInfo> 레지스트리 클래스 의미는 표준 시간대 인식 응용 프로그램의 특정 표준 시간대가 레지스트리에 정의 되어 있는지 확신할 수 없습니다. 결과적으로 현지 표준 시간대 또는 UTC를 나타내는 표준 시간대 이외의 특정 표준 시간대를 인스턴스화하려면 예외 처리를 사용해야 합니다. 일부 메서드는 필요한 경우 계속 하려면 응용 프로그램을 제공 해야 <xref:System.TimeZoneInfo> 레지스트리에서 개체를 인스턴스화할 수 없습니다.

필요한 표준 시간대가 없는 경우에 <xref:System.TimeZoneInfo> 클래스에 포함 되어는 <xref:System.TimeZoneInfo.CreateCustomTimeZone%2A> 메서드를 레지스트리에서 찾을 수 없는 사용자 지정 표준 시간대를 만드는 데 사용할 수 있습니다. 사용자 지정 표준 시간대를 만드는 방법에 대 한 세부 정보를 참조 하세요. [방법: 조정 규칙 없이 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-without-adjustment-rules.md) 및 [방법: 조정 규칙을 사용 하 여 표준 시간대 만들기](../../../docs/standard/datetime/create-time-zones-with-adjustment-rules.md)합니다. 또한 사용할 수 있습니다는 <xref:System.TimeZoneInfo.ToSerializedString%2A> 메서드를 새로 만든된 표준 시간대를 문자열로 변환 하 고 (예: 데이터베이스, 텍스트 파일, 레지스트리, 또는 응용 프로그램 리소스) 데이터 저장소에 저장 합니다. 사용할 수 있습니다 합니다 <xref:System.TimeZoneInfo.FromSerializedString%2A> 이 문자열을 변환 하는 방법으로는 <xref:System.TimeZoneInfo> 개체입니다. 세부 정보를 참조 하세요. [방법: 포함된 리소스에 표준 시간대 저장](../../../docs/standard/datetime/save-time-zones-to-an-embedded-resource.md) 하 고 [방법: 포함된 리소스에서 표준 시간대 복원](../../../docs/standard/datetime/restore-time-zones-from-an-embedded-resource.md)합니다.

각 표준 시간대가 기존 조정 규칙을 반영하는 UTC의 오프셋뿐만 아니라 UTC의 기본 오프셋을 특징으로 하기 때문에 표준 시간대의 시간은 다른 표준 시간대의 시간으로 쉽게 변환될 수 있습니다. 이 목적을 위해는 <xref:System.TimeZoneInfo> 개체에 포함 하 여 여러 가지 변환 메서드를 포함 합니다.

* <xref:System.TimeZoneInfo.ConvertTimeFromUtc%2A>에 UTC를 지정한 표준 시간대의 시간으로 변환 합니다.

* <xref:System.TimeZoneInfo.ConvertTimeToUtc%2A>에 지정한 표준 시간대의 시간을 UTC로 변환 합니다.

* <xref:System.TimeZoneInfo.ConvertTime%2A>에 지정 된 시간대의 시간을 지정된 하는 다른 표준 시간대의 시간으로 변환 하 합니다.

* <xref:System.TimeZoneInfo.ConvertTimeBySystemTimeZoneId%2A>에서 표준 시간대 식별자를 사용 하는 (대신 <xref:System.TimeZoneInfo> 개체)을 지정된 하는 다른 표준 시간대의 시간 지정 된 시간대의 시간을 변환 하는 매개 변수로 합니다.

표준 시간대 간의 시간 변환에 대한 세부 정보는 [표준 시간대 간의 시간 변환](../../../docs/standard/datetime/converting-between-time-zones.md)을 참조하세요.

## <a name="see-also"></a>참고자료

* [날짜, 시간 및 표준 시간대](../../../docs/standard/datetime/index.md)
