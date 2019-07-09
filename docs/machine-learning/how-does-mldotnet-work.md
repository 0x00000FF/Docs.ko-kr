---
title: ML.NET은 무엇이며 어떻게 작동하나요?
description: ML.NET은 .NET 애플리케이션에 기계 학습을 추가할 수 있는 기능을 제공합니다. 이 기능을 사용하여 애플리케이션에 사용 가능한 데이터를 사용하여 자동 예측할 수 있습니다. 이 문서에서는 ML.NET에서 기계 학습의 기본 사항을 설명합니다.
ms.date: 04/10/2019
ms.topic: overview
ms.custom: mvc
ms.author: nakersha
author: natke
ms.openlocfilehash: 06085091a13ad76dcd554cfe637bcc151bbb8476
ms.sourcegitcommit: eaa6d5cd0f4e7189dbe0bd756e9f53508b01989e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2019
ms.locfileid: "67610174"
---
# <a name="what-is-mlnet-and-how-does-it-work"></a><span data-ttu-id="57f3a-105">ML.NET은 무엇이며 어떻게 작동하나요?</span><span class="sxs-lookup"><span data-stu-id="57f3a-105">What is ML.NET and how does it work?</span></span>

<span data-ttu-id="57f3a-106">ML.NET은 .NET 애플리케이션에 기계 학습을 추가할 수 있는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-106">ML.NET gives you the ability to add machine learning to .NET applications.</span></span> <span data-ttu-id="57f3a-107">이 기능을 사용하여 애플리케이션에 사용 가능한 데이터를 사용하여 자동 예측할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-107">With this capability, you can make automatic predictions using the data available to your application.</span></span> <span data-ttu-id="57f3a-108">이 문서에서는 ML.NET에서 기계 학습의 기본 사항을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-108">This article explains the basics of machine learning in ML.NET.</span></span> 

<span data-ttu-id="57f3a-109">ML.NET을 사용하여 수행할 수 있는 예측 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-109">Examples of the type of predictions that you can make with ML.NET include:</span></span>

|||
|-|-|
|<span data-ttu-id="57f3a-110">분류/범주화</span><span class="sxs-lookup"><span data-stu-id="57f3a-110">Classification/Categorization</span></span>|<span data-ttu-id="57f3a-111">고객 피드백을 긍정과 부정 범주로 자동 구분</span><span class="sxs-lookup"><span data-stu-id="57f3a-111">Automatically divide customer feedback into positive and negative categories</span></span>|
|<span data-ttu-id="57f3a-112">재발/연속 값 예측</span><span class="sxs-lookup"><span data-stu-id="57f3a-112">Regression/Predict continuous values</span></span>|<span data-ttu-id="57f3a-113">크기 및 위치에 따라 주택 가격 예측</span><span class="sxs-lookup"><span data-stu-id="57f3a-113">Predict the price of houses based on size and location</span></span>|
|<span data-ttu-id="57f3a-114">변칙 검색</span><span class="sxs-lookup"><span data-stu-id="57f3a-114">Anomaly Detection</span></span>|<span data-ttu-id="57f3a-115">사기성 은행 거래 검색</span><span class="sxs-lookup"><span data-stu-id="57f3a-115">Detect fraudulent banking transactions</span></span> |
|<span data-ttu-id="57f3a-116">권장 사항</span><span class="sxs-lookup"><span data-stu-id="57f3a-116">Recommendations</span></span>|<span data-ttu-id="57f3a-117">이전 구매 내역에 기반하여 온라인 구매자가 구매하려는 제품 제안</span><span class="sxs-lookup"><span data-stu-id="57f3a-117">Suggest products that online shoppers may want to buy, based on their previous purchases</span></span>|

## <a name="hello-mlnet-world"></a><span data-ttu-id="57f3a-118">Hello ML.NET World</span><span class="sxs-lookup"><span data-stu-id="57f3a-118">Hello ML.NET World</span></span>

