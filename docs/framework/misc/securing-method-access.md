---
title: 메서드 액세스 보안
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- code security, method access
- secure coding, method access
- security [.NET Framework], method access
- method access security
ms.assetid: f7c2d6ec-3b18-4e0e-9991-acd97189d818
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2159199fc12ef83a6bf4a44841d71799e0dad4dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61868968"
---
# <a name="securing-method-access"></a><span data-ttu-id="65b2c-102">메서드 액세스 보안</span><span class="sxs-lookup"><span data-stu-id="65b2c-102">Securing Method Access</span></span>
[!INCLUDE[net_security_note](../../../includes/net-security-note-md.md)]  
  
 <span data-ttu-id="65b2c-103">몇몇 메서드는 임의의 신뢰할 수 없는 코드 호출을 허용하는 데 적합하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-103">Some methods might not be suitable to allow arbitrary untrusted code to call.</span></span> <span data-ttu-id="65b2c-104">이러한 메서드는 위험을 가져옵니다. 메서드는 몇 가지 제한 된 정보를 제공할 수 있습니다. 적용 합니다. 전달 된 모든 정보를 생각할 수 있습니다. 매개 변수를;에서 오류 검사를 수행 하지 않을 수 있습니다. 또는 잘못 된 매개 변수를 사용 하 여 오작동 하거나 피해 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-104">Such methods pose several risks: The method might provide some restricted information; it might believe any information passed to it; it might not do error checking on the parameters; or with the wrong parameters, it might malfunction or do something harmful.</span></span> <span data-ttu-id="65b2c-105"> 이들 경우에 대해 알고 있어야 하고 메서드 보호를 도와주는 조치를 취해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-105">You should be aware of these cases and take action to help protect the method.</span></span>  
  
 <span data-ttu-id="65b2c-106">경우에 따라 공용으로 제공되지 않지만 공용으로 사용되어야 하는 메서드를 제한해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-106">In some cases, you might need to restrict methods that are not intended for public use but still must be public.</span></span> <span data-ttu-id="65b2c-107">예를 들어 자체 DLL에서 호출되어야 하고 공용으로도 사용되어야 하는 인터페이스를 포함하지만, 이 인터페이스를 고객이 사용하지 않도록 하고 악성 코드가 구성 요소에 대한 진입점으로 악용하지 못하도록 방지하기 위해 이 인터페이스를 공개적으로 노출하지 않고자 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-107">For example, you might have an interface that needs to be called across your own DLLs and hence must be public, but you do not want to expose it publicly to prevent customers from using it or to prevent malicious code from exploiting the entry point into your component.</span></span> <span data-ttu-id="65b2c-108">공용으로 제공되지 않은 메서드를 제한하는 또 다른 일반적인 이유는 완전히 내부적인 인터페이스일 수 있는 내용을 문서화하고 지원할 필요가 없도록 하려는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-108">Another common reason to restrict a method not intended for public use (but that must be public) is to avoid having to document and support what might be a very internal interface.</span></span>  
  
 <span data-ttu-id="65b2c-109">관리 코드는 메서드 액세스를 제한하는 여러 가지 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-109">Managed code offers several ways to restrict method access:</span></span>  
  
-   <span data-ttu-id="65b2c-110">액세스 가능성 범위를 신뢰할 수 있는 클래스, 어셈블리 또는 파생 클래스로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-110">Limit the scope of accessibility to the class, assembly, or derived classes, if they can be trusted.</span></span> <span data-ttu-id="65b2c-111">이는 메서드 액세스를 제한하는 가장 간단한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-111">This is the simplest way to limit method access.</span></span> <span data-ttu-id="65b2c-112">일반적으로 파생 클래스는 자신이 파생된 소스 클래스보다 신뢰도가 더 낮지만 경우에 따라 부모 클래스의 ID를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-112">Note that, in general, derived classes can be less trustworthy than the class they derive from, though in some cases they share the parent class's identity.</span></span> <span data-ttu-id="65b2c-113">특히 키워드에서 신뢰를 유추 하지 마세요 **보호**, 보안 컨텍스트에서 반드시 사용 되지 않는 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-113">In particular, do not infer trust from the keyword **protected**, which is not necessarily used in the security context.</span></span>  
  
-   <span data-ttu-id="65b2c-114">지정된 된 id, 기본적으로, 특정의 호출자에 게 메서드 액세스를 제한 [증거](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29) 선택 (강력한 이름, 게시자, 영역 및 등).</span><span class="sxs-lookup"><span data-stu-id="65b2c-114">Limit the method access to callers of a specified identity--essentially, any particular [evidence](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/7y5x1hcd%28v=vs.100%29) (strong name, publisher, zone, and so on) you choose.</span></span>  
  
