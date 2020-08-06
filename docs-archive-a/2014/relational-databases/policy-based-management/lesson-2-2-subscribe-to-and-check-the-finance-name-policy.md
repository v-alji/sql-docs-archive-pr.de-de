---
title: Abonnieren und Überprüfen der Richtlinie „Finance Name“ | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 126b4c4c-2a1c-4701-a0ad-8de23fbd7306
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 2bfe6f463d03fe8b95f000dc6f34dc0718a7729f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608593"
---
# <a name="subscribe-to-and-check-the-finance-name-policy"></a><span data-ttu-id="b7577-102">Abonnieren und Überprüfen der Richtlinie 'Finanz_Name'</span><span class="sxs-lookup"><span data-stu-id="b7577-102">Subscribe to and Check the Finance Name Policy</span></span>
  <span data-ttu-id="b7577-103">In dieser Aufgabe konfigurieren Sie die Datenbank Finanzen, um die Richtlinienkategorie Finanzen zu abonnieren.</span><span class="sxs-lookup"><span data-stu-id="b7577-103">In this task, you will configure the Finance database to subscribe to the Finance policy category.</span></span> <span data-ttu-id="b7577-104">Anschließend testen Sie die Richtlinie Finanz_Name.</span><span class="sxs-lookup"><span data-stu-id="b7577-104">Then, you will test the Finance Name policy.</span></span>  
  
### <a name="to-subscribe-to-the-finance-policy-category"></a><span data-ttu-id="b7577-105">So abonnieren Sie die Richtlinienkategorie 'Finanzen'</span><span class="sxs-lookup"><span data-stu-id="b7577-105">To subscribe to the Finance policy category</span></span>  
  
1.  <span data-ttu-id="b7577-106">Erweitern Sie in Objekt-Explorer **Datenbanken**, klicken Sie mit der rechten Maustaste `Finance` , zeigen Sie auf **Richtlinien**, und klicken Sie dann auf **Kategorien**.</span><span class="sxs-lookup"><span data-stu-id="b7577-106">In Object Explorer, expand **Databases**, right-click `Finance`, point to **Policies**, and then click **Categories**.</span></span>  
  
2.  <span data-ttu-id="b7577-107">Aktivieren Sie das Kontrollkästchen **abonniert** für die `Finance` Kategorie.</span><span class="sxs-lookup"><span data-stu-id="b7577-107">Select the **Subscribed** checkbox for the `Finance` category.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
### <a name="to-test-the-enforcement-of-the-finance-name-policy"></a><span data-ttu-id="b7577-108">So testen Sie die Durchsetzung der Richtlinie 'Finanz_Name'</span><span class="sxs-lookup"><span data-stu-id="b7577-108">To test the enforcement of the Finance Name policy</span></span>  
  
