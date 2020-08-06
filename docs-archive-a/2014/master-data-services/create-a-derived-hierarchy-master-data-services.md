---
title: Erstellen einer abgeleiteten Hierarchie (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- derived hierarchies, creating
- creating derived hierarchies [Master Data Services]
ms.assetid: fec653c4-11cc-46a2-8dd8-b605341ebb40
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 20469ad30222e43a3104503cc32187c2e6512743
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701258"
---
# <a name="create-a-derived-hierarchy-master-data-services"></a><span data-ttu-id="5a0c1-102">Erstellen einer abgeleiteten Hierarchie (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5a0c1-102">Create a Derived Hierarchy (Master Data Services)</span></span>
  <span data-ttu-id="5a0c1-103">Erstellen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eine abgeleitete Hierarchie, wenn Sie eine ebenenbasierte Hierarchie möchten, die sicherstellt, dass sich die Elemente auf der richtigen Ebene befinden.</span><span class="sxs-lookup"><span data-stu-id="5a0c1-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a derived hierarchy when you want a level-based hierarchy that ensures that members exist at the correct level.</span></span> <span data-ttu-id="5a0c1-104">Abgeleitete Hierarchien basieren auf den domänenbasierten Attributbeziehungen, die in einem Modell vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="5a0c1-104">Derived hierarchies are based on the domain-based attribute relationships that exist in a model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="5a0c1-105">Wenn ein domänenbasierter Attributwert für ein Element nicht vorhanden ist, ist das Element nicht in der abgeleiteten Hierarchie enthalten.</span><span class="sxs-lookup"><span data-stu-id="5a0c1-105">If a domain-based attribute value doesn't exist for a member, the member is not included in the derived hierarchy.</span></span> <span data-ttu-id="5a0c1-106">Gehen Sie auf die Seite [Erfordern von Attributwerten &#40;Master Data Services&#41;](require-attribute-values-master-data-services.md), um einen domänenbasierten Attributwert für alle Mitglieder anzufordern.</span><span class="sxs-lookup"><span data-stu-id="5a0c1-106">See [Require Attribute Values &#40;Master Data Services&#41;](require-attribute-values-master-data-services.md) to require a domain-based attribute value for all members.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5a0c1-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5a0c1-107">Prerequisites</span></span>  
 <span data-ttu-id="5a0c1-108">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="5a0c1-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5a0c1-109">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="5a0c1-109">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="5a0c1-110">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="5a0c1-110">You must be a model administrator.</span></span> <span data-ttu-id="5a0c1-111">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5a0c1-111">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-derived-hierarchy"></a><span data-ttu-id="5a0c1-112">So erstellen Sie eine abgeleitete Hierarchie</span><span class="sxs-lookup"><span data-stu-id="5a0c1-112">To create a derived hierarchy</span></span>  
  
1.  <span data-ttu-id="5a0c1-113">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="5a0c1-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="5a0c1-114">Zeigen Sie auf der Seite **Modell Ansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **abgeleitete Hierarchien**.</span><span class="sxs-lookup"><span data-stu-id="5a0c1-114">On the **Model View** page, from the menu bar, point to **Manage** and click **Derived Hierarchies**.</span></span>  
  
3.  <span data-ttu-id="5a0c1-115">Wählen Sie auf der Seite **Verwaltung abgeleiteter Hierarchien** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="5a0c1-115">On the **Derived Hierarchy Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="5a0c1-116">Klicken auf **abgeleitete Hierarchie hinzufügen**</span><span class="sxs-lookup"><span data-stu-id="5a0c1-116">Click **Add derived hierarchy**.</span></span>  
  
5.  <span data-ttu-id="5a0c1-117">Geben Sie auf der Seite **Abgeleitete Hierarchie hinzufügen** im Feld **Name der abgeleiteten Hierarchie** einen Namen für die Hierarchie ein.</span><span class="sxs-lookup"><span data-stu-id="5a0c1-117">On the **Add Derived Hierarchy** page, in the **Derived hierarchy name** box, type a name for the hierarchy.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="5a0c1-118"> Verwenden Sie einen Namen, der die Ebenen in der Hierarchie beschreibt, z. B. **Produkt-zu-Unterkategorie-zu-Kategorie**.</span><span class="sxs-lookup"><span data-stu-id="5a0c1-118">Use a name that describes the levels in the hierarchy, for example **Product to Subcategory to Category**.</span></span>  
  
6.  <span data-ttu-id="5a0c1-119">Klicken Sie auf **Abgeleitete Hierarchie speichern**.</span><span class="sxs-lookup"><span data-stu-id="5a0c1-119">Click **Save derived hierarchy**.</span></span>  
  
7.  <span data-ttu-id="5a0c1-120">Klicken Sie auf der Seite **abgeleitete Hierarchie bearbeiten** im Bereich **Verfügbare Entitäten und Hierarchien** auf eine Entität oder Hierarchie, und ziehen Sie Sie in den Bereich **aktuelle Ebenen** .</span><span class="sxs-lookup"><span data-stu-id="5a0c1-120">On the **Edit Derived Hierarchy** page, in the **Available Entities and Hierarchies** pane, click an entity or hierarchy and drag it to the **Current Levels** pane.</span></span>  
  
8.  <span data-ttu-id="5a0c1-121">Ziehen Sie Entitäten oder Hierarchien in diesen Bereich, bis die Hierarchie vollständig ist.</span><span class="sxs-lookup"><span data-stu-id="5a0c1-121">Continue dragging entities or hierarchies until your hierarchy is complete.</span></span>  
  
9. <span data-ttu-id="5a0c1-122">Klicken Sie auf **Zurück**.</span><span class="sxs-lookup"><span data-stu-id="5a0c1-122">Click **Back**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a0c1-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a0c1-123">See Also</span></span>  
 <span data-ttu-id="5a0c1-124">[Abgeleitete Hierarchien &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5a0c1-124">[Derived Hierarchies &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-master-data-services.md) </span></span>  
 <span data-ttu-id="5a0c1-125">[Abgeleitete Hierarchien mit expliziten Caps &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5a0c1-125">[Derived Hierarchies with Explicit Caps &#40;Master Data Services&#41;](../../2014/master-data-services/derived-hierarchies-with-explicit-caps-master-data-services.md) </span></span>  
 [<span data-ttu-id="5a0c1-126">Domänenbasierte Attribute &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5a0c1-126">Domain-Based Attributes &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/domain-based-attributes-master-data-services.md)  
  
  
