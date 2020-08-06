---
title: Erstellen eines Blattelements (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- leaf members [Master Data Services], creating
- creating leaf members [Master Data Services]
- members [Master Data Services], creating leaf members
ms.assetid: 0499d3b3-d508-4d43-a740-19cf53ade9f1
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: fe0245dd30019e1cb9112754bd8b8eeafed93aa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607880"
---
# <a name="create-a-leaf-member-master-data-services"></a><span data-ttu-id="51b55-102">Erstellen eines Blattelements (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="51b55-102">Create a Leaf Member (Master Data Services)</span></span>
  <span data-ttu-id="51b55-103">[!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]Erstellen Sie in ein Blatt Element, wenn Sie dem System Master Daten hinzufügen möchten und keine Stagingtabellen oder verwenden [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] [!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] , um Daten zu importieren.</span><span class="sxs-lookup"><span data-stu-id="51b55-103">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], create a leaf member when you want to add master data to your system and are not using staging tables or the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)][!INCLUDE[ssMDSXLS](../includes/ssmdsxls-md.md)] to import data.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="51b55-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="51b55-104">Prerequisites</span></span>  
 <span data-ttu-id="51b55-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="51b55-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="51b55-106">Sie müssen über die Berechtigung für den Zugriff auf den Funktionsbereich **Explorer** verfügen.</span><span class="sxs-lookup"><span data-stu-id="51b55-106">You must have permission to access the **Explorer** functional area.</span></span>  
  
-   <span data-ttu-id="51b55-107">Sie müssen mindestens über die Berechtigung **Aktualisieren** für das Blatt Modell Objekt für die Entität verfügen, der Sie ein Mitglied hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="51b55-107">You must have a minimum of **Update** permission to the leaf model object for the entity you are adding a member to.</span></span>  
  
### <a name="to-create-a-leaf-member"></a><span data-ttu-id="51b55-108">So erstellen Sie ein Blattelement</span><span class="sxs-lookup"><span data-stu-id="51b55-108">To create a leaf member</span></span>  
  
1.  <span data-ttu-id="51b55-109">Wählen Sie auf der [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] -Startseite aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="51b55-109">On the [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)] home page, from the **Model** list, select a model.</span></span>  
  
2.  <span data-ttu-id="51b55-110">Wenn Sie Benutzer sind, wählen Sie eine geöffnete Version aus der Liste **Version** aus.</span><span class="sxs-lookup"><span data-stu-id="51b55-110">If you are a user, select an open version from the **Version** list.</span></span> <span data-ttu-id="51b55-111">Wenn Sie Administrator sind, wählen Sie eine Version mit dem Status „Geöffnet“ oder „Gesperrt“ aus der Liste **Version** aus.</span><span class="sxs-lookup"><span data-stu-id="51b55-111">If you are an administrator, select a version with open or locked status from the **Version** list.</span></span>  
  
3.  <span data-ttu-id="51b55-112">Klicken Sie auf **Explorer**.</span><span class="sxs-lookup"><span data-stu-id="51b55-112">Click **Explorer**.</span></span>  
  
4.  <span data-ttu-id="51b55-113">Zeigen Sie auf der Menüleiste auf **Entitäten** , und klicken Sie auf den Namen der Entität, der Sie ein Element hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="51b55-113">From the menu bar, point to **Entities** and click the name of the entity you want to add a member to.</span></span>  
  
5.  <span data-ttu-id="51b55-114">Klicken Sie auf **Mitglied hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="51b55-114">Click **Add member**.</span></span>  
  
6.  <span data-ttu-id="51b55-115">Vervollständigen Sie die Felder im Bereich **Details** .</span><span class="sxs-lookup"><span data-stu-id="51b55-115">In the **Details** pane, complete the fields.</span></span>  
  
7.  <span data-ttu-id="51b55-116">Optional.</span><span class="sxs-lookup"><span data-stu-id="51b55-116">Optional.</span></span> <span data-ttu-id="51b55-117">Geben Sie im Feld **Anmerkungen** einen Kommentar dazu ein, warum das Element hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="51b55-117">In the **Annotations** box, type a comment about why the member was added.</span></span> <span data-ttu-id="51b55-118">Alle Benutzer, die Zugriff auf das Element haben, können die Anmerkung anzeigen.</span><span class="sxs-lookup"><span data-stu-id="51b55-118">All users who have access to the member can view the annotation.</span></span>  
  
8.  <span data-ttu-id="51b55-119">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="51b55-119">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51b55-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="51b55-120">See Also</span></span>  
 <span data-ttu-id="51b55-121">[Laden oder Aktualisieren von Elementen in Master Data Services mithilfe des Stagingprozesses](add-update-and-delete-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="51b55-121">[Load or Update Members in Master Data Services by Using the Staging Process](add-update-and-delete-data-master-data-services.md) </span></span>  
 <span data-ttu-id="51b55-122">[Erstellen Sie ein konsolidiertes Element &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="51b55-122">[Create a Consolidated Member &#40;Master Data Services&#41;](../../2014/master-data-services/create-a-consolidated-member-master-data-services.md) </span></span>  
 [<span data-ttu-id="51b55-123">Elemente &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="51b55-123">Members &#40;Master Data Services&#41;</span></span>](../../2014/master-data-services/members-master-data-services.md)  
  
  