1.  <span data-ttu-id="b7577-109">Öffnen Sie ein Abfragefenster in [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b7577-109">In [!INCLUDE[ssManStudio](../../includes/ssmanstudio-md.md)], open a query window.</span></span> <span data-ttu-id="b7577-110">Führen Sie die folgenden Anweisungen aus, mit denen versucht wird, eine Tabelle zu erstellen, die gegen die Richtlinie **Finanz_Name** verstößt.</span><span class="sxs-lookup"><span data-stu-id="b7577-110">Execute the following statements that try to create a table that violates the **Finance Name** policy.</span></span> <span data-ttu-id="b7577-111">Die Tabelle verstößt gegen die Richtlinie, da der Tabellenname nicht mit den Buchstaben **fintbl**beginnt.</span><span class="sxs-lookup"><span data-stu-id="b7577-111">The table violates the policy because the table name does not begin with the letters **fintbl**.</span></span>  
  
    ```  
    USE Finance ;  
    GO  
    CREATE TABLE NewTable  
    (Col1 int) ;  
    GO  
  
    ```  
  
     <span data-ttu-id="b7577-112">Beachten Sie, dass die Richtlinie das Erstellen der Tabelle verhindert und eine Informationsmeldung zurückgibt, die den Richtliniennamen liefert.</span><span class="sxs-lookup"><span data-stu-id="b7577-112">Notice that the policy prevents the table from being created and returns an informational message that provides the policy name.</span></span>  
  
2.  <span data-ttu-id="b7577-113">Um einen gültigen Namen anzugeben, ändern Sie den Code wie folgt, und führen Sie dann erneut die Anweisung aus.</span><span class="sxs-lookup"><span data-stu-id="b7577-113">To provide a valid name, modify the code as follows and run the statement again.</span></span>  
  
    ```  
    USE Finance ;  
    GO  
    CREATE TABLE fintblNewTable  
    (Col1 int) ;  
    GO  
  
    ```  
  
     <span data-ttu-id="b7577-114">Nun wird die Tabelle erstellt.</span><span class="sxs-lookup"><span data-stu-id="b7577-114">This time, the table is created.</span></span>  
  
### <a name="to-apply-the-policy-to-the-whole-server"></a><span data-ttu-id="b7577-115">So übernehmen Sie die Richtlinie für den ganzen Server</span><span class="sxs-lookup"><span data-stu-id="b7577-115">To apply the policy to the whole server</span></span>  
  
1.  <span data-ttu-id="b7577-116">Momentan hat nur die Datenbank Finanzen die Richtlinienkategorie Finanzen abonniert.</span><span class="sxs-lookup"><span data-stu-id="b7577-116">Currently, only the Finance database subscribes to the Finance policy category.</span></span> <span data-ttu-id="b7577-117">In vielen Fällen ist es einfacher, die Richtlinienkategorie für den ganzen Server zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="b7577-117">In many cases, it is easier to apply the policy category to the whole server.</span></span> <span data-ttu-id="b7577-118">Erweitern Sie im Objekt-Explorer **Verwaltung**, klicken Sie mit der rechten Maustaste auf **Richtlinienverwaltung**und anschließend auf **Kategorien verwalten**.</span><span class="sxs-lookup"><span data-stu-id="b7577-118">In Object Explorer, expand **Management**, right-click **Policy Management**, and then click **Manage Categories**.</span></span>  
  
2.  <span data-ttu-id="b7577-119">Suchen Sie im Dialogfeld **Richtlinienkategorien verwalten** nach der Kategorie „Finanzen“, und aktivieren Sie das Kontrollkästchen **Datenbankabonnements beauftragen** für die Kategorie „Finanzen“.</span><span class="sxs-lookup"><span data-stu-id="b7577-119">In the **Manage Policy Categories** dialog box, locate the Finance category, and select the **Mandate Database Subscriptions** checkbox for the Finance category.</span></span>  
  
3.  [!INCLUDE[clickOK](../../includes/clickok-md.md)] <span data-ttu-id="b7577-120">Nun gilt die Kategorie „Finanzen“ für alle Datenbanken, aber durch die von Ihnen erstellte Bedingung ist die Richtlinie „Finanz_Name“ nur auf die Datenbank „Finanzen“ beschränkt.</span><span class="sxs-lookup"><span data-stu-id="b7577-120">Now the Finance category applies to all databases, but the condition that you have created restricts the Finance Name policy to the Finance database.</span></span> <span data-ttu-id="b7577-121">Dieses Beispiel zeigt, wie Sie komplexe Kombinationen von Bedingungen verwenden können, um Richtlinien so zuzuweisen, dass sie für viele Server richtig übernommen werden.</span><span class="sxs-lookup"><span data-stu-id="b7577-121">This shows how you can use complex combinations of conditions to target policies in ways that will apply correctly on many servers.</span></span>  
  
## <a name="summary"></a><span data-ttu-id="b7577-122">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b7577-122">Summary</span></span>  
 <span data-ttu-id="b7577-123">Dieses Lernprogramm hat gezeigt, wie Sie Bedingungen, Richtlinien und Richtliniengruppen der richtlinienbasierten Verwaltung erstellen und die Kompatibilität der Ziele der richtlinienbasierten Verwaltung überprüfen können.</span><span class="sxs-lookup"><span data-stu-id="b7577-123">This tutorial has shown you how to create Policy-Based Management conditions, policies and policy groups, and how to apply filters and check the compliance of Policy-Based Management targets.</span></span>  
  
## <a name="next"></a><span data-ttu-id="b7577-124">Nächste</span><span class="sxs-lookup"><span data-stu-id="b7577-124">Next</span></span>  
 <span data-ttu-id="b7577-125">Dieses Lernprogramm ist beendet.</span><span class="sxs-lookup"><span data-stu-id="b7577-125">This tutorial is finished.</span></span> <span data-ttu-id="b7577-126">Um zum Anfang des Tutorials zurückzukehren, klicken Sie auf [Tutorial: Verwalten von Servern mit der richtlinienbasierten Verwaltung](tutorial-administering-servers-by-using-policy-based-management.md).</span><span class="sxs-lookup"><span data-stu-id="b7577-126">To return to the start, click [Tutorial: Administering Servers by Using Policy-Based Management](tutorial-administering-servers-by-using-policy-based-management.md).</span></span>  
  
 <span data-ttu-id="b7577-127">Eine Liste der Tutorials finden Sie unter [Tutorials für SQL Server 2014](../../tutorials/tutorials-for-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="b7577-127">For a list of tutorials, see [Tutorials for SQL Server 2014](../../tutorials/tutorials-for-sql-server-2014.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7577-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b7577-128">See Also</span></span>  
 [<span data-ttu-id="b7577-129">Verwalten von Servern mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="b7577-129">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
