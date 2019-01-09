---
title: SqlStreamChars.Read (Char, Int32, Int32) 메서드 (System.Data.SqlTypes)
author: douglaslMS
ms.author: douglasl
ms.date: 12/20/2018
ms.technology:
- dotnet-data
api_name:
- System.Data.SqlTypes.SqlStreamChars.Read
api_location:
- System.Data.dll
api_type:
- Assembly
ms.openlocfilehash: 87bff6dd78743ae08a5a3db8a783b56a0b7c3f24
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/09/2019
ms.locfileid: "54152536"
---
# <a name="sqlstreamcharsreadchar-int32-int32-method"></a><span data-ttu-id="58c82-102">(Char, Int32, Int32) SqlStreamChars.Read 메서드</span><span class="sxs-lookup"><span data-stu-id="58c82-102">SqlStreamChars.Read(Char[], Int32, Int32) Method</span></span>

<span data-ttu-id="58c82-103">파생된 클래스에서 재정의할 경우, 입력 스트림에서 다음 문자 집합을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="58c82-103">When overridden in a derived class, reads the next set of characters from the input stream.</span></span> <span data-ttu-id="58c82-104">이 메서드를 포함 하는 어셈블리에는 SQLAccess.dll friend 관계를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="58c82-104">The assembly that contains this method has a friend relationship with SQLAccess.dll.</span></span> <span data-ttu-id="58c82-105">SQL Server에서 사용할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="58c82-105">It's intended for use by SQL Server.</span></span> <span data-ttu-id="58c82-106">다른 데이터베이스에 대 한 해당 데이터베이스에서 제공 하는 호스팅 메커니즘을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="58c82-106">For other databases, use the hosting mechanism provided by that database.</span></span>

```csharp
public abstract int Read (char[] buffer, int offset, int count);
```

## <a name="parameters"></a><span data-ttu-id="58c82-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="58c82-107">Parameters</span></span>

`buffer`\
<span data-ttu-id="58c82-108">읽을 문자 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="58c82-108">A char array to read.</span></span>

`offset`\
<span data-ttu-id="58c82-109">원점 기준으로 하는 오프셋입니다.</span><span class="sxs-lookup"><span data-stu-id="58c82-109">An offset relative to origin.</span></span>

`count`\
<span data-ttu-id="58c82-110">현재 스트림에서 읽을 문자의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58c82-110">The number of characters to be read from the current stream.</span></span>

## <a name="returns"></a><span data-ttu-id="58c82-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="58c82-111">Returns</span></span>

<xref:System.Int32>\
<span data-ttu-id="58c82-112">버퍼로 읽어온 총 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="58c82-112">The total number of characters read into the buffer.</span></span>

## <a name="remarks"></a><span data-ttu-id="58c82-113">설명</span><span class="sxs-lookup"><span data-stu-id="58c82-113">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="58c82-114">`SqlStreamChars.Read` 메서드가 private 이며 코드에서 직접 사용할 하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58c82-114">The `SqlStreamChars.Read` method is private and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="58c82-115">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 필드의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="58c82-115">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="58c82-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="58c82-116">Requirements</span></span>

<span data-ttu-id="58c82-117">**네임스페이스:** <xref:System.Data.SqlTypes></span><span class="sxs-lookup"><span data-stu-id="58c82-117">**Namespace:** <xref:System.Data.SqlTypes></span></span>

<span data-ttu-id="58c82-118">**어셈블리:** System.Data (System.Data.dll)</span><span class="sxs-lookup"><span data-stu-id="58c82-118">**Assembly:** System.Data (in System.Data.dll)</span></span>

<span data-ttu-id="58c82-119">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58c82-119">**.NET Framework versions:** Available since 2.0.</span></span>