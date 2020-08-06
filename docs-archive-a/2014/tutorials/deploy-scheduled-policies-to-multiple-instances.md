---
title: Bereitstellen geplanter Richtlinien auf mehreren Instanzen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: f551b8e8-3668-4ed4-852f-bae826254f4f
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: 30faf94c2033be43ac035517e58d5a18c0c68ab8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696345"
---
# <a name="deploy-scheduled-policies-to-multiple-instances"></a><span data-ttu-id="61969-102">Bereitstellen geplanter Richtlinien auf mehreren Instanzen</span><span class="sxs-lookup"><span data-stu-id="61969-102">Deploy Scheduled Policies to Multiple Instances</span></span>
  <span data-ttu-id="61969-103">Mithilfe von registrierten Servern können Sie geplante Richtlinien von einem zentralen Ort aus auf verwalteten Servern bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="61969-103">By using Registered Servers, you can deploy scheduled policies to managed servers from a central location.</span></span> <span data-ttu-id="61969-104">Sie können geplante Richtlinien entweder über eine lokale Servergruppe oder über einen zentralen Verwaltungsserver bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="61969-104">You can deploy scheduled policies from either a local server group, or from a Central Management Server.</span></span>  
  
 <span data-ttu-id="61969-105">Dabei führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="61969-105">In this task, you will do the following:</span></span>  
  
1.  <span data-ttu-id="61969-106">Exportieren Sie die Richtlinien, die Sie in der vorherigen Aufgabe geplant haben, in einen Ordner.</span><span class="sxs-lookup"><span data-stu-id="61969-106">Export the policies that you scheduled in the previous task to a folder.</span></span>  
  
2.  <span data-ttu-id="61969-107">Stellen Sie die geplanten Richtlinien auf Zielinstanzen bereit, die über registrierte Server verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="61969-107">Deploy the scheduled policies to target instances that are managed through Registered Servers.</span></span>  
  
 <span data-ttu-id="61969-108">Sie führen diese Aufgaben auf dem Computer durch, auf dem Sie auch die vorherigen Aufgaben dieser Lektion durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="61969-108">You will perform these tasks on the computer where you completed the previous tasks in this lesson.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="61969-109">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="61969-109">Prerequisites</span></span>  
 <span data-ttu-id="61969-110">Für diese Aufgabe gelten die folgenden Voraussetzungen:</span><span class="sxs-lookup"><span data-stu-id="61969-110">This task has the following prerequisites:</span></span>  
  
-   <span data-ttu-id="61969-111">Sie müssen die vorherigen Aufgaben dieser Lektion abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="61969-111">You must have completed the previous tasks in this lesson.</span></span>  
  
-   <span data-ttu-id="61969-112">Auf den Instanzen, auf denen Sie die geplanten Richtlinien bereitstellen möchten, muss [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] oder eine höhere Version ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="61969-112">The instances where you want to deploy the scheduled policies must be running [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] or a later version.</span></span> <span data-ttu-id="61969-113">Die Automatisierung erfordert, dass die Richtlinien lokal gespeichert werden. Dies wird für ältere [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Versionen als [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="61969-113">Automation requires the policies to be stored locally, which is not supported on versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)].</span></span>  
  
