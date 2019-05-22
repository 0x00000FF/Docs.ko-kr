---
title: '자습서: 웹 사이트 주석 분석 -이진 분류'
description: 이 자습서에서는 웹 사이트 주석에서 감정을 분류하고 적절한 조치를 취하는 .NET Core 콘솔 애플리케이션을 만드는 방법을 보여 줍니다. 이 감정 이진 분류자는 Visual Studio 2017에서 C#을 사용합니다.
ms.date: 04/18/2019
ms.topic: tutorial
ms.custom: mvc, seodec18
ms.openlocfilehash: 1989a11a2f06ce4d713d6c3ecc70de0da606604e
ms.sourcegitcommit: 438824ff21f77c4301c6ba8a89a106114aa27bc8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65462225"
---
# <a name="tutorial-analyze-sentiment-of-website-comments-with-binary-classification-in-mlnet"></a><span data-ttu-id="96ad1-104">자습서: ML.NET에서 이진 분류를 사용하여 웹 사이트 주석의 감정 분석</span><span class="sxs-lookup"><span data-stu-id="96ad1-104">Tutorial: Analyze sentiment of website comments with binary classification in ML.NET</span></span>

<span data-ttu-id="96ad1-105">이 자습서에서는 웹 사이트 주석에서 감정을 분류하고 적절한 조치를 취하는 .NET Core 콘솔 애플리케이션을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-105">This tutorial shows you how to create a .NET Core console application that classifies sentiment from website comments and takes the appropriate action.</span></span> <span data-ttu-id="96ad1-106">이 감정 이진 분류자는 Visual Studio 2017에서 C#을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-106">The binary sentiment classifier uses C# in Visual Studio 2017.</span></span>

<span data-ttu-id="96ad1-107">이 자습서에서는 다음과 같은 작업을 수행하는 방법을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-107">In this tutorial, you learn how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="96ad1-108">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="96ad1-108">Create a console application</span></span>
> * <span data-ttu-id="96ad1-109">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="96ad1-109">Prepare data</span></span>
> * <span data-ttu-id="96ad1-110">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="96ad1-110">Load the data</span></span>
> * <span data-ttu-id="96ad1-111">모델 빌드 및 학습</span><span class="sxs-lookup"><span data-stu-id="96ad1-111">Build and train the model</span></span>
> * <span data-ttu-id="96ad1-112">모델 평가</span><span class="sxs-lookup"><span data-stu-id="96ad1-112">Evaluate the model</span></span>
> * <span data-ttu-id="96ad1-113">모델로 예측 수행</span><span class="sxs-lookup"><span data-stu-id="96ad1-113">Use the model to make a prediction</span></span>
> * <span data-ttu-id="96ad1-114">결과 보기</span><span class="sxs-lookup"><span data-stu-id="96ad1-114">See the results</span></span>

<span data-ttu-id="96ad1-115">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-115">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="96ad1-116">전제 조건</span><span class="sxs-lookup"><span data-stu-id="96ad1-116">Prerequisites</span></span>

* <span data-ttu-id="96ad1-117">“.NET Core 플랫폼 간 개발” 워크로드가 설치된 [Visual Studio 2017 15.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017)</span><span class="sxs-lookup"><span data-stu-id="96ad1-117">[Visual Studio 2017 15.6 or later](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2017) with the ".NET Core cross-platform development" workload installed</span></span>

* <span data-ttu-id="96ad1-118">[UCI Sentiment Labeled Sentences 데이터 세트](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)(zip 파일)</span><span class="sxs-lookup"><span data-stu-id="96ad1-118">[UCI Sentiment Labeled Sentences dataset](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip) (ZIP file)</span></span>

## <a name="create-a-console-application"></a><span data-ttu-id="96ad1-119">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="96ad1-119">Create a console application</span></span>

1. <span data-ttu-id="96ad1-120">"SentimentAnalysis"라고 하는 **.NET Core 콘솔 애플리케이션**을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-120">Create a **.NET Core Console Application** called "SentimentAnalysis".</span></span>

2. <span data-ttu-id="96ad1-121">프로젝트에서 *Data* 디렉터리를 만들어 데이터 세트 파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-121">Create a directory named *Data* in your project to save your data set files.</span></span>

3. <span data-ttu-id="96ad1-122">**Microsoft.ML NuGet 패키지**를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-122">Install the **Microsoft.ML NuGet Package**:</span></span>

    <span data-ttu-id="96ad1-123">솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-123">In Solution Explorer, right-click on your project and select **Manage NuGet Packages**.</span></span> <span data-ttu-id="96ad1-124">패키지 소스로 "nuget.org"를 선택하고 **찾아보기** 탭을 선택합니다. **Microsoft.ML**을 검색하고 원하는 패키지를 선택한 다음, **설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-124">Choose "nuget.org" as the package source, and then select the **Browse** tab. Search for **Microsoft.ML**, select the package you want, and then select the **Install** button.</span></span> <span data-ttu-id="96ad1-125">선택한 패키지에 대한 사용 조건에 동의하여 설치를 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-125">Proceed with the installation by agreeing to the the license terms for the package you choose.</span></span> <span data-ttu-id="96ad1-126">**Microsoft.ML.FastTree** NuGet 패키지에 대해 동일한 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-126">Do the same for the **Microsoft.ML.FastTree** NuGet package.</span></span>

## <a name="prepare-your-data"></a><span data-ttu-id="96ad1-127">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="96ad1-127">Prepare your data</span></span>