<span data-ttu-id="57f3a-119">다음 코드 조각의 코드는 가장 단순한 ML.NET 애플리케이션을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-119">The code in the following snippet demonstrates the simplest ML.NET application.</span></span> <span data-ttu-id="57f3a-120">이 예제에서는 집 크기 및 가격 데이터를 사용하여 주택 가격을 예측하도록 선형 회귀 모델을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-120">This example constructs a linear regression model to predict house prices using house size and price data.</span></span> <span data-ttu-id="57f3a-121">실제 애플리케이션에서 사용자의 데이터와 모델은 훨씬 더 복잡할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-121">In your real-life applications, your data and model will be much more complex.</span></span>

 ```csharp
    using System;
    using Microsoft.ML;
    using Microsoft.ML.Data;
    
    class Program
    {
        public class HouseData
        {
            public float Size { get; set; }
            public float Price { get; set; }
        }
    
        public class Prediction
        {
            [ColumnName("Score")]
            public float Price { get; set; }
        }
    
        static void Main(string[] args)
        {
            MLContext mlContext = new MLContext();
    
            // 1. Import or create training data
            HouseData[] houseData = {
                new HouseData() { Size = 1.1F, Price = 1.2F },
                new HouseData() { Size = 1.9F, Price = 2.3F },
                new HouseData() { Size = 2.8F, Price = 3.0F },
                new HouseData() { Size = 3.4F, Price = 3.7F } };
            IDataView trainingData = mlContext.Data.LoadFromEnumerable(houseData);

            // 2. Specify data preparation and model training pipeline
            var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
                .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
    
            // 3. Train model
            var model = pipeline.Fit(trainingData);
    
            // 4. Make a prediction
            var size = new HouseData() { Size = 2.5F };
            var price = mlContext.Model.CreatePredictionEngine<HouseData, Prediction>(model).Predict(size);

            Console.WriteLine($"Predicted price for size: {size.Size*1000} sq ft= {price.Price*100:C}k");

            // Predicted price for size: 2500 sq ft= $261.98k
        }
    } 
```

## <a name="code-workflow"></a><span data-ttu-id="57f3a-122">코드 워크플로</span><span class="sxs-lookup"><span data-stu-id="57f3a-122">Code workflow</span></span>

<span data-ttu-id="57f3a-123">다음 다이어그램은 반복적인 모델 개발 프로세스뿐만 아니라 애플리케이션 코드 구조를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-123">The following diagram represents the application code structure, as well as the iterative process of model development:</span></span>
- <span data-ttu-id="57f3a-124">학습 데이터를 수집하여 **IDataView** 개체로 로드</span><span class="sxs-lookup"><span data-stu-id="57f3a-124">Collect and load training data into an **IDataView** object</span></span>
- <span data-ttu-id="57f3a-125">기능을 추출하고 기계 학습 알고리즘을 적용할 작업 파이프라인 지정</span><span class="sxs-lookup"><span data-stu-id="57f3a-125">Specify a pipeline of operations to extract features and apply a machine learning algorithm</span></span>
- <span data-ttu-id="57f3a-126">파이프라인에서 **Fit()** 를 호출하여 모델 학습</span><span class="sxs-lookup"><span data-stu-id="57f3a-126">Train a model by calling **Fit()** on the pipeline</span></span>
- <span data-ttu-id="57f3a-127">모델을 평가하고 반복하여 개선</span><span class="sxs-lookup"><span data-stu-id="57f3a-127">Evaluate the model and iterate to improve</span></span>
- <span data-ttu-id="57f3a-128">애플리케이션에서 사용할 수 있도록 모델을 이진 형식으로 저장</span><span class="sxs-lookup"><span data-stu-id="57f3a-128">Save the model into binary format, for use in an application</span></span>
- <span data-ttu-id="57f3a-129">모델을 **ITransformer** 개체로 다시 로드</span><span class="sxs-lookup"><span data-stu-id="57f3a-129">Load the model back into an **ITransformer** object</span></span>
- <span data-ttu-id="57f3a-130">**CreatePredictionEngine.Predict()** 를 호출하여 예측</span><span class="sxs-lookup"><span data-stu-id="57f3a-130">Make predictions by calling **CreatePredictionEngine.Predict()**</span></span>

![데이터 생성, 파이프라인 개발, 모델 학습, 모델 평가 및 모델 사용에 대한 구성 요소를 포함한 ML.NET 애플리케이션 개발 흐름](./media/mldotnet-annotated-workflow.png) 

<span data-ttu-id="57f3a-132">이러한 개념을 좀 더 깊이 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-132">Let's dig a little deeper into those concepts.</span></span>

## <a name="machine-learning-model"></a><span data-ttu-id="57f3a-133">기계 학습 모델</span><span class="sxs-lookup"><span data-stu-id="57f3a-133">Machine learning model</span></span>

<span data-ttu-id="57f3a-134">ML.NET 모델은 예측된 출력에 도달하기 위해 입력 데이터에서 수행할 변형이 포함된 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-134">An ML.NET model is an object that contains transformations to perform on your input data to arrive at the predicted output.</span></span>

### <a name="basic"></a><span data-ttu-id="57f3a-135">Basic</span><span class="sxs-lookup"><span data-stu-id="57f3a-135">Basic</span></span>

