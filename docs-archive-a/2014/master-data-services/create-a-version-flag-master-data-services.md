---
title: Erstellen eines Versionsflags (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- creating version flags [Master Data Services]
- version flags [Master Data Services], creating
- versions [Master Data Services], creating flags
ms.assetid: 3067e1e3-05b7-4f11-9206-c612ef4e7e42
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: f04c93f8315ccd5b53e07db169783da53afe0156
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619888"
---
# <a name="create-a-version-flag-master-data-services"></a><span data-ttu-id="97036-102">Erstellen eines Versionsflags (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="97036-102">Create a Version Flag (Master Data Services)</span></span>
  <span data-ttu-id="97036-103">Erstellen Sie in [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)]ein Versionsflag, das Sie einer Version zuweisen.</span><span class="sxs-lookup"><span data-stu-id="97036-103">In [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)], create a version flag to assign to a version.</span></span> <span data-ttu-id="97036-104">Das Flag kann die Version angeben, die Benutzer oder abonnierende Systeme verwenden sollten.</span><span class="sxs-lookup"><span data-stu-id="97036-104">The flag can indicate the version that users or subscribing systems should use.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="97036-105">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="97036-105">Prerequisites</span></span>  
 <span data-ttu-id="97036-106">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="97036-106">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="97036-107">Sie müssen über die Berechtigung verfügen, auf den Funktionsbereich **Versionsverwaltung** zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="97036-107">You must have permission to access the **Version Management** functional area.</span></span>  
  
-   <span data-ttu-id="97036-108">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="97036-108">You must be a model administrator.</span></span> <span data-ttu-id="97036-109">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="97036-109">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-version-flag"></a><span data-ttu-id="97036-110">So erstellen Sie ein Versionsflag</span><span class="sxs-lookup"><span data-stu-id="97036-110">To create a version flag</span></span>  
  
1.  <span data-ttu-id="97036-111">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Versionsverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="97036-111">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Version Management**.</span></span>  
  
2.  <span data-ttu-id="97036-112">Zeigen Sie auf der Seite **Versionen verwalten** in der Menüleiste auf **Verwalten** und klicken Sie dann auf **Flags**.</span><span class="sxs-lookup"><span data-stu-id="97036-112">On the **Manage Versions** page, from the menu bar, point to **Manage** and then click **Flags**.</span></span>  
  
3.  <span data-ttu-id="97036-113">Wählen Sie auf der Seite **Versionsflags verwalten** im Feld **Modell** das Modell aus, für das Sie ein Flag erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="97036-113">On the **Manage Version Flags** page, from the **Model** field, select the model for which you want to create a flag.</span></span>  
  
4.  <span data-ttu-id="97036-114">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="97036-114">Click **Add**.</span></span>  
  
5.  <span data-ttu-id="97036-115">Geben Sie im Feld **Name** einen Namen ein.</span><span class="sxs-lookup"><span data-stu-id="97036-115">In the **Name** box, type a name.</span></span>  
  
6.  <span data-ttu-id="97036-116">Geben Sie in das Feld **Beschreibung** eine Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="97036-116">In the **Description** box, type a description.</span></span>  
  
7.  <span data-ttu-id="97036-117">Wählen Sie im Feld **Nur Versionen, für die ein Commit ausgeführt wurde\*\*\*\*True** aus, um anzugeben, dass das Flag nur Versionen mit dem Status **Commit wurde ausgeführt** zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="97036-117">In the **Committed Versions Only** field, select **True** to indicate that the flag can be assigned to versions with a status of **Committed** only.</span></span> <span data-ttu-id="97036-118">Wählen Sie **False** aus, um anzugeben, dass das Flag Versionen mit beliebigem Status zugewiesen werden kann.</span><span class="sxs-lookup"><span data-stu-id="97036-118">Select **False** to indicate that the flag can be assigned to versions with any status.</span></span>  
  
8.  <span data-ttu-id="97036-119">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="97036-119">Click **Save**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="97036-120">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="97036-120">Next Steps</span></span>  
  
-   [<span data-ttu-id="97036-121">Zuweisen eines Flags zu einer Version &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="97036-121">Assign a Flag to a Version &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/assign-a-flag-to-a-version-master-data-services.md)  
  
## <a name="see-also"></a><span data-ttu-id="97036-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="97036-122">See Also</span></span>  
 <span data-ttu-id="97036-123">[Versionen &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="97036-123">[Versions &#40;Master Data Services&#41;](../../2014/master-data-services/versions-master-data-services.md) </span></span>  
 [<span data-ttu-id="97036-124">Ändern des Namens eines Versionsflags &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="97036-124">Change a Version Flag Name &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/change-a-version-flag-name-master-data-services.md)  
  
  
