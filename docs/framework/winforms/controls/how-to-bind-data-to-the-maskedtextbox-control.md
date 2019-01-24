---
title: '방법: MaskedTextBox 컨트롤에 데이터 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
- data binding [Windows Forms], MaskedTextBox control [Windows Forms]
- MaskedTextBox control [Windows Forms], binding data
ms.assetid: 34b29f07-e8df-48d4-b08b-53fcca524708
ms.openlocfilehash: 1eccfb40cd256cb3ebea6f0dcf38d73d5d53e8bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54735080"
---
# <a name="how-to-bind-data-to-the-maskedtextbox-control"></a><span data-ttu-id="14f81-102">방법: MaskedTextBox 컨트롤에 데이터 바인딩</span><span class="sxs-lookup"><span data-stu-id="14f81-102">How to: Bind Data to the MaskedTextBox Control</span></span>
<span data-ttu-id="14f81-103">데이터를 바인딩할 수 있습니다는 <xref:System.Windows.Forms.MaskedTextBox> 다른 Windows Forms 컨트롤에 같이 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-103">You can bind data to a <xref:System.Windows.Forms.MaskedTextBox> control just as you can to any other Windows Forms control.</span></span> <span data-ttu-id="14f81-104">그러나 데이터베이스에서 데이터 형식의 마스크 정의 필요한 형식이 일치 하지 않으면, 데이터의 서식을 다시 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-104">However, if the format of your data in the database does not match the format expected by your mask definition, you will need to reformat the data.</span></span> <span data-ttu-id="14f81-105">다음 절차를 사용 하 여 이렇게 하는 방법에 설명 합니다 <xref:System.Windows.Forms.Binding.Format> 및 <xref:System.Windows.Forms.Binding.Parse> 의 이벤트는 <xref:System.Windows.Forms.Binding> 클래스를 별도 전화 번호를 표시 및 편집할 수 있는 단일 필드로 확장 데이터베이스 필드를 전화 합니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-105">The following procedure demonstrates how to do this using the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events of the <xref:System.Windows.Forms.Binding> class to display separate phone number and phone extension database fields as a single editable field.</span></span>  
  
 <span data-ttu-id="14f81-106">다음 절차는 Northwind 샘플 데이터베이스가 설치 된 SQL Server 데이터베이스에 액세스할 수 있는지에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-106">The following procedure requires that you have access to a SQL Server database with the Northwind sample database installed.</span></span>  
  
### <a name="to-bind-data-to-a-maskedtextbox-control"></a><span data-ttu-id="14f81-107">MaskedTextBox 컨트롤에 데이터를 바인딩하려면</span><span class="sxs-lookup"><span data-stu-id="14f81-107">To bind data to a MaskedTextBox control</span></span>  
  
1.  <span data-ttu-id="14f81-108">새 Windows Forms 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-108">Create a new Windows Forms project.</span></span>  
  
2.  <span data-ttu-id="14f81-109">두 개의 끌어 <xref:System.Windows.Forms.TextBox> ; 양식에 컨트롤 이름을 지정 하 여 `FirstName` 및 `LastName`합니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-109">Drag two <xref:System.Windows.Forms.TextBox> controls onto your form; name them `FirstName` and `LastName`.</span></span>  
  
3.  <span data-ttu-id="14f81-110">끌어서를 <xref:System.Windows.Forms.MaskedTextBox> 컨트롤을 폼; 이름을 `PhoneMask`입니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-110">Drag a <xref:System.Windows.Forms.MaskedTextBox> control onto your form; name it `PhoneMask`.</span></span>  
  
4.  <span data-ttu-id="14f81-111">설정 된 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> 속성을 `PhoneMask` 에 `(000) 000-0000 x9999`입니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-111">Set the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property of `PhoneMask` to `(000) 000-0000 x9999`.</span></span>  
  
5.  <span data-ttu-id="14f81-112">폼에 다음 네임 스페이스 가져오기를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-112">Add the following namespace imports to the form.</span></span>  
  
    ```csharp  
    using System.Data.SqlClient;  
    ```  
  
    ```vb  
    Imports System.Data.SqlClient  
    ```  
  
