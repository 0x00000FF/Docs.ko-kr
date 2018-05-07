---
title: '방법: Async를 사용 하 여 병렬로 여러 웹 요청 만들기 및 Await (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: a894b99b-7cfd-4a38-adfb-20d24f986730
ms.openlocfilehash: 1b98a0f29409fa49af1c9c8f7c91f2170981f7cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-make-multiple-web-requests-in-parallel-by-using-async-and-await-visual-basic"></a>방법: Async를 사용 하 여 병렬로 여러 웹 요청 만들기 및 Await (Visual Basic)
비동기 메서드에서 작업은 만들어질 때 시작됩니다. [Await](../../../../visual-basic/language-reference/operators/await-operator.md) 연산자를 계속할 수 없습니다 작업이 완료 될 때까지 메서드의 지점에서 작업에 적용 됩니다. 다음 예제와 같이 작업이 생성되는 즉시 대기되는 경우가 많습니다.  
  
```vb  
Dim result = Await someWebAccessMethodAsync(url)  
```  
  
 그러나 프로그램에서 작업 완료에 의존하지 않는 다른 작업을 수행해야 하는 경우 작업 생성과 작업 대기를 구분할 수 있습니다.  
  
```vb  
' The following line creates and starts the task.  
Dim myTask = someWebAccessMethodAsync(url)  
  
' While the task is running, you can do other work that does not depend  
' on the results of the task.  
' . . . . .  
  
' The application of Await suspends the rest of this method until the task is   
' complete.  
Dim result = Await myTask  
```  
  
 작업 시작과 작업 대기 사이에 다른 작업을 시작할 수 있습니다. 추가 작업은 암시적으로 병렬로 실행되지만 추가 스레드는 생성되지 않습니다.  
  
 다음 프로그램은 세 개의 비동기 웹 다운로드를 시작한 다음 호출된 순서대로 대기합니다. 프로그램을 실행할 때 작업이 항상 생성 및 대기된 순서로 완료되지는 않습니다. 작업은 생성 시 실행을 시작하고, 메서드가 await 식에 도달하기 전에 작업 중 하나 이상이 완료될 수도 있습니다.  
  