-   <span data-ttu-id="65b2c-115">메서드 액세스를 선택한 권한을 가진 호출자로 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-115">Limit the method access to callers having whatever permissions you select.</span></span>  
  
 <span data-ttu-id="65b2c-116">마찬가지로 선언적 보안을 통해 클래스 상속을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-116">Similarly, declarative security allows you to control inheritance of classes.</span></span> <span data-ttu-id="65b2c-117">사용할 수 있습니다 **InheritanceDemand** 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-117">You can use **InheritanceDemand** to do the following:</span></span>  
  
-   <span data-ttu-id="65b2c-118">지정된 ID 또는 권한을 포함할 파생 클래스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-118">Require derived classes to have a specified identity or permission.</span></span>  
  
-   <span data-ttu-id="65b2c-119">지정된 ID 또는 권한을 포함하도록 특정 메서드를 재정의하는 파생 클래스가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-119">Require derived classes that override specific methods to have a specified identity or permission.</span></span>  
  
 <span data-ttu-id="65b2c-120">다음 예제에서는 특정 강력한 이름을 통해 호출자에 서명하도록 요구하여 제한된 액세스용 공용 클래스를 보호하도록 도와주는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-120">The following example shows how to help protect a public class for limited access by requiring that callers be signed with a particular strong name.</span></span> <span data-ttu-id="65b2c-121">이 예제에서는 합니다 <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> 사용 하 여는 **수요** 강력한 이름에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-121">This example uses the <xref:System.Security.Permissions.StrongNameIdentityPermissionAttribute> with a **Demand** for the strong name.</span></span> <span data-ttu-id="65b2c-122">강력한 이름의 어셈블리에 서명 하는 방법에 작업 기반 정보를 참조 하세요. [강력한 어셈블리 만들기 및 사용](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-122">For task-based information on how to sign an assembly with a strong name, see [Creating and Using Strong-Named Assemblies](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).</span></span>  
  
```vb  
<StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey := "…hex…", Name := "App1", Version := "0.0.0.0")>  _  
Public Class Class1  
End Class  
```  
  
```csharp  
[StrongNameIdentityPermissionAttribute(SecurityAction.Demand, PublicKey="…hex…", Name="App1", Version="0.0.0.0")]  
public class Class1  
{  
  
}   
```  
  
## <a name="excluding-classes-and-members-from-use-by-untrusted-code"></a><span data-ttu-id="65b2c-123">신뢰할 수 없는 코드에 의한 클래스 및 멤버 사용 방지</span><span class="sxs-lookup"><span data-stu-id="65b2c-123">Excluding Classes and Members from Use by Untrusted Code</span></span>  
 <span data-ttu-id="65b2c-124">이 섹션에 표시된 선언을 사용하여 특정 클래스와 메서드 및 속성과 이벤트가 부분 신뢰 코드에서 사용되지 않도록 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-124">Use the declarations shown in this section to prevent specific classes and methods, as well as properties and events, from being used by partially trusted code.</span></span> <span data-ttu-id="65b2c-125">이들 선언을 클래스에 적용하여 모든 메서드, 속성 및 이벤트에 보호를 적용하지만, 필드 액세스는 선언적 보안의 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-125">By applying these declarations to a class, you apply the protection to all its methods, properties, and events; however, note that field access is not affected by declarative security.</span></span> <span data-ttu-id="65b2c-126">또한 링크 요청은 직접 실행 호출자 차단에만 도움이 되고 유인 공격의 대상이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-126">Note also that link demands help protect against only the immediate callers and might still be subject to luring attacks.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65b2c-127">새 투명성 모델은 [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)]에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-127">A new transparency model has been introduced in the [!INCLUDE[net_v40_long](../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="65b2c-128">합니다 [보안 투명 코드, 수준 2](../../../docs/framework/misc/security-transparent-code-level-2.md) 사용 하 여 보안 코드를 식별 하는 모델을 <xref:System.Security.SecurityCriticalAttribute> 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-128">The [Security-Transparent Code, Level 2](../../../docs/framework/misc/security-transparent-code-level-2.md) model identifies secure code with the <xref:System.Security.SecurityCriticalAttribute> attribute.</span></span> <span data-ttu-id="65b2c-129">보안에 중요한 코드에서는 호출자와 상속자를 둘 다 완전히 신뢰할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-129">Security-critical code requires both callers and inheritors to be fully trusted.</span></span> <span data-ttu-id="65b2c-130">이전 .NET Framework 버전에서 코드 액세스 보안 규칙에 따라 실행 중인 어셈블리는 수준 2 어셈블리를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-130">Assemblies that are running under the code access security rules from earlier .NET Framework versions can call level 2 assemblies.</span></span> <span data-ttu-id="65b2c-131">이 경우 보안에 중요한 특성은 완전 신뢰를 위해 링크 요청으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-131">In this case, the security-critical attributes will be treated as link demands for full trust.</span></span>  
  
 <span data-ttu-id="65b2c-132">강력한 이름의 어셈블리에는 [LinkDemand](../../../docs/framework/misc/link-demands.md) 모든 공개적으로 액세스할 수 있는 메서드, 속성 및 완전히 신뢰할 수 있는 호출자에 게 해당 사용을 제한 하도록 이벤트에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-132">In strong-named assemblies, a [LinkDemand](../../../docs/framework/misc/link-demands.md) is applied to all publicly accessible methods, properties, and events therein to restrict their use to fully trusted callers.</span></span> <span data-ttu-id="65b2c-133">이 기능을 사용하지 않도록 설정하려면 <xref:System.Security.AllowPartiallyTrustedCallersAttribute> 특성을 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-133">To disable this feature, you must apply the <xref:System.Security.AllowPartiallyTrustedCallersAttribute> attribute.</span></span> <span data-ttu-id="65b2c-134">따라서 신뢰할 수 없는 호출자를 제외하도록 클래스에 명시적으로 표시하는 작업은 서명되지 않은 어셈블리나 이 특성이 포함된 어셈블리에만 필요합니다. 이들 선언을 사용하여 신뢰할 수 없는 호출자로 제공되지 않은 형식 하위 집합을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-134">Thus, explicitly marking classes to exclude untrusted callers is necessary only for unsigned assemblies or assemblies with this attribute; you can use these declarations to mark a subset of types therein that are not intended for untrusted callers.</span></span>  
  
 <span data-ttu-id="65b2c-135">다음 예제에서는 클래스와 멤버가 신뢰할 수 없는 코드에서 사용되지 않도록 방지하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-135">The following examples show how to prevent classes and members from being used by untrusted code.</span></span>  
  
 <span data-ttu-id="65b2c-136">봉인되지 않은 공용 클래스의 경우:</span><span class="sxs-lookup"><span data-stu-id="65b2c-136">For public nonsealed classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _   
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
Public Class CanDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public class CanDeriveFromMe  
{  
}  
```  
  
 <span data-ttu-id="65b2c-137">봉인된 공용 클래스의 경우:</span><span class="sxs-lookup"><span data-stu-id="65b2c-137">For public sealed classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
NotInheritable Public Class CannotDeriveFromMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public sealed class CannotDeriveFromMe  
{  
}  
```  
  
 <span data-ttu-id="65b2c-138">공용 추상 클래스의 경우:</span><span class="sxs-lookup"><span data-stu-id="65b2c-138">For public abstract classes:</span></span>  
  
