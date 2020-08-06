---
title: Überprüfen von bestimmten Elementen auf Geschäftsregeln (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- applying business rules [Master Data Services]
- business rules [Master Data Services], applying to select members
ms.assetid: 2288ef43-5392-47ea-b651-ec25e5692a14
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 18af83146679eb77638dfbc98b31f198dc8e07b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617157"
---
# <a name="validate-specific-members-against-business-rules-master-data-services"></a><span data-ttu-id="8019d-102">Überprüfen von bestimmten Elementen auf Geschäftsregeln (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="8019d-102">Validate Specific Members against Business Rules (Master Data Services)</span></span>
  <span data-ttu-id="8019d-103">Wenn Sie Teilmengen von Elementen aktualisieren oder mit Geschäftsregeln abgleichen möchten, können Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]Geschäftsregeln selektiv anwenden.</span><span class="sxs-lookup"><span data-stu-id="8019d-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], apply business rules selectively when you want to update or validate subsets of members against business rules.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8019d-104">Wenn Sie Geschäftsregeln auf alle Elemente in einer Version eines Modells anwenden möchten, gehen Sie auf die Seite [Überprüfen einer Version anhand von Geschäftsregeln &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8019d-104">If you want to apply business rules to all members in a version of a model, see [Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8019d-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8019d-105">Prerequisites</span></span>  
 <span data-ttu-id="8019d-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="8019d-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="8019d-107">Sie müssen über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** verfügen.</span><span class="sxs-lookup"><span data-stu-id="8019d-107">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="8019d-108">Sie müssen mindestens die Berechtigung **Aktualisieren** für das Modellobjekt haben, auf das Sie Geschäftsregeln anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8019d-108">You must have a minimum of **Update** permission to the model object you are applying business rules to.</span></span>  
  
### <a name="to-apply-business-rules-selectively"></a><span data-ttu-id="8019d-109">So wenden Sie Geschäftsregeln selektiv an</span><span class="sxs-lookup"><span data-stu-id="8019d-109">To apply business rules selectively</span></span>  
  
1.  <span data-ttu-id="8019d-110">Wählen Sie auf der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Startseite aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="8019d-110">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="8019d-111">Wählen Sie aus der Liste **Version** eine Version aus.</span><span class="sxs-lookup"><span data-stu-id="8019d-111">From the **Version** list, select a version.</span></span>  
  
3.  <span data-ttu-id="8019d-112">Klicken Sie auf **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="8019d-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="8019d-113">Zeigen Sie in der Menüleiste auf **Entitäten** und klicken Sie auf den Namen der Entität mit den Elementen, auf die Sie Regeln anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8019d-113">From the menu bar, point to **Entities** and click the name of the entity that contains members you want to apply rules to.</span></span>  
  
5.  <span data-ttu-id="8019d-114">Klicken Sie auf **Geschäftsregeln anwenden**.</span><span class="sxs-lookup"><span data-stu-id="8019d-114">Click **Apply business rules**.</span></span> <span data-ttu-id="8019d-115">Die Geschäftsregeln werden nur auf die im Raster angezeigten Elemente angewendet.</span><span class="sxs-lookup"><span data-stu-id="8019d-115">Business rules are applied only to the members displayed in the grid.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8019d-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8019d-116">See Also</span></span>  
 <span data-ttu-id="8019d-117">[Überprüfen einer Version anhand von Geschäftsregeln &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="8019d-117">[Validate a Version against Business Rules &#40;Master Data Services&#41;](validate-a-version-against-business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="8019d-118">Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="8019d-118">Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/business-rules-master-data-services.md)  
  
  
