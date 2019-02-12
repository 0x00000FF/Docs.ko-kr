---
title: 이진 데이터 검색
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 56c5a9e3-31f1-482f-bce0-ff1c41a658d0
ms.openlocfilehash: 7b0cfb9273603850d2451245b81f1bb651f16d56
ms.sourcegitcommit: d2ccb199ae6bc5787b4762e9ea6d3f6fe88677af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/12/2019
ms.locfileid: "56094063"
---
# <a name="retrieving-binary-data"></a><span data-ttu-id="16e9b-102">이진 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="16e9b-102">Retrieving Binary Data</span></span>
<span data-ttu-id="16e9b-103">기본적으로 **DataReader** 데이터의 전체 행 수와 행으로 들어오는 데이터를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-103">By default, the **DataReader** loads incoming data as a row as soon as an entire row of data is available.</span></span> <span data-ttu-id="16e9b-104">그러나 BLOB(Binary Large Object)는 단일 행에 포함할 수 없는 기가바이트 데이터를 포함할 수 있으므로 다르게 처리되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-104">Binary large objects (BLOBs) need different treatment, however, because they can contain gigabytes of data that cannot be contained in a single row.</span></span> <span data-ttu-id="16e9b-105">합니다 **Command.ExecuteReader** 메서드가 걸리는 오버 로드를 <xref:System.Data.CommandBehavior> 의 기본 동작을 수정 하는 인수를 **DataReader**합니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-105">The **Command.ExecuteReader** method has an overload that will take a <xref:System.Data.CommandBehavior> argument to modify the default behavior of the **DataReader**.</span></span> <span data-ttu-id="16e9b-106">전달할 수 있습니다 <xref:System.Data.CommandBehavior.SequentialAccess> 에 **ExecuteReader** 의 기본 동작을 수정 하는 방법의 **DataReader** 데이터 행을 로드 하는 대신 해당 데이터를 로드 합니다 순차적으로 받으면 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-106">You can pass <xref:System.Data.CommandBehavior.SequentialAccess> to the **ExecuteReader** method to modify the default behavior of the **DataReader** so that instead of loading rows of data, it will load data sequentially as it is received.</span></span> <span data-ttu-id="16e9b-107">이것은 BLOB 또는 기타 대형 데이터 구조를 로드하는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-107">This is ideal for loading BLOBs or other large data structures.</span></span> <span data-ttu-id="16e9b-108">이 동작은 데이터 소스에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-108">Note that this behavior may depend on your data source.</span></span> <span data-ttu-id="16e9b-109">예를 들어, Microsoft Access에서 BLOB를 반환할 경우에는 BLOB를 받을 때 데이터를 순서대로 로드하는 것이 아니라 전체 BLOB를 메모리에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-109">For example, returning a BLOB from Microsoft Access will load the entire BLOB being loaded into memory, rather than sequentially as it is received.</span></span>  
  
 <span data-ttu-id="16e9b-110">설정 하는 경우는 **DataReader** 사용 하 **SequentialAccess**를 반환 하는 필드에 액세스할 수 있는 시퀀스를 참고 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-110">When setting the **DataReader** to use **SequentialAccess**, it is important to note the sequence in which you access the fields returned.</span></span> <span data-ttu-id="16e9b-111">기본 동작을 **DataReader**을 다음 행을 읽을 때까지 임의의 순서로 반환 된 필드에 액세스할 수 있습니다 가능 하다는 즉시 전체 행을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-111">The default behavior of the **DataReader**, which loads an entire row as soon as it is available, allows you to access the fields returned in any order until the next row is read.</span></span> <span data-ttu-id="16e9b-112">그러나 사용 하는 경우 **SequentialAccess** 가 반환한 필드에 액세스 해야 합니다 합니다 **DataReader** 순서로 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-112">When using **SequentialAccess** however, you must access the fields returned by the **DataReader** in order.</span></span> <span data-ttu-id="16e9b-113">예를 들어, 쿼리에서 세 열을 반환하고 그 셋째 열이 BLOB이면 셋째 필드의 BLOB 데이터에 액세스하기 전에 첫째와 둘째 필드의 값을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-113">For example, if your query returns three columns, the third of which is a BLOB, you must return the values of the first and second fields before accessing the BLOB data in the third field.</span></span> <span data-ttu-id="16e9b-114">첫째나 둘째 필드에 액세스하기 전에 셋째 필드에 액세스하면 첫째와 둘째 필드 값을 더 이상 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-114">If you access the third field before the first or second fields, the first and second field values are no longer available.</span></span> <span data-ttu-id="16e9b-115">때문에 이것이 **SequentialAccess** 가 수정 합니다 **DataReader** 데이터 순서 및 데이터의 반환을 사용할 수 없는 후는 **DataReader** 것을 넘어 읽으려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-115">This is because **SequentialAccess** has modified the **DataReader** to return data in sequence and the data is not available after the **DataReader** has read past it.</span></span>  
  
 <span data-ttu-id="16e9b-116">BLOB 필드의 데이터에 액세스할 때 사용 합니다 **GetBytes** 또는 **GetChars** 의 형식화 된 접근자는 **DataReader**, 배열을 데이터로 채우는 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-116">When accessing the data in the BLOB field, use the **GetBytes** or **GetChars** typed accessors of the **DataReader**, which fill an array with data.</span></span> <span data-ttu-id="16e9b-117">사용할 수도 있습니다 **GetString** 문자 데이터에 대해 단 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-117">You can also use **GetString** for character data; however.</span></span> <span data-ttu-id="16e9b-118">하지만 시스템 리소스를 절약하기 위해 전체 BLOB 값을 단일 문자열 변수에 로드하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-118">to conserve system resources you might not want to load an entire BLOB value into a single string variable.</span></span> <span data-ttu-id="16e9b-119">대신 반환될 데이터의 특정 버퍼 크기와 반환된 데이터에서 읽은 첫째 바이트 또는 문자의 시작 위치를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-119">You can instead specify a specific buffer size of data to be returned, and a starting location for the first byte or character to be read from the returned data.</span></span> <span data-ttu-id="16e9b-120">**GetBytes** 및 **GetChars** 돌아갑니다는 `long` 반환 하는 문자 또는 바이트의 수를 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-120">**GetBytes** and **GetChars** will return a `long` value, which represents the number of bytes or characters returned.</span></span> <span data-ttu-id="16e9b-121">Null 배열을 전달 하는 경우 **GetBytes** 하거나 **GetChars**를 long 값 BLOB 문자 또는 바이트의 총 수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-121">If you pass a null array to **GetBytes** or **GetChars**, the long value returned will be the total number of bytes or characters in the BLOB.</span></span> <span data-ttu-id="16e9b-122">배열의 인덱스를 읽고 있는 데이터의 시작 위치로서 선택적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-122">You can optionally specify an index in the array as a starting position for the data being read.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16e9b-123">예제</span><span class="sxs-lookup"><span data-stu-id="16e9b-123">Example</span></span>  
 <span data-ttu-id="16e9b-124">다음 예제에서는 게시자 ID와 로고를 반환 합니다 **pubs** Microsoft SQL server에서 예제 데이터베이스.</span><span class="sxs-lookup"><span data-stu-id="16e9b-124">The following example returns the publisher ID and logo from the **pubs** sample database in Microsoft SQL Server.</span></span> <span data-ttu-id="16e9b-125">게시자 ID(`pub_id`)는 문자 필드이고 로고는 BLOB 이미지입니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-125">The publisher ID (`pub_id`) is a character field, and the logo is an image, which is a BLOB.</span></span> <span data-ttu-id="16e9b-126">때문에 합니다 **로고** 필드는 비트맵 이므로 예에서는 이진 데이터를 사용 하 여 반환 **GetBytes**합니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-126">Because the **logo** field is a bitmap, the example returns binary data using **GetBytes**.</span></span> <span data-ttu-id="16e9b-127">필드에 순차적으로 액세스해야 하므로 현재 데이터 행에 대해 게시자 ID가 로고에 앞서 액세스됩니다.</span><span class="sxs-lookup"><span data-stu-id="16e9b-127">Notice that the publisher ID is accessed for the current row of data before the logo, because the fields must be accessed sequentially.</span></span>  
  
