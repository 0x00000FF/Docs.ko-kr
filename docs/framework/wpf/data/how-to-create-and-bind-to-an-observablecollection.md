---
title: '방법: ObservableCollection 만들기 및 바인딩'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- data binding [WPF], ObservableCollection class
- notifications [WPF]
ms.assetid: 6cf7e275-df76-41c6-a611-53b889b8fd5a
ms.openlocfilehash: 10cea133651739df8bb8e27c58221b34067782f5
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57376119"
---
# <a name="how-to-create-and-bind-to-an-observablecollection"></a>방법: ObservableCollection 만들기 및 바인딩
만들고에서 파생 되는 컬렉션에 바인딩하는 방법을 보여 주는이 예제는 <xref:System.Collections.ObjectModel.ObservableCollection%601> 항목이 추가 되거나 제거 될 때 알림을 제공 하는 컬렉션 클래스 클래스.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `NameList` 컬렉션의 구현을 보여 줍니다.  
  
```csharp  
public class NameList : ObservableCollection<PersonName>  
{  
    public NameList() : base()  
    {  
        Add(new PersonName("Willa", "Cather"));  
        Add(new PersonName("Isak", "Dinesen"));  
        Add(new PersonName("Victor", "Hugo"));  
        Add(new PersonName("Jules", "Verne"));  
    }  
  }  
  
  public class PersonName  
  {  
      private string firstName;  
      private string lastName;  
  
      public PersonName(string first, string last)  
      {  
          this.firstName = first;  
          this.lastName = last;  
      }  
  
      public string FirstName  
      {  
          get { return firstName; }  
          set { firstName = value; }  
      }  
  
      public string LastName  
      {  
          get { return lastName; }  
          set { lastName = value; }  
      }  
  }  
```  
  
```vb  
Public Class NameList  
    Inherits ObservableCollection(Of PersonName)  
  
    ' Methods  
    Public Sub New()  
        MyBase.Add(New PersonName("Willa", "Cather"))  
        MyBase.Add(New PersonName("Isak", "Dinesen"))  
        MyBase.Add(New PersonName("Victor", "Hugo"))  
        MyBase.Add(New PersonName("Jules", "Verne"))  
    End Sub  
  
End Class  
  
Public Class PersonName  
    ' Methods  
    Public Sub New(ByVal first As String, ByVal last As String)  
        Me._firstName = first  
        Me._lastName = last  
    End Sub  
  
    ' Properties  
    Public Property FirstName() As String  
        Get  
            Return Me._firstName  
        End Get  
        Set(ByVal value As String)  
            Me._firstName = value  
        End Set  
    End Property  
  
    Public Property LastName() As String  
        Get  
            Return Me._lastName  
        End Get  
        Set(ByVal value As String)  
            Me._lastName = value  
        End Set  
    End Property  
  
    ' Fields  
    Private _firstName As String  
    Private _lastName As String  
End Class  
```  
  
 [XAML의 바인딩에 사용할 수 있는 데이터 만들기](how-to-make-data-available-for-binding-in-xaml.md)에 설명되어 있는 것처럼 다른 [!INCLUDE[TLA#tla_clr](../../../../includes/tlasharptla-clr-md.md)] 개체의 경우와 마찬가지 방식으로 해당 컬렉션을 바인딩에 사용할 수 있게 만들 수 있습니다. 예를 들어 다음과 같이 [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]에서 컬렉션을 인스턴스화하고 컬렉션을 리소스로 지정할 수 있습니다.  
  
```xaml  
<Window  
  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"  
  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"  
  xmlns:c="clr-namespace:SDKSample"  
  x:Class="SDKSample.Window1"  
  Width="400"  
  Height="280"  
  Title="MultiBinding Sample">  
  
  <Window.Resources>  
    <c:NameList x:Key="NameListData"/>  
  
...  
  
</Window.Resources>  
```  
  
 그런 다음 컬렉션에 바인딩할 수 있습니다.  
  
```xaml  
<ListBox Width="200"  
         ItemsSource="{Binding Source={StaticResource NameListData}}"  
         ItemTemplate="{StaticResource NameItemTemplate}"  
         IsSynchronizedWithCurrentItem="True"/>  
```  
  
 `NameItemTemplate`의 정의는 여기에 나와 있지 않습니다.  
  
> [!NOTE]
>  컬렉션의 개체는 [바인딩 소스 개요](binding-sources-overview.md)에 설명된 요구 사항을 충족해야 합니다. 특히 사용 중인 경우 <xref:System.Windows.Data.BindingMode.OneWay> 또는 <xref:System.Windows.Data.BindingMode.TwoWay> (예를 들어 원하는 [!INCLUDE[TLA2#tla_ui](../../../../includes/tla2sharptla-ui-md.md)] 소스 속성이 동적으로 변경 하는 경우 업데이트), 합니다 와같은적절한속성변경알림메커니즘을구현해야합니다<xref:System.ComponentModel.INotifyPropertyChanged>인터페이스입니다.  
  
 자세한 내용은 [데이터 바인딩 개요](data-binding-overview.md)에서 컬렉션에 바인딩 단원을 참조하세요.  
  
## <a name="see-also"></a>참고자료
- [뷰의 데이터 정렬](how-to-sort-data-in-a-view.md)
- [뷰에서 데이터 필터링](how-to-filter-data-in-a-view.md)
- [XAML 데이터 정렬 및 그룹화](how-to-sort-and-group-data-using-a-view-in-xaml.md)
- [데이터 바인딩 개요](data-binding-overview.md)
- [방법 항목](data-binding-how-to-topics.md)
