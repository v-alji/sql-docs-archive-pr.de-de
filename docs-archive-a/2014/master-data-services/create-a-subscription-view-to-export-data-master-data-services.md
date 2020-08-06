---
title: Erstellen einer Abonnement Sicht (Master Data Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: master-data-services
ms.topic: conceptual
helpviewer_keywords:
- subscription views [Master Data Services], creating
- creating subscription views [Master Data Services]
ms.assetid: a5e28961-af16-414a-9845-d2e06aac5214
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: e5e2b901e56d75e97a444fd2858ef95872f3b766
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619891"
---
# <a name="create-a-subscription-view-master-data-services"></a><span data-ttu-id="ce317-102">Erstellen einer Abonnementsicht (Master Data Services)</span><span class="sxs-lookup"><span data-stu-id="ce317-102">Create a Subscription View (Master Data Services)</span></span>
  <span data-ttu-id="ce317-103">Erstellen Sie eine Abonnement Sicht, wenn Sie eine Sicht Ihrer Daten in der [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] Datenbank für die Verwendung durch Abonnement Systeme erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="ce317-103">Create a subscription view when you want to create a view of your data in the [!INCLUDE[ssMDSshort](../includes/ssmdsshort-md.md)] database for use by subscribing systems.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="ce317-104">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="ce317-104">Prerequisites</span></span>  
 <span data-ttu-id="ce317-105">So führen Sie diese Prozedur aus</span><span class="sxs-lookup"><span data-stu-id="ce317-105">To perform this procedure:</span></span>  
  
-   <span data-ttu-id="ce317-106">Sie müssen über die entsprechende Berechtigung für den Zugriff auf den Funktionsbereich **Integrationsmanagement** verfügen.</span><span class="sxs-lookup"><span data-stu-id="ce317-106">You must have permission to access the **Integration Management** functional area.</span></span>  
  
-   <span data-ttu-id="ce317-107">Sie müssen ein Modelladministrator sein.</span><span class="sxs-lookup"><span data-stu-id="ce317-107">You must be a model administrator.</span></span> <span data-ttu-id="ce317-108">Weitere Informationen finden Sie unter [Administratoren &#40;Master Data Services&#41;](administrators-master-data-services.md).</span><span class="sxs-lookup"><span data-stu-id="ce317-108">For more information, see [Administrators &#40;Master Data Services&#41;](administrators-master-data-services.md).</span></span>  
  
### <a name="to-create-a-subscription-view"></a><span data-ttu-id="ce317-109">So erstellen Sie eine Abonnementsicht</span><span class="sxs-lookup"><span data-stu-id="ce317-109">To create a subscription view</span></span>  
  
1.  <span data-ttu-id="ce317-110">Klicken Sie in [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)]auf **Integrationsmanagement**.</span><span class="sxs-lookup"><span data-stu-id="ce317-110">In [!INCLUDE[ssMDSmdm](../includes/ssmdsmdm-md.md)], click **Integration Management**.</span></span>  
  
2.  <span data-ttu-id="ce317-111">Klicken Sie auf der Menüleiste auf **Sichten erstellen**.</span><span class="sxs-lookup"><span data-stu-id="ce317-111">From the menu bar, click **Create Views**.</span></span>  
  
3.  <span data-ttu-id="ce317-112">Klicken Sie auf der Seite **Abonnement Sichten** auf **Abonnement Sicht hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="ce317-112">On the **Subscription Views** page, click **Add subscription view**.</span></span>  
  
4.  <span data-ttu-id="ce317-113">Geben Sie im Bereich **Abonnement Sicht erstellen** im Feld **Name der Abonnement Sicht** einen Namen für die Ansicht ein.</span><span class="sxs-lookup"><span data-stu-id="ce317-113">In the **Create Subscription View** pane, in the **Subscription view name** box, type a name for the view.</span></span>  
  
5.  <span data-ttu-id="ce317-114">Wählen Sie aus der Liste **Modell** ein Modell aus.</span><span class="sxs-lookup"><span data-stu-id="ce317-114">From the **Model** list, select a model.</span></span>  
  
6.  <span data-ttu-id="ce317-115">Wählen Sie entweder die Option **Version** oder Versionsflag aus, und wählen Sie dann aus der entsprechenden Liste aus. **Version Flag**</span><span class="sxs-lookup"><span data-stu-id="ce317-115">Select either the **Version** or **Version Flag** option, and then select from the corresponding list.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="ce317-116">Erstellen Sie auf Grundlage eines Versionsflags eine Abonnementsicht.</span><span class="sxs-lookup"><span data-stu-id="ce317-116">Create a subscription view based on a version flag.</span></span> <span data-ttu-id="ce317-117">Wenn Sie eine Version sperren, können Sie das Flag einer geöffneten Version erneut zuweisen, ohne die Abonnementsicht zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="ce317-117">When you lock a version, you can reassign the flag to an open version without updating the subscription view.</span></span>  
  
7.  <span data-ttu-id="ce317-118">Wählen Sie entweder die Option **Entität** oder **abgeleitete Hierarchie** aus, und wählen Sie dann aus der entsprechenden Liste aus.</span><span class="sxs-lookup"><span data-stu-id="ce317-118">Select either the **Entity** or **Derived hierarchy** option, and then select from the corresponding list.</span></span>  
  
8.  <span data-ttu-id="ce317-119">Wählen Sie aus der Liste **Format** ein Format für die Abonnementsicht aus.</span><span class="sxs-lookup"><span data-stu-id="ce317-119">From the **Format** list, select a subscription view format.</span></span>  
  
9. <span data-ttu-id="ce317-120">Wenn Sie **Explizite Ebenen** oder **Abgeleitete Ebenen** aus der Liste **Format** ausgewählt haben, geben Sie die Anzahl der in die Sicht aufzunehmenden Hierarchieebenen ein.</span><span class="sxs-lookup"><span data-stu-id="ce317-120">If you chose **Explicit levels** or **Derived levels** from the **Format** list, type the number of levels in the hierarchy to include in the view.</span></span>  
  
10. <span data-ttu-id="ce317-121">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ce317-121">Click **Save**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce317-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ce317-122">See Also</span></span>  
 <span data-ttu-id="ce317-123">[Daten &#40;Master Data Services werden exportiert&#41;](overview-exporting-data-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ce317-123">[Exporting Data &#40;Master Data Services&#41;](overview-exporting-data-master-data-services.md) </span></span>  
 <span data-ttu-id="ce317-124">[&#40;Master Data Services eine Abonnement Sicht löschen&#41;](delete-a-subscription-view-master-data-services.md) </span><span class="sxs-lookup"><span data-stu-id="ce317-124">[Delete a Subscription View &#40;Master Data Services&#41;](delete-a-subscription-view-master-data-services.md) </span></span>  
 [<span data-ttu-id="ce317-125">Erstellen eines Versionsflags &#40;Master Data Services&#41;</span><span class="sxs-lookup"><span data-stu-id="ce317-125">Create a Version Flag &#40;Master Data Services&#41;</span></span>](create-a-version-flag-master-data-services.md)  
  
  
