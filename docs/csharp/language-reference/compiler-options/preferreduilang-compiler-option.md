---
title: -preferreduilang(C# 컴파일러 옵션)
ms.date: 07/20/2015
f1_keywords:
- /preferreduilang
helpviewer_keywords:
- preferreduilang compiler option [C#]
- /preferreduilang compiler option [C#]
- -preferreduilang compiler option [C#]
ms.assetid: 68b2462f-6778-48d7-8052-62805fe8e02c
ms.openlocfilehash: 21a3baceb8a46723de1c633e415af0660bb41840
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33211753"
---
# <a name="-preferreduilang-c-compiler-options"></a><span data-ttu-id="8cb7a-102">-preferreduilang(C# 컴파일러 옵션)</span><span class="sxs-lookup"><span data-stu-id="8cb7a-102">-preferreduilang (C# Compiler Options)</span></span>
<span data-ttu-id="8cb7a-103">`-preferreduilang` 컴파일러 옵션을 사용하여 C# 컴파일러에서 오류 메시지 등의 출력을 표시하는 언어를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb7a-103">By using the `-preferreduilang` compiler option, you can specify the language in which the C# compiler displays output, such as error messages.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cb7a-104">구문</span><span class="sxs-lookup"><span data-stu-id="8cb7a-104">Syntax</span></span>  
  
```console  
-preferreduilang: language  
```  
  
## <a name="arguments"></a><span data-ttu-id="8cb7a-105">인수</span><span class="sxs-lookup"><span data-stu-id="8cb7a-105">Arguments</span></span>  
 `language`  
 <span data-ttu-id="8cb7a-106">컴파일러 출력에 사용할 언어의 [언어 이름](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx)입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb7a-106">The [language name](https://msdn.microsoft.com/library/windows/desktop/dd318696(v=vs.85).aspx) of the language to use for compiler output.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8cb7a-107">설명</span><span class="sxs-lookup"><span data-stu-id="8cb7a-107">Remarks</span></span>  
 <span data-ttu-id="8cb7a-108">`-preferreduilang` 컴파일러 옵션을 사용하여 C# 컴파일러에서 오류 메시지와 기타 명령줄 출력에 사용할 언어를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb7a-108">You can use the `-preferreduilang` compiler option to specify the language that you want the C# compiler to use for error messages and other command-line output.</span></span> <span data-ttu-id="8cb7a-109">해당 언어의 언어 팩이 설치되지 않은 경우 운영 체제의 언어 설정이 대신 사용되고 오류가 보고되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb7a-109">If the language pack for the language is not installed, the language setting of the operating system is used instead, and no error is reported.</span></span>  
  
```csharp  
csc.exe -preferreduilang:ja-JP  
```  
  
## <a name="requirements"></a><span data-ttu-id="8cb7a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8cb7a-110">Requirements</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cb7a-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8cb7a-111">See Also</span></span>  
 [<span data-ttu-id="8cb7a-112">C# 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="8cb7a-112">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)
