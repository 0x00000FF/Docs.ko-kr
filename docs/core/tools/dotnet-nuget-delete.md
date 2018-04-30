---
title: dotnet nuget delete 명령 - .NET Core CLI
description: dotnet-nuget-delete 명령은 서버에서 패키지를 삭제하거나 목록에서 제거합니다.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 1e81501d526ae92336b808f98c7c192b55e89f98
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-nuget-delete"></a>dotnet nuget delete

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet nuget delete` - 서버에서 패키지를 삭제하거나 목록에서 제거합니다.

## <a name="synopsis"></a>개요

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a>설명

`dotnet nuget delete` 명령은 패키지를 삭제하거나 목록에서 제거합니다. [nuget.org](https://www.nuget.org/)의 경우 작업을 통해 패키지가 목록에서 제거됩니다.

## <a name="arguments"></a>인수

`PACKAGE_NAME`

삭제할 패키지입니다.

`PACKAGE_VERSION`

삭제할 패키지의 버전입니다.

## <a name="options"></a>옵션

`-h|--help`

명령에 대한 간단한 도움말을 출력합니다.

`-s|--source <SOURCE>`

서버 URL을 지정합니다. nuget.org에 대해 지원되는 URL에는 `http://www.nuget.org`, `http://www.nuget.org/api/v3` 및 `http://www.nuget.org/api/v2/package`가 포함됩니다. 개인용 피드의 경우 호스트 이름(예: `%hostname%/api/v3`)을 대체합니다.

`--non-interactive`

사용자 입력 또는 확인에 대한 메시지를 표시하지 않습니다.

`-k|--api-key <API_KEY>`

서버에 대한 API 키입니다.

`--force-english-output`

명령줄 출력이 영어로 강제로 표시됩니다.

## <a name="examples"></a>예제

`Microsoft.AspNetCore.Mvc` 패키지 버전 1.0을 삭제합니다.

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

사용자에게 자격 증명 또는 기타 입력을 위한 메시지를 표시하지 않고 `Microsoft.AspNetCore.Mvc` 패키지 버전 1.0을 삭제합니다.

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`