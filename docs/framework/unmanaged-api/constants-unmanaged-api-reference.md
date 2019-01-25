---
title: 상수(관리되지 않는 API 참조)
ms.date: 03/30/2017
helpviewer_keywords:
- constants for unmanaged API [.NET Framework]
- native API reference [.NET Framework], constants
- unmanaged API reference [.NET Framework], constants
ms.assetid: 77526f65-b71c-4483-9d19-3a3751fd8a45
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3c537e4967c284df899a131b44d96dbdb6e1af29
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54587676"
---
# <a name="constants-unmanaged-api-reference"></a><span data-ttu-id="2b3ed-102">상수(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="2b3ed-102">Constants (Unmanaged API Reference)</span></span>
<span data-ttu-id="2b3ed-103">이 항목에서는 언어 유형, 언어 공급 업체 및 CorSym.idl에 정의 되어 있는 문서 형식 상수를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-103">This topic describes the language type, language vendor, and document type constants that are defined in CorSym.idl.</span></span>  
  
## <a name="language-type-constants"></a><span data-ttu-id="2b3ed-104">언어 형식 상수</span><span class="sxs-lookup"><span data-stu-id="2b3ed-104">Language Type Constants</span></span>  
 <span data-ttu-id="2b3ed-105">다음 표에서 언어 프로그래밍 언어를 식별 하는 Guid를 나타내는 형식 상수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-105">The following table shows language type constants, which represent GUIDs that identify programming languages.</span></span>  
  
|<span data-ttu-id="2b3ed-106">기호</span><span class="sxs-lookup"><span data-stu-id="2b3ed-106">Symbol</span></span>|<span data-ttu-id="2b3ed-107">설명</span><span class="sxs-lookup"><span data-stu-id="2b3ed-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2b3ed-108">CorSym_LanguageType_C</span><span class="sxs-lookup"><span data-stu-id="2b3ed-108">CorSym_LanguageType_C</span></span>|<span data-ttu-id="2b3ed-109">C 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-109">Indicates the C language.</span></span>|  
|<span data-ttu-id="2b3ed-110">CorSym_LanguageType_CPlusPlus</span><span class="sxs-lookup"><span data-stu-id="2b3ed-110">CorSym_LanguageType_CPlusPlus</span></span>|<span data-ttu-id="2b3ed-111">C + + 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-111">Indicates the C++ language.</span></span>|  
|<span data-ttu-id="2b3ed-112">CorSym_LanguageType_CSharp</span><span class="sxs-lookup"><span data-stu-id="2b3ed-112">CorSym_LanguageType_CSharp</span></span>|<span data-ttu-id="2b3ed-113">나타냅니다는 C# 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-113">Indicates the C# language.</span></span>|  
|<span data-ttu-id="2b3ed-114">CorSym_LanguageType_Basic</span><span class="sxs-lookup"><span data-stu-id="2b3ed-114">CorSym_LanguageType_Basic</span></span>|<span data-ttu-id="2b3ed-115">기본 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-115">Indicates the Basic language.</span></span>|  
|<span data-ttu-id="2b3ed-116">CorSym_LanguageType_Java</span><span class="sxs-lookup"><span data-stu-id="2b3ed-116">CorSym_LanguageType_Java</span></span>|<span data-ttu-id="2b3ed-117">Java 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-117">Indicates the Java language.</span></span>|  
|<span data-ttu-id="2b3ed-118">CorSym_LanguageType_Cobol</span><span class="sxs-lookup"><span data-stu-id="2b3ed-118">CorSym_LanguageType_Cobol</span></span>|<span data-ttu-id="2b3ed-119">COBOL 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-119">Indicates the COBOL language.</span></span>|  
|<span data-ttu-id="2b3ed-120">CorSym_LanguageType_Pascal</span><span class="sxs-lookup"><span data-stu-id="2b3ed-120">CorSym_LanguageType_Pascal</span></span>|<span data-ttu-id="2b3ed-121">Pascal 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-121">Indicates the Pascal language.</span></span>|  
|<span data-ttu-id="2b3ed-122">CorSym_LanguageType_ILAssembly</span><span class="sxs-lookup"><span data-stu-id="2b3ed-122">CorSym_LanguageType_ILAssembly</span></span>|<span data-ttu-id="2b3ed-123">Microsoft 중간 언어 (MSIL) 어셈블리 코드를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-123">Indicates the Microsoft intermediate language (MSIL) assembly code.</span></span>|  
|<span data-ttu-id="2b3ed-124">CorSym_LanguageType_JScript</span><span class="sxs-lookup"><span data-stu-id="2b3ed-124">CorSym_LanguageType_JScript</span></span>|<span data-ttu-id="2b3ed-125">JScript 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-125">Indicates the JScript language.</span></span>|  
|<span data-ttu-id="2b3ed-126">CorSym_LanguageType_SMC</span><span class="sxs-lookup"><span data-stu-id="2b3ed-126">CorSym_LanguageType_SMC</span></span>|<span data-ttu-id="2b3ed-127">SMC 언어를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-127">Indicates the SMC language.</span></span>|  
|<span data-ttu-id="2b3ed-128">CorSym_LanguageType_MCPlusPlus</span><span class="sxs-lookup"><span data-stu-id="2b3ed-128">CorSym_LanguageType_MCPlusPlus</span></span>|<span data-ttu-id="2b3ed-129">C + + 언어를.NET Framework에 대 한 사용을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-129">Indicates the C++ language enabled for the .NET Framework.</span></span>|  
  
