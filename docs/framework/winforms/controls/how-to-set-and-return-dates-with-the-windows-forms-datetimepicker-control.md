---
title: "방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜 설정 및 반환 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-winforms"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "jsharp"
helpviewer_keywords: 
  - "날짜, DateTimePicker에서 설정"
  - "DateTimePicker 컨트롤[Windows Forms], 날짜 설정 및 반환"
  - "예제[Windows Forms], DateTimePicker 컨트롤"
ms.assetid: a8a48d68-e4b5-426e-9764-51230fc9acd2
caps.latest.revision: 17
author: "dotnet-bot"
ms.author: "dotnetcontent"
manager: "wpickett"
caps.handback.revision: 17
---
# 방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜 설정 및 반환
Windows Forms <xref:System.Windows.Forms.DateTimePicker> 컨트롤의 현재 선택된 날짜 또는 시간은 <xref:System.Windows.Forms.DateTimePicker.Value%2A> 속성에 의해 결정됩니다.  컨트롤이 표시되기 전에\(예: 디자인 타임에 또는 폼의 <xref:System.Windows.Forms.Form.Load> 이벤트에서\) <xref:System.Windows.Forms.DateTimePicker.Value%2A> 속성을 설정하여 컨트롤에서 초기에 선택되는 날짜를 결정할 수 있습니다.  기본적으로 컨트롤의 <xref:System.Windows.Forms.DateTimePicker.Value%2A>는 현재 날짜로 설정됩니다.  코드에서 컨트롤의 <xref:System.Windows.Forms.DateTimePicker.Value%2A>를 변경하는 경우 폼의 컨트롤이 새 설정을 반영하도록 자동으로 업데이트됩니다.  
  
 <xref:System.Windows.Forms.DateTimePicker.Value%2A> 속성은 <xref:System.DateTime> 구조체를 해당 값으로 반환합니다.  표시된 날짜에 대한 특정 정보를 반환하는 <xref:System.DateTime> 구조체의 여러 속성이 있습니다.  이러한 속성은 값을 반환하는 데만 사용할 수 있습니다. 값을 설정하는 데 사용하지 마세요.  
  
-   날짜 값의 경우 <xref:System.DateTime.Month%2A>, <xref:System.DateTime.Day%2A> 및 <xref:System.DateTime.Year%2A> 속성은 선택한 날짜의 해당 시간 단위에 대한 정수 값을 반환합니다.  <xref:System.DateTime.DayOfWeek%2A> 속성은 선택한 요일을 나타내는 값을 반환합니다\(가능한 값은 <xref:System.DayOfWeek> 열거형에 나열되어 있음\).  
  
-   시간 값의 경우 <xref:System.DateTime.Hour%2A>, <xref:System.DateTime.Minute%2A>, <xref:System.DateTime.Second%2A> 및 <xref:System.DateTime.Millisecond%2A> 속성은 해당 시간 단위에 대한 정수 값을 반환합니다.  시간을 표시하도록 컨트롤을 구성하려면 [방법: DateTimePicker 컨트롤을 사용하여 시간 표시](../../../../docs/framework/winforms/controls/how-to-display-time-with-the-datetimepicker-control.md)를 참조하세요.  
  
### 컨트롤의 날짜 및 시간 값을 설정하려면  
  
-   <xref:System.Windows.Forms.DateTimePicker.Value%2A> 속성을 날짜 또는 시간 값으로 설정합니다.  
  
    ```vb  
    DateTimePicker1.Value = New DateTime(2001, 10, 20)  
  
    ```  
  
    ```csharp  
    dateTimePicker1.Value = new DateTime(2001, 10, 20);  
  
    ```  
  
    ```cpp  
    dateTimePicker1->Value = DateTime(2001, 10, 20);  
    ```  
  
### 날짜 및 시간 값을 반환하려면  
  
-   <xref:System.Windows.Forms.DateTimePicker.Text%2A> 속성을 호출하여 컨트롤에서 지정된 형식의 전체 값을 반환하거나, <xref:System.Windows.Forms.DateTimePicker.Value%2A> 값의 적절한 메서드를 호출하여 값의 일부를 반환합니다.  <xref:System.Windows.Forms.DateTimePicker.ToString%2A>을 통해 사용자에게 표시할 수 있는 문자열로 정보를 변환합니다.  
  
    ```vb  
    MessageBox.Show("The selected value is ", DateTimePicker1.Text)  
    MessageBox.Show("The day of the week is ",   
       DateTimePicker1.Value.DayOfWeek.ToString)  
    MessageBox.Show("Millisecond is: ",   
       DateTimePicker1.Value.Millisecond.ToString)  
  
    ```  
  
    ```csharp  
    MessageBox.Show ("The selected value is " +   
       dateTimePicker1.Text);  
    MessageBox.Show ("The day of the week is " +   
       dateTimePicker1.Value.DayOfWeek.ToString());  
    MessageBox.Show("Millisecond is: " +   
       dateTimePicker1.Value.Millisecond.ToString());  
  
    ```  
  
    ```cpp  
    MessageBox::Show (String::Concat("The selected value is ",  
       dateTimePicker1->Text));  
    MessageBox::Show (String::Concat("The day of the week is ",  
       dateTimePicker1->Value.DayOfWeek.ToString()));  
    MessageBox::Show(String::Concat("Millisecond is: ",  
       dateTimePicker1->Value.Millisecond.ToString()));  
    ```  
  
## 참고 항목  
 [DateTimePicker 컨트롤](../../../../docs/framework/winforms/controls/datetimepicker-control-windows-forms.md)   
 [방법: Windows Forms DateTimePicker 컨트롤을 사용하여 날짜를 사용자 지정 형식으로 표시](../../../../docs/framework/winforms/controls/display-a-date-in-a-custom-format-with-wf-datetimepicker-control.md)