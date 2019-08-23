---
title: 특성 개요(Visual Basic)
ms.date: 07/20/2015
ms.assetid: 1449f69b-c063-41de-8d89-f0bbdcf96ac6
ms.openlocfilehash: c799b9be9b936beadde28374bd9882ebc6e2d9a2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69966311"
---
# <a name="attributes-overview-visual-basic"></a><span data-ttu-id="97f33-102">특성 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97f33-102">Attributes overview (Visual Basic)</span></span>
<span data-ttu-id="97f33-103">특성은 메타데이터 또는 선언적 정보를 코드(어셈블리, 형식, 메서드, 속성 등)에 연결하는 강력한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-103">Attributes provide a powerful method of associating metadata, or declarative information, with code (assemblies, types, methods, properties, and so forth).</span></span> <span data-ttu-id="97f33-104">특성이 프로그램 엔터티와 연결되면 *리플렉션*이라는 기법을 사용하여 런타임에 특성이 쿼리될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-104">After an attribute is associated with a program entity, the attribute can be queried at run time by using a technique called *reflection*.</span></span> <span data-ttu-id="97f33-105">자세한 내용은 [리플렉션(Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97f33-105">For more information, see [Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/reflection.md).</span></span>  
  
 <span data-ttu-id="97f33-106">특성에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-106">Attributes have the following properties:</span></span>  
  
- <span data-ttu-id="97f33-107">특성은 프로그램에 메타데이터를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-107">Attributes add metadata to your program.</span></span> <span data-ttu-id="97f33-108">*메타데이터*는 프로그램에 정의된 형식에 대한 정보를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-108">*Metadata* is information about the types defined in a program.</span></span> <span data-ttu-id="97f33-109">모든 .NET 어셈블리에는 어셈블리에 정의된 형식 및 형식 멤버를 설명하는 지정된 메타데이터 집합이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-109">All .NET assemblies contain a specified set of metadata that describes the types and type members defined in the assembly.</span></span> <span data-ttu-id="97f33-110">필요한 추가 정보를 지정하는 사용자 지정 특성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-110">You can add custom attributes to specify any additional information that is required.</span></span> <span data-ttu-id="97f33-111">자세한 내용은 [사용자 지정 특성 만들기(Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97f33-111">For more information, see, [Creating Custom Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md).</span></span>  
  
- <span data-ttu-id="97f33-112">전체 어셈블리, 모듈 또는 좀 더 작은 프로그램 요소(예: 클래스 및 속성)에 하나 이상의 특성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-112">You can apply one or more attributes to entire assemblies, modules, or smaller program elements such as classes and properties.</span></span>  
  
- <span data-ttu-id="97f33-113">메서드 및 속성의 경우와 같은 방식으로 특성은 인수를 수락할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-113">Attributes can accept arguments in the same way as methods and properties.</span></span>  
  
- <span data-ttu-id="97f33-114">프로그램은 리플렉션을 사용하여 자체 메타데이터 또는 다른 프로그램의 메타데이터를 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-114">Your program can examine its own metadata or the metadata in other programs by using reflection.</span></span> <span data-ttu-id="97f33-115">자세한 내용은 [리플렉션을 사용하여 특성 액세스(Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97f33-115">For more information, see [Accessing Attributes by Using Reflection (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md).</span></span>  
  
## <a name="using-attributes"></a><span data-ttu-id="97f33-116">특성 사용</span><span class="sxs-lookup"><span data-stu-id="97f33-116">Using Attributes</span></span>  
 <span data-ttu-id="97f33-117">특정 특성이 유효한 선언 형식을 제한할 수  있지만 거의 모든 선언에 특성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-117">Attributes can be placed on most any declaration, though a specific attribute might restrict the types of declarations on which it is valid.</span></span> <span data-ttu-id="97f33-118">Visual Basic의 경우 특성은 꺾쇠 괄호(\<>) 안에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-118">In Visual Basic, an attribute is enclosed in angle brackets (\< >).</span></span> <span data-ttu-id="97f33-119">특성은 적용되는 요소 바로 앞에 표시되어야 하며 같은 줄에 위치합니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-119">It must appear immediately before the element to which it is applied, on the same line.</span></span>  
  
 <span data-ttu-id="97f33-120">이 예제에서 <xref:System.SerializableAttribute> 특성은 클래스에 특정 특성을 적용하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-120">In this example, the <xref:System.SerializableAttribute> attribute is used to apply a specific characteristic to a class:</span></span>  
  
```vb  
<System.Serializable()> Public Class SampleClass  
    ' Objects of this type can be serialized.  
End Class  
```  
  
 <span data-ttu-id="97f33-121"><xref:System.Runtime.InteropServices.DllImportAttribute> 특성을 사용하는 메서드는 다음과 같이 선언됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-121">A method with the attribute <xref:System.Runtime.InteropServices.DllImportAttribute> is declared like this:</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
```  
  
```vb  
<System.Runtime.InteropServices.DllImport("user32.dll")>   
Sub SampleMethod()  
End Sub  
```  
  
 <span data-ttu-id="97f33-122">둘 이상의 특성을 하나의 선언에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-122">More than one attribute can be placed on a declaration:</span></span>  
  
```vb  
Imports System.Runtime.InteropServices  
```  
  
```vb  
Sub MethodA(<[In](), Out()> ByVal x As Double)  
End Sub  
Sub MethodB(<Out(), [In]()> ByVal x As Double)  
End Sub  
```  
  
 <span data-ttu-id="97f33-123">지정된 엔터티에 대해 일부 특성을 두 번 이상 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-123">Some attributes can be specified more than once for a given entity.</span></span> <span data-ttu-id="97f33-124">이러한 다용도 특성의 예로 <xref:System.Diagnostics.ConditionalAttribute>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-124">An example of such a multiuse attribute is <xref:System.Diagnostics.ConditionalAttribute>:</span></span>  
  
```vb  
<Conditional("DEBUG"), Conditional("TEST1")>   
Sub TraceMethod()  
End Sub  
```  
  
> [!NOTE]
> <span data-ttu-id="97f33-125">규칙에 따라 모든 특성 이름은 .NET Framework의 다른 항목과 구분하기 위해 단어 "Attribute"로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-125">By convention, all attribute names end with the word "Attribute" to distinguish them from other items in the .NET Framework.</span></span> <span data-ttu-id="97f33-126">그러나 코드에서 특성을 사용하는 경우 특성 접미사를 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-126">However, you do not need to specify the attribute suffix when using attributes in code.</span></span> <span data-ttu-id="97f33-127">예를 들어 `[DllImport]`는 `[DllImportAttribute]`와 같지만 `DllImportAttribute`는 .NET Framework에서 특성의 실제 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-127">For example, `[DllImport]` is equivalent to `[DllImportAttribute]`, but `DllImportAttribute` is the attribute's actual name in the .NET Framework.</span></span>  
  
### <a name="attribute-parameters"></a><span data-ttu-id="97f33-128">특성 매개 변수</span><span class="sxs-lookup"><span data-stu-id="97f33-128">Attribute Parameters</span></span>  
 <span data-ttu-id="97f33-129">많은 특성에는 매개 변수를 위치, 명명되지 않은 또는 명명된 상태의 매개 변수가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-129">Many attributes have parameters, which can be positional, unnamed, or named.</span></span> <span data-ttu-id="97f33-130">모든 위치 매개 변수는 특정 순서로 지정해야 하며 생략할 수 없습니다. 명명된 매개 변수는 선택적이며 순서에 관계 없이 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-130">Any positional parameters must be specified in a certain order and cannot be omitted; named parameters are optional and can be specified in any order.</span></span> <span data-ttu-id="97f33-131">위치 매개 변수가 가장 먼저 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-131">Positional parameters are specified first.</span></span> <span data-ttu-id="97f33-132">예를 들어 다음 세 가지 특성은 동급입니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-132">For example, these three attributes are equivalent:</span></span>  
  
```vb  
<DllImport("user32.dll")>  
<DllImport("user32.dll", SetLastError:=False, ExactSpelling:=False)>  
<DllImport("user32.dll", ExactSpelling:=False, SetLastError:=False)>  
```  
  
 <span data-ttu-id="97f33-133">첫 번째 매개 변수인 DLL 이름은 위치 매개 변수이므로 항상 맨 먼저 오고 나머지 매개 변수가 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-133">The first parameter, the DLL name, is positional and always comes first; the others are named.</span></span> <span data-ttu-id="97f33-134">이 경우 명명된 두 매개 변수는 기본적으로 false이므로 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-134">In this case, both named parameters default to false, so they can be omitted.</span></span> <span data-ttu-id="97f33-135">기본 매개 변수 값에 대한 자세한 내용은 개별 특성의 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97f33-135">Refer to the individual attribute's documentation for information on default parameter values.</span></span>  
  
### <a name="attribute-targets"></a><span data-ttu-id="97f33-136">특성 대상</span><span class="sxs-lookup"><span data-stu-id="97f33-136">Attribute Targets</span></span>  
 <span data-ttu-id="97f33-137">특성의 *대상*은 특성이 적용되는 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-137">The *target* of an attribute is the entity to which the attribute applies.</span></span> <span data-ttu-id="97f33-138">예를 들어 특성은 클래스, 특정 메서드 또는 전체 어셈블리에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-138">For example, an attribute may apply to a class, a particular method, or an entire assembly.</span></span> <span data-ttu-id="97f33-139">기본적으로 특성은 그 앞에 오는 요소에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-139">By default, an attribute applies to the element that it precedes.</span></span> <span data-ttu-id="97f33-140">하지만 특성이 메서드, 해당 매개 변수 또는 해당 반환 값 중 어디에 적용될지를 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-140">But you can also explicitly identify, for example, whether an attribute is applied to a method, or to its parameter, or to its return value.</span></span>  
  
 <span data-ttu-id="97f33-141">특성 대상을 명시적으로 식별하려면 다음 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-141">To explicitly identify an attribute target, use the following syntax:</span></span>  
  
```vb  
<target : attribute-list>  
```  
  
 <span data-ttu-id="97f33-142">가능한 `target` 값 목록은 다음 표에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-142">The list of possible `target` values is shown in the following table.</span></span>  
  
|<span data-ttu-id="97f33-143">대상 값</span><span class="sxs-lookup"><span data-stu-id="97f33-143">Target value</span></span>|<span data-ttu-id="97f33-144">적용 대상</span><span class="sxs-lookup"><span data-stu-id="97f33-144">Applies to</span></span>|  
|------------------|----------------|  
|`assembly`|<span data-ttu-id="97f33-145">전체 어셈블리</span><span class="sxs-lookup"><span data-stu-id="97f33-145">Entire assembly</span></span>|  
|`module`|<span data-ttu-id="97f33-146">현재 어셈블리 모듈(Visual Basic 모듈과는 다름)</span><span class="sxs-lookup"><span data-stu-id="97f33-146">Current assembly module (which is different from a Visual Basic Module)</span></span>|  
  
 <span data-ttu-id="97f33-147">다음 예제에서는 어셈블리와 모듈에 특성을 적용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-147">The following example shows how to apply attributes to assemblies and modules.</span></span> <span data-ttu-id="97f33-148">자세한 내용은 [사용자 지정 특성(Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97f33-148">For more information, see [Common Attributes (Visual Basic)](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md).</span></span>  
  
```vb  
Imports System.Reflection  
<Assembly: AssemblyTitleAttribute("Production assembly 4"),   
Module: CLSCompliant(True)>   
```  
  
## <a name="common-uses-for-attributes"></a><span data-ttu-id="97f33-149">특성의 일반적인 용도</span><span class="sxs-lookup"><span data-stu-id="97f33-149">Common Uses for Attributes</span></span>  
 <span data-ttu-id="97f33-150">다음 목록에는 코드에서 특성이 사용되는 일반적인 경우가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97f33-150">The following list includes a few of the common uses of attributes in code:</span></span>  
  
- <span data-ttu-id="97f33-151">SOAP 프로토콜을 통해 메서드를 호출할 수 있음을 나타내기 위해 웹 서비스에서 `WebMethod` 특성을 사용하여 메서드에 표시.</span><span class="sxs-lookup"><span data-stu-id="97f33-151">Marking methods using the `WebMethod` attribute in Web services to indicate that the method should be callable over the SOAP protocol.</span></span> <span data-ttu-id="97f33-152">자세한 내용은 <xref:System.Web.Services.WebMethodAttribute>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97f33-152">For more information, see <xref:System.Web.Services.WebMethodAttribute>.</span></span>  
  
- <span data-ttu-id="97f33-153">네이티브 코드와 상호 운용될 경우 메서드 매개 변수를 마샬링하는 방법 설명.</span><span class="sxs-lookup"><span data-stu-id="97f33-153">Describing how to marshal method parameters when interoperating with native code.</span></span> <span data-ttu-id="97f33-154">자세한 내용은 <xref:System.Runtime.InteropServices.MarshalAsAttribute>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97f33-154">For more information, see <xref:System.Runtime.InteropServices.MarshalAsAttribute>.</span></span>  
  
- <span data-ttu-id="97f33-155">클래스, 메서드 및 인터페이스에 대한 COM 속성 설명</span><span class="sxs-lookup"><span data-stu-id="97f33-155">Describing the COM properties for classes, methods, and interfaces.</span></span>  
  
- <span data-ttu-id="97f33-156"><xref:System.Runtime.InteropServices.DllImportAttribute> 클래스를 사용하는 비관리 코드 호출</span><span class="sxs-lookup"><span data-stu-id="97f33-156">Calling unmanaged code using the <xref:System.Runtime.InteropServices.DllImportAttribute> class.</span></span>  
  
- <span data-ttu-id="97f33-157">제목, 버전, 설명 또는 상표를 기준으로 어셈블리 설명</span><span class="sxs-lookup"><span data-stu-id="97f33-157">Describing your assembly in terms of title, version, description, or trademark.</span></span>  
  
- <span data-ttu-id="97f33-158">지속성을 위해 serialize할 클래스의 멤버 설명</span><span class="sxs-lookup"><span data-stu-id="97f33-158">Describing which members of a class to serialize for persistence.</span></span>  
  
- <span data-ttu-id="97f33-159">XML serialization를 위해 클래스 멤버 및 XML 노드 간을 매핑하는 방법 설명</span><span class="sxs-lookup"><span data-stu-id="97f33-159">Describing how to map between class members and XML nodes for XML serialization.</span></span>  
  
- <span data-ttu-id="97f33-160">메서드에 대한 보안 요구 사항 설명</span><span class="sxs-lookup"><span data-stu-id="97f33-160">Describing the security requirements for methods.</span></span>  
  
- <span data-ttu-id="97f33-161">보안을 적용하는 데 사용되는 특징 지정</span><span class="sxs-lookup"><span data-stu-id="97f33-161">Specifying characteristics used to enforce security.</span></span>  
  
- <span data-ttu-id="97f33-162">코드를 쉽게 디버그할 수 있도록 하기 위해 JIT(Just-In-Time) 컴파일러를 통해 최적화 제어</span><span class="sxs-lookup"><span data-stu-id="97f33-162">Controlling optimizations by the just-in-time (JIT) compiler so the code remains easy to debug.</span></span>  
  
- <span data-ttu-id="97f33-163">메서드 호출자에 대한 정보 얻기</span><span class="sxs-lookup"><span data-stu-id="97f33-163">Obtaining information about the caller to a method.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="97f33-164">관련 단원</span><span class="sxs-lookup"><span data-stu-id="97f33-164">Related Sections</span></span>  
 <span data-ttu-id="97f33-165">자세한 내용은 다음을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="97f33-165">For more information, see:</span></span>  
  
- [<span data-ttu-id="97f33-166">사용자 지정 특성 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97f33-166">Creating Custom Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/creating-custom-attributes.md)  
  
- [<span data-ttu-id="97f33-167">리플렉션을 사용하여 특성 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97f33-167">Accessing Attributes by Using Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/accessing-attributes-by-using-reflection.md)  
  
- [<span data-ttu-id="97f33-168">방법: 특성을 사용 하C++ 여 C/공용 구조체 만들기 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97f33-168">How to: Create a C/C++ Union by Using Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/how-to-create-a-c-cpp-union-by-using-attributes.md)  
  
- [<span data-ttu-id="97f33-169">일반 특성(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97f33-169">Common Attributes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/attributes/common-attributes.md)  
  
- [<span data-ttu-id="97f33-170">호출자 정보(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97f33-170">Caller Information (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/caller-information.md)  
  
## <a name="see-also"></a><span data-ttu-id="97f33-171">참고자료</span><span class="sxs-lookup"><span data-stu-id="97f33-171">See also</span></span>

- [<span data-ttu-id="97f33-172">Visual Basic 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="97f33-172">Visual Basic Programming Guide</span></span>](../../../../visual-basic/programming-guide/index.md)
- [<span data-ttu-id="97f33-173">리플렉션(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="97f33-173">Reflection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/reflection.md)
- [<span data-ttu-id="97f33-174">특성</span><span class="sxs-lookup"><span data-stu-id="97f33-174">Attributes</span></span>](../../../../standard/attributes/index.md)
