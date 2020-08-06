---
title: Modelle (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- models [Master Data Services], about models
- models [Master Data Services]
ms.assetid: 9f862a3d-25ab-41e9-b833-1db99959e825
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 1d5a4a431d3ca7b6fa499de68a2bc4c5033cd086
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622174"
---
# <a name="models-master-data-services"></a><span data-ttu-id="1ea56-102">Modelle (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="1ea56-102">Models (Master Data Services)</span></span>
  <span data-ttu-id="1ea56-103">Modelle stellen die höchste Ebene der Datenorganisation in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]dar.</span><span class="sxs-lookup"><span data-stu-id="1ea56-103">Models are the highest level of data organization in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)].</span></span> <span data-ttu-id="1ea56-104">Ein Modell definiert die Struktur der Daten in der Masterdaten-Verwaltungslösung.</span><span class="sxs-lookup"><span data-stu-id="1ea56-104">A model defines the structure of data in your master data management solution.</span></span> <span data-ttu-id="1ea56-105">Ein Modell enthält die folgenden Objekte:</span><span class="sxs-lookup"><span data-stu-id="1ea56-105">A model contains the following objects:</span></span>  
  
-   <span data-ttu-id="1ea56-106">Entitäten</span><span class="sxs-lookup"><span data-stu-id="1ea56-106">Entities</span></span>  
  
-   <span data-ttu-id="1ea56-107">Attribute und Attributgruppen</span><span class="sxs-lookup"><span data-stu-id="1ea56-107">Attributes and attribute groups</span></span>  
  
-   <span data-ttu-id="1ea56-108">Explizite und abgeleitete Hierarchien</span><span class="sxs-lookup"><span data-stu-id="1ea56-108">Explicit and derived hierarchies</span></span>  
  
-   <span data-ttu-id="1ea56-109">Sammlungen</span><span class="sxs-lookup"><span data-stu-id="1ea56-109">Collections</span></span>  
  
 <span data-ttu-id="1ea56-110">In Modellen wird die Struktur der Masterdaten organisiert.</span><span class="sxs-lookup"><span data-stu-id="1ea56-110">Models organize the structure of your master data.</span></span> <span data-ttu-id="1ea56-111">Ihre [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] -Implementierung kann über ein Modell oder viele Modelle verfügen, von denen jedes Daten ähnlichen Typs gruppiert.</span><span class="sxs-lookup"><span data-stu-id="1ea56-111">Your [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] implementation can have one or many models that each group similar kinds of data.</span></span> <span data-ttu-id="1ea56-112">Die Masterdaten werden im Allgemeinen in vier Kategorien unterteilt: Personen, Orte, Gegenstände oder Begriffe.</span><span class="sxs-lookup"><span data-stu-id="1ea56-112">In general, master data can be categorized in one of four ways: people, places, things, or concepts.</span></span> <span data-ttu-id="1ea56-113">Sie können z. B. ein Produktmodell erstellen, das produktbezogene Daten enthält, oder ein Kundenmodell, das kundenbezogene Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="1ea56-113">For example, you can create a Product model to contain product-related data or a Customer model to contain customer-related data.</span></span>  
  
 <span data-ttu-id="1ea56-114">Sie können Benutzern und Gruppen Berechtigungen für die Anzeige und Aktualisierung von Objekten innerhalb des Modells zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1ea56-114">You can assign users and groups permission to view and update objects within the model.</span></span> <span data-ttu-id="1ea56-115">Wenn Sie keine Berechtigung für das Modell gewähren, wird es nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ea56-115">If you do not give permission to the model, it is not displayed.</span></span>  
  
 <span data-ttu-id="1ea56-116">Zu einem beliebigen Zeitpunkt können Sie Kopien der Masterdaten innerhalb eines Modells erstellen.</span><span class="sxs-lookup"><span data-stu-id="1ea56-116">At any given time, you can create copies of the master data within a model.</span></span> <span data-ttu-id="1ea56-117">Diese Kopien werden als Versionen bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="1ea56-117">These copies are called versions.</span></span>  
  
 <span data-ttu-id="1ea56-118">Nachdem Sie ein Modell in einer Testumgebung definiert haben, können Sie es mit oder ohne die entsprechenden Daten von der Testumgebung aus in einer Produktionsumgebung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1ea56-118">When you have defined a model in a test environment, you can deploy it, with or without the corresponding data, from the test environment to a production environment.</span></span> <span data-ttu-id="1ea56-119">Auf diese Weise erübrigt sich die Neuerstellung der Modelle in der Produktionsumgebung.</span><span class="sxs-lookup"><span data-stu-id="1ea56-119">This eliminates the need to recreate your models in your production environment.</span></span>  
  
