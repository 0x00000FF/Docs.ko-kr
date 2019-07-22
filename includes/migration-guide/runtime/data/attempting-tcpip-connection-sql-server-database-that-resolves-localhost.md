---
ms.openlocfilehash: e36dac19beb6251debef100656670a6623344eea
ms.sourcegitcommit: 4d8efe00f2e5ab42e598aff298d13b8c052d9593
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/16/2019
ms.locfileid: "68237830"
---
### <a name="attempting-a-tcpip-connection-to-a-sql-server-database-that-resolves-to-localhost-fails"></a><span data-ttu-id="f5978-101">`localhost`로 확인된 SQL Server 데이터베이스에 대한 TCP/IP 연결 시도 실패</span><span class="sxs-lookup"><span data-stu-id="f5978-101">Attempting a TCP/IP connection to a SQL Server database that resolves to `localhost` fails</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f5978-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="f5978-102">Details</span></span>|<span data-ttu-id="f5978-103">.NET Framework 4.6 및 4.6.1에서 <code>localhost</code>로 확인된 SQL Server 데이터베이스에 대한 TCP/IP 연결 시도가 오류와 함께 실패합니다. &quot;SQL Server에 연결을 설정하는 동안 네트워크 관련 또는 인스턴스 관련 오류가 발생했습니다.</span><span class="sxs-lookup"><span data-stu-id="f5978-103">In the .NET Framework 4.6 and 4.6.1, attempting a TCP/IP connection to a SQL Server database that resolves to <code>localhost</code> fails with the error, &quot;A network-related or instance-specific error occurred while establishing a connection to SQL Server.</span></span> <span data-ttu-id="f5978-104">서버를 찾을 수 없거나 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f5978-104">The server was not found or was not accessible.</span></span> <span data-ttu-id="f5978-105">인스턴스 이름이 올바르고 SQL Server가 원격 연결을 허용하도록 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f5978-105">Verify that the instance name is correct and that SQL Server is configured to allow remote connections.</span></span> <span data-ttu-id="f5978-106">(공급자: SQL 네트워크 인터페이스, 오류: 26 - 지정된 서버/인스턴스 찾기 오류)&quot;</span><span class="sxs-lookup"><span data-stu-id="f5978-106">(provider: SQL Network Interfaces, error: 26 - Error Locating Server/Instance Specified)&quot;</span></span>|
|<span data-ttu-id="f5978-107">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="f5978-107">Suggestion</span></span>|<span data-ttu-id="f5978-108">이 문제가 해결되었으며 이전 동작은 .NET Framework 4.6.2에서 복원되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f5978-108">This issue has been addressed and the previous behavior restored in the .NET Framework 4.6.2.</span></span> <span data-ttu-id="f5978-109"><code>localhost</code>로 확인된 SQL Server 데이터베이스에 연결하려면 .NET Framework 4.6.2로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="f5978-109">To connect to a SQL Server databsae that resolves to <code>localhost</code>, upgrade to the .NET Framework 4.6.2.</span></span>|
|<span data-ttu-id="f5978-110">범위</span><span class="sxs-lookup"><span data-stu-id="f5978-110">Scope</span></span>|<span data-ttu-id="f5978-111">부</span><span class="sxs-lookup"><span data-stu-id="f5978-111">Minor</span></span>|
|<span data-ttu-id="f5978-112">버전</span><span class="sxs-lookup"><span data-stu-id="f5978-112">Version</span></span>|<span data-ttu-id="f5978-113">4.6</span><span class="sxs-lookup"><span data-stu-id="f5978-113">4.6</span></span>|
|<span data-ttu-id="f5978-114">형식</span><span class="sxs-lookup"><span data-stu-id="f5978-114">Type</span></span>|<span data-ttu-id="f5978-115">런타임</span><span class="sxs-lookup"><span data-stu-id="f5978-115">Runtime</span></span>|