<span data-ttu-id="57f3a-136">가장 기본적인 모델은 위의 주택 가격 예에서와 같이 하나의 지속적인 수량이 다른 것과 비례하는 2차원 선형 회귀입니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-136">The most basic model is two-dimensional linear regression, where one continuous quantity is proportional to another, as in the house price example above.</span></span> 

![편차와 가중치 매개 변수가 포함된 선형 회귀 모델](./media/linear-regression-model.svg)

<span data-ttu-id="57f3a-138">모델은 단순히 $Price = b + Size \* w$입니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-138">The model is simply: $Price = b + Size \* w$.</span></span> <span data-ttu-id="57f3a-139">매개 변수 $b$ 및 $w$는 쌍 세트(크기, 가격)에 줄을 맞춰 추정됩니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-139">The parameters $b$ and $w$ are estimated by fitting a line on a set of (size, price) pairs.</span></span> <span data-ttu-id="57f3a-140">데이터 모델의 매개 변수를 찾는 데 이라고 **학습 데이터**입니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-140">The data used to find the parameters of the model is called **training data**.</span></span> <span data-ttu-id="57f3a-141">이 기계 학습 모델의 입력을 **기능**이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-141">The inputs of a machine learning model are called **features**.</span></span> <span data-ttu-id="57f3a-142">이 예제에서는 $Size$가 유일한 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-142">In this example, $Size$ is the only feature.</span></span> <span data-ttu-id="57f3a-143">기계 학습 모델을 학습하는 데 사용하는 실측 자료(ground-truth) 값은 **레이블**이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-143">The ground-truth values used to train a machine learning model are called **labels**.</span></span> <span data-ttu-id="57f3a-144">여기에서는 학습 데이터 세트의 $Price$ 값이 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-144">Here, the $Price$ values in the training data set are the labels.</span></span>

### <a name="more-complex"></a><span data-ttu-id="57f3a-145">더 복잡한</span><span class="sxs-lookup"><span data-stu-id="57f3a-145">More complex</span></span>

<span data-ttu-id="57f3a-146">더 복잡한 모델은 거래 텍스트 설명을 사용하여 금융 거래를 범주로 분류합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-146">A more complex model classifies financial transactions into categories using the transaction text description.</span></span>

<span data-ttu-id="57f3a-147">각 거래 설명은 중복되는 단어와 문자를 제거하고 단어와 문자 조합을 계산하여 일련의 기능으로 세분화됩니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-147">Each transaction description is broken down into a set of features by removing redundant words and characters, and counting word and character combinations.</span></span> <span data-ttu-id="57f3a-148">기능 집합은 학습 데이터에서 범주 집합에 기반하여 선형 모델을 학습하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-148">The feature set is used to train a linear model based on the set of categories in the training data.</span></span> <span data-ttu-id="57f3a-149">새로운 설명이 학습 집합의 설명과 유사할수록 동일한 범주에 할당될 가능성이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-149">The more similar a new description is to the ones in the training set, the more likely it will be assigned to the same category.</span></span> 

![텍스트 분류 모델](./media/text-classification-model.svg)

<span data-ttu-id="57f3a-151">주택 가격 책정 모델 및 텍스트 분류 모델 둘 다 **선형** 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-151">Both the house price model and the text classification model are **linear** models.</span></span> <span data-ttu-id="57f3a-152">데이터의 성격과 해결하려는 문제에 따라, **결정 트리**, **일반화된 부가** 모델 등을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-152">Depending on the nature of your data and the problem you are solving, you can also use **decision tree** models, **generalized additive** models, and others.</span></span> <span data-ttu-id="57f3a-153">[작업](./resources/tasks.md)에서 모델에 대해 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-153">You can find out more about the models in [Tasks](./resources/tasks.md).</span></span>

## <a name="data-preparation"></a><span data-ttu-id="57f3a-154">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="57f3a-154">Data preparation</span></span>

<span data-ttu-id="57f3a-155">대부분의 경우에서 사용자가 가지고 있는 사용 가능한 데이터는 기계 학습 모델을 학습하기 위해 직접 사용하기에는 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-155">In most cases, the data that you have available isn't suitable to be used directly to train a machine learning model.</span></span> <span data-ttu-id="57f3a-156">원시 데이터는 준비하거나 사전 처리되어야 모델의 매개 변수를 찾기 위해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-156">The raw data needs to be prepared, or pre-processed before it can be used to find the parameters of your model.</span></span> <span data-ttu-id="57f3a-157">데이터를 문자열 값에서 숫자 표현으로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-157">Your data may need to be converted from string values to a numerical representation.</span></span> <span data-ttu-id="57f3a-158">사용자의 입력 데이터에서 중복되는 정보가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-158">You might have redundant information in your input data.</span></span> <span data-ttu-id="57f3a-159">입력 데이터의 크기를 축소 또는 확장해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-159">You may need to reduce or expand the dimensions of your input data.</span></span> <span data-ttu-id="57f3a-160">데이터를 정규화 또는 크기 조정해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-160">Your data might need to be normalized or scaled.</span></span>

