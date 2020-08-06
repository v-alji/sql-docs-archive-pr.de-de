---
title: 'Aufgabe 6: Importieren von Werten aus dem Projekt zum Bereinigen der Lieferantenliste | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: fec0deef-a729-4ff1-b709-72d2b3f407ac
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b674cfb42ddf31c3b903a465d1be1b04e9a355ab
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609585"
---
# <a name="task-6-importing-values-from-the-cleanse-supplier-list-project"></a><span data-ttu-id="19205-102">Aufgabe 6: Importieren von Werten aus dem Cleanse Supplier List-Projekt</span><span class="sxs-lookup"><span data-stu-id="19205-102">Task 6: Importing Values from the Cleanse Supplier List Project</span></span>
  <span data-ttu-id="19205-103">In dieser Aufgabe importieren Sie während des Bereinigungsprozesses gesammeltes Data Quality-Wissen.</span><span class="sxs-lookup"><span data-stu-id="19205-103">In this task, you import the data quality knowledge gathered during the cleansing process.</span></span> <span data-ttu-id="19205-104">Weitere Informationen finden Sie im Thema Importieren von Bereinigungs [Projekt Werten in eine Domäne](https://msdn.microsoft.com/library/hh479581.aspx) .</span><span class="sxs-lookup"><span data-stu-id="19205-104">See [Importing Cleansing Project Values into a Domain](https://msdn.microsoft.com/library/hh479581.aspx) topic for more details.</span></span> <span data-ttu-id="19205-105">Sie exportieren die Wissensdatenbank auch in eine DQS-Datei, bevor Sie die aktualisierte Wissensdatenbank **Suppliers** veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="19205-105">You also export the knowledge base into a DQS file before publishing the updated **Suppliers** knowledge base.</span></span>  
  
1.  <span data-ttu-id="19205-106">Klicken Sie auf der **DQS-Client**-Hauptseite auf den **Pfeil nach rechts** neben **Suppliers** unter **zuletzt verwendete Wissensdatenbanken** , und klicken Sie dann auf **Domänen Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="19205-106">In the main page of **DQS Client**, click **right-arrow** next to **Suppliers** under **Recent Knowledge Bases** and click **Domain Management**.</span></span>  
  
2.  <span data-ttu-id="19205-107">Klicken Sie in der Liste der Domänen auf **Kontakt-e-Mail** , und wechseln Sie im rechten Bereich zur Registerkarte **Domänen Werte** .</span><span class="sxs-lookup"><span data-stu-id="19205-107">Click **Contact Email** in the list of domains, and switch to the **Domain Values** tab in the right pane.</span></span>  
  
3.  <span data-ttu-id="19205-108">Klicken Sie auf der Symbolleiste neben dem Symbol **Werte importieren** auf den **Pfeil nach unten** , und klicken Sie auf **Projektwerte importieren**.</span><span class="sxs-lookup"><span data-stu-id="19205-108">Click **down arrow** next to the **Import Values** icon on the toolbar and click **Import Project Values**.</span></span>  
  
     <span data-ttu-id="19205-109">![Projektwerte importieren (Symbolleistenschaltfläche)](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-01.jpg "Projektwerte importieren (Symbolleistenschaltfläche)")</span><span class="sxs-lookup"><span data-stu-id="19205-109">![Import Project Values Toolbar Button](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-01.jpg "Import Project Values Toolbar Button")</span></span>  
  
4.  <span data-ttu-id="19205-110">Wählen Sie im Dialogfeld **Projektwerte importieren** das Projekt " **Lieferantenliste** bereinigen" aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="19205-110">In the **Import Project Values** dialog box, select the **Cleanse Supplier List** project, and click **OK**.</span></span>  
  
5.  <span data-ttu-id="19205-111">Beachten Sie, dass alle E-Mails zusammen mit den beiden Korrekturen importiert werden, die Sie während der interaktiven Bereinigung durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="19205-111">Notice that all the emails are imported along with the two corrections you did during interactive cleansing.</span></span> <span data-ttu-id="19205-112">Führen Sie einen Bildlauf durch, um die beiden Korrekturen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="19205-112">Scroll to see the two corrections.</span></span>  
  
    |<span data-ttu-id="19205-113">Wert</span><span class="sxs-lookup"><span data-stu-id="19205-113">Value</span></span>|<span data-ttu-id="19205-114">Korrigieren in</span><span class="sxs-lookup"><span data-stu-id="19205-114">Correct To</span></span>|  
    |-----------|----------------|  
    |bobby0@adventure-work.com|bobby0@adventure-works.com|  
    |tad0@adventure-work.com|tad0@adventure-works.com|  
  
6.  <span data-ttu-id="19205-115">Wiederholen Sie den vorherigen Schritt zum Importieren von Projekt Werten für die Domäne **Country** , und beachten Sie, dass ein neuer Eintrag für die Korrektur von **United State** in **USA** (mit "s") hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="19205-115">Repeat the previous step of importing project values for the **Country** domain and notice that a new entry is added for correcting **United State** to **United States** (with 's').</span></span>  
  
    |<span data-ttu-id="19205-116">Wert</span><span class="sxs-lookup"><span data-stu-id="19205-116">Value</span></span>|<span data-ttu-id="19205-117">Korrigieren in</span><span class="sxs-lookup"><span data-stu-id="19205-117">Correct To</span></span>|  
    |-----------|----------------|  
    |<span data-ttu-id="19205-118">United State</span><span class="sxs-lookup"><span data-stu-id="19205-118">United State</span></span>|<span data-ttu-id="19205-119">USA</span><span class="sxs-lookup"><span data-stu-id="19205-119">United States</span></span>|  
  
7.  <span data-ttu-id="19205-120">Um die alten Domänen Werte anzuzeigen, deaktivieren Sie das Kontrollkästchen **nur neue anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="19205-120">To see the old domain values, clear **Show Only New** checkbox.</span></span>  
  
8.  <span data-ttu-id="19205-121">Wiederholen Sie den vorherigen Schritt zum Importieren von Projekt Werten für die Domäne **Supplier Name** .</span><span class="sxs-lookup"><span data-stu-id="19205-121">Repeat the previous step of importing project values for the **Supplier Name** domain.</span></span> <span data-ttu-id="19205-122">Standardmäßig werden nach dem Import nur die neuen Werte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="19205-122">By default, after importing, you will only see the new values.</span></span> <span data-ttu-id="19205-123">Um alle Werte anzuzeigen, deaktivieren Sie das Kontrollkästchen **nur neue anzeigen** .</span><span class="sxs-lookup"><span data-stu-id="19205-123">To see all the values, clear **Show Only New** check box.</span></span> <span data-ttu-id="19205-124">Sie haben die Wissensdatenbank **Suppliers** mit den von der Bereinigungs Aktivität gewonnenen Informationen erweitert.</span><span class="sxs-lookup"><span data-stu-id="19205-124">You have enriched the **Suppliers** knowledge base with what you learned from the cleansing activity.</span></span> <span data-ttu-id="19205-125">Je größer die Wissensdatenbank ist, desto besser sind die Bereinigungsergebnisse.</span><span class="sxs-lookup"><span data-stu-id="19205-125">The stronger the knowledge base is, the better the cleansing results are.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="19205-126">Es ist nicht möglich, Werte für eine Verbunddomäne zu importieren.</span><span class="sxs-lookup"><span data-stu-id="19205-126">It is not possible import values for a composite domain.</span></span>  
  
9. <span data-ttu-id="19205-127">Klicken Sie auf der Symbolleiste auf **Wissensdatenbank exportieren** , und klicken Sie dann auf **Wissensdatenbank exportieren**.</span><span class="sxs-lookup"><span data-stu-id="19205-127">Click **Export Knowledge Base** icon on the toolbar and then click **Export Knowledge Base**.</span></span>  
  
     <span data-ttu-id="19205-128">![Wissensdatenbank exportieren (Menü)](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-02.jpg "Wissensdatenbank exportieren (Menü)")</span><span class="sxs-lookup"><span data-stu-id="19205-128">![Export Knowledge Base Menu](../../2014/tutorials/media/et-importingvaluesfromthecslistproject-02.jpg "Export Knowledge Base Menu")</span></span>  
  
10. <span data-ttu-id="19205-129">Navigieren Sie zum Tutorial-Ordner, geben Sie **Suppliers. DQS** als **Dateiname**ein, und klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="19205-129">Navigate to the Tutorial folder, type **Suppliers.dqs** for the **file name**, and click **Save**.</span></span> <span data-ttu-id="19205-130">Sie können diese DQS-Datei verwenden, um eine neue Wissensdatenbank zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="19205-130">You can use this DQS file to create a new knowledge base based on it.</span></span>  
  
11. <span data-ttu-id="19205-131">Klicken Sie auf **OK** , um das Meldungs Feld **Wissensdatenbank exportieren-Suppliers** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="19205-131">Click **OK** to close the **Export Knowledge Base - Suppliers** message box.</span></span>  
  
12. <span data-ttu-id="19205-132">Klicken Sie auf **Fertig** stellen, um die Aktivität abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="19205-132">Click **Finish** to finish the activity.</span></span>  
  
13. <span data-ttu-id="19205-133">Klicken Sie auf **Veröffentlichen**.</span><span class="sxs-lookup"><span data-stu-id="19205-133">Click **Publish**.</span></span>  
  
14. <span data-ttu-id="19205-134">Klicken Sie im Meldungs Feld auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="19205-134">Click **OK** on the message box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="19205-135">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="19205-135">Next Step</span></span>  
 [<span data-ttu-id="19205-136">Lektion 3: Abgleich von Daten zur Entfernung von Duplikaten aus der Lieferantenliste</span><span class="sxs-lookup"><span data-stu-id="19205-136">Lesson 3: Matching Data to Remove Duplicates from Supplier List</span></span>](../../2014/tutorials/lesson-3-matching-data-to-remove-duplicates-from-supplier-list.md)  
  
  
