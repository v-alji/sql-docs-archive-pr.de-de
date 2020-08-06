---
title: Tabellen und Sichten auswählen (Datenquellen Sicht-Assistent) (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.datasourceviewwizard.selecttablesandviews.f1
ms.assetid: ea7d1232-f213-46e9-90d9-0fd616ca003d
author: minewiskan
ms.author: owend
ms.openlocfilehash: ac7159255ef526d871ed8906fc873d9f16d2eb64
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723153"
---
# <a name="select-tables-and-views-data-source-view-wizard-analysis-services"></a><span data-ttu-id="8ad55-102">Tabellen und Sichten auswählen (Datenquellensicht-Assistent) (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="8ad55-102">Select Tables and Views (Data Source View Wizard) (Analysis Services)</span></span>
  <span data-ttu-id="8ad55-103">Mithilfe der Seite **Tabellen und Sichten auswählen** können Sie die Tabellen und Sichten aus der Datenquelle auswählen, die Sie in die Datenquellensicht aufnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="8ad55-103">Use the **Select Tables and Views** page to select the tables or views from the data source that you want to include in the data source view.</span></span>  
  
## <a name="options"></a><span data-ttu-id="8ad55-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="8ad55-104">Options</span></span>  
 <span data-ttu-id="8ad55-105">**Available objects**</span><span class="sxs-lookup"><span data-stu-id="8ad55-105">**Available objects**</span></span>  
 <span data-ttu-id="8ad55-106">Führt die Tabellen und Sichten im Datenquellenschema auf.</span><span class="sxs-lookup"><span data-stu-id="8ad55-106">Lists the tables and views in the data source schema.</span></span> <span data-ttu-id="8ad55-107">Wenn mehr als ein Schema aufgeführt ist, erhält der Name jedes Objekts den Schemanamen als Präfix.</span><span class="sxs-lookup"><span data-stu-id="8ad55-107">The schema name prefixes the name of every object if more than one schema is listed.</span></span> <span data-ttu-id="8ad55-108">Bei nur einem aufgeführten Schema wird der Name des Schemas nicht als Präfix für die Objektnamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="8ad55-108">If only one schema is listed, the schema's name does not prefix the object names.</span></span>  
  
 <span data-ttu-id="8ad55-109">Zum erneuten Ordnen der Liste in aufsteigender oder absteigender Reihenfolge klicken Sie entweder auf **Name** oder auf **Typ**.</span><span class="sxs-lookup"><span data-stu-id="8ad55-109">To reorder the list in ascending or descending order, click either **Name** or **Type**.</span></span>  
  
 <span data-ttu-id="8ad55-110">**Included objects**</span><span class="sxs-lookup"><span data-stu-id="8ad55-110">**Included objects**</span></span>  
 <span data-ttu-id="8ad55-111">Führt die in die Datenquellensicht einzuschließenden Tabellen und Sichten auf.</span><span class="sxs-lookup"><span data-stu-id="8ad55-111">Lists the tables and views to include in the data source view.</span></span>  
  
 <span data-ttu-id="8ad55-112">Zum erneuten Ordnen der Liste in aufsteigender oder absteigender Reihenfolge klicken Sie entweder auf **Name** oder auf **Typ**.</span><span class="sxs-lookup"><span data-stu-id="8ad55-112">To reorder the list in ascending or descending order, click either **Name** or **Type**.</span></span>  
  
 <span data-ttu-id="8ad55-113">**Filter**</span><span class="sxs-lookup"><span data-stu-id="8ad55-113">**Filter**</span></span>  
 <span data-ttu-id="8ad55-114">Filtert die unter **Verfügbare Objekte**aufgeführten Objekte.</span><span class="sxs-lookup"><span data-stu-id="8ad55-114">Filters the objects listed under **Available objects**.</span></span> <span data-ttu-id="8ad55-115">Geben Sie eine Zeichenfolge ein, und klicken Sie dann auf **Filtern** , um nur die Namen anzuzeigen, die die angegebene Zeichenfolge enthalten.</span><span class="sxs-lookup"><span data-stu-id="8ad55-115">Type a string, and then click **Filter** to list only the names that contain a specified string.</span></span> <span data-ttu-id="8ad55-116">Zum Auffinden einer genauen Zeichenfolge schließen Sie die Zeichenfolge in doppelte Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="8ad55-116">To find an exact string of characters, enclose the string between double quotation marks.</span></span> <span data-ttu-id="8ad55-117">Der Filter unterscheidet nicht zwischen Groß- und Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="8ad55-117">The filter is not case sensitive.</span></span>  
  
 <span data-ttu-id="8ad55-118">Sie können die in der folgenden Tabelle aufgeführten Platzhalterzeichen an beliebiger Stelle in der Filterzeichenfolge verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ad55-118">You can include the wildcard characters listed in the following table anywhere in the filter string.</span></span>  
  
|<span data-ttu-id="8ad55-119">Platzhalter</span><span class="sxs-lookup"><span data-stu-id="8ad55-119">Wildcard character</span></span>|<span data-ttu-id="8ad55-120">Wert</span><span class="sxs-lookup"><span data-stu-id="8ad55-120">Value</span></span>|  
|------------------------|-----------|  
|**\***|<span data-ttu-id="8ad55-121">Beliebige Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8ad55-121">Any string of characters</span></span>|  
|**%**|<span data-ttu-id="8ad55-122">Beliebige Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8ad55-122">Any string of characters</span></span>|  
|<span data-ttu-id="8ad55-123">**?**</span><span class="sxs-lookup"><span data-stu-id="8ad55-123">**?**</span></span>|<span data-ttu-id="8ad55-124">Ein einzelnes Zeichen</span><span class="sxs-lookup"><span data-stu-id="8ad55-124">A single character</span></span>|  
|<span data-ttu-id="8ad55-125">**"** *Zeichenfolge* **"**</span><span class="sxs-lookup"><span data-stu-id="8ad55-125">**"** *string* **"**</span></span>|<span data-ttu-id="8ad55-126">Eine Literalzeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="8ad55-126">A literal string of characters.</span></span> <span data-ttu-id="8ad55-127">Dieses Platzhalterzeichen entspricht jeder Teilzeichenfolge innerhalb des Objektnamens.</span><span class="sxs-lookup"><span data-stu-id="8ad55-127">This wildcard character will match any substring within the object name.</span></span>|  
  
 <span data-ttu-id="8ad55-128">**Systemobjekte anzeigen**</span><span class="sxs-lookup"><span data-stu-id="8ad55-128">**Show system objects**</span></span>  
 <span data-ttu-id="8ad55-129">Zeigt unter **Verfügbare Objekte**Systemobjekte an.</span><span class="sxs-lookup"><span data-stu-id="8ad55-129">Displays system objects under **Available objects**.</span></span> <span data-ttu-id="8ad55-130">Diese Option steht nur zur Verfügung, wenn der Datenquellenanbieter Systemobjekte verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="8ad55-130">This option is available only if the data source provider exposes system objects.</span></span> <span data-ttu-id="8ad55-131">Durch das Entfernen eines Systemobjekts aus der Liste **Eingeschlossene Objekte** wird diese Option automatisch ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="8ad55-131">Removing a system object from the **Included objects** list automatically selects this option.</span></span>  
  
 <span data-ttu-id="8ad55-132">**Add related tables**</span><span class="sxs-lookup"><span data-stu-id="8ad55-132">**Add related tables**</span></span>  
 <span data-ttu-id="8ad55-133">Fügt alle Tabellen hinzu, die mit den unter **Eingeschlossene Objekte**aufgeführten verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="8ad55-133">Adds all the tables that are related to those listed under **Included objects**.</span></span> <span data-ttu-id="8ad55-134">Mit dieser Option können keine Sichten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8ad55-134">This option does not add views.</span></span> <span data-ttu-id="8ad55-135">Das Hinzufügen partitionierter Tabellen ist mithilfe dieser Option jedoch möglich.</span><span class="sxs-lookup"><span data-stu-id="8ad55-135">However, this option does add partitioned tables.</span></span> <span data-ttu-id="8ad55-136">Wenn Sie auf der Seite **Namensübereinstimmung** des Assistenten Kriterien für die Namensübereinstimmung auswählen, schließt diese Option auch logisch verknüpfte Tabellen entsprechend der von Ihnen ausgewählten Kriterien ein.</span><span class="sxs-lookup"><span data-stu-id="8ad55-136">If you select name-matching criteria on the **Name Matching** page of the wizard, this option also includes logically related tables according to the criteria you select.</span></span> <span data-ttu-id="8ad55-137">Tabellen werden auch eingeschlossen, wenn sie mit den neu hinzugefügten verknüpften Tabellen verknüpft sind und wenn sie eine identische Struktur wie die ursprüngliche Tabelle haben.</span><span class="sxs-lookup"><span data-stu-id="8ad55-137">Tables are also included if they are related to the newly added related tables, and if they have an identical structure to the original table.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ad55-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8ad55-138">See Also</span></span>  
 <span data-ttu-id="8ad55-139">[Datenquellen Sicht-Assistent (F1-Hilfe &#40;Analysis Services&#41;](data-source-view-wizard-f1-help-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="8ad55-139">[Data Source View Wizard F1 Help &#40;Analysis Services&#41;](data-source-view-wizard-f1-help-analysis-services.md) </span></span>  
 [<span data-ttu-id="8ad55-140">Datenquellsichten in mehrdimensionalen Modellen</span><span class="sxs-lookup"><span data-stu-id="8ad55-140">Data Source Views in Multidimensional Models</span></span>](multidimensional-models/data-source-views-in-multidimensional-models.md)  
  
  
