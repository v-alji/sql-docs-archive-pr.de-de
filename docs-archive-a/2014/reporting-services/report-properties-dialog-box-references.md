---
title: Berichts Eigenschaften (Dialog Feld), Verweise | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10530"
- sql12.rtp.rptdesigner.reportproperties.references.f1
ms.assetid: 4639d368-9918-4bb1-9953-7a724ca78dea
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4b28ea0865d37bdc56054d6b23dc8c82d9279b08
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717383"
---
# <a name="report-properties-dialog-box-references"></a><span data-ttu-id="00779-102">Berichtseigenschaften (Dialogfeld), Verweise</span><span class="sxs-lookup"><span data-stu-id="00779-102">Report Properties Dialog Box, References</span></span>
  <span data-ttu-id="00779-103">Wählen Sie die Registerkarte **Verweise** im Dialogfeld **Berichtseigenschaften** , um Verweise auf benutzerdefinierte oder andere externe Assemblys sowie benutzerdefinierte Klasseninstanzen hinzuzufügen oder zu entfernen, die von Ausdrücken in der Berichtsdefinition verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="00779-103">Select **References** on the **Report Properties** dialog box to add or remove references to custom or other external assemblies and custom class instances that are used by expressions in the report definition.</span></span>  
  
## <a name="options"></a><span data-ttu-id="00779-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="00779-104">Options</span></span>  
 <span data-ttu-id="00779-105">**Assemblys hinzufügen oder entfernen**</span><span class="sxs-lookup"><span data-stu-id="00779-105">**Add or remove assemblies**</span></span>  
 <span data-ttu-id="00779-106">Führt die Assemblys auf, auf die der Bericht verweist.</span><span class="sxs-lookup"><span data-stu-id="00779-106">Lists the assemblies that the report references.</span></span> <span data-ttu-id="00779-107">Die Assembly muss auf dem Computer, auf dem das Tool zum Entwerfen des Berichts installiert ist, und auf dem Berichtsserver verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="00779-107">The assembly must be available on the computer on which the tool you are using to design the report is installed and on the report server.</span></span> <span data-ttu-id="00779-108">Der Name des Verweises muss genau mit dem Inhalt der **\<CodeModule>** Tags in der RDL-Datei (Report Definition Language) übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="00779-108">The name of the reference must match the contents of **\<CodeModule>** tags in the Report Definition Language (.rdl) file exactly.</span></span>  
  
 <span data-ttu-id="00779-109">**Add**</span><span class="sxs-lookup"><span data-stu-id="00779-109">**Add**</span></span>  
 <span data-ttu-id="00779-110">Klicken Sie auf diese Option, um eine Assembly hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="00779-110">Click to add an assembly.</span></span> <span data-ttu-id="00779-111">Klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (...), um das Dialogfeld **Öffnen** zu öffnen und die für die Berichts Verarbeitung und Ausdrucks Auswertung erforderlichen Assemblys auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="00779-111">Click the ellipsis (...) button to open the **Open** dialog box and select the assemblies necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="00779-112">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="00779-112">**Delete**</span></span>  
 <span data-ttu-id="00779-113">Um einen Assemblyverweis aus der Liste zu entfernen, wählen Sie den Assemblynamen aus, und klicken Sie auf die Schaltfläche **Entfernen** .</span><span class="sxs-lookup"><span data-stu-id="00779-113">To remove an assembly reference from the list, select the assembly name and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="00779-114">**Klassen hinzufügen oder entfernen**</span><span class="sxs-lookup"><span data-stu-id="00779-114">**Add or remove classes**</span></span>  
 <span data-ttu-id="00779-115">Führt die vom Bericht verwendeten Klasseninstanzen auf.</span><span class="sxs-lookup"><span data-stu-id="00779-115">Lists the class instances that are used by the report.</span></span> <span data-ttu-id="00779-116">Die Klassenliste wird nur von instanzbasierten Elementen, nicht von statischen Elementen, verwendet.</span><span class="sxs-lookup"><span data-stu-id="00779-116">The class list is used only by instance-based members, not static members.</span></span>  
  
 <span data-ttu-id="00779-117">**Add**</span><span class="sxs-lookup"><span data-stu-id="00779-117">**Add**</span></span>  
 <span data-ttu-id="00779-118">Klicken Sie auf diese Schaltfläche, um einen Klassenverweis hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="00779-118">Click to add a class reference.</span></span> <span data-ttu-id="00779-119">Klicken Sie auf die Schaltfläche mit den Auslassungs Punkten (...), um das Dialogfeld **Öffnen** zu öffnen und die für die Berichts Verarbeitung und Ausdrucks Auswertung erforderlichen Klassen auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="00779-119">Click the ellipsis (...) button to open the **Open** dialog box and select the classes necessary to complete report processing and expression evaluation.</span></span>  
  
 <span data-ttu-id="00779-120">**Löschen**</span><span class="sxs-lookup"><span data-stu-id="00779-120">**Delete**</span></span>  
 <span data-ttu-id="00779-121">Um die Klasseninstanz zu löschen, wählen Sie sie aus, und klicken Sie auf die Schaltfläche **Entfernen** .</span><span class="sxs-lookup"><span data-stu-id="00779-121">To delete the class instance, select it and click the **Remove** button.</span></span>  
  
 <span data-ttu-id="00779-122">**Nach oben**</span><span class="sxs-lookup"><span data-stu-id="00779-122">**Up**</span></span>  
 <span data-ttu-id="00779-123">Für Klassen mit Abhängigkeiten können Sie diesen Verweis in der Liste nach oben verschieben.</span><span class="sxs-lookup"><span data-stu-id="00779-123">For classes that have dependencies, you can move this reference higher in the list.</span></span>  
  
 <span data-ttu-id="00779-124">**Nach unten**</span><span class="sxs-lookup"><span data-stu-id="00779-124">**Down**</span></span>  
 <span data-ttu-id="00779-125">Für Klassen mit Abhängigkeiten können Sie diesen Verweis in der Liste nach unten verschieben.</span><span class="sxs-lookup"><span data-stu-id="00779-125">For classes that have dependencies, you can move this reference lower in the list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00779-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="00779-126">See Also</span></span>  
 <span data-ttu-id="00779-127">[Benutzerdefinierter Code und Assemblyverweise in Ausdrücken in Berichts-Designer (SSRS)](report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="00779-127">[Custom Code and Assembly References in Expressions in Report Designer &#40;SSRS&#41;](report-design/custom-code-and-assembly-references-in-expressions-in-report-designer-ssrs.md) </span></span>  
 <span data-ttu-id="00779-128">[Berichts-und Gruppen Variablen Sammlungen verweisen auf &#40;Berichts-Generator und SSRS&#41;](report-design/built-in-collections-report-and-group-variables-references-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="00779-128">[Report and Group Variables Collections References &#40;Report Builder and SSRS&#41;](report-design/built-in-collections-report-and-group-variables-references-report-builder.md) </span></span>  
 [<span data-ttu-id="00779-129">Beispiele für Ausdrücke &#40;Berichts-Generator und SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="00779-129">Expression Examples &#40;Report Builder and SSRS&#41;</span></span>](report-design/expression-examples-report-builder-and-ssrs.md)  
  
  
