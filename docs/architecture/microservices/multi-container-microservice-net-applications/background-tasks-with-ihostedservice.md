---
title: IHostedService 및 BackgroundService 클래스를 사용하여 마이크로 서비스에서 백그라운드 작업 구현
description: 컨테이너화된 .NET 애플리케이션용 .NET 마이크로 서비스 아키텍처 | IHostedService 및 BackgroundService를 사용하여 마이크로 서비스 .NET Core에서 백그라운드 작업을 구현하는 새 옵션을 이해합니다.
ms.date: 01/07/2019
ms.openlocfilehash: 2d0b41bc7853dc616284c46462efe96ca1a9d296
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72770116"
---
# <a name="implement-background-tasks-in-microservices-with-ihostedservice-and-the-backgroundservice-class"></a><span data-ttu-id="c3c06-103">IHostedService 및 BackgroundService 클래스를 사용하여 마이크로 서비스에서 백그라운드 작업 구현</span><span class="sxs-lookup"><span data-stu-id="c3c06-103">Implement background tasks in microservices with IHostedService and the BackgroundService class</span></span>

<span data-ttu-id="c3c06-104">백그라운드 작업 및 예약된 작업은 마이크로 서비스 기반 애플리케이션 또는 모든 종류의 애플리케이션에서 결국 구현해야 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-104">Background tasks and scheduled jobs are something you might need to implement, eventually, in a microservice based application or in any kind of application.</span></span> <span data-ttu-id="c3c06-105">마이크로 서비스 아키텍처를 사용하는 경우 차이점은 이러한 백그라운드 작업을 호스팅하기 위한 단일 마이크로 서비스 프로세스/컨테이너를 구현할 수 있으므로 필요에 따라 축소/확대하거나 해당 마이크로 서비스 프로세스/컨테이너의 단일 인스턴스를 실행하는지 확인할 수도 있다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-105">The difference when using a microservices architecture is that you can implement a single microservice process/container for hosting these background tasks so you can scale it down/up as you need or you can even make sure that it runs a single instance of that microservice process/container.</span></span>

<span data-ttu-id="c3c06-106">일반 관점에서 호스트/애플리케이션/마이크로 서비스 내에서 호스팅하는 서비스/논리이기 때문에 .NET Core에서 이러한 유형의 작업 *호스팅 서비스*를 호출했습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-106">From a generic point of view, in .NET Core we called these type of tasks *Hosted Services*, because they are services/logic that you host within your host/application/microservice.</span></span> <span data-ttu-id="c3c06-107">이 경우 호스팅 서비스는 단순히 백그라운드 작업 논리가 있는 클래스를 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-107">Note that in this case, the hosted service simply means a class with the background task logic.</span></span>

<span data-ttu-id="c3c06-108">.NET Core 2.0부터 프레임워크는 호스팅 서비스를 쉽게 구현할 수 있도록 돕는 <xref:Microsoft.Extensions.Hosting.IHostedService>라는 새 인터페이스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-108">Since .NET Core 2.0, the framework provides a new interface named <xref:Microsoft.Extensions.Hosting.IHostedService> helping you to easily implement hosted services.</span></span> <span data-ttu-id="c3c06-109">기본적인 개념은 그림 6-26과 같이 웹 호스트 또는 호스트를 실행하는 동안 백그라운드에서 실행되는 여러 개의 백그라운드 작업(호스티드 서비스)을 등록할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-109">The basic idea is that you can register multiple background tasks (hosted services) that run in the background while your web host or host is running, as shown in the image 6-26.</span></span>

![ASP.NET Core 1.x 및 2.x는 웹앱의 백그라운드 프로세스용 IWebHost를 지원하며, .NET Core 2.1은 일반 콘솔 앱으로 백그라운드 프로세스용 IHost를 지원합니다.](./media/image26.png)

<span data-ttu-id="c3c06-111">**그림 6-26**.</span><span class="sxs-lookup"><span data-stu-id="c3c06-111">**Figure 6-26**.</span></span> <span data-ttu-id="c3c06-112">WebHost 및 Host에서 IHostedService 사용 비교</span><span class="sxs-lookup"><span data-stu-id="c3c06-112">Using IHostedService in a WebHost vs. a Host</span></span>

