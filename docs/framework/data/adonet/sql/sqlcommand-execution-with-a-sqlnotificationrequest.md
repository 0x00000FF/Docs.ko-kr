---
title: SqlNotificationRequest를 사용하여 SqlCommand 실행
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1776f48f-9bea-41f6-83a4-c990c7a2c991
ms.openlocfilehash: 3115bfb80d4e5e61ed49da11e36eaa37bc24334f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70791539"
---
# <a name="sqlcommand-execution-with-a-sqlnotificationrequest"></a><span data-ttu-id="6eb24-102">SqlNotificationRequest를 사용하여 SqlCommand 실행</span><span class="sxs-lookup"><span data-stu-id="6eb24-102">SqlCommand Execution with a SqlNotificationRequest</span></span>

<span data-ttu-id="6eb24-103">데이터가 서버에서 반입된 후 변경될 때 알림을 생성하도록 <xref:System.Data.SqlClient.SqlCommand>를 구성할 수 있으며 쿼리가 다시 실행된 경우 결과 집합은 달라질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eb24-103">A <xref:System.Data.SqlClient.SqlCommand> can be configured to generate a notification when data changes after it has been fetched from the server and the result set would be different if the query were executed again.</span></span> <span data-ttu-id="6eb24-104">이 기능은 서버에 사용자 지정 알림 큐를 사용하려는 경우나 활성 개체를 유지하지 않으려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="6eb24-104">This is useful for scenarios where you want to use custom notification queues on the server or when you do not want to maintain live objects.</span></span>

## <a name="creating-the-notification-request"></a><span data-ttu-id="6eb24-105">Notification 요청 만들기</span><span class="sxs-lookup"><span data-stu-id="6eb24-105">Creating the Notification Request</span></span>

<span data-ttu-id="6eb24-106"><xref:System.Data.Sql.SqlNotificationRequest> 개체를 사용하여 `SqlCommand`개체에 바인딩하여 알림 요청을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eb24-106">You can use a <xref:System.Data.Sql.SqlNotificationRequest> object to create the notification request by binding it to a `SqlCommand` object.</span></span> <span data-ttu-id="6eb24-107">요청이 만들어지면 `SqlNotificationRequest` 개체는 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6eb24-107">Once the request is created, you no longer need the `SqlNotificationRequest` object.</span></span> <span data-ttu-id="6eb24-108">알림에 대해 큐를 쿼리하여 적절하게 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eb24-108">You can query the queue for any notifications and respond appropriately.</span></span> <span data-ttu-id="6eb24-109">애플리케이션이 종료된 후 나중에 다시 시작하더라도 알림이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eb24-109">Notifications can occur even if the application is shut down and subsequently restarted.</span></span>

<span data-ttu-id="6eb24-110">연결된 알림에 대한 명령이 실행될 때 원래 결과 집합에 대한 변경 사항이 있으면 알림 요청에 구성되어 있는 SQL Server 큐로 메시지를 보내는 작업이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eb24-110">When the command with the associated notification is executed, any changes to the original result set trigger sending a message to the SQL Server queue that was configured in the notification request.</span></span>

<span data-ttu-id="6eb24-111">SQL Server 큐를 폴링하고 메시지를 해석하는 방법은 애플리케이션에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6eb24-111">How you poll the SQL Server queue and interpret the message is specific to your application.</span></span> <span data-ttu-id="6eb24-112">애플리케이션에서는 큐를 폴링하고 메시지의 내용에 따라 반응하는 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6eb24-112">The application is responsible for polling the queue and reacting based on the contents of the message.</span></span>

> [!NOTE]
> <span data-ttu-id="6eb24-113"><xref:System.Data.SqlClient.SqlDependency>를 사용하여 SQL Server 알림 요청을 사용하는 경우 기본 서비스 이름을 사용하는 대신 사용자 고유의 큐 이름을 만드세요.</span><span class="sxs-lookup"><span data-stu-id="6eb24-113">When using SQL Server notification requests with <xref:System.Data.SqlClient.SqlDependency>, create your own queue name instead of using the default service name.</span></span>

<span data-ttu-id="6eb24-114"><xref:System.Data.Sql.SqlNotificationRequest>에 대한 새로운 클라이언트측 보안 요소는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6eb24-114">There are no new client-side security elements for <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="6eb24-115">이는 대부분 서버 기능이며 서버에는 사용자가 알림을 요청하기 위해 가져야 하는 특별한 권한이 만들어져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eb24-115">This is primarily a server feature, and the server has created special privileges that users must have to request a notification.</span></span>

### <a name="example"></a><span data-ttu-id="6eb24-116">예제</span><span class="sxs-lookup"><span data-stu-id="6eb24-116">Example</span></span>

<span data-ttu-id="6eb24-117">다음 코드 조각에서는 <xref:System.Data.Sql.SqlNotificationRequest>를 만들어 <xref:System.Data.SqlClient.SqlCommand>에 연결하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6eb24-117">The following code fragment demonstrates how to create a <xref:System.Data.Sql.SqlNotificationRequest> and associate it with a <xref:System.Data.SqlClient.SqlCommand>.</span></span>

```vb
' Assume connection is an open SqlConnection.
' Create a new SqlCommand object.
Dim command As New SqlCommand( _
  "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection)

' Create a SqlNotificationRequest object.
Dim notifcationRequest As New SqlNotificationRequest()
notificationRequest.id = "NotificationID"
notificationRequest.Service = "mySSBQueue"

' Associate the notification request with the command.
command.Notification = notificationRequest
' Execute the command.
command.ExecuteReader()
' Process the DataReader.
' You can use Transact-SQL syntax to periodically poll the
' SQL Server queue to see if you have a new message.
```

```csharp
// Assume connection is an open SqlConnection.
// Create a new SqlCommand object.
SqlCommand command=new SqlCommand(
 "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection);

// Create a SqlNotificationRequest object.
SqlNotificationRequest notificationRequest=new SqlNotificationRequest();
notificationRequest.id="NotificationID";
notificationRequest.Service="mySSBQueue";

// Associate the notification request with the command.
command.Notification=notificationRequest;
// Execute the command.
command.ExecuteReader();
// Process the DataReader.
// You can use Transact-SQL syntax to periodically poll the
// SQL Server queue to see if you have a new message.
```

## <a name="see-also"></a><span data-ttu-id="6eb24-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="6eb24-118">See also</span></span>

- [<span data-ttu-id="6eb24-119">SQL Server에서 쿼리 알림</span><span class="sxs-lookup"><span data-stu-id="6eb24-119">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="6eb24-120">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="6eb24-120">ADO.NET Overview</span></span>](../ado-net-overview.md)
