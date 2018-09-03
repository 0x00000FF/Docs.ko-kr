---
title: 'F #을 사용 하 여 Azure Blob storage 시작'
description: Azure Blob storage 사용 하 여 클라우드에 구조화 되지 않은 데이터를 저장 합니다.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: ea9dc334ec9c2bcd4a80cc501d4b6634da5f64e4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467165"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a>F #을 사용 하 여 Azure Blob storage 시작 #

Azure Blob Storage는 클라우드에서 구조화되지 않은 데이터를 개체/Blob으로 저장하는 서비스입니다. Blob Storage는 문서, 미디어 파일, 응용 프로그램 설치 관리자 등과 같은 모든 유형의 텍스트 또는 이진 데이터를 저장할 수 있습니다. Blob Storage를 개체 저장소라고도 합니다.

이 문서에서는 Blob storage를 사용 하 여 일반적인 작업을 수행 하는 방법을 보여 줍니다. 샘플은 Azure Storage 클라이언트 라이브러리를 사용 하 여.NET 용 F #을 사용 하 여 작성 되었습니다. 대상 작업을 업로드, 나열, 다운로드 및 blob을 삭제 하는 방법을 포함 합니다.

Blob 저장소의 개념적인 개요를 참조 하세요 [blob storage에 대 한.NET 가이드](/azure/storage/storage-dotnet-how-to-use-blobs)합니다.

## <a name="prerequisites"></a>전제 조건

이 가이드를 사용 하려면 먼저 [Azure storage 계정 만들기](/azure/storage/storage-create-storage-account)합니다. 이 계정에 대 한 저장소 액세스 키도 필요 합니다.

## <a name="create-an-f-script-and-start-f-interactive"></a>만들기는 F # 스크립트와 시작 F # 대화형

이 문서의 샘플에에서는 F # 응용 프로그램 또는 F # 스크립트에서 사용할 수 있습니다. F # 스크립트를 만들려면 사용 하 여 파일을 만듭니다는 `.fsx` 확장명을 예를 들어 `blobs.fsx`, F # 개발 환경에서.