<span data-ttu-id="57f3a-161">[ML.NET 자습서](./tutorials/index.md)는 특정 기계 학습 작업에 사용되는 텍스트, 이미지, 숫자 및 시계열 데이터에 대한 다른 데이터 처리 파이프라인에 대해 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-161">The [ML.NET tutorials](./tutorials/index.md) teach you about different data processing pipelines for text, image, numerical, and time-series data used for specific machine learning tasks.</span></span>

<span data-ttu-id="57f3a-162">[데이터 준비 방법](./how-to-guides/prepare-data-ml-net.md)은 데이터 준비를 더 일반적으로 적요하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-162">[How to prepare your data](./how-to-guides/prepare-data-ml-net.md) shows you how to applied data preparation more generally.</span></span>

<span data-ttu-id="57f3a-163">리소스 섹션에서 모든 [사용 가능한 변환](./resources/transforms.md)의 부록을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-163">You can find an appendix of all of the [available transformations](./resources/transforms.md) in the resources section.</span></span>

## <a name="model-evaluation"></a><span data-ttu-id="57f3a-164">모델 평가</span><span class="sxs-lookup"><span data-stu-id="57f3a-164">Model evaluation</span></span>

<span data-ttu-id="57f3a-165">모델을 학습한 후에는 미래의 예측을 얼마나 잘 할지 어떻게 알까요?</span><span class="sxs-lookup"><span data-stu-id="57f3a-165">Once you have trained your model, how do you know how well it will make future predictions?</span></span> <span data-ttu-id="57f3a-166">ML.NET를 사용하여 새로운 테스트 데이터를 기준으로 모델을 평가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-166">With ML.NET, you can evaluate your model against some new test data.</span></span> 

<span data-ttu-id="57f3a-167">기계 학습 작업의 각 유형에는 테스트 데이터 세트를 기준으로 모델의 정확성 및 정밀도를 평가하는 데 사용하는 메트릭이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-167">Each type of machine learning task has metrics used to evaluate the accuracy and precision of the model against the test data set.</span></span>

<span data-ttu-id="57f3a-168">주택 가격 예의 경우 **회귀** 작업을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-168">For our house price example, we used the **Regression** task.</span></span> <span data-ttu-id="57f3a-169">모델을 평가하려면 원래 샘플에 다음 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-169">To evaluate the model, add the following code to the original sample.</span></span>

```csharp
        HouseData[] testHouseData =
        {
            new HouseData() { Size = 1.1F, Price = 0.98F },
            new HouseData() { Size = 1.9F, Price = 2.1F },
            new HouseData() { Size = 2.8F, Price = 2.9F },
            new HouseData() { Size = 3.4F, Price = 3.6F }
        };

        var testHouseDataView = mlContext.Data.LoadFromEnumerable(testHouseData);
        var testPriceDataView = model.Transform(testHouseDataView);
                
        var metrics = mlContext.Regression.Evaluate(testPriceDataView, labelColumnName: "Price");

        Console.WriteLine($"R^2: {metrics.RSquared:0.##}");
        Console.WriteLine($"RMS error: {metrics.RootMeanSquaredError:0.##}");

        // R^2: 0.96
        // RMS error: 0.19
```

<span data-ttu-id="57f3a-170">평가 메트릭은 오류가 낮은 수준이며 예측한 출력과 테스트 출력 간 상관 관계가 높다는 것을 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-170">The evaluation metrics tell you that the error is low-ish, and that correlation between the predicted output and the test output is high.</span></span> <span data-ttu-id="57f3a-171">이 과정은 아주 쉽습니다!</span><span class="sxs-lookup"><span data-stu-id="57f3a-171">That was easy!</span></span> <span data-ttu-id="57f3a-172">실제 사례에서는 훌륭한 모델 메트릭을 얻는 데 더 많은 튜닝이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-172">In real examples, it takes more tuning to achieve good model metrics.</span></span>

## <a name="mlnet-architecture"></a><span data-ttu-id="57f3a-173">ML.NET 아키텍처</span><span class="sxs-lookup"><span data-stu-id="57f3a-173">ML.NET architecture</span></span>

