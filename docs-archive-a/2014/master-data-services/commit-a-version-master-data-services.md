---
title: Durchführen eines Commits für eine Version (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- committing versions [Master Data Services]
- versions [Master Data Services], committing
ms.assetid: 6b967a39-b333-4b84-9e5f-4fb07e156826
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cec3244d4ddaa78d9168e3ede503fa16756633a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699975"
---
# <a name="commit-a-version-master-data-services"></a><span data-ttu-id="1bf7c-102">Durchführen eines Commits für eine Version (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="1bf7c-102">Commit a Version (Master Data Services)</span></span>
  <span data-ttu-id="1bf7c-103">Führen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]einen Commit für eine Version eines Modells durch, um Änderungen an den Elementen des Modells und den Attributen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="1bf7c-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], commit a version of a model to prevent changes to the model's members and their attributes.</span></span> <span data-ttu-id="1bf7c-104">Versionen mit ausgeführtem Commit können nicht entsperrt werden.</span><span class="sxs-lookup"><span data-stu-id="1bf7c-104">Committed versions cannot be unlocked.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="1bf7c-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1bf7c-105">Prerequisites</span></span>  
 <span data-ttu-id="1bf7c-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="1bf7c-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="1bf7c-107">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Versionsverwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="1bf7c-107">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="1bf7c-108">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="1bf7c-108">You must be a model administrator.</span></span> <span data-ttu-id="1bf7c-109">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1bf7c-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="1bf7c-110">Der Status der Version muss **Gesperrt**sein.</span><span class="sxs-lookup"><span data-stu-id="1bf7c-110">The version's status must be **Locked**.</span></span> <span data-ttu-id="1bf7c-111">Weitere Informationen finden Sie unter [Sperren einer Version &#40;Master Data Services&#41;](../../2014/master-data-services/lock-a-version-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="1bf7c-111">For more information, see [Lock a Version &#40;Master Data Services&#41;](../../2014/master-data-services/lock-a-version-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="1bf7c-112">Alle Elemente müssen erfolgreich überprüft worden sein.</span><span class="sxs-lookup"><span data-stu-id="1bf7c-112">All members must have validated successfully.</span></span>  
  
### <a name="to-commit-a-version"></a><span data-ttu-id="1bf7c-113">So führen Sie einen Commit für eine Version durch</span><span class="sxs-lookup"><span data-stu-id="1bf7c-113">To commit a version</span></span>  
  
1.  <span data-ttu-id="1bf7c-114">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Versionsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="1bf7c-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="1bf7c-115">Klicken Sie auf der Seite **Versionen verwalten** auf der Menüleiste auf **Version überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="1bf7c-115">On the **Manage Versions** page, on the menu bar, click **Validate Version**.</span></span>  
  
3.  <span data-ttu-id="1bf7c-116">Wählen Sie auf der Seite **Version überprüfen** das Modell und die Version aus, für das bzw. die Sie einen Commit durchführen möchten.</span><span class="sxs-lookup"><span data-stu-id="1bf7c-116">On the **Validate Version** page, select the model and version you want to commit.</span></span>  
  
4.  <span data-ttu-id="1bf7c-117">Klicken Sie auf **Commit ausführen**.</span><span class="sxs-lookup"><span data-stu-id="1bf7c-117">Click **Commit**.</span></span>  
  
5.  <span data-ttu-id="1bf7c-118">Klicken Sie im Bestätigungsdialogfeld auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1bf7c-118">In the confirmation dialog box, click **OK**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="1bf7c-119">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1bf7c-119">Next Steps</span></span>  
  
-   [<span data-ttu-id="1bf7c-120">Erstellen eines Versionsflags &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1bf7c-120">Create a Version Flag &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/create-a-version-flag-master-data-services.md)  
  
-   [<span data-ttu-id="1bf7c-121">Zuweisen eines Flags zu einer Version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1bf7c-121">Assign a Flag to a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
-   [<span data-ttu-id="1bf7c-122">Kopieren einer Version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1bf7c-122">Copy a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/copy-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="1bf7c-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1bf7c-123">See Also</span></span>  
 [<span data-ttu-id="1bf7c-124">Versionen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="1bf7c-124">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
  
