---
title: 정수 계열 형식 표(C# 참조)
description: 기본 제공 C# 정수 계열 형식 개요
ms.date: 08/20/2018
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
ms.assetid: 62e86126-46ff-40b0-9028-e61d7558268c
ms.openlocfilehash: 4ac16d185a52cdb03fcb22f57ebf7506f2fb2745
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2018
ms.locfileid: "44078850"
---
# <a name="integral-types-table-c-reference"></a><span data-ttu-id="1fab1-103">정수 계열 형식 표(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="1fab1-103">Integral types table (C# Reference)</span></span>

<span data-ttu-id="1fab1-104">다음 표에서는 단순 형식의 하위 집합을 구성하는 정수 형식의 크기와 범위를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1fab1-104">The following table shows the sizes and ranges of the integral types, which constitute a subset of simple types.</span></span>  
  
|<span data-ttu-id="1fab1-105">형식</span><span class="sxs-lookup"><span data-stu-id="1fab1-105">Type</span></span>|<span data-ttu-id="1fab1-106">범위</span><span class="sxs-lookup"><span data-stu-id="1fab1-106">Range</span></span>|<span data-ttu-id="1fab1-107">크기</span><span class="sxs-lookup"><span data-stu-id="1fab1-107">Size</span></span>|  
|----------|-----------|----------|  
|[<span data-ttu-id="1fab1-108">sbyte</span><span class="sxs-lookup"><span data-stu-id="1fab1-108">sbyte</span></span>](sbyte.md)|<span data-ttu-id="1fab1-109">-128 ~ 127</span><span class="sxs-lookup"><span data-stu-id="1fab1-109">-128 to 127</span></span>|<span data-ttu-id="1fab1-110">부호 있는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="1fab1-110">Signed 8-bit integer</span></span>|  
|[<span data-ttu-id="1fab1-111">byte</span><span class="sxs-lookup"><span data-stu-id="1fab1-111">byte</span></span>](byte.md)|<span data-ttu-id="1fab1-112">0 ~ 255</span><span class="sxs-lookup"><span data-stu-id="1fab1-112">0 to 255</span></span>|<span data-ttu-id="1fab1-113">부호 없는 8비트 정수</span><span class="sxs-lookup"><span data-stu-id="1fab1-113">Unsigned 8-bit integer</span></span>|  
|[<span data-ttu-id="1fab1-114">char</span><span class="sxs-lookup"><span data-stu-id="1fab1-114">char</span></span>](char.md)|<span data-ttu-id="1fab1-115">U+0000 ~ U+ffff</span><span class="sxs-lookup"><span data-stu-id="1fab1-115">U+0000 to U+ffff</span></span>|<span data-ttu-id="1fab1-116">유니코드 16비트 문자</span><span class="sxs-lookup"><span data-stu-id="1fab1-116">Unicode 16-bit character</span></span>|  
|[<span data-ttu-id="1fab1-117">short</span><span class="sxs-lookup"><span data-stu-id="1fab1-117">short</span></span>](short.md)|<span data-ttu-id="1fab1-118">–32,768 ~ 32,767</span><span class="sxs-lookup"><span data-stu-id="1fab1-118">-32,768 to 32,767</span></span>|<span data-ttu-id="1fab1-119">부호 있는 16비트 정수</span><span class="sxs-lookup"><span data-stu-id="1fab1-119">Signed 16-bit integer</span></span>|  
|[<span data-ttu-id="1fab1-120">ushort</span><span class="sxs-lookup"><span data-stu-id="1fab1-120">ushort</span></span>](ushort.md)|<span data-ttu-id="1fab1-121">0 ~ 65,535</span><span class="sxs-lookup"><span data-stu-id="1fab1-121">0 to 65,535</span></span>|<span data-ttu-id="1fab1-122">부호 없는 16비트 정수</span><span class="sxs-lookup"><span data-stu-id="1fab1-122">Unsigned 16-bit integer</span></span>|  
|[<span data-ttu-id="1fab1-123">int</span><span class="sxs-lookup"><span data-stu-id="1fab1-123">int</span></span>](int.md)|<span data-ttu-id="1fab1-124">–2,147,483,648 ~ 2,147,483,647</span><span class="sxs-lookup"><span data-stu-id="1fab1-124">-2,147,483,648 to 2,147,483,647</span></span>|<span data-ttu-id="1fab1-125">부호 있는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="1fab1-125">Signed 32-bit integer</span></span>|  
|[<span data-ttu-id="1fab1-126">uint</span><span class="sxs-lookup"><span data-stu-id="1fab1-126">uint</span></span>](uint.md)|<span data-ttu-id="1fab1-127">0 ~ 4,294,967,295</span><span class="sxs-lookup"><span data-stu-id="1fab1-127">0 to 4,294,967,295</span></span>|<span data-ttu-id="1fab1-128">부호 없는 32비트 정수</span><span class="sxs-lookup"><span data-stu-id="1fab1-128">Unsigned 32-bit integer</span></span>|  
|[<span data-ttu-id="1fab1-129">long</span><span class="sxs-lookup"><span data-stu-id="1fab1-129">long</span></span>](long.md)|<span data-ttu-id="1fab1-130">–9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807</span><span class="sxs-lookup"><span data-stu-id="1fab1-130">-9,223,372,036,854,775,808 to 9,223,372,036,854,775,807</span></span>|<span data-ttu-id="1fab1-131">부호 있는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="1fab1-131">Signed 64-bit integer</span></span>|  
|[<span data-ttu-id="1fab1-132">ulong</span><span class="sxs-lookup"><span data-stu-id="1fab1-132">ulong</span></span>](ulong.md)|<span data-ttu-id="1fab1-133">0 ~ 18,446,744,073,709,551,615</span><span class="sxs-lookup"><span data-stu-id="1fab1-133">0 to 18,446,744,073,709,551,615</span></span>|<span data-ttu-id="1fab1-134">부호 없는 64비트 정수</span><span class="sxs-lookup"><span data-stu-id="1fab1-134">Unsigned 64-bit integer</span></span>|  

## <a name="remarks"></a><span data-ttu-id="1fab1-135">설명</span><span class="sxs-lookup"><span data-stu-id="1fab1-135">Remarks</span></span>
  
<span data-ttu-id="1fab1-136">정수 리터럴로 표시되는 값이 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>를 초과하면 컴파일 오류 [CS1021](../../misc/cs1021.md)이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="1fab1-136">If the value represented by an integer literal exceeds <xref:System.UInt64.MaxValue?displayProperty=nameWithType>, a compiler error [CS1021](../../misc/cs1021.md) occurs.</span></span>

<span data-ttu-id="1fab1-137"><xref:System.Numerics.BigInteger?displayProperty=nameWithType> 클래스를 사용하여 부호 있는 임의의 큰 정수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1fab1-137">Use the <xref:System.Numerics.BigInteger?displayProperty=nameWithType> class to represent an arbitrarily large signed integer.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1fab1-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1fab1-138">See also</span></span>

- [<span data-ttu-id="1fab1-139">C# 참조</span><span class="sxs-lookup"><span data-stu-id="1fab1-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1fab1-140">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1fab1-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1fab1-141">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="1fab1-141">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1fab1-142">형식 참조 테이블</span><span class="sxs-lookup"><span data-stu-id="1fab1-142">Reference tables for types</span></span>](reference-tables-for-types.md)
- [<span data-ttu-id="1fab1-143">부동 소수점 형식 표</span><span class="sxs-lookup"><span data-stu-id="1fab1-143">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="1fab1-144">기본값 표</span><span class="sxs-lookup"><span data-stu-id="1fab1-144">Default values table</span></span>](default-values-table.md)
- [<span data-ttu-id="1fab1-145">숫자 결과 형식 지정 표</span><span class="sxs-lookup"><span data-stu-id="1fab1-145">Formatting numeric results table</span></span>](formatting-numeric-results-table.md)
- [<span data-ttu-id="1fab1-146">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="1fab1-146">Built-in types table</span></span>](built-in-types-table.md)
