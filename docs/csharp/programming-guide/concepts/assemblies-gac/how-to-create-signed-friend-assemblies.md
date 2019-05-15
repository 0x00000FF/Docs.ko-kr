---
title: '방법: 서명된 Friend 어셈블리 만들기(C#)'
ms.date: 07/20/2015
ms.assetid: bab62063-61e6-453f-905f-77673df9534e
ms.openlocfilehash: df04f6f5a006c7eea7984004e20578c85e51efe0
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64582978"
---
# <a name="how-to-create-signed-friend-assemblies-c"></a>방법: 서명된 Friend 어셈블리 만들기(C#)
이 예제에서는 강력한 이름을 가진 어셈블리와 함께 friend 어셈블리를 사용하는 방법을 보여 줍니다. 두 어셈블리에 모두 강력한 이름을 지정해야 합니다. 이 예제의 두 어셈블리는 모두 동일한 키를 사용하지만 두 어셈블리에 서로 다른 키를 사용할 수 있습니다.  
  
### <a name="to-create-a-signed-assembly-and-a-friend-assembly"></a>서명된 어셈블리 및 friend 어셈블리를 만들려면  
  
1. 명령 프롬프트를 엽니다.  
  
2. 강력한 이름 도구와 함께 다음 명령 시퀀스를 사용하여 키 파일을 생성하고 해당 공개 키를 표시합니다. 자세한 내용은 [Sn.exe(강력한 이름 도구)](../../../../framework/tools/sn-exe-strong-name-tool.md)를 참조하세요.  
  
    1. 이 예제에 대한 강력한 이름 키를 생성하고 FriendAssemblies.snk 파일에 저장합니다.  
  
         `sn -k FriendAssemblies.snk`  
  
    2. FriendAssemblies.snk에서 공개 키를 추출하고 FriendAssemblies.publickey에 넣습니다.  
  
         `sn -p FriendAssemblies.snk FriendAssemblies.publickey`  
  
    3. FriendAssemblies.publickey 파일에 저장된 공개 키를 표시합니다.  
  
         `sn -tp FriendAssemblies.publickey`  
  
3. 다음 코드가 포함된 `friend_signed_A`라는 C# 파일을 만듭니다. 코드에서는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성을 사용하여 friend_signed_B를 friend 어셈블리로 선언합니다.  
  
     강력한 이름 도구는 실행할 때마다 새 공개 키를 생성합니다. 따라서 다음 예제와 같이 다음 코드의 공개 키를 방금 생성한 공개 키로 대체해야 합니다.  
  
    ```csharp  
    // friend_signed_A.cs  
    // Compile with:   
    // csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    using System.Runtime.CompilerServices;  
  
    [assembly: InternalsVisibleTo("friend_signed_B, PublicKey=0024000004800000940000000602000000240000525341310004000001000100e3aedce99b7e10823920206f8e46cd5558b4ec7345bd1a5b201ffe71660625dcb8f9a08687d881c8f65a0dcf042f81475d2e88f3e3e273c8311ee40f952db306c02fbfc5d8bc6ee1e924e6ec8fe8c01932e0648a0d3e5695134af3bb7fab370d3012d083fa6b83179dd3d031053f72fc1f7da8459140b0af5afc4d2804deccb6")]  
    class Class1  
    {  
        public void Test()  
        {  
            System.Console.WriteLine("Class1.Test");  
            System.Console.ReadLine();  
        }  
    }  
    ```  
  
4. 다음 명령을 사용하여 friend_signed_A를 컴파일하고 서명합니다.  
  
    ```csharp  
    csc /target:library /keyfile:FriendAssemblies.snk friend_signed_A.cs  
    ```  
  
5. 다음 코드가 포함된 `friend_signed_B`라는 C# 파일을 만듭니다. friend_signed_A는 friend_signed_B를 friend 어셈블리로 지정하기 때문에 friend_signed_B의 코드는 friend_signed_A의 `internal` 형식과 멤버에 액세스할 수 있습니다. 파일에는 다음 코드가 포함되어 있습니다.  
  
    ```csharp  
    // friend_signed_B.cs  
    // Compile with:   
    // csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    public class Program  
    {  
        static void Main()  
        {  
            Class1 inst = new Class1();  
            inst.Test();  
        }  
    }  
    ```  
  
6. 다음 명령을 사용하여 friend_signed_B를 컴파일하고 서명합니다.  
  
    ```csharp  
    csc /keyfile:FriendAssemblies.snk /r:friend_signed_A.dll /out:friend_signed_B.exe friend_signed_B.cs  
    ```  
  
     컴파일러에서 생성된 어셈블리 이름은 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성에 전달된 friend 어셈블리 이름과 일치해야 합니다. `/out` 컴파일러 옵션을 사용하여 출력 어셈블리(.exe 또는 .dll)의 이름을 명시적으로 지정해야 합니다.  자세한 내용은 [/out(C# 컴파일러 옵션)](../../../../csharp/language-reference/compiler-options/out-compiler-option.md)을 참조하세요.  
  
7. friend_signed_B.exe 파일을 실행합니다.  
  
     프로그램에서 "Class1.Test" 문자열을 인쇄합니다.  
  
## <a name="net-framework-security"></a>.NET Framework 보안  
 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성과 <xref:System.Security.Permissions.StrongNameIdentityPermission> 클래스 간에는 유사점이 있습니다. 주요 차이점은 <xref:System.Security.Permissions.StrongNameIdentityPermission>은 코드의 특정 섹션을 실행하는 보안 권한을 요구할 수 있는 반면, <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성은 `internal` 형식 및 멤버의 표시 유형을 제어한다는 것입니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute>
- [.NET 어셈블리](../../../../standard/assembly/index.md)
- [Friend 어셈블리](../../../../standard/assembly/friend-assemblies.md)
- [방법: 서명되지 않은 Friend 어셈블리 만들기(C#)](../../../../csharp/programming-guide/concepts/assemblies-gac/how-to-create-unsigned-friend-assemblies.md)
- [/keyfile](../../../../csharp/language-reference/compiler-options/keyfile-compiler-option.md)
- [Sn.exe(강력한 이름 도구)](../../../../framework/tools/sn-exe-strong-name-tool.md)
- [강력한 이름의 어셈블리 만들기 및 사용](../../../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)
- [C# 프로그래밍 가이드](../../../../csharp/programming-guide/index.md)
