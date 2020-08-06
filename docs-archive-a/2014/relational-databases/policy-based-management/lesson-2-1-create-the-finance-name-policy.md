---
title: Erstellen der Richtlinie „Finance Name“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 56b2c852-fd69-4cd2-9b5d-977467b94fd9
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 44ffff45f126d2ad9b73c5b8410b8f89ad2b0604
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609163"
---
# <a name="create-the-finance-name-policy"></a><span data-ttu-id="8a763-102">Erstellen der Richtlinie Finance Name</span><span class="sxs-lookup"><span data-stu-id="8a763-102">Create the Finance Name Policy</span></span>
  <span data-ttu-id="8a763-103"> In diesem Task erstellen Sie eine Datenbank mit dem Namen „Finanzen“. Anschließend erstellen Sie eine Bedingung, die vorschreibt, dass alle Tabellen mit den Buchstaben **fintbl** anfangen.</span><span class="sxs-lookup"><span data-stu-id="8a763-103">In this task, you will create a database named Finance, and then create a condition that requires all tables to start with the letters **fintbl**.</span></span> <span data-ttu-id="8a763-104">Dann erstellen Sie eine Richtlinie und eine Richtlinienkategorie, um einen Namensstandard für Tabellen in der Datenbank Finanzen zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="8a763-104">Then, you will create a policy and policy category to enforce a naming standard for tables in the Finance database.</span></span>  
  
### <a name="to-create-the-finance-database"></a><span data-ttu-id="8a763-105">So erstellen Sie die Datenbank "Finance"</span><span class="sxs-lookup"><span data-stu-id="8a763-105">To create the Finance database</span></span>  
  
1.  <span data-ttu-id="8a763-106">Öffnen Sie ein Abfragefenster in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], und führen Sie die folgende Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="8a763-106">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a query window and execute the following statement:</span></span>  
  
    ```  
    CREATE DATABASE Finance ;  
    GO  
    ```  
  
2.  <span data-ttu-id="8a763-107">Klicken Sie im Objekt-Explorer auf **Datenbanken**, und drücken Sie anschließend F5, um die Liste der Datenbanken zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8a763-107">In Object Explorer, click **Databases**, and then press F5 to refresh the list of databases.</span></span>  
  
### <a name="to-create-the-finance-tables-condition"></a><span data-ttu-id="8a763-108">So erstellen Sie die Bedingung 'Finanz_Tabellen'</span><span class="sxs-lookup"><span data-stu-id="8a763-108">To create the Finance Tables condition</span></span>  
  
1.  <span data-ttu-id="8a763-109">Erweitern Sie im Objekt-Explorer **Verwaltung**, erweitern Sie **Richtlinienverwaltung**, klicken Sie mit der rechten Maustaste auf **Bedingungen**und anschließend auf **Neue Bedingung**.</span><span class="sxs-lookup"><span data-stu-id="8a763-109">In Object Explorer, expand **Management**, expand **Policy Management**, right-click **Conditions**, and then click **New Condition**.</span></span>  
  
2.  <span data-ttu-id="8a763-110">Geben Sie im Dialogfeld **Neue Bedingung erstellen** im Feld **Name** den Namen **Finanz_Tabellen**ein.</span><span class="sxs-lookup"><span data-stu-id="8a763-110">In the **Create New Condition** dialog box, in the **Name** box, type **Finance Tables**.</span></span>  
  
3.  <span data-ttu-id="8a763-111">Wählen Sie in der Liste **Facet** die Option **Mehrteiliger Name**aus.</span><span class="sxs-lookup"><span data-stu-id="8a763-111">In the **Facet** list, select **Multipart Name**.</span></span>  
  
