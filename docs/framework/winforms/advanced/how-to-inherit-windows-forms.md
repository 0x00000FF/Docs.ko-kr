---
title: '방법: Windows Forms 상속'
ms.date: 03/30/2017
dev_langs:
- CSharp
- VB
helpviewer_keywords:
- inherited forms [Windows Forms], creating at run-time
- inheritance [Windows Forms], forms
- Windows Forms, inheritance
ms.assetid: cb3e1c0f-3d2a-4cdc-b0d1-c92eae567ffb
ms.openlocfilehash: 60c238430d44371bbd3859c3864fd2ef73f70098
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69037922"
---
# <a name="how-to-inherit-windows-forms"></a><span data-ttu-id="737c9-102">방법: Windows Forms 상속</span><span class="sxs-lookup"><span data-stu-id="737c9-102">How to: Inherit Windows Forms</span></span>

<span data-ttu-id="737c9-103">기본 폼에서 상속해서 새 Windows Forms를 만드는 것은 필요할 때마다 폼을 전체적으로 다시 만드는 프로세스를 거치지 않고 최선의 노력을 되풀이하는 편리한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="737c9-103">Creating new Windows Forms by inheriting from base forms is a handy way to duplicate your best efforts without going through the process of entirely recreating a form every time you require it.</span></span>

<span data-ttu-id="737c9-104">디자인 타임에 **상속 선택** 대화 상자를 사용 하 여 폼을 상속 하는 방법과 상속 된 컨트롤 [의 보안 수준을 시각적으로 구분 하는 방법에 대 한 자세한 내용은 방법: 상속 선택 대화 상자](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md)를 사용 하 여 폼을 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="737c9-104">For more information about inheriting forms at design time using the **Inheritance Picker** dialog box and how to visually distinguish between security levels of inherited controls, see [How to: Inherit Forms Using the Inheritance Picker Dialog Box](how-to-inherit-forms-using-the-inheritance-picker-dialog-box.md).</span></span>

> [!NOTE]
> <span data-ttu-id="737c9-105">폼에서 상속 하려면 해당 양식을 포함 하는 파일 또는 네임 스페이스가 실행 파일 또는 DLL에 내장 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="737c9-105">In order to inherit from a form, the file or namespace containing that form must have been built into an executable file or DLL.</span></span> <span data-ttu-id="737c9-106">프로젝트를 빌드하려면 **빌드** 메뉴에서 **빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="737c9-106">To build the project, choose **Build** from the **Build** menu.</span></span> <span data-ttu-id="737c9-107">또한 네임스페이스에 대한 참조는 폼을 상속하는 클래스에 추가되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="737c9-107">Also, a reference to the namespace must be added to the class inheriting the form.</span></span>

## <a name="inherit-a-form-programmatically"></a><span data-ttu-id="737c9-108">프로그래밍 방식으로 양식 상속</span><span class="sxs-lookup"><span data-stu-id="737c9-108">Inherit a form programmatically</span></span>

1. <span data-ttu-id="737c9-109">클래스에서 상속받을 폼이 포함된 네임스페이스에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="737c9-109">In your class, add a reference to the namespace containing the form you wish to inherit from.</span></span>

2. <span data-ttu-id="737c9-110">클래스 정의에서 상속받을 폼에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="737c9-110">In the class definition, add a reference to the form to inherit from.</span></span> <span data-ttu-id="737c9-111">참조에는 폼이 들어 있는 네임스페이스, 마침표, 기본 폼 자체의 이름이 차례로 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="737c9-111">The reference should include the namespace that contains the form, followed by a period, then the name of the base form itself.</span></span>

    ```vb
    Public Class Form2
        Inherits Namespace1.Form1
    ```

    ```csharp
    public class Form2 : Namespace1.Form1
    ```

 <span data-ttu-id="737c9-112">폼을 상속할 때 이벤트 처리기가 기본 클래스와 상속된 클래스에서 두 번 호출되는 문제가 발생할 수 있다는 점을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="737c9-112">When inheriting forms, keep in mind that issues may arise with regard to event handlers being called twice, because each event is being handled by both the base class and the inherited class.</span></span> <span data-ttu-id="737c9-113">이 문제를 방지하는 방법에 대한 자세한 내용은 [Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="737c9-113">For more information on how to avoid this problem, see [Troubleshooting Inherited Event Handlers in Visual Basic](~/docs/visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="737c9-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="737c9-114">See also</span></span>

- [<span data-ttu-id="737c9-115">Inherits 문</span><span class="sxs-lookup"><span data-stu-id="737c9-115">Inherits Statement</span></span>](~/docs/visual-basic/language-reference/statements/inherits-statement.md)
- [<span data-ttu-id="737c9-116">Imports 문(.NET 네임스페이스 및 형식)</span><span class="sxs-lookup"><span data-stu-id="737c9-116">Imports Statement (.NET Namespace and Type)</span></span>](~/docs/visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [<span data-ttu-id="737c9-117">using</span><span class="sxs-lookup"><span data-stu-id="737c9-117">using</span></span>](~/docs/csharp/language-reference/keywords/using.md)
- [<span data-ttu-id="737c9-118">기본 폼의 모양 수정 효과</span><span class="sxs-lookup"><span data-stu-id="737c9-118">Effects of Modifying a Base Form's Appearance</span></span>](effects-of-modifying-base-form-appearance.md)
- [<span data-ttu-id="737c9-119">Windows Forms 시각적 개체 상속</span><span class="sxs-lookup"><span data-stu-id="737c9-119">Windows Forms Visual Inheritance</span></span>](windows-forms-visual-inheritance.md)
