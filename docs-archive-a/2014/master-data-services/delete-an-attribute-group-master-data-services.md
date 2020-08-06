---
title: Löschen einer Attributgruppe (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting attribute groups [Master Data Services]
- attribute groups [Master Data Services], deleting
ms.assetid: f915e89b-629d-4725-aea6-a7f051978244
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 833c5cf327034b25d68af123a1fc134372bd6f10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622185"
---
# <a name="delete-an-attribute-group-master-data-services"></a><span data-ttu-id="02518-102">Löschen einer Attributgruppe (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="02518-102">Delete an Attribute Group (Master Data Services)</span></span>
  <span data-ttu-id="02518-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Sie eine Attributgruppe löschen, wenn die Registerkarte nicht länger im Funktionsbereich **Explorer** von [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]angezeigt werden muss.</span><span class="sxs-lookup"><span data-stu-id="02518-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an attribute group when you no longer need the tab to display in the **Explorer** functional area of [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)].</span></span>  
  
-   <span data-ttu-id="02518-104">**Hinweis** Wenn Attributgruppen vorhanden sind, werden Attribute, die keiner Attributgruppe angehören, in **Explorer**nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="02518-104">**Note** When attribute groups exist, attributes that do not belong to an attribute group are not displayed in **Explorer**.</span></span> <span data-ttu-id="02518-105">Wenn keine Attributgruppen vorhanden sind, werden alle Attribute angezeigt.</span><span class="sxs-lookup"><span data-stu-id="02518-105">When no attribute groups exist, all attributes are displayed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="02518-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="02518-106">Prerequisites</span></span>  
 <span data-ttu-id="02518-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="02518-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="02518-108">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="02518-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="02518-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="02518-109">You must be a model administrator.</span></span> <span data-ttu-id="02518-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="02518-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-attribute-group"></a><span data-ttu-id="02518-111">So löschen Sie eine Attributgruppe</span><span class="sxs-lookup"><span data-stu-id="02518-111">To delete an attribute group</span></span>  
  
1.  <span data-ttu-id="02518-112">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="02518-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="02518-113">Zeigen Sie auf der Seite **Modell Ansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Attribut Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="02518-113">On the **Model View** page, from the menu bar, point to **Manage** and click **Attribute Groups**.</span></span>  
  
3.  <span data-ttu-id="02518-114">Wählen Sie aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="02518-114">From the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="02518-115">Wählen Sie aus der Liste **Entität** eine Entität aus.</span><span class="sxs-lookup"><span data-stu-id="02518-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="02518-116">Klicken Sie auf das Pluszeichen, um **Blatt Gruppen**, **konsolidierte Gruppen**oder Auflistungs **Gruppen**zu erweitern, je nach dem Typ der Gruppe, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="02518-116">Click the plus sign to expand **Leaf Groups**, **Consolidated Groups**, or **Collection Groups**, depending on the type of group you want to delete.</span></span>  
  
6.  <span data-ttu-id="02518-117">Klicken Sie auf die Attributgruppe, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="02518-117">Click the attribute group you want to delete.</span></span>  
  
7.  <span data-ttu-id="02518-118">Klicken Sie auf **ausgewählte Gruppe löschen**.</span><span class="sxs-lookup"><span data-stu-id="02518-118">Click **Delete selected group**.</span></span>  
  
8.  <span data-ttu-id="02518-119">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="02518-119">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="02518-120">Klicken Sie im zusätzlichen Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="02518-120">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02518-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="02518-121">See Also</span></span>  
 <span data-ttu-id="02518-122">[Attribut Gruppen &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="02518-122">[Attribute Groups &#40;Master Data Services&#41;](../../2014/master-data-services/attribute-groups-master-data-services.md) </span></span>  
 [<span data-ttu-id="02518-123">Erstellen einer Attributgruppe &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="02518-123">Create an Attribute Group &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-an-attribute-group-master-data-services.md)  
  
  
