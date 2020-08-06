---
title: Objekt Anzahl angeben (Aggregations Entwurfs-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.storagedesignwizard.calculatingobjectcounts.f1
ms.assetid: 305d9d79-d1ab-4704-a7b5-3283842b3996
author: minewiskan
ms.author: owend
ms.openlocfilehash: c66b972395f86746b2d08df234db8aa0c71d03fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619383"
---
# <a name="specify-object-counts-aggregation-design-wizard"></a><span data-ttu-id="3894a-102">Objektanzahl angeben (Aggregationsentwurfs-Assistent)</span><span class="sxs-lookup"><span data-stu-id="3894a-102">Specify Object Counts (Aggregation Design Wizard)</span></span>
  <span data-ttu-id="3894a-103">Auf der Seite **Objektanzahl angeben** können Sie die Anzahl der Objekte im Cube automatisch berechnen lassen oder die geschätzte Anzahl manuell eingeben.</span><span class="sxs-lookup"><span data-stu-id="3894a-103">Use the **Specify Object Counts** page to automatically calculate the count of objects in the cube or to manually enter estimated counts.</span></span> <span data-ttu-id="3894a-104">Mithilfe dieser Objektanzahl ermittelt der Aggregationsentwurfs-Assistent die geschätzten Speicheranforderungen.</span><span class="sxs-lookup"><span data-stu-id="3894a-104">The Aggregation Design Wizard uses the object counts to estimate storage requirements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3894a-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="3894a-105">Options</span></span>  
 <span data-ttu-id="3894a-106">**Cubeobjekte**</span><span class="sxs-lookup"><span data-stu-id="3894a-106">**Cube Objects**</span></span>  
 <span data-ttu-id="3894a-107">Zeigt die Dimensionen und Attribute im Cube an.</span><span class="sxs-lookup"><span data-stu-id="3894a-107">Displays the dimensions and attributes in the cube.</span></span> <span data-ttu-id="3894a-108">Es werden nur die Attribute `AggregationUsage` angezeigt, deren-Eigenschaft `None` auf der Seite **Aggregations Verwendung überprüfen** des Assistenten nicht auf festgelegt ist, da dies die einzigen Attribute sind, für die die Anzahl angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="3894a-108">Only the attributes that do not have their `AggregationUsage` property set to `None` in the **Review Aggregation Usage** page of the wizard are shown, because those are the only attributes that require the counts to be specified.</span></span>  
  
 <span data-ttu-id="3894a-109">**Geschätzte Anzahl**</span><span class="sxs-lookup"><span data-stu-id="3894a-109">**Estimated count**</span></span>  
 <span data-ttu-id="3894a-110">Zeigt die geschätzte Anzahl der Zeilen in der Measuregruppe sowie die geschätzte Anzahl der Attributelemente in den Datenbankdimensionen an.</span><span class="sxs-lookup"><span data-stu-id="3894a-110">Displays the estimated number of rows in the measure group and the estimated attribute member counts in the database dimensions.</span></span> <span data-ttu-id="3894a-111">Sie können einen Wert eingeben, der als geschätzte Anzahl verwendet werden soll, oder die Werte für die geschätzte Anzahl berechnen.</span><span class="sxs-lookup"><span data-stu-id="3894a-111">You can type a value to use as the estimated count or you can calculate the estimated count values.</span></span> <span data-ttu-id="3894a-112">Um die Anzahl Werte zu berechnen, geben `0` Sie in das Feld ein, und klicken Sie dann auf **count**.</span><span class="sxs-lookup"><span data-stu-id="3894a-112">To calculate the count values, type `0` in the field and then click **Count**.</span></span> <span data-ttu-id="3894a-113">Felder, in denen bereits eine Anzahl angezeigt wird, werden nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3894a-113">Fields that already display a count are not updated.</span></span>  
  
 <span data-ttu-id="3894a-114">**Anzahl von Partitionen**</span><span class="sxs-lookup"><span data-stu-id="3894a-114">**Partition count**</span></span>  
 <span data-ttu-id="3894a-115">(Optional) Geben Sie die geschätzte Anzahl von Zeilen in der Measuregruppe sowie die geschätzte Anzahl von Attributelementen in den Partitionen ein.</span><span class="sxs-lookup"><span data-stu-id="3894a-115">(Optional) Type the estimated number of rows in the measure group and type the estimated attribute member counts in the partitions.</span></span>  
  
 <span data-ttu-id="3894a-116">**Count**</span><span class="sxs-lookup"><span data-stu-id="3894a-116">**Count**</span></span>  
 <span data-ttu-id="3894a-117">Berechnet und füllt für alle leeren Felder die Werte in der Spalte **Geschätzte Anzahl** neu.</span><span class="sxs-lookup"><span data-stu-id="3894a-117">Calculates and repopulates the values in the **Estimated count** column for all empty fields.</span></span> <span data-ttu-id="3894a-118">Felder, in denen bereits eine Anzahl angezeigt wird, werden nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3894a-118">Fields that already display a count are not updated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3894a-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3894a-119">See Also</span></span>  
 <span data-ttu-id="3894a-120">[Aggregations Entwurfs-Assistent F1-Hilfe](aggregation-design-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="3894a-120">[Aggregation Design Wizard F1 Help](aggregation-design-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="3894a-121">Analysis Services Assistenten &#40;Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="3894a-121">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
