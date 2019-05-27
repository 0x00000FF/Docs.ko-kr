---
title: '방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
f1_keywords:
- ListItem
helpviewer_keywords:
- examples [Windows Forms], TreeView control
- examples [Windows Forms], ListView control
- ListView control [Windows Forms], adding custom information
- TreeView control [Windows Forms], adding custom information
ms.assetid: 68be11de-1d5b-430e-901f-cfbe48d14b19
ms.openlocfilehash: 5f51744878da526147dd742e98117e8e87c94e20
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66052233"
---
# <a name="how-to-add-custom-information-to-a-treeview-or-listview-control-windows-forms"></a><span data-ttu-id="18ca2-102">방법: TreeView 또는 ListView 컨트롤에 사용자 지정 정보 추가(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="18ca2-102">How to: Add Custom Information to a TreeView or ListView Control (Windows Forms)</span></span>
<span data-ttu-id="18ca2-103">Windows Forms에서 파생 된 노드를 만들 수 있습니다 <xref:System.Windows.Forms.TreeView> 컨트롤 또는에서 파생된 된 항목을 <xref:System.Windows.Forms.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="18ca2-103">You can create a derived node in a Windows Forms <xref:System.Windows.Forms.TreeView> control or a derived item in a <xref:System.Windows.Forms.ListView> control.</span></span> <span data-ttu-id="18ca2-104">파생은 필드를 처리하는 사용자 지정 메서드 및 생성자뿐만 아니라 필요로 하는 모든 필드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18ca2-104">Derivation allows you to add any fields you require, as well as custom methods and constructors for handling them.</span></span> <span data-ttu-id="18ca2-105">이 기능을 사용하여 각 트리 노드 또는 목록 항목에 고객 개체를 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="18ca2-105">One use of this feature is to attach a Customer object to each tree node or list item.</span></span> <span data-ttu-id="18ca2-106">여기에 있는 예제는 한 <xref:System.Windows.Forms.TreeView> 컨트롤 이지만 동일한 접근 방식을 사용할 수 있습니다는 <xref:System.Windows.Forms.ListView> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="18ca2-106">The examples here are for a <xref:System.Windows.Forms.TreeView> control, but the same approach can be used for a <xref:System.Windows.Forms.ListView> control.</span></span>  
  
### <a name="to-derive-a-tree-node"></a><span data-ttu-id="18ca2-107">트리 노드를 파생하려면</span><span class="sxs-lookup"><span data-stu-id="18ca2-107">To derive a tree node</span></span>  
  
- <span data-ttu-id="18ca2-108">파생 된 새 노드 클래스를 만들기는 <xref:System.Windows.Forms.TreeNode> 파일 경로 기록 하는 사용자 지정 필드가 있는 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="18ca2-108">Create a new node class, derived from the <xref:System.Windows.Forms.TreeNode> class, which has a custom field to record a file path.</span></span>  
  
    ```vb  
    Class myTreeNode  
       Inherits TreeNode  
  
       Public FilePath As String  
  
       Sub New(ByVal fp As String)  
          MyBase.New()  
          FilePath = fp  
          Me.Text = fp.Substring(fp.LastIndexOf("\"))  
       End Sub  
    End Class  
    ```  
  
    ```csharp  
    class myTreeNode : TreeNode  
    {  
       public string FilePath;  
  
       public myTreeNode(string fp)  
       {  
          FilePath = fp;  
          this.Text = fp.Substring(fp.LastIndexOf("\\"));  
       }  
    }  
    ```  
  
    ```cpp  
    ref class myTreeNode : public TreeNode  
    {  
    public:  
       System::String ^ FilePath;  
  
       myTreeNode(System::String ^ fp)  
       {  
          FilePath = fp;  
          this->Text = fp->Substring(fp->LastIndexOf("\\"));  
       }  
    };  
    ```  
  
### <a name="to-use-a-derived-tree-node"></a><span data-ttu-id="18ca2-109">파생된 트리 노드를 사용하려면</span><span class="sxs-lookup"><span data-stu-id="18ca2-109">To use a derived tree node</span></span>  
  
