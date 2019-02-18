---
title: MsgBox 샘플
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- marshaling, MsgBox sample
- data marshaling, MsgBox sample
ms.assetid: 9e0edff6-cc0d-4d5c-a445-aecf283d9c3a
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3393adf5beed02a5a4bda2e07bd26e29e47fae2f
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/13/2019
ms.locfileid: "56219310"
---
# <a name="msgbox-sample"></a><span data-ttu-id="530cc-102">MsgBox 샘플</span><span class="sxs-lookup"><span data-stu-id="530cc-102">MsgBox Sample</span></span>
<span data-ttu-id="530cc-103">이 샘플에서는 In 매개 변수로 값 형식 문자열 형식을 전달하는 방법과 <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> 및 <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> 필드 사용 시기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="530cc-103">This sample demonstrates how to pass string types by value as In parameters and when to use the <xref:System.Runtime.InteropServices.DllImportAttribute.EntryPoint>, <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet>, and <xref:System.Runtime.InteropServices.DllImportAttribute.ExactSpelling> fields.</span></span>  
  
 <span data-ttu-id="530cc-104">MsgBox 샘플에서는 원래 함수 선언과 함께 표시되는 다음과 같은 관리되지 않는 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="530cc-104">The MsgBox sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
-   <span data-ttu-id="530cc-105">User32.dll에서 내보낸 **MessageBox**.</span><span class="sxs-lookup"><span data-stu-id="530cc-105">**MessageBox** exported from User32.dll.</span></span>  
  
    ```  
    int MessageBox(HWND hWnd, LPCTSTR lpText, LPCTSTR lpCaption,   
       UINT uType);  
    ```  
  
 <span data-ttu-id="530cc-106">이 샘플에서 `LibWrap` 클래스에는 `MsgBoxSample` 클래스에서 호출하는 관리되지 않는 각 함수의 관리되는 프로토타입이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="530cc-106">In this sample, the `LibWrap` class contains a managed prototype for each unmanaged function called by the `MsgBoxSample` class.</span></span> <span data-ttu-id="530cc-107">관리되는 프로토타입 메서드 `MsgBox`, `MsgBox2` 및 `MsgBox3`에는 관리되지 않는 동일한 함수에 대한 다른 선언이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="530cc-107">The managed prototype methods `MsgBox`, `MsgBox2`, and `MsgBox3` have different declarations for the same unmanaged function.</span></span>  
  
 <span data-ttu-id="530cc-108">ANSI로 지정된 문자 유형은 Unicode 함수의 이름인 진입점 `MessageBoxW`와 일치하지 않으므로 `MsgBox2`를 선언하면 메시지 상자에 잘못된 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="530cc-108">The declaration for `MsgBox2` produces incorrect output in the message box because the character type, specified as ANSI, is mismatched with the entry point `MessageBoxW`, which is the name of the Unicode function.</span></span> <span data-ttu-id="530cc-109">`MsgBox3`의 선언으로 인해 **EntryPoint**, **CharSet** 및 **ExactSpelling** 필드가 불일치하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="530cc-109">The declaration for `MsgBox3` creates a mismatch between the **EntryPoint**, **CharSet**, and **ExactSpelling** fields.</span></span> <span data-ttu-id="530cc-110">호출되면 `MsgBox3`에서 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="530cc-110">When called, `MsgBox3` throws an exception.</span></span> <span data-ttu-id="530cc-111">문자열 이름 지정 및 이름 마샬링에 대한 자세한 내용은 [문자 집합 지정](specifying-a-character-set.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="530cc-111">For detailed information on string naming and name marshaling, see [Specifying a Character Set](specifying-a-character-set.md).</span></span>  
  
## <a name="declaring-prototypes"></a><span data-ttu-id="530cc-112">프로토타입 선언</span><span class="sxs-lookup"><span data-stu-id="530cc-112">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#5)]
 [!code-csharp[Conceptual.Interop.Marshaling#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#5)]
 [!code-vb[Conceptual.Interop.Marshaling#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#5)]  
  
## <a name="calling-functions"></a><span data-ttu-id="530cc-113">함수 호출</span><span class="sxs-lookup"><span data-stu-id="530cc-113">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/msgbox.cpp#6)]
 [!code-csharp[Conceptual.Interop.Marshaling#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/msgbox.cs#6)]
 [!code-vb[Conceptual.Interop.Marshaling#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/msgbox.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="530cc-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="530cc-114">See also</span></span>
- [<span data-ttu-id="530cc-115">문자열 마샬링</span><span class="sxs-lookup"><span data-stu-id="530cc-115">Marshaling Strings</span></span>](marshaling-strings.md)
- [<span data-ttu-id="530cc-116">문자열에 대한 기본 마샬링</span><span class="sxs-lookup"><span data-stu-id="530cc-116">Default Marshaling for Strings</span></span>](default-marshaling-for-strings.md)
- [<span data-ttu-id="530cc-117">관리 코드에서 프로토타입 만들기</span><span class="sxs-lookup"><span data-stu-id="530cc-117">Creating Prototypes in Managed Code</span></span>](creating-prototypes-in-managed-code.md)
- [<span data-ttu-id="530cc-118">문자 집합 지정</span><span class="sxs-lookup"><span data-stu-id="530cc-118">Specifying a Character Set</span></span>](specifying-a-character-set.md)
