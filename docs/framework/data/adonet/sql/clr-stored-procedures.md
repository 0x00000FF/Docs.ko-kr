---
title: CLR 저장 프로시저
ms.date: 03/30/2017
ms.assetid: fd7eea9b-218a-4988-8c9a-8abcc6031c66
ms.openlocfilehash: a1a37ac1257594913c6d06cb08df2882e8773da8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54554636"
---
# <a name="clr-stored-procedures"></a><span data-ttu-id="bd0f7-102">CLR 저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="bd0f7-102">CLR Stored Procedures</span></span>
<span data-ttu-id="bd0f7-103">저장 프로시저는 스칼라 식에 사용할 수 없는 루틴입니다.</span><span class="sxs-lookup"><span data-stu-id="bd0f7-103">Stored procedures are routines that cannot be used in scalar expressions.</span></span> <span data-ttu-id="bd0f7-104">또한 클라이언트에 테이블 형식 결과와 메시지를 반환하고 DDL(데이터 정의 언어) 및 DML(데이터 조작 언어) 문을 호출하며 출력 매개 변수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0f7-104">They can return tabular results and messages to the client, invoke data definition language (DDL) and data manipulation language (DML) statements, and return output parameters.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bd0f7-105">Microsoft Visual Basic에서는 Microsoft Visual C#과 다른 방식으로 출력 매개 변수를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0f7-105">Microsoft Visual Basic does not support output parameters in the same way that Microsoft Visual C# does.</span></span> <span data-ttu-id="bd0f7-106">참조로 매개 변수를 전달 하 고 적용을 지정 해야 합니다 \<나타내야 >는 다음과 같이 출력 매개 변수를 나타내는 특성:</span><span class="sxs-lookup"><span data-stu-id="bd0f7-106">You must specify to pass the parameter by reference and apply the \<Out()> attribute to represent an output parameter, as in the following:</span></span>  
  
```vb
Public Shared Sub ExecuteToClient( <Out()> ByRef number As Integer)  
```
  
<span data-ttu-id="bd0f7-107">자세한 내용은 참조는 버전의 [SQL Server 설명서](/sql) 사용 중인 SQL Server의 버전에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd0f7-107">For more detailed information, see the version of [SQL Server documentation](/sql) for the version of SQL Server you're using.</span></span>
  
 <span data-ttu-id="bd0f7-108">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="bd0f7-108">**SQL Server documentation**</span></span>

1. [<span data-ttu-id="bd0f7-109">CLR 저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="bd0f7-109">CLR Stored Procedures</span></span>](https://go.microsoft.com/fwlink/?LinkId=115400)  
  
## <a name="see-also"></a><span data-ttu-id="bd0f7-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="bd0f7-110">See also</span></span>
- [<span data-ttu-id="bd0f7-111">관리 코드에서 SQL Server 2005 개체 만들기</span><span class="sxs-lookup"><span data-stu-id="bd0f7-111">Creating SQL Server 2005 Objects In Managed Code</span></span>](https://msdn.microsoft.com/library/5358a825-e19b-49aa-8214-674ce5fed1da)
- [<span data-ttu-id="bd0f7-112">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="bd0f7-112">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