4.  <span data-ttu-id="8a763-112">Wählen Sie im Bereich **Ausdruck** im **Feld Feld** die Option \*\* \@ Name\*\*aus, wählen Sie im Feld **Operator** die Option like aus, und geben Sie im Feld **Wert den Wert** **' fintbl anfangen% '** ein, um zu erzwingen, **dass**alle Tabellennamen mit den Buchstaben **fintbl anfangen**beginnen.</span><span class="sxs-lookup"><span data-stu-id="8a763-112">In the **Expression** area, in the **Field** box, select **\@Name**; in the **Operator** box, select **Like**; and in the **Value** box, type **'fintbl%'** to force all table names to start with the letters **fintbl**.</span></span>  
  
5.  <span data-ttu-id="8a763-113">Geben Sie auf der Seite **Beschreibung** die Beschreibung **Finanz_Tabellen-Namen müssen mit fintbl beginnen**ein, und klicken Sie anschließend auf **OK** , um die Bedingung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="8a763-113">On the **Description** page, type **Finance table names must begin with fintbl**, and then click **OK** to create the condition.</span></span>  
  
### <a name="to-create-the-finance-name-policy"></a><span data-ttu-id="8a763-114">So erstellen Sie die Richtlinie 'Finanz_Name'</span><span class="sxs-lookup"><span data-stu-id="8a763-114">To create the Finance Name policy</span></span>  
  
1.  <span data-ttu-id="8a763-115">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf **Richtlinien**und anschließend auf **Neue Richtlinie**.</span><span class="sxs-lookup"><span data-stu-id="8a763-115">In Object Explorer, right-click **Policies**, and then click **New Policy**.</span></span>  
  
2.  <span data-ttu-id="8a763-116">Geben Sie im Dialogfeld **Neue Richtlinie erstellen** im Feld **Name** den Namen **Finanz_Name**ein.</span><span class="sxs-lookup"><span data-stu-id="8a763-116">In the **Create New Policy** dialog box, in the **Name** box, type **Finance Name**.</span></span>  
  
3.  <span data-ttu-id="8a763-117">Wählen Sie in der Liste **Bedingung überprüfen** die Option **Finanz_Tabellen**aus.</span><span class="sxs-lookup"><span data-stu-id="8a763-117">In the **Check condition** list, select **Finance Tables**.</span></span> <span data-ttu-id="8a763-118">Diese befindet sich im Abschnitt **Mehrteiliger Name** .</span><span class="sxs-lookup"><span data-stu-id="8a763-118">This is in the **Multipart Name** area.</span></span>  
  
4.  <span data-ttu-id="8a763-119">Im Abschnitt **Für** wird eine Liste der Datenbankobjekte angezeigt, die diese Richtlinie anwenden könnten.</span><span class="sxs-lookup"><span data-stu-id="8a763-119">In the **Against** area you will see a list of the database objects that could apply this policy.</span></span> <span data-ttu-id="8a763-120">Aktivieren Sie das Kontrollkästchen für **Jede Tabelle**.</span><span class="sxs-lookup"><span data-stu-id="8a763-120">Select the check box for **Every Table**.</span></span>  
  
5.  <span data-ttu-id="8a763-121">Erweitern Sie im Abschnitt **Jede Datenbank** den Eintrag **Jede**, und klicken Sie anschließend auf **Neue Bedingung**.</span><span class="sxs-lookup"><span data-stu-id="8a763-121">In the **Every Database** area, expand **Every**, and then click **New condition**.</span></span>  
  
6.  <span data-ttu-id="8a763-122">Geben Sie im Dialogfeld **Neue Bedingung erstellen** im Feld **Name** den Namen **Finanz_Datenbank**ein.</span><span class="sxs-lookup"><span data-stu-id="8a763-122">In the **Create New Condition** dialog box, in the **Name** box, type **Finance Database**.</span></span>  
  