<span data-ttu-id="c3c06-113">`WebHost`와 `Host` 사이에서 만들어진 차이점입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-113">Note the difference made between `WebHost` and `Host`.</span></span>

<span data-ttu-id="c3c06-114">ASP.NET Core 2.0의 `WebHost`(`IWebHost`를 구현하는 기본 클래스)는 MVC 웹앱 또는 Web API 서비스를 구현하는 경우와 같이 프로세스에 HTTP 서버 기능을 제공하는 데 사용하는 인프라 아티팩트입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-114">A `WebHost` (base class implementing `IWebHost`) in ASP.NET Core 2.0 is the infrastructure artifact you use to provide HTTP server features to your process, such as if you are implementing an MVC web app or Web API service.</span></span> <span data-ttu-id="c3c06-115">종속성 주입을 사용하고 요청 파이프라인 등에 미들웨어를 넣고 백그라운드 작업에 대해 이러한 `IHostedServices`를 정확하게 사용할 수 있도록 하는 ASP.NET Core의 새로운 모든 인프라 장점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-115">It provides all the new infrastructure goodness in ASP.NET Core, enabling you to use dependency injection, insert middlewares in the request pipeline, etc. and precisely use these `IHostedServices` for background tasks.</span></span>

<span data-ttu-id="c3c06-116">`Host`(`IHost`를 구현하는 기본 클래스)는 .NET Core 2.1에서 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-116">A `Host` (base class implementing `IHost`) was introduced in .NET Core 2.1.</span></span> <span data-ttu-id="c3c06-117">기본적으로 `Host`를 통해 `WebHost`(종속성 주입, 호스팅 서비스 등)를 사용하여 가진 것보다 유사한 인프라를 가질 수 있지만 이 경우 MVC, Web API 또는 HTTP 서버 기능과 관련이 없는 호스트로 간단하고 쉬운 프로세스를 갖길 원합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-117">Basically, a `Host` allows you to have a similar infrastructure than what you have with `WebHost` (dependency injection, hosted services, etc.), but in this case, you just want to have a simple and lighter process as the host, with nothing related to MVC, Web API or HTTP server features.</span></span>

<span data-ttu-id="c3c06-118">따라서 `IHostedServices`를 호스트하기 위해 만들어진 마이크로 서비스와 같은 호스팅 서비스 및 그 밖의 것을 처리하도록 IHost로 특수화된 호스트 프로세스를 선택하고 만들 수 있거나 기존 ASP.NET Core Web API 또는 MVC 앱과 같이 기존 ASP.NET Core `WebHost`를 대안으로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-118">Therefore, you can choose and either create a specialized host-process with IHost to handle the hosted services and nothing else, such a microservice made just for hosting the `IHostedServices`, or you can alternatively extend an existing ASP.NET Core `WebHost`, such as an existing ASP.NET Core Web API or MVC app.</span></span>

<span data-ttu-id="c3c06-119">각 방식은 비즈니스 및 확장성 요구에 따라 장점과 단점을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-119">Each approach has pros and cons depending on your business and scalability needs.</span></span> <span data-ttu-id="c3c06-120">요점은 기본적으로 백그라운드 작업에 HTTP(IWebHost)와 아무 관련이 없다면 IHost를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-120">The bottom line is basically that if your background tasks have nothing to do with HTTP (IWebHost) you should use IHost.</span></span>

## <a name="registering-hosted-services-in-your-webhost-or-host"></a><span data-ttu-id="c3c06-121">WebHost 또는 Host에서 호스팅 서비스 등록</span><span class="sxs-lookup"><span data-stu-id="c3c06-121">Registering hosted services in your WebHost or Host</span></span>

<span data-ttu-id="c3c06-122">사용 방법은 `WebHost` 또는 `Host`에서 매우 유사하므로 `IHostedService` 인터페이스에서 자세히 살펴보도록 하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-122">Let’s drill down further on the `IHostedService` interface since its usage is pretty similar in a `WebHost` or in a `Host`.</span></span>

