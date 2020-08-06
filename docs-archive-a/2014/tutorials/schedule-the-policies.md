---
title: Planen der Richtlinien | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: 59417a54-55f1-4468-ba41-368aa852c2d4
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 1bce1b9d650606e9485899c34c72ca6b27a72dae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720449"
---
# <a name="schedule-the-policies"></a><span data-ttu-id="a5858-102">Planen der Richtlinien</span><span class="sxs-lookup"><span data-stu-id="a5858-102">Schedule the Policies</span></span>
  <span data-ttu-id="a5858-103">In dieser Aufgabe planen Sie die Best Practices-Richtlinien, die Sie in der vorherigen Aufgabe importiert haben.</span><span class="sxs-lookup"><span data-stu-id="a5858-103">In this task, you will schedule the best practices policies that you imported in the previous task.</span></span>  
  
### <a name="to-schedule-the-best-practices-policies"></a><span data-ttu-id="a5858-104">So planen Sie Best Practices-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="a5858-104">To schedule the best practices policies</span></span>  
  
1.  <span data-ttu-id="a5858-105">Erweitern **Sie in**Objekt-Explorer den Knoten **Verwaltung**, erweitern Sie **Richtlinien Verwaltung**, erweitern Sie **Richtlinien**, klicken Sie mit der rechten Maustaste auf eine Richtlinie für bewährte Methoden, und klicken Sie</span><span class="sxs-lookup"><span data-stu-id="a5858-105">In Object Explorer, expand **Management**, expand **Policy Management**, expand **Policies**, right-click a best practices policy, and then click **Properties**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a5858-106">Um die Best Practices-Kategorien zu sortieren und um einfach zu erkennen, welche Richtlinien zu Best Practices zugeordnet sind, können Sie alternativ **Verwaltung**und dann **Richtlinienverwaltung**erweitern und anschließend auf **Richtlinien**klicken.</span><span class="sxs-lookup"><span data-stu-id="a5858-106">As an alternative, to easily see which policies are associated with best practices and to sort the best practices categories, expand **Management**, expand **Policy Management**, and then click **Policies**.</span></span> <span data-ttu-id="a5858-107">Klicken Sie im Menü **Ansicht** auf **Details zum Objekt-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="a5858-107">On the **View** menu, click **Object Explorer Details**.</span></span> <span data-ttu-id="a5858-108">Klicken Sie im Bereich **Details zum Objekt-Explorer** auf die Überschrift **Kategorie** , um die Richtlinien nach Kategorie zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="a5858-108">In the **Object Explorer Details** pane, click the **Category** heading to sort the policies by category.</span></span> <span data-ttu-id="a5858-109">Die Best Practices-Richtlinien sind mit dem Präfix **Microsoft Best Practices**versehen.</span><span class="sxs-lookup"><span data-stu-id="a5858-109">The best practices policies have the prefix **Microsoft Best Practices**.</span></span> <span data-ttu-id="a5858-110">Klicken Sie mit der rechten Maustaste auf die Richtlinie, die Sie konfigurieren möchten, und klicken Sie dann auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="a5858-110">Right-click the policy that you want to configure, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="a5858-111">Klicken Sie auf der Seite **Allgemein** des Dialogfelds **Richtlinie öffnen** in der Liste **Auswertungsmodus** auf **Nach Zeitplan**.</span><span class="sxs-lookup"><span data-stu-id="a5858-111">On the **General** page of the **Open Policy** dialog box, in the **Evaluation Mode** list, click **On schedule**.</span></span>  
  
3.  <span data-ttu-id="a5858-112">Klicken Sie neben dem Feld **Zeitplan** auf **Auswählen** , um einen vorhandenen Zeitplan anzugeben, oder klicken Sie auf **Neu** , um einen neuen Zeitplan zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a5858-112">Next to the **Schedule** box, click **Pick** to specify an existing schedule, or click **New** to create a new schedule.</span></span>  
  
4.  <span data-ttu-id="a5858-113">Nachdem Sie einen Zeitplan konfiguriert haben, können Sie zum Aktivieren der geplanten Richtlinie oben auf der Seite das Kontrollkästchen **Aktiviert** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a5858-113">After you have configured a schedule, you can select the **Enabled** check box near the top of the page to enable the scheduled policy.</span></span>  
  
5.  <span data-ttu-id="a5858-114">Wiederholen Sie die Schritte 1 bis 4 für jede Richtlinie, die Sie planen möchten.</span><span class="sxs-lookup"><span data-stu-id="a5858-114">Repeats steps 1 through 4 for each policy that you want to schedule.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="a5858-115">Um nach der Ausführung einer geplanten Richtlinie die Auswertungsergebnisse anzuzeigen, öffnen Sie auf der Zielinstanz das Protokoll zum Richtlinienverlauf.</span><span class="sxs-lookup"><span data-stu-id="a5858-115">To view the evaluation results after a scheduled policy runs, open the Policy History log on the target instance.</span></span> <span data-ttu-id="a5858-116">Um das Protokoll zu öffnen, klicken Sie mit der rechten Maustaste auf **Richtlinien Verwaltung**, und klicken Sie dann auf **Verlauf anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="a5858-116">To open the log, right-click **Policy Management**, and then click **View History**.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="a5858-117">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="a5858-117">Summary</span></span>  
 <span data-ttu-id="a5858-118">Sie haben geplante Richtlinien konfiguriert, die auf einer einzelnen Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a5858-118">You configured scheduled policies to run on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="a5858-119">Wenn Sie geplante Richtlinien auf mehreren Instanzen bereitstellen möchten, setzen Sie das Lernprogramm mit der nächsten Aufgabe fort.</span><span class="sxs-lookup"><span data-stu-id="a5858-119">If you want to deploy scheduled policies to multiple instances, continue to the next task in this tutorial.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="a5858-120">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a5858-120">Next Steps</span></span>  
 [<span data-ttu-id="a5858-121">Bereitstellen geplanter Richtlinien auf mehreren Instanzen</span><span class="sxs-lookup"><span data-stu-id="a5858-121">Deploy Scheduled Policies to Multiple Instances</span></span>](../../2014/tutorials/deploy-scheduled-policies-to-multiple-instances.md)  
  
  
