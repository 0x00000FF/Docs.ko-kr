---
title: '방법: 부호 없는 형식 (Visual Basic)를 사용 하는 Windows 함수를 호출 합니다.'
ms.date: 07/20/2015
helpviewer_keywords:
- Windows functions [Visual Basic], calling
- unsigned data types [Visual Basic]
- UShort data type [Visual Basic], using
- functions [Visual Basic], calling Windows functions
- ULong data type [Visual Basic], using
- UInteger data type [Visual Basic], using
- data types [Visual Basic], using
- unsigned types [Visual Basic]
- data types [Visual Basic], unsigned
- data types [Visual Basic], numeric
- unsigned types [Visual Basic], using
ms.assetid: c2c0e712-8dc2-43b9-b4c6-345fbb02e7ce
ms.openlocfilehash: 092f1acf6e6a8468890a371836979db4e0692d1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54669317"
---
# <a name="how-to-call-a-windows-function-that-takes-unsigned-types-visual-basic"></a><span data-ttu-id="333a9-102">방법: 부호 없는 형식 (Visual Basic)를 사용 하는 Windows 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="333a9-102">How to: Call a Windows Function that Takes Unsigned Types (Visual Basic)</span></span>
<span data-ttu-id="333a9-103">클래스, 모듈 또는 부호 없는 정수 형식의 멤버가 있는 구조를 사용 중인 경우에 Visual Basic을 사용 하 여 이러한 멤버를 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="333a9-103">If you are consuming a class, module, or structure that has members of unsigned integer types, you can access these members with Visual Basic.</span></span>  
  
### <a name="to-call-a-windows-function-that-takes-an-unsigned-type"></a><span data-ttu-id="333a9-104">Windows 함수 호출을 사용 하는 부호 없는 형식</span><span class="sxs-lookup"><span data-stu-id="333a9-104">To call a Windows function that takes an unsigned type</span></span>  
  
1.  <span data-ttu-id="333a9-105">사용 하 여는 [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) 함수가 포함 된 라이브러리, 해당 라이브러리의 이란 해당 이름, 호출 시퀀스 란, 및 호출 시 문자열을 변환 하는 방법을 Visual Basic을 알려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="333a9-105">Use a [Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md) to tell Visual Basic which library holds the function, what its name is in that library, what its calling sequence is, and how to convert strings when calling it.</span></span>  
  
2.  <span data-ttu-id="333a9-106">에 `Declare` 문을 사용 하 여 `UInteger`를 `ULong`를 `UShort`, 또는 `Byte` 부호 없는 형식 사용 하 여 각 매개 변수에 대해 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="333a9-106">In the `Declare` statement, use `UInteger`, `ULong`, `UShort`, or `Byte` as appropriate for each parameter with an unsigned type.</span></span>  
  
3.  <span data-ttu-id="333a9-107">이름 및 사용 되는 상수 값을 찾으려면 호출 하는 Windows 함수 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="333a9-107">Consult the documentation for the Windows function you are calling to find the names and values of the constants it uses.</span></span> <span data-ttu-id="333a9-108">이러한 많은 WinUser.h 파일에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="333a9-108">Many of these are defined in the WinUser.h file.</span></span>  
  
4.  <span data-ttu-id="333a9-109">코드에서 필요한 상수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="333a9-109">Declare the necessary constants in your code.</span></span> <span data-ttu-id="333a9-110">많은 Windows 상수는 32 비트 부호 없는 값 및 이러한 선언 해야 `As``UInteger`합니다.</span><span class="sxs-lookup"><span data-stu-id="333a9-110">Many Windows constants are 32-bit unsigned values, and you should declare these `As``UInteger`.</span></span>  
  