<span data-ttu-id="57f3a-174">이 섹션에서는 ML.NET의 아키텍처 패턴을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-174">In this section, we go through the architectural patterns of ML.NET.</span></span> <span data-ttu-id="57f3a-175">숙련된 .NET 개발자라면 이러한 패턴의 일부는 익숙하고 일부는 덜 익숙해집니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-175">If you are an experienced .NET developer, some of these patterns will be familiar to you, and some will be less familiar.</span></span> <span data-ttu-id="57f3a-176">자세히 살펴보는 동안 긴장을 놓지 마세요!</span><span class="sxs-lookup"><span data-stu-id="57f3a-176">Hold tight, while we dive in!</span></span>

<span data-ttu-id="57f3a-177">ML.NET 애플리케이션은 <xref:Microsoft.ML.MLContext> 개체로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-177">An ML.NET application starts with an <xref:Microsoft.ML.MLContext> object.</span></span> <span data-ttu-id="57f3a-178">이 싱글톤 개체는 **카탈로그**를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-178">This singleton object contains **catalogs**.</span></span> <span data-ttu-id="57f3a-179">카탈로그는 데이터 로드 및 저장, 변환, 트레이너, 모델 작동 구성 요소를 위한 팩터리입니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-179">A catalog is a factory for data loading and saving, transforms, trainers, and model operation components.</span></span> <span data-ttu-id="57f3a-180">각 카탈로그 개체마다 다른 유형의 구성 요소를 만드는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-180">Each catalog object has methods to create the different types of components:</span></span>

||||
|-|-|-|-|
|<span data-ttu-id="57f3a-181">데이터 로드 및 저장</span><span class="sxs-lookup"><span data-stu-id="57f3a-181">Data loading and saving</span></span>||<xref:Microsoft.ML.DataOperationsCatalog>||
|<span data-ttu-id="57f3a-182">데이터 준비</span><span class="sxs-lookup"><span data-stu-id="57f3a-182">Data preparation</span></span>||<xref:Microsoft.ML.TransformsCatalog>||
|<span data-ttu-id="57f3a-183">학습 알고리즘</span><span class="sxs-lookup"><span data-stu-id="57f3a-183">Training algorithms</span></span>|<span data-ttu-id="57f3a-184">이진 분류</span><span class="sxs-lookup"><span data-stu-id="57f3a-184">Binary classification</span></span>|<xref:Microsoft.ML.BinaryClassificationCatalog>||
||<span data-ttu-id="57f3a-185">다중 클래스 분류</span><span class="sxs-lookup"><span data-stu-id="57f3a-185">Multiclass classification</span></span>|<xref:Microsoft.ML.MulticlassClassificationCatalog>||
||<span data-ttu-id="57f3a-186">변칙 검색</span><span class="sxs-lookup"><span data-stu-id="57f3a-186">Anomaly detection</span></span>|<xref:Microsoft.ML.AnomalyDetectionCatalog>||
||<span data-ttu-id="57f3a-187">클러스터링</span><span class="sxs-lookup"><span data-stu-id="57f3a-187">Clustering</span></span>|<xref:Microsoft.ML.ClusteringCatalog>||
||<span data-ttu-id="57f3a-188">예측</span><span class="sxs-lookup"><span data-stu-id="57f3a-188">Forecasting</span></span>|<xref:Microsoft.ML.Forecasting>||
||<span data-ttu-id="57f3a-189">순위 지정</span><span class="sxs-lookup"><span data-stu-id="57f3a-189">Ranking</span></span>|<xref:Microsoft.ML.RankingCatalog>||
||<span data-ttu-id="57f3a-190">재발</span><span class="sxs-lookup"><span data-stu-id="57f3a-190">Regression</span></span>|<xref:Microsoft.ML.RegressionCatalog>||
||<span data-ttu-id="57f3a-191">권장 사항</span><span class="sxs-lookup"><span data-stu-id="57f3a-191">Recommendation</span></span>|<xref:Microsoft.ML.RecommendationCatalog>|<span data-ttu-id="57f3a-192">Microsoft.ML.Recommender 추가</span><span class="sxs-lookup"><span data-stu-id="57f3a-192">add Microsoft.ML.Recommender</span></span>|
||<span data-ttu-id="57f3a-193">TimeSeries</span><span class="sxs-lookup"><span data-stu-id="57f3a-193">TimeSeries</span></span>|<xref:Microsoft.ML.TimeSeriesCatalog>|<span data-ttu-id="57f3a-194">Microsoft.ML.TimeSeries 추가</span><span class="sxs-lookup"><span data-stu-id="57f3a-194">add Microsoft.ML.TimeSeries</span></span>|
|<span data-ttu-id="57f3a-195">모델 사용</span><span class="sxs-lookup"><span data-stu-id="57f3a-195">Model usage</span></span> ||<xref:Microsoft.ML.ModelOperationsCatalog>||