> [!NOTE]
>  이 프로젝트를 완료하려면 Visual Studio 2012 이상 및 .NET Framework 4.5 이상이 컴퓨터에 설치되어 있어야 합니다.  
  
 동시에 여러 작업을 시작 하는 또 다른 예로, 참조 [하는 방법: Task.WhenAll (Visual Basic)를 사용 하 여 비동기 연습 확장](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)합니다.  
  
 이 예제의 코드는 [개발자 코드 샘플](http://go.microsoft.com/fwlink/?LinkId=254906)에서 다운로드할 수 있습니다.  
  
### <a name="to-set-up-the-project"></a>프로젝트를 설정하려면  
  
1.  WPF 응용 프로그램을 설정하려면 다음 단계를 완료합니다. 이러한 단계에 대 한 자세한 지침을 찾을 수 [연습:를 사용 하 여 Async 및 Await (Visual Basic) 하 여 웹 서비스에 액세스](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)합니다.  
  
    -   텍스트 상자와 단추가 포함된 WPF 응용 프로그램을 만듭니다. 단추의 이름을 `startButton`, 텍스트 상자의 이름을 `resultsTextBox`로 지정합니다.  
  
    -   <xref:System.Net.Http>에 대한 참조를 추가합니다.  
  
    -   MainWindow.xaml.vb 파일에 추가 `Imports` 문을 `System.Net.Http`합니다.  
  
### <a name="to-add-the-code"></a>코드를 추가하려면  
  
1.  디자인 창 MainWindow.xaml에서에서 만들기 단추를 두 번 클릭은 `startButton_Click` MainWindow.xaml.vb의 이벤트 처리기입니다.  
  
2.  다음 코드를 복사 하 고 본문에 붙여 `startButton_Click` MainWindow.xaml.vb에 있습니다.  
  
    ```vb  
    resultsTextBox.Clear()  
    Await CreateMultipleTasksAsync()  
    resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    ```  
  
     코드는 응용 프로그램을 구동하는 비동기 메서드 `CreateMultipleTasksAsync`를 호출합니다.  
  
3.  프로젝트에 다음과 같은 지원 메서드를 추가합니다.  
  
    -   `ProcessURLAsync`는 <xref:System.Net.Http.HttpClient> 메서드를 사용하여 웹 사이트 내용을 바이트 배열로 다운로드합니다. 그런 다음 지원 메서드 `ProcessURLAsync`는 배열의 길이를 표시하고 반환합니다.  
  
    -   `DisplayResults`에 각 URL에 대한 바이트 배열의 바이트 수가 표시됩니다. 이 표시는 각 작업의 다운로드가 완료된 시간을 보여 줍니다.  
  
     다음 메서드를 복사한 후 붙여는 `startButton_Click` MainWindow.xaml.vb의 이벤트 처리기입니다.  
  
    ```vb  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
    ```  
  
4.  마지막으로, 다음 단계를 수행하는 `CreateMultipleTasksAsync` 메서드를 정의합니다.  
  
    -   이 메서드는 `ProcessURLAsync`의 <xref:System.Net.Http.HttpClient.GetByteArrayAsync%2A> 메서드에 액세스하는 데 필요한 `HttpClient` 개체를 선언합니다.  
  
    -   메서드는 `TResult`가 정수인 <xref:System.Threading.Tasks.Task%601> 형식의 세 가지 작업을 만들고 시작합니다. 각 작업이 완료되면 `DisplayResults`에 작업의 URL 및 다운로드한 콘텐츠의 길이가 표시됩니다. 작업이 비동기적으로 실행되므로 결과가 표시되는 순서는 선언된 순서와 다를 수 있습니다.  
  
    -   메서드는 각 작업이 완료될 때까지 기다립니다. 각 `Await` 연산자는 대기된 작업이 완료될 때까지 `CreateMultipleTasksAsync`의 실행을 중단합니다. 또한 연산자는 완료된 각 작업에서 `ProcessURLAsync` 호출의 반환 값을 검색합니다.  
  
    -   작업이 완료되고 정수 값이 검색된 경우 메서드는 웹 사이트의 길이를 합산하고 결과를 표시합니다.  
  
     다음 메서드를 복사하고 솔루션에 붙여넣습니다.  
  
    ```vb  
    Private Async Function CreateMultipleTasksAsync() As Task  
  
        ' Declare an HttpClient object, and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Create and start the tasks. As each task finishes, DisplayResults   
        ' displays its length.  
        Dim download1 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com", client)  
        Dim download2 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)  
        Dim download3 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/67w7t67f.aspx", client)  
  
        ' Await each task.  
        Dim length1 As Integer = Await download1  
        Dim length2 As Integer = Await download2  
        Dim length3 As Integer = Await download3  
  
        Dim total As Integer = length1 + length2 + length3  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
    ```  
  
5.  F5 키를 선택하여 프로그램을 실행한 다음 **시작** 단추를 선택합니다.  
  
     프로그램을 여러 번 실행하여 세 가지 작업이 항상 동일한 순서로 완료되지는 않으며, 완료되는 순서가 생성 및 대기된 순서와 다를 수도 있음을 확인합니다.  
  
## <a name="example"></a>예제  
 다음 코드에는 전체 예제가 포함되어 있습니다.  
  
```vb  
' Add the following Imports statements, and add a reference for System.Net.Http.  
Imports System.Net.Http  
  
Class MainWindow  
  
    Async Sub startButton_Click(sender As Object, e As RoutedEventArgs) Handles startButton.Click  
        resultsTextBox.Clear()  
        Await CreateMultipleTasksAsync()  
        resultsTextBox.Text &= vbCrLf & "Control returned to button1_Click."  
    End Sub  
  
    Private Async Function CreateMultipleTasksAsync() As Task  
  
        ' Declare an HttpClient object, and increase the buffer size. The  
        ' default buffer size is 65,536.  
        Dim client As HttpClient =  
            New HttpClient() With {.MaxResponseContentBufferSize = 1000000}  
  
        ' Create and start the tasks. As each task finishes, DisplayResults   
        ' displays its length.  
        Dim download1 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com", client)  
        Dim download2 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/hh156528(VS.110).aspx", client)  
        Dim download3 As Task(Of Integer) =  
            ProcessURLAsync("http://msdn.microsoft.com/library/67w7t67f.aspx", client)  
  
        ' Await each task.  
        Dim length1 As Integer = Await download1  
        Dim length2 As Integer = Await download2  
        Dim length3 As Integer = Await download3  
  
        Dim total As Integer = length1 + length2 + length3  
  
        ' Display the total count for all of the websites.  
        resultsTextBox.Text &= String.Format(vbCrLf & vbCrLf &  
                                             "Total bytes returned:  {0}" & vbCrLf, total)  
    End Function  
  
    Private Async Function ProcessURLAsync(url As String, client As HttpClient) As Task(Of Integer)  
  
        Dim byteArray = Await client.GetByteArrayAsync(url)  
        DisplayResults(url, byteArray)  
        Return byteArray.Length  
    End Function  
  
    Private Sub DisplayResults(url As String, content As Byte())  
  
        ' Display the length of each website. The string format   
        ' is designed to be used with a monospaced font, such as  
        ' Lucida Console or Global Monospace.  
        Dim bytes = content.Length  
        ' Strip off the "http://".  
        Dim displayURL = url.Replace("http://", "")  
        resultsTextBox.Text &= String.Format(vbCrLf & "{0,-58} {1,8}", displayURL, bytes)  
    End Sub  
End Class  
```  
  
## <a name="see-also"></a>참고 항목  
 [연습: Async 및 Await를 사용하여 웹에 액세스(Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/walkthrough-accessing-the-web-by-using-async-and-await.md)  
 [Async 및 Await를 사용한 비동기 프로그래밍(Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/index.md)  
 [방법: Task.WhenAll을 사용하여 비동기 연습 확장(Visual Basic)](../../../../visual-basic/programming-guide/concepts/async/how-to-extend-the-async-walkthrough-by-using-task-whenall.md)
