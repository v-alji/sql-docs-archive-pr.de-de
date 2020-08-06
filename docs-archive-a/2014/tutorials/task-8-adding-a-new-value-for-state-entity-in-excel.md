---
title: 'Aufgabe 8: Hinzufügen eines neuen Werts für die Entität "State" in Excel | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: a763d76b-06a3-4d51-9614-01fc9fb1c158
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: cace99419997e48088420c331a823cdf3639a3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719003"
---
# <a name="task-8-adding-a-new-value-for-state-entity-in-excel"></a><span data-ttu-id="1a337-102">Aufgabe 8: Hinzufügen eines neuen Werts für die Entität „State“ in Excel</span><span class="sxs-lookup"><span data-stu-id="1a337-102">Task 8: Adding a New Value for State Entity in Excel</span></span>
  <span data-ttu-id="1a337-103">In dieser Aufgabe fügen Sie einen Wert für die Entität "State" in Excel hinzu und veröffentlichen die Änderung auf dem MDS-Server.</span><span class="sxs-lookup"><span data-stu-id="1a337-103">In this task, you add a value for the State entity in Excel and publish the change to the MDS server.</span></span>  
  
1.  <span data-ttu-id="1a337-104">Fügen Sie ein **Arbeitsblatt** in Excel hinzu, indem Sie unten auf die Registerkarte Neu klicken.</span><span class="sxs-lookup"><span data-stu-id="1a337-104">Add a **work sheet** in Excel by clicking the new tab at the bottom.</span></span>  
  
     <span data-ttu-id="1a337-105">![Excel – Neues Arbeitsblatt (Registerkarte)](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-01.jpg "Excel – Neues Arbeitsblatt (Registerkarte)")</span><span class="sxs-lookup"><span data-stu-id="1a337-105">![Excel - New Worksheet Tab](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-01.jpg "Excel - New Worksheet Tab")</span></span>  
  
2.  <span data-ttu-id="1a337-106">Klicken Sie in **Excel**im Menü auf die Registerkarte **Master Daten** , und klicken Sie dann auf dem Menüband auf **Explorer anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="1a337-106">In **Excel**, click the **Master Data** tab on the menu, and then click **Show Explorer** on the ribbon.</span></span>  
  
3.  <span data-ttu-id="1a337-107">Wählen Sie im **Master Daten-Explorer** **Suppliers** für **Model**aus.</span><span class="sxs-lookup"><span data-stu-id="1a337-107">In the **Master Data Explorer**, select **Suppliers** for **Model**.</span></span> <span data-ttu-id="1a337-108">Es sollten zwei Entitäten angezeigt werden: **Supplier** und **State** in der Liste der Entitäten.</span><span class="sxs-lookup"><span data-stu-id="1a337-108">You should see two entities: **Supplier** and **State** in the entity list.</span></span>  
  
4.  <span data-ttu-id="1a337-109">Doppelklicken Sie in der Liste auf **Zustand** .</span><span class="sxs-lookup"><span data-stu-id="1a337-109">Double-click **State** in the list.</span></span> <span data-ttu-id="1a337-110">Alle Member der **State** -Entität aus MDS sollten im Arbeitsblatt angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1a337-110">All the members of the **State** entity from MDS should be displayed in the worksheet.</span></span>  
  
5.  <span data-ttu-id="1a337-111">Fügen Sie nun eine Zeile am Ende mit den folgenden Werten hinzu: **North Carolina** für **Name** und **NC** für **Code**.</span><span class="sxs-lookup"><span data-stu-id="1a337-111">Now, add a row at the end with the following values: **North Carolina** for **Name** and **NC** for **Code**.</span></span> <span data-ttu-id="1a337-112">Die Farbcodierung unterscheidet alle neuen/aktualisierten Datensätze von den anderen Datensätzen.</span><span class="sxs-lookup"><span data-stu-id="1a337-112">The color coding differentiates any new/updated records from the other records.</span></span>  
  
     <span data-ttu-id="1a337-113">![Excel – Hinzufügen von North Carolina zu Bundesstaaten](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-02.jpg "Excel – Hinzufügen von North Carolina zu Bundesstaaten")</span><span class="sxs-lookup"><span data-stu-id="1a337-113">![Excel - Add North Carolina to States](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-02.jpg "Excel - Add North Carolina to States")</span></span>  
  