<span data-ttu-id="57f3a-196">위의 각 범주에서 만들기 메서드로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-196">You can navigate to the creation methods in each of the above categories.</span></span> <span data-ttu-id="57f3a-197">카탈로그는 Visual Studio를 사용하여 IntelliSense를 통해 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-197">Using Visual Studio, the catalogs show up via IntelliSense.</span></span>

   ![회귀 트레이너용 Intellisense](./media/catalog-intellisense.png)

### <a name="build-the-pipeline"></a><span data-ttu-id="57f3a-199">파이프라인 빌드</span><span class="sxs-lookup"><span data-stu-id="57f3a-199">Build the pipeline</span></span>

<span data-ttu-id="57f3a-200">각 카탈로그 내에는 확장 메서드의 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-200">Inside each catalog is a set of extension methods.</span></span> <span data-ttu-id="57f3a-201">확장 메서드를 사용하여 학습 파이프라인을 만드는 방법을 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-201">Let's look at how extension methods are used to create a training pipeline.</span></span>

```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
        .Append(mlContext.Regression.Trainers.Sdca(labelColumnName: "Price", maximumNumberOfIterations: 100));
```

<span data-ttu-id="57f3a-202">코드 조각에서 `Concatenate` 및 `Sdca`는 카탈로그에 있는 두 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-202">In the snippet, `Concatenate` and `Sdca` are both methods in the catalog.</span></span> <span data-ttu-id="57f3a-203">이러한 메서드는 파이프라인에 연결된 [IEstimator](xref:Microsoft.ML.IEstimator%601) 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-203">They each create an [IEstimator](xref:Microsoft.ML.IEstimator%601) object that is appended to the pipeline.</span></span>

<span data-ttu-id="57f3a-204">이 시점에서는 개체만 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-204">At this point, the objects are created only.</span></span> <span data-ttu-id="57f3a-205">어떠한 실행도 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-205">No execution has happened.</span></span>

### <a name="train-the-model"></a><span data-ttu-id="57f3a-206">모델 학습</span><span class="sxs-lookup"><span data-stu-id="57f3a-206">Train the model</span></span>

<span data-ttu-id="57f3a-207">파이프라인에서 개체가 만들어지면 모델을 학습하는 데 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-207">Once the objects in the pipeline have been created, data can be used to train the model.</span></span>

```csharp
    var model = pipeline.Fit(trainingData);
```

<span data-ttu-id="57f3a-208">`Fit()` 호출 시 입력 학습 데이터를 사용하여 모델의 매개 변수를 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-208">Calling `Fit()` uses the input training data to estimate the parameters of the model.</span></span> <span data-ttu-id="57f3a-209">이를 모델 학습이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-209">This is known as training the model.</span></span> <span data-ttu-id="57f3a-210">단, 위의 선형 회귀 모델에서는 두 가지 모델 매개 변수, 즉 **편차**와 **가중치**가 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-210">Remember, the linear regression model above had two model parameters: **bias** and **weight**.</span></span> <span data-ttu-id="57f3a-211">`Fit()` 호출 후 매개 변수의 값이 알려집니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-211">After the `Fit()` call, the values of the parameters are known.</span></span> <span data-ttu-id="57f3a-212">대부분 모델에는 이것보다 더 많은 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-212">Most models will have many more parameters than this.</span></span>

<span data-ttu-id="57f3a-213">[모델 학습 방법](./how-to-guides/train-machine-learning-model-ml-net.md)에서 모델 학습에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-213">You can learn more about model training in [How to train your model](./how-to-guides/train-machine-learning-model-ml-net.md)</span></span>

<span data-ttu-id="57f3a-214">결과 모델 개체는 <xref:Microsoft.ML.ITransformer> 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-214">The resulting model object implements the <xref:Microsoft.ML.ITransformer> interface.</span></span> <span data-ttu-id="57f3a-215">즉, 모델은 입력 데이터를 예측으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-215">That is, the model transforms input data into predictions.</span></span>

```csharp
   IDataView predictions = model.Transform(inputData);
```

### <a name="use-the-model"></a><span data-ttu-id="57f3a-216">모델 사용</span><span class="sxs-lookup"><span data-stu-id="57f3a-216">Use the model</span></span>

