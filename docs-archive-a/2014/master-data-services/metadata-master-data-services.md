---
title: Metadaten (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/19/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- user-defined metadata [Master Data Services], about user-defined metadata
- metadata [Master Data Services], about metadata
- metadata [Master Data Services]
- user-defined metadata [Master Data Services]
ms.assetid: ac1aabe3-d8d4-4d7a-8954-50ee3c185d81
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 39ab95b7925306febb551962495da7ec9751589b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698403"
---
# <a name="metadata-master-data-services"></a><span data-ttu-id="ef7f4-102">Metadaten (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ef7f4-102">Metadata (Master Data Services)</span></span>
  <span data-ttu-id="ef7f4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] handelt es sich bei benutzerdefinierten Metadaten um Informationen, mit denen Sie die Modellobjekte beschreiben.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], user-defined metadata is information that you use to describe model objects.</span></span> <span data-ttu-id="ef7f4-104">Sie möchten z. B. die Besitzer eines bestimmten Modells oder einer Entität oder die Quellsysteme verfolgen, die Daten für eine Entität bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-104">For example, you may want to track the owners of a particular model or entity, or track the source systems that supply data to an entity.</span></span>  
  
 <span data-ttu-id="ef7f4-105">Benutzerdefinierte Metadaten werden von einem Modell verwaltet, das als **Metadaten**bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-105">User-defined metadata is managed by a model called **Metadata**.</span></span> <span data-ttu-id="ef7f4-106">Dieses Modell wird bei der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Installation von automatisch eingeschlossen und ähnelt allen anderen MDS-Modellen, mit dem Unterschied, dass Sie keine Versionen erstellen können.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-106">This model is automatically included when [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] is installed, and it is similar to all other MDS models, except that you cannot create versions of it.</span></span>  
  
 <span data-ttu-id="ef7f4-107">Nach dem Ausfüllen des Metadatenmodells mit benutzerdefinierten Metadaten können Sie sie in Abonnementsichten einfügen, damit sie von abonnierenden Systemen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-107">After you populate the Metadata model with user-defined metadata, you can include it in subscription views, so it can be consumed by subscribing systems.</span></span>  
  
## <a name="metadata-entities"></a><span data-ttu-id="ef7f4-108">Metadatenentitäten</span><span class="sxs-lookup"><span data-stu-id="ef7f4-108">Metadata Entities</span></span>  
 <span data-ttu-id="ef7f4-109">Das Modell Metadaten umfasst fünf Entitäten, von denen jede einen Typ eines Masterdaten-Modellobjekts darstellt, das benutzerdefinierte Metadaten unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-109">The Metadata model includes five entities, each of which represents a type of master data model object that supports user-defined metadata.</span></span> <span data-ttu-id="ef7f4-110">Beispielsweise enthält die **Definition der modellmetadatendefinition** Elemente, die Modelle darstellen, und die **Attribut Metadaten-Definitions** Entität verfügt über Member, die alle Attribute in allen Modellen darstellen.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-110">For example, the **Model Metadata Definition** entity contains members that represent models, and the **Attribute Metadata Definition** entity has members that represent all attributes in all models.</span></span>  
  
 <span data-ttu-id="ef7f4-111">Um Metadaten für ein Modellobjekt zu definieren, füllen Sie die Attribute eines dieser Elemente auf.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-111">To define metadata for a model object, you populate one of these member's attributes.</span></span> <span data-ttu-id="ef7f4-112">Beispielsweise können Sie in der Entität **Entitäts-Metadatendefinition** das Beschreibungs Attribut des Price-Members mit dem Text Auffüllen: **dem Produkt Preis, wenn er an einen Kunden verkauft**wird.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-112">For example, in the **Entity Metadata Definition** entity, you can populate the Price member's Description attribute with the text: **The product price when sold to a customer**.</span></span>  
  
 <span data-ttu-id="ef7f4-113">Die Elemente im Metadatenmodell werden automatisch immer dann aktualisiert, wenn Modellobjekte, die benutzerdefinierte Metadaten unterstützen, hinzugefügt oder gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-113">The members in the Metadata model are automatically updated whenever model objects that support user-defined metadata are added or deleted.</span></span>  
  
 <span data-ttu-id="ef7f4-114">Das Metadatenmodell darf nicht versionsspezifisch sein, über hinzugefügte oder geänderte Versionsflags verfügen oder als Modellbereitstellungspaket gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-114">The Metadata model cannot be versioned, have version flags added or changed, or be saved as a model deployment package.</span></span> <span data-ttu-id="ef7f4-115">Es hat ansonsten jedoch die gleiche vollständige Funktionalität anderer Masterdatenmodelle.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-115">However, it has all the same other functionality available to other master data models.</span></span> <span data-ttu-id="ef7f4-116">Sie könnten z. B. auf dem Metadatenmodell einen Satz von Geschäftsregeln implementieren, um Datenrichtlinien zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-116">For example, you might implement a set of business rules on the Metadata model to enforce data policies.</span></span>  
  
## <a name="customizing-your-metadata-model"></a><span data-ttu-id="ef7f4-117">Anpassen des Metadatenmodells</span><span class="sxs-lookup"><span data-stu-id="ef7f4-117">Customizing Your Metadata Model</span></span>  
 <span data-ttu-id="ef7f4-118">Jede Metadaten-Definitionsentität schließt die Attribute Name, Code und Description ein.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-118">Each metadata definition entity includes Name, Code, and Description attributes.</span></span> <span data-ttu-id="ef7f4-119">Sie möchten möglicherweise zusätzliche Attribute erstellen, um die Modellobjekte weiter zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-119">You may want to create additional attributes to further describe your model objects.</span></span>  
  
 <span data-ttu-id="ef7f4-120">Sie könnten z. B. erstellen:</span><span class="sxs-lookup"><span data-stu-id="ef7f4-120">For example, you might create:</span></span>  
  
-   <span data-ttu-id="ef7f4-121">Ein domänenbasiertes Attribut mit dem Namen "Besitzer", mit dem Sie den Besitzer jedes Modellobjekts verfolgen.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-121">A domain-based attribute named Owner, which you use to track the owner of each model object.</span></span>  
  
-   <span data-ttu-id="ef7f4-122">Ein Freiformattribut mit dem Namen "Datum der letzten Überprüfung", mit dem Sie das Datum verfolgen, an dem ein Objekt zuletzt vom Besitzer überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-122">A free-form attribute named Last Review Date, which you use to track the date that an object was last reviewed by the owner.</span></span>  
  
-   <span data-ttu-id="ef7f4-123">Ein domänenbasiertes Attribut mit dem Namen sources, das Sie zum Nachverfolgen und Verwalten der Quell Systeme verwenden, die mit der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Instanz interagieren.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-123">A domain-based attribute named Sources, which you use to track and manage the source systems that interact with the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] instance.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="ef7f4-124">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="ef7f4-124">Related Tasks</span></span>  
  
|<span data-ttu-id="ef7f4-125">Taskbeschreibung</span><span class="sxs-lookup"><span data-stu-id="ef7f4-125">Task Description</span></span>|<span data-ttu-id="ef7f4-126">Thema</span><span class="sxs-lookup"><span data-stu-id="ef7f4-126">Topic</span></span>|  
|----------------------|-----------|  
|<span data-ttu-id="ef7f4-127">Fügen Sie einem Modellobjekt Metadaten hinzu.</span><span class="sxs-lookup"><span data-stu-id="ef7f4-127">Add metadata to a model object.</span></span>|[<span data-ttu-id="ef7f4-128">Metadaten &#40;Master Data Services hinzufügen&#41;</span><span class="sxs-lookup"><span data-stu-id="ef7f4-128">Add Metadata &#40;Master Data Services&#41;</span></span>](add-metadata-master-data-services.md)
|&nbsp;|&nbsp;|
  
## <a name="related-content"></a><span data-ttu-id="ef7f4-129">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="ef7f4-129">Related Content</span></span>  
  
-   [<span data-ttu-id="ef7f4-130">Daten &#40;Master Data Services werden exportiert&#41;</span><span class="sxs-lookup"><span data-stu-id="ef7f4-130">Exporting Data &#40;Master Data Services&#41;</span></span>](overview-exporting-data-master-data-services.md)  
  
  