6.  <span data-ttu-id="14f81-113">폼을 마우스 오른쪽 단추로 클릭 하 고 선택 **코드 보기**합니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-113">Right-click the form and choose **View Code**.</span></span> <span data-ttu-id="14f81-114">이 코드를 어디서 나 폼 클래스에 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-114">Place this code anywhere in your form class.</span></span>  
  
    ```csharp  
    Binding currentBinding, phoneBinding;  
    DataSet employeesTable = new DataSet();  
    SqlConnection sc;  
    SqlDataAdapter dataConnect;  
  
    private void Form1_Load(object sender, EventArgs e)  
    {  
        DoMaskBinding();  
    }  
  
    private void DoMaskBinding()  
    {  
        try  
        {  
            sc = new SqlConnection("Data Source=CLIENTUE;Initial Catalog=NORTHWIND;Integrated Security=SSPI");  
            sc.Open();  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
  
        dataConnect = new SqlDataAdapter("SELECT * FROM Employees", sc);  
        dataConnect.Fill(employeesTable, "Employees");  
  
        // Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        // before adding them to the control - otherwise, we won't get a Format event on the   
        // initial load.   
        try  
        {  
            currentBinding = new Binding("Text", employeesTable, "Employees.FirstName");  
            firstName.DataBindings.Add(currentBinding);  
  
            currentBinding = new Binding("Text", employeesTable, "Employees.LastName");  
            lastName.DataBindings.Add(currentBinding);  
  
            phoneBinding =new Binding("Text", employeesTable, "Employees.HomePhone");  
            // We must add the event handlers before we bind, or the Format event will not get called  
            // for the first record.  
            phoneBinding.Format += new ConvertEventHandler(phoneBinding_Format);  
            phoneBinding.Parse += new ConvertEventHandler(phoneBinding_Parse);  
            phoneMask.DataBindings.Add(phoneBinding);  
        }  
        catch (Exception ex)  
        {  
            MessageBox.Show(ex.Message);  
            return;  
        }  
    }  
    ```  
  
    ```vb  
    Dim WithEvents CurrentBinding, PhoneBinding As Binding  
    Dim EmployeesTable As New DataSet()  
    Dim sc As SqlConnection  
    Dim DataConnect As SqlDataAdapter  
  
    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load  
        DoMaskedBinding()  
    End Sub  
  
    Private Sub DoMaskedBinding()  
        Try  
            sc = New SqlConnection("Data Source=SERVERNAME;Initial Catalog=NORTHWIND;Integrated Security=SSPI")  
            sc.Open()  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Exit Sub  
        End Try  
  
        DataConnect = New SqlDataAdapter("SELECT * FROM Employees", sc)  
        DataConnect.Fill(EmployeesTable, "Employees")  
  
        ' Now bind MaskedTextBox to appropriate field. Note that we must create the Binding objects  
        ' before adding them to the control - otherwise, we won't get a Format event on the   
        ' initial load.  
        Try  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.FirstName")  
            firstName.DataBindings.Add(CurrentBinding)  
            CurrentBinding = New Binding("Text", EmployeesTable, "Employees.LastName")  
            lastName.DataBindings.Add(CurrentBinding)  
            PhoneBinding = New Binding("Text", EmployeesTable, "Employees.HomePhone")  
            PhoneMask.DataBindings.Add(PhoneBinding)  
        Catch ex As Exception  
            MessageBox.Show(ex.Message)  
            Application.Exit()  
        End Try  
    End Sub  
    ```  
  
7.  <span data-ttu-id="14f81-115">에 대 한 이벤트 처리기를 추가 합니다 <xref:System.Windows.Forms.Binding.Format> 및 <xref:System.Windows.Forms.Binding.Parse> 조합 및 분리 하는 이벤트를 `PhoneNumber` 및 `Extension` 바인딩된 필드 <xref:System.Data.DataSet>합니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-115">Add event handlers for the <xref:System.Windows.Forms.Binding.Format> and <xref:System.Windows.Forms.Binding.Parse> events to combine and separate the `PhoneNumber` and `Extension` fields from the bound <xref:System.Data.DataSet>.</span></span>  
  
    ```csharp  
    private void phoneBinding_Format(Object sender, ConvertEventArgs e)  
    {  
        String ext;  
  
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        if (currentRow["Extension"] == null)   
        {  
            ext = "";  
        } else   
        {  
            ext = currentRow["Extension"].ToString();  
        }  
  
        e.Value = e.Value.ToString().Trim() + " x" + ext;  
    }  
  
    private void phoneBinding_Parse(Object sender, ConvertEventArgs e)  
    {  
        String phoneNumberAndExt = e.Value.ToString();  
  
        int extIndex = phoneNumberAndExt.IndexOf("x");  
        String ext = phoneNumberAndExt.Substring(extIndex).Trim();  
        String phoneNumber = phoneNumberAndExt.Substring(0, extIndex).Trim();  
  
        //Get the current binding object, and set the new extension manually.   
        DataRowView currentRow = (DataRowView)BindingContext[employeesTable, "Employees"].Current;  
        // Remove the "x" from the extension.  
        currentRow["Extension"] = ext.Substring(1);  
  
        //Return the phone number.  
        e.Value = phoneNumber;  
    }  
    ```  
  
    ```vb  
    Private Sub PhoneBinding_Format(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Format  
        Dim Ext As String  
  
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        If (CurrentRow("Extension") Is Nothing) Then  
            Ext = ""  
        Else  
            Ext = CurrentRow("Extension").ToString()  
        End If  
  
        e.Value = e.Value.ToString().Trim() & " x" & Ext  
    End Sub  
  
    Private Sub PhoneBinding_Parse(ByVal sender As Object, ByVal e As ConvertEventArgs) Handles PhoneBinding.Parse  
        Dim PhoneNumberAndExt As String = e.Value.ToString()  
  
        Dim ExtIndex As Integer = PhoneNumberAndExt.IndexOf("x")  
        Dim Ext As String = PhoneNumberAndExt.Substring(ExtIndex).Trim()  
        Dim PhoneNumber As String = PhoneNumberAndExt.Substring(0, ExtIndex).Trim()  
  
        ' Get the current binding object, and set the new extension manually.   
        Dim CurrentRow As DataRowView = CType(Me.BindingContext(EmployeesTable, "Employees").Current, DataRowView)  
        ' Remove the "x" from the extension.  
        CurrentRow("Extension") = CObj(Ext.Substring(1))  
  
        ' Return the phone number.  
        e.Value = PhoneNumber  
    End Sub  
    ```  
  