1. <span data-ttu-id="18ca2-110">함수 호출에 대한 매개 변수로 새롭게 파생된 트리 노드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18ca2-110">You can use the new derived tree node as a parameter to function calls.</span></span>  
  
     <span data-ttu-id="18ca2-111">아래 예제에서 텍스트 파일의 위치에 설정된 경로는 내 문서 폴더입니다.</span><span class="sxs-lookup"><span data-stu-id="18ca2-111">In the example below, the path set for the location of the text file is the My Documents folder.</span></span> <span data-ttu-id="18ca2-112">Windows 운영 체제를 실행하는 대부분 컴퓨터가 이 디렉터리에 포함된다고 가정할 수 있기 때문에 그렇습니다.</span><span class="sxs-lookup"><span data-stu-id="18ca2-112">This is done because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="18ca2-113">또한 최소한의 시스템 액세스 수준을 가진 사용자가 안전하게 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18ca2-113">This also allows users with minimal system access levels to safely run the application.</span></span>  
  
    ```vb  
    ' You should replace the bold text file   
    ' in the sample below with a text file of your own choosing.  
    TreeView1.Nodes.Add(New myTreeNode (System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\ TextFile.txt ") )  
    ```  
  
    ```csharp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    // Note the escape character used (@) when specifying the path.  
    treeView1.Nodes.Add(new myTreeNode(System.Environment.GetFolderPath
       (System.Environment.SpecialFolder.Personal)
       + @"\TextFile.txt") );  
    ```  
  
    ```cpp  
    // You should replace the bold text file   
    // in the sample below with a text file of your own choosing.  
    treeView1->Nodes->Add(new myTreeNode(String::Concat(  
       System::Environment::GetFolderPath  
       (System::Environment::SpecialFolder::Personal),  
       "\\TextFile.txt")));  
    ```  
  
2. <span data-ttu-id="18ca2-114">트리 노드를 전달 하 고 형식화 되어를 <xref:System.Windows.Forms.TreeNode> 클래스를 파생 클래스로 캐스팅 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18ca2-114">If you are passed the tree node and it is typed as a <xref:System.Windows.Forms.TreeNode> class, then you will need to cast to your derived class.</span></span> <span data-ttu-id="18ca2-115">캐스팅은 개체의 한 유형에서 다른 유형으로의 명시적 변환입니다.</span><span class="sxs-lookup"><span data-stu-id="18ca2-115">Casting is an explicit conversion from one type of object to another.</span></span> <span data-ttu-id="18ca2-116">캐스팅에 대 한 자세한 내용은 참조 하세요. [암시적 변환과 명시적 변환](~/docs/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) (Visual Basic), [캐스팅 및 형식 변환](~/docs/csharp/programming-guide/types/casting-and-type-conversions.md) (Visual C#), 또는 [캐스트 연산자: ()](/cpp/cpp/cast-operator-parens) ( Visual C++).</span><span class="sxs-lookup"><span data-stu-id="18ca2-116">For more information on casting, see [Implicit and Explicit Conversions](~/docs/visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md) (Visual Basic), [Casting and type conversions](~/docs/csharp/programming-guide/types/casting-and-type-conversions.md) (Visual C#), or [Cast Operator: ()](/cpp/cpp/cast-operator-parens) (Visual C++).</span></span>  
  
    ```vb  
    Public Sub TreeView1_AfterSelect(ByVal sender As Object, ByVal e As System.Windows.Forms.TreeViewEventArgs) Handles TreeView1.AfterSelect  
       Dim mynode As myTreeNode  
       mynode = CType(e.node, myTreeNode)  
       MessageBox.Show("Node selected is " & mynode.filepath)  
    End Sub  
    ```  
  
    ```csharp  
    protected void treeView1_AfterSelect (object sender,  
    System.Windows.Forms.TreeViewEventArgs e)  
    {  
       myTreeNode myNode = (myTreeNode)e.Node;  
       MessageBox.Show("Node selected is " + myNode.FilePath);  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void treeView1_AfterSelect(System::Object ^  sender,  
          System::Windows::Forms::TreeViewEventArgs ^  e)  
       {  
          myTreeNode ^ myNode = safe_cast<myTreeNode^>(e->Node);  
          MessageBox::Show(String::Concat("Node selected is ",   
             myNode->FilePath));  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="18ca2-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="18ca2-117">See also</span></span>

- [<span data-ttu-id="18ca2-118">TreeView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="18ca2-118">TreeView Control</span></span>](treeview-control-windows-forms.md)
- [<span data-ttu-id="18ca2-119">ListView 컨트롤</span><span class="sxs-lookup"><span data-stu-id="18ca2-119">ListView Control</span></span>](listview-control-windows-forms.md)