> [!NOTE]
> <span data-ttu-id="96ad1-128">이 자습서의 데이터 세트는 ‘From Group to Individual Labels using Deep Features’(Kotzias</span><span class="sxs-lookup"><span data-stu-id="96ad1-128">The datasets for this tutorial are from the 'From Group to Individual Labels using Deep Features', Kotzias et.</span></span> <span data-ttu-id="96ad1-129">외,</span><span class="sxs-lookup"><span data-stu-id="96ad1-129">al,.</span></span> <span data-ttu-id="96ad1-130">KDD 2015)에서 제공되고 UCI Machine Learning Repository(Dua, D. 및 Karra Taniskidou, E. (2017))에서 호스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-130">KDD 2015, and hosted at the UCI Machine Learning Repository - Dua, D. and Karra Taniskidou, E. (2017).</span></span> <span data-ttu-id="96ad1-131">UCI Machine Learning Repository[http://archive.ics.uci.edu/ml].</span><span class="sxs-lookup"><span data-stu-id="96ad1-131">UCI Machine Learning Repository [http://archive.ics.uci.edu/ml].</span></span> <span data-ttu-id="96ad1-132">Irvine, CA: University of California, School of Information and Computer Science.</span><span class="sxs-lookup"><span data-stu-id="96ad1-132">Irvine, CA: University of California, School of Information and Computer Science.</span></span>

1. <span data-ttu-id="96ad1-133">[UCI Sentiment Labeled Sentences 데이터 세트 ZIP 파일](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip)을 다운로드하여 압축을 풉니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-133">Download [UCI Sentiment Labeled Sentences dataset ZIP file](https://archive.ics.uci.edu/ml/machine-learning-databases/00331/sentiment%20labelled%20sentences.zip), and unzip.</span></span>

2. <span data-ttu-id="96ad1-134">만든 *Data* 디렉터리에 `yelp_labelled.txt` 파일을 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-134">Copy the `yelp_labelled.txt` file into the *Data* directory you created.</span></span>

3. <span data-ttu-id="96ad1-135">솔루션 탐색기에서 `yelp_labeled.txt` 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-135">In Solution Explorer, right-click the `yelp_labeled.txt` file and select **Properties**.</span></span> <span data-ttu-id="96ad1-136">**고급** 아래에서 **출력 디렉터리에 복사** 값을 **변경된 내용만 복사**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-136">Under **Advanced**, change the value of **Copy to Output Directory** to **Copy if newer**.</span></span>

### <a name="create-classes-and-define-paths"></a><span data-ttu-id="96ad1-137">클래스 만들기 및 경로 정의</span><span class="sxs-lookup"><span data-stu-id="96ad1-137">Create classes and define paths</span></span>

1. <span data-ttu-id="96ad1-138">*Program.cs* 파일 맨 위에 다음 추가 `using` 문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-138">Add the following additional `using` statements to the top of the *Program.cs* file:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddUsings "Add necessary usings")]

2. <span data-ttu-id="96ad1-139">최근에 다운로드한 데이터 세트 파일 경로 및 저장된 모델 파일 경로를 포함할 두 개의 글로벌 필드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-139">Create two global fields to hold the recently downloaded dataset file path and the saved model file path:</span></span>

    * <span data-ttu-id="96ad1-140">`_dataPath`에는 모델을 학습시키는 데 사용되는 데이터 세트의 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-140">`_dataPath` has the path to the dataset used to train the model.</span></span>
    * <span data-ttu-id="96ad1-141">`_modelPath`에는 학습된 모델이 저장되는 경로가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-141">`_modelPath` has the path where the trained model is saved.</span></span>

3. <span data-ttu-id="96ad1-142">`Main` 메서드 바로 위의 줄에 다음 코드를 추가하여 해당 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-142">Add the following code to the line right above the `Main` method to specify the paths:</span></span>

    [!code-csharp[Declare global variables](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DeclareGlobalVariables "Declare global variables")]

4. <span data-ttu-id="96ad1-143">이제 입력 데이터 및 예측에 대한 클래스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-143">Next, create classes for your input data and predictions.</span></span> <span data-ttu-id="96ad1-144">새 클래스를 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-144">Add a new class to your project:</span></span>

    - <span data-ttu-id="96ad1-145">**솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **추가** > **새 항목**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-145">In **Solution Explorer**, right-click the project, and then select **Add** > **New Item**.</span></span>

    - <span data-ttu-id="96ad1-146">**새 항목 추가** 대화 상자에서 **클래스**를 선택하고 **이름** 필드를 *SentimentData.cs*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-146">In the **Add New Item** dialog box, select **Class** and change the **Name** field to *SentimentData.cs*.</span></span> <span data-ttu-id="96ad1-147">그런 다음, **추가** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-147">Then, select the **Add** button.</span></span>

