---
title: '방법: 인쇄 대화 상자 호출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- invoking print dialogs [WPF]
- print dialogs [WPF], invoking
ms.assetid: e3a2c84c-74fe-45a4-8501-5813f9dbfed2
ms.openlocfilehash: 271652fe9e98f9a381da5655bd313e12f8ee917d
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43741048"
---
# <a name="how-to-invoke-a-print-dialog"></a><span data-ttu-id="a57b7-102">방법: 인쇄 대화 상자 호출</span><span class="sxs-lookup"><span data-stu-id="a57b7-102">How to: Invoke a Print Dialog</span></span>
<span data-ttu-id="a57b7-103">응용 프로그램에서 인쇄 하는 기능을 제공 하려면 있습니다 단순히 만들고 열 수는 <xref:System.Windows.Controls.PrintDialog> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a57b7-103">To provide the ability to print from you application, you can simply create and open a <xref:System.Windows.Controls.PrintDialog> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a57b7-104">예제</span><span class="sxs-lookup"><span data-stu-id="a57b7-104">Example</span></span>  
 <span data-ttu-id="a57b7-105"><xref:System.Windows.Controls.PrintDialog> 컨트롤은 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], 구성 및 [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] 작업 제출을 위한 단일 진입점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a57b7-105">The <xref:System.Windows.Controls.PrintDialog> control provides a single entry point for [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)], configuration, and [!INCLUDE[TLA2#tla_metro](../../../../includes/tla2sharptla-metro-md.md)] job submission.</span></span> <span data-ttu-id="a57b7-106">컨트롤을 쉽게 사용 하 고 사용 하 여 인스턴스화할 수 있습니다 [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] 태그나 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="a57b7-106">The control is easy to use and can be instantiated by using [!INCLUDE[TLA#tla_xaml](../../../../includes/tlasharptla-xaml-md.md)] markup or code.</span></span> <span data-ttu-id="a57b7-107">다음 예제에서는 인스턴스화하고 코드에서 컨트롤을 열고 방법에서 인쇄 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a57b7-107">The following example demonstrates how to instantiate and open the control in code and how to print from it.</span></span> <span data-ttu-id="a57b7-108">또한는 대화 상자는 사용자에 게 제공 페이지의 특정 범위를 설정 하는 옵션을 확인 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a57b7-108">It also shows how to ensure that the dialog will give the user the option of setting a specific range of pages.</span></span> <span data-ttu-id="a57b7-109">예제 코드를 c: 드라이브의 루트에 있는 파일 FixedDocumentSequence.xps 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57b7-109">The example code assumes that there is a file FixedDocumentSequence.xps in the root of the C: drive.</span></span>  
  
 [!code-csharp[printdialog#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/PrintDialog/CSharp/Window1.xaml.cs#1)]
 [!code-vb[printdialog#1](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/PrintDialog/visualbasic/window1.xaml.vb#1)]  
  
 <span data-ttu-id="a57b7-110">대화 상자를 연 후 사용자가 자신의 컴퓨터에 설치 된 프린터 중에서 선택할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a57b7-110">Once the dialog is open, users will be able to select from the printers installed on their computer.</span></span> <span data-ttu-id="a57b7-111">옵션을 선택 하는 단위도 합니다 [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319) 만들려면는 [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] 인쇄 하는 대신 파일.</span><span class="sxs-lookup"><span data-stu-id="a57b7-111">They will also have the option of selecting the [Microsoft XPS Document Writer](https://go.microsoft.com/fwlink/?LinkId=147319) to create an [!INCLUDE[TLA#tla_xps](../../../../includes/tlasharptla-xps-md.md)] file instead of printing.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a57b7-112">합니다 <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> 제어 [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)],이 항목에서 설명 하는 혼동 하지는 <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> Windows Forms 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a57b7-112">The <xref:System.Windows.Controls.PrintDialog?displayProperty=nameWithType> control of [!INCLUDE[TLA2#tla_wpf](../../../../includes/tla2sharptla-wpf-md.md)], which is discussed in this topic, should not be confused with the <xref:System.Windows.Forms.PrintDialog?displayProperty=nameWithType> component of Windows Forms.</span></span>  
  
 <span data-ttu-id="a57b7-113">엄격히 말해, 사용할 수 있습니다는 <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> 적이 대화 상자를 열지 않고 메서드.</span><span class="sxs-lookup"><span data-stu-id="a57b7-113">Strictly speaking, you can use the <xref:System.Windows.Controls.PrintDialog.PrintDocument%2A> method without ever opening the dialog.</span></span> <span data-ttu-id="a57b7-114">이런 의미에서 컨트롤이 보이지 않는 인쇄 구성 요소로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a57b7-114">In that sense, the control can be used as an unseen printing component.</span></span> <span data-ttu-id="a57b7-115">하지만 성능상의 이유로 사용 하 여 더 나은 것은 <xref:System.Printing.PrintQueue.AddJob%2A> 메서드 또는 다양 한 <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> 및 <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> 의 메서드는 <xref:System.Windows.Xps.XpsDocumentWriter>합니다.</span><span class="sxs-lookup"><span data-stu-id="a57b7-115">But for performance reasons, it would be better to use either the <xref:System.Printing.PrintQueue.AddJob%2A> method or one of the many <xref:System.Windows.Xps.XpsDocumentWriter.Write%2A> and <xref:System.Windows.Xps.XpsDocumentWriter.WriteAsync%2A> methods of the <xref:System.Windows.Xps.XpsDocumentWriter>.</span></span> <span data-ttu-id="a57b7-116">이 대 한 자세한 내용은 참조 하세요 [프로그래밍 방식으로 XPS 파일 인쇄](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) 및 합니다.</span><span class="sxs-lookup"><span data-stu-id="a57b7-116">For more about this, see [Programmatically Print XPS Files](../../../../docs/framework/wpf/advanced/how-to-programmatically-print-xps-files.md) and .</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a57b7-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a57b7-117">See Also</span></span>  
 <xref:System.Windows.Controls.PrintDialog>  
 [<span data-ttu-id="a57b7-118">WPF의 문서</span><span class="sxs-lookup"><span data-stu-id="a57b7-118">Documents in WPF</span></span>](../../../../docs/framework/wpf/advanced/documents-in-wpf.md)  
 [<span data-ttu-id="a57b7-119">인쇄 개요</span><span class="sxs-lookup"><span data-stu-id="a57b7-119">Printing Overview</span></span>](../../../../docs/framework/wpf/advanced/printing-overview.md)  
 [<span data-ttu-id="a57b7-120">Microsoft XPS Document Writer</span><span class="sxs-lookup"><span data-stu-id="a57b7-120">Microsoft XPS Document Writer</span></span>](https://go.microsoft.com/fwlink/?LinkId=147319)