```vb  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name := "FullTrust"), _  
System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name := "FullTrust")>  _  
MustInherit Public Class CannotCreateInstanceOfMe_CanCastToMe  
End Class  
```  
  
```csharp  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
public abstract class CannotCreateInstanceOfMe_CanCastToMe {}  
```  
  
 <span data-ttu-id="65b2c-139">공용 가상 함수의 경우:</span><span class="sxs-lookup"><span data-stu-id="65b2c-139">For public virtual functions:</span></span>  
  
```vb  
Class Base1   
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overridable Sub CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Base1  
```  
  
```csharp  
class Base1   
{  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name="FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]  
    public virtual void CanOverrideOrCallMe() {}  
}  
```  
  
 <span data-ttu-id="65b2c-140">공용 추상 함수의 경우:</span><span class="sxs-lookup"><span data-stu-id="65b2c-140">For public abstract functions:</span></span>  
  
```vb  
MustInherit Class Base2  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Sub MustOverrideMe()  
    End Sub  
End Class 'Base2  
```  
  
```csharp  
abstract class Base2 {  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(  
System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
public abstract void MustOverrideMe();  
}  
```  
  
 <span data-ttu-id="65b2c-141">기본 클래스가 완전 신뢰를 요청하지 않는 공용 재정의 함수의 경우:</span><span class="sxs-lookup"><span data-stu-id="65b2c-141">For public override functions where the base class does not demand full trust:</span></span>  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe  
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{     
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.Demand, Name="FullTrust")]      
    public override void CanOverrideOrCallMe()   
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 <span data-ttu-id="65b2c-142">기본 클래스가 완전 신뢰를 요청하는 공용 재정의 함수의 경우:</span><span class="sxs-lookup"><span data-stu-id="65b2c-142">For public override functions where the base class demands full trust:</span></span>  
  
```vb  
Class Derived  
    Inherits Base1  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust")> _  
    Public Overrides Sub CanOverrideOrCallMe()  
        MyBase.CanOverrideOrCallMe()  
    End Sub 'CanOverrideOrCallMe   
End Class 'Derived  
```  
  