## <a name="how-models-relate-to-other-objects"></a><span data-ttu-id="1ea56-120">Zusammenhang zwischen Modellen und anderen Objekten</span><span class="sxs-lookup"><span data-stu-id="1ea56-120">How Models Relate to Other Objects</span></span>  
 <span data-ttu-id="1ea56-121">Ein Modell enthält Entitäten.</span><span class="sxs-lookup"><span data-stu-id="1ea56-121">A model contains entities.</span></span> <span data-ttu-id="1ea56-122">Entitäten enthalten Attribute, explizite Hierarchien und Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="1ea56-122">Entities contain attributes, explicit hierarchies, and collections.</span></span> <span data-ttu-id="1ea56-123">Attribute können in Attributgruppen enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="1ea56-123">Attributes can be contained in attribute groups.</span></span> <span data-ttu-id="1ea56-124">Domänenbasierte Attributesind vorhanden, wenn eine Entität für eine andere Entität als Attribut verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1ea56-124">Domain-based attributes exist when an entity is used as an attribute for another entity.</span></span>  
  
 <span data-ttu-id="1ea56-125">Dieses Bild zeigt die Beziehung zwischen den Objekten in einem Modell an.</span><span class="sxs-lookup"><span data-stu-id="1ea56-125">This image shows the relationships among the objects in a model.</span></span>  
  
 <span data-ttu-id="1ea56-126">![Objekte in einem Master Data Services-Modell](../../2014/master-data-services/media/mds-conc-model-circles.gif "Objekte in einem Master Data Services-Modell")</span><span class="sxs-lookup"><span data-stu-id="1ea56-126">![Objects in a Master Data Services Model](../../2014/master-data-services/media/mds-conc-model-circles.gif "Objects in a Master Data Services Model")</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1ea56-127">Abgeleitete Hierarchien sind ebenfalls Modellobjekte, sie werden jedoch nicht im Bild angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1ea56-127">Derived hierarchies are also model objects, but they are not shown in the image.</span></span> <span data-ttu-id="1ea56-128">Abgeleitete Hierarchien werden von den domänenbasierten Attributbeziehungen abgeleitet, die zwischen Entitäten vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="1ea56-128">Derived hierarchies are derived from the domain-based attribute relationships that exist between entities.</span></span> <span data-ttu-id="1ea56-129">Weitere Informationen finden Sie unter [Abgeleitete Hierarchien &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1ea56-129">See [Derived Hierarchies &#40;Master Data Services&#41;](derived-hierarchies-master-data-services.md) for more information.</span></span>  
  
 <span data-ttu-id="1ea56-130">Masterdaten sind die Daten, die in den Modellobjekten enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="1ea56-130">Master data is the data that is contained in the model objects.</span></span> <span data-ttu-id="1ea56-131">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]werden Masterdaten als Elemente in einer Entität gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1ea56-131">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], master data is stored as members in an entity.</span></span>  
  
 <span data-ttu-id="1ea56-132">Modellobjekte werden im Funktionsbereich **Systemverwaltung** der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Benutzeroberfläche verwaltet.</span><span class="sxs-lookup"><span data-stu-id="1ea56-132">Model objects are maintained in the **System Administration** functional area of the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] user interface.</span></span>  
  
