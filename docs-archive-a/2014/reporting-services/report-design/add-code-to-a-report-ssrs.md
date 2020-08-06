---
title: Hinzufügen von Code zu einem Bericht (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- code [Reporting Services]
- custom code [Reporting Services]
- expressions [Reporting Services], code
- adding code
- reports [Reporting Services], code
ms.assetid: 00ef8fc6-99fe-49b2-8a22-7eb475881dc4
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: c1964e69d00e1a27da29ce8cfb73b7bee1bece7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717518"
---
# <a name="add-code-to-a-report-ssrs"></a><span data-ttu-id="5abde-102">Hinzufügen von Code zu einem Bericht (SSRS)</span><span class="sxs-lookup"><span data-stu-id="5abde-102">Add Code to a Report (SSRS)</span></span>
  <span data-ttu-id="5abde-103">Sie können in jedem beliebigen Ausdruck einen eigenen benutzerdefinierten Code aufrufen.</span><span class="sxs-lookup"><span data-stu-id="5abde-103">In any expression, you can call your own custom code.</span></span> <span data-ttu-id="5abde-104">Sie können Code auf folgende zwei Arten bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="5abde-104">You can provide code in the following two ways:</span></span>  
  
-   <span data-ttu-id="5abde-105">Betten Sie in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] geschriebenen Code direkt in Ihren Bericht ein.</span><span class="sxs-lookup"><span data-stu-id="5abde-105">Embed code written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] directly in your report.</span></span> <span data-ttu-id="5abde-106">Wenn Ihr Code auf eine [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Instanz verweist, die <xref:System.Math> oder <xref:System.Convert> nicht aufweist, müssen Sie einen Verweis auf den Bericht hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5abde-106">If your code refers to a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] that is not <xref:System.Math> or <xref:System.Convert>, you must add the reference to the report.</span></span> <span data-ttu-id="5abde-107">Weitere Informationen finden Sie unter [Hinzufügen eines Assemblyverweises zu einem Bericht &#40;SSRS&#41;](add-an-assembly-reference-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5abde-107">For more information, see [Add an Assembly Reference to a Report &#40;SSRS&#41;](add-an-assembly-reference-to-a-report-ssrs.md).</span></span> <span data-ttu-id="5abde-108">Weitere Informationen zu anderen Verweisen finden Sie unter [Benutzerdefinierter Code und Assemblyverweise in Ausdrücken in Berichts-Designer (SSRS)](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="5abde-108">For more information about other references you can make from your code, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
-   <span data-ttu-id="5abde-109">Stellen Sie mit dem [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]eine benutzerdefinierte Codeassembly bereit.</span><span class="sxs-lookup"><span data-stu-id="5abde-109">Provide a custom code assembly by using the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)].</span></span> <span data-ttu-id="5abde-110">Wenn Sie eine benutzerdefinierte Assembly bereitstellen, müssen Sie sie sowohl auf dem Computer, auf dem Sie den Bericht schreiben, als auch auf dem Berichtsserver, auf dem Sie den Bericht anzeigen, installieren.</span><span class="sxs-lookup"><span data-stu-id="5abde-110">If you provide a custom assembly, you must install it on both the computer where you author the report and the report server where you view the report.</span></span> <span data-ttu-id="5abde-111">Weitere Informationen finden Sie unter [Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md).</span><span class="sxs-lookup"><span data-stu-id="5abde-111">For more information, see [Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md).</span></span>  
  
### <a name="to-add-embedded-code-to-a-report"></a><span data-ttu-id="5abde-112">So fügen Sie einem Bericht eingebetteten Code hinzu</span><span class="sxs-lookup"><span data-stu-id="5abde-112">To add embedded code to a report</span></span>  
  
1.  <span data-ttu-id="5abde-113">Klicken Sie in der **Entwurfsansicht** mit der rechten Maustaste auf die Entwurfsoberfläche außerhalb des Rahmens des Berichts, und klicken Sie auf **Berichtseigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="5abde-113">In **Design** view, right-click the design surface outside the border of the report and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="5abde-114">Klicken Sie auf **Code**.</span><span class="sxs-lookup"><span data-stu-id="5abde-114">Click **Code**.</span></span>  
  
3.  <span data-ttu-id="5abde-115">Geben Sie den Code unter **Benutzerdefinierter Code**ein.</span><span class="sxs-lookup"><span data-stu-id="5abde-115">In **Custom code**, type the code.</span></span> <span data-ttu-id="5abde-116">Fehler im Code erzeugen Warnungen, wenn der Bericht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5abde-116">Errors in the code produce warnings when the report runs.</span></span> <span data-ttu-id="5abde-117">Im folgenden Beispiel wird eine benutzerdefinierte Funktion namens `ChangeWord` erstellt, die das Wort "`Bike`" mit "`Bicycle`" ersetzt.</span><span class="sxs-lookup"><span data-stu-id="5abde-117">The following example creates a custom function named `ChangeWord` that replaces the word "`Bike`" with "`Bicycle`".</span></span>  
  
    ```  
    Public Function ChangeWord(ByVal s As String) As String  
       Dim strBuilder As New System.Text.StringBuilder(s)  
       If s.Contains("Bike") Then  
          strBuilder.Replace("Bike", "Bicycle")  
          Return strBuilder.ToString()  
          Else : Return s  
       End If  
    End Function  
    ```  
  
4.  <span data-ttu-id="5abde-118">Im folgenden Beispiel wird gezeigt, wie ein Datasetfeld namens Kategorie in einem Ausdruck an diese Funktion übergeben wird:</span><span class="sxs-lookup"><span data-stu-id="5abde-118">The following example shows how to pass a dataset field named Category to this function in an expression:</span></span>  
  
    ```  
    =Code.ChangeWord(Fields!Category.Value)  
    ```  
  
     <span data-ttu-id="5abde-119">Wenn Sie diesen Ausdruck einer Tabellenzelle hinzufügen, in der Kategoriewerte angezeigt werden, wird, wenn das Wort "Bike" im Datasetfeld für diese Zeile enthalten ist, stattdessen das Wort "Bicycle" als Tabellenzellenwert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5abde-119">If you add this expression to a table cell that displays category values, whenever the word "Bike" is in the dataset field for that row, the table cell value displays the word "Bicycle" instead.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5abde-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5abde-120">See Also</span></span>  
 <span data-ttu-id="5abde-121">[Berichtseigenschaften (Dialogfeld), Code](../report-properties-dialog-box-code.md) </span><span class="sxs-lookup"><span data-stu-id="5abde-121">[Report Properties Dialog Box, Code](../report-properties-dialog-box-code.md) </span></span>  
 <span data-ttu-id="5abde-122">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="5abde-122">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="5abde-123">Verweise auf Parameters-Sammlungen &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="5abde-123">Parameters Collection References &#40;Report Builder and SSRS&#41;</span></span>](built-in-collections-parameters-collection-references-report-builder.md)  
  
  
