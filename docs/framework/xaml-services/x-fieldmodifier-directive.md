---
title: x:FieldModifier 指令
ms.date: 03/30/2017
helpviewer_keywords:
- FieldModifier attribute in XAML [XAML Services]
- x:FieldModifier attribute [XAML Services]
- XAML [XAML Services], x:FieldModifier attribute
ms.assetid: ed427cd4-2f35-4d24-bd2f-0fa7b71ec248
ms.openlocfilehash: 646ad1ca99d83f9fb2994f3c394eca27a60c0eac
ms.sourcegitcommit: 4b9c2d893b45d47048c6598b4182ba87759b1b59
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/25/2019
ms.locfileid: "68484722"
---
# <a name="xfieldmodifier-directive"></a>x:FieldModifier 指令
修改 XAML 编译行为, 以便使用<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> access 而不<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>是默认行为来定义命名对象引用的字段。  
  
## <a name="xaml-attribute-usage"></a>XAML 属性用法  
  
```xaml  
<object x:FieldModifier="Public".../>  
```  
  
## <a name="xaml-values"></a>XAML 值  
  
|||  
|-|-|  
|*Public*|传递给指定<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>的确切字符串与<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>不同, 具体取决于所使用的代码隐藏编程语言。 请参阅“备注”。|  
  
## <a name="dependencies"></a>依赖项  
 如果 xaml 生产使用`x:FieldModifier`任意位置, 则该 xaml 生产的根元素必须声明[x:Class 指令](x-class-directive.md)。  
  
## <a name="remarks"></a>备注  
 `x:FieldModifier`与声明类或其成员的常规访问级别无关。 当处理作为 XAML 生产一部分的特定 XAML 对象时, 此方法仅适用于 XAML 处理行为, 并成为可在应用程序的对象图中访问的对象。 默认情况下, 此类对象的字段引用保持为私有, 这会阻止控件使用者直接修改对象图。 相反, 控件使用者应该使用由编程模型启用的标准模式 (如通过获取布局根、子元素集合、专用公共属性等) 来修改对象关系图。  
  
 `x:FieldModifier`特性的值因编程语言而异, 其用途在特定框架中可能有所不同。 要使用的字符串取决于每种语言如何实现<xref:System.CodeDom.Compiler.CodeDomProvider>其和返回的类型转换器, 以定义<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>和<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>的含义, 以及该语言是否区分大小写。  
  
- 对于C#, 要传递的要传递<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType>的字符串为。 `public`  
  
- 对于 Microsoft Visual Basic .net, 要传递<xref:System.Reflection.TypeAttributes.Public?displayProperty=nameWithType> `Public`的字符串为。  
  
- 对于C++/cli, 当前不存在 XAML 的目标;因此, 传递的字符串未定义。  
  
 你还可以在<xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType> Visual Basic`internal`中C#指定`Friend` (在中), <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>但指定不`NotPublic`常见, 因为行为已是默认值。  
  
 <xref:System.Reflection.TypeAttributes.NotPublic?displayProperty=nameWithType>是默认行为, 因为编译 XAML 的程序集之外的代码很少需要访问 XAML 创建的元素。 WPF 安全体系结构与 XAML 编译行为一起不会声明将元素实例存储为公共的字段, 除非您专门`x:FieldModifier`将设置为允许公共访问。  
  
 `x:FieldModifier`仅适用于具有[X:Name 指令](x-name-directive.md)的元素, 因为该名称用于在其公开后引用字段。  
  
 默认情况下, 根元素的分部类是公共的;但是, 可以使用[X:ClassModifier 指令](x-classmodifier-directive.md)使其成为非公共的。 [X:ClassModifier 指令](x-classmodifier-directive.md)还会影响 root 元素类的实例的访问级别。 你可以将`x:Name`和`x:FieldModifier`置于根元素上, 但这只会生成根元素的公共字段副本, 其真正的根元素类访问级别仍由[x:ClassModifier 指令](x-classmodifier-directive.md)控制。  
  
## <a name="see-also"></a>请参阅

- [XAML 及 WPF 的自定义类](../wpf/advanced/xaml-and-custom-classes-for-wpf.md)
- [WPF 中的代码隐藏和 XAML](../wpf/advanced/code-behind-and-xaml-in-wpf.md)
- [x:Name 指令](x-name-directive.md)
- [Building a WPF Application (WPF)](../wpf/app-development/building-a-wpf-application-wpf.md)（生成 WPF 应用程序 (WPF)）
- [x:ClassModifier 指令](x-classmodifier-directive.md)
