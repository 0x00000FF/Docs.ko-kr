---
title: "Visual Studio for Mac을 사용하여 macOS에서 .NET Core 시작 | Microsoft Docs"
description: "이 항목에서는 Mac 및 .NET Core용 Visual Studio를 사용하여 간단한 콘솔 응용 프로그램을 빌드하는 과정을 안내합니다."
keywords: .NET, .NET Core, macOS, Mac
author: guardrex
ms.author: mairaw
ms.date: 06/12/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: 8902e849-dd17-42c0-8264-cc7ae3927a0c
ms.translationtype: Human Translation
ms.sourcegitcommit: 83200e452bccc20bfa82d94899514019e9d05a23
ms.openlocfilehash: c377d0669efed9abb50965652d286ceb6fad3299
ms.contentlocale: ko-kr
ms.lasthandoff: 07/05/2017

---

<a id="getting-started-with-net-core-on-macos-using-visual-studio-for-mac" class="xliff"></a>

# Visual Studio for Mac을 사용하여 macOS에서 .NET Core 시작

Visual Studio for Mac은 .NET Core 응용 프로그램 개발을 위해 필요한 전기능 IDE(통합 개발 환경)를 제공합니다. 이 항목에서는 Mac 및 .NET Core용 Visual Studio를 사용하여 간단한 콘솔 응용 프로그램을 빌드하는 과정을 안내합니다.

> [!NOTE]
> Visual Studio for Mac은 미리 보기 소프트웨어입니다. 모든 미리 보기 버전의 Microsoft 제품과 마찬가지로 사용자의 의견은 매우 중요합니다. 두 가지가 Visual Studio for Mac의 개발 팀에 다음 두 가지 방법으로 의견을 제공할 수 있습니다.
> * Visual Studio for Mac의 메뉴에서 **도움말 > 문제 보고**를 선택하거나 시작 화면에서 **문제 보고**를 선택하면 버그 보고서를 작성하기 위한 창이 열립니다.
> * 제안을 하려면 메뉴에서 **도움말 > 제안하기**를 선택하거나 시작 화면에서 **제안 하기**를 선택합니다. 그러면 [Visual Studio for Mac UserVoice 웹 페이지](https://visualstudio.uservoice.com/forums/563332-visual-studio-for-mac)로 이동됩니다.

<a id="prerequisites" class="xliff"></a>

## 필수 조건

필수 구성 요소에 대한 자세한 내용은 [Mac의 .NET Core에 대한 필수 구성 요소](../../core/macos-prerequisites.md)를 참조하세요.

<a id="getting-started" class="xliff"></a>

## 시작

필수 구성 요소와 Visual Studio for Mac을 이미 설치한 경우 이 섹션을 건너뛰고 [프로젝트 만들기](#creating-a-project)를 계속 진행합니다. 다음 단계에 따라 필수 구성 요소 및 Visual Studio for Mac을 설치합니다.

[Visual Studio for Mac 설치 관리자](https://www.visualstudio.com/vs/visual-studio-mac/)를 다운로드합니다. 설치 관리자를 실행합니다. 사용권 계약을 읽은 다음 동의합니다. 설치하는 동안 플랫폼 간 모바일 앱 개발 기술인 Xamarin을 설치할 기회가 제공됩니다. Xamarin 및 관련된 구성 요소의 설치는 .NET Core 개발에서 선택 사항입니다. Visual Studio for Mac 설치 프로세스에 대한 연습을 진행하려면 [Visual Studio for Mac 소개](https://developer.xamarin.com/guides/cross-platform/visual-studio-mac/)를 참조하세요. 설치가 완료되면 Visual Studio for Mac IDE를 시작합니다.

<a id="creating-a-project" class="xliff"></a>

## 프로젝트 만들기

1. 시작 화면에서 **새 프로젝트**를 선택합니다.

   ![Visual Studio for Mac 시작 화면의 새 프로젝트 단추](./media/using-on-mac-vs/vsmac1.png)

1. **새 프로젝트** 대화 상자에서 **.NET Core** 노드 아래에서 **앱**을 선택합니다. **콘솔 응용 프로그램** 템플릿을 선택하고 **다음**을 선택합니다.

   ![새 프로젝트 템플릿 목록](./media/using-on-mac-vs/vsmac2.png)

1. **프로젝트 이름**으로 "HelloWorld"를 입력합니다. **만들기**를 선택합니다.

   ![새 콘솔 응용 프로그램 대화 상자 구성](./media/using-on-mac-vs/vsmac3.png)

1. 프로젝트의 종속성이 복원되는 동안 기다립니다. 프로젝트에는 `Main` 메서드가 있는 `Program` 클래스를 포함하는 C# 파일 *Program.cs*가 있습니다. 앱이 실행되면 `Console.WriteLine` 문은 "Hello World!"를 콘솔에 출력합니다.

   ![Program.cs 파일이 열려 있는 주 창](./media/using-on-mac-vs/vsmac4.png)

<a id="run-the-application" class="xliff"></a>

## 응용 프로그램 실행

<kbd>F5</kbd> 키를 사용하여 디버그 모드에서 또는 <kbd>Ctrl</kbd>+<kbd>F5</kbd>를 사용하여 릴리스 모드에서 이 앱을 실행합니다.

![응용 프로그램 출력 창에 Hello World!가 표시됩니다.](./media/using-on-mac-vs/vsmac5.png)

<a id="next-step" class="xliff"></a>

## 다음 단계

[Visual Studio for Mac을 사용하여 macOS에서 완전한 .NET Core 솔루션 빌드](using-on-mac-vs-full-solution.md) 항목에서는 재사용 가능한 라이브러리 및 단위 테스트를 포함하는 전체 .NET Core 솔루션을 빌드하는 방법을 보여 줍니다.

