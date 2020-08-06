---
title: Hinzufügen eines Assemblyverweises zu einem Bericht (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- code [Reporting Services]
- custom assemblies [Reporting Services], referencing
- custom code [Reporting Services]
- adding assembly references
- assemblies [Reporting Services], references
ms.assetid: 0a03939e-48ce-4c30-b227-98533f2e0ccb
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 23dda0c65589e55849f906c621e42ce70f0d7ab5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620217"
---
# <a name="add-an-assembly-reference-to-a-report-ssrs"></a><span data-ttu-id="8dfdd-102">Hinzufügen eines Assemblyverweises zu einem Bericht (SSRS)</span><span class="sxs-lookup"><span data-stu-id="8dfdd-102">Add an Assembly Reference to a Report (SSRS)</span></span>
  <span data-ttu-id="8dfdd-103">Wenn Sie benutzerdefinierten Code einbetten, der Verweise auf [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Klassen enthält, die sich nicht in <xref:System.Math> oder <xref:System.Convert> befinden, müssen Sie einen Assemblyverweis auf den Bericht bereitstellen, damit der Berichtsprozessor die Namen auflösen kann.</span><span class="sxs-lookup"><span data-stu-id="8dfdd-103">When you embed custom code that contains references to [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] classes that are not in <xref:System.Math> or <xref:System.Convert>, you must provide an assembly reference to the report so that the report processor can resolve the names.</span></span> <span data-ttu-id="8dfdd-104">Weitere Informationen finden Sie unter [Hinzufügen von Code zu einem Bericht &#40;SSRS&#41;](add-code-to-a-report-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="8dfdd-104">For more information, see [Add Code to a Report &#40;SSRS&#41;](add-code-to-a-report-ssrs.md).</span></span>  
  
### <a name="to-add-an-assembly-reference-to-a-report"></a><span data-ttu-id="8dfdd-105">So fügen Sie einen Assemblyverweis einem Bericht hinzu</span><span class="sxs-lookup"><span data-stu-id="8dfdd-105">To add an assembly reference to a report</span></span>  
  
1.  <span data-ttu-id="8dfdd-106">Klicken Sie in der **Entwurfsansicht** mit der rechten Maustaste auf die Entwurfsoberfläche außerhalb des Rahmens des Berichts, und klicken Sie auf **Berichtseigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="8dfdd-106">In **Design** view, right-click the design surface outside the border of the report and click **Report Properties**.</span></span>  
  
2.  <span data-ttu-id="8dfdd-107">Klicken Sie auf **Verweise**.</span><span class="sxs-lookup"><span data-stu-id="8dfdd-107">Click **References**.</span></span>  
  
3.  <span data-ttu-id="8dfdd-108">Klicken Sie in **Assemblys hinzufügen oder entfernen**auf **Hinzufügen** , und klicken Sie dann auf die Schaltfläche mit den Auslassungspunkten, um zur Assembly zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="8dfdd-108">In **Add or remove assemblies**, click **Add** and then click the ellipsis button to browse to the assembly.</span></span>  
  
4.  <span data-ttu-id="8dfdd-109">Klicken Sie unter **Klassen hinzufügen oder entfernen**auf **Hinzufügen** , und geben Sie dann den Namen der Klasse ein. Geben Sie außerdem einen Instanznamen an, der im Bericht verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8dfdd-109">In **Add or remove classes**, click **Add** and then type name of the class and provide an instance name to use within the report.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8dfdd-110">Geben Sie nur für instanzbasierte Mitglieder einen Klassen- und Instanznamen an.</span><span class="sxs-lookup"><span data-stu-id="8dfdd-110">Specify a class and instance name only for instance-based members.</span></span> <span data-ttu-id="8dfdd-111">Geben Sie in der Liste **Klassen** keine statischen Mitglieder an.</span><span class="sxs-lookup"><span data-stu-id="8dfdd-111">Do not specify static members in the **Classes** list.</span></span> <span data-ttu-id="8dfdd-112">Weitere Informationen finden Sie unter [Benutzerdefinierter Code und Assemblyverweise in Ausdrücken in Berichts-Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)-Ausdruck dar.</span><span class="sxs-lookup"><span data-stu-id="8dfdd-112">For more information, see [Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md).</span></span>  
  
5.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8dfdd-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8dfdd-113">See Also</span></span>  
 <span data-ttu-id="8dfdd-114">[Verwenden benutzerdefinierter Assemblys mit Berichten](../custom-assemblies/using-custom-assemblies-with-reports.md) </span><span class="sxs-lookup"><span data-stu-id="8dfdd-114">[Using Custom Assemblies with Reports](../custom-assemblies/using-custom-assemblies-with-reports.md) </span></span>  
 [<span data-ttu-id="8dfdd-115">Berichtseigenschaften (Dialogfeld), Verweise</span><span class="sxs-lookup"><span data-stu-id="8dfdd-115">Report Properties Dialog Box, References</span></span>](../report-properties-dialog-box-references.md)  
  
  