<span data-ttu-id="57f3a-217">입력 데이터를 대량의 예측으로 변환하거나 한 번에 하나의 입력을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-217">You can transform input data into predictions in bulk, or one input at a time.</span></span> <span data-ttu-id="57f3a-218">주택 가격 예에서는 두 가지(모델 평가 목적으로는 대량, 새로운 예측을 하기 위해서는 한 번에 하나씩)를 수행했습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-218">In the house price example, we did both: in bulk for the purpose of evaluating the model, and one at a time to make a new prediction.</span></span> <span data-ttu-id="57f3a-219">단일 예측하기를 살펴 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-219">Let's look at making single predictions.</span></span>

```csharp
    var size = new HouseData() { Size = 2.5F };
    var predEngine = mlContext.CreatePredictionEngine<HouseData, Prediction>(model);
    var price = predEngine.Predict(size);
```
 
<span data-ttu-id="57f3a-220">`CreatePredictionEngine()` 메서드는 입력 클래스 및 출력 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-220">The `CreatePredictionEngine()` method takes an input class and an output class.</span></span> <span data-ttu-id="57f3a-221">필드 이름 및/또는 코드 특성은 모델 학습 및 예측 중 사용된 데이터 열의 이름을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-221">The field names and/or code attributes determine the names of the data columns used during model training and prediction.</span></span> <span data-ttu-id="57f3a-222">방법 섹션에서 [단일 예측하는 방법](./how-to-guides/single-predict-model-ml-net.md)에 대해 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-222">You can read about  [How to make a single prediction](./how-to-guides/single-predict-model-ml-net.md) in the How-to section.</span></span>

### <a name="data-models-and-schema"></a><span data-ttu-id="57f3a-223">데이터 모델 및 스키마</span><span class="sxs-lookup"><span data-stu-id="57f3a-223">Data models and schema</span></span>

<span data-ttu-id="57f3a-224">ML.NET 기계 학습 파이프라인의 핵심에는 [DataView](xref:Microsoft.ML.IDataView) 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-224">At the core of an ML.NET machine learning pipeline are [DataView](xref:Microsoft.ML.IDataView) objects.</span></span>

<span data-ttu-id="57f3a-225">파이프라인의 각 변환에는 입력 스키마(변환 시 입력에서 보길 원하는 데이터 이름, 유형 및 크기)와 출력 스키마(변환 후 해당 변환이 생성하는 데이터 이름, 유형 및 크기)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-225">Each transformation in the pipeline has an input schema (data names, types, and sizes that the transform expects to see on its input); and an output schema (data names, types, and sizes that the transform produces after the transformation).</span></span> 

<span data-ttu-id="57f3a-226">파이프라인에서 하나의 변환으로 인한 출력 스키마가 다음 변환의 입력 스키마와 일치하지 않는 경우 ML.NET은 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-226">If the output schema from one transform in the pipeline doesn't match the input schema of the next transform, ML.NET will throw an exception.</span></span>

<span data-ttu-id="57f3a-227">데이터 뷰 개체에는 열과 행이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-227">A data view object has columns and rows.</span></span> <span data-ttu-id="57f3a-228">각 열에는 이름과 유형 및 길이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-228">Each column has a name and a type and a length.</span></span> <span data-ttu-id="57f3a-229">예: 주택 가격 예의 입력 열에는 **크기**와 **가격**이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-229">For example: the input columns in the house price example are **Size** and **Price**.</span></span> <span data-ttu-id="57f3a-230">두 가지 유형이며, 벡터 수량이라기 보다는 스칼라 수량입니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-230">They are both type  and they are scalar quantities rather than vector ones.</span></span>

   ![주택 가격 예측 데이터가 있는 ML.NET 데이터 뷰 예제](./media/ml-net-dataview.png)

<span data-ttu-id="57f3a-232">모든 ML.NET 알고리즘은 벡터인 입력 열을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-232">All ML.NET algorithms look for an input column that is a vector.</span></span> <span data-ttu-id="57f3a-233">기본적으로 이 벡터 열은 **기능**이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-233">By default this vector column is called **Features**.</span></span> <span data-ttu-id="57f3a-234">이것이 바로 주택 가격 예제에서 **기능**이라고 하는 새 열로 **크기** 열을 연관시킨 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-234">This is why we concatenated the **Size** column into a new column called **Features** in our house price example.</span></span>

 ```csharp
    var pipeline = mlContext.Transforms.Concatenate("Features", new[] { "Size" })
 ```