6.  <span data-ttu-id="1a337-114">Klicken Sie im Menüband auf **veröffentlichen** , um die Änderung in MDS zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="1a337-114">Click **Publish** on the ribbon to publish the change to MDS.</span></span>  
  
     <span data-ttu-id="1a337-115">![Excel – Schaltfläche "Veröffentlichen" auf der Registerkarte "Masterdaten"](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-03.jpg "Excel – Schaltfläche "Veröffentlichen" auf der Registerkarte "Masterdaten"")</span><span class="sxs-lookup"><span data-stu-id="1a337-115">![Excel - Publish Button on Master Data Tab](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-03.jpg "Excel - Publish Button on Master Data Tab")</span></span>  
  
7.  <span data-ttu-id="1a337-116">Beachten Sie, dass im Dialogfeld **veröffentlichen und mit Anmerkung** versehen die Option **dieselbe Anmerkung für alle Änderungen verwenden** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="1a337-116">On the **Publish and Annotate** dialog box, notice that the **Use same annotation for all changes** is selected.</span></span> <span data-ttu-id="1a337-117">Hier können Sie eine einzige Anmerkung für alle Änderungen eingeben.</span><span class="sxs-lookup"><span data-stu-id="1a337-117">You can enter a single annotation for all the changes here.</span></span>  
  
8.  <span data-ttu-id="1a337-118">Wählen Sie die Option **Änderungen überprüfen und Anmerkungen einzeln bereitstellen** aus, um eine Anmerkung für jede Änderung bereitzustellen (in diesem Fall nur eine).</span><span class="sxs-lookup"><span data-stu-id="1a337-118">Select **Review changes and provide annotations individually** option to provide annotation for each change (in this case, only one).</span></span>  
  
     <span data-ttu-id="1a337-119">![Excel – Veröffentlichen und mit Anmerkung versehen (Dialogfeld)](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-04.jpg "Excel – Veröffentlichen und mit Anmerkung versehen (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="1a337-119">![Excel - Publish and Annotate Dialog Box](../../2014/tutorials/media/et-addinganewvalueforstateentityinexcel-04.jpg "Excel - Publish and Annotate Dialog Box")</span></span>  
  
9. <span data-ttu-id="1a337-120">Klicken Sie auf **veröffentlichen** , um die Daten in MDS zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="1a337-120">Click **Publish** to publish data to MDS.</span></span>  
  
10. <span data-ttu-id="1a337-121">Beachten Sie, dass die **Farbcodierung** für die Zeile mit **North Carolina** als **Zustand** mit anderen Datensätzen übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="1a337-121">Notice that **color coding** for the row with **North Carolina** as the **State** is same as other records now.</span></span>  
  
11. <span data-ttu-id="1a337-122">**Optional:** Überprüfen Sie, ob das neue Element (NC) zur Entität **State** hinzugefügt wird, indem Sie den **Explorer** in **Master Data Manager**verwenden.</span><span class="sxs-lookup"><span data-stu-id="1a337-122">**Optional:** Verify that the new member (NC) is added to the **State** entity by using the **Explorer** in **Master Data Manager**.</span></span>  
  
12. <span data-ttu-id="1a337-123">Klicken Sie in Excel im unteren Bereich mit der rechten Maustaste auf das Arbeitsblatt **State** , und klicken Sie auf **Löschen** , um das Arbeitsblatt zu löschen.</span><span class="sxs-lookup"><span data-stu-id="1a337-123">In Excel, right-click the **State** worksheet at the bottom, and click **Delete** to delete the worksheet.</span></span> <span data-ttu-id="1a337-124">Durch Löschen des Arbeitsblatts werden keine Daten vom MDS-Server gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1a337-124">Deleting the worksheet does not delete any data from the MDS server.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="1a337-125">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="1a337-125">Next Step</span></span>  
 [<span data-ttu-id="1a337-126">Aufgabe 9: Erstellen einer abgeleiteten Hierarchie mithilfe des Master Data Manager</span><span class="sxs-lookup"><span data-stu-id="1a337-126">Task 9: Creating a Derived Hierarchy using Master Data Manager</span></span>](../../2014/tutorials/task-9-creating-a-derived-hierarchy-using-master-data-manager.md)  
  
  
