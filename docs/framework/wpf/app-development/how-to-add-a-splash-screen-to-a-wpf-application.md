---
title: '방법: WPF 응용 프로그램에 시작 화면 추가하기'
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 46efa041736870c5c0f08baa321ef0dc53cacc0d
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43502756"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a>방법: WPF 응용 프로그램에 시작 화면 추가하기

이 항목에서는 시작 창 또는 *시작 화면*을 Windows Presentation Foundation(WPF) 응용 프로그램에 추가하는 방법을 소개합니다.

## <a name="to-add-an-existing-image-as-a-splash-screen"></a>기존 이미지를 시작 화면으로 추가하려면

1.  시작 화면으로 사용하려는 이미지를 찾거나 만듭니다. Windows Imaging 구성 요소(WIC)에서 지원되는 모든 이미지 형식을 사용할 수 있습니다. 예를 들어, BMP, GIF, JPEG, PNG 또는 TIFF 형식으로 사용할 수 있습니다.

2.  WPF 응용 프로그램 프로젝트에 해당 이미지 파일을 추가합니다.

3.  **솔루션 탐색기**에서 이미지를 선택합니다.

4.  속성 창에서 **빌드 작업** 속성의 드롭다운 화살표를 클릭합니다.

5.  드롭 다운 목록에서 **SplashScreen**을 선택합니다.

6.  **F5** 키를 눌러 응용 프로그램을 빌드하고 실행합니다.

     시작 화면 이미지가 화면 중앙에 나타난 다음 메인 응용 프로그램 창이 나타나면 사라집니다.

## <a name="to-exclude-the-splash-screen-from-build"></a>빌드에서 시작 화면을 제외하려면

1.  **솔루션 탐색기**에서 시작 화면 이미지를 선택합니다.

2.  **속성** 창에서 **빌드 작업**을 **None**으로 설정합니다.

## <a name="to-remove-the-splash-screen-from-an-application"></a>응용 프로그램에서 시작 화면을 제거 하려면

**솔루션 탐색기**에서 시작 화면 이미지를 삭제합니다.

## <a name="see-also"></a>참고 항목

- <xref:System.Windows.SplashScreen>
- [방법: 프로젝트에 기존 항목 추가](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))