```vb  
' Assumes that connection is a valid SqlConnection object.  
Dim command As SqlCommand = New SqlCommand( _  
  "SELECT pub_id, logo FROM pub_info", connection)  
  
' Writes the BLOB to a file (*.bmp).  
Dim stream As FileStream                   
' Streams the binary data to the FileStream object.  
Dim writer As BinaryWriter                 
' The size of the BLOB buffer.  
Dim bufferSize As Integer = 100        
' The BLOB byte() buffer to be filled by GetBytes.  
Dim outByte(bufferSize - 1) As Byte    
' The bytes returned from GetBytes.  
Dim retval As Long                     
' The starting position in the BLOB output.  
Dim startIndex As Long = 0             
  
' The publisher id to use in the file name.  
Dim pubID As String = ""              
  
' Open the connection and read data into the DataReader.  
connection.Open()  
Dim reader As SqlDataReader = command.ExecuteReader(CommandBehavior.SequentialAccess)  
  
Do While reader.Read()  
  ' Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0)  
  
  ' Create a file to hold the output.  
  stream = New FileStream( _  
    "logo" & pubID & ".bmp", FileMode.OpenOrCreate, FileAccess.Write)  
  writer = New BinaryWriter(stream)  
  
  ' Reset the starting byte for a new BLOB.  
  startIndex = 0  
  
  ' Read bytes into outByte() and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  
  ' Continue while there are bytes beyond the size of the buffer.  
  Do While retval = bufferSize  
    writer.Write(outByte)  
    writer.Flush()  
  
    ' Reposition start index to end of the last buffer and fill buffer.  
    startIndex += bufferSize  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize)  
  Loop  
  
  ' Write the remaining buffer.  
  writer.Write(outByte, 0 , retval - 1)  
  writer.Flush()  
  
  ' Close the output file.  
  writer.Close()  
  stream.Close()  
Loop  
  
' Close the reader and the connection.  
reader.Close()  
connection.Close()  
```  
  
