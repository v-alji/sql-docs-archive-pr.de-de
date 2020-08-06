---
title: Löschen einer Geschäftsregel (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- deleting business rules [Master Data Services]
- business rules [Master Data Services], deleting
ms.assetid: b97aa4f9-569f-451d-ad62-65b81f980299
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 8e6db486f71634cf025c57eabbedeeb9efdbc437
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695774"
---
# <a name="delete-a-business-rule-master-data-services"></a><span data-ttu-id="e89a7-102">Löschen einer Geschäftsregel (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="e89a7-102">Delete a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="e89a7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Sie eine Geschäftsregel löschen, die Sie nicht mehr benötigen.</span><span class="sxs-lookup"><span data-stu-id="e89a7-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], delete a business rule when it is no longer needed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e89a7-104">Sie können die Überprüfung von Daten anhand einer Geschäftsregel unterbinden, indem Sie die Geschäftsregel ausschließen, anstatt sie zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e89a7-104">You can prevent data from being validated against a business rule by excluding it, rather than deleting it.</span></span> <span data-ttu-id="e89a7-105">Weitere Informationen finden Sie unter [Ausschließen einer Geschäftsregel &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e89a7-105">For more information, see [Exclude a Business Rule &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="e89a7-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e89a7-106">Prerequisites</span></span>  
 <span data-ttu-id="e89a7-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="e89a7-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="e89a7-108">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="e89a7-108">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="e89a7-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="e89a7-109">You must be a model administrator.</span></span> <span data-ttu-id="e89a7-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="e89a7-110">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
### <a name="to-delete-a-business-rule"></a><span data-ttu-id="e89a7-111">So löschen Sie eine Geschäftsregel</span><span class="sxs-lookup"><span data-stu-id="e89a7-111">To delete a business rule</span></span>  
  
1.  <span data-ttu-id="e89a7-112">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="e89a7-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="e89a7-113">Zeigen Sie auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Geschäftsregeln**.</span><span class="sxs-lookup"><span data-stu-id="e89a7-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="e89a7-114">Wählen Sie auf der Seite **Verwaltung von Geschäftsregeln** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="e89a7-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="e89a7-115">Wählen Sie aus der Liste **Entität** eine Entität aus.</span><span class="sxs-lookup"><span data-stu-id="e89a7-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="e89a7-116">Wählen Sie aus der Liste **Elementtyp** einen Typ des Elements aus, auf das die Geschäftsregel angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e89a7-116">From the **Member Type** list, select a type of member for the business rule to apply to.</span></span>  
  
6.  <span data-ttu-id="e89a7-117">Wählen Sie aus der Liste **Attribut** ein Attribut aus, oder behalten Sie die Standardeinstellung **Alle**bei.</span><span class="sxs-lookup"><span data-stu-id="e89a7-117">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="e89a7-118">Klicken Sie im Raster auf die Zeile der Geschäftsregel, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="e89a7-118">In the grid, click the row for the business rule you want to delete.</span></span>  
  
8.  <span data-ttu-id="e89a7-119">Klicken Sie auf **ausgewählte Geschäftsregel löschen**.</span><span class="sxs-lookup"><span data-stu-id="e89a7-119">Click **Delete selected business rule**.</span></span>  
  
9. <span data-ttu-id="e89a7-120">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e89a7-120">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="e89a7-121">Der Wert in der Spalte **Status** lautet **Lösch**Vorgang steht aus.</span><span class="sxs-lookup"><span data-stu-id="e89a7-121">The value in the **Status** column is **Deletion pending**.</span></span>  
  
10. <span data-ttu-id="e89a7-122">Klicken Sie auf **Geschäftsregeln veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="e89a7-122">Click **Publish business rules**.</span></span>  
  
11. <span data-ttu-id="e89a7-123">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e89a7-123">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e89a7-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e89a7-124">See Also</span></span>  
 <span data-ttu-id="e89a7-125">[Ausschließen einer Geschäftsregel &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e89a7-125">[Exclude a Business Rule &#40;Master Data Services&#41;](exclude-a-business-rule-master-data-services.md) </span></span>  
 <span data-ttu-id="e89a7-126">[Erstellen und Veröffentlichen einer Geschäftsregel &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="e89a7-126">[Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span></span>  
 [<span data-ttu-id="e89a7-127">Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="e89a7-127">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
