---
title: "비동기 작업 또는 작업 목록 취소(C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: eec32dbb-70ea-4c88-bd27-fa2e34546914
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2e34344c9cdf0717291c4c7375bab703679515a7
ms.contentlocale: ko-kr
ms.lasthandoff: 07/28/2017

---
# <a name="cancel-an-async-task-or-a-list-of-tasks-c"></a><span data-ttu-id="745d8-102">비동기 작업 또는 작업 목록 취소(C#)</span><span class="sxs-lookup"><span data-stu-id="745d8-102">Cancel an Async Task or a List of Tasks (C#)</span></span>
<span data-ttu-id="745d8-103">작업이 완료될 때까지 기다리지 않으려면 비동기 응용 프로그램을 취소할 때 사용하는 단추를 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-103">You can set up a button that you can use to cancel an async application if you don't want to wait for it to finish.</span></span> <span data-ttu-id="745d8-104">이 항목의 예제에 따라 한 웹 사이트 또는 웹 사이트 목록의 콘텐츠를 다운로드하는 응용 프로그램에 취소 단추를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-104">By following the examples in this topic, you can add a cancellation button to an application that downloads the contents of one website or a list of websites.</span></span>  
  
 <span data-ttu-id="745d8-105">예제에서는 [비동기 응용 프로그램 미세 조정(C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md)에서 설명하는 UI를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-105">The examples use the UI that [Fine-Tuning Your Async Application (C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md) describes.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="745d8-106">예제를 실행하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-106">To run the examples, you must have Visual Studio 2012 or newer and the .NET Framework 4.5 or newer installed on your computer.</span></span>  
  
##  <span data-ttu-id="745d8-107"><a name="BKMK_CancelaTask"></a> 작업 취소</span><span class="sxs-lookup"><span data-stu-id="745d8-107"><a name="BKMK_CancelaTask"></a> Cancel a Task</span></span>  
 <span data-ttu-id="745d8-108">첫 번째 예제에서는 **취소** 단추를 단일 다운로드 작업에 연결합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-108">The first example associates the **Cancel** button with a single download task.</span></span> <span data-ttu-id="745d8-109">응용 프로그램이 콘텐츠를 다운로드하는 동안 단추를 선택하면 다운로드가 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-109">If you choose the button while the application is downloading content, the download is canceled.</span></span>  
  
### <a name="downloading-the-example"></a><span data-ttu-id="745d8-110">예제 다운로드</span><span class="sxs-lookup"><span data-stu-id="745d8-110">Downloading the Example</span></span>  
 <span data-ttu-id="745d8-111">[Async 샘플: 응용 프로그램 세부 조정](http://go.microsoft.com/fwlink/?LinkId=255046)에서 전체 WPF(Windows Presentation Foundation) 프로젝트를 다운로드한 후 다음 단계를 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-111">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="745d8-112">다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-112">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="745d8-113">메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-113">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="745d8-114">**프로젝트 열기** 대화 상자에서 압축을 해제한 샘플 코드가 포함된 폴더를 열고 AsyncFineTuningCS에 대한 솔루션(.sln) 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-114">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>  
  
4.  <span data-ttu-id="745d8-115">**솔루션 탐색기**에서 **CancelATask** 프로젝트에 대한 바로 가기 메뉴를 열고 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-115">In **Solution Explorer**, open the shortcut menu for the **CancelATask** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="745d8-116">F5 키를 선택하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-116">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="745d8-117">디버그하지 않고 프로젝트를 실행하려면 Ctrl+F5를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-117">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
 <span data-ttu-id="745d8-118">프로젝트를 다운로드하지 않으려는 경우 이 항목의 끝에 있는 MainWindow.xaml.cs 파일을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-118">If you don't want to download the project, you can review the MainWindow.xaml.cs files at the end of this topic.</span></span>  
  
### <a name="building-the-example"></a><span data-ttu-id="745d8-119">예제 빌드</span><span class="sxs-lookup"><span data-stu-id="745d8-119">Building the Example</span></span>  
 <span data-ttu-id="745d8-120">다음 변경 내용은 웹 사이트를 다운로드하는 응용 프로그램에 **취소** 단추를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-120">The following changes add a **Cancel** button to an application that downloads a website.</span></span> <span data-ttu-id="745d8-121">예제를 다운로드하거나 빌드하지 않으려면 이 항목의 끝에 있는 “전체 예제” 섹션에서 최종 결과를 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-121">If you don't want to download or build the example, you can review the final product in the "Complete Examples" section at the end of this topic.</span></span> <span data-ttu-id="745d8-122">코드에서 변경 내용에는 별표가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-122">Asterisks mark the changes in the code.</span></span>  
  
 <span data-ttu-id="745d8-123">직접 예제를 빌드하려면 "예제 다운로드" 섹션의 지침을 단계별로 따르지만 **시작 프로젝트**로 **CancelATask** 대신 **StarterCode**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-123">To build the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **StarterCode** as the **StartUp Project** instead of **CancelATask**.</span></span>  
  
 <span data-ttu-id="745d8-124">그리고 다음 변경 내용을 해당 프로젝트의 MainWindow.xaml.cs 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-124">Then add the following changes to the MainWindow.xaml.cs file of that project.</span></span>  
  
1.  <span data-ttu-id="745d8-125">액세스하는 모든 메서드에 대한 범위 내에 있는 `CancellationTokenSource` 변수 `cts`를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-125">Declare a `CancellationTokenSource` variable, `cts`, that’s in scope for all methods that access it.</span></span>  
  
    ```csharp  
    public partial class MainWindow : Window  
    {  
        // ***Declare a System.Threading.CancellationTokenSource.  
        CancellationTokenSource cts;  
    ```  
  
2.  <span data-ttu-id="745d8-126">**취소** 단추에 대한 다음 이벤트 처리기를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-126">Add the following event handler for the **Cancel** button.</span></span> <span data-ttu-id="745d8-127">이벤트 처리기는 <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName> 메서드를 사용하여 사용자가 취소를 요청할 때 `cts`에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-127">The event handler uses the <xref:System.Threading.CancellationTokenSource.Cancel%2A?displayProperty=fullName> method to notify `cts` when the user requests cancellation.</span></span>  
  
    ```csharp  
    // ***Add an event handler for the Cancel button.  
    private void cancelButton_Click(object sender, RoutedEventArgs e)  
    {  
        if (cts != null)  
        {  
            cts.Cancel();  
        }  
    }  
    ```  
  
3.  <span data-ttu-id="745d8-128">이벤트 처리기에서 **시작** 단추 `startButton_Click`을 다음과 같이 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-128">Make the following changes in the event handler for the **Start** button, `startButton_Click`.</span></span>  
  
    -   <span data-ttu-id="745d8-129">`CancellationTokenSource`, `cts`를 인스턴스화합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-129">Instantiate the `CancellationTokenSource`, `cts`.</span></span>  
  
        ```csharp  
        // ***Instantiate the CancellationTokenSource.  
        cts = new CancellationTokenSource();  
        ```  
  
    -   <span data-ttu-id="745d8-130">지정된 웹 사이트의 콘텐츠를 다운로드하는 `AccessTheWebAsync` 호출에서 `cts`의 <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName> 속성을 인수로 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-130">In the call to `AccessTheWebAsync`, which downloads the contents of a specified website, send the <xref:System.Threading.CancellationTokenSource.Token%2A?displayProperty=fullName> property of `cts` as an argument.</span></span> <span data-ttu-id="745d8-131">취소가 요청되면 `Token` 속성은 메시지를 전파합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-131">The `Token` property propagates the message if cancellation is requested.</span></span> <span data-ttu-id="745d8-132">사용자가 다운로드 작업을 취소하도록 선택할 경우 메시지를 표시하는 catch 블록을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-132">Add a catch block that displays a message if the user chooses to cancel the download operation.</span></span> <span data-ttu-id="745d8-133">다음 코드는 변경 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-133">The following code shows the changes.</span></span>  
  
        ```csharp  
        try  
        {  
            // ***Send a token to carry the message if cancellation is requested.  
            int contentLength = await AccessTheWebAsync(cts.Token);  
            resultsTextBox.Text +=  
                String.Format("\r\nLength of the downloaded string: {0}.\r\n", contentLength);  
        }  
        // *** If cancellation is requested, an OperationCanceledException results.  
        catch (OperationCanceledException)  
        {  
            resultsTextBox.Text += "\r\nDownload canceled.\r\n";  
        }  
        catch (Exception)  
        {  
            resultsTextBox.Text += "\r\nDownload failed.\r\n";  
        }  
        ```  
  
4.  <span data-ttu-id="745d8-134">`AccessTheWebAsync`에서 <xref:System.Net.Http.HttpClient> 형식에 있는 `GetAsync` 메서드의 <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName> 오버로드를 사용하여 웹 사이트의 콘텐츠를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-134">In `AccessTheWebAsync`, use the  <xref:System.Net.Http.HttpClient.GetAsync%28System.String%2CSystem.Threading.CancellationToken%29?displayProperty=fullName> overload of the `GetAsync` method in the <xref:System.Net.Http.HttpClient> type to download the contents of a website.</span></span> <span data-ttu-id="745d8-135">`AccessTheWebAsync`의 <xref:System.Threading.CancellationToken> 매개 변수인 `ct`를 두 번째 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-135">Pass `ct`, the <xref:System.Threading.CancellationToken> parameter of `AccessTheWebAsync`, as the second argument.</span></span> <span data-ttu-id="745d8-136">사용자가 **취소** 단추를 선택하면 토큰이 메시지를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-136">The token carries the message if the user chooses the **Cancel** button.</span></span>  
  
     <span data-ttu-id="745d8-137">다음 코드는 `AccessTheWebAsync`의 변경 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-137">The following code shows the changes in `AccessTheWebAsync`.</span></span>  
  
    ```csharp  
    // ***Provide a parameter for the CancellationToken.  
    async Task<int> AccessTheWebAsync(CancellationToken ct)  
    {  
        HttpClient client = new HttpClient();  
  
        resultsTextBox.Text +=  
            String.Format("\r\nReady to download.\r\n");  
  
        // You might need to slow things down to have a chance to cancel.  
        await Task.Delay(250);  
  
        // GetAsync returns a Task<HttpResponseMessage>.   
        // ***The ct argument carries the message if the Cancel button is chosen.  
        HttpResponseMessage response = await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct);  
  
        // Retrieve the website contents from the HttpResponseMessage.  
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
        // The result of the method is the length of the downloaded website.  
        return urlContents.Length;  
    }  
    ```  
  
5.  <span data-ttu-id="745d8-138">프로그램을 취소하지 않으면 다음 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-138">If you don’t cancel the program, it produces the following output.</span></span>  
  
    ```  
    Ready to download.  
    Length of the downloaded string: 158125.  
    ```  
  
     <span data-ttu-id="745d8-139">프로그램이 다운로드를 완료하기 전에 **취소** 단추를 선택하면 다음 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-139">If you choose the **Cancel** button before the program finishes downloading the content, the program produces the following output.</span></span>  
  
    ```  
    Ready to download.  
    Download canceled.  
    ```  
  
##  <span data-ttu-id="745d8-140"><a name="BKMK_CancelaListofTasks"></a> 작업 목록 취소</span><span class="sxs-lookup"><span data-stu-id="745d8-140"><a name="BKMK_CancelaListofTasks"></a> Cancel a List of Tasks</span></span>  
 <span data-ttu-id="745d8-141">이전 예제를 확장하여 같은 `CancellationTokenSource` 인스턴스를 각 작업과 연결하는 방식으로 여러 작업을 취소할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-141">You can extend the previous example to cancel many tasks by associating the same `CancellationTokenSource` instance with each task.</span></span> <span data-ttu-id="745d8-142">**취소** 단추를 선택하면 아직 완료되지 않은 모든 작업이 취소됩니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-142">If you choose the **Cancel** button, you cancel all tasks that aren’t yet complete.</span></span>  
  
### <a name="downloading-the-example"></a><span data-ttu-id="745d8-143">예제 다운로드</span><span class="sxs-lookup"><span data-stu-id="745d8-143">Downloading the Example</span></span>  
 <span data-ttu-id="745d8-144">[Async 샘플: 응용 프로그램 세부 조정](http://go.microsoft.com/fwlink/?LinkId=255046)에서 전체 WPF(Windows Presentation Foundation) 프로젝트를 다운로드한 후 다음 단계를 따를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-144">You can download the complete Windows Presentation Foundation (WPF) project from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046) and then follow these steps.</span></span>  
  
1.  <span data-ttu-id="745d8-145">다운로드한 파일의 압축을 푼 다음 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-145">Decompress the file that you downloaded, and then start Visual Studio.</span></span>  
  
2.  <span data-ttu-id="745d8-146">메뉴 모음에서 **파일**, **열기**, **프로젝트/솔루션**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-146">On the menu bar, choose **File**, **Open**, **Project/Solution**.</span></span>  
  
3.  <span data-ttu-id="745d8-147">**프로젝트 열기** 대화 상자에서 압축을 해제한 샘플 코드가 포함된 폴더를 열고 AsyncFineTuningCS에 대한 솔루션(.sln) 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-147">In the **Open Project** dialog box, open the folder that holds the sample code that you decompressed, and then open the solution (.sln) file for AsyncFineTuningCS.</span></span>  
  
4.  <span data-ttu-id="745d8-148">**솔루션 탐색기**에서 **CancelAListOfTasks** 프로젝트에 대한 바로 가기 메뉴를 열고 **시작 프로젝트로 설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-148">In **Solution Explorer**, open the shortcut menu for the **CancelAListOfTasks** project, and then choose **Set as StartUp Project**.</span></span>  
  
5.  <span data-ttu-id="745d8-149">F5 키를 선택하여 프로젝트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-149">Choose the F5 key to run the project.</span></span>  
  
     <span data-ttu-id="745d8-150">디버그하지 않고 프로젝트를 실행하려면 Ctrl+F5를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-150">Choose the Ctrl+F5 keys to run the project without debugging it.</span></span>  
  
 <span data-ttu-id="745d8-151">프로젝트를 다운로드하지 않으려는 경우 이 항목의 끝에 있는 MainWindow.xaml.cs 파일을 검토할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-151">If you don't want to download the project, you can review the MainWindow.xaml.cs files at the end of this topic.</span></span>  
  
### <a name="building-the-example"></a><span data-ttu-id="745d8-152">예제 빌드</span><span class="sxs-lookup"><span data-stu-id="745d8-152">Building the Example</span></span>  
 <span data-ttu-id="745d8-153">직접 예제를 확장하려면 "예제 다운로드" 섹션의 지침을 단계별로 따르되, **CancelATask**를 **시작 프로젝트**로 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-153">To extend the example yourself, step by step, follow the instructions in the "Downloading the Example" section, but choose **CancelATask** as the **StartUp Project**.</span></span> <span data-ttu-id="745d8-154">해당 프로젝트에 다음 변경 내용을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-154">Add the following changes to that project.</span></span> <span data-ttu-id="745d8-155">프로그램에서 변경 내용에는 별표가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-155">Asterisks mark the changes in the program.</span></span>  
  
1.  <span data-ttu-id="745d8-156">웹 주소 목록에 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-156">Add a method to create a list of web addresses.</span></span>  
  
    ```csharp  
    // ***Add a method that creates a list of web addresses.  
    private List<string> SetUpURLList()  
    {  
        List<string> urls = new List<string>   
        {   
            "http://msdn.microsoft.com",  
            "http://msdn.microsoft.com/library/hh290138.aspx",  
            "http://msdn.microsoft.com/library/hh290140.aspx",  
            "http://msdn.microsoft.com/library/dd470362.aspx",  
            "http://msdn.microsoft.com/library/aa578028.aspx",  
            "http://msdn.microsoft.com/library/ms404677.aspx",  
            "http://msdn.microsoft.com/library/ff730837.aspx"  
        };  
        return urls;  
    }  
    ```  
  
2.  <span data-ttu-id="745d8-157">`AccessTheWebAsync`에서 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-157">Call the method in `AccessTheWebAsync`.</span></span>  
  
    ```csharp  
    // ***Call SetUpURLList to make a list of web addresses.  
    List<string> urlList = SetUpURLList();  
    ```  
  
3.  <span data-ttu-id="745d8-158">`AccessTheWebAsync`에서 다음 루프를 추가하여 목록에 있는 각 웹 주소를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-158">Add the following loop in `AccessTheWebAsync` to process each web address in the list.</span></span>  
  
    ```csharp  
    // ***Add a loop to process the list of web addresses.  
    foreach (var url in urlList)  
    {  
        // GetAsync returns a Task<HttpResponseMessage>.   
        // Argument ct carries the message if the Cancel button is chosen.   
        // ***Note that the Cancel button can cancel all remaining downloads.  
        HttpResponseMessage response = await client.GetAsync(url, ct);  
  
        // Retrieve the website contents from the HttpResponseMessage.  
        byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
        resultsTextBox.Text +=  
            String.Format("\r\nLength of the downloaded string: {0}.\r\n", urlContents.Length);  
    }  
    ```  
  
4.  <span data-ttu-id="745d8-159">`AccessTheWebAsync`는 길이를 표시하므로 메서드가 아무것도 반환할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-159">Because `AccessTheWebAsync` displays the lengths, the method doesn't need to return anything.</span></span> <span data-ttu-id="745d8-160">return 문을 제거하고 메서드의 반환 형식을 <xref:System.Threading.Tasks.Task%601> 대신 <xref:System.Threading.Tasks.Task>로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-160">Remove the return statement, and change the return type of the method to <xref:System.Threading.Tasks.Task> instead of <xref:System.Threading.Tasks.Task%601>.</span></span>  
  
    ```csharp  
    async Task AccessTheWebAsync(CancellationToken ct)  
    ```  
  
     <span data-ttu-id="745d8-161">식 대신 문을 사용하여 `startButton_Click`에서 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-161">Call the method from `startButton_Click` by using a statement instead of an expression.</span></span>  
  
    ```csharp  
    await AccessTheWebAsync(cts.Token);  
    ```  
  
5.  <span data-ttu-id="745d8-162">프로그램을 취소하지 않으면 다음 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-162">If you don’t cancel the program, it produces the following output.</span></span>  
  
    ```  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Length of the downloaded string: 158124.  
  
    Length of the downloaded string: 204890.  
  
    Length of the downloaded string: 175488.  
  
    Length of the downloaded string: 145790.  
  
    Downloads complete.  
    ```  
  
     <span data-ttu-id="745d8-163">다운로드가 완료되기 전에 **취소** 단추를 선택하면 취소하기 전에 완료된 다운로드의 길이가 출력에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-163">If you choose the **Cancel** button before the downloads are complete, the output contains the lengths of the downloads that completed before the cancellation.</span></span>  
  
    ```  
    Length of the downloaded string: 35939.  
  
    Length of the downloaded string: 237682.  
  
    Length of the downloaded string: 128607.  
  
    Downloads canceled.  
    ```  
  
##  <span data-ttu-id="745d8-164"><a name="BKMK_CompleteExamples"></a> 전체 예제</span><span class="sxs-lookup"><span data-stu-id="745d8-164"><a name="BKMK_CompleteExamples"></a> Complete Examples</span></span>  
 <span data-ttu-id="745d8-165">다음 섹션에는 각각의 이전 예제에 대한 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-165">The following sections contain the code for each of the previous examples.</span></span> <span data-ttu-id="745d8-166"><xref:System.Net.Http>에 대한 참조를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-166">Notice that you must add a reference for <xref:System.Net.Http>.</span></span>  
  
 <span data-ttu-id="745d8-167">[Async 샘플: 응용 프로그램 미세 조정](http://go.microsoft.com/fwlink/?LinkId=255046)에서 프로젝트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-167">You can download the projects from [Async Sample: Fine Tuning Your Application](http://go.microsoft.com/fwlink/?LinkId=255046).</span></span>  
  
### <a name="cancel-a-task-example"></a><span data-ttu-id="745d8-168">작업 취소 예제</span><span class="sxs-lookup"><span data-stu-id="745d8-168">Cancel a Task Example</span></span>  
 <span data-ttu-id="745d8-169">다음 코드는 단일 작업을 취소하는 예제에 대한 전체 MainWindow.xaml.cs 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-169">The following code is the complete MainWindow.xaml.cs file for the example that cancels a single task.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Threading.Tasks;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
  
// Add a using directive and a reference for System.Net.Http.  
using System.Net.Http;  
  
// Add the following using directive for System.Threading.  
  
using System.Threading;  
namespace CancelATask  
{  
    public partial class MainWindow : Window  
    {  
        // ***Declare a System.Threading.CancellationTokenSource.  
        CancellationTokenSource cts;  
  
        public MainWindow()  
        {  
            InitializeComponent();  
        }  
  
        private async void startButton_Click(object sender, RoutedEventArgs e)  
        {  
            // ***Instantiate the CancellationTokenSource.  
            cts = new CancellationTokenSource();  
  
            resultsTextBox.Clear();  
  
            try  
            {  
                // ***Send a token to carry the message if cancellation is requested.  
                int contentLength = await AccessTheWebAsync(cts.Token);  
                resultsTextBox.Text +=  
                    String.Format("\r\nLength of the downloaded string: {0}.\r\n", contentLength);  
            }  
            // *** If cancellation is requested, an OperationCanceledException results.  
            catch (OperationCanceledException)  
            {  
                resultsTextBox.Text += "\r\nDownload canceled.\r\n";  
            }  
            catch (Exception)  
            {  
                resultsTextBox.Text += "\r\nDownload failed.\r\n";  
            }  
  
            // ***Set the CancellationTokenSource to null when the download is complete.  
            cts = null;   
        }  
  
        // ***Add an event handler for the Cancel button.  
        private void cancelButton_Click(object sender, RoutedEventArgs e)  
        {  
            if (cts != null)  
            {  
                cts.Cancel();  
            }  
        }  
  
        // ***Provide a parameter for the CancellationToken.  
        async Task<int> AccessTheWebAsync(CancellationToken ct)  
        {  
            HttpClient client = new HttpClient();  
  
            resultsTextBox.Text +=  
                String.Format("\r\nReady to download.\r\n");  
  
            // You might need to slow things down to have a chance to cancel.  
            await Task.Delay(250);  
  
            // GetAsync returns a Task<HttpResponseMessage>.   
            // ***The ct argument carries the message if the Cancel button is chosen.  
            HttpResponseMessage response = await client.GetAsync("http://msdn.microsoft.com/library/dd470362.aspx", ct);  
  
            // Retrieve the website contents from the HttpResponseMessage.  
            byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
            // The result of the method is the length of the downloaded website.  
            return urlContents.Length;  
        }  
    }  
  
    // Output for a successful download:  
  
    // Ready to download.  
  
    // Length of the downloaded string: 158125.  
  
    // Or, if you cancel:  
  
    // Ready to download.  
  
    // Download canceled.  
}  
```  
  
### <a name="cancel-a-list-of-tasks-example"></a><span data-ttu-id="745d8-170">작업 목록 취소 예제</span><span class="sxs-lookup"><span data-stu-id="745d8-170">Cancel a List of Tasks Example</span></span>  
 <span data-ttu-id="745d8-171">다음 코드는 작업 목록을 취소하는 예제에 대한 전체 MainWindow.xaml.cs 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="745d8-171">The following code is the complete MainWindow.xaml.cs file for the example that cancels a list of tasks.</span></span>  
  
```csharp  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.Text;  
using System.Threading.Tasks;  
using System.Windows;  
using System.Windows.Controls;  
using System.Windows.Data;  
using System.Windows.Documents;  
using System.Windows.Input;  
using System.Windows.Media;  
using System.Windows.Media.Imaging;  
using System.Windows.Navigation;  
using System.Windows.Shapes;  
  
// Add a using directive and a reference for System.Net.Http.  
using System.Net.Http;  
  
// Add the following using directive for System.Threading.  
using System.Threading;  
  
namespace CancelAListOfTasks  
{  
    public partial class MainWindow : Window  
    {  
        // Declare a System.Threading.CancellationTokenSource.  
        CancellationTokenSource cts;  
  
        public MainWindow()  
        {  
            InitializeComponent();  
        }  
  
        private async void startButton_Click(object sender, RoutedEventArgs e)  
        {  
            // Instantiate the CancellationTokenSource.  
            cts = new CancellationTokenSource();  
  
            resultsTextBox.Clear();  
  
            try  
            {  
                await AccessTheWebAsync(cts.Token);  
                // ***Small change in the display lines.  
                resultsTextBox.Text += "\r\nDownloads complete.";  
            }  
            catch (OperationCanceledException)  
            {  
                resultsTextBox.Text += "\r\nDownloads canceled.";  
            }  
            catch (Exception)  
            {  
                resultsTextBox.Text += "\r\nDownloads failed.";  
            }  
  
            // Set the CancellationTokenSource to null when the download is complete.  
            cts = null;  
        }  
  
        // Add an event handler for the Cancel button.  
        private void cancelButton_Click(object sender, RoutedEventArgs e)  
        {  
            if (cts != null)  
            {  
                cts.Cancel();  
            }  
        }  
  
        // Provide a parameter for the CancellationToken.  
        // ***Change the return type to Task because the method has no return statement.  
        async Task AccessTheWebAsync(CancellationToken ct)  
        {  
            // Declare an HttpClient object.  
            HttpClient client = new HttpClient();  
  
            // ***Call SetUpURLList to make a list of web addresses.  
            List<string> urlList = SetUpURLList();  
  
            // ***Add a loop to process the list of web addresses.  
            foreach (var url in urlList)  
            {  
                // GetAsync returns a Task<HttpResponseMessage>.   
                // Argument ct carries the message if the Cancel button is chosen.   
                // ***Note that the Cancel button can cancel all remaining downloads.  
                HttpResponseMessage response = await client.GetAsync(url, ct);  
  
                // Retrieve the website contents from the HttpResponseMessage.  
                byte[] urlContents = await response.Content.ReadAsByteArrayAsync();  
  
                resultsTextBox.Text +=  
                    String.Format("\r\nLength of the downloaded string: {0}.\r\n", urlContents.Length);  
            }  
        }  
  
        // ***Add a method that creates a list of web addresses.  
        private List<string> SetUpURLList()  
        {  
            List<string> urls = new List<string>   
            {   
                "http://msdn.microsoft.com",  
                "http://msdn.microsoft.com/library/hh290138.aspx",  
                "http://msdn.microsoft.com/library/hh290140.aspx",  
                "http://msdn.microsoft.com/library/dd470362.aspx",  
                "http://msdn.microsoft.com/library/aa578028.aspx",  
                "http://msdn.microsoft.com/library/ms404677.aspx",  
                "http://msdn.microsoft.com/library/ff730837.aspx"  
            };  
            return urls;  
        }  
    }  
  
    // Output if you do not choose to cancel:  
  
    //Length of the downloaded string: 35939.  
  
    //Length of the downloaded string: 237682.  
  
    //Length of the downloaded string: 128607.  
  
    //Length of the downloaded string: 158124.  
  
    //Length of the downloaded string: 204890.  
  
    //Length of the downloaded string: 175488.  
  
    //Length of the downloaded string: 145790.  
  
    //Downloads complete.  
  
    // Sample output if you choose to cancel:  
  
    //Length of the downloaded string: 35939.  
  
    //Length of the downloaded string: 237682.  
  
    //Length of the downloaded string: 128607.  
  
    //Downloads canceled.  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="745d8-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="745d8-172">See Also</span></span>  
 <span data-ttu-id="745d8-173"><xref:System.Threading.CancellationTokenSource></span><span class="sxs-lookup"><span data-stu-id="745d8-173"><xref:System.Threading.CancellationTokenSource></span></span>   
 <span data-ttu-id="745d8-174"><xref:System.Threading.CancellationToken></span><span class="sxs-lookup"><span data-stu-id="745d8-174"><xref:System.Threading.CancellationToken></span></span>   
 <span data-ttu-id="745d8-175">[async 및 await를 사용한 비동기 프로그래밍(C#)](../../../../csharp/programming-guide/concepts/async/index.md) </span><span class="sxs-lookup"><span data-stu-id="745d8-175">[Asynchronous Programming with async and await (C#)](../../../../csharp/programming-guide/concepts/async/index.md) </span></span>  
 <span data-ttu-id="745d8-176">[Async 응용 프로그램 미세 조정(C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span><span class="sxs-lookup"><span data-stu-id="745d8-176">[Fine-Tuning Your Async Application (C#)](../../../../csharp/programming-guide/concepts/async/fine-tuning-your-async-application.md) </span></span>  
 [<span data-ttu-id="745d8-177">Async 샘플: 응용 프로그램 미세 조정</span><span class="sxs-lookup"><span data-stu-id="745d8-177">Async Sample: Fine Tuning Your Application</span></span>](http://go.microsoft.com/fwlink/?LinkId=255046)

