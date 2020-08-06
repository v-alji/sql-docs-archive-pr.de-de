---
title: Beispiele für Gruppierungsausdrücke (Berichts-Generator und SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- data [Reporting Services], grouping
- grouping data
- expressions [Reporting Services], adding
- groups [Reporting Services], expressions
ms.assetid: 34cd0249-fc74-4cf2-ba11-7b072992bfd2
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 128e3fa7aed189fd00072c2c3e961b80f8137c99
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695337"
---
# <a name="group-expression-examples-report-builder-and-ssrs"></a><span data-ttu-id="da02a-102">Beispiele für Gruppierungsausdrücke (Berichts-Generator und SSRS)</span><span class="sxs-lookup"><span data-stu-id="da02a-102">Group Expression Examples (Report Builder and SSRS)</span></span>
  <span data-ttu-id="da02a-103">In einem Datenbereich können Sie Daten nach einem einzelnen Feld gruppieren oder komplexe Ausdrücke erstellen, mit denen die Daten identifiziert werden, nach denen gruppiert wird.</span><span class="sxs-lookup"><span data-stu-id="da02a-103">In a data region, you can group data by a single field, or create more complex expressions that identify the data on which to group.</span></span> <span data-ttu-id="da02a-104">Komplexe Ausdrücke schließen Verweise auf mehrere Felder oder Parameter, Bedingungsanweisungen oder benutzerdefinierten Code ein.</span><span class="sxs-lookup"><span data-stu-id="da02a-104">Complex expressions include references to multiple fields or parameters, conditional statements, or custom code.</span></span> <span data-ttu-id="da02a-105">Wenn Sie für einen Datenbereich eine Gruppe definieren, fügen Sie diese Ausdrücke den **Gruppeneigenschaften** hinzu.</span><span class="sxs-lookup"><span data-stu-id="da02a-105">When you define a group for a data region, you add these expressions to the **Group** properties.</span></span> <span data-ttu-id="da02a-106">Weitere Informationen finden Sie unter [Hinzufügen oder Löschen einer Gruppe in einem Datenbereich &#40;Berichts-Generator und SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="da02a-106">For more information, see [Add or Delete a Group in a Data Region &#40;Report Builder and SSRS&#41;](add-or-delete-a-group-in-a-data-region-report-builder-and-ssrs.md).</span></span>  
  
 <span data-ttu-id="da02a-107">Um zwei oder mehr Gruppen zusammenzuführen, die auf einfachen Feldausdrücken basieren, fügen Sie jedes Feld der Gruppenausdrucksliste in der Gruppendefinition hinzu.</span><span class="sxs-lookup"><span data-stu-id="da02a-107">To merge two or more groups that are based on simple field expressions, add each field to the group expressions list in the group definition.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="examples-of-group-expressions"></a><span data-ttu-id="da02a-108">Beispiele für Gruppenausdrücke</span><span class="sxs-lookup"><span data-stu-id="da02a-108">Examples of Group Expressions</span></span>  
 <span data-ttu-id="da02a-109">In der folgenden Tabelle sind Beispiele für Gruppenausdrücke aufgeführt, die Sie zum Definieren einer Gruppe verwenden können.</span><span class="sxs-lookup"><span data-stu-id="da02a-109">The following table provides examples of group expressions that you can use to define a group.</span></span>  
  
|<span data-ttu-id="da02a-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="da02a-110">Description</span></span>|<span data-ttu-id="da02a-111">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="da02a-111">Expression</span></span>|  
|-----------------|----------------|  
|<span data-ttu-id="da02a-112">Gruppieren nach dem `Region` -Feld.</span><span class="sxs-lookup"><span data-stu-id="da02a-112">Group by the `Region` field.</span></span>|`=Fields!Region.Value`|  
|<span data-ttu-id="da02a-113">Gruppieren Sie nach Nachnamen und Vornamen.</span><span class="sxs-lookup"><span data-stu-id="da02a-113">Group by last name and first name.</span></span>|`=Fields!LastName.Value`<br /><br /> `=Fields!FirstName.Value`|  
|<span data-ttu-id="da02a-114">Gruppieren nach dem ersten Buchstaben des Nachnamens.</span><span class="sxs-lookup"><span data-stu-id="da02a-114">Group by the first letter of the last name.</span></span>|`=Fields!LastName.Value.Substring(0,1)`|  
|<span data-ttu-id="da02a-115">Gruppieren Sie auf Grundlage der Benutzerauswahl nach Parameter.</span><span class="sxs-lookup"><span data-stu-id="da02a-115">Group by parameter, based on user selection.</span></span><br /><br /> <span data-ttu-id="da02a-116">In diesem Beispiel muss der Parameter `GroupBy` auf einer verfügbaren Werteliste basieren, die eine gültige Auswahl für eine Gruppierung bietet.</span><span class="sxs-lookup"><span data-stu-id="da02a-116">In this example, the parameter `GroupBy` must be based on an available values list that provides a valid choice to group on.</span></span>|`=Fields(Parameters!GroupBy.Value).Value`|  
|<span data-ttu-id="da02a-117">Gruppieren Sie nach drei separaten Altersgruppen:</span><span class="sxs-lookup"><span data-stu-id="da02a-117">Group by three separate age ranges:</span></span><br /><br /> <span data-ttu-id="da02a-118">"Unter 21", "Zwischen 21 und 50" und "Über 50".</span><span class="sxs-lookup"><span data-stu-id="da02a-118">"Under 21", "Between 21 and 50", and "Over 50".</span></span>|`=IIF(First(Fields!Age.Value)<21,"Under 21",(IIF(First(Fields!Age.Value)>=21 AND First(Fields!Age.Value)<=50,"Between 21 and 50","Over 50")))`|  
|<span data-ttu-id="da02a-119">Gruppieren Sie nach vielen Altersgruppen.</span><span class="sxs-lookup"><span data-stu-id="da02a-119">Group by many age ranges.</span></span> <span data-ttu-id="da02a-120">In diesem Beispiel wird benutzerdefinierter Code veranschaulicht, der in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET geschrieben ist und der eine Zeichenfolge für die folgenden Bereiche zurückgibt:</span><span class="sxs-lookup"><span data-stu-id="da02a-120">This example shows custom code, written in [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] .NET, that returns a string for the following ranges:</span></span><br /><br /> <span data-ttu-id="da02a-121">25 oder darunter</span><span class="sxs-lookup"><span data-stu-id="da02a-121">25 or Under</span></span><br /><br /> <span data-ttu-id="da02a-122">26 bis 50</span><span class="sxs-lookup"><span data-stu-id="da02a-122">26 to 50</span></span><br /><br /> <span data-ttu-id="da02a-123">51 bis 75</span><span class="sxs-lookup"><span data-stu-id="da02a-123">51 to 75</span></span><br /><br /> <span data-ttu-id="da02a-124">Über 75</span><span class="sxs-lookup"><span data-stu-id="da02a-124">Over 75</span></span>|`=Code.GetRangeValueByAge(Fields!Age.Value)`<br /><br /> <span data-ttu-id="da02a-125">Benutzerdefinierter Code:</span><span class="sxs-lookup"><span data-stu-id="da02a-125">Custom code:</span></span><br /><br /> `Function GetRangeValueByAge(ByVal age As Integer) As String`<br /><br /> `Select Case age`<br /><br /> `Case 0 To 25`<br /><br /> `GetRangeValueByByAge = "25 or Under"`<br /><br /> `Case 26 To 50`<br /><br /> `GetRangeValueByByAge = "26 to 50"`<br /><br /> `Case 51 to 75`<br /><br /> `GetRangeValueByByAge = "51 to 75"`<br /><br /> `Case Else`<br /><br /> `GetRangeValueByByAge = "Over 75"`<br /><br /> `End Select`<br /><br /> `Return GetRangeValueByByAge`<br /><br /> `End Function`|  
  
## <a name="see-also"></a><span data-ttu-id="da02a-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da02a-126">See Also</span></span>  
 <span data-ttu-id="da02a-127">[Filtern, Gruppieren und Sortieren von Daten &#40;Berichts-Generator und SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="da02a-127">[Filter, Group, and Sort Data &#40;Report Builder and SSRS&#41;](filter-group-and-sort-data-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="da02a-128">[Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="da02a-128">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="da02a-129">Benutzerdefinierter Code und Assemblyverweise in Ausdrücken in Berichts-Designer &#40;SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="da02a-129">Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;</span></span>](custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md)  
  
  
