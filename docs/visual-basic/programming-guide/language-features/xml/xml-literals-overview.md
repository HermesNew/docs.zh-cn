---
title: XML 文本概述
ms.date: 07/20/2015
helpviewer_keywords:
- XML literals [Visual Basic], about XML literals
- declaring XML literals [Visual Basic]
- LINQ to XML [Visual Basic], XML literals
- literals [Visual Basic], XML
ms.assetid: 37987c15-4ab8-471b-bd45-399816bfb57f
ms.openlocfilehash: e5d2465d145f4059600121c6cef30bb2c74a8c1c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346190"
---
# <a name="xml-literals-overview-visual-basic"></a>XML 文本概述 (Visual Basic)
*Xml 文本*允许将 xml 直接合并到 Visual Basic 代码。 XML 文本语法表示 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 对象，它类似于 XML 1.0 语法。 这样可以更轻松地以编程方式创建 XML 元素和文档，因为你的代码具有与最终 XML 相同的结构。  
  
 Visual Basic 将 XML 文本编译到 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 对象中。 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 提供了一种用于创建和操作 XML 的简单对象模型，此模型很好地与 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)]集成。 有关详细信息，请参阅 <xref:System.Xml.Linq.XElement>。  
  
 您可以在 XML 文本中嵌入 Visual Basic 表达式。 在运行时，应用程序将为每个文本创建一个 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 对象，并合并嵌入式表达式的值。 这使您可以在 XML 文本中指定动态内容。 有关详细信息，请参阅[XML 中的嵌入式表达式](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)。  
  
 有关 XML 文本语法和 XML 1.0 语法之间的差异的详细信息，请参阅[Xml 文本和 xml 1.0 规范](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)。  
  
## <a name="simple-literals"></a>简单文本  
 可以通过在有效的 XML 中键入或粘贴，在 Visual Basic 代码中创建 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 对象。 XML 元素文本返回 <xref:System.Xml.Linq.XElement> 的对象。 有关详细信息，请参阅[Xml 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)和[XML 文本和 xml 1.0 规范](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)。 下面的示例创建一个具有多个子元素的 XML 元素。  
  
 [!code-vb[VbXMLSamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#5)]  
  
 可以通过使用 `<?xml version="1.0"?>`启动 XML 文本来创建 XML 文档，如以下示例中所示。 XML 文档文本返回 <xref:System.Xml.Linq.XDocument> 的对象。 有关详细信息，请参阅[XML 文档文本](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)。  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
> [!NOTE]
> Visual Basic 中的 XML 文本语法与 XML 1.0 规范中的语法不完全相同。 有关详细信息，请参阅[Xml 文本和 xml 1.0 规范](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-and-the-xml-1-0-specification.md)。  
  
## <a name="line-continuation"></a>行继续符  
 XML 文本可以跨多行，而无需使用行继续符（空格-下划线-enter 序列）。 这样就可以更轻松地在代码中将 XML 文本与 XML 文档进行比较。  
  
 编译器将行继续符视为 XML 文本的一部分。 因此，只有在 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 对象中时，才应使用空格-下划线-enter 序列。  
  
 但是，如果在嵌入式表达式中有多行表达式，则需要行继续符。 有关详细信息，请参阅[XML 中的嵌入式表达式](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)。  
  
## <a name="embedding-queries-in-xml-literals"></a>在 XML 文本中嵌入查询  
 您可以在嵌入式表达式中使用查询。 执行此操作时，查询返回的元素将添加到 XML 元素。 这使你可以向 XML 文本添加动态内容（例如用户的查询结果）。  
  
 例如，下面的代码使用嵌入式查询从 `phoneNumbers2` 数组的成员创建 XML 元素，然后将这些元素作为 `contact2`的子级添加。  
  
 [!code-vb[VbXMLSamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#7)]  
  
## <a name="how-the-compiler-creates-objects-from-xml-literals"></a>编译器如何从 XML 文本创建对象  
 Visual Basic 编译器将 XML 文本转换为对等效 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 构造函数的调用，以生成 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 对象。 例如，Visual Basic 编译器会将下面的代码示例转换为对 XML 版本指令的 <xref:System.Xml.Linq.XProcessingInstruction> 构造函数的调用，对 `<contact>`、`<name>`和 `<phone>` 元素调用 <xref:System.Xml.Linq.XElement> 构造函数，并调用 <xref:System.Xml.Linq.XAttribute> 特性的 `type` 构造函数。 具体而言，假设下面的示例中的特性，Visual Basic 编译器将调用 <xref:System.Xml.Linq.XAttribute.%23ctor%28System.Xml.Linq.XName%2CSystem.Object%29> 构造函数两次。 第一个参数将传递 `name` 参数的值 `type`，并为 `value` 参数传递值 `home`。 第二个还将传递 `name` 参数 `type` 的值，但 `value` 参数的值 `work`。  
  
 [!code-vb[VbXMLSamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples2.vb#6)]  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Xml.Linq.XElement>
- [在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML 中的嵌入式表达式](../../../../visual-basic/programming-guide/language-features/xml/embedded-expressions-in-xml.md)
- [XML 文档文本](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML 文本](../../../../visual-basic/language-reference/xml-literals/index.md)
