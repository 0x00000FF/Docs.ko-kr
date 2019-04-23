---
title: '방법: 서명 된 Friend 어셈블리 (Visual Basic) 만들기'
ms.date: 03/14/2018
ms.assetid: f2afd83d-b044-484b-a56d-56d0a8a40647
ms.openlocfilehash: 4ff32015647a565f7f68e944ae028deb7f738e28
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59324671"
---
# <a name="how-to-create-signed-friend-assemblies-visual-basic"></a><span data-ttu-id="ad112-102">방법: 서명 된 Friend 어셈블리 (Visual Basic) 만들기</span><span class="sxs-lookup"><span data-stu-id="ad112-102">How to: Create Signed Friend Assemblies (Visual Basic)</span></span>
<span data-ttu-id="ad112-103">이 예제에서는 강력한 이름을 가진 어셈블리와 함께 friend 어셈블리를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-103">This example shows how to use friend assemblies with assemblies that have strong names.</span></span> <span data-ttu-id="ad112-104">두 어셈블리에 모두 강력한 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-104">Both assemblies must be strong named.</span></span> <span data-ttu-id="ad112-105">이 예제의 두 어셈블리는 모두 동일한 키를 사용하지만 두 어셈블리에 서로 다른 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-105">Although both assemblies in this example use the same keys, you could use different keys for two assemblies.</span></span>  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a><span data-ttu-id="ad112-106">서명된 어셈블리 및 friend 어셈블리를 만들려면</span><span class="sxs-lookup"><span data-stu-id="ad112-106">To create a signed assembly and a friend assembly</span></span>  
  
1. <span data-ttu-id="ad112-107">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-107">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="ad112-108">강력한 이름 도구와 함께 다음 명령 시퀀스를 사용하여 키 파일을 생성하고 해당 공개 키를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-108">Use the following sequence of commands with the Strong Name tool to generate a keyfile and to display its public key.</span></span> <span data-ttu-id="ad112-109">자세한 내용은 [Sn.exe (강력한 이름 도구)](../../../../framework/tools/sn-exe-strong-name-tool.md)).</span><span class="sxs-lookup"><span data-stu-id="ad112-109">For more information, see [Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md)).</span></span>  
  
    1.  <span data-ttu-id="ad112-110">이 예제에 대한 강력한 이름 키를 생성하고 FriendAssemblies.snk 파일에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-110">Generate a strong-name key for this example and store it in the file FriendAssemblies.snk:</span></span>  
  
         `sn -k FriendAssemblies.snk`  
  
    2.  <span data-ttu-id="ad112-111">FriendAssemblies.snk에서 공개 키를 추출하고 FriendAssemblies.publickey에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-111">Extract the public key from FriendAssemblies.snk and put it into FriendAssemblies.publickey:</span></span>  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3.  <span data-ttu-id="ad112-112">FriendAssemblies.publickey 파일에 저장된 공개 키를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-112">Display the public key stored in the file FriendAssemblies.publickey:</span></span>  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. <span data-ttu-id="ad112-113">Visual Basic 파일을 만듭니다 `friend_signed_A` 다음 코드를 포함 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-113">Create a Visual Basic file named `friend_signed_A` that contains the following code.</span></span> <span data-ttu-id="ad112-114">코드에서는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성을 사용하여 friend_signed_B를 friend 어셈블리로 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-114">The code uses the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute to declare friend_signed_B as a friend assembly.</span></span>  
  
     <span data-ttu-id="ad112-115">강력한 이름 도구는 실행할 때마다 새 공개 키를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-115">The Strong Name tool generates a new public key every time it runs.</span></span> <span data-ttu-id="ad112-116">따라서 다음 예제와 같이 다음 코드의 공개 키를 방금 생성한 공개 키로 대체해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-116">Therefore, you must replace the public key in the following code with the public key you just generated, as shown in the following example.</span></span>  
  
    ```vb  
    ' friend_signed_A.vb  
    ' Compile with:   
    ' Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
    Imports System.Runtime.CompilerServices  
  
    <Assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")>   
    Public Class Class1  
        Public Sub Test()  
            System.Console.WriteLine("Class1.Test")  
            System.Console.ReadLine()  
        End Sub  
    End Class  
    ```  
  
4. <span data-ttu-id="ad112-117">다음 명령을 사용하여 friend_signed_A를 컴파일하고 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-117">Compile and sign friend_signed_A by using the following command.</span></span>  
  
    ```console  
    Vbc -target:library -keyfile:FriendAssemblies.snk friend_signed_A.vb  
    ```  
  
