---
title: '방법: 런타임에 이벤트 처리기 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handlers [Windows Forms], creating
- run time [Windows Forms], creating event handlers at
- examples [Windows Forms], event handling
- Button control [Windows Forms], event handlers
ms.assetid: 2e7c9e1a-61fe-444d-8113-3c5bacf1c8cb
ms.openlocfilehash: 0b496a3da77c5bcf7a08c435edba468a7c5809cb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76739503"
---
# <a name="how-to-create-event-handlers-at-run-time-for-windows-forms"></a>방법: 런타임에 Windows Forms의 이벤트 처리기 만들기

Visual Studio에서 Windows Forms 디자이너 사용 하 여 이벤트를 만드는 것 외에도 런타임에 이벤트 처리기를 만들 수 있습니다. 이렇게 하면 프로그램이 처음 시작될 때 이벤트 처리기를 연결하는 대신 런타임에 코드를 사용하여 조건에 따라 이벤트 처리기를 연결할 수 있습니다.

## <a name="create-an-event-handler-at-run-time"></a>런타임에 이벤트 처리기 만들기

1. 이벤트 처리기를 추가 하려는 폼을 엽니다.

2. 처리할 이벤트의 메서드 시그니처가 있는 양식에 메서드를 추가합니다.

     예를 들어 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트를 처리 하는 경우 다음과 같은 메서드를 만듭니다.

    ```vb
    Private Sub Button1_Click(ByVal sender As Object, ByVal e As EventArgs)
       ' Add event handler code here.
    End Sub
    ```

    ```csharp
    private void button1_Click(object sender, System.EventArgs e)
    {
    // Add event handler code here.
    }
    ```

    ```cpp
    private:
       void button1_Click(System::Object ^ sender,
          System::EventArgs ^ e)
       {
          // Add event handler code here.
       }
    ```

3. 애플리케이션에 적합한 코드를 이벤트 처리기에 추가합니다.

4. 이벤트 처리기를 만들 양식 또는 컨트롤을 결정합니다.

5. 양식의 클래스에 있는 메서드에 이벤트를 처리할 이벤트 처리기를 지정하는 코드를 추가합니다. 예를 들어 다음 코드는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 `button1_Click` 처리할 이벤트 처리기를 지정 합니다.

    ```vb
    AddHandler Button1.Click, AddressOf Button1_Click
    ```

    ```csharp
    button1.Click += new EventHandler(button1_Click);
    ```

    ```cpp
    button1->Click += gcnew System::EventHandler(this, &Form1::button1_Click);
    ```

     위의 Visual Basic 코드에 설명 된 <xref:System.ComponentModel.EventHandlerList.AddHandler%2A> 메서드는 단추에 대 한 클릭 이벤트 처리기를 설정 합니다.

## <a name="see-also"></a>참고 항목

- [Windows Forms에서 이벤트 처리기 만들기](creating-event-handlers-in-windows-forms.md)
- [이벤트 처리기 개요](event-handlers-overview-windows-forms.md)
- [Visual Basic에서 상속된 이벤트 처리기 관련 문제 해결](../../visual-basic/programming-guide/language-features/events/troubleshooting-inherited-event-handlers.md)