<span data-ttu-id="c3c06-123">SignalR은 호스팅 서비스를 사용하는 아티팩트의 한 가지 예이지만 다음과 같이 훨씬 간단한 작업에 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-123">SignalR is one example of an artifact using hosted services, but you can also use it for much simpler things like:</span></span>

- <span data-ttu-id="c3c06-124">변경 내용을 찾는 데이터베이스를 폴링하는 백그라운드 작업</span><span class="sxs-lookup"><span data-stu-id="c3c06-124">A background task polling a database looking for changes.</span></span>
- <span data-ttu-id="c3c06-125">주기적으로 일부 캐시를 업데이트하는 예약된 작업</span><span class="sxs-lookup"><span data-stu-id="c3c06-125">A scheduled task updating some cache periodically.</span></span>
- <span data-ttu-id="c3c06-126">백그라운드 스레드에서 작업이 실행되도록 허용하는 QueueBackgroundWorkItem의 구현</span><span class="sxs-lookup"><span data-stu-id="c3c06-126">An implementation of QueueBackgroundWorkItem that allows a task to be executed on a background thread.</span></span>
- <span data-ttu-id="c3c06-127">`ILogger`와 같은 공통 서비스를 공유하는 동안 웹앱의 백그라운드에서 메시지 큐의 메시지 처리</span><span class="sxs-lookup"><span data-stu-id="c3c06-127">Processing messages from a message queue in the background of a web app while sharing common services such as `ILogger`.</span></span>
- <span data-ttu-id="c3c06-128">`Task.Run()`으로 시작한 백그라운드 작업</span><span class="sxs-lookup"><span data-stu-id="c3c06-128">A background task started with `Task.Run()`.</span></span>

<span data-ttu-id="c3c06-129">기본적으로 IHostedService에 따라 백그라운드 작업에 이러한 작업을 오프로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-129">You can basically offload any of those actions to a background task based on IHostedService.</span></span>

<span data-ttu-id="c3c06-130">하나 또는 여러 `IHostedServices`를 `WebHost` 또는 `Host`에 추가하는 방법은 ASP.NET Core `WebHost`(또는 .NET Core 2.1 이상의 `Host`)에서 <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A> 확장 메서드를 통해 등록하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-130">The way you add one or multiple `IHostedServices` into your `WebHost` or `Host` is by registering them up through the <xref:Microsoft.Extensions.DependencyInjection.ServiceCollectionHostedServiceExtensions.AddHostedService%2A> extension method in an ASP.NET Core `WebHost` (or in a `Host` in .NET Core 2.1 and above).</span></span> <span data-ttu-id="c3c06-131">기본적으로 ASP.NET WebHost의 다음 코드에서처럼 `Startup` 클래스의 친숙한 `ConfigureServices()` 메서드 내에서 호스팅 서비스를 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-131">Basically, you have to register the hosted services within the familiar `ConfigureServices()` method of the `Startup` class, as in the following code from a typical ASP.NET WebHost.</span></span>

```csharp
public IServiceProvider ConfigureServices(IServiceCollection services)
{
    //Other DI registrations;

    // Register Hosted Services
    services.AddHostedService<GracePeriodManagerService>();
    services.AddHostedService<MyHostedServiceB>();
    services.AddHostedService<MyHostedServiceC>();
    //...
}
```

<span data-ttu-id="c3c06-132">해당 코드에서 `GracePeriodManagerService` 호스팅 서비스는 eShopOnContainers에서 순서 지정 비즈니스 마이크로 서비스의 실제 코드인 반면 다른 두 가지는 두 개의 추가 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-132">In that code, the `GracePeriodManagerService` hosted service is real code from the Ordering business microservice in eShopOnContainers, while the other two are just two additional samples.</span></span>

