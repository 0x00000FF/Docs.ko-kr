---
title: '방법: 두 개의 Windows Forms DataGridView 컨트롤을 사용 하 여 마스터-세부 폼 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- DataGridView control [Windows Forms], master/detail form
- parent-child tables [Windows Forms], displaying on Windows Forms
- master-details lists [Windows Forms], creating
ms.assetid: 99f6e876-3f7f-4139-9063-e36587c95b02
ms.openlocfilehash: ccd9354d623cf1b452bc3890b7fd9a5248cb69c8
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59088797"
---
# <a name="how-to-create-a-masterdetail-form-using-two-windows-forms-datagridview-controls"></a><span data-ttu-id="03e5e-102">방법: 두 개의 Windows Forms DataGridView 컨트롤을 사용하여 마스터/세부 양식 만들기</span><span class="sxs-lookup"><span data-stu-id="03e5e-102">How to: Create a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>
<span data-ttu-id="03e5e-103">다음 코드 예제에서는 두 개의 <xref:System.Windows.Forms.BindingSource> 구성 요소에 바인딩된 두 개의 <xref:System.Windows.Forms.DataGridView> 컨트롤을 사용하여 마스터/세부 폼을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="03e5e-103">The following code example creates a master/detail form using two <xref:System.Windows.Forms.DataGridView> controls bound to two <xref:System.Windows.Forms.BindingSource> components.</span></span> <span data-ttu-id="03e5e-104">데이터 소스는 SQL Server Northwind 샘플 데이터베이스의 `Customers` 및 `Orders` 테이블과 `CustomerID` 열을 통해 두 테이블을 연결하는 <xref:System.Data.DataRelation>을 포함하는 <xref:System.Data.DataSet>니다.</span><span class="sxs-lookup"><span data-stu-id="03e5e-104">The data source is a <xref:System.Data.DataSet> that contains the `Customers` and `Orders` tables from the Northwind SQL Server sample database along with a <xref:System.Data.DataRelation> that relates the two through the `CustomerID` column.</span></span>  
  
 <span data-ttu-id="03e5e-105">하나의 <xref:System.Windows.Forms.BindingSource>가 데이터 집합의 부모 `Customers` 테이블에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e5e-105">One <xref:System.Windows.Forms.BindingSource> is bound to the parent `Customers` table in the data set.</span></span> <span data-ttu-id="03e5e-106">이 데이터는 마스터 <xref:System.Windows.Forms.DataGridView> 컨트롤에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e5e-106">This data is displayed in the master <xref:System.Windows.Forms.DataGridView> control.</span></span> <span data-ttu-id="03e5e-107">다른 <xref:System.Windows.Forms.BindingSource>는 첫 번째 데이터 커넥터에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e5e-107">The other <xref:System.Windows.Forms.BindingSource> is bound to the first data connector.</span></span> <span data-ttu-id="03e5e-108">두 번째 <xref:System.Windows.Forms.BindingSource>의 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 속성은 <xref:System.Data.DataRelation> 이름으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e5e-108">The <xref:System.Windows.Forms.BindingSource.DataMember%2A> property of the second <xref:System.Windows.Forms.BindingSource> is set to the <xref:System.Data.DataRelation> name.</span></span> <span data-ttu-id="03e5e-109">이렇게 하면 연결된 세부 <xref:System.Windows.Forms.DataGridView> 컨트롤에 마스터 <xref:System.Windows.Forms.DataGridView> 컨트롤의 현재 행에 해당하는 자식 `Orders` 테이블의 행이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="03e5e-109">This causes the associated detail <xref:System.Windows.Forms.DataGridView> control to display the rows of the child `Orders` table that correspond to the current row in the master <xref:System.Windows.Forms.DataGridView> control.</span></span>  
  
 <span data-ttu-id="03e5e-110">에 대 한 전체 설명은이 코드 예제를 참조 하세요. [연습: Forms DataGridView 컨트롤을 두 개의 Windows를 사용 하 여 마스터/세부 폼 만들기](creating-a-master-detail-form-using-two-datagridviews.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03e5e-110">For a complete explanation of this code example, see [Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls](creating-a-master-detail-form-using-two-datagridviews.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="03e5e-111">예제</span><span class="sxs-lookup"><span data-stu-id="03e5e-111">Example</span></span>  
 [!code-csharp[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/CS/masterdetails.cs#00)]
 [!code-vb[System.Windows.Forms.DataGridViewMasterDetails#00](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMasterDetails/VB/masterdetails.vb#00)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="03e5e-112">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="03e5e-112">Compiling the Code</span></span>  
 <span data-ttu-id="03e5e-113">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="03e5e-113">This example requires:</span></span>  
  
 <span data-ttu-id="03e5e-114">System, System.Data, System.Windows.Forms 및 System.XML 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="03e5e-114">References to the System, System.Data, System.Windows.Forms, and System.XML assemblies.</span></span>  
  
-   <span data-ttu-id="03e5e-115">Visual Basic 또는 Visual C#에 대 한 명령줄에서이 예제를 빌드하는 방법에 대 한 내용은 [명령줄에서 빌드](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) 하거나 [csc.exe를 사용한 명령줄 빌드](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="03e5e-115">For information about building this example from the command line for Visual Basic or Visual C#, see [Building from the Command Line](../../../visual-basic/reference/command-line-compiler/building-from-the-command-line.md) or [Command-line Building With csc.exe](../../../csharp/language-reference/compiler-options/command-line-building-with-csc-exe.md).</span></span> <span data-ttu-id="03e5e-116">또한 새 프로젝트에 코드를 붙여 넣어 Visual Studio에서이 예제를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e5e-116">You can also build this example in Visual Studio by pasting the code into a new project.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="03e5e-117">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="03e5e-117">.NET Framework Security</span></span>  
 <span data-ttu-id="03e5e-118">암호와 같은 중요한 정보를 연결 문자열 내에 저장하면 애플리케이션 보안 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03e5e-118">Storing sensitive information, such as a password, within the connection string can affect the security of your application.</span></span> <span data-ttu-id="03e5e-119">데이터베이스 액세스를 제어할 경우에는 통합 보안이라고도 하는 Windows 인증을 사용하는 방법이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="03e5e-119">Using Windows Authentication (also known as integrated security) is a more secure way to control access to a database.</span></span> <span data-ttu-id="03e5e-120">자세한 내용은 [연결 정보 보호](../../data/adonet/protecting-connection-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="03e5e-120">For more information, see [Protecting Connection Information](../../data/adonet/protecting-connection-information.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03e5e-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="03e5e-121">See also</span></span>

- <xref:System.Windows.Forms.DataGridView>
- <xref:System.Windows.Forms.BindingSource>
- [<span data-ttu-id="03e5e-122">연습: 두 개의 Windows Forms DataGridView 컨트롤을 사용 하 여 마스터/세부 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="03e5e-122">Walkthrough: Creating a Master/Detail Form Using Two Windows Forms DataGridView Controls</span></span>](creating-a-master-detail-form-using-two-datagridviews.md)
- [<span data-ttu-id="03e5e-123">Windows Forms DataGridView 컨트롤에서 데이터 표시</span><span class="sxs-lookup"><span data-stu-id="03e5e-123">Displaying Data in the Windows Forms DataGridView Control</span></span>](displaying-data-in-the-windows-forms-datagridview-control.md)
- [<span data-ttu-id="03e5e-124">연결 정보 보호</span><span class="sxs-lookup"><span data-stu-id="03e5e-124">Protecting Connection Information</span></span>](../../data/adonet/protecting-connection-information.md)
