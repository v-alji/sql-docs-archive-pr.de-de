---
title: Ausschließen einer Geschäftsregel (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], excluding
ms.assetid: bdbc9df0-23f7-40b9-8aba-4445c1482580
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 317964dcbc7b2cbe212c415b3aa4f9f1a0743301
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699945"
---
# <a name="exclude-a-business-rule-master-data-services"></a><span data-ttu-id="5ee0d-102">Ausschließen einer Geschäftsregel (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="5ee0d-102">Exclude a Business Rule (Master Data Services)</span></span>
  <span data-ttu-id="5ee0d-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Sie eine Geschäftsregel ausschließen, die nicht zur Datenüberprüfung verwendet, aber auch nicht dauerhaft gelöscht werden soll.</span><span class="sxs-lookup"><span data-stu-id="5ee0d-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], exclude a business rule when you do not want to delete the rule permanently, but you do not want to validate data against it.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="5ee0d-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="5ee0d-104">Prerequisites</span></span>  
 <span data-ttu-id="5ee0d-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="5ee0d-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="5ee0d-106">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="5ee0d-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="5ee0d-107">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="5ee0d-107">You must be a model administrator.</span></span> <span data-ttu-id="5ee0d-108">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="5ee0d-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-exclude-a-business-rule"></a><span data-ttu-id="5ee0d-109">So schließen Sie eine Geschäftsregel aus</span><span class="sxs-lookup"><span data-stu-id="5ee0d-109">To exclude a business rule</span></span>  
  
1.  <span data-ttu-id="5ee0d-110">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="5ee0d-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="5ee0d-111">Zeigen Sie auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Geschäftsregeln**.</span><span class="sxs-lookup"><span data-stu-id="5ee0d-111">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="5ee0d-112">Wählen Sie auf der Seite **Verwaltung von Geschäftsregeln** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="5ee0d-112">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="5ee0d-113">Wählen Sie aus der Liste **Entität** eine Entität aus.</span><span class="sxs-lookup"><span data-stu-id="5ee0d-113">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="5ee0d-114">Wählen Sie in der Liste **Elementtyp** einen Typ des Members aus.</span><span class="sxs-lookup"><span data-stu-id="5ee0d-114">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="5ee0d-115">Wählen Sie aus der Liste **Attribut** ein Attribut aus, oder behalten Sie die Standardeinstellung **Alle**bei.</span><span class="sxs-lookup"><span data-stu-id="5ee0d-115">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="5ee0d-116">Aktivieren Sie im Raster in der Zeile für die Geschäftsregel das Kontrollkästchen in der Spalte **ausschließen** .</span><span class="sxs-lookup"><span data-stu-id="5ee0d-116">In the grid, in the row for the business rule, select the check box in the **Exclude** column.</span></span> <span data-ttu-id="5ee0d-117">Der Wert in der Spalte **Status** lautet **Ausschluss steht aus**.</span><span class="sxs-lookup"><span data-stu-id="5ee0d-117">The value in the **Status** column is **Exclusion pending**.</span></span>  
  
8.  <span data-ttu-id="5ee0d-118">Klicken Sie auf **Geschäftsregeln veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="5ee0d-118">Click **Publish business rules**.</span></span>  
  
9. <span data-ttu-id="5ee0d-119">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="5ee0d-119">In the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="5ee0d-120">Der Wert in der Spalte **Status** wird **ausgeschlossen**.</span><span class="sxs-lookup"><span data-stu-id="5ee0d-120">The value in the **Status** column is **Excluded**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ee0d-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ee0d-121">See Also</span></span>  
 <span data-ttu-id="5ee0d-122">[Hiermit wird eine Geschäftsregel &#40;Master Data Services gelöscht&#41;](../../2014/master-data-services/delete-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5ee0d-122">[Delete a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/delete-a-business-rule-master-data-services.md) </span></span>  
 <span data-ttu-id="5ee0d-123">[Erstellen und Veröffentlichen einer Geschäftsregel &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="5ee0d-123">[Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md) </span></span>  
 [<span data-ttu-id="5ee0d-124">Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="5ee0d-124">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