<span data-ttu-id="c3c06-133">`IHostedService` 백그라운드 작업 실행은 애플리케이션의 수명에 맞게 조정됩니다(해당하는 경우 호스트 또는 마이크로 서비스).</span><span class="sxs-lookup"><span data-stu-id="c3c06-133">The `IHostedService` background task execution is coordinated with the lifetime of the application (host or microservice, for that matter).</span></span> <span data-ttu-id="c3c06-134">애플리케이션이 시작할 때 작업을 등록하고 애플리케이션이 종료될 때 일부 정상적인 작업 또는 정리를 수행할 기회를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-134">You register tasks when the application starts and you have the opportunity to do some graceful action or clean-up when the application is shutting down.</span></span>

<span data-ttu-id="c3c06-135">`IHostedService`를 사용하지 않고 항상 백그라운드 스레드를 시작하여 작업을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-135">Without using `IHostedService`, you could always start a background thread to run any task.</span></span> <span data-ttu-id="c3c06-136">차이점은 정상적인 정리 작업을 실행할 기회를 갖지 않고 해당 스레드가 그냥 제거되는 경우 정확하게 앱의 종료 시간에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-136">The difference is precisely at the app’s shutdown time when that thread would simply be killed without having the opportunity to run graceful clean-up actions.</span></span>

## <a name="the-ihostedservice-interface"></a><span data-ttu-id="c3c06-137">IHostedService 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3c06-137">The IHostedService interface</span></span>

<span data-ttu-id="c3c06-138">`IHostedService`를 등록할 때 .NET Core는 애플리케이션 시작 및 중지 중에 각각 `IHostedService` 유형의 `StartAsync()` 및 `StopAsync()` 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-138">When you register an `IHostedService`, .NET Core will call the `StartAsync()` and `StopAsync()` methods of your `IHostedService` type during application start and stop respectively.</span></span> <span data-ttu-id="c3c06-139">특히 서버가 시작되고 `IApplicationLifetime.ApplicationStarted`가 트리거된 후 시작이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-139">Specifically, start is called after the server has started and `IApplicationLifetime.ApplicationStarted` is triggered.</span></span>

<span data-ttu-id="c3c06-140">.NET Core에 정의된 대로 `IHostedService`는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-140">The `IHostedService` as defined in .NET Core, looks like the following.</span></span>

```csharp
namespace Microsoft.Extensions.Hosting
{
    //
    // Summary:
    //     Defines methods for objects that are managed by the host.
    public interface IHostedService
    {
        //
        // Summary:
        // Triggered when the application host is ready to start the service.
        Task StartAsync(CancellationToken cancellationToken);
        //
        // Summary:
        // Triggered when the application host is performing a graceful shutdown.
        Task StopAsync(CancellationToken cancellationToken);
    }
}
```

<span data-ttu-id="c3c06-141">상상할 수 있듯이 IHostedService의 여러 구현을 만들고 이전에 표시된 것처럼 `ConfigureService()` 메서드에서 DI 컨테이너로 등록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-141">As you can imagine, you can create multiple implementations of IHostedService and register them at the `ConfigureService()` method into the DI container, as shown previously.</span></span> <span data-ttu-id="c3c06-142">이러한 모든 호스팅 서비스는 애플리케이션/마이크로 서비스와 함께 시작되고 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-142">All those hosted services will be started and stopped along with the application/microservice.</span></span>

<span data-ttu-id="c3c06-143">개발자는 `StopAsync()` 메서드가 호스트에 의해 트리거될 때 서비스의 중지 작업을 처리할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-143">As a developer, you are responsible for handling the stopping action of your services when `StopAsync()` method is triggered by the host.</span></span>

## <a name="implementing-ihostedservice-with-a-custom-hosted-service-class-deriving-from-the-backgroundservice-base-class"></a><span data-ttu-id="c3c06-144">BackgroundService 기본 클래스에서 파생되는 사용자 지정 호스팅 서비스 클래스로 IHostedService 구현</span><span class="sxs-lookup"><span data-stu-id="c3c06-144">Implementing IHostedService with a custom hosted service class deriving from the BackgroundService base class</span></span>

<span data-ttu-id="c3c06-145">.NET Core 2.0을 사용할 때 수행해야 하므로 계속 진행하고 처음부터 사용자 지정 호스팅 서비스 클래스를 만들고 `IHostedService`를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-145">You could go ahead and create your custom hosted service class from scratch and implement the `IHostedService`, as you need to do when using .NET Core 2.0.</span></span>