```csharp  
// Assumes that connection is a valid SqlConnection object.  
SqlCommand command = new SqlCommand(  
  "SELECT pub_id, logo FROM pub_info", connection);  
  
// Writes the BLOB to a file (*.bmp).  
FileStream stream;                            
// Streams the BLOB to the FileStream object.  
BinaryWriter writer;                          
  
// Size of the BLOB buffer.  
int bufferSize = 100;                     
// The BLOB byte[] buffer to be filled by GetBytes.  
byte[] outByte = new byte[bufferSize];    
// The bytes returned from GetBytes.  
long retval;                              
// The starting position in the BLOB output.  
long startIndex = 0;                      
  
// The publisher id to use in the file name.  
string pubID = "";                       
  
// Open the connection and read data into the DataReader.  
connection.Open();  
SqlDataReader reader = command.ExecuteReader(CommandBehavior.SequentialAccess);  
  
while (reader.Read())  
{  
  // Get the publisher id, which must occur before getting the logo.  
  pubID = reader.GetString(0);    
  
  // Create a file to hold the output.  
  stream = new FileStream(  
    "logo" + pubID + ".bmp", FileMode.OpenOrCreate, FileAccess.Write);  
  writer = new BinaryWriter(stream);  
  
  // Reset the starting byte for the new BLOB.  
  startIndex = 0;  
  
  // Read bytes into outByte[] and retain the number of bytes returned.  
  retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  
  // Continue while there are bytes beyond the size of the buffer.  
  while (retval == bufferSize)  
  {  
    writer.Write(outByte);  
    writer.Flush();  
  
    // Reposition start index to end of last buffer and fill buffer.  
    startIndex += bufferSize;  
    retval = reader.GetBytes(1, startIndex, outByte, 0, bufferSize);  
  }  
  
  // Write the remaining buffer.  
  writer.Write(outByte, 0, (int)retval);  
  writer.Flush();  
  
  // Close the output file.  
  writer.Close();  
  stream.Close();  
}  
  
// Close the reader and the connection.  
reader.Close();  
connection.Close();  
```  
  
## <a name="see-also"></a><span data-ttu-id="16e9b-128">참고자료</span><span class="sxs-lookup"><span data-stu-id="16e9b-128">See also</span></span>
- [<span data-ttu-id="16e9b-129">SQL Server 이진 및 큰 값 데이터</span><span class="sxs-lookup"><span data-stu-id="16e9b-129">SQL Server Binary and Large-Value Data</span></span>](../../../../docs/framework/data/adonet/sql/sql-server-binary-and-large-value-data.md)
- [<span data-ttu-id="16e9b-130">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="16e9b-130">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
