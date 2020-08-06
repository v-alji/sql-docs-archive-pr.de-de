---
title: 'Aufgabe 2 (optional): Erstellen einer MDS-Abonnement Sicht mithilfe Master Data Manager | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f3da8219-e0cb-4848-95ca-285a76ec1ba9
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 998436734ba5c3cf09cfe88f266a0908c0550abc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720434"
---
# <a name="task-2-optional-creating-a-mds-subscription-view-using-master-data-manager"></a><span data-ttu-id="e9f71-102">Aufgabe 2 (optional): Erstellen einer MDS-Abonnementsicht mithilfe des Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="e9f71-102">Task 2 (Optional): Creating a MDS Subscription View using Master Data Manager</span></span>
  <span data-ttu-id="e9f71-103">In dieser Aufgabe erstellen Sie eine Abonnement Sicht, um die Entität **Supplier** im **Lieferanten** Modell für andere Anwendungen verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="e9f71-103">In this task, you create a subscription view to expose the **Supplier** entity in the **Suppliers** model to other applications.</span></span> <span data-ttu-id="e9f71-104">Sie verwenden diese Sicht nicht in der aktuellen Version des Lernprogramms.</span><span class="sxs-lookup"><span data-stu-id="e9f71-104">You do not consume this view in the current version of the tutorial.</span></span>  
  
1.  <span data-ttu-id="e9f71-105">Wechseln Sie zur Hauptseite **Master Data Manager** ( `http://localhost/MDS` ), indem Sie oben auf **SQL Server 2012 Master Data Services** klicken.</span><span class="sxs-lookup"><span data-stu-id="e9f71-105">Switch to the main page of **Master Data Manager** (`http://localhost/MDS`) by clicking **SQL Server 2012 Master Data Services** at the top.</span></span>  
  
2.  <span data-ttu-id="e9f71-106">Klicken Sie auf **Integrations Management**.</span><span class="sxs-lookup"><span data-stu-id="e9f71-106">Click **Integration Management**.</span></span>  
  
3.  <span data-ttu-id="e9f71-107">Klicken Sie in der Menüleiste auf **Ansichten erstellen** .</span><span class="sxs-lookup"><span data-stu-id="e9f71-107">Click **Create Views** on the menu bar.</span></span>  
  
     <span data-ttu-id="e9f71-108">![Neue Abonnementsicht hinzufügen (Schaltfläche)](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-01.jpg "Neue Abonnementsicht hinzufügen (Schaltfläche)")</span><span class="sxs-lookup"><span data-stu-id="e9f71-108">![Add a New Subscription View Button](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-01.jpg "Add a New Subscription View Button")</span></span>  
  
4.  <span data-ttu-id="e9f71-109">Klicken Sie in der Symbolleiste auf das Symbol **+ (Plus Zeichen)** , um eine Abonnement Sicht zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e9f71-109">Click **+ (Plus)** icon on the toolbar to create a subscription view.</span></span>  
  
5.  <span data-ttu-id="e9f71-110">Geben Sie im Bereich **Abonnement Sicht erstellen** den Namen **Suppliers** als **Name der Abonnement Sicht**ein.</span><span class="sxs-lookup"><span data-stu-id="e9f71-110">In the **Create Subscription View** pane, type **Suppliers** for **Subscription view name**.</span></span>  
  
6.  <span data-ttu-id="e9f71-111">Wählen Sie **Suppliers** für **Model**aus.</span><span class="sxs-lookup"><span data-stu-id="e9f71-111">Select **Suppliers** for **Model**.</span></span>  
  
7.  <span data-ttu-id="e9f71-112">Wählen Sie **VERSION_1** für die **Version**aus.</span><span class="sxs-lookup"><span data-stu-id="e9f71-112">Select **VERSION_1** for **Version**.</span></span>  
  
8.  <span data-ttu-id="e9f71-113">Wählen Sie **Lieferant** für **Entität**aus.</span><span class="sxs-lookup"><span data-stu-id="e9f71-113">Select **Supplier** for **Entity**.</span></span>  
  
9. <span data-ttu-id="e9f71-114">Wählen Sie **Blatt** Elemente für das **Format**aus.</span><span class="sxs-lookup"><span data-stu-id="e9f71-114">Select **Leaf members** for **Format**.</span></span>  
  
     <span data-ttu-id="e9f71-115">![Abonnementsicht speichern (Schaltfläche)](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-02.jpg "Abonnementsicht speichern (Schaltfläche)")</span><span class="sxs-lookup"><span data-stu-id="e9f71-115">![Save Subscription View Button](../../2014/tutorials/media/et-creatingamdssubscriptionviewusingmdm-02.jpg "Save Subscription View Button")</span></span>  
  
10. <span data-ttu-id="e9f71-116">Klicken Sie in der Symbolleiste auf **Speichern** , um die Abonnement Ansicht zu speichern.</span><span class="sxs-lookup"><span data-stu-id="e9f71-116">Click **Save** on the toolbar to save the subscription view.</span></span> <span data-ttu-id="e9f71-117">Diese Aktion erstellt eine Ansicht in SQL Server namens **Suppliers**.</span><span class="sxs-lookup"><span data-stu-id="e9f71-117">This action creates a view in SQL Server named **Suppliers**.</span></span> <span data-ttu-id="e9f71-118">Sie können dies mit SQL Server Management Studio (SSMS) überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e9f71-118">You can verify this using SQL Server Management Studio (SSMS).</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="e9f71-119">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="e9f71-119">Next Step</span></span>  
 [<span data-ttu-id="e9f71-120">Aufgabe 3 &#40;optionale&#41;: Überprüfen der Abonnement Sichten</span><span class="sxs-lookup"><span data-stu-id="e9f71-120">Task 3 &#40;Optional&#41;: Reviewing the Subscription Views</span></span>](task-3-optional-reviewing-the-subscription-views.md)  
  
  
