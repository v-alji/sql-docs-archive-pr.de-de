---
title: Ändern des Namens einer Geschäftsregel (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- business rules [Master Data Services], changing name
ms.assetid: cffcae43-a208-443f-9f43-a0ec9e05f79c
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 0e99047ffe27332aaed4514394ca2357942a1297
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622763"
---
# <a name="change-a-business-rule-name-master-data-services"></a><span data-ttu-id="94889-102">Ändern des Namens einer Geschäftsregel (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="94889-102">Change a Business Rule Name (Master Data Services)</span></span>
  <span data-ttu-id="94889-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]können Sie den Namen einer Geschäftsregel ändern, wenn der zugewiesene Name nicht Ihren Geschäftsanforderungen entspricht.</span><span class="sxs-lookup"><span data-stu-id="94889-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], change a business rule name when the name assigned does not meet your business needs.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="94889-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="94889-104">Prerequisites</span></span>  
 <span data-ttu-id="94889-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="94889-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="94889-106">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **System Verwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="94889-106">You must have permission to access the **System Administration** functional area.</span></span>  
  
-   <span data-ttu-id="94889-107">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="94889-107">You must be a model administrator.</span></span> <span data-ttu-id="94889-108">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="94889-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="94889-109">Eine Geschäftsregel muss vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="94889-109">A business rule must exist.</span></span> <span data-ttu-id="94889-110">Weitere Informationen finden Sie unter [Erstellen und Veröffentlichen einer Geschäftsregel &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="94889-110">For more information, see [Create and Publish a Business Rule &#40;Master Data Services&#41;](../../2014/master-data-services/create-and-publish-a-business-rule-master-data-services.md).</span></span>  
  
### <a name="to-change-the-name-of-a-business-rule"></a><span data-ttu-id="94889-111">So ändern Sie den Namen einer Geschäftsregel</span><span class="sxs-lookup"><span data-stu-id="94889-111">To change the name of a business rule</span></span>  
  
1.  <span data-ttu-id="94889-112">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Systemverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="94889-112">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **System Administration**.</span></span>  
  
2.  <span data-ttu-id="94889-113">Zeigen Sie auf der Menüleiste auf **Verwalten** , und klicken Sie auf **Geschäftsregeln**.</span><span class="sxs-lookup"><span data-stu-id="94889-113">From the menu bar, point to **Manage** and click **Business Rules**.</span></span>  
  
3.  <span data-ttu-id="94889-114">Wählen Sie auf der Seite **Verwaltung von Geschäftsregeln** aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="94889-114">On the **Business Rule Maintenance** page, from the **Model** list, select a model.</span></span>  
  
4.  <span data-ttu-id="94889-115">Wählen Sie aus der Liste **Entität** eine Entität aus.</span><span class="sxs-lookup"><span data-stu-id="94889-115">From the **Entity** list, select an entity.</span></span>  
  
5.  <span data-ttu-id="94889-116">Wählen Sie in der Liste **Elementtyp** einen Typ des Members aus.</span><span class="sxs-lookup"><span data-stu-id="94889-116">From the **Member Type** list, select a type of member.</span></span>  
  
6.  <span data-ttu-id="94889-117">Wählen Sie aus der Liste **Attribut** ein Attribut aus, oder behalten Sie die Standardeinstellung **Alle**bei.</span><span class="sxs-lookup"><span data-stu-id="94889-117">From the **Attribute** list, select an attribute or leave the default of **All**.</span></span>  
  
7.  <span data-ttu-id="94889-118">Doppelklicken Sie im Raster in der Zeile für die Geschäftsregel auf das Feld **Name** .</span><span class="sxs-lookup"><span data-stu-id="94889-118">In the grid, in the row for the business rule, double-click the **Name** field.</span></span>  
  
8.  <span data-ttu-id="94889-119">Geben Sie einen Namen für die Geschäftsregel ein.</span><span class="sxs-lookup"><span data-stu-id="94889-119">Type a name for the business rule.</span></span>  
  
9. <span data-ttu-id="94889-120">Drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="94889-120">Press ENTER.</span></span>  
  
10. <span data-ttu-id="94889-121">Klicken Sie auf **Geschäftsregeln veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="94889-121">Click **Publish business rules**.</span></span>  
  
11. <span data-ttu-id="94889-122">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="94889-122">On the confirmation dialog box, click **OK**.</span></span> <span data-ttu-id="94889-123">Der Status der Regel ändert sich zu **Aktiv**.</span><span class="sxs-lookup"><span data-stu-id="94889-123">The rule's status changes to **Active**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94889-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="94889-124">See Also</span></span>  
 [<span data-ttu-id="94889-125">Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="94889-125">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