<span data-ttu-id="c3c06-146">그러나 대부분의 백그라운드 작업은 취소 토큰 관리 및 기타 일반적인 작업과 관련하여 비슷한 요구 사항이 있으므로 `BackgroundService`라는(.NET Core 2.1부터 사용 가능) 파생시킬 수 있는 매우 편리한 추상 기본 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-146">However, since most background tasks will have similar needs in regard to the cancellation tokens management and other typical operations, there is a convenient abstract base class you can derive from, named `BackgroundService` (available since .NET Core 2.1).</span></span>

<span data-ttu-id="c3c06-147">해당 클래스는 백그라운드 작업을 설정하는 데 필요한 주요 작업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-147">That class provides the main work needed to set up the background task.</span></span>

<span data-ttu-id="c3c06-148">다음 코드는 .NET Core에서 구현되는 추상 BackgroundService 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-148">The next code is the abstract BackgroundService base class as implemented in .NET Core.</span></span>

```csharp
// Copyright (c) .NET Foundation. Licensed under the Apache License, Version 2.0.
/// <summary>
/// Base class for implementing a long running <see cref="IHostedService"/>.
/// </summary>
public abstract class BackgroundService : IHostedService, IDisposable
{
    private Task _executingTask;
    private readonly CancellationTokenSource _stoppingCts =
                                                   new CancellationTokenSource();

    protected abstract Task ExecuteAsync(CancellationToken stoppingToken);

    public virtual Task StartAsync(CancellationToken cancellationToken)
    {
        // Store the task we're executing
        _executingTask = ExecuteAsync(_stoppingCts.Token);

        // If the task is completed then return it,
        // this will bubble cancellation and failure to the caller
        if (_executingTask.IsCompleted)
        {
            return _executingTask;
        }

        // Otherwise it's running
        return Task.CompletedTask;
    }

    public virtual async Task StopAsync(CancellationToken cancellationToken)
    {
        // Stop called without start
        if (_executingTask == null)
        {
            return;
        }

        try
        {
            // Signal cancellation to the executing method
            _stoppingCts.Cancel();
        }
        finally
        {
            // Wait until the task completes or the stop token triggers
            await Task.WhenAny(_executingTask, Task.Delay(Timeout.Infinite,
                                                          cancellationToken));
        }

    }

    public virtual void Dispose()
    {
        _stoppingCts.Cancel();
    }
}
```

<span data-ttu-id="c3c06-149">이전 추상 기본 클래스에서 파생될 때 상속된 해당 구현 덕분에 데이터베이스를 폴링하고 필요한 경우 통합 이벤트를 이벤트 버스로 게시하는 eShopOnContainers의 다음 단순화된 코드에서처럼 사용자 고유의 사용자 지정 호스팅 서비스 클래스에서 `ExecuteAsync()` 메서드를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-149">When deriving from the previous abstract base class, thanks to that inherited implementation, you just need to implement the `ExecuteAsync()` method in your own custom hosted service class, as in the following simplified code from eShopOnContainers which is polling a database and publishing integration events into the Event Bus when needed.</span></span>

```csharp
public class GracePeriodManagerService : BackgroundService
{
    private readonly ILogger<GracePeriodManagerService> _logger;
    private readonly OrderingBackgroundSettings _settings;

    private readonly IEventBus _eventBus;

    public GracePeriodManagerService(IOptions<OrderingBackgroundSettings> settings,
                                     IEventBus eventBus,
                                     ILogger<GracePeriodManagerService> logger)
    {
        //Constructor’s parameters validations...
    }

    protected override async Task ExecuteAsync(CancellationToken stoppingToken)
    {
        _logger.LogDebug($"GracePeriodManagerService is starting.");

        stoppingToken.Register(() =>
            _logger.LogDebug($" GracePeriod background task is stopping."));

        while (!stoppingToken.IsCancellationRequested)
        {
            _logger.LogDebug($"GracePeriod task doing background work.");

            // This eShopOnContainers method is querying a database table
            // and publishing events into the Event Bus (RabbitMQ / ServiceBus)
            CheckConfirmedGracePeriodOrders();

            await Task.Delay(_settings.CheckUpdateTime, stoppingToken);
        }

        _logger.LogDebug($"GracePeriod background task is stopping.");
    }

    .../...
}
```