5. <span data-ttu-id="ad112-118">라는 Visual Basic 파일을 만들 `friend_signed_B` 는 다음 코드가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-118">Create a Visual Basic file that is named `friend_signed_B` and contains the following code.</span></span> <span data-ttu-id="ad112-119">friend_signed_A는 friend_signed_B를 friend 어셈블리로 지정하기 때문에 friend_signed_B의 코드는 friend_signed_A의 `Friend` 형식과 멤버에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-119">Because friend_signed_A specifies friend_signed_B as a friend assembly, the code in friend_signed_B can access `Friend` types and members from friend_signed_A.</span></span> <span data-ttu-id="ad112-120">파일에는 다음 코드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-120">The file contains the following code.</span></span>  
  
    ```vb  
    ' friend_signed_B.vb  
    ' Compile with:   
    ' Vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    Module Sample  
        Public Sub Main()  
            Dim inst As New Class1  
            inst.Test()  
        End Sub  
    End Module  
    ```  
  
6. <span data-ttu-id="ad112-121">다음 명령을 사용하여 friend_signed_B를 컴파일하고 서명합니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-121">Compile and sign friend_signed_B by using the following command.</span></span>  
  
    ```console  
    vbc -keyfile:FriendAssemblies.snk -r:friend_signed_A.dll friend_signed_B.vb  
    ```  
  
     <span data-ttu-id="ad112-122">컴파일러에서 생성된 어셈블리 이름은 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성에 전달된 friend 어셈블리 이름과 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-122">The name of the assembly generated by the compiler must match the friend assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute.</span></span> <span data-ttu-id="ad112-123">사용 하 여 어셈블리를 명시적으로 설정할 수는 `-out` 컴파일러 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-123">You can explicitly set the assembly by using the `-out` compiler option.</span></span> <span data-ttu-id="ad112-124">자세한 내용은 [-(Visual Basic) out](../../../../visual-basic/reference/command-line-compiler/out.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-124">For more information, see [-out (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/out.md).</span></span>  
  
7. <span data-ttu-id="ad112-125">friend_signed_B.exe 파일을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-125">Run the friend_signed_B.exe file.</span></span>  
  
     <span data-ttu-id="ad112-126">프로그램에서 "Class1.Test" 문자열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-126">The program displays the string "Class1.Test".</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="ad112-127">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="ad112-127">.NET Framework Security</span></span>  
 <span data-ttu-id="ad112-128"><xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성과 <xref:System.Security.Permissions.StrongNameIdentityPermission> 클래스 간에는 유사점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-128">There are similarities between the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute and the <xref:System.Security.Permissions.StrongNameIdentityPermission> class.</span></span> <span data-ttu-id="ad112-129">주요 차이점은 <xref:System.Security.Permissions.StrongNameIdentityPermission>은 코드의 특정 섹션을 실행하는 보안 권한을 요구할 수 있는 반면, <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성은 `Friend` 형식 및 멤버의 표시 유형을 제어한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ad112-129">The main difference is that <xref:System.Security.Permissions.StrongNameIdentityPermission> can demand security permissions to run a particular section of code, whereas the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute controls the visibility of `Friend` types and members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad112-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="ad112-130">See also</span></span>

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [<span data-ttu-id="ad112-131">.NET 어셈블리</span><span class="sxs-lookup"><span data-stu-id="ad112-131">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
- [<span data-ttu-id="ad112-132">Friend 어셈블리</span><span class="sxs-lookup"><span data-stu-id="ad112-132">Friend Assemblies</span></span>](../../../../standard/assembly/friend-assemblies.md)
- [<span data-ttu-id="ad112-133">방법: 서명 되지 않은 Friend 어셈블리 (Visual Basic) 만들기</span><span class="sxs-lookup"><span data-stu-id="ad112-133">How to: Create Unsigned Friend Assemblies (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [<span data-ttu-id="ad112-134">-keyfile</span><span class="sxs-lookup"><span data-stu-id="ad112-134">-keyfile</span></span>](../../../../visual-basic/reference/command-line-compiler/keyfile.md)
- <span data-ttu-id="ad112-135">[Sn.exe (강력한 이름 도구)](../../../../framework/tools/sn-exe-strong-name-tool.md))</span><span class="sxs-lookup"><span data-stu-id="ad112-135">[Sn.exe (Strong Name Tool)](../../../../framework/tools/sn-exe-strong-name-tool.md))</span></span>
- [<span data-ttu-id="ad112-136">강력한 이름의 어셈블리 만들기 및 사용</span><span class="sxs-lookup"><span data-stu-id="ad112-136">Creating and Using Strong-Named Assemblies</span></span>](../../../../framework/app-domains/create-and-use-strong-named-assemblies.md)
- [<span data-ttu-id="ad112-137">프로그래밍 개념</span><span class="sxs-lookup"><span data-stu-id="ad112-137">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
