---
title: CorFlags.exe(CorFlags 변환 도구)
ms.date: 03/30/2017
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 21b9881f1275c6a9343421131af478e11b826073
ms.sourcegitcommit: a36cfc9dbbfc04bd88971f96e8a3f8e283c15d42
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54222729"
---
# <a name="corflagsexe-corflags-conversion-tool"></a><span data-ttu-id="5ecbe-102">CorFlags.exe(CorFlags 변환 도구)</span><span class="sxs-lookup"><span data-stu-id="5ecbe-102">CorFlags.exe (CorFlags Conversion Tool)</span></span>
<span data-ttu-id="5ecbe-103">CorFlags 변환 도구를 사용하면 이식할 수 있는 실행 가능 이미지 헤더의 CorFlags 섹션을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-103">The CorFlags Conversion tool allows you to configure the CorFlags section of the header of a portable executable image.</span></span>  
  
 <span data-ttu-id="5ecbe-104">이 도구는 자동으로 Visual Studio와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-104">This tool is automatically installed with Visual Studio.</span></span> <span data-ttu-id="5ecbe-105">이 도구를 실행하려면 Visual Studio용 개발자 명령 프롬프트(또는 Windows 7의 Visual Studio 명령 프롬프트)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-105">To run the tool, use the Developer Command Prompt for Visual Studio (or the Visual Studio Command Prompt in Windows 7).</span></span> <span data-ttu-id="5ecbe-106">자세한 내용은 [명령 프롬프트](../../../docs/framework/tools/developer-command-prompt-for-vs.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-106">For more information, see [Command Prompts](../../../docs/framework/tools/developer-command-prompt-for-vs.md).</span></span>  
  
 <span data-ttu-id="5ecbe-107">명령 프롬프트에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-107">At the command prompt, type the following:</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ecbe-108">구문</span><span class="sxs-lookup"><span data-stu-id="5ecbe-108">Syntax</span></span>  
  
```  
CorFlags.exe assembly [options]  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5ecbe-109">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ecbe-109">Parameters</span></span>  
  
|<span data-ttu-id="5ecbe-110">필수적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ecbe-110">Required parameter</span></span>|<span data-ttu-id="5ecbe-111">설명</span><span class="sxs-lookup"><span data-stu-id="5ecbe-111">Description</span></span>|  
|------------------------|-----------------|  
|`assembly`|<span data-ttu-id="5ecbe-112">CorFlags를 구성할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-112">The name of the assembly for which to configure the CorFlags.</span></span>|  
  
|<span data-ttu-id="5ecbe-113">옵션</span><span class="sxs-lookup"><span data-stu-id="5ecbe-113">Option</span></span>|<span data-ttu-id="5ecbe-114">설명</span><span class="sxs-lookup"><span data-stu-id="5ecbe-114">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="5ecbe-115">**/32BIT[REQ]+**</span><span class="sxs-lookup"><span data-stu-id="5ecbe-115">**/32BIT[REQ]+**</span></span>|<span data-ttu-id="5ecbe-116">32BITREQUIRED 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-116">Sets the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="5ecbe-117">**/32BIT[REQ]-**</span><span class="sxs-lookup"><span data-stu-id="5ecbe-117">**/32BIT[REQ]-**</span></span>|<span data-ttu-id="5ecbe-118">32BITREQUIRED 플래그를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-118">Clears the 32BITREQUIRED flag.</span></span>|  
|<span data-ttu-id="5ecbe-119">**/32BITPREF+**</span><span class="sxs-lookup"><span data-stu-id="5ecbe-119">**/32BITPREF+**</span></span>|<span data-ttu-id="5ecbe-120">32BITPREFERRED 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-120">Sets the 32BITPREFERRED flag.</span></span> <span data-ttu-id="5ecbe-121">응용 프로그램이 64비트 플랫폼에서 32비트 프로세스로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-121">The app runs as a 32-bit process even on 64-bit platforms.</span></span> <span data-ttu-id="5ecbe-122">EXE 파일에만 이 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-122">Set this flag only on EXE files.</span></span> <span data-ttu-id="5ecbe-123">DLL에 플래그가 설정되면 DLL은 64비트 프로세스 로드에 실패하고 <xref:System.BadImageFormatException> 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-123">If the flag is set on a DLL, the DLL fails to load in 64-bit processes, and a <xref:System.BadImageFormatException> exception is thrown.</span></span> <span data-ttu-id="5ecbe-124">이 플래그를 사용하여 EXE 파일은 64비트 프로세스에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-124">An EXE file with this flag can be loaded into a 64-bit process.</span></span><br /><br /> <span data-ttu-id="5ecbe-125">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에 새로 추가된 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-125">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="5ecbe-126">**/32BITPREF-**</span><span class="sxs-lookup"><span data-stu-id="5ecbe-126">**/32BITPREF-**</span></span>|<span data-ttu-id="5ecbe-127">32BITPREFERRED 플래그를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-127">Clears the 32BITPREFERRED flag.</span></span><br /><br /> <span data-ttu-id="5ecbe-128">[!INCLUDE[net_v45](../../../includes/net-v45-md.md)]에 새로 추가된 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-128">New in the [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].</span></span>|  
|<span data-ttu-id="5ecbe-129">**/?**</span><span class="sxs-lookup"><span data-stu-id="5ecbe-129">**/?**</span></span>|<span data-ttu-id="5ecbe-130">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-130">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="5ecbe-131">**/Force**</span><span class="sxs-lookup"><span data-stu-id="5ecbe-131">**/Force**</span></span>|<span data-ttu-id="5ecbe-132">어셈블리의 이름이 강력한 이름인 경우에도 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-132">Forces an update even if the assembly is strong-named.</span></span> <span data-ttu-id="5ecbe-133">**중요:**  강력한 이름의 어셈블리를 업데이트하면 코드를 실행하기 전에 다시 서명해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-133">**Important:**  If you update a strong-named assembly, you must sign it again before executing its code.</span></span>|  
|<span data-ttu-id="5ecbe-134">**/help**</span><span class="sxs-lookup"><span data-stu-id="5ecbe-134">**/help**</span></span>|<span data-ttu-id="5ecbe-135">이 도구의 명령 구문 및 옵션을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-135">Displays command syntax and options for the tool.</span></span>|  
|<span data-ttu-id="5ecbe-136">**/ILONLY+**</span><span class="sxs-lookup"><span data-stu-id="5ecbe-136">**/ILONLY+**</span></span>|<span data-ttu-id="5ecbe-137">ILONLY 플래그를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-137">Sets the ILONLY flag.</span></span>|  
|<span data-ttu-id="5ecbe-138">**/ILONLY-**</span><span class="sxs-lookup"><span data-stu-id="5ecbe-138">**/ILONLY-**</span></span>|<span data-ttu-id="5ecbe-139">ILONLY 플래그를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-139">Clears the ILONLY flag.</span></span>|  
|<span data-ttu-id="5ecbe-140">**/nologo**</span><span class="sxs-lookup"><span data-stu-id="5ecbe-140">**/nologo**</span></span>|<span data-ttu-id="5ecbe-141">Microsoft 시작 배너를 표시하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-141">Suppresses the Microsoft startup banner display.</span></span>|  
|<span data-ttu-id="5ecbe-142">**/RevertCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="5ecbe-142">**/RevertCLRHeader**</span></span>|<span data-ttu-id="5ecbe-143">CLR 헤더 버전을 2.0으로 되돌립니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-143">Reverts the CLR header version to 2.0.</span></span>|  
|<span data-ttu-id="5ecbe-144">**/UpgradeCLRHeader**</span><span class="sxs-lookup"><span data-stu-id="5ecbe-144">**/UpgradeCLRHeader**</span></span>|<span data-ttu-id="5ecbe-145">CLR 헤더 버전을 2.5로 업그레이드합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-145">Upgrades the CLR header version to 2.5.</span></span> <span data-ttu-id="5ecbe-146">**참고:**  기본적으로 어셈블리를 실행하려면 CLR 헤더 버전이 2.5 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-146">**Note:**  Assemblies must have a CLR header version of 2.5 or greater to run natively.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ecbe-147">주의</span><span class="sxs-lookup"><span data-stu-id="5ecbe-147">Remarks</span></span>  
 <span data-ttu-id="5ecbe-148">옵션을 지정하지 않으면 CorFlags 변환 도구에서 지정한 어셈블리에 대한 플래그를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="5ecbe-148">If no options are specified, the CorFlags Conversion tool displays the flags for the specified assembly.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ecbe-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5ecbe-149">See Also</span></span>  
 [<span data-ttu-id="5ecbe-150">도구</span><span class="sxs-lookup"><span data-stu-id="5ecbe-150">Tools</span></span>](../../../docs/framework/tools/index.md)  
 [<span data-ttu-id="5ecbe-151">64비트 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="5ecbe-151">64-bit Applications</span></span>](../../../docs/framework/64-bit-apps.md)  
 [<span data-ttu-id="5ecbe-152">명령 프롬프트</span><span class="sxs-lookup"><span data-stu-id="5ecbe-152">Command Prompts</span></span>](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