다음을 사용 하 여는 [패키지 관리자](package-management.md) 와 같은 [Paket](https://fsprojects.github.io/Paket/) 또는 [NuGet](https://www.nuget.org/) 설치 하는 `WindowsAzure.Storage` 및 `Microsoft.WindowsAzure.ConfigurationManager` 패키지와 참조 `WindowsAzure.Storage.dll` 및 `Microsoft.WindowsAzure.Configuration.dll` 사용 하 여 스크립트를 `#r` 지시문입니다.

### <a name="add-namespace-declarations"></a>네임 스페이스 선언을 추가합니다

다음을 추가 합니다 `open` 의 맨 위에 문을 `blobs.fsx` 파일:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>연결 문자열 가져오기

이 자습서는 Azure Storage 연결 문자열이 필요합니다. 연결 문자열에 대 한 자세한 내용은 참조 하세요. [저장소 연결 문자열 구성](/azure/storage/storage-configure-connection-string)합니다.

자습서의 경우 다음과 같은 스크립트에서 연결 문자열을 입력:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

그러나 이것이 **좋지** 실제 프로젝트입니다. 저장소 계정 키는 저장소 계정의 루트 암호와 비슷합니다. 항상 저장소 계정 키를 보호 해야 합니다. 다른 사용자에 하드 코딩 하거나 다른 사용자에 게 액세스할 수 있는 일반 텍스트 파일을 저장 하 게 배포 하지 마세요. 손상 되었다고 생각 하는 경우 Azure Portal을 사용 하 여 키를 다시 생성할 수 있습니다.

실제 응용 프로그램 저장소 연결 문자열을 유지 하는 가장 좋은 방법은 구성 파일에서 됩니다. 구성 파일에서 연결 문자열을 가져올,이 수행할 수 있습니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

Azure 구성 관리자를 사용 하는 것은 선택 사항입니다. .NET Framework의 등의 API를 사용할 수도 있습니다 `ConfigurationManager` 형식입니다.

### <a name="parse-the-connection-string"></a>연결 문자열을 구문 분석

연결 문자열을 구문 분석 하려면 다음을 사용 합니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

반환 된 `CloudStorageAccount`합니다.

### <a name="create-some-local-dummy-data"></a>몇 가지 로컬 더미 데이터 만들기

시작 하기 전에 스크립트의 디렉터리에 더미 로컬 데이터를 만듭니다. 나중에이 데이터를 업로드 합니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>Blob service 클라이언트 만들기

`CloudBlobClient` 컨테이너 및 Blob storage에 저장 된 blob을 검색할 수도 있습니다. 서비스 클라이언트를 만드는 한 가지 방법은 다음과 같습니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

이제 데이터를 읽어 오고 Blob storage로 데이터를 기록 하는 코드를 작성할 준비가 되었습니다.

## <a name="create-a-container"></a>컨테이너 만들기

이 예제에는 아직 존재 하지 않는 경우 컨테이너를 만드는 방법을 보여 줍니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

기본적으로 새 컨테이너는 private,이 컨테이너에서 blob을 다운로드 하려면 저장소 액세스 키를 지정 해야 함을 의미 합니다. 모든 사용자에 게 컨테이너 내의 파일을 사용할 수 있도록 하려는 경우에 다음 코드를 사용 하 여 공용 컨테이너를 설정할 수 있습니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

인터넷 상의 누구 든 지 공용 컨테이너의 blob를 볼 수 있지만 수정 하거나 적절 한 계정 액세스 키 또는 공유 액세스 서명이 있는 경우에 삭제할 수 있습니다.

## <a name="upload-a-blob-into-a-container"></a>컨테이너에 blob 업로드

Azure Blob Storage는 블록 blob 및 페이지 blob을 지원합니다. 대부분의 경우 블록 blob의는 권장 되는 형식을 사용 해야 합니다.

파일에 블록 blob을 업로드 하려면 컨테이너 참조를 가져오고 사용 하 여 블록 blob 참조를 가져옵니다. Blob 참조가 있으면 스트림을 업로드할 수 있습니다 모든 데이터를 호출 하 여는 `UploadFromFile` 메서드. 이 작업은 이전에 존재 하거나 없는 경우 덮어 쓸까요 하지 않은 경우 blob을 만듭니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>컨테이너의 blob을 나열

컨테이너의 blob을 나열 하려면 먼저 컨테이너 참조를 가져옵니다. 컨테이너의 사용할 수 있습니다 `ListBlobs` blob 및/또는 그 디렉터리를 검색 하는 방법입니다. 속성 및 메서드 반환 된 다양 한 집합에 액세스 하려면 `IListBlobItem`를 캐스트 해야를 `CloudBlockBlob`를 `CloudPageBlob`, 또는 `CloudBlobDirectory` 개체입니다. 종류를 알 수 없는 경우 캐스트 확인할 형식 검사를 사용할 수 있습니다. 다음 코드에는 검색의 각 항목의 URI를 출력 하는 방법을 보여 줍니다.는 `mydata` 컨테이너:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

이름에 대 한 경로 정보를 사용 하 여 이름을 blob 수도 있습니다. 이 구성 하 고 기존 파일 시스템과 마찬가지로 트래버스할 수 있는 가상 디렉터리 구조를 만듭니다. 디렉터리 구조는 가상만 해당-컨테이너 및 blob는 Blob storage에서 사용할 수 있는 리소스만 note 합니다. 그러나 storage 클라이언트 라이브러리를 제공 된 `CloudBlobDirectory` 가상 디렉터리를 참조 하 여이 방식으로 구성 된 blob을 사용 하는 프로세스를 간소화 하는 개체입니다.

예를 들어, 다음 라는 컨테이너에 블록 blob 집합을 고려 `photos`:

*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015/architecture/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg*
*2016/architecture/description.txt*
*2016/photo7.jpg*

호출 하는 경우 `ListBlobs` 는 위의 샘플과 같이 컨테이너에서 계층적 목록이 반환 됩니다. 둘 다 포함 되어 있으면 `CloudBlobDirectory` 고 `CloudBlockBlob` 결과 출력은 다음과 유사 하 게 한 다음 컨테이너에 blob 및 디렉터리를 각각 나타내는 개체입니다.

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

선택적으로 설정할 수 있습니다 합니다 `UseFlatBlobListing` 의 매개 변수를 `ListBlobs` 메서드를 `true`입니다. 으로 컨테이너의 모든 blob는 반환 하는 경우에 `CloudBlockBlob` 개체입니다. 에 대 한 호출 `ListBlobs` 반환할 한 플랫 목록이 다음과 같이 표시 됩니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

및 컨테이너의 현재 내용에 따라 결과 다음과 같습니다.

```console
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2015/architecture/description.txt
Block blob of length 314618: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo3.jpg
Block blob of length 522713: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo4.jpg
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2016/architecture/description.txt
Block blob of length 419048: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo5.jpg
Block blob of length 506388: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo6.jpg
Block blob of length 399751: https://<accountname>.blob.core.windows.net/photos/2016/photo7.jpg
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

## <a name="download-blobs"></a>Blob 다운로드

Blob을 다운로드 하려면 먼저 blob 참조를 검색 한 다음 호출을 `DownloadToStream` 메서드. 다음 예제에서는 `DownloadToStream` 로컬 파일에 저장할 수 있습니다 하는 스트림 개체로 blob 콘텐츠를 전송 하는 방법입니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

사용할 수도 있습니다는 `DownloadToStream` 메서드를 텍스트 문자열로 blob의 콘텐츠를 다운로드 합니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>Blob 삭제

Blob을 삭제 하려면 먼저 blob 참조를 가져온 및 호출 된 `Delete` 메서드를 합니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>페이지에서 blob를 비동기적으로 나열

많은 수의 blob 나열 하는 경우 단일 목록 작업에서 반환 되는 결과의 수를 제어 하려면 결과 페이지에 blob를 나열할 수 있습니다. 이 예제는 큰 결과 집합이 반환 되기를 기다리는 동안 실행이 차단 되지 않도록 비동기적으로 페이지에 결과 반환 하는 방법을 보여줍니다.

이 예제에서는 플랫 blob 나열을 보여주지만 설정 하 여 계층적 나열을 수행할 수도 있습니다는 `useFlatBlobListing` 의 매개 변수를 `ListBlobsSegmentedAsync` 메서드를 `false`입니다.

샘플 정의 비동기 메서드를 사용 하는 `async` 블록. ``let!`` 키워드는 나열 작업이 완료 될 때까지 샘플 메서드의 실행을 일시 중단 합니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

이제이 비동기 루틴을 다음과 같이 사용할 수 있습니다. 먼저 일부 더미 데이터 (이 자습서의 앞부분에서 만든 로컬 파일 사용)를 업로드 합니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

이제는 루틴을 호출 합니다. 사용할 `Async.RunSynchronously` 비동기 작업을 실행 하도록 합니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>추가 blob에 쓰기

추가 blob은 로깅 등의 추가 작업을 위해 최적화 됩니다. 블록 blob과 같은 추가 blob은 블록으로 구성 되지만 추가 blob에 새 블록을 추가 하면 항상 blob 끝에 추가 됩니다. 업데이트 하거나 추가 blob의 기존 블록을 삭제할 수 없습니다. 추가 blob의 블록 Id는 블록 blob으로 노출 되지 않습니다.

추가 blob의 각 블록에는 최대 4MB까지 크기가 다양할 수 있습니다 및 추가 blob는 최대 50,000 개의 블록을 포함할 수 있습니다. 추가 blob의 최대 크기 (4 X 50,000 개 블록) 보다 약간 더 195GB 되므로 합니다.

다음 예제에서는 새 추가 blob을 만들고 간단한 로깅 작업을 시뮬레이션에 일부 데이터를 추가 합니다.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

참조 [이해 블록 Blob, 페이지 Blob 및 추가 Blob](https://msdn.microsoft.com/library/azure/ee691964.aspx) 세 가지 blob 유형의 차이점에 대 한 자세한 내용은 합니다.

## <a name="concurrent-access"></a>동시 액세스

여러 클라이언트 또는 여러 프로세스 인스턴스에서 blob에 대 한 동시 액세스를 지원, 사용할 수 있습니다 **Etag** 하거나 **임대**합니다.

* **Etag** -blob 또는 컨테이너를 다른 프로세스에서 수정 되었다는 사실을 감지 하는 방법을 제공 합니다.

* **임대** -가져오는 단독, 갱신 가능, 쓰기 또는 특정 기간에 대 한 blob에 대 한 액세스를 삭제 하는 방법을 제공 합니다.

자세한 내용은 [Microsoft Azure Storage에서 동시성 관리](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/)합니다.

## <a name="naming-containers"></a>명명 컨테이너

Azure storage의 모든 blob 컨테이너에 있어야 합니다. 컨테이너는 blob 이름의 일부를 형성 합니다. 예를 들어 `mydata` 이러한 샘플 blob Uri에서에서 컨테이너의 이름입니다.

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

컨테이너 이름에는 다음 명명 규칙을 따르는 유효한 DNS 이름 이어야 합니다.

1. 컨테이너 이름은 문자 또는 숫자로 시작 해야 하며 문자, 숫자 및 대시 (-) 문자만 포함할 수 있습니다.
1. 모든 대시 (-) 문자 바로 앞뒤에 뒤에 문자 또는 숫자로; 컨테이너 이름에서 연속 대시 허용 되지 않습니다.
1. 컨테이너 이름의 모든 문자는 소문자 여야 합니다.
1. 컨테이너 이름은 3 ~ 63 자에서에서 이어야 합니다.

참고 컨테이너의 이름을 항상 소문자 여야 합니다. 컨테이너 이름에는 대문자를 포함 하거나 컨테이너 명명 규칙 위반을 경우 400 오류 (잘못 된 요청)를 나타날 수 있습니다.

## <a name="managing-security-for-blobs"></a>Blob에 대 한 보안 관리

기본적으로 Azure Storage 데이터 보안 유지를 계정 액세스 키를 보유 하는 계정 소유자에 대 한 액세스를 제한 하 여 합니다. 저장소 계정의 blob 데이터를 공유 해야 할 경우 계정 액세스 키의 보안을 손상 시 키 지 않고도 중요 한 것입니다. 또한 Azure Storage에 연결을 통해 서 안전 하다는 것을 확인 하려면 blob 데이터를 암호화할 수 있습니다.

### <a name="controlling-access-to-blob-data"></a>Blob 데이터에 대 한 액세스를 제어합니다.

기본적으로 저장소 계정의 blob 데이터는 저장소 계정 소유자만 액세스할 수 있습니다. 기본적으로 계정 액세스 키를 필요 Blob storage에 대 한 요청을 인증 합니다. 그러나 다음 다른 사용자에 게 특정 blob 데이터를 사용할 수 있도록 하는 것이 좋습니다.

Blob storage에 대 한 액세스를 제어 하는 방법에 대 한 세부 정보를 참조 하세요 [액세스 제어에 blob 저장소 섹션에 대 한.NET 가이드](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data)합니다.


### <a name="encrypting-blob-data"></a>Blob 데이터를 암호화합니다.

Azure Storage 클라이언트와 서버에서 blob 데이터를 암호화를 지원 합니다.

Blob 데이터를 암호화에 대 한 내용은 참조 하세요 [암호화 blob 저장소 섹션에 대 한.NET 가이드](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data)합니다.

## <a name="next-steps"></a>다음 단계

이제 Blob 저장소의 기본 사항을 배웠으므로 다음 링크를 자세히 알아보세요.

### <a name="tools"></a>도구
- [F # AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/) 는 F # 형식 공급자는 Blob, 테이블 및 큐 Azure Storage 자산을 탐색 하 고 쉽게 CRUD 작업을 적용할 수 있습니다.
- [FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) Microsoft Azure Table Storage 서비스를 사용 하는 F # API
- [Microsoft Azure Storage 탐색기 (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) 는 Windows, OS X 및 Linux에서 Azure Storage 데이터로 시각적으로 작업할 수 있도록 하는 Microsoft에서 무료로 사용할 수 있는 독립 실행형 앱입니다.

### <a name="blob-storage-reference"></a>Blob storage 참조

- [.NET 용 azure Storage Api](/dotnet/api/overview/azure/storage)
- [Azure Storage 서비스 REST API 참조](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a>관련된 지침

- [C#에서 Azure Blob Storage 시작](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [Windows에서 AzCopy 명령줄 유틸리티로 데이터 전송](/azure/storage/common/storage-use-azcopy)
- [Linux에서 AzCopy 명령줄 유틸리티로 데이터 전송](/azure/storage/common/storage-use-azcopy-linux)
- [Azure Storage 연결 문자열 구성](/azure/storage/common/storage-configure-connection-string)
- [Azure Storage 팀 블로그](https://blogs.msdn.microsoft.com/windowsazurestorage/)