8.  <span data-ttu-id="14f81-116">두 개의 추가 <xref:System.Windows.Forms.Button> 폼에 컨트롤을 합니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-116">Add two <xref:System.Windows.Forms.Button> controls to the form.</span></span> <span data-ttu-id="14f81-117">해당 이름을 `previousButton` 고 `nextButton`입니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-117">Name them `previousButton` and `nextButton`.</span></span> <span data-ttu-id="14f81-118">추가할 각 단추를 두 번 클릭을 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기 및 다음 코드 예제 에서처럼 이벤트 처리기를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-118">Double-click each button to add a <xref:System.Windows.Forms.Control.Click> event handler, and fill in the event handlers as shown in the following code example.</span></span>  
  
    ```csharp  
    private void previousButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position - 1;  
    }  
  
    private void nextButton_Click(object sender, EventArgs e)  
    {  
        BindingContext[employeesTable, "Employees"].Position = BindingContext[employeesTable, "Employees"].Position + 1;  
    }  
    ```  
  
    ```vb  
    Private Sub PreviousButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles PreviousButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position - 1  
    End Sub  
  
    Private Sub NextButton_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles NextButton.Click  
        Me.BindingContext(EmployeesTable, "Employees").Position = Me.BindingContext(EmployeesTable, "Employees").Position + 1  
    End Sub  
    ```  
  
9. <span data-ttu-id="14f81-119">샘플을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-119">Run the sample.</span></span> <span data-ttu-id="14f81-120">데이터를 편집 하 고 사용 합니다 **이전** 및 **다음** 데이터를 올바르게 유지 되어 있는지 확인 하려면 단추를 <xref:System.Data.DataSet>입니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-120">Edit the data, and use the **Previous** and **Next** buttons to see that the data is properly persisted to the <xref:System.Data.DataSet>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14f81-121">예제</span><span class="sxs-lookup"><span data-stu-id="14f81-121">Example</span></span>  
 <span data-ttu-id="14f81-122">다음 코드 예제에는 이전 절차를 완료 한 결과를 나열 하는 전체 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-122">The following code example is the full code listing that results from completing the previous procedure.</span></span>  
  
 [!code-cpp[MaskedTextBoxData#1](../../../../samples/snippets/cpp/VS_Snippets_Winforms/MaskedTextBoxData/cpp/form1.cpp#1)]
 [!code-csharp[MaskedTextBoxData#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/MaskedTextBoxData/CS/form1.cs#1)]
 [!code-vb[MaskedTextBoxData#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/MaskedTextBoxData/VB/form1.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="14f81-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="14f81-123">Compiling the Code</span></span>  
  
-   <span data-ttu-id="14f81-124">시각적 개체 만들기 C# 또는 Visual Basic 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-124">Create a Visual C# or Visual Basic project.</span></span>  
  
-   <span data-ttu-id="14f81-125">추가 된 <xref:System.Windows.Forms.TextBox> 및 <xref:System.Windows.Forms.MaskedTextBox> 이전 절차에서 설명한 대로 폼에 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-125">Add the <xref:System.Windows.Forms.TextBox> and <xref:System.Windows.Forms.MaskedTextBox> controls to the form, as described in the previous procedure.</span></span>  
  
-   <span data-ttu-id="14f81-126">프로젝트의 기본 폼에 대 한 소스 코드 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-126">Open the source code file for the project's default form.</span></span>  
  
-   <span data-ttu-id="14f81-127">이전 "코드" 섹션에 나와 있는 코드를 사용 하 여이 파일의 소스 코드를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-127">Replace the source code in this file with the code listed in the previous "Code" section.</span></span>  
  
-   <span data-ttu-id="14f81-128">응용 프로그램을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="14f81-128">Compile the application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14f81-129">참고자료</span><span class="sxs-lookup"><span data-stu-id="14f81-129">See also</span></span>
- [<span data-ttu-id="14f81-130">연습: MaskedTextBox 컨트롤 사용</span><span class="sxs-lookup"><span data-stu-id="14f81-130">Walkthrough: Working with the MaskedTextBox Control</span></span>](../../../../docs/framework/winforms/controls/walkthrough-working-with-the-maskedtextbox-control.md)
