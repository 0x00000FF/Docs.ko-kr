---
title: dotnet vstest로 게시된 출력 테스트
description: dotnet vstest 명령을 사용하여 소스 코드 대신, 게시된 라이브러리에 대해 테스트를 실행하는 방법을 알아봅니다.
author: kendrahavens
ms.author: kehavens
ms.date: 10/18/2017
ms.custom: seodec18
ms.openlocfilehash: 9d842f26336d0ddf5375d49676523086bb632684
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/11/2018
ms.locfileid: "53239529"
---
# <a name="test-published-output-with-dotnet-vstest"></a>dotnet vstest로 게시된 출력 테스트

`dotnet vstest` 명령을 사용하여 이미 게시된 출력에 대해 테스트를 실행할 수 있습니다. 이는 xUnit, MSTest 및 NUnit 테스트에서 작동합니다. 게시된 출력의 일부인 DLL 파일을 찾아 실행하기만 하면 됩니다.

```
dotnet vstest <MyPublishedTests>.dll
```

여기서 `<MyPublishedTests>`는 게시된 테스트 프로젝트의 이름입니다.

## <a name="example"></a>예제

아래 명령은 게시된 DLL에서 실행 중인 테스트를 보여 줍니다.

```
dotnet new mstest -o MyProject.Tests
cd MyProject.Tests
dotnet publish -o out
dotnet vstest out/MyProject.Tests.dll
```

> [!NOTE]
> 참고: 앱이 `netcoreapp` 이외의 프레임워크를 대상으로 하는 경우 프레임워크 플래그를 사용하여 대상 프레임워크를 전달함으로써 `dotnet vstest` 명령을 계속 실행할 수 있습니다. 예를 들어 `dotnet vstest <MyPublishedTests>.dll  --Framework:".NETFramework,Version=v4.6"`과 같은 형식입니다. Visual Studio 2017 업데이트 5에서는 필요한 프레임워크가 자동으로 검색됩니다.

## <a name="see-also"></a>참고 항목
- [dotnet 테스트 및 xUnit을 사용한 단위 테스트](unit-testing-with-dotnet-test.md)
- [dotnet 테스트 및 NUnit을 사용한 단위 테스트](unit-testing-with-nunit.md)
- [dotnet 테스트 및 MSTest를 사용한 단위 테스트](unit-testing-with-mstest.md)
