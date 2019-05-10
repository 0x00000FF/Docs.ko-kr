---
title: '방법: Windows Form 인쇄'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, printing
- printing [Windows Forms]
- printing a form
- printing [Windows Forms], printing a form
ms.assetid: c8dff5f8-f56a-4c07-ae31-64643b31f8fc
ms.openlocfilehash: 68dbad807e79f16bdc3cbdd3f55c62c3d6c854e9
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64621301"
---
# <a name="how-to-print-a-windows-form"></a><span data-ttu-id="7ea55-102">방법: Windows Form 인쇄</span><span class="sxs-lookup"><span data-stu-id="7ea55-102">How to: Print a Windows Form</span></span>
<span data-ttu-id="7ea55-103">개발 프로세스의 일환으로, 일반적으로 하려는 Windows Form의 복사본을 인쇄 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea55-103">As part of the development process, you typically will want to print a copy of your Windows Form.</span></span> <span data-ttu-id="7ea55-104">다음 코드 예제를 사용 하 여 현재 폼의 복사본을 인쇄 하는 방법을 보여 줍니다는 <xref:System.Drawing.Graphics.CopyFromScreen%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="7ea55-104">The following code example shows how to print a copy of the current form by using the <xref:System.Drawing.Graphics.CopyFromScreen%2A> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7ea55-105">예제</span><span class="sxs-lookup"><span data-stu-id="7ea55-105">Example</span></span>  
 [!code-csharp[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/CS/Form1.cs#1)]
 [!code-vb[System.Drawing.Graphics.CopyFromScreen#1](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.Graphics.CopyFromScreen/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="7ea55-106">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="7ea55-106">Compiling the Code</span></span>  
 <span data-ttu-id="7ea55-107">이 포함 하는 전체 코드 예제는 `Main` 메서드.</span><span class="sxs-lookup"><span data-stu-id="7ea55-107">This is a complete code example that contains a `Main` method.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="7ea55-108">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="7ea55-108">Robust Programming</span></span>  
 <span data-ttu-id="7ea55-109">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea55-109">The following conditions may cause an exception:</span></span>  
  
- <span data-ttu-id="7ea55-110">프린터에 액세스할 수 있는 권한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ea55-110">You do not have permission to access the printer.</span></span>  
  
- <span data-ttu-id="7ea55-111">설치 된 프린터가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ea55-111">There is no printer installed.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="7ea55-112">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="7ea55-112">.NET Framework Security</span></span>  
 <span data-ttu-id="7ea55-113">이 코드 예제를 실행 하기 위해 사용할 프린터를 사용 하 여 컴퓨터를 액세스할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea55-113">In order to run this code example, you must have permission to access the printer you use with your computer.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ea55-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="7ea55-114">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="7ea55-115">방법: GDI +를 사용 하 여 이미지를 렌더링 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ea55-115">How to: Render Images with GDI+</span></span>](how-to-render-images-with-gdi.md)
- [<span data-ttu-id="7ea55-116">방법: Windows Forms의 그래픽 인쇄</span><span class="sxs-lookup"><span data-stu-id="7ea55-116">How to: Print Graphics in Windows Forms</span></span>](how-to-print-graphics-in-windows-forms.md)
