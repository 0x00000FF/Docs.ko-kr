---
title: "dotnet-add reference 명령 - .NET Core CLI"
description: "dotnet add reference 명령은 프로젝트 간 참조를 추가하는 편리한 옵션을 제공합니다."
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 18e3ce22c1b9a4506b2690262d8d0c4e13a58ed1
ms.contentlocale: ko-kr
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-add-reference"></a>dotnet-add reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>이름

`dotnet add reference` - 프로젝트 간(P2P) 참조를 추가합니다.

## <a name="synopsis"></a>개요

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>설명

`dotnet add reference` 명령은 프로젝트에 프로젝트 참조를 추가하는 편리한 옵션을 제공합니다. 명령을 실행한 후 [ `<ProjectReference>` ](/visualstudio/msbuild/common-msbuild-project-items) 요소가 프로젝트 파일에 추가됩니다.

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a>인수

`PROJECT`

프로젝트 파일을 지정합니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 솔루션 파일을 하나 검색합니다.

`PROJECT_REFERENCES`

추가할 프로젝트 간(P2P) 참조입니다. 하나 이상의 프로젝트를 지정합니다. Unix/Linux 기반 시스템에서는 [와일드카드 사용 패턴](https://en.wikipedia.org/wiki/Glob_(programming))이 지원됩니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

`-f|--framework <FRAMEWORK>`

특정 [프레임워크](../../standard/frameworks.md)를 대상으로 하는 경우에만 프로젝트 참조를 추가합니다.

## <a name="examples"></a>예제

프로젝트 참조 추가:

`dotnet add app/app.csproj reference lib/lib.csproj`

여러 프로젝트 참조 추가:

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

Linux/Unix에서 와일드카드 사용 패턴을 사용하여 여러 프로젝트 참조 추가:

`dotnet add app/app.csproj reference **/*.csproj`
