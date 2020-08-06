---
title: Ausführen einer bedarfsgesteuerten Auswertung mithilfe Objekt-Explorer | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: ee6d3b79-18bc-49d3-8a1d-0c0905b990f0
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: e32876978ac462af361986d84e11ef3dc0f278e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608159"
---
# <a name="perform-an-on-demand-evaluation-by-using-object-explorer"></a><span data-ttu-id="33f51-102">Ausführen einer bedarfsgesteuerten Auswertung mit dem Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="33f51-102">Perform an On-Demand Evaluation by Using Object Explorer</span></span>
  <span data-ttu-id="33f51-103">In dieser Aufgabe verwenden Sie den Objekt-Explorer, um eine bedarfsgesteuerte Auswertung von Best Practices-Richtlinien für [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] auf einer einzelnen [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Instanz auszuführen.</span><span class="sxs-lookup"><span data-stu-id="33f51-103">In this task, you will use Object Explorer to perform an on-demand evaluation of best practices policies for the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] on a single instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33f51-104">Sie können Richtlinien auch mithilfe der registrierten Server auf einer einzelnen Instanz auswerten.</span><span class="sxs-lookup"><span data-stu-id="33f51-104">You can also evaluate policies on a single instance through Registered Servers.</span></span> <span data-ttu-id="33f51-105">Weitere Informationen finden Sie unter [Ausführen einer bedarfsgesteuerten Auswertung mithilfe registrierter Server](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span><span class="sxs-lookup"><span data-stu-id="33f51-105">For more information, see [Perform an On-Demand Evaluation by Using Registered Servers](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="33f51-106">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="33f51-106">Prerequisites</span></span>  
 <span data-ttu-id="33f51-107">Diese Lektion basiert auf der von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] ausgeführten Version von [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span><span class="sxs-lookup"><span data-stu-id="33f51-107">This lesson is based on the version of [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] from [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)].</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="33f51-108">Wenn Sie eine Bedarfs gesteuerte Auswertung von Best Practices-Richtlinien für Instanzen mit ausführen möchten [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)] , müssen Sie das Verfahren im Thema [Ausführen einer bedarfsgesteuerten Auswertung mithilfe von registrierten Servern](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md)verwenden.</span><span class="sxs-lookup"><span data-stu-id="33f51-108">To perform an on-demand evaluation of best practices policies against instances that are running [!INCLUDE[ssVersion2005](../includes/ssversion2005-md.md)], you must use the procedure in the topic [Perform an On-Demand Evaluation by Using Registered Servers](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md).</span></span>  
  
### <a name="to-perform-an-on-demand-evaluation-by-using-object-explorer"></a><span data-ttu-id="33f51-109">So führen Sie eine bedarfsgesteuerte Auswertung mit dem Objekt-Explorer aus</span><span class="sxs-lookup"><span data-stu-id="33f51-109">To perform an on-demand evaluation by using Object Explorer</span></span>  
  
1.  <span data-ttu-id="33f51-110">Starten Sie [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], und stellen Sie dann eine Verbindung mit dem [!INCLUDE[ssDE](../includes/ssde-md.md)]her.</span><span class="sxs-lookup"><span data-stu-id="33f51-110">Start [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], and then connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="33f51-111">Erweitern Sie in Objekt-Explorer den Knoten **Verwaltung**, erweitern Sie **Richtlinien Verwaltung**, klicken Sie mit der rechten Maustaste auf **Richtlinien**, und klicken Sie auf **Auswerten**</span><span class="sxs-lookup"><span data-stu-id="33f51-111">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Policies**, and then click **Evaluate**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="33f51-112">Standardmäßig wird die lokale Instanz als Quelle der Richtlinien verwendet.</span><span class="sxs-lookup"><span data-stu-id="33f51-112">By default, the local instance is used as the source of the policies.</span></span> <span data-ttu-id="33f51-113">Wenn Sie zuvor Best Practices-Richtlinien importiert haben, werden diese zusammen mit anderen, von Ihnen erstellten Richtlinien aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="33f51-113">If you have previously imported best practices policies, they will be listed, together with any other policies that you have created.</span></span> <span data-ttu-id="33f51-114">Sie können alle importierten Best Practices-Richtlinien auswählen und dann auf **Auswerten**klicken.</span><span class="sxs-lookup"><span data-stu-id="33f51-114">You can select any of the imported best practices policies, and then click **Evaluate**.</span></span> <span data-ttu-id="33f51-115">Falls Sie keine Best Practices-Richtlinien importiert haben, fahren Sie mit dieser Prozedur fort.</span><span class="sxs-lookup"><span data-stu-id="33f51-115">If you have not imported the best practices policies, continue with this procedure.</span></span>  
  