<span data-ttu-id="c3c06-150">eShopOnContainers에 대한 이 특정 경우에 특정 상태로 주문을 조회하는 데이터베이스 테이블을 쿼리하는 애플리케이션 메서드를 실행하고, 변경 내용을 적용하는 경우 이벤트 버스를 통해 통합 이벤트를 게시합니다(아래에서 RabbitMQ 또는 Azure Service Bus를 사용할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="c3c06-150">In this specific case for eShopOnContainers, it's executing an application method that's querying a database table looking for orders with a specific state and when applying changes, it is publishing integration events through the event bus (underneath it can be using RabbitMQ or Azure Service Bus).</span></span>

<span data-ttu-id="c3c06-151">물론 다른 비즈니스 백그라운드 작업을 대신 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-151">Of course, you could run any other business background task, instead.</span></span>

<span data-ttu-id="c3c06-152">`IWebHostBuilder`의 `UseShutdownTimeout` 확장을 사용하여 `WebHost`를 빌드할 때 해당 값을 변경할 수 있지만 기본적으로 취소 토큰은 5초 시간 제한으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-152">By default, the cancellation token is set with a 5 second timeout, although you can change that value when building your `WebHost` using the `UseShutdownTimeout` extension of the `IWebHostBuilder`.</span></span> <span data-ttu-id="c3c06-153">즉, 서비스는 5초 내에 취소될 것으로 예상되며 그렇지 않은 경우 갑자기 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-153">This means that our service is expected to cancel within 5 seconds otherwise it will be more abruptly killed.</span></span>

<span data-ttu-id="c3c06-154">다음 코드는 해당 시간을 10초로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-154">The following code would be changing that time to 10 seconds.</span></span>

```csharp
WebHost.CreateDefaultBuilder(args)
    .UseShutdownTimeout(TimeSpan.FromSeconds(10))
    ...
```

### <a name="summary-class-diagram"></a><span data-ttu-id="c3c06-155">요약 클래스 다이어그램</span><span class="sxs-lookup"><span data-stu-id="c3c06-155">Summary class diagram</span></span>

<span data-ttu-id="c3c06-156">다음 이미지는 IHostedServices를 구현할 때 관련되는 클래스 및 인터페이스의 시각적 개체 요약을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-156">The following image shows a visual summary of the classes and interfaces involved when implementing IHostedServices.</span></span>

![클래스 다이어그램: IWebHost와 IHost는 IHostedService를 구현하는 BackgroundService에서 상속되는 많은 서비스를 호스트할 수 있습니다.](./media/image27.png)

<span data-ttu-id="c3c06-158">**그림 6-27**.</span><span class="sxs-lookup"><span data-stu-id="c3c06-158">**Figure 6-27**.</span></span> <span data-ttu-id="c3c06-159">IHostedService와 관련된 다중 클래스 및 인터페이스를 보여 주는 클래스 다이어그램</span><span class="sxs-lookup"><span data-stu-id="c3c06-159">Class diagram showing the multiple classes and interfaces related to IHostedService</span></span>

### <a name="deployment-considerations-and-takeaways"></a><span data-ttu-id="c3c06-160">배포 고려 사항 및 요점</span><span class="sxs-lookup"><span data-stu-id="c3c06-160">Deployment considerations and takeaways</span></span>

<span data-ttu-id="c3c06-161">ASP.NET Core `WebHost` 또는 .NET Core `Host`를 배포하는 방법은 최종 솔루션에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-161">It is important to note that the way you deploy your ASP.NET Core `WebHost` or .NET Core `Host` might impact the final solution.</span></span> <span data-ttu-id="c3c06-162">예를 들어 IIS에서 `WebHost` 또는 일반 Azure App Service를 배포하는 경우 호스트는 앱 풀 재활용으로 인해 종료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-162">For instance, if you deploy your `WebHost` on IIS or a regular Azure App Service, your host can be shut down because of app pool recycles.</span></span> <span data-ttu-id="c3c06-163">하지만 호스트를 컨테이너로 Kubernetes 또는 Service Fabric과 같은 오케스트레이터에 배포하는 경우 호스트의 실제 인스턴스의 보증된 수를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-163">But if you are deploying your host as a container into an orchestrator like Kubernetes or Service Fabric, you can control the assured number of live instances of your host.</span></span> <span data-ttu-id="c3c06-164">또한 Azure Functions와 같은 해당 시나리오에 대해 특별히 만들어진 클라우드에서 다른 방법을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-164">In addition, you could consider other approaches in the cloud especially made for these scenarios, like Azure Functions.</span></span> <span data-ttu-id="c3c06-165">마지막으로 서비스가 항상 실행 중이어야 하고 Windows Server에 배포하는 경우 Windows 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-165">Finally, if you need the service to be running all the time and are deploying on a Windows Server you could use a Windows Service.</span></span>

<span data-ttu-id="c3c06-166">하지만 앱 풀에 배포된 `WebHost`의 경우에도 애플리케이션의 메모리 내 캐시를 다시 채우거나 플러시하는 등의 시나리오는 계속 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-166">But even for a `WebHost` deployed into an app pool, there are scenarios like repopulating or flushing application’s in-memory cache that would be still applicable.</span></span>

<span data-ttu-id="c3c06-167">`IHostedService` 인터페이스는 ASP.NET Core 웹 애플리케이션(.NET Core 2.0에서) 또는 모든 프로세스/호스트(`IHost`로 .NET Core 2.1에서 시작)에서 백그라운드 작업을 시작하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-167">The `IHostedService` interface provides a convenient way to start background tasks in an ASP.NET Core web application (in .NET Core 2.0) or in any process/host (starting in .NET Core 2.1 with `IHost`).</span></span> <span data-ttu-id="c3c06-168">주요 혜택은 호스트 자체가 종료될 때 백그라운드 작업의 정리 코드에 대한 정상적인 취소를 얻는 기회입니다.</span><span class="sxs-lookup"><span data-stu-id="c3c06-168">Its main benefit is the opportunity you get with the graceful cancellation to clean-up code of your background tasks when the host itself is shutting down.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c3c06-169">추가 자료</span><span class="sxs-lookup"><span data-stu-id="c3c06-169">Additional resources</span></span>

- <span data-ttu-id="c3c06-170">**ASP.NET Core/Standard 2.0에서 예약된 작업 빌드**
  <https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html></span><span class="sxs-lookup"><span data-stu-id="c3c06-170">**Building a scheduled task in ASP.NET Core/Standard 2.0**
<https://blog.maartenballiauw.be/post/2017/08/01/building-a-scheduled-cache-updater-in-aspnet-core-2.html></span></span>

- <span data-ttu-id="c3c06-171">**ASP.NET Core 2.0에서 IHostedService 구현**
  <https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice></span><span class="sxs-lookup"><span data-stu-id="c3c06-171">**Implementing IHostedService in ASP.NET Core 2.0**
<https://www.stevejgordon.co.uk/asp-net-core-2-ihostedservice></span></span>

- <span data-ttu-id="c3c06-172">**ASP.NET Core 2.1을 사용한 GenericHost 샘플**
  <https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample></span><span class="sxs-lookup"><span data-stu-id="c3c06-172">**GenericHost Sample using ASP.NET Core 2.1**
<https://github.com/aspnet/Hosting/tree/release/2.1/samples/GenericHostSample></span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c3c06-173">[이전](test-aspnet-core-services-web-apps.md)
>[다음](implement-api-gateways-with-ocelot.md)</span><span class="sxs-lookup"><span data-stu-id="c3c06-173">[Previous](test-aspnet-core-services-web-apps.md)
[Next](implement-api-gateways-with-ocelot.md)</span></span>