## <a name="model-example"></a><span data-ttu-id="1ea56-133">Modellbeispiel</span><span class="sxs-lookup"><span data-stu-id="1ea56-133">Model Example</span></span>  
 <span data-ttu-id="1ea56-134">Im folgenden Beispiel gruppieren die Objekte im Produktmodell logisch produktbezogene Daten.</span><span class="sxs-lookup"><span data-stu-id="1ea56-134">In the following example, the objects in the Product model logically group product-related data.</span></span>  
  
 <span data-ttu-id="1ea56-135">![Beispiel für Produktmodellmasterdaten](../../2014/master-data-services/media/mds-conc-model.gif "Beispiel für Produktmodellmasterdaten")</span><span class="sxs-lookup"><span data-stu-id="1ea56-135">![Product Model Master Data Example](../../2014/master-data-services/media/mds-conc-model.gif "Product Model Master Data Example")</span></span>  
  
 <span data-ttu-id="1ea56-136">Weitere allgemeine Modelle:</span><span class="sxs-lookup"><span data-stu-id="1ea56-136">Other common models are:</span></span>  
  
-   <span data-ttu-id="1ea56-137">Konten: Mögliche Entitäten sind Bilanzkonten, Gewinn- und Verlustrechnungen, Statistiken und Kontotyp.</span><span class="sxs-lookup"><span data-stu-id="1ea56-137">Accounts, which could include entities such as balance sheet accounts, income statement accounts, statistics, and account type.</span></span>  
  
-   <span data-ttu-id="1ea56-138">Kunde: Mögliche Entitäten sind Geschlecht, Ausbildung, Beruf und Familienstand.</span><span class="sxs-lookup"><span data-stu-id="1ea56-138">Customer, which could include entities such as gender, education, occupation, and marital status.</span></span>  
  
-   <span data-ttu-id="1ea56-139">Geografie: Mögliche Entitäten sind Postleitzahlen, Städte, Landkreise, Staaten, Provinzen, Regionen, Gebiete, Länder und Kontinente.</span><span class="sxs-lookup"><span data-stu-id="1ea56-139">Geography, which could include entities such as postal codes, cities, counties, states, provinces, regions, territories, countries, and continents.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="1ea56-140">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="1ea56-140">Related Tasks</span></span>  
  
|<span data-ttu-id="1ea56-141">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="1ea56-141">Task Description</span></span>|<span data-ttu-id="1ea56-142">Thema</span><span class="sxs-lookup"><span data-stu-id="1ea56-142">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="1ea56-143">Erstellen Sie ein Modell, um die Masterdaten zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="1ea56-143">Create a model to organize your master data.</span></span>|[<span data-ttu-id="1ea56-144">Erstellen eines Modells &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1ea56-144">Create a Model &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-model-master-data-services.md)|  
|<span data-ttu-id="1ea56-145">Ändern Sie den Namen eines vorhandenen Modells.</span><span class="sxs-lookup"><span data-stu-id="1ea56-145">Change the name of an existing model.</span></span>|[<span data-ttu-id="1ea56-146">Ändern eines Modell namens &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1ea56-146">Change a Model Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-model-name-master-data-services.md)|  
|<span data-ttu-id="1ea56-147">Löschen Sie ein vorhandenes Modell.</span><span class="sxs-lookup"><span data-stu-id="1ea56-147">Delete an existing model.</span></span>|[<span data-ttu-id="1ea56-148">Löschen eines Modells &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1ea56-148">Delete a Model &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/delete-a-model-master-data-services.md)|  
  
## <a name="related-content"></a><span data-ttu-id="1ea56-149">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="1ea56-149">Related Content</span></span>  
  
-   [<span data-ttu-id="1ea56-150">Übersicht über Master Data Services</span><span class="sxs-lookup"><span data-stu-id="1ea56-150">Master Data Services Overview</span></span>](master-data-services-overview-mds.md)  
  
-   [<span data-ttu-id="1ea56-151">Entitäten &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1ea56-151">Entities &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/entities-master-data-services.md)  
  
-   [<span data-ttu-id="1ea56-152">Attribute &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1ea56-152">Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/attributes-master-data-services.md)  
  
-   [<span data-ttu-id="1ea56-153">Bereitstellen von Modellen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1ea56-153">Deploying Models &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/deploying-models-master-data-services.md)  
  
-   [<span data-ttu-id="1ea56-154">Berechtigungen für Modellobjekte &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1ea56-154">Model Object Permissions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/model-object-permissions-master-data-services.md)  
  
  
