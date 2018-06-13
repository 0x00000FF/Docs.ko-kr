---
title: '방법: 서로 다른 파일의 콘텐츠 조인(LINQ)(C#)'
ms.date: 07/20/2015
ms.assetid: aa2d12a6-70a9-492f-a6db-b2b850d46811
ms.openlocfilehash: c6af2c0f90d3ebb69438b670a4f0cecb10d8d2fc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33319171"
---
# <a name="how-to-join-content-from-dissimilar-files-linq-c"></a><span data-ttu-id="3e1cf-102">방법: 서로 다른 파일의 콘텐츠 조인(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="3e1cf-102">How to: Join Content from Dissimilar Files (LINQ) (C#)</span></span>
<span data-ttu-id="3e1cf-103">이 예제에서는 일치하는 키로 사용되는 공통 값을 공유하는 두 개의 쉼표로 구분된 파일의 데이터를 조인하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3e1cf-103">This example shows how to join data from two comma-delimited files that share a common value that is used as a matching key.</span></span> <span data-ttu-id="3e1cf-104">이 방법은 두 스프레드시트나 한 스프레드시트와 다른 형식으로 된 파일의 데이터를 하나의 새 파일로 결합해야 하는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e1cf-104">This technique can be useful if you have to combine data from two spreadsheets, or from a spreadsheet and from a file that has another format, into a new file.</span></span> <span data-ttu-id="3e1cf-105">모든 종류의 구조적 텍스트에서 작동하도록 예제를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3e1cf-105">You can modify the example to work with any kind of structured text.</span></span>  
  
### <a name="to-create-the-data-files"></a><span data-ttu-id="3e1cf-106">데이터 파일을 만들려면</span><span class="sxs-lookup"><span data-stu-id="3e1cf-106">To create the data files</span></span>  
  
1.  <span data-ttu-id="3e1cf-107">다음 줄을 scores.csv 파일에 복사하고 파일을 프로젝트 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1cf-107">Copy the following lines into a file that is named scores.csv and save it to your project folder.</span></span> <span data-ttu-id="3e1cf-108">파일은 스프레드시트 데이터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e1cf-108">The file represents spreadsheet data.</span></span> <span data-ttu-id="3e1cf-109">열 1은 학생 ID이고, 열 2-5는 시험 점수입니다.</span><span class="sxs-lookup"><span data-stu-id="3e1cf-109">Column 1 is the student's ID, and columns 2 through 5 are test scores.</span></span>  
  
    ```  
    111, 97, 92, 81, 60  
    112, 75, 84, 91, 39  
    113, 88, 94, 65, 91  
    114, 97, 89, 85, 82  
    115, 35, 72, 91, 70  
    116, 99, 86, 90, 94  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    119, 68, 79, 88, 92  
    120, 99, 82, 81, 79  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    ```  
  
2.  <span data-ttu-id="3e1cf-110">다음 줄을 names.csv 파일에 복사하고 파일을 프로젝트 폴더에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="3e1cf-110">Copy the following lines into a file that is named names.csv and save it to your project folder.</span></span> <span data-ttu-id="3e1cf-111">파일은 학생의 성, 이름 및 학생 ID를 포함하는 스프레드시트를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="3e1cf-111">The file represents a spreadsheet that contains the student's last name, first name, and student ID.</span></span>  
  
    ```  
    Omelchenko,Svetlana,111  
    O'Donnell,Claire,112  
    Mortensen,Sven,113  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Hugo,118  
    Tucker,Lance,119  
    Adams,Terry,120  
    Zabokritski,Eugene,121  
    Tucker,Michael,122  
    ```  
  
## <a name="example"></a><span data-ttu-id="3e1cf-112">예</span><span class="sxs-lookup"><span data-stu-id="3e1cf-112">Example</span></span>  
  
```csharp  
class JoinStrings  
{  
    static void Main()  
    {  
        // Join content from dissimilar files that contain  
        // related information. File names.csv contains the student  
        // name plus an ID number. File scores.csv contains the ID   
        // and a set of four test scores. The following query joins  
        // the scores to the student names by using ID as a  
        // matching key.  
  
        string[] names = System.IO.File.ReadAllLines(@"../../../names.csv");  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Name:    Last[0],       First[1],  ID[2]  
        //          Omelchenko,    Svetlana,  11  
        // Score:   StudentID[0],  Exam1[1]   Exam2[2],  Exam3[3],  Exam4[4]  
        //          111,           97,        92,        81,        60  
  
        // This query joins two dissimilar spreadsheets based on common ID value.  
        // Multiple from clauses are used instead of a join clause  
        // in order to store results of id.Split.  
        IEnumerable<string> scoreQuery1 =  
            from name in names  
            let nameFields = name.Split(',')  
            from id in scores  
            let scoreFields = id.Split(',')  
            where nameFields[2] == scoreFields[0]  
            select nameFields[0] + "," + scoreFields[1] + "," + scoreFields[2]   
                   + "," + scoreFields[3] + "," + scoreFields[4];  
  
        // Pass a query variable to a method and execute it  
        // in the method. The query itself is unchanged.  
        OutputQueryResults(scoreQuery1, "Merge two spreadsheets:");  
  
        // Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    static void OutputQueryResults(IEnumerable<string> query, string message)  
    {  
        Console.WriteLine(System.Environment.NewLine + message);  
        foreach (string item in query)  
        {  
            Console.WriteLine(item);  
        }  
        Console.WriteLine("{0} total names in list", query.Count());  
    }  
}  
/* Output:  
Merge two spreadsheets:  
Adams, 99, 82, 81, 79  
Fakhouri, 99, 86, 90, 94  
Feng, 93, 92, 80, 87  
Garcia, 97, 89, 85, 82  
Garcia, 35, 72, 91, 70  
Garcia, 92, 90, 83, 78  
Mortensen, 88, 94, 65, 91  
O'Donnell, 75, 84, 91, 39  
Omelchenko, 97, 92, 81, 60  
Tucker, 68, 79, 88, 92  
Tucker, 94, 92, 91, 91  
Zabokritski, 96, 85, 91, 60  
12 total names in list  
 */  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="3e1cf-113">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="3e1cf-113">Compiling the Code</span></span>  
 <span data-ttu-id="3e1cf-114">System.Core.dll에 대한 참조와 System.Linq 및 System.IO 네임스페이스에 대한 `using` 지시문을 사용하여 .NET Framework 버전 3.5 이상을 대상으로 하는 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3e1cf-114">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e1cf-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3e1cf-115">See Also</span></span>  
 [<span data-ttu-id="3e1cf-116">LINQ 및 문자열(C#)</span><span class="sxs-lookup"><span data-stu-id="3e1cf-116">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)  
 [<span data-ttu-id="3e1cf-117">LINQ 및 파일 디렉터리(C#)</span><span class="sxs-lookup"><span data-stu-id="3e1cf-117">LINQ and File Directories (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
