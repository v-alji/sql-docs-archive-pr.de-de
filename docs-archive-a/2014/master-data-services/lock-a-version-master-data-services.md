---
title: Sperren einer Version (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- versions [Master Data Services], locking
- locking versions [Master Data Services]
ms.assetid: 7bb62a84-12d8-4b29-9b6e-6aa25410618e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 68ef979b14d9bd228c7ca89a260b31b2fc6efccd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722869"
---
# <a name="lock-a-version-master-data-services"></a><span data-ttu-id="dd661-102">Sperren einer Version (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="dd661-102">Lock a Version (Master Data Services)</span></span>
  <span data-ttu-id="dd661-103">Sperren Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eine Version eines Modells, um Änderungen an den Elementen des Modells und den Attributen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="dd661-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], lock a version of a model to prevent changes to the model's members and their attributes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="dd661-104">Wenn eine Version gesperrt ist, können Modelladministratoren weiterhin Elemente hinzuzufügen, bearbeiten und entfernen.</span><span class="sxs-lookup"><span data-stu-id="dd661-104">When a version is locked, model administrators can continue to add, edit, and remove members.</span></span> <span data-ttu-id="dd661-105">Andere Benutzer mit Berechtigungen für das Modell können die Elemente jedoch nur anzeigen.</span><span class="sxs-lookup"><span data-stu-id="dd661-105">Other users with permission to the model can view members only.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="dd661-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="dd661-106">Prerequisites</span></span>  
 <span data-ttu-id="dd661-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="dd661-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="dd661-108">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Versionsverwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="dd661-108">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="dd661-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="dd661-109">You must be a model administrator.</span></span> <span data-ttu-id="dd661-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="dd661-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="dd661-111">Der Status der Version muss **Öffnen**sein.</span><span class="sxs-lookup"><span data-stu-id="dd661-111">The version's status must be **Open**.</span></span>  
  
### <a name="to-lock-a-version"></a><span data-ttu-id="dd661-112">So sperren Sie eine Version</span><span class="sxs-lookup"><span data-stu-id="dd661-112">To lock a version</span></span>  
  
1.  <span data-ttu-id="dd661-113">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Versionsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="dd661-113">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="dd661-114">Wählen Sie auf der Seite **Versionen verwalten** die Zeile für die Version aus, die Sie sperren möchten.</span><span class="sxs-lookup"><span data-stu-id="dd661-114">On the **Manage Versions** page, select the row for the version that you want to lock.</span></span>  
  
3.  <span data-ttu-id="dd661-115">Klicken Sie auf **Sperren**.</span><span class="sxs-lookup"><span data-stu-id="dd661-115">Click **Lock**.</span></span>  
  
4.  <span data-ttu-id="dd661-116">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd661-116">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="dd661-117">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="dd661-117">Next Steps</span></span>  
  
-   [<span data-ttu-id="dd661-118">Überprüfen einer Version anhand von Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dd661-118">Validate a Version against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-a-version-against-business-rules-master-data-services.md)  
  
-   [<span data-ttu-id="dd661-119">Durchführen eines Commits für eine Version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dd661-119">Commit a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/commit-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="dd661-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd661-120">See Also</span></span>  
 <span data-ttu-id="dd661-121">[Versionen &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="dd661-121">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="dd661-122">Entsperren einer Version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="dd661-122">Unlock a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/unlock-a-version-master-data-services.md)  
  
  
