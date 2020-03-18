---
ms.openlocfilehash: f9d7b8d22818245b96cafffe3732bdfe82ff69d8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "67858461"
---
### <a name="a-concurrentdictionary-serialized-in-net-framework-45-with-netdatacontractserializer-cannot-be-deserialized-by-net-framework-451-or-452"></a>.NET Framework 4.5에서 NetDataContractSerializer로 직렬화된 ConcurrentDictionary는 .NET Framework 4.5.1 또는 4.5.2에서 역직렬화될 수 없습니다.

|   |   |
|---|---|
|세부 정보|이 형식의 내부 변경 내용으로 인해 <xref:System.Collections.Concurrent.ConcurrentDictionary%602>을 사용하여 .NET Framework 4.5로 직렬화된 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> 개체를 .NET Framework 4.5.1 또는 .NET Framework 4.5.2에서 역직렬화할 수 없습니다. 반대 방향의 경우(.NET Framework 4.5.x로 직렬화하고 .NET Framework 4.5로 역직렬화하는 경우)는 작동합니다. 마찬가지로 .NET Framework 4.6으로 모든 4.x 버전 간 직렬화가 실행됩니다. 단일 버전의 .NET Framework로 직렬화 및 역직렬화하는 것은 영향을 받지 않습니다.|
|제안 해결 방법|.NET Framework 4.5와 .NET Framework 4.5.1/4.5.2 간에 <xref:System.Collections.Concurrent.ConcurrentDictionary%602?displayProperty=name>을 직렬화 및 역직렬화해야 하는 경우 <xref:System.Runtime.Serialization.DataContractSerializer?displayProperty=name> 대신 <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter?displayProperty=name> 또는 <xref:System.Runtime.Serialization.NetDataContractSerializer?displayProperty=name> 직렬기와 같은 대체 직렬기가 사용되어야 합니다. 또는 .NET Framework 4.6에서 이 문제가 해결되므로 해당 버전의 .NET Framework로 업그레이드하여 이 문제를 해결할 수 있습니다.|
|범위|사소함|
|Version|4.5.1|
|형식|런타임|