-   <span data-ttu-id="61969-114">Die Server, auf denen Sie die geplanten Richtlinien bereitstellen möchten, müssen in den registrierten Servern entweder in den **lokalen Server Gruppen** oder im Knoten für **zentrale Verwaltungs Server** registriert sein.</span><span class="sxs-lookup"><span data-stu-id="61969-114">The servers where you want to deploy the scheduled policies must be registered in Registered Servers in either the **Local Server Groups** or the **Central Management Servers** node.</span></span> <span data-ttu-id="61969-115">Weitere Informationen finden Sie unter den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="61969-115">For more information, see the following topics:</span></span>  
  
    -   [<span data-ttu-id="61969-116">Erstellen oder Bearbeiten einer Servergruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="61969-116">Create or Edit a Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-or-edit-a-server-group-sql-server-management-studio.md)  
  
    -   <span data-ttu-id="61969-117">[Registrieren Sie einen verbundenen Server &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span><span class="sxs-lookup"><span data-stu-id="61969-117">[Register a Connected Server &#40;SQL Server Management Studio&#41;](../ssms/register-servers/register-a-connected-server-sql-server-management-studio.md).</span></span>  
  
    -   [<span data-ttu-id="61969-118">Erstellen eines zentralen Verwaltungsservers und einer Servergruppe &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="61969-118">Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;</span></span>](../ssms/register-servers/create-a-central-management-server-and-server-group.md)  
  
### <a name="to-export-the-scheduled-policies-as-xml-files"></a><span data-ttu-id="61969-119">So exportieren Sie die geplanten Richtlinien als XML-Dateien</span><span class="sxs-lookup"><span data-stu-id="61969-119">To export the scheduled policies as .xml files</span></span>  
  
1.  <span data-ttu-id="61969-120">Erweitern Sie auf dem Server, auf dem Sie in der vorherigen Aufgabe geplante Richtlinien konfiguriert haben, **Verwaltung**, **Richtlinien Verwaltung**, und klicken Sie dann auf **Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="61969-120">On the server where you configured scheduled policies in the previous task, expand **Management**, expand **Policy Management**, and then click **Policies**.</span></span>  
  
2.  <span data-ttu-id="61969-121">Klicken Sie im Menü **Ansicht** auf **Details zum Objekt-Explorer**.</span><span class="sxs-lookup"><span data-stu-id="61969-121">On the **View** menu, click **Object Explorer Details**.</span></span>  
  
3.  <span data-ttu-id="61969-122">Wählen Sie im Bereich **Objekt-Explorer Details** alle geplanten Best Practices-Richtlinien aus, die Sie auf anderen Servern über registrierte Server bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="61969-122">In the **Object Explorer Details** pane, select all the scheduled best practices policies that you want to deploy to other servers through Registered Servers.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61969-123">Sie können auf die Überschrift der **Kategorie** klicken, um die Richtlinien nach Kategorie zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="61969-123">You can click the **Category** heading to sort the policies by category.</span></span>  
  
4.  <span data-ttu-id="61969-124">Klicken Sie mit der rechten Maustaste auf die Auswahl, und klicken Sie auf **Richtlinie exportieren**.</span><span class="sxs-lookup"><span data-stu-id="61969-124">Right-click the selection, and then click **Export Policy**.</span></span>  
  
5.  <span data-ttu-id="61969-125">Wenn Sie mehrere Richtlinien für den Export ausgewählt haben, wählen Sie im Dialogfeld **Ordner suchen** einen Zielordner aus, oder erstellen Sie einen neuen Ordner.</span><span class="sxs-lookup"><span data-stu-id="61969-125">If you selected multiple policies to export, in the **Browse For Folder** dialog box, select a destination folder, or create a new folder.</span></span> <span data-ttu-id="61969-126">Erstellen Sie für diese Lektion einen neuen Ordner mit dem Pfad **c:\ Scheduled_BP_Policies**, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="61969-126">For this lesson, create a new folder with the path **C:\Scheduled_BP_Policies**, and then click **OK**.</span></span>  
  
     <span data-ttu-id="61969-127">Wenn Sie nur eine Richtlinie für den Export ausgewählt haben, erstellen Sie im Dialogfeld **Richtlinie exportieren** einen neuen Ordner mit dem Pfad **c:\ Scheduled_BP_Policies**, klicken Sie auf **Öffnen**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="61969-127">If you only selected one policy to export, in the **Export Policy** dialog box, create a new folder with the path **C:\Scheduled_BP_Policies**, click **Open**, and then click **Save**.</span></span>  
  
     <span data-ttu-id="61969-128">Die XML-Richtliniendateien werden am Speicherort des Ordners erstellt.</span><span class="sxs-lookup"><span data-stu-id="61969-128">The .xml policy files are created in the folder location.</span></span>  
  
### <a name="to-deploy-the-scheduled-policies-to-servers-that-are-managed-through-registered-servers"></a><span data-ttu-id="61969-129">So stellen Sie die geplanten Richtlinien auf Servern bereit, die über registrierte Server verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="61969-129">To deploy the scheduled policies to servers that are managed through Registered Servers</span></span>  
  
1.  <span data-ttu-id="61969-130">Klicken Sie im Menü **Ansicht** auf **Registrierte Server**.</span><span class="sxs-lookup"><span data-stu-id="61969-130">On the **View** menu, click **Registered Servers**.</span></span>  
  
2.  <span data-ttu-id="61969-131">Erweitern Sie **Datenbank-Engine**, erweitern Sie entweder **lokale Server Gruppen** oder **zentrale Verwaltungs Server**, klicken Sie mit der rechten Maustaste auf den Knoten, für den Sie die Richtlinien bereitstellen möchten, und klicken Sie dann auf **Richtlinien importieren**.</span><span class="sxs-lookup"><span data-stu-id="61969-131">Expand **Database Engine**, expand either **Local Server Groups** or **Central Management Servers**, right-click the node that you want to deploy the policies to, and then click **Import Policies**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61969-132">Wenn Sie mit der rechten Maustaste auf **lokale Server Gruppen** oder den zentralen Verwaltungs Server selbst klicken, werden die Richtlinien auf allen verwalteten Servern bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="61969-132">If you right-click **Local Server Groups** or the Central Management Server itself, the policies will be deployed to all managed servers.</span></span> <span data-ttu-id="61969-133">Falls Sie mit der rechten Maustaste auf eine bestimmte Servergruppe klicken, werden die Richtlinien nur auf den Servern dieser Gruppe bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="61969-133">If you right-click a specific server group, the policies will only be deployed to servers in that group.</span></span> <span data-ttu-id="61969-134">Falls Sie mit der rechten Maustaste auf einen bestimmten registrierten Server klicken, werden die Richtlinien nur auf diesem Server bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="61969-134">If you right-click a specific registered server, the policies will only be deployed to that server.</span></span>  
  
3.  <span data-ttu-id="61969-135">Klicken Sie neben zu **importierende Dateien**auf die Schaltfläche mit den Auslassungs Punkten (**...**).</span><span class="sxs-lookup"><span data-stu-id="61969-135">Next to **Files to import**, click the ellipsis button (**...**).</span></span>  
  
4.  <span data-ttu-id="61969-136">Navigieren Sie im Dialogfeld **Richtlinie auswählen** zum Speicherort des Ordners, in dem Sie die geplanten Richtlinien gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="61969-136">In the **Select Policy** dialog box, browse to the folder location where you saved the scheduled policies.</span></span> <span data-ttu-id="61969-137">Navigieren Sie in diesem Beispiel zum Speicherort **c:\ Scheduled_BP_Policies**.</span><span class="sxs-lookup"><span data-stu-id="61969-137">For this example, browse to the location **C:\Scheduled_BP_Policies**.</span></span>  
  
5.  <span data-ttu-id="61969-138">Wählen Sie die Richtlinien aus, die Sie in die Ziel Instanzen importieren möchten, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="61969-138">Select the policies that you want to import to the target instances, and then click **Open**.</span></span>  
  
6.  <span data-ttu-id="61969-139">Wählen Sie im Dialogfeld **importieren** in der Liste **Richtlinien Status** den gewünschten Richtlinien Status aus.</span><span class="sxs-lookup"><span data-stu-id="61969-139">In the **Import** dialog box, in the **Policy state** list, select the desired policy state.</span></span> <span data-ttu-id="61969-140">Sie können wählen, ob Sie den Richtlinienstatus beim Importieren beibehalten oder die Richtlinien aktivieren bzw. deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="61969-140">You can choose to preserve the policy state, enable, or disable the policies on import.</span></span> <span data-ttu-id="61969-141">Denken Sie daran, dass die Richtlinien aktiviert sein müssen, wenn sie nach einem Zeitplan ausgeführt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="61969-141">Be aware that the policies must be enabled to run on a schedule.</span></span>  
  
7.  <span data-ttu-id="61969-142">Klicken Sie auf **OK** , um die Richtlinien in alle Ziel Instanzen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="61969-142">Click **OK** to import the policies to all the target instances.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61969-143">Wenn Fehler auftreten, wird das Dialogfeld **importieren** nicht ausgeblendet.</span><span class="sxs-lookup"><span data-stu-id="61969-143">If there are any errors, the **Import** dialog box does not disappear.</span></span> <span data-ttu-id="61969-144">Klicken Sie auf die Seite **Protokoll** , um die Meldungen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="61969-144">Click the **Log** page to review the messages.</span></span> <span data-ttu-id="61969-145">Klicken Sie auf **Abbrechen**, um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="61969-145">Click **Cancel** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="61969-146">Um die Richtlinien von einer Ziel Instanz anzuzeigen, stellen Sie eine Verbindung mit der Instanz her, öffnen Sie Objekt-Explorer, erweitern Sie **Verwaltung**, und erweitern Sie dann **Richtlinien**.</span><span class="sxs-lookup"><span data-stu-id="61969-146">To view the policies from a target instance, connect to the instance, open Object Explorer, expand **Management**, and then expand **Policies**.</span></span> <span data-ttu-id="61969-147">Die importierten Richtlinien sollten im Knoten **Richtlinien** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="61969-147">You should see the imported policies in the **Policies** node.</span></span> <span data-ttu-id="61969-148">Sie können jeweils den Zeitplan anzeigen, indem Sie auf die einzelnen Richtlinien doppelklicken, oder Sie können die Einstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="61969-148">If you double-click each policy, you can view the schedule, or change the settings.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="61969-149">Um nach der Ausführung einer geplanten Richtlinie die Auswertungsergebnisse anzuzeigen, öffnen Sie auf der Zielinstanz das Protokoll zum Richtlinienverlauf.</span><span class="sxs-lookup"><span data-stu-id="61969-149">To view the evaluation results after a scheduled policy runs, open the Policy History log on the target instance.</span></span> <span data-ttu-id="61969-150">Um das Protokoll zu öffnen, klicken Sie mit der rechten Maustaste auf **Richtlinien Verwaltung**, und klicken Sie dann auf **Verlauf anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="61969-150">To open the log, right-click **Policy Management**, and then click **View History**.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="61969-151">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="61969-151">Summary</span></span>  
 <span data-ttu-id="61969-152">In diesem Lernprogramm wurde gezeigt, wie Sie für eine oder mehrere Instanzen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] bedarfsgesteuerte und geplante Auswertungen der Best Practices-Richtlinien durchführen.</span><span class="sxs-lookup"><span data-stu-id="61969-152">This tutorial has shown you how to perform both on-demand and scheduled evaluations of the best practices policies against one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="next"></a><span data-ttu-id="61969-153">Nächste</span><span class="sxs-lookup"><span data-stu-id="61969-153">Next</span></span>  
 <span data-ttu-id="61969-154">Dieses Lernprogramm ist beendet.</span><span class="sxs-lookup"><span data-stu-id="61969-154">This tutorial is finished.</span></span> <span data-ttu-id="61969-155">Um zum Anfang zurückzukehren, lesen Sie [Tutorial: auswerten bewährter Methoden mithilfe der Richtlinien basierten Verwaltung](../../2014/tutorials/tutorial-evaluating-best-practices-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="61969-155">To return to the start, see [Tutorial: Evaluating Best Practices by Using Policy-Based Management](../../2014/tutorials/tutorial-evaluating-best-practices-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="61969-156">Um eine Liste der [!INCLUDE[ssDE](../includes/ssde-md.md)] Tutorials anzuzeigen, klicken Sie auf [Datenbank-Engine Tutorials](../relational-databases/database-engine-tutorials.md).</span><span class="sxs-lookup"><span data-stu-id="61969-156">To see a list of [!INCLUDE[ssDE](../includes/ssde-md.md)] tutorials, click [Database Engine Tutorials](../relational-databases/database-engine-tutorials.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61969-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="61969-157">See Also</span></span>  
 [<span data-ttu-id="61969-158">Verwalten von Servern mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="61969-158">Administer Servers by Using Policy-Based Management</span></span>](../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
