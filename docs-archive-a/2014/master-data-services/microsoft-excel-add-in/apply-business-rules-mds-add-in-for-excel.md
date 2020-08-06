---
title: Anwenden von Geschäftsregeln (MDS-Add-In für Excel) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
ms.assetid: cd106345-f561-4966-88d3-a69139b2bd78
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: aad5ce6bcebb635fa4659c32654d67406d4ba0dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698396"
---
# <a name="apply-business-rules-mds-add-in-for-excel"></a><span data-ttu-id="8a7ce-102">Anwenden von Geschäftsregeln (MDS-Add-In für Excel)</span><span class="sxs-lookup"><span data-stu-id="8a7ce-102">Apply Business Rules (MDS Add-in for Excel)</span></span>
  <span data-ttu-id="8a7ce-103">Wenden Sie in [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] Geschäftsregeln an, wenn Sie Daten überprüfen und bestätigen möchten, dass sie gültig sind.</span><span class="sxs-lookup"><span data-stu-id="8a7ce-103">In the [!INCLUDE[ssMDSshort](../../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../../includes/ssmdsxls-md.md)] apply business rules when you want to validate data and confirm that it is valid.</span></span> <span data-ttu-id="8a7ce-104">Sie können Überprüfungen korrigieren und die Daten erneut veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="8a7ce-104">You can correct validations and re-publish the data.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8a7ce-105">Die Datenüberprüfung findet automatisch statt, wenn Sie Daten veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="8a7ce-105">Data validation occurs automatically when you publish data.</span></span> <span data-ttu-id="8a7ce-106">Weitere Informationen finden Sie unter [Gespeicherte Überprüfungsprozedur &#40;Master Data Services&#41;](../validation-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="8a7ce-106">For more information, see [Validation Stored Procedure &#40;Master Data Services&#41;](../validation-stored-procedure-master-data-services.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="8a7ce-107">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8a7ce-107">Prerequisites</span></span>  
 <span data-ttu-id="8a7ce-108">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="8a7ce-108">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="8a7ce-109">Sie müssen über den Zugriff auf den Funktionsbereich **Explorer** verfügen.</span><span class="sxs-lookup"><span data-stu-id="8a7ce-109">You must have access to the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="8a7ce-110">Sie müssen über ein aktives Arbeitsblatt mit von MDS verwalteten Daten verfügen.</span><span class="sxs-lookup"><span data-stu-id="8a7ce-110">You must have an active worksheet that contains MDS-managed data.</span></span>  
  
### <a name="to-apply-business-rules"></a><span data-ttu-id="8a7ce-111">So wenden Sie Geschäftsregeln an</span><span class="sxs-lookup"><span data-stu-id="8a7ce-111">To apply business rules</span></span>  
  
1.  <span data-ttu-id="8a7ce-112">Klicken Sie in der Gruppe **Veröffentlichen und Validieren** auf **Regeln anwenden**.</span><span class="sxs-lookup"><span data-stu-id="8a7ce-112">In the **Publish and Validate** group, click **Apply Rules**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8a7ce-113">Die Anzahl der Elemente (Zeilen), die gleichzeitig überprüft werden, richtet sich nach einer Einstellung in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8a7ce-113">The number of members (rows) that are validated at one time depends on a setting in [!INCLUDE[ssMDScfgmgr](../../includes/ssmdscfgmgr-md.md)].</span></span> <span data-ttu-id="8a7ce-114">Weitere Informationen finden Sie unter [Business Rule Settings](../system-settings-master-data-services.md#BusinessRules).</span><span class="sxs-lookup"><span data-stu-id="8a7ce-114">For more information, see [Business Rule Settings](../system-settings-master-data-services.md#BusinessRules).</span></span>  
  
2.  <span data-ttu-id="8a7ce-115">Die Daten werden anhand von Geschäftsregeln überprüft, und zwei Statusspalten werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8a7ce-115">The data is validated against business rules and two status columns are displayed.</span></span> <span data-ttu-id="8a7ce-116">Wenn diese Spalten nicht automatisch angezeigt werden, klicken Sie in der Gruppe **Veröffentlichen und Validieren** auf **Status anzeigen** , um sie anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8a7ce-116">If these columns are not displayed automatically, in the **Publish and Validate** group, click **Show Status** to view them.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a7ce-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8a7ce-117">See Also</span></span>  
 [<span data-ttu-id="8a7ce-118">Veröffentlichen von Daten &#40;MDS-Add-in für Excel&#41;</span><span class="sxs-lookup"><span data-stu-id="8a7ce-118">Publishing Data &#40;MDS Add-in for Excel&#41;</span></span>](overview-importing-data-from-excel-mds-add-in-for-excel.md)  
  
  