<span data-ttu-id="57f3a-235">또한 모든 알고리즘은 예측을 수행한 후 새 열을 만들기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-235">All algorithms also create new columns after they have performed a prediction.</span></span> <span data-ttu-id="57f3a-236">이러한 새 열의 고정된 이름은 기계 학습 알고리즘의 유형에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-236">The fixed names of these new columns depend on the type of machine learning algorithm.</span></span> <span data-ttu-id="57f3a-237">회귀 작업의 경우 새 열 중 하나가 **점수**라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-237">For the regression task, one of the new columns is called **Score**.</span></span> <span data-ttu-id="57f3a-238">이것이 바로 이 이름으로 가격 데이터의 이름을 지정한 이유입니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-238">This is why we attributed our price data with this name.</span></span>

```csharp
    public class Prediction
    {
        [ColumnName("Score")]
        public float Price { get; set; }
    }
```    

<span data-ttu-id="57f3a-239">[Machine Learning 작업](resources/tasks.md) 가이드에서 다른 기계 학습 작업의 출력 열에 대해 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-239">You can find out more about output columns of different machine learning tasks in the [Machine Learning Tasks](resources/tasks.md) guide.</span></span>

<span data-ttu-id="57f3a-240">DataView의 중요한 속성은 이들이 **느리게** 평가된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-240">An important property of DataView objects is that they are evaluated **lazily**.</span></span> <span data-ttu-id="57f3a-241">데이터 뷰는 모델 학습 및 평가, 데이터 예측 중에만 로드되고 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-241">Data views are only loaded and operated on during model training and evaluation, and data prediction.</span></span> <span data-ttu-id="57f3a-242">ML.NET 애플리케이션을 쓰고 테스트하는 동안에는 Visual Studio 디버거를 사용하여 [미리 보기](xref:Microsoft.ML.DebuggerExtensions.Preview*) 메서드를 호출하여 어떠한 데이터 뷰 개체도 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-242">While you are writing and testing your ML.NET application, you can use the Visual Studio debugger to take a peek at any data view object by calling the [Preview](xref:Microsoft.ML.DebuggerExtensions.Preview*) method.</span></span>

```csharp
    var debug = testPriceDataView.Preview();
```

<span data-ttu-id="57f3a-243">디버거에서 `debug` 변수를 보고 내용을 살펴볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-243">You can watch the `debug` variable in the debugger and examine its contents.</span></span> <span data-ttu-id="57f3a-244">성능이 크게 저하되므로 프로덕션 코드에서는 미리 보기 메서드를 사용하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="57f3a-244">Do not use the Preview method in production code, as it significantly degrades performance.</span></span>

### <a name="model-deployment"></a><span data-ttu-id="57f3a-245">모델 배포</span><span class="sxs-lookup"><span data-stu-id="57f3a-245">Model Deployment</span></span>

<span data-ttu-id="57f3a-246">실제 애플리케이션에서 모델 학습과 평가 코드는 예측과 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-246">In real-life applications, your model training and evaluation code will be separate from your prediction.</span></span> <span data-ttu-id="57f3a-247">사실,이 두 가지 활동은 별도의 팀에서 수행하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-247">In fact, these two activities are often performed by separate teams.</span></span> <span data-ttu-id="57f3a-248">모델 개발 팀은 예측 애플리케이션에서 사용하기 위해 이 모델을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-248">Your model development team can save the model for use in the prediction application.</span></span>

```csharp   
   mlContext.Model.Save(model, trainingData.Schema,"model.zip");
```

## <a name="where-to-now"></a><span data-ttu-id="57f3a-249">현재 위치</span><span class="sxs-lookup"><span data-stu-id="57f3a-249">Where to now?</span></span>

<span data-ttu-id="57f3a-250">[자습서](./tutorials/index.md)에서 보다 현실적인 데이터 세트로 다른 기계 학습 작업을 사용하여 애플리케이션을 빌드하는 방법을 학습하거나</span><span class="sxs-lookup"><span data-stu-id="57f3a-250">You can learn how to build applications using different machine learning tasks with more realistic data sets in the [tutorials](./tutorials/index.md).</span></span>

<span data-ttu-id="57f3a-251">[방법 가이드](./how-to-guides/index.md)에서 더 자세히 특정 항목에 대해 학습할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57f3a-251">Or you can learn about specific topics in more depth in the [How To Guides](./how-to-guides/index.md).</span></span>

<span data-ttu-id="57f3a-252">만일 관심이 아주 많다면 [API 참조 문서](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet)를 바로 참조할 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="57f3a-252">And if you're super keen, you can dive straight into the [API Reference documentation](https://docs.microsoft.com/dotnet/api/?view=ml-dotnet)!</span></span>
