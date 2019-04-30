---
title: ColorDialog 구성 요소 개요(Windows Forms)
ms.date: 03/30/2017
f1_keywords:
- ColorDialog
helpviewer_keywords:
- color dialog box [Windows Forms], about color dialog box
- ColorDialog component [Windows Forms], about ColorDialog
ms.assetid: 6dbdd8f0-f697-4728-bb09-7ea156f6d800
ms.openlocfilehash: 284d42218fb4fbce873325b1e45c883d51eefab8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61956340"
---
# <a name="colordialog-component-overview-windows-forms"></a><span data-ttu-id="4d40c-102">ColorDialog 구성 요소 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="4d40c-102">ColorDialog Component Overview (Windows Forms)</span></span>
<span data-ttu-id="4d40c-103">Windows Forms <xref:System.Windows.Forms.ColorDialog> 구성 요소는 사용자 색상표에서 색을 선택 하 고 해당 색상표에 사용자 지정 색을 추가할 수 있도록 미리 구성 된 대화 상자.</span><span class="sxs-lookup"><span data-stu-id="4d40c-103">The Windows Forms <xref:System.Windows.Forms.ColorDialog> component is a pre-configured dialog box that allows the user to select a color from a palette and to add custom colors to that palette.</span></span> <span data-ttu-id="4d40c-104">이 구성 요소는 다른 Windows 기반 애플리케이션에서 색상 선택하는 데 사용하는 대화 상자와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="4d40c-104">It is the same dialog box that you see in other Windows-based applications to select colors.</span></span> <span data-ttu-id="4d40c-105">고유한 대화 상자를 구성하는 대신 Windows 기반 애플리케이션 내에서 간단한 솔루션으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4d40c-105">Use it within your Windows-based application as a simple solution in lieu of configuring your own dialog box.</span></span>  
  
 <span data-ttu-id="4d40c-106">대화 상자에서 선택한 색에 반환 되는 <xref:System.Windows.Forms.ColorDialog.Color%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4d40c-106">The color selected in the dialog box is returned in the <xref:System.Windows.Forms.ColorDialog.Color%2A> property.</span></span> <span data-ttu-id="4d40c-107">경우는 <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> 속성이 `false`"사용자 지정 색" 단추가 비활성화 되 고 사용자가 미리 정의 된 색상표 색으로 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="4d40c-107">If the <xref:System.Windows.Forms.ColorDialog.AllowFullOpen%2A> property is set to `false`, the "Define Custom Colors" button is disabled and the user is restricted to the predefined colors in the palette.</span></span> <span data-ttu-id="4d40c-108">경우는 <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> 속성이 `true`, 디더링된 색을 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4d40c-108">If the <xref:System.Windows.Forms.ColorDialog.SolidColorOnly%2A> property is set to `true`, the user cannot select dithered colors.</span></span> <span data-ttu-id="4d40c-109">대화 상자를 표시 하려면 해당 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="4d40c-109">To display the dialog box, you must call its <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d40c-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="4d40c-110">See also</span></span>

- <xref:System.Windows.Forms.ColorDialog>
- [<span data-ttu-id="4d40c-111">ColorDialog 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4d40c-111">ColorDialog Component</span></span>](colordialog-component-windows-forms.md)
- [<span data-ttu-id="4d40c-112">대화 상자 컨트롤 및 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4d40c-112">Dialog-Box Controls and Components</span></span>](dialog-box-controls-and-components-windows-forms.md)
- [<span data-ttu-id="4d40c-113">방법: Windows Forms ColorDialog 구성 요소의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="4d40c-113">How to: Change the Appearance of the Windows Forms ColorDialog Component</span></span>](how-to-change-the-appearance-of-the-windows-forms-colordialog-component.md)
