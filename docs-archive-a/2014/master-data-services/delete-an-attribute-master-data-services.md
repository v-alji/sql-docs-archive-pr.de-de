---
title: Löschen eines Attributs (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- attributes [Master Data Services], deleting
- deleting attributes [Master Data Services]
ms.assetid: ec3e66f7-0e35-43d7-a80d-64899948ebfe
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 96db56dac9356b1131e722fc7f6b779c93305bb7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695778"
---
# <a name="delete-an-attribute-master-data-services"></a><span data-ttu-id="d14d4-102">Löschen eines Attributs (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="d14d4-102">Delete an Attribute (Master Data Services)</span></span>
  <span data-ttu-id="d14d4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Sie ein Attribut löschen, wenn Sie das Attribut und alle zugehörigen Attributwerte dauerhaft entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="d14d4-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete an attribute when you want to permanently delete the attribute and all associated attribute values.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d14d4-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="d14d4-104">Prerequisites</span></span>  
 <span data-ttu-id="d14d4-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="d14d4-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="d14d4-106">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="d14d4-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="d14d4-107">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="d14d4-107">You must be a model administrator.</span></span> <span data-ttu-id="d14d4-108">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="d14d4-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-an-attribute"></a><span data-ttu-id="d14d4-109">So löschen Sie ein Attribut</span><span class="sxs-lookup"><span data-stu-id="d14d4-109">To delete an attribute</span></span>  
  
1.  <span data-ttu-id="d14d4-110">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="d14d4-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="d14d4-111">Zeigen Sie auf der Seite **Modellansicht** auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Entitäten**.</span><span class="sxs-lookup"><span data-stu-id="d14d4-111">On the **Model View** page, from the menu bar, point to **Manage** and click **Entities**.</span></span>  
  
3.  <span data-ttu-id="d14d4-112">Wählen Sie auf der Seite **Entitätsverwaltung** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="d14d4-112">On the **Entity Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="d14d4-113">Wählen Sie die Zeile der Entität aus, in der das zu löschende Attribut enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="d14d4-113">Select the row for the entity that contains the attribute you want to delete.</span></span>  
  
5.  <span data-ttu-id="d14d4-114">Klicken Sie auf **Ausgewählte Entität bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="d14d4-114">Click **Edit selected entity**.</span></span>  
  
6.  <span data-ttu-id="d14d4-115">Klicken Sie auf der Seite **Entität bearbeiten** auf das Attribut, das Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="d14d4-115">On the **Edit Entity** page, click the attribute you want to delete.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="d14d4-116">Das Name-Attribut und das Code-Attribut können nicht gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="d14d4-116">You cannot delete the Name or Code attributes.</span></span>  
  
7.  <span data-ttu-id="d14d4-117">Klicken Sie auf **ausgewähltes Attribut löschen**.</span><span class="sxs-lookup"><span data-stu-id="d14d4-117">Click **Delete selected attribute**.</span></span>  
  
8.  <span data-ttu-id="d14d4-118">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d14d4-118">In the confirmation dialog box, click **OK**.</span></span>  
  
9. <span data-ttu-id="d14d4-119">Klicken Sie im zusätzlichen Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d14d4-119">In the additional confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d14d4-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d14d4-120">See Also</span></span>  
 <span data-ttu-id="d14d4-121">[Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d14d4-121">[Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="d14d4-122">[Domänen basierte Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d14d4-122">[Domain-Based Attributes &#40;Master Data Services&#41;](../../2014/master-data-services/domain-based-attributes-master-data-services.md) </span></span>  
 <span data-ttu-id="d14d4-123">[Erstellen Sie ein Text Attribut &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="d14d4-123">[Create a Text Attribute &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-text-attribute-master-data-services.md) </span></span>  
 [<span data-ttu-id="d14d4-124">Erstellen eines domänenbasierten Attributs &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="d14d4-124">Create a Domain-Based Attribute &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-domain-based-attribute-master-data-services.md)  
  
  