5. <span data-ttu-id="96ad1-148">*SentimentData.cs* 파일이 코드 편집기에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-148">The *SentimentData.cs* file opens in the code editor.</span></span> <span data-ttu-id="96ad1-149">다음 `using` 문을 *SentimentData.cs*의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-149">Add the following `using` statement to the top of *SentimentData.cs*:</span></span>

    [!code-csharp[AddUsings](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#AddUsings "Add necessary usings")]

6. <span data-ttu-id="96ad1-150">기존 클래스 정의를 제거하고 두 개의 클래스 `SentimentData` 및 `SentimentPrediction`가 있는 다음 코드를 *SentimentData.cs* 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-150">Remove the existing class definition and add the following code, which has two classes `SentimentData` and `SentimentPrediction`, to the *SentimentData.cs* file:</span></span>

    [!code-csharp[DeclareTypes](~/samples/machine-learning/tutorials/SentimentAnalysis/SentimentData.cs#DeclareTypes "Declare data record types")]

### <a name="how-the-data-was-prepared"></a><span data-ttu-id="96ad1-151">데이터를 준비하는 방법</span><span class="sxs-lookup"><span data-stu-id="96ad1-151">How the data was prepared</span></span>
<span data-ttu-id="96ad1-152">입력 데이터 세트 클래스 `SentimentData`는 사용자 주석에 대한 `string`(`SentimentText`) 및 감정에 대해 1(긍정) 또는 0(부정) 값을 갖는 `bool`(`Sentiment`)를 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-152">The input dataset class, `SentimentData`, has a `string` for user comments (`SentimentText`) and a `bool` (`Sentiment`) value of either 1 (positive) or 0 (negative) for sentiment.</span></span> <span data-ttu-id="96ad1-153">두 필드에는 각 필드의 데이터 파일 순서를 설명하는 [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) 특성이 연결되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-153">Both fields have [LoadColumn](xref:Microsoft.ML.Data.LoadColumnAttribute.%23ctor%28System.Int32%29) attributes attached to them, which describes the data file order of each field.</span></span>  <span data-ttu-id="96ad1-154">또한 `Sentiment` 속성에는 `Label` 필드로 지정하는 [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-154">In addition, the `Sentiment` property has a [ColumnName](xref:Microsoft.ML.Data.ColumnNameAttribute.%23ctor%2A) attribute to designate it as the `Label` field.</span></span> <span data-ttu-id="96ad1-155">다음 예제 파일에는 머리글 행이 없고 다음과 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-155">The following example file doesn't have a header row, and looks like this:</span></span>

|<span data-ttu-id="96ad1-156">SentimentText</span><span class="sxs-lookup"><span data-stu-id="96ad1-156">SentimentText</span></span>                         |<span data-ttu-id="96ad1-157">감정(레이블)</span><span class="sxs-lookup"><span data-stu-id="96ad1-157">Sentiment (Label)</span></span> |
|--------------------------------------|----------|
|<span data-ttu-id="96ad1-158">웨이트리스의 서비스가 좀 느렸습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-158">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="96ad1-159">0</span><span class="sxs-lookup"><span data-stu-id="96ad1-159">0</span></span>     |
|<span data-ttu-id="96ad1-160">모양이 별로 였습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-160">Crust is not good.</span></span>                    |    <span data-ttu-id="96ad1-161">0</span><span class="sxs-lookup"><span data-stu-id="96ad1-161">0</span></span>     |
|<span data-ttu-id="96ad1-162">우와... 여기가 좋았습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-162">Wow... Loved this place.</span></span>              |    <span data-ttu-id="96ad1-163">1</span><span class="sxs-lookup"><span data-stu-id="96ad1-163">1</span></span>     |
|<span data-ttu-id="96ad1-164">서비스가 매우 신속합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-164">Service was very prompt.</span></span>              |    <span data-ttu-id="96ad1-165">1</span><span class="sxs-lookup"><span data-stu-id="96ad1-165">1</span></span>     |

<span data-ttu-id="96ad1-166">`SentimentPrediction`은 모델 학습 후 사용되는 예측 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-166">`SentimentPrediction` is the prediction class used after the model training.</span></span> <span data-ttu-id="96ad1-167">예측과 함께 `SentimentText`를 표시하기 위해 `SentimentData`에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-167">It inherits from `SentimentData` for displaying the `SentimentText` with the predictions.</span></span> <span data-ttu-id="96ad1-168">`SentimentPrediction`에는 단일 부울(`Sentiment`)과 `PredictedLabel` `ColumnName` 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-168">`SentimentPrediction` has a single boolean (`Sentiment`) and a `PredictedLabel` `ColumnName` attribute.</span></span> <span data-ttu-id="96ad1-169">`Label`은 세트를 만들고 학습시키는 데 사용되며 분할된 테스트 데이터 세트와 함께 모델을 평가하는 데도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-169">The `Label` is used to create and train the model, and it's also used with the split out test dataset to evaluate the model.</span></span> <span data-ttu-id="96ad1-170">`PredictedLabel`은 예측 및 평가 중에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-170">The `PredictedLabel` is used during prediction and evaluation.</span></span> <span data-ttu-id="96ad1-171">평가를 위해 학습 데이터, 예측 값 및 모델이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-171">For evaluation, training data, the predicted values, and the model are used.</span></span>

<span data-ttu-id="96ad1-172">[MLContext 클래스](xref:Microsoft.ML.MLContext)는 모든 ML.NET 작업의 시작 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-172">The [MLContext class](xref:Microsoft.ML.MLContext) is a starting point for all ML.NET operations.</span></span> <span data-ttu-id="96ad1-173">`mlContext`를 초기화하면 모델 생성 워크플로 개체 간에 공유할 수 있는 새 ML.NET 환경이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-173">Initializing `mlContext` creates a new ML.NET environment that can be shared across the model creation workflow objects.</span></span> <span data-ttu-id="96ad1-174">개념적으로 Entity Framework의 `DBContext`와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-174">It's similar, conceptually, to `DBContext` in Entity Framework.</span></span>

## <a name="load-the-data"></a><span data-ttu-id="96ad1-175">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="96ad1-175">Load the data</span></span>
<span data-ttu-id="96ad1-176">ML.NET의 데이터는 [IDataView 클래스](xref:Microsoft.ML.IDataView)로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-176">Data in ML.NET is represented as an [IDataView class](xref:Microsoft.ML.IDataView).</span></span> <span data-ttu-id="96ad1-177">`IDataView`는 표 형식 데이터(숫자 및 텍스트)를 유연하고 효율적으로 설명하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-177">`IDataView` is a flexible, efficient way of describing tabular data (numeric and text).</span></span> <span data-ttu-id="96ad1-178">데이터를 텍스트 파일 또는 실시간(예: SQL 데이터베이스 또는 로그 파일)에서 `IDataView` 개체로 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-178">Data can be loaded from a text file or in real time (for example, SQL database or log files) to an `IDataView` object.</span></span>

<span data-ttu-id="96ad1-179">앱을 준비한 다음, 데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-179">You prepare the app, and then load data:</span></span>

1. <span data-ttu-id="96ad1-180">`Main` 메서드의 `Console.WriteLine("Hello World!")` 줄을 다음 코드로 바꾸어 mlContext 변수를 선언하고 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-180">Replace the `Console.WriteLine("Hello World!")` line in the `Main` method with the following code to declare and initialize the mlContext variable:</span></span>

    [!code-csharp[CreateMLContext](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateMLContext "Create the ML Context")]

2. <span data-ttu-id="96ad1-181">`Main()` 메서드에 아래 코드를 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-181">Add the following as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallLoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallLoadData)]

3. <span data-ttu-id="96ad1-182">다음 코드를 사용하여 `Main()` 메서드 바로 뒤에 `LoadData()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-182">Create the `LoadData()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static TrainTestData LoadData(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="96ad1-183">`LoadData()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-183">The `LoadData()` method executes the following tasks:</span></span>

    * <span data-ttu-id="96ad1-184">데이터를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-184">Loads the data.</span></span>
    * <span data-ttu-id="96ad1-185">로드된 데이터 세트를 학습 및 테스트 세트로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-185">Splits the loaded dataset into train and test datasets.</span></span>
    * <span data-ttu-id="96ad1-186">분할된 학습 및 테스트 데이터 세트를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-186">Returns the split train and test datasets.</span></span>

4. <span data-ttu-id="96ad1-187">다음 코드를 `LoadData()` 메서드의 첫 번째 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-187">Add the following code as the first line of the `LoadData()` method:</span></span>

    [!code-csharp[LoadData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#LoadData "loading dataset")]

    <span data-ttu-id="96ad1-188">[LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29)은 데이터 스키마를 정의하고 파일에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-188">The [LoadFromTextFile()](xref:Microsoft.ML.TextLoaderSaverCatalog.LoadFromTextFile%60%601%28Microsoft.ML.DataOperationsCatalog,System.String,System.Char,System.Boolean,System.Boolean,System.Boolean,System.Boolean%29) defines the data schema and reads in the file.</span></span> <span data-ttu-id="96ad1-189">데이터 경로 변수를 가져와서 `IDataView`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-189">It takes in the data path variables and returns an `IDataView`.</span></span>

### <a name="split-the-dataset-for-model-training-and-testing"></a><span data-ttu-id="96ad1-190">데이터 세트를 모델 학습 및 테스트용으로 분할</span><span class="sxs-lookup"><span data-stu-id="96ad1-190">Split the dataset for model training and testing</span></span>

<span data-ttu-id="96ad1-191">모델을 준비할 때는 일부 데이터 세트는 학습에, 일부 데이터 세트는 모델 정확도 테스트에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-191">When preparing a model, you use part of the dataset to train it and part of the dataset to test the model's accuracy.</span></span>

1. <span data-ttu-id="96ad1-192">로드된 데이터를 필요한 데이터 세트로 분할하려면 `LoadData()` 메서드에 아래 코드를 다음 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-192">To split the loaded data into the needed datasets, add the following code as the next line in the `LoadData()` method:</span></span>

    [!code-csharp[SplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#SplitData "Split the Data")]

    <span data-ttu-id="96ad1-193">앞의 코드는 [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) 메서드를 사용하여 로드된 데이터 세트를 학습으로 분할하고 데이터 세트를 테스트하며 [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) 클래스에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-193">The previous code uses the [TrainTestSplit()](xref:Microsoft.ML.DataOperationsCatalog.TrainTestSplit%2A) method to split the loaded dataset into train and test datasets and return them in the [TrainTestData](xref:Microsoft.ML.DataOperationsCatalog.TrainTestData) class.</span></span> <span data-ttu-id="96ad1-194">`testFraction` 매개 변수로 데이터의 테스트 집합 백분율을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-194">Specify the test set percentage of data with the `testFraction`parameter.</span></span> <span data-ttu-id="96ad1-195">기본값은 10%이며, 여기서는 20%를 사용하여 데이터를 더 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-195">The default is 10%, in this case you use 20% to evaluate more data.</span></span>

2. <span data-ttu-id="96ad1-196">`splitDataView` 메서드의 끝에 `LoadData()`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-196">Return the `splitDataView` at the end of the `LoadData()` method:</span></span>

    [!code-csharp[ReturnSplitData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnSplitData)]

## <a name="build-and-train-the-model"></a><span data-ttu-id="96ad1-197">모델 빌드 및 학습</span><span class="sxs-lookup"><span data-stu-id="96ad1-197">Build and train the model</span></span>

1. <span data-ttu-id="96ad1-198">`BuildAndTrainModel` 메서드에 다음 호출을 `Main()` 메서드의 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-198">Add the following call to the `BuildAndTrainModel`method as the next line of code in the `Main()` method:</span></span>

    [!code-csharp[CallBuildAndTrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallBuildAndTrainModel)]

    <span data-ttu-id="96ad1-199">`BuildAndTrainModel()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-199">The `BuildAndTrainModel()` method executes the following tasks:</span></span>

    * <span data-ttu-id="96ad1-200">데이터를 추출하고 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-200">Extracts and transforms the data.</span></span>
    * <span data-ttu-id="96ad1-201">모델을 학습시킵니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-201">Trains the model.</span></span>
    * <span data-ttu-id="96ad1-202">테스트 데이터를 기반으로 감정을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-202">Predicts sentiment based on test data.</span></span>
    * <span data-ttu-id="96ad1-203">모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-203">Returns the model.</span></span>

2. <span data-ttu-id="96ad1-204">다음 코드를 사용하여 `Main()` 메서드 바로 뒤에 `BuildAndTrainModel()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-204">Create the `BuildAndTrainModel()` method, just after the `Main()` method, using the following code:</span></span>

    ```csharp
    public static ITransformer BuildAndTrainModel(MLContext mlContext, IDataView splitTrainSet)
    {

    }
    ```

### <a name="extract-and-transform-the-data"></a><span data-ttu-id="96ad1-205">데이터 추출 및 변환</span><span class="sxs-lookup"><span data-stu-id="96ad1-205">Extract and transform the data</span></span>

1. <span data-ttu-id="96ad1-206">`FeaturizeText`를 다음 코드 줄로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-206">Call `FeaturizeText` as the next line of code:</span></span>

    [!code-csharp[FeaturizeText](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#FeaturizeText "Featurize the text")]

    <span data-ttu-id="96ad1-207">이전 코드의 `FeaturizeText()` 메서드는 텍스트 열(`SentimentText`)을 기계 학습 알고리즘에서 사용하는 숫자 키 형식 `Features` 열로 변환하여 새 데이터 세트 열로 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-207">The `FeaturizeText()` method in the previous code converts the text column (`SentimentText`) into a numeric key type `Features` column used by the machine learning algorithm and adds it as a new dataset column:</span></span>

    |<span data-ttu-id="96ad1-208">SentimentText</span><span class="sxs-lookup"><span data-stu-id="96ad1-208">SentimentText</span></span>                         |<span data-ttu-id="96ad1-209">감정</span><span class="sxs-lookup"><span data-stu-id="96ad1-209">Sentiment</span></span> |<span data-ttu-id="96ad1-210">기능</span><span class="sxs-lookup"><span data-stu-id="96ad1-210">Features</span></span>              |
    |--------------------------------------|----------|----------------------|
    |<span data-ttu-id="96ad1-211">웨이트리스의 서비스가 좀 느렸습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-211">Waitress was a little slow in service.</span></span>|    <span data-ttu-id="96ad1-212">0</span><span class="sxs-lookup"><span data-stu-id="96ad1-212">0</span></span>     |<span data-ttu-id="96ad1-213">[0.76, 0.65, 0.44, …]</span><span class="sxs-lookup"><span data-stu-id="96ad1-213">[0.76, 0.65, 0.44, …]</span></span> |
    |<span data-ttu-id="96ad1-214">모양이 별로 였습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-214">Crust is not good.</span></span>                    |    <span data-ttu-id="96ad1-215">0</span><span class="sxs-lookup"><span data-stu-id="96ad1-215">0</span></span>     |<span data-ttu-id="96ad1-216">[0.98, 0.43, 0.54, …]</span><span class="sxs-lookup"><span data-stu-id="96ad1-216">[0.98, 0.43, 0.54, …]</span></span> |
    |<span data-ttu-id="96ad1-217">우와... 여기가 좋았습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-217">Wow... Loved this place.</span></span>              |    <span data-ttu-id="96ad1-218">1</span><span class="sxs-lookup"><span data-stu-id="96ad1-218">1</span></span>     |<span data-ttu-id="96ad1-219">[0.35, 0.73, 0.46, …]</span><span class="sxs-lookup"><span data-stu-id="96ad1-219">[0.35, 0.73, 0.46, …]</span></span> |
    |<span data-ttu-id="96ad1-220">서비스가 매우 신속합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-220">Service was very prompt.</span></span>              |    <span data-ttu-id="96ad1-221">1</span><span class="sxs-lookup"><span data-stu-id="96ad1-221">1</span></span>     |<span data-ttu-id="96ad1-222">[0.39, 0, 0.75, …]</span><span class="sxs-lookup"><span data-stu-id="96ad1-222">[0.39, 0, 0.75, …]</span></span>    |

### <a name="add-a-learning-algorithm"></a><span data-ttu-id="96ad1-223">학습 알고리즘 추가</span><span class="sxs-lookup"><span data-stu-id="96ad1-223">Add a learning algorithm</span></span>

<span data-ttu-id="96ad1-224">이 앱은 항목 또는 데이터 행을 분류하는 분류 알고리즘을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-224">This app uses a classification algorithm that categorizes items or rows of data.</span></span> <span data-ttu-id="96ad1-225">앱은 웹 사이트 주석을 긍정 또는 부정으로 분류하므로 이진 분류 작업을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-225">The app categorizes website comments as either positive or negative, so use the binary classification task.</span></span>

<span data-ttu-id="96ad1-226">`BuildAndTrainModel()`의 다음 코드 줄로 다음을 추가하여 데이터 변환 정의에 기계 학습 작업을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-226">Append the machine learning task to the data transformation definitions by adding the following as the next line of code in `BuildAndTrainModel()`:</span></span>

[!code-csharp[SdcaLogisticRegressionBinaryTrainer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddTrainer "Add a SdcaLogisticRegressionBinaryTrainer")]

<span data-ttu-id="96ad1-227">[SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer)는 분류 학습 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-227">The [SdcaLogisticRegressionBinaryTrainer](xref:Microsoft.ML.Trainers.SdcaLogisticRegressionBinaryTrainer) is your classification training algorithm.</span></span> <span data-ttu-id="96ad1-228">이것은 `estimator`에 추가되며, 기록 데이터에서 학습할 기능화된 `SentimentText`(`Features`) 및 `Label` 입력 매개 변수를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-228">This is appended to the `estimator` and accepts the featurized `SentimentText` (`Features`) and the `Label` input parameters to learn from the historic data.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="96ad1-229">모델 학습</span><span class="sxs-lookup"><span data-stu-id="96ad1-229">Train the model</span></span>

<span data-ttu-id="96ad1-230">모델을 `splitTrainSet` 데이터에 맞추고 `BuildAndTrainModel()` 메서드에서 다음 줄의 코드로 다음 항목을 추가하여 학습된 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-230">Fit the model to the `splitTrainSet` data and return the trained model by adding the following as the next line of code in the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[TrainModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TrainModel "Train the model")]

<span data-ttu-id="96ad1-231">[Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) 메서드는 데이터 세트를 변환하고 학습을 적용하여 모델을 학습합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-231">The [Fit()](xref:Microsoft.ML.Trainers.MatrixFactorizationTrainer.Fit%28Microsoft.ML.IDataView,Microsoft.ML.IDataView%29) method trains your model by transforming the dataset and applying the training.</span></span>

### <a name="return-the-model-trained-to-use-for-evaluation"></a><span data-ttu-id="96ad1-232">평가에 사용하기 위해 학습된 모델 반환</span><span class="sxs-lookup"><span data-stu-id="96ad1-232">Return the model trained to use for evaluation</span></span>

 <span data-ttu-id="96ad1-233">`BuildAndTrainModel()` 메서드의 끝에 모델을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-233">Return the model at the end of the `BuildAndTrainModel()` method:</span></span>

[!code-csharp[ReturnModel](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#ReturnModel "Return the model")]

## <a name="evaluate-the-model"></a><span data-ttu-id="96ad1-234">모델 평가</span><span class="sxs-lookup"><span data-stu-id="96ad1-234">Evaluate the model</span></span>

<span data-ttu-id="96ad1-235">모델을 학습한 후 테스트 데이터를 사용하여 모델의 성능 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-235">After your model is trained, use your test data validate the model's performance.</span></span>

1. <span data-ttu-id="96ad1-236">다음 코드로 `BuildAndTrainModel()` 바로 뒤에 `Evaluate()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-236">Create the `Evaluate()` method, just after `BuildAndTrainModel()`, with the following code:</span></span>

    ```csharp
    public static void Evaluate(MLContext mlContext, ITransformer model, IDataView splitTestSet)
    {

    }
    ```

    <span data-ttu-id="96ad1-237">`Evaluate()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-237">The `Evaluate()` method executes the following tasks:</span></span>

    * <span data-ttu-id="96ad1-238">테스트 데이터 세트를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-238">Loads the test dataset.</span></span>
    * <span data-ttu-id="96ad1-239">BinaryClassification 평가자를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-239">Creates the BinaryClassification evaluator.</span></span>
    * <span data-ttu-id="96ad1-240">모델을 평가하고 메트릭을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-240">Evaluates the model and creates metrics.</span></span>
    * <span data-ttu-id="96ad1-241">메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-241">Displays the metrics.</span></span>

2. <span data-ttu-id="96ad1-242">다음 코드를 사용하여 `BuildAndTrainModel()` 메서드 호출 바로 아래에 `Main()` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-242">Add a call to the new method from the `Main()` method, right under the `BuildAndTrainModel()` method call, using the following code:</span></span>

    [!code-csharp[CallEvaluate](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallEvaluate "Call the Evaluate method")]

3. <span data-ttu-id="96ad1-243">`Evaluate()`에 다음 코드를 추가하여 `splitTestSet`데이터를 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-243">Transform the `splitTestSet` data by adding the following code to `Evaluate()`:</span></span>

    [!code-csharp[PredictWithTransformer](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#TransformData "Predict using the Transformer")]

    <span data-ttu-id="96ad1-244">이전 코드는 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 메서드를 사용하여 여러 제공된 테스트 데이터 세트 입력 행에 대한 예측을 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-244">The previous code uses the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method to make predictions for multiple provided input rows of a test dataset.</span></span>

4. <span data-ttu-id="96ad1-245">`Evaluate()` 메서드에서 다음 코드 줄로 다음 항목을 추가하여 모델을 평가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-245">Evaluate the model by adding the following as the next line of code in the `Evaluate()` method:</span></span>

    [!code-csharp[ComputeMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Evaluate "Compute Metrics")]

<span data-ttu-id="96ad1-246">예측 집합(`predictions`)이 있으면 [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) 메서드는 모델을 평가하여 예측된 값을 테스트 데이터 세트의 실제 `Labels`와 비교하고, 모델 수행 방법에 대한 [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-246">Once you have the prediction set (`predictions`), the [Evaluate()](xref:Microsoft.ML.BinaryClassificationCatalog.Evaluate%2A) method assesses the model, which compares the predicted values with the actual `Labels` in the test dataset and returns a [CalibratedBinaryClassificationMetrics](xref:Microsoft.ML.Data.CalibratedBinaryClassificationMetrics) object on how the model is performing.</span></span>

### <a name="displaying-the-metrics-for-model-validation"></a><span data-ttu-id="96ad1-247">모델 유효성 검사를 위해 메트릭 표시</span><span class="sxs-lookup"><span data-stu-id="96ad1-247">Displaying the metrics for model validation</span></span>

<span data-ttu-id="96ad1-248">다음 코드를 사용하여 메트릭을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-248">Use the following code to display the metrics:</span></span>

[!code-csharp[DisplayMetrics](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayMetrics "Display selected metrics")]

* <span data-ttu-id="96ad1-249">`Accuracy` 메트릭은 테스트 세트에서 정확한 예측의 비율인 모델 정확도를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-249">The `Accuracy` metric gets the accuracy of a model, which is the proportion of correct predictions in the test set.</span></span>

* <span data-ttu-id="96ad1-250">`AreaUnderRocCurve` 메트릭은 모델이 긍정 및 부정 클래스 분류의 정확도를 자신하는 정도를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-250">The `AreaUnderRocCurve` metric indicates how confident the model is correctly classifying the positive and negative classes.</span></span> <span data-ttu-id="96ad1-251">`AreaUnderRocCurve`를 가능한 근접하게 하고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-251">You want the `AreaUnderRocCurve` to be as close to one as possible.</span></span>

* <span data-ttu-id="96ad1-252">`F1Score` 메트릭은 모델의 F1 점수를 가져옵니다. [정밀도](../resources/glossary.md#precision)와 [회수](../resources/glossary.md#recall) 사이의 균형을 측정한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-252">The `F1Score` metric gets the model's F1 score, which is a measure of balance between [precision](../resources/glossary.md#precision) and [recall](../resources/glossary.md#recall).</span></span>  <span data-ttu-id="96ad1-253">`F1Score`를 가능한 근접하게 하고자 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-253">You want the `F1Score` to be as close to one as possible.</span></span>

### <a name="predict-the-test-data-outcome"></a><span data-ttu-id="96ad1-254">테스트 데이터 결과 예측</span><span class="sxs-lookup"><span data-stu-id="96ad1-254">Predict the test data outcome</span></span>

1. <span data-ttu-id="96ad1-255">다음 코드를 사용하여 `Evaluate()` 메서드 바로 뒤에 `UseModelWithSingleItem()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-255">Create the `UseModelWithSingleItem()` method, just after the `Evaluate()` method, using the following code:</span></span>

    ```csharp
    private static void UseModelWithSingleItem(MLContext mlContext, ITransformer model)
    {

    }
    ```

    <span data-ttu-id="96ad1-256">`UseModelWithSingleItem()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-256">The `UseModelWithSingleItem()` method executes the following tasks:</span></span>

    * <span data-ttu-id="96ad1-257">테스트 데이터의 단일 댓글을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-257">Creates a single comment of test data.</span></span>
    * <span data-ttu-id="96ad1-258">테스트 데이터를 기반으로 감정을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-258">Predicts sentiment based on test data.</span></span>
    * <span data-ttu-id="96ad1-259">보고를 위해 테스트 데이터 및 예측을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-259">Combines test data and predictions for reporting.</span></span>
    * <span data-ttu-id="96ad1-260">예측 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-260">Displays the predicted results.</span></span>

2. <span data-ttu-id="96ad1-261">다음 코드를 사용하여 `Evaluate()` 메서드 호출 바로 아래에 `Main()` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-261">Add a call to the new method from the `Main()` method, right under the `Evaluate()` method call, using the following code:</span></span>

    [!code-csharp[CallUseModelWithSingleItem](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithSingleItem "Call the UseModelWithSingleItem method")]

3. <span data-ttu-id="96ad1-262">다음 코드를 추가하여 `Predict()` 메서드의 첫 줄로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-262">Add the following code to create as the first line in the `Predict()` Method:</span></span>

    [!code-csharp[CreatePredictionEngine](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreatePredictionEngine1 "Create the PredictionEngine")]

    <span data-ttu-id="96ad1-263">[PredictionEngine](xref:Microsoft.ML.PredictionEngine%602)은 데이터의 단일 인스턴스를 전달한 다음, 이 단일 데이터 인스턴스에 대한 예측을 수행할 수 있는 편리한 API입니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-263">The [PredictionEngine](xref:Microsoft.ML.PredictionEngine%602) is a convenience API, which allows you to pass in and then perform a prediction on a single instance of data.</span></span>

4. <span data-ttu-id="96ad1-264">`SentimentData` 인스턴스를 만들어 댓글을 추가하여 `Predict()` 메서드에서 학습된 모델의 예측을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-264">Add a comment to test the trained model's prediction in the `Predict()` method by creating an instance of `SentimentData`:</span></span>

    [!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssue1 "Create test data for single prediction")]

5. <span data-ttu-id="96ad1-265">다음을 `UseModelWithSingleItem()` 메서드의 다음 코드 줄로 추가하여 테스트 주석 데이터를 `Prediction Engine`에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-265">Pass the test comment data to the `Prediction Engine` by adding the following as the next lines of code in the `UseModelWithSingleItem()` method:</span></span>

    [!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Predict "Create a prediction of sentiment")]

    <span data-ttu-id="96ad1-266">[Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) 함수는 단일 데이터 행에 대한 예측을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-266">The [Predict()](xref:Microsoft.ML.PredictionEngine%602.Predict%2A) function makes a prediction on a single row of data.</span></span>

6. <span data-ttu-id="96ad1-267">다음 코드를 사용하여 `SentimentText` 및 해당 감정 예측을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-267">Display `SentimentText` and corresponding sentiment prediction using the following code:</span></span>

    [!code-csharp[OutputPrediction](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#OutputPrediction "Display prediction output")]

## <a name="use-the-model-for-prediction"></a><span data-ttu-id="96ad1-268">예측에 모델 사용</span><span class="sxs-lookup"><span data-stu-id="96ad1-268">Use the model for prediction</span></span>

### <a name="deploy-and-predict-batch-items"></a><span data-ttu-id="96ad1-269">일괄 처리 항목 배포 및 예측</span><span class="sxs-lookup"><span data-stu-id="96ad1-269">Deploy and predict batch items</span></span>

1. <span data-ttu-id="96ad1-270">다음 코드를 사용하여 `UseModelWithSingleItem()` 메서드 바로 뒤에 `UseModelWithBatchItems()` 메서드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-270">Create the `UseModelWithBatchItems()` method, just after the `UseModelWithSingleItem()` method, using the following code:</span></span>

    ```csharp
    public static void UseModelWithBatchItems(MLContext mlContext)
    {

    }
    ```

    <span data-ttu-id="96ad1-271">`UseModelWithBatchItems()` 메서드는 다음 작업을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-271">The `UseModelWithBatchItems()` method executes the following tasks:</span></span>

    * <span data-ttu-id="96ad1-272">일괄 처리 테스트 데이터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-272">Creates batch test data.</span></span>
    * <span data-ttu-id="96ad1-273">테스트 데이터를 기반으로 감정을 예측합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-273">Predicts sentiment based on test data.</span></span>
    * <span data-ttu-id="96ad1-274">보고를 위해 테스트 데이터 및 예측을 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-274">Combines test data and predictions for reporting.</span></span>
    * <span data-ttu-id="96ad1-275">예측 결과를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-275">Displays the predicted results.</span></span>

2. <span data-ttu-id="96ad1-276">다음 코드를 사용하여 `UseModelWithSingleItem()` 메서드 호출 바로 아래에 `Main` 메서드의 새 메서드 호출을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-276">Add a call to the new method from the `Main` method, right under the `UseModelWithSingleItem()` method call, using the following code:</span></span>

    [!code-csharp[CallPredictModelBatchItems](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CallUseModelWithBatchItems "Call the CallUseModelWithBatchItems method")]

3. <span data-ttu-id="96ad1-277">몇몇 댓글을 추가하여 `UseModelWithBatchItems()` 메서드에서 학습된 모델의 예측을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-277">Add some comments to test the trained model's predictions in the `UseModelWithBatchItems()` method:</span></span>

    [!code-csharp[PredictionData](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#CreateTestIssues "Create test data for predictions")]

### <a name="predict-comment-sentiment"></a><span data-ttu-id="96ad1-278">주석 감정 예측</span><span class="sxs-lookup"><span data-stu-id="96ad1-278">Predict comment sentiment</span></span>

<span data-ttu-id="96ad1-279">모델을 사용하여 [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) 메서드를 통한 주석 데이터 감정 예측:</span><span class="sxs-lookup"><span data-stu-id="96ad1-279">Use the model to predict the comment data sentiment using the [Transform()](xref:Microsoft.ML.ITransformer.Transform%2A) method:</span></span>

[!code-csharp[Predict](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#Prediction "Create predictions of sentiments")]

### <a name="combine-and-display-the-predictions"></a><span data-ttu-id="96ad1-280">예측 결합 및 표시</span><span class="sxs-lookup"><span data-stu-id="96ad1-280">Combine and display the predictions</span></span>

<span data-ttu-id="96ad1-281">다음 코드를 사용하여 예측에 대한 헤더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-281">Create a header for the predictions using the following code:</span></span>

[!code-csharp[OutputHeaders](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#AddInfoMessage "Display prediction outputs")]

<span data-ttu-id="96ad1-282">`SentimentPrediction`은 `SentimentData`에서 상속되므로 `Transform()` 메서드가 예측된 필드로 `SentimentText`를 입력했습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-282">Because `SentimentPrediction` is inherited from `SentimentData`, the `Transform()` method populated `SentimentText` with the predicted fields.</span></span> <span data-ttu-id="96ad1-283">ML.NET 프로세스를 처리하면서 각 구성 요소가 열을 추가하므로 결과를 쉽게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-283">As the ML.NET process processes, each component adds columns, and this makes it easy to display the results:</span></span>

[!code-csharp[DisplayPredictions](~/samples/machine-learning/tutorials/SentimentAnalysis/Program.cs#DisplayResults "Display the predictions")]

## <a name="results"></a><span data-ttu-id="96ad1-284">결과</span><span class="sxs-lookup"><span data-stu-id="96ad1-284">Results</span></span>

<span data-ttu-id="96ad1-285">다음과 같은 결과가 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-285">Your results should be similar to the following.</span></span> <span data-ttu-id="96ad1-286">처리 중 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-286">During processing, messages are displayed.</span></span> <span data-ttu-id="96ad1-287">경고 또는 메시지 처리를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-287">You may see warnings, or processing messages.</span></span> <span data-ttu-id="96ad1-288">이해하기 쉽도록 이러한 결과는 다음 결과에서 제거되었습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-288">These have been removed from the following results for clarity.</span></span>

```console
Model quality metrics evaluation
--------------------------------
Accuracy: 83.96%
Auc: 90.51%
F1Score: 84.04%

=============== End of model evaluation ===============

=============== Prediction Test of model with a single sample and test dataset ===============

Sentiment: This was a very bad steak | Prediction: Negative | Probability: 0.1027377
=============== End of Predictions ===============


=============== Prediction Test of loaded model with a multiple samples ===============

Sentiment: This was a horrible meal | Prediction: Negative | Probability: 0.1369192
Sentiment: I love this spaghetti. | Prediction: Positive | Probability: 0.9960636
=============== End of predictions ===============

=============== End of process ===============
Press any key to continue . . .

```

<span data-ttu-id="96ad1-289">지금까지</span><span class="sxs-lookup"><span data-stu-id="96ad1-289">Congratulations!</span></span> <span data-ttu-id="96ad1-290">이제 메시지 감정을 분류하고 예측하기 위한 기계 학습 모델을 성공적으로 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-290">You've now successfully built a machine learning model for classifying and predicting messages sentiment.</span></span>

<span data-ttu-id="96ad1-291">성공한 모델 빌드하는 것은 반복적인 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-291">Building successful models is an iterative process.</span></span> <span data-ttu-id="96ad1-292">자습서에서는 작은 데이터 세트를 사용하여 빠른 모델 학습을 제공하므로 이 모델은 초기 품질이 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-292">This model has initial lower quality as the tutorial uses small datasets to provide quick model training.</span></span> <span data-ttu-id="96ad1-293">모델 품질에 만족하지 않는 경우 더 큰 학습 데이터 세트를 제공하거나 각 알고리즘에 대한 다양한 [하이퍼 매개 변수](../resources/glossary.md##hyperparameter)와 함께 다양한 학습 알고리즘을 선택하여 모델 품질을 개선할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-293">If you aren't satisfied with the model quality, you can try to improve it by providing larger training datasets or by choosing different training algorithms with different [hyper-parameters](../resources/glossary.md##hyperparameter) for each algorithm.</span></span>

<span data-ttu-id="96ad1-294">[dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) 리포지토리에서 이 자습서의 소스 코드를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-294">You can find the source code for this tutorial at the [dotnet/samples](https://github.com/dotnet/samples/tree/master/machine-learning/tutorials/SentimentAnalysis) repository.</span></span>

## <a name="next-steps"></a><span data-ttu-id="96ad1-295">다음 단계</span><span class="sxs-lookup"><span data-stu-id="96ad1-295">Next steps</span></span>

<span data-ttu-id="96ad1-296">본 자습서에서는 다음 작업에 관한 방법을 학습했습니다.</span><span class="sxs-lookup"><span data-stu-id="96ad1-296">In this tutorial, you learned how to:</span></span>
> [!div class="checklist"]
> * <span data-ttu-id="96ad1-297">콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="96ad1-297">Create a console application</span></span>
> * <span data-ttu-id="96ad1-298">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="96ad1-298">Prepare data</span></span>
> * <span data-ttu-id="96ad1-299">데이터 로드</span><span class="sxs-lookup"><span data-stu-id="96ad1-299">Load the data</span></span>
> * <span data-ttu-id="96ad1-300">모델 빌드 및 학습</span><span class="sxs-lookup"><span data-stu-id="96ad1-300">Build and train the model</span></span>
> * <span data-ttu-id="96ad1-301">모델 평가</span><span class="sxs-lookup"><span data-stu-id="96ad1-301">Evaluate the model</span></span>
> * <span data-ttu-id="96ad1-302">모델로 예측 수행</span><span class="sxs-lookup"><span data-stu-id="96ad1-302">Use the model to make a prediction</span></span>
> * <span data-ttu-id="96ad1-303">결과 보기</span><span class="sxs-lookup"><span data-stu-id="96ad1-303">See the results</span></span>

<span data-ttu-id="96ad1-304">다음 자습서로 이동하여 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="96ad1-304">Advance to the next tutorial to learn more</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="96ad1-305">문제 분류</span><span class="sxs-lookup"><span data-stu-id="96ad1-305">Issue Classification</span></span>](github-issue-classification.md)
