---
title: Überprüfen einer Version anhand von Geschäftsregeln (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- validating versions [Master Data Services]
- validating versions [Master Data Services], about validating versions
- versions [Master Data Services], validating
- business rules [Master Data Services], applying to all members
ms.assetid: 5aee7901-6d05-41d4-8bbb-c6f26791d1df
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 085fa071ca511c9d838c140547419bf87fb857bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617158"
---
# <a name="validate-a-version-against-business-rules-master-data-services"></a><span data-ttu-id="11b19-102">Überprüfen einer Version anhand von Geschäftsregeln (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="11b19-102">Validate a Version against Business Rules (Master Data Services)</span></span>
  <span data-ttu-id="11b19-103">Überprüfen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]eine Version, um Geschäftsregeln auf alle Elemente in der Modellversion anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="11b19-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], validate a version to apply business rules to all members in the model version.</span></span>  
  
 <span data-ttu-id="11b19-104">Im folgenden Verfahren wird erklärt, wie Daten mit der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Webanwendung überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="11b19-104">This procedure explains how to use the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] web application to validate data.</span></span> <span data-ttu-id="11b19-105">Wenn Sie über die Berechtigung in der MDS-Datenbank verfügen, können Sie stattdessen eine gespeicherte Prozedur verwenden.</span><span class="sxs-lookup"><span data-stu-id="11b19-105">If you have permission in the MDS database, you can use a stored procedure instead.</span></span> <span data-ttu-id="11b19-106">Weitere Informationen finden Sie unter [Gespeicherte Überprüfungsprozedur &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="11b19-106">For more information, see [Validation Stored Procedure &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="11b19-107">Damit ein Commit für eine Version ausgeführt werden kann, müssen alle Elemente die Überprüfung bestehen.</span><span class="sxs-lookup"><span data-stu-id="11b19-107">All members must pass validation before a version can be committed.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="11b19-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="11b19-108">Prerequisites</span></span>  
 <span data-ttu-id="11b19-109">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="11b19-109">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="11b19-110">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Versionsverwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="11b19-110">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="11b19-111">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="11b19-111">You must be a model administrator.</span></span> <span data-ttu-id="11b19-112">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="11b19-112">For more information, see [Administrators &#40;Master Data Services&#41;](../../2014/master-data-services/administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="11b19-113">Der Status der Version muss **Öffnen** oder **Gesperrt**sein.</span><span class="sxs-lookup"><span data-stu-id="11b19-113">The version's status must be **Open** or **Locked**.</span></span>  
  
-   <span data-ttu-id="11b19-114">Auf der Seite **Versionen überprüfen** müssen Elemente mit einem anderen Status als **Überprüfung erfolgreich**vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="11b19-114">On the **Validate Versions** page, members must exist with a status other than **Validation succeeded**.</span></span>  
  
### <a name="to-validate-a-version"></a><span data-ttu-id="11b19-115">So überprüfen Sie eine Version</span><span class="sxs-lookup"><span data-stu-id="11b19-115">To validate a version</span></span>  
  
1.  <span data-ttu-id="11b19-116">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Versionsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="11b19-116">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="11b19-117">Klicken Sie auf der Seite **Versionen verwalten** auf der Menüleiste auf **Version überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="11b19-117">On the **Manage Versions** page, from the menu bar, click **Validate Version**.</span></span>  
  
3.  <span data-ttu-id="11b19-118">Wählen Sie auf der Seite **Versionen überprüfen** das Modell und die Version aus, die Sie überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="11b19-118">On the **Validate Versions** page, select the model and version you want to validate.</span></span>  
  
4.  <span data-ttu-id="11b19-119">Klicken Sie auf **Überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="11b19-119">Click **Validate**.</span></span>  
  
5.  <span data-ttu-id="11b19-120">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="11b19-120">In the confirmation dialog box, click **OK**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="11b19-121">Wenn die Statusanzeige nicht mehr angezeigt wird, hat die Version die Überprüfung beendet.</span><span class="sxs-lookup"><span data-stu-id="11b19-121">When the progress indicator is no longer displayed, the version has finished validation.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="11b19-122">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="11b19-122">Next Steps</span></span>  
  
-   [<span data-ttu-id="11b19-123">Sperren einer Version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="11b19-123">Lock a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/lock-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="11b19-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="11b19-124">See Also</span></span>  
 <span data-ttu-id="11b19-125">[Der Überprüfungs Status &#40;Master Data Services&#41;](../../2014/master-data-services/validation-statuses-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="11b19-125">[Validation Statuses &#40;Master Data Services&#41;](../../2014/master-data-services/validation-statuses-master-data-services.md) </span></span>  
 <span data-ttu-id="11b19-126">[Die gespeicherte Überprüfungs Prozedur &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="11b19-126">[Validation Stored Procedure &#40;Master Data Services&#41;](validation-stored-procedure-master-data-services.md) </span></span>  
 <span data-ttu-id="11b19-127">[Versionen &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="11b19-127">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 <span data-ttu-id="11b19-128">[Master Data Services von Geschäftsregeln &#40;&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="11b19-128">[Business Rules &#40;Master Data Services&#41;](../../2014/master-data-services/business-rules-master-data-services.md) </span></span>  
 [<span data-ttu-id="11b19-129">Überprüfen von bestimmten Elementen auf Geschäftsregeln &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="11b19-129">Validate Specific Members against Business Rules &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/validate-specific-members-against-business-rules-master-data-services.md)  
  
  
