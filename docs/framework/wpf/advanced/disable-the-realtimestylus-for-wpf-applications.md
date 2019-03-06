---
title: WPF 응용 프로그램에 대해 RealTimeStylus를 사용하지 않도록 설정
ms.date: 03/30/2017
ms.assetid: e0525309-5ede-4782-837d-dbf6e5554859
ms.openlocfilehash: 6af7ff3addfe2673ab73ff0f977770f89c6234bb
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57371133"
---
# <a name="disable-the-realtimestylus-for-wpf-applications"></a><span data-ttu-id="2f5c9-102">WPF 응용 프로그램에 대해 RealTimeStylus를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="2f5c9-102">Disable the RealTimeStylus for WPF Applications</span></span>
<span data-ttu-id="2f5c9-103">Windows Presentation Foundation (WPF)은 Windows 7 터치 입력을 처리 하는 것에 대 한 지원을 구축 했습니다. 지원으로 tablet 플랫폼의 실시간 스타일러스 입력을 통해 제공 됩니다 <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, 및 <xref:System.Windows.UIElement.OnStylusMove%2A> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="2f5c9-103">Windows Presentation Foundation (WPF) has built in support for processing Windows 7 touch input.The support comes through the tablet platform’s real-time stylus input as <xref:System.Windows.UIElement.OnStylusDown%2A>, <xref:System.Windows.UIElement.OnStylusUp%2A>, and <xref:System.Windows.UIElement.OnStylusMove%2A> events.</span></span> <span data-ttu-id="2f5c9-104">또한 Windows 7 WM_TOUCH Win32 창 메시지를 멀티 터치 입력을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2f5c9-104">Windows 7 also provides multi-touch input as Win32 WM_TOUCH window messages.</span></span> <span data-ttu-id="2f5c9-105">이러한 두 Api는 동일한 HWND에서 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f5c9-105">These two APIs are mutually exclusive on the same HWND.</span></span> <span data-ttu-id="2f5c9-106">사용 하지 않도록 설정 WM_TOUCH 메시지는 tablet 플랫폼 (WPF 응용 프로그램에 대 한 기본값)을 통해 터치 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f5c9-106">Enabling touch input via the tablet platform (the default for WPF applications) disables WM_TOUCH messages.</span></span> <span data-ttu-id="2f5c9-107">결과적으로, WM_TOUCH에 WPF 창에서 터치 메시지를 수신 하는 데 사용 하려면 WPF에서 기본 제공 스타일러스 지원을 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f5c9-107">As a result, to use WM_TOUCH to receive touch messages from a WPF window, you must disable the built-in stylus support in WPF.</span></span> <span data-ttu-id="2f5c9-108">WM_TOUCH를 사용 하는 구성 요소를 호스팅하는 WPF 창 등의 시나리오에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f5c9-108">This is applicable in a scenario such as a WPF window hosting a component that uses WM_TOUCH.</span></span>  
  
 <span data-ttu-id="2f5c9-109">스타일러스 입력에 수신 대기 하는 WPF를 사용 하지 않으려면 WPF 창에 추가 된 태블릿 지원을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f5c9-109">To disable WPF listening to stylus input, remove any tablet support added by the WPF window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f5c9-110">예제</span><span class="sxs-lookup"><span data-stu-id="2f5c9-110">Example</span></span>  
 <span data-ttu-id="2f5c9-111">다음 샘플 코드는 리플렉션을 사용 하 여 기본 tablet 플랫폼 지원 기능을 제거 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f5c9-111">The following sample code shows how to remove the default tablet platform support by using reflection.</span></span>  
  
```  
public static void DisableWPFTabletSupport()  
{  
    // Get a collection of the tablet devices for this window.    
    TabletDeviceCollection devices = System.Windows.Input.Tablet.TabletDevices;  
  
    if (devices.Count > 0)  
    {     
        // Get the Type of InputManager.  
        Type inputManagerType = typeof(System.Windows.Input.InputManager);  
  
        // Call the StylusLogic method on the InputManager.Current instance.  
        object stylusLogic = inputManagerType.InvokeMember("StylusLogic",  
                    BindingFlags.GetProperty | BindingFlags.Instance | BindingFlags.NonPublic,  
                    null, InputManager.Current, null);  
  
        if (stylusLogic != null)  
        {  
            //  Get the type of the stylusLogic returned from the call to StylusLogic.  
            Type stylusLogicType = stylusLogic.GetType();  
  
            // Loop until there are no more devices to remove.  
            while (devices.Count > 0)  
            {  
                // Remove the first tablet device in the devices collection.  
                stylusLogicType.InvokeMember("OnTabletRemoved",  
                        BindingFlags.InvokeMethod | BindingFlags.Instance | BindingFlags.NonPublic,  
                        null, stylusLogic, new object[] { (uint)0 });  
            }                  
        }  
  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2f5c9-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="2f5c9-112">See also</span></span>
- [<span data-ttu-id="2f5c9-113">스타일러스에서 입력 가로채기</span><span class="sxs-lookup"><span data-stu-id="2f5c9-113">Intercepting Input from the Stylus</span></span>](intercepting-input-from-the-stylus.md)