7.  <span data-ttu-id="8a763-123">Vervollständigen Sie im Feld **Ausdruck** den Ausdruck, um \*\* \@ Name = ' Finance '\*\* einzuschließen, und klicken Sie dann auf **OK** , um die Seite Bedingung zu schließen.</span><span class="sxs-lookup"><span data-stu-id="8a763-123">In the **Expression** box, complete the expression to include **\@Name = 'Finance'**, and then click **OK** to close the condition page.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8a763-124">Sie müssen möglicherweise mit dem Cursor aus dem Feld **Wert** wechseln, um die Schaltfläche **OK** zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8a763-124">You might have to tab out of the **Value** box to enable the **OK** button.</span></span>  
  
8.  <span data-ttu-id="8a763-125">Wählen Sie in der Liste **Auswertungsmodus** die Option **Bei Änderung: Verhindern**aus.</span><span class="sxs-lookup"><span data-stu-id="8a763-125">In the **Evaluation Mode** list, select **On change: prevent**.</span></span> <span data-ttu-id="8a763-126">Dadurch wird die Richtlinie erzwungen, indem ein Datenbanktrigger für die Datenbank Finanzen erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="8a763-126">This will enforce the policy by creating a database trigger on the Finance database.</span></span>  
  
9. <span data-ttu-id="8a763-127">Wählen Sie in der Liste **Aktiviert** aus.</span><span class="sxs-lookup"><span data-stu-id="8a763-127">Select the **Enabled** list.</span></span> <span data-ttu-id="8a763-128">(Das Feld **Aktiviert** gilt nicht für **bedarfsgesteuerte** Richtlinien.)</span><span class="sxs-lookup"><span data-stu-id="8a763-128">(The **Enabled** box does not apply to **On demand** policies.)</span></span>  
  
10. <span data-ttu-id="8a763-129">Wählen Sie in der Liste **Serverbeschränkung** die Option **Keine**aus.</span><span class="sxs-lookup"><span data-stu-id="8a763-129">In the **Server restriction** list, select **None**.</span></span>  
  
11. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-create-the-finance-policy-category"></a><span data-ttu-id="8a763-130">So erstellen Sie die Richtlinienkategorie 'Finanzen'</span><span class="sxs-lookup"><span data-stu-id="8a763-130">To create the Finance policy category</span></span>  
  
1.  <span data-ttu-id="8a763-131">Erweitern Sie im Objekt-Explorer **Verwaltung**, klicken Sie mit der rechten Maustaste auf **Richtlinienverwaltung**und anschließend auf **Kategorien verwalten**.</span><span class="sxs-lookup"><span data-stu-id="8a763-131">In Object Explorer, expand **Management**, right-click **Policy Management**, and then click **Manage Categories**.</span></span>  
  
2.  <span data-ttu-id="8a763-132">Geben Sie im Dialogfeld **Richtlinien Kategorien verwalten** unter **Name** `Finance` das leere Feld ein, und deaktivieren Sie dann **Daten Bank Abonnements beauftragen**.</span><span class="sxs-lookup"><span data-stu-id="8a763-132">In the **Manage Policy Categories** dialog box, under **Name**, type `Finance` in the blank box, and then clear **Mandate Database Subscriptions**.</span></span> <span data-ttu-id="8a763-133">**Datenbankabonnements beauftragen** zwingt jede Datenbank in der Instanz, die zu dieser Richtlinienkategorie gehörenden Richtlinien zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="8a763-133">**Mandate Database Subscriptions** will force every database in the instance to subscribe to the policies that belong to this policy category.</span></span> <span data-ttu-id="8a763-134">Für diese Lektion darf nur die Datenbank Finanzen die Richtlinie Finanz_Name abonnieren.</span><span class="sxs-lookup"><span data-stu-id="8a763-134">For this lesson, only the Finance database should subscribe to the Finance Name policy.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="8a763-135">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="8a763-135">Next Task in Lesson</span></span>  
 [<span data-ttu-id="8a763-136">Abonnieren und Überprüfen der Richtlinie 'Finanz_Name'</span><span class="sxs-lookup"><span data-stu-id="8a763-136">Subscribe to and Check the Finance Name Policy</span></span>](lesson-2-2-subscribe-to-and-check-the-finance-name-policy.md)  
  
  
