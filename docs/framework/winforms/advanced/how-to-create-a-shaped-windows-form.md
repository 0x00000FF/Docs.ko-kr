---
title: '방법: 모양을 가진 Windows Form 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- forms [Windows Forms], rounded
- Windows Forms, custom shapes
- Windows Forms, shaped
- shaped forms
- forms [Windows Forms], changing the shape of
- forms [Windows Forms], circular
- forms [Windows Forms], nonrectangular
- Windows Forms, nonrectangular shape
- Windows Forms, rounded
- Windows Forms, circular
- forms [Windows Forms], custom shapes
ms.assetid: 6e6041e0-8e67-4487-b1e9-e410dbd1ef6c
ms.openlocfilehash: 4a799baa2732b4d2a28a9d8d67fa54d8b48dd191
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33522219"
---
# <a name="how-to-create-a-shaped-windows-form"></a><span data-ttu-id="f868e-102">방법: 모양을 가진 Windows Form 만들기</span><span class="sxs-lookup"><span data-stu-id="f868e-102">How to: Create a Shaped Windows Form</span></span>
<span data-ttu-id="f868e-103">이 예제에서는 폼을 타원 폼과 크기를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f868e-103">This example gives a form an elliptical shape that resizes with the form.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f868e-104">예제</span><span class="sxs-lookup"><span data-stu-id="f868e-104">Example</span></span>  
 [!code-cpp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/cpp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/cpp/form1.cpp#10)]
 [!code-csharp[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/CS/form1.cs#10)]
 [!code-vb[System.Drawing.ConceptualHowTos#10](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ConceptualHowTos/VB/form1.vb#10)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f868e-105">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f868e-105">Compiling the Code</span></span>  
 <span data-ttu-id="f868e-106">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="f868e-106">This example requires:</span></span>  
  
-   <span data-ttu-id="f868e-107"><xref:System.Windows.Forms> 및 <xref:System.Drawing> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="f868e-107">References to the <xref:System.Windows.Forms> and <xref:System.Drawing> namespaces.</span></span>  
  
 <span data-ttu-id="f868e-108">이 예제는 재정의 <xref:System.Windows.Forms.Control.OnPaint%2A> 메서드를 폼의 모양을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="f868e-108">This example overrides the <xref:System.Windows.Forms.Control.OnPaint%2A> method to change the shape of the form.</span></span> <span data-ttu-id="f868e-109">이 코드를 사용 하려면 메서드 선언 뿐만 아니라 메서드 내부 그리기 코드를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f868e-109">To use this code, copy the method declaration as well as the drawing code inside the method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f868e-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f868e-110">See Also</span></span>  
 <xref:System.Windows.Forms.Control.OnPaint%2A>  
 <xref:System.Drawing.Region>  
 <xref:System.Drawing>  
 <xref:System.Drawing.Drawing2D.GraphicsPath.AddEllipse%2A>  
 <xref:System.Windows.Forms.Control.Region%2A>  
 [<span data-ttu-id="f868e-111">그래픽 프로그래밍 시작</span><span class="sxs-lookup"><span data-stu-id="f868e-111">Getting Started with Graphics Programming</span></span>](../../../../docs/framework/winforms/advanced/getting-started-with-graphics-programming.md)
