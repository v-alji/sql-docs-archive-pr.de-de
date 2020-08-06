---
title: Objekt Anzahl angeben (Assistent für Verwendungs basierte Optimierung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.calculatingobjectcounts.f1
ms.assetid: 306c7c25-ae24-4852-ab8c-c82f68a4bc1f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 862be19f12308def815a280dba04f42f0cbe6878
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620550"
---
# <a name="specify-object-counts-usage-based-optimization-wizard"></a><span data-ttu-id="22dc4-102">Objektanzahl angeben (Assistent für verwendungsbasierte Optimierung)</span><span class="sxs-lookup"><span data-stu-id="22dc4-102">Specify Object Counts (Usage-Based Optimization Wizard)</span></span>
  <span data-ttu-id="22dc4-103">Auf der Seite **Objektanzahl angeben** können Sie die Anzahl der Objekte im Cube automatisch berechnen lassen oder die geschätzte Anzahl manuell eingeben.</span><span class="sxs-lookup"><span data-stu-id="22dc4-103">Use the **Specify Object Counts** page to automatically calculate the count of objects in the cube or to manually enter estimated counts.</span></span> <span data-ttu-id="22dc4-104">Der Assistent für verwendungsbasierte Optimierung schätzt die Speicheranforderungen anhand der Objektanzahlen.</span><span class="sxs-lookup"><span data-stu-id="22dc4-104">The Usage-Based Optimization Wizard uses the object counts to estimate storage requirements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="22dc4-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="22dc4-105">Options</span></span>  
 <span data-ttu-id="22dc4-106">**Cubeobjekte**</span><span class="sxs-lookup"><span data-stu-id="22dc4-106">**Cube Objects**</span></span>  
 <span data-ttu-id="22dc4-107">Zeigt die Dimensionen und Attribute im Cube an.</span><span class="sxs-lookup"><span data-stu-id="22dc4-107">Displays the dimensions and attributes in the cube.</span></span> <span data-ttu-id="22dc4-108">Es werden nur die Attribute angezeigt, deren- `AggregationUsage` Eigenschaft auf der Seite **Aggregations Verwendung überprüfen** des Assistenten nicht auf None festgelegt ist, da dies die einzigen Attribute sind, für die die Anzahl angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="22dc4-108">Only the attributes that do not have their `AggregationUsage` property set to None in the **Review Aggregation Usage** page of the wizard are shown because those are the only attributes that need counts specified.</span></span>  
  
 <span data-ttu-id="22dc4-109">**Geschätzte Anzahl**</span><span class="sxs-lookup"><span data-stu-id="22dc4-109">**Estimated count**</span></span>  
 <span data-ttu-id="22dc4-110">Zeigt die geschätzte Anzahl der Zeilen in der Measuregruppe sowie die geschätzte Anzahl der Attributelemente in den Datenbankdimensionen an.</span><span class="sxs-lookup"><span data-stu-id="22dc4-110">Displays the estimated number of rows in the measure group and the estimated attribute member counts in the database dimensions.</span></span> <span data-ttu-id="22dc4-111">Sie können einen Wert eingeben, der als geschätzte Anzahl verwendet werden soll, oder die Werte für die geschätzte Anzahl berechnen.</span><span class="sxs-lookup"><span data-stu-id="22dc4-111">You can type a value to use as the estimated count or you can calculate the estimated count values.</span></span> <span data-ttu-id="22dc4-112">Geben Sie 0 in das Feld ein, und klicken Sie dann auf **Anzahl**, um die Anzahlwerte zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="22dc4-112">To calculate the count values, type 0 in the field and then click **Count**.</span></span> <span data-ttu-id="22dc4-113">Felder, in denen bereits eine Anzahl angezeigt wird, werden nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="22dc4-113">Fields that already display a count are not updated.</span></span>  
  
 <span data-ttu-id="22dc4-114">**Anzahl von Partitionen**</span><span class="sxs-lookup"><span data-stu-id="22dc4-114">**Partition count**</span></span>  
 <span data-ttu-id="22dc4-115">(Optional) Geben Sie die geschätzte Anzahl der Zeilen in der Measuregruppe sowie die geschätzte Anzahl der Attributelemente in den Partitionen ein.</span><span class="sxs-lookup"><span data-stu-id="22dc4-115">(Optional) Type the estimated number of rows in the measure group and the estimated attribute member counts in the partitions.</span></span>  
  
 <span data-ttu-id="22dc4-116">**Count**</span><span class="sxs-lookup"><span data-stu-id="22dc4-116">**Count**</span></span>  
 <span data-ttu-id="22dc4-117">Berechnet und füllt für alle leeren Felder die Werte in der Spalte **Geschätzte Anzahl** neu.</span><span class="sxs-lookup"><span data-stu-id="22dc4-117">Calculates and repopulates the values in the **Estimated count** column for all empty fields.</span></span> <span data-ttu-id="22dc4-118">Felder, in denen bereits eine Anzahl angezeigt wird, werden nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="22dc4-118">Fields that already display a count are not updated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22dc4-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="22dc4-119">See Also</span></span>  
 <span data-ttu-id="22dc4-120">[Aggregations Entwurfs-Assistent F1-Hilfe](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="22dc4-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="22dc4-121">Analysis Services Assistenten &#40;Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="22dc4-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