3.  <span data-ttu-id="33f51-116">Klicken Sie im Dialogfeld **Richtlinien auswerten** neben dem Feld **Quelle** auf die Schaltfläche mit den Auslassungs Punkten (**...**).</span><span class="sxs-lookup"><span data-stu-id="33f51-116">In the **Evaluate Policies** dialog box, next to the **Source** box, click the ellipsis (**...**) button.</span></span>  
  
4.  <span data-ttu-id="33f51-117">Im Dialogfeld **Quelle auswählen** können Sie entweder **Dateien** oder **Server** als Quelle der auszuwertenden Richtlinien Dateien auswählen.</span><span class="sxs-lookup"><span data-stu-id="33f51-117">In the **Select Source** dialog box, you can select either **Files** or **Server** as the source of the policy files to evaluate.</span></span> <span data-ttu-id="33f51-118">Wenn Sie auf **Server**klicken, können Sie eine Bedarfs gesteuerte Auswertung aller Best Practices-Richtlinien durchführen, die zuvor in die Richtlinien basierte Verwaltung auf einem lokalen Server oder Remote Server importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="33f51-118">If you click **Server**, you can perform an on-demand evaluation of any best practices policies that were previously imported into Policy-Based Management on a local or remote server.</span></span> <span data-ttu-id="33f51-119">In diesem Tutorial klicken Sie auf **Dateien**und wählen dann die einzelnen Richtlinien Dateien aus, die Sie auswerten möchten.</span><span class="sxs-lookup"><span data-stu-id="33f51-119">In this tutorial, you will click **Files**, and then select the individual policy files that you want to evaluate.</span></span> <span data-ttu-id="33f51-120">Gehen Sie hierzu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="33f51-120">To do this, follow these steps:</span></span>  
  
    1.  <span data-ttu-id="33f51-121">Klicken Sie auf **Dateien**.</span><span class="sxs-lookup"><span data-stu-id="33f51-121">Click **Files**.</span></span>  
  
    2.  <span data-ttu-id="33f51-122">Klicken Sie neben **Dateien**auf die Schaltfläche mit den Auslassungs Punkten (**...**).</span><span class="sxs-lookup"><span data-stu-id="33f51-122">Next to **Files**, click the ellipsis (**...**) button.</span></span>  
  
    3.  <span data-ttu-id="33f51-123">Navigieren Sie im Dialogfeld **Richtlinie auswählen** zum folgenden Ordner, in dem die Best Practices-Richtlinien enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="33f51-123">In the **Select Policy** dialog box, browse to the following folder, which contains the best practices policies:</span></span>  
  
         <span data-ttu-id="33f51-124">**C:\Programme (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span><span class="sxs-lookup"><span data-stu-id="33f51-124">**C:\Program Files (x86)\Microsoft SQL Server\110\Tools\Policies\DatabaseEngine\1033**</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="33f51-125">Abhängig davon, wo die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Programmdateien installiert sind, ob ein 32-Bit- oder 64-Bit-Betriebssystem ausgeführt bzw. ein Sprachbezeichner verwendet wird, kann sich der Dateipfad ändern.</span><span class="sxs-lookup"><span data-stu-id="33f51-125">The file path may vary, depending on where you installed the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] program files, whether you are running a 32-bit or 64-bit operating system, and the language identifier.</span></span>  
  
    4.  <span data-ttu-id="33f51-126">Wählen Sie eine oder mehrere XML-Richtlinien Dateien aus, die ausgewertet werden sollen, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="33f51-126">Select one or more .xml policy files to evaluate, and then click **Open**.</span></span>  
  
         <span data-ttu-id="33f51-127">Die Liste der ausgewählten Dateien wird im Feld **Dateien** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33f51-127">The list of selected files appears in the **Files** box.</span></span>  
  
    5.  <span data-ttu-id="33f51-128">Klicken Sie im Dialogfeld **Quelle auswählen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="33f51-128">In the **Select Source** dialog box, click **OK**.</span></span>  
  
    6.  <span data-ttu-id="33f51-129">Wenn das Dialogfeld **Richtlinien laden** angezeigt wird, klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="33f51-129">If the **Loading Policies** dialog box appears, click **Close**.</span></span>  
  
     <span data-ttu-id="33f51-130">Die Richtlinien, die Sie ausgewählt haben, werden auf der Seite **Richtlinien Auswahl** aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="33f51-130">The policies that you selected are listed on the **Policy Selection** page.</span></span> <span data-ttu-id="33f51-131">Ein Warnsymbol neben einer Richtlinie weist darauf hin, dass die Richtlinie Skripts enthält.</span><span class="sxs-lookup"><span data-stu-id="33f51-131">Be aware that a warning icon next to a policy indicates that the policy contains scripts.</span></span>  
  
