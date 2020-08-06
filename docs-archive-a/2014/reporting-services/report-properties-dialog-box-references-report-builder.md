---
title: Dialog Feld "Berichts Eigenschaften", "Verweise" (Berichts-Generator) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10082"
ms.assetid: 3414c857-8ea6-4fc4-a6d5-b4883c039efa
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2c28e9053a1c13f8d0e0b7b44f3b1a037976c318
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717392"
---
# <a name="report-properties-dialog-box-references-report-builder"></a><span data-ttu-id="b703b-102">Berichtseigenschaften (Dialogfeld), Verweise (Berichts-Generator)</span><span class="sxs-lookup"><span data-stu-id="b703b-102">Report Properties Dialog Box, References (Report Builder)</span></span>
  <span data-ttu-id="b703b-103">Wählen Sie die Registerkarte **Verweise** im Dialogfeld **Berichtseigenschaften** , um Verweise auf benutzerdefinierte oder andere externe Assemblys sowie benutzerdefinierte Klasseninstanzen hinzuzufügen oder zu entfernen, die von Ausdrücken in der Berichtsdefinition verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b703b-103">Select **References** on the **Report Properties** dialog box to add or remove references to custom or other external assemblies and custom class instances that are used by expressions in the report definition.</span></span> <span data-ttu-id="b703b-104">Benutzerdefinierte Assemblys werden im lokalen Modus in Berichts-Generator nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b703b-104">Custom assemblies are not supported in local mode in Report Builder.</span></span> <span data-ttu-id="b703b-105">Verwenden Sie Berichts-Designer in, um Berichte zu erstellen, die benutzerdefinierte Assemblys verwenden [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b703b-105">To author reports that use custom assemblies, use Report Designer in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="b703b-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b703b-106">Options</span></span>  
 <span data-ttu-id="b703b-107">**Assemblys hinzufügen oder entfernen**</span><span class="sxs-lookup"><span data-stu-id="b703b-107">**Add or remove assemblies**</span></span>  
 <span data-ttu-id="b703b-108">Führt die Assemblys auf, auf die der Bericht verweist.</span><span class="sxs-lookup"><span data-stu-id="b703b-108">Lists the assemblies that the report references.</span></span> <span data-ttu-id="b703b-109">Die Assembly muss auf dem Computer, auf dem das Tool zum Entwerfen des Berichts installiert ist, und auf dem Berichtsserver verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="b703b-109">The assembly must be available on the computer on which the tool you are using to design the report is installed and on the report server.</span></span> <span data-ttu-id="b703b-110">Der Name des Verweises muss genau mit dem Inhalt der **\<CodeModule>** Tags in der RDL-Datei (Report Definition Language) übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="b703b-110">The name of the reference must match the contents of **\<CodeModule>** tags in the Report Definition Language (.rdl) file exactly.</span></span>  
  
 <span data-ttu-id="b703b-111">**Add**</span><span class="sxs-lookup"><span data-stu-id="b703b-111">**Add**</span></span>  
 <span data-ttu-id="b703b-112">Klicken Sie auf diese Option, um eine Assembly hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b703b-112">Click to add an assembly.</span></span> <span data-ttu-id="b703b-113">Klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (...), um das Dialogfeld **Öffnen** zu öffnen und die für die Berichts Verarbeitung und Ausdrucks Auswertung erforderlichen Assemblys auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b703b-113">Click the ellipsis (...) button to open the **Open** dialog box and select the assemblies necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="b703b-114">**Entfernen**</span><span class="sxs-lookup"><span data-stu-id="b703b-114">**Remove**</span></span>  
 <span data-ttu-id="b703b-115">Um einen Assemblyverweis aus der Liste zu entfernen, wählen Sie den Assemblynamen aus, und klicken Sie auf die Schaltfläche **Entfernen** .</span><span class="sxs-lookup"><span data-stu-id="b703b-115">To remove an assembly reference from the list, select the assembly name and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="b703b-116">**Klassen hinzufügen oder entfernen**</span><span class="sxs-lookup"><span data-stu-id="b703b-116">**Add or remove classes**</span></span>  
 <span data-ttu-id="b703b-117">Führt die vom Bericht verwendeten Klasseninstanzen auf.</span><span class="sxs-lookup"><span data-stu-id="b703b-117">Lists the class instances that are used by the report.</span></span> <span data-ttu-id="b703b-118">Die Klassenliste wird nur von instanzbasierten Elementen, nicht von statischen Elementen, verwendet.</span><span class="sxs-lookup"><span data-stu-id="b703b-118">The class list is used only by instance-based members, not static members.</span></span>  
  
 <span data-ttu-id="b703b-119">**Add**</span><span class="sxs-lookup"><span data-stu-id="b703b-119">**Add**</span></span>  
 <span data-ttu-id="b703b-120">Klicken Sie auf diese Schaltfläche, um einen Klassenverweis hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b703b-120">Click to add a class reference.</span></span> <span data-ttu-id="b703b-121">Klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (...), um das Dialogfeld **Öffnen** zu öffnen und die für die Berichts Verarbeitung und Ausdrucks Auswertung erforderlichen Klassen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b703b-121">Click the ellipsis (...) button to open the **Open** dialog box and select the classes necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="b703b-122">**Entfernen**</span><span class="sxs-lookup"><span data-stu-id="b703b-122">**Remove**</span></span>  
 <span data-ttu-id="b703b-123">Um die Klasseninstanz zu löschen, wählen Sie sie aus, und klicken Sie auf die Schaltfläche **Entfernen** .</span><span class="sxs-lookup"><span data-stu-id="b703b-123">To delete the class instance, select it and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="b703b-124">**Nach oben**</span><span class="sxs-lookup"><span data-stu-id="b703b-124">**Up**</span></span>  
 <span data-ttu-id="b703b-125">Für Klassen mit Abhängigkeiten können Sie diesen Verweis in der Liste nach oben verschieben.</span><span class="sxs-lookup"><span data-stu-id="b703b-125">For classes that have dependencies, you can move this reference higher in the list.</span></span>  
  
 <span data-ttu-id="b703b-126">**Nach unten**</span><span class="sxs-lookup"><span data-stu-id="b703b-126">**Down**</span></span>  
 <span data-ttu-id="b703b-127">Für Klassen mit Abhängigkeiten können Sie diesen Verweis in der Liste nach unten verschieben.</span><span class="sxs-lookup"><span data-stu-id="b703b-127">For classes that have dependencies, you can move this reference lower in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b703b-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b703b-128">See Also</span></span>  
 <span data-ttu-id="b703b-129">[Berichts-Generator Hilfe zu Dialog Feldern, Bereichen und Assistenten](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span><span class="sxs-lookup"><span data-stu-id="b703b-129">[Report Builder Help for Dialog Boxes, Panes, and Wizards](../../2014/reporting-services/report-builder-help-for-dialog-boxes-panes-and-wizards.md) </span></span>  
 [<span data-ttu-id="b703b-130">Ausdrücke &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="b703b-130">Expressions &#40;Report Builder and SSRS&#41;</span></span>](report-design/expressions-report-builder-and-ssrs.md)  
  
  
