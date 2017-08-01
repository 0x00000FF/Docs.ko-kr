---
title: "dotnet-add package 명령 - .NET Core CLI"
description: "dotnet-add package 명령은 NuGet 패키지 참조를 프로젝트에 추가하는 편리한 옵션을 제공합니다."
keywords: "dotnet-add, CLI, CLI 명령, .NET Core"
author: spboyer
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 88e0da69-a5ea-46cc-8b46-5493242b7af9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 40ee7cac969d4752ede66ba8df6ff6cb3f439aec
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-add-package"></a>dotnet-add package

## <a name="name"></a>이름

`dotnet-add package` - 패키지 참조를 프로젝트 파일에 추가합니다.

## <a name="synopsis"></a>개요

`dotnet add [<PROJECT>] package <PACKAGE_NAME> [-v|--version] [-f|--framework] [-n|--no-restore] [-s|--source] [--package-directory] [-h|--help]`

## <a name="description"></a>설명

`dotnet add package` 명령은 패키지 참조를 프로젝트 파일에 추가하는 편리한 옵션을 제공합니다. 명령을 실행한 후 패키지가 프로젝트의 프레임워크와 호환되는지 확인하는 호환성 검사가 있습니다. 검사를 통과하면 `<PackageReference>` 요소가 프로젝트 파일에 추가되고 [dotnet restore](dotnet-restore.md)가 실행됩니다.

예를 들어 `Newtonsoft.Json`를 *ToDo.csproj*에 추가하면 다음과 유사한 출력이 생성됩니다.

```
Microsoft (R) Build Engine version 15.1.545.13942
Copyright (C) Microsoft Corporation. All rights reserved.

Writing /var/folders/gj/1mgg_4jx7mbdqbhw1kgcpcjr0000gn/T/tmpm0kTMD.tmp
info : Adding PackageReference for package 'Newtonsoft.Json' into project 'ToDo.csproj'.
log  : Restoring packages for ToDo.csproj...
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/index.json 119ms
info :   GET https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg
info :   OK https://api.nuget.org/v3-flatcontainer/newtonsoft.json/9.0.1/newtonsoft.json.9.0.1.nupkg 27ms
info : Package 'Newtonsoft.Json' is compatible with all the specified frameworks in project 'ToDo.csproj'.
info : PackageReference for package 'Newtonsoft.Json' version '9.0.1' added to file 'ToDo.csproj'.
```

이제 *ToDo.csproj* 파일에 참조되는 패키지에 대한 [`<PackageReference>`](/nuget/consume-packages/package-references-in-project-files) 요소가 포함됩니다.

```xml
<PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
```

## <a name="arguments"></a>인수

`PROJECT`

프로젝트 파일을 지정합니다. 지정하지 않으면 이 명령은 현재 디렉터리에서 검색합니다.

`PACKAGE_NAME`

추가할 패키지 참조입니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

`-v|--version <VERSION>`

패키지의 버전입니다.

`-f|--framework <FRAMEWORK>`

특정 [프레임워크](../../standard/frameworks.md)를 대상으로 하는 경우에만 패키지 참조를 추가합니다.

`-n|--no-restore`

복원 미리 보기 및 호환성 검사를 수행하지 않고 패키지 참조를 추가합니다.

`-s|--source <SOURCE>`

복원 작업 중 특정 NuGet 패키지 소스를 사용합니다.

`--package-directory <PACKAGE_DIRECTORY>`

지정된 디렉터리에 패키지를 복원합니다.

## <a name="examples"></a>예제

`Newtonsoft.Json` NuGet 패키지를 프로젝트에 추가합니다.

`dotnet add package Newtonsoft.Json`

특정 버전의 패키지를 프로젝트에 추가합니다.

`dotnet add ToDo.csproj package Microsoft.Azure.DocumentDB.Core -v 1.0.0`

특정 NuGet 소스를 사용하여 패키지를 추가합니다.

`dotnet add package Microsoft.AspNetCore.StaticFiles -s https://dotnet.myget.org/F/dotnet-core/api/v3/index.json`