5.  <span data-ttu-id="333a9-111">일반적인 방법으로 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="333a9-111">Call the function in the normal way.</span></span> <span data-ttu-id="333a9-112">Windows 함수를 호출 하는 다음 예제에서는 `MessageBox`, 부호 없는 정수 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="333a9-112">The following example calls the Windows function `MessageBox`, which takes an unsigned integer argument.</span></span>  
  
    ```  
    Public Class windowsMessage  
        Private Declare Auto Function mb Lib "user32.dll" Alias "MessageBox" (  
            ByVal hWnd As Integer,   
            ByVal lpText As String,   
            ByVal lpCaption As String,   
            ByVal uType As UInteger) As Integer  
        Private Const MB_OK As UInteger = 0  
        Private Const MB_ICONEXCLAMATION As UInteger = &H30  
        Private Const IDOK As UInteger = 1  
        Private Const IDCLOSE As UInteger = 8  
        Private Const c As UInteger = MB_OK Or MB_ICONEXCLAMATION  
        Public Function messageThroughWindows() As String  
            Dim r As Integer = mb(0, "Click OK if you see this!",   
                "Windows API call", c)  
            Dim s As String = "Windows API MessageBox returned " &  
                 CStr(r)& vbCrLf & "(IDOK = " & CStr(IDOK) &  
                 ", IDCLOSE = " & CStr(IDCLOSE) & ")"  
            Return s  
        End Function  
    End Class  
    ```  
  
     <span data-ttu-id="333a9-113">함수를 테스트할 수 `messageThroughWindows` 다음 코드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="333a9-113">You can test the function `messageThroughWindows` with the following code.</span></span>  
  
    ```  
    Public Sub consumeWindowsMessage()  
        Dim w As New windowsMessage  
        w.messageThroughWindows()  
    End Sub  
    ```  
  
    > [!CAUTION]
    >  <span data-ttu-id="333a9-114">`UInteger`, `ULong`, `UShort`, 및 `SByte` 데이터 형식이 다의 일부를 [Language Independence and Language-independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), CLS 규격 코드 구성 요소를 사용할 수 없습니다 있도록 하는 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="333a9-114">The `UInteger`, `ULong`, `UShort`, and `SByte` data types are not part of the [Language Independence and Language-Independent Components](../../../standard/language-independence-and-language-independent-components.md) (CLS), so CLS-compliant code cannot consume a component that uses them.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="333a9-115">Windows 응용 프로그램 프로그래밍 인터페이스 (API)와 같은 관리 되지 않는 코드를 호출 하는 잠재적인 보안 위험에 코드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="333a9-115">Making a call to unmanaged code, such as the Windows application programming interface (API), exposes your code to potential security risks.</span></span>  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="333a9-116">Windows API를 호출 하려면 부분 신뢰 상황에서 해당 실행에 영향을 줄 수 있는 비관리 코드 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="333a9-116">Calling the Windows API requires unmanaged code permission, which might affect its execution in partial-trust situations.</span></span> <span data-ttu-id="333a9-117">자세한 내용은 <xref:System.Security.Permissions.SecurityPermission> 하 고 [코드 액세스 권한](https://msdn.microsoft.com/library/e5ae402f-6dda-4732-bbe8-77296630f675)합니다.</span><span class="sxs-lookup"><span data-stu-id="333a9-117">For more information, see <xref:System.Security.Permissions.SecurityPermission> and [Code Access Permissions](https://msdn.microsoft.com/library/e5ae402f-6dda-4732-bbe8-77296630f675).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="333a9-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="333a9-118">See also</span></span>
- [<span data-ttu-id="333a9-119">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="333a9-119">Data Types</span></span>](../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="333a9-120">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="333a9-120">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)
- [<span data-ttu-id="333a9-121">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="333a9-121">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)
- [<span data-ttu-id="333a9-122">Declare 문</span><span class="sxs-lookup"><span data-stu-id="333a9-122">Declare Statement</span></span>](../../../visual-basic/language-reference/statements/declare-statement.md)
- [<span data-ttu-id="333a9-123">연습: Windows API 호출</span><span class="sxs-lookup"><span data-stu-id="333a9-123">Walkthrough: Calling Windows APIs</span></span>](../../../visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis.md)