5.  <span data-ttu-id="33f51-132">Klicken Sie auf **Auswerten** , um die Richtlinien auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="33f51-132">Click **Evaluate** to evaluate the policies.</span></span>  
  
     <span data-ttu-id="33f51-133">In der **Ergebnis** Tabelle werden die Ergebnisse für jede Richtlinie aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="33f51-133">In the **Results** table, the results for each policy are listed.</span></span> <span data-ttu-id="33f51-134">Ein rotes "x"-Symbol gibt an, dass die Richtlinie nicht eingehalten wurde.</span><span class="sxs-lookup"><span data-stu-id="33f51-134">A red "x" icon indicates that policy compliance failed.</span></span>  
  
6.  <span data-ttu-id="33f51-135">Bei einigen Richtlinienfehlern ermöglicht die richtlinienbasierte Verwaltung Ihnen, sofortige Richtlinieneinhaltung auf dem Ziel zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="33f51-135">For some policy failures, Policy-Based Management enables you to immediately enforce policy compliance on the target.</span></span> <span data-ttu-id="33f51-136">Im Fall eines solchen Fehlers wird ein Kontrollkästchen neben der fehlerhaften Richtlinie angezeigt.</span><span class="sxs-lookup"><span data-stu-id="33f51-136">For such failures, a check box will appear next to the failed policy.</span></span> <span data-ttu-id="33f51-137">Wenn Sie das Kontrollkästchen aktivieren, wird die Schaltfläche **anwenden** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="33f51-137">If you select the check box, the **Apply** button becomes available.</span></span> <span data-ttu-id="33f51-138">Wenn Sie auf **anwenden**klicken, wird die nicht kompatible Einstellung automatisch auf der Ziel Instanz aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="33f51-138">When you click **Apply**, the noncompliant setting will be automatically updated on the target instance.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="33f51-139">Bevor Sie eine Zielinstanz automatisch aktualisieren, sollten Sie die Richtlinieneinstellung vollständig verstanden haben.</span><span class="sxs-lookup"><span data-stu-id="33f51-139">Make sure that you fully understand the policy setting before automatically updating a target instance.</span></span> <span data-ttu-id="33f51-140">Wir empfehlen, dass Sie nach dem Aktivieren eines oder mehrerer Kontrollkästchen auf **Skript**klicken und einen Ausgabe Speicherort auswählen, damit Sie den zugrunde liegenden Code überprüfen können, [!INCLUDE[tsql](../includes/tsql-md.md)] bevor Sie die Änderungen anwenden.</span><span class="sxs-lookup"><span data-stu-id="33f51-140">We recommend that after you select one or more check boxes, you click **Script**, and choose an output location so that you can review the underlying [!INCLUDE[tsql](../includes/tsql-md.md)] code before you apply the changes.</span></span>  
  
7.  <span data-ttu-id="33f51-141">Um ausführliche Ergebnisse für eine Richtlinie anzuzeigen, klicken Sie auf die Richtlinie in der Tabelle **Ergebnisse** .</span><span class="sxs-lookup"><span data-stu-id="33f51-141">To view detailed results for a policy, click the policy in the **Results** table.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="33f51-142">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="33f51-142">Next Task in Lesson</span></span>  
 [<span data-ttu-id="33f51-143">Ausführen einer bedarfsgesteuerten Auswertung mithilfe von registrierten Servern</span><span class="sxs-lookup"><span data-stu-id="33f51-143">Perform an On-Demand Evaluation by Using Registered Servers</span></span>](../../2014/tutorials/perform-an-on-demand-evaluation-by-using-registered-servers.md)  
  
  
