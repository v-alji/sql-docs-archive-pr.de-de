---
title: Zuweisen eines Flags zu einer Version (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- version flags [Master Data Services], assigning flags
- versions [Master Data Services], assigning flags
ms.assetid: 6629ec7e-32e7-4a1e-8b31-eb43c5923766
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 2de0d0d8d8ea96814e13b9123fe4fcd4782d6bef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622191"
---
# <a name="assign-a-flag-to-a-version-master-data-services"></a><span data-ttu-id="2fb2b-102">Zuweisen eines Flags zu einer Version (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="2fb2b-102">Assign a Flag to a Version (Master Data Services)</span></span>
  <span data-ttu-id="2fb2b-103">Weisen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]ein Flag einer Version zu, um die Version anzugeben, die Benutzer oder abonnierende Systeme verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="2fb2b-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], assign a flag to a version to indicate the version that users or subscribing systems should use.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2fb2b-104">Versionsflags können nur jeweils einer Version zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="2fb2b-104">Version flags can be assigned to only one version at a time.</span></span> <span data-ttu-id="2fb2b-105">Wenn Sie ein Flag zuweisen, das einer anderen Version bereits zugewiesen ist, wird das Flag in die Version verschoben, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="2fb2b-105">If you assign a flag that is already assigned to another version, the flag is moved to the version you selected.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="2fb2b-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2fb2b-106">Prerequisites</span></span>  
 <span data-ttu-id="2fb2b-107">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="2fb2b-107">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="2fb2b-108">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Versionsverwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="2fb2b-108">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="2fb2b-109">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="2fb2b-109">You must be a model administrator.</span></span> <span data-ttu-id="2fb2b-110">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2fb2b-110">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
-   <span data-ttu-id="2fb2b-111">Sie müssen ein Versionsflag erstellt haben, um es zuweisen zu können.</span><span class="sxs-lookup"><span data-stu-id="2fb2b-111">You must have created a version flag to assign.</span></span> <span data-ttu-id="2fb2b-112">Weitere Informationen finden Sie unter [Erstellen eines Versionsflags &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="2fb2b-112">For more information, see [Create a Version Flag &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md).</span></span>  
  
### <a name="to-assign-a-flag-to-a-version"></a><span data-ttu-id="2fb2b-113">So weisen Sie einer Version ein Flag zu</span><span class="sxs-lookup"><span data-stu-id="2fb2b-113">To assign a flag to a version</span></span>  
  
1.  <span data-ttu-id="2fb2b-114">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Versionsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="2fb2b-114">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="2fb2b-115">Doppelklicken Sie auf der Seite **Versionen verwalten** in der Zeile für die Version, der Sie ein Flag zuweisen möchten, auf die Zelle in der Spalte **Flag** .</span><span class="sxs-lookup"><span data-stu-id="2fb2b-115">On the **Manage Versions** page, in the row for the version to which you want to assign a flag, double-click the cell in the **Flag** column.</span></span>  
  
3.  <span data-ttu-id="2fb2b-116">Wählen Sie aus der Liste das Flag aus, das Sie zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="2fb2b-116">From the list, select the flag you want to assign.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2fb2b-117">Wenn das gewünschte Flag nicht verfügbar ist, steht dieses möglicherweise nur für Versionen **Mit ausgeführtem Commit** zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="2fb2b-117">If the flag you want is not available, the flag might be available for **Committed** versions only.</span></span> <span data-ttu-id="2fb2b-118">Sie können dies überprüfen, indem Sie die Seite **Versionsflags verwalten** aufrufen und das Feld **Nur Versionen, für die ein Commit ausgeführt wurde** für das Flag anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2fb2b-118">To confirm, go to the **Manage Version Flags** page and view the **Committed Versions Only** field for the flag.</span></span>  
  
4.  <span data-ttu-id="2fb2b-119">Drücken Sie die EINGABETASTE, um die Änderung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2fb2b-119">Press ENTER to save the change.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fb2b-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2fb2b-120">See Also</span></span>  
 <span data-ttu-id="2fb2b-121">[Erstellen Sie ein Versionsflag &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="2fb2b-121">[Create a Version Flag &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-version-flag-master-data-services.md) </span></span>  
 [<span data-ttu-id="2fb2b-122">Versionen &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="2fb2b-122">Versions &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/versions-master-data-services.md)  
  
  