```csharp  
class Derived : Base1  
{     
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name="FullTrust")]      
    public override void CanOverrideOrCallMe()   
    {  
        base.CanOverrideOrCallMe();  
    }  
}  
```  
  
 <span data-ttu-id="65b2c-143">공용 인터페이스의 경우:</span><span class="sxs-lookup"><span data-stu-id="65b2c-143">For public interfaces:</span></span>  
  
```vb  
Public Interface ICanCastToMe  
    <System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
    Sub CanImplementMe()  
End Interface 'ICanCastToMe  
<System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name:="FullTrust"), System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name:="FullTrust")> _  
Class Implemented  
    Implements ICanCastToMe  
    Public Sub CanImplementMe()  
    End Sub 'CanImplementMe  
```  
  
```csharp  
public interface ICanCastToMe   
{  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
void CanImplementMe();  
}  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.LinkDemand, Name = "FullTrust")]  
[System.Security.Permissions.PermissionSetAttribute(System.Security.Permissions.SecurityAction.InheritanceDemand, Name = "FullTrust")]  
class Implemented : ICanCastToMe  
{  
    public void CanImplementMe()  
    {  
    }  
}  
```  
  
## <a name="virtual-internal-overrides-or-overloads-overridable-friend"></a><span data-ttu-id="65b2c-144">Virtual Internal 재정의 또는 Overloads Overridable Friend</span><span class="sxs-lookup"><span data-stu-id="65b2c-144">Virtual Internal Overrides or Overloads Overridable Friend</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="65b2c-145">둘 다로 메서드를 선언 하는 경우이 섹션에서는 보안 문제에 대 한 경고 `virtual` 하 고 `internal` (`Overloads` `Overridable` `Friend` Visual basic에서).</span><span class="sxs-lookup"><span data-stu-id="65b2c-145">This section warns about a security issue when declaring a method as both `virtual` and `internal` (`Overloads` `Overridable` `Friend` in Visual Basic).</span></span> <span data-ttu-id="65b2c-146">이 경고는.NET Framework 버전 1.0 및 1.1에만 적용 됩니다, 그리고 이후 버전에 적용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-146">This warning applies only to the .NET Framework versions 1.0 and 1.1, it does not apply to later versions.</span></span>  
  
 <span data-ttu-id="65b2c-147">.NET Framework 버전 1.0 및 1.1에서는 알아야 형식 시스템 액세스 가능성의 미묘한 차이 확인 코드를 다른 어셈블리에 사용할 수 없는 경우.</span><span class="sxs-lookup"><span data-stu-id="65b2c-147">In the .NET Framework versions 1.0 and 1.1, you must be aware of a nuance of the type system accessibility when confirming that your code is unavailable to other assemblies.</span></span> <span data-ttu-id="65b2c-148">선언 된 메서드 **가상** 하 고 **내부** (**Overloads Overridable Friend** Visual basic에서) 부모 클래스의 vtable 항목을 재정의할 수 있습니다 및 에서만 사용할 수 있습니다 동일한 어셈블리 내에서 내부 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-148">A method that is declared **virtual** and **internal** (**Overloads Overridable Friend** in Visual Basic) can override the parent class's vtable entry and can be used only from within the same assembly because it is internal.</span></span> <span data-ttu-id="65b2c-149">그러나 재정의 대 한 내게 필요한 옵션에 의해 결정 되는 **가상** 키워드 및 해당 코드는 클래스 자체에 액세스할 수 있다면 다른 어셈블리에서 재정의 될 수이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-149">However, the accessibility for overriding is determined by the **virtual** keyword, and this can be overridden from another assembly as long as that code has access to the class itself.</span></span> <span data-ttu-id="65b2c-150">재정의 가능성 문제를 제출 하는 경우 선언적 보안을 사용 하 여, 수정 하거나 제거 합니다 **가상** 키워드 엄격 하 게 필요 하지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="65b2c-150">If the possibility of an override presents a problem, use declarative security to fix it, or remove the **virtual** keyword if it is not strictly required.</span></span>  
  
 <span data-ttu-id="65b2c-151">언어 컴파일러에서 컴파일 오류 때문에 이 재정의가 차단되더라도 다른 컴파일러로 작성된 코드는 재정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b2c-151">Note that even if a language compiler prevents these overrides with a compilation error, it is possible for code written with other compilers to override.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65b2c-152">참고자료</span><span class="sxs-lookup"><span data-stu-id="65b2c-152">See also</span></span>

- [<span data-ttu-id="65b2c-153">보안 코딩 지침</span><span class="sxs-lookup"><span data-stu-id="65b2c-153">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
