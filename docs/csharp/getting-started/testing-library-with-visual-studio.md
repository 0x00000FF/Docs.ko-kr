---
title: "Visual Studio 2017에서 .NET Core로 클래스 라이브러리 테스트"
description: "Visual Studio 2017을 사용하여 C#으로 작성된 클래스 라이브러리를 테스트하는 방법 알아보기"
keywords: ".NET Core, .NET 표준 클래스 라이브러리, Visual Studio 2017, 단위 테스트"
author: stevehoag
ms.author: shoag
ms.date: 11/16/2016
ms.topic: article
ms.prod: .net-core
ms.technology: devlang-csharp
ms.devlang: csharp
ms.assetid: 069ad711-3eaa-45c6-94d7-b40249cc8b99
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: ee21799706b971f0ec13285b0771b32b4367f570
ms.lasthandoff: 03/13/2017

---

# <a name="testing-a-class-library-with-net-core-in-visual-studio-2017"></a>Visual Studio 2017에서 .NET Core로 클래스 라이브러리 테스트 #

[Visual Studio 2017에서 C# 및 .NET Core를 사용하여 클래스 라이브러리 빌드](library-with-visual-studio-2017.md)에서는 @System.String 클래스에 확장 메서드를 추가하는 간단한 클래스 라이브러리를 만들었습니다. 이제 예상대로 작동하는지 확인하기 위한 단위 테스트를 만들어 보겠습니다. 이전 항목에서 만든 솔루션에 단위 테스트 프로젝트를 추가할 것입니다.

## <a name="creating-a-unit-test-project"></a>단위 테스트 프로젝트 만들기 ##

단위 테스트 프로젝트를 만들려면 다음을 수행합니다.

1. 솔루션 탐색기에서 **ClassLibraryProject** 솔루션 노드의 상황에 맞는 메뉴를 열고 **추가**, **새 프로젝트**를 차례로 선택합니다.

   <!-- Need a VS 2017 version  [!NOTE] In addition to a Unit Test project, you can also use Visual Studio to create an XUnit test project for .NET Core. For a walkthrough that includes an XUnit test project, see [Getting started with .NET Core on Windows, using Visual Studio 2015](../../core/tutorials/using-on-windows.md). --> 

1. 다음 그림과 같이 **새 프로젝트 추가** 대화 상자에서 **Visual C#** 노드 및 **.NET Core** 노드를 확장하고 **단위 테스트 프로젝트(.NET Core)** 프로젝트 템플릿을 선택한 다음 `StringLibraryTest`라고 이름을 지정합니다.

   ![이미지](./media/testproject.jpg)

1. **확인** 단추를 선택하여 프로젝트를 만듭니다. Visual Studio에서는 해당 프로젝트를 만들고 다음 그림과 같이 코드 창에서 `UnitTest1.cs` 파일을 엽니다.

   ![이미지](./media/unit_test_code_window.jpg)

   단위 테스트 템플릿을 통해 만들어진 소스 코드는 다음을 수행합니다.

   - 단위 테스트에 사용되는 형식이 포함되어 있는 [Microsoft.VisualStudio.TestTools.UnitTesting](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.aspx) 네임스페이스를 가져옵니다.

   - [ \[TestClass\] ](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testclassattribute.aspx) 특성을 `UnitTest1` 클래스에 적용합니다. \[TestMethod\] 특성으로 태그가 지정된 테스트 클래스의 각 테스트 메서드는 단위 테스트가 실행될 때 자동으로 실행됩니다.

   - [\[TestMethod\] 특성을 적용하여 ](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testmethodattribute.aspx) `TestMethod1`을 단위 테스트가 실행할 때 자동으로 실행되는 테스트 메서드로 정의합니다.

1. 솔루션 탐색기에서 **StringLibraryTest** 프로젝트의 **종속성** 노드의 상황에 맞는 메뉴를 열고 **참조 추가**를 선택합니다. 그러면 클래스 라이브러리 프로젝트 `StringLibrary`에 대한 참조가 추가됩니다. 

1. 다음과 같이 **참조 관리자** 대화 상자에서 **프로젝트** 노드를 확장하고 **솔루션**을 선택한 후 **StringLibrary** 옆의 확인란을 선택합니다. `StringLibrary` 어셈블리에 대한 참조를 추가하면 컴파일러가 **StringLibrary** 메서드에 대한 호출을 확인할 수 있습니다.

   ![이미지](./media/add_reference.jpg)

1. **확인** 단추를 클릭하여 **참조 관리자** 대화 상자를 닫습니다.

## <a name="adding-and-running-unit-test-methods"></a>단위 테스트 메서드 추가 및 실행 ##

Visual Studio는 단위 테스트를 실행할 때 단위 테스트 클래스([\[TestClass\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testclassattribute.aspx) 특성이 적용된 클래스)에서 [\[TestMethod\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.testmethodattribute.aspx) 특성으로 표시된 각 메서드를 실행합니다. 테스트 메서드는 첫 번째 오류가 발생하거나 메서드에 포함된 모든 테스트가 성공적으로 수행되면 종료됩니다.

가장 일반적인 테스트는 [Assert](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.assert.aspx) 클래스의 멤버를 호출합니다. 많은 어설션 메서드에는 2개 이상의 매개 변수가 포함되며, 그 중 하나는 예상된 테스트 결과이고, 다른 하나는 실제 테스트 결과입니다. 가장 자주 호출되는 일부 메서드는 다음과 같습니다.

- `Assert.AreEqual`: 두 개의 값이나 개체가 같은지를 확인합니다. 값이나 개체가 같지 않으면 어설션이 실패합니다.

- `Assert.AreSame`: 두 개의 개체 변수가 같은 개체를 참조하는지를 확인합니다. 변수가 서로 다른 개체를 참조하면 어설션이 실패합니다.

- `Assert.IsFalse`: 조건이 False인지를 확인합니다. 조건이 True이면 어설션이 실패합니다.

- `Assert.IsNotNull`: 개체가 `null`이 아닌지를 확인합니다. 개체가 `null`이면 어설션이 실패합니다.

또한 [\[ExpectedException\]](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.expectedexceptionattribute.aspx) 특성을 사용하여 테스트 메서드가 throw할 것으로 예상되는 예외 유형을 나타낼 수 있습니다. 이를 예외를 발생하는 조건을 테스트하는 데 사용할 수 있습니다. 지정된 예외가 throw되지 않으면 테스트가 실패한 것입니다.

`StringLibrary.StartsWithUpper` 메서드를 테스트할 때 대문자로 시작하는 많은 문자열을 제공하려고 합니다. 이러한 경우에 메서드가 `True`를 반환할 것으로 기대하므로 [Assert.IsTrue(Boolean, String)](https://msdn.microsoft.com/library/ms243754.aspx) 메서드를 호출할 수 있습니다. 마찬가지로 대문자 이외의 문자로 시작하는 많은 문자열을 제공하려고 합니다. 이러한 경우에 메서드가 False를 반환할 것으로 기대하므로 [Assert.IsFalse(Boolean, String)](https://msdn.microsoft.com/library/ms243805.aspx) 메서드를 호출할 수 있습니다.

또한 라이브러리가 문자열을 처리하므로 [빈 문자열](xref:System.String.Empty)(문자가 없고 해당 @System.String.Length가 0인 유효한 문자열) 및 `null` 문자열(초기화되지 않은 문자열)을 성공적으로 처리하는지 확인하려고 합니다. `StartsWithUpper`가 @System.String 인스턴스에 대한 확장 메서드로 호출될 경우 `null` 문자열이 제공될 수 없습니다. 그러나 정적 메서드로 직접 호출된 후 단일 @System.String 인수로 전달될 수도 있습니다.

각각이 문자열 배열의 각 요소에 대해 [Assert](https://msdn.microsoft.com/library/microsoft.visualstudio.testtools.unittesting.assert.aspx) 메서드를 반복적으로 호출하는 3가지 메서드를 정의해 보겠습니다. 첫 번째 오류가 발생하는 즉시 테스트 메서드가 실패하기 때문에 메서드 호출에 사용되는 문자열 값을 나타내는 문자열을 전달할 수 있도록 하는 메서드 오버로드를 호출합니다.

테스트 메서드를 만들려면

1. 코드 창의 코드를 다음 코드로 바꿉니다.

   [!CODE-csharp[Test#1](../../../samples/snippets/csharp/getting_started/with_visual_studio_2017/testlib1.cs#1)]

   `TestStartsWithUpper` 메서드의 대문자 테스트는 그리스어 대문자 알파(U+0391) 및 키릴 자모 대문자 EM(U+041C)을 포함하고, `TestDoesNotStartWithUpper` 메서드의 소문자의 테스트는 그리스어 소문자 알파(U+03B1) 및 키릴 자모 소문자 Ghe(U+0433)를 포함합니다.

1. 메뉴 모음에서 **파일**, **다른 이름으로 UnitTest1.cs 저장...**을 차례로 선택합니다. **다른 이름으로 파일 저장** 대화 상자에서 **저장** 단추 옆에 있는 화살표를 선택한 다음 **인코딩하여 저장...***을 선택합니다.

1. 다른 이름으로 저장 확인 대화 상자에서 **예** 단추를 선택하여 파일을 저장합니다.

1. **고급 저장 옵션** 대화 상자의 **인코딩** 드롭다운 목록에서 **유니코드(서명 있는 UTF-8) - 코드 페이지 65001**을 선택한 다음 **확인**을 선택합니다.

   소스 코드를 UTF8로 인코딩된 파일에 저장하지 못하면 Visual Studio에서 해당 파일이 ASCII 파일로 저장될 수 있습니다. 이 경우 런타임은 ASCII 범위 밖의 문자를 정확히 디코딩하지 않으며 테스트 결과는 정확하지 않게 됩니다.

1. 메뉴 모음에서 **테스트**, **실행**, **모든 테스트**를 선택합니다. 다음 그림과 같이 **테스트 탐색기** 창이 열리고 두 테스트가 모두 성공적으로 실행되었음을 보여 줍니다. 세 가지 테스트가 **통과한 테스트** 섹션에 표시되고 **요약** 섹션이 테스트 실행의 결과를 보고합니다.

   ![이미지](./media/first_test.jpg)

## <a name="handling-test-failures"></a>테스트 오류 처리 ##

테스트를 실행할 때 오류가 발생하지 않았으므로 테스트 메서드 중 하나가 실패하도록 약간 변경해 보겠습니다.

1. `TestDoesNotStartWithUpper` 메서드의 `words` 배열이 "Error" 문자열을 포함하도록 수정합니다. 그러면 문은 다음과 같이 표시됩니다.

   ```csharp
   string[] words = { "alphabet", "Error", "zebra", "abc", "αυτοκινητοβιομηχανία", "государство",
                      "1234", ".", ";", " " };
   ```

1. **테스트**, **실행**, **모든 테스트**를 선택하여 테스트를 실행합니다. 이제 **테스트 탐색기** 창에는 다음 그림과 같이 두 가지 테스트는 성공하고 한 가지 테스트는 실패한 것으로 나타납니다.

   ![이미지](./media/failed_test.jpg)

1. **실패한 테스트** 섹션에서 실패한 테스트 `TestDoesNotStartWith`를 선택합니다. **테스트 탐색기**의 아래쪽 창에는 어설션이 생성하는 메시지 "Assert.IsFalse가 실패했습니다. 'Error': false; actual: True가 필요합니다."가 표시됩니다. 이 내용은 다음 **테스트 탐색기** 그림에 나와 있습니다. 이 오류 때문에 "Error" 다음에 나오는 배열의 모든 문자열이 테스트되지는 않았습니다.

   ![이미지](./media/failed_test2.jpg)

1. 추가된 코드(`"Error", `)를 제거하고 테스트를 다시 실행합니다. 이제 통과됩니다.

## <a name="testing-the-release-version-of-the-library"></a>라이브러리의 릴리스 버전 테스트 ##

지금까지 라이브러리의 디버그 버전에 대한 테스트를 실행했습니다. 테스트가 모두 통과되고 라이브러리를 적절히 테스트했으므로 추가 시간 동안 라이브러리의 릴리스 빌드에 테스트를 실행해야 합니다. 컴파일러 최적화를 비롯한 여러 가지 요인 때문에 디버그 및 릴리스 빌드 간에 서로 다른 동작이 발생할 수도 있습니다.

릴리스 빌드를 테스트하려면

1. Visual Studio 도구 모음에서 빌드 구성을 **디버그**에서 **릴리스**로 변경합니다. 다음 그림은 도구 모음의 일부를 보여 줍니다.

   ![이미지](./media/lib_release.jpg)

1. **솔루션 탐색기**에서 **StringLibrary** 프로젝트 노드에 대한 , 상황에 맞는 메뉴를 열고 **빌드**를 선택하여 라이브러리를 다시 컴파일합니다.

1. Visual Studio 메뉴에서 **테스트**, **실행**, **모든 테스트**를 선택하여 단위 테스트를 다시 실행합니다. 테스트가 모두 통과되어야 합니다.

라이브러리에 테스트를 마쳤으므로 다음 단계는 호출자가 사용할 수 있도록 하는 것입니다. 하나 이상의 응용 프로그램과 함께 번들로 묶거나 NuGet 패키지로 배포할 수 있습니다. 이 작업을 수행하는 방법에 대한 자세한 내용은 [.NET 표준 클래스 라이브러리 사용](./consuming-library-with-visual-studio-2017.md)을 참조하세요.