## <a name="language-vendor-constants"></a><span data-ttu-id="2b3ed-130">언어 공급 업체 상수</span><span class="sxs-lookup"><span data-stu-id="2b3ed-130">Language Vendor Constants</span></span>  
 <span data-ttu-id="2b3ed-131">다음 표에서 언어 프로그래밍 언어 공급 업체를 식별 하는 Guid를 표시 하는 공급 업체 상수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-131">The following table shows language vendor constants, which represent GUIDs that identify programming language vendors.</span></span>  
  
|<span data-ttu-id="2b3ed-132">기호</span><span class="sxs-lookup"><span data-stu-id="2b3ed-132">Symbol</span></span>|<span data-ttu-id="2b3ed-133">설명</span><span class="sxs-lookup"><span data-stu-id="2b3ed-133">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2b3ed-134">CorSym_LanguageVendor_Microsoft</span><span class="sxs-lookup"><span data-stu-id="2b3ed-134">CorSym_LanguageVendor_Microsoft</span></span>|<span data-ttu-id="2b3ed-135">Microsoft를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-135">Indicates Microsoft.</span></span>|  
  
## <a name="document-type-constants"></a><span data-ttu-id="2b3ed-136">문서 형식 상수</span><span class="sxs-lookup"><span data-stu-id="2b3ed-136">Document Type Constants</span></span>  
 <span data-ttu-id="2b3ed-137">다음 표에서 문서 문서 형식을 식별 하는 Guid를 나타내는 형식 상수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-137">The following table shows document type constants, which represent GUIDs that identify document types.</span></span>  
  
|<span data-ttu-id="2b3ed-138">기호</span><span class="sxs-lookup"><span data-stu-id="2b3ed-138">Symbol</span></span>|<span data-ttu-id="2b3ed-139">설명</span><span class="sxs-lookup"><span data-stu-id="2b3ed-139">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2b3ed-140">CorSym_DocumentType_Text</span><span class="sxs-lookup"><span data-stu-id="2b3ed-140">CorSym_DocumentType_Text</span></span>|<span data-ttu-id="2b3ed-141">텍스트 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-141">Indicates a text document.</span></span>|  
|<span data-ttu-id="2b3ed-142">CorSym_DocumentType_MC</span><span class="sxs-lookup"><span data-stu-id="2b3ed-142">CorSym_DocumentType_MC</span></span>|<span data-ttu-id="2b3ed-143">텍스트가 아닌 문서를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2b3ed-143">Indicates a non-text document.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2b3ed-144">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b3ed-144">See also</span></span>
- [<span data-ttu-id="2b3ed-145">관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="2b3ed-145">Unmanaged API Reference</span></span>](../../../docs/framework/unmanaged-api/index.md)
