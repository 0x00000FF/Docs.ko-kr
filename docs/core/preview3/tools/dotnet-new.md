---
title: "dotnet-new 명령 | Microsoft 문서"
description: "dotnet-new 명령은 현재 디렉터리에 새 .NET Core 프로젝트를 만듭니다."
keywords: "dotnet-new, CLI, CLI 명령, .NET Core"
author: blackdwarf
ms.author: mairaw
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: fcc3ed2e-9265-4d50-b59e-dc2e5c190b34
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: d4ca76f3de38b5d05868292d5c4bb8e3b0c7fdf2

---

#<a name="dotnet-new-tooling-preview-4"></a>dotnet-new(Tooling Preview 4)

> [!WARNING]
> 이 항목은 Visual Studio 2017 RC - .NET Core Tools Preview 4에 적용됩니다. .NET Core Tools Preview 2 버전의 경우 [dotnet-new](../../tools/dotnet-new.md) 항목을 참조하세요.

## <a name="name"></a>이름
dotnet-new -- 현재 디렉터리에 새 .NET Core 프로젝트를 만듭니다.

## <a name="synopsis"></a>개요
`dotnet new [--help] [--type] [--lang]`

## <a name="description"></a>설명
`dotnet new` 명령은 CLI(명령줄 인터페이스) 도구 집합을 사용해 보기 위해 유효한 .NET Core 프로젝트 및 샘플 소스 코드를 초기화하는 편리한 방법을 제공합니다. 

이 명령은 디렉터리의 컨텍스트에서 호출됩니다. 이 명령은 호출되면 두 가지 주요 아티팩트를 현재 디렉터리로 끌어 옵니다. 

1. 샘플 "Hello World" 프로그램을 포함하는 `Program.cs`(또는 `Program.fs`) 파일
2. 유효한 csproj 프로젝트 파일입니다.

그런 다음 프로젝트를 추가로 컴파일하거나 편집할 수 있습니다. 

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.  

`-l|--lang C#`

프로젝트의 언어입니다. 기본값은 `C#`입니다. 다른 유효한 값은 `csharp` 및 `cs`입니다.

`-t|--type`

프로젝트의 형식입니다. C#에 유효한 값은 `console`, `web`, `lib` 및 `xunittest`이고 F#의 경우 `console`만 유효합니다. 

## <a name="examples"></a>예제

현재 디렉터리에 C# 콘솔 응용 프로그램 프로젝트를 만듭니다.

`dotnet new` 또는 `dotnet new --lang c#` 
   
현재 디렉터리에 새 ASP.NET Core C# 응용 프로그램 프로젝트를 만듭니다.

`dotnet new -t web`


<!--HONumber=Jan17_HO3-->


