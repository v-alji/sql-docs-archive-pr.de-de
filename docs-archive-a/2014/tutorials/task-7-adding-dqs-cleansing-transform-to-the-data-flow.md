---
title: 'Aufgabe 7: Hinzufügen der Transformation für die DQS-Bereinigung zum Datenfluss | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 0b749c71-dfb6-493a-804f-600290d46eef
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 887bc361a51b61e9137404e054bd52e2b630ca5d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609579"
---
# <a name="task-7-adding-dqs-cleansing-transform-to-the-data-flow"></a><span data-ttu-id="d7a53-102">Aufgabe 7: Hinzufügen der Transformation für DQS-Bereinigung zum Datenfluss</span><span class="sxs-lookup"><span data-stu-id="d7a53-102">Task 7: Adding DQS Cleansing Transform to the Data Flow</span></span>
  <span data-ttu-id="d7a53-103">In dieser Aufgabe fügen Sie dem Datenfluss eine DQS-Bereinigungstransformation hinzu, um die Eingabelieferantendaten mithilfe von DQS zu bereinigen.</span><span class="sxs-lookup"><span data-stu-id="d7a53-103">In this task, you add DQS Cleansing Transform to the data flow to cleanse the input supplier data by using DQS.</span></span> <span data-ttu-id="d7a53-104">Weitere Informationen zur Transformation finden Sie unter **[DQS](https://msdn.microsoft.com/library/ee677619.aspx)** -Bereinigungs Transformation.</span><span class="sxs-lookup"><span data-stu-id="d7a53-104">See **[DQS Cleansing Transform](https://msdn.microsoft.com/library/ee677619.aspx)** for more details about the transform.</span></span>  
  
1.  <span data-ttu-id="d7a53-105">Klicken Sie **mit der rechten** Maustaste auf **DQS-Bereinigung** , und klicken Sie auf **Umbenennen**.</span><span class="sxs-lookup"><span data-stu-id="d7a53-105">Right-click **DQS Cleansing** in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="d7a53-106">Geben Sie Hersteller **Daten**bereinigen ein, und drücken **Sie Eingabe**Taste.</span><span class="sxs-lookup"><span data-stu-id="d7a53-106">Type **Cleanse Supplier Data**, and press **ENTER**.</span></span>  
  
2.  <span data-ttu-id="d7a53-107">Wählen Sie **Lieferantendaten aus Excel-Datei lesen aus**. Ziehen Sie den blauen Connector, um **Lieferantendaten**zu bereinigen.</span><span class="sxs-lookup"><span data-stu-id="d7a53-107">Select **Read Supplier Data from Excel File**; drag the blue connector to **Cleanse Supplier Data**.</span></span> <span data-ttu-id="d7a53-108">Die Komponenten sind jetzt verbunden.</span><span class="sxs-lookup"><span data-stu-id="d7a53-108">The components are now connected.</span></span>  
  
     <span data-ttu-id="d7a53-109">![Lesen von Lieferantendaten > Bereinigen der Lieferantendaten](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-01.jpg "Lieferantendaten lesen -> Lieferantendaten bereinigen")</span><span class="sxs-lookup"><span data-stu-id="d7a53-109">![Read Supplier Data -> Cleanse Supplier Data](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-01.jpg "Read Supplier Data -> Cleanse Supplier Data")</span></span>  
  
3.  <span data-ttu-id="d7a53-110">Doppelklicken Sie auf **Lieferantendaten**bereinigen.</span><span class="sxs-lookup"><span data-stu-id="d7a53-110">Double-click **Cleanse Supplier Data**.</span></span>  
  
4.  <span data-ttu-id="d7a53-111">Klicken Sie im Transformations-Editor für die **DQS-Bereinigung**neben der **Dropdown Liste Data Quality-Verbindungs-Manager**auf **neu** .</span><span class="sxs-lookup"><span data-stu-id="d7a53-111">In the **DQS Cleansing Transformation Editor**, click **New** next to the **Data Quality Connection Manager drop-down list**.</span></span>  
  
5.  <span data-ttu-id="d7a53-112">Geben Sie im Dialogfeld **Verbindungs-Manager für DQS-Bereinigung** **(local)** oder **Period** (.) ein, um eine Verbindung mit dem lokalen Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d7a53-112">In the **DQS Cleansing Connection Manager** dialog box, type **(local)** or **period** (.) to connect to the local server.</span></span> <span data-ttu-id="d7a53-113">In dieser Lektion wird davon ausgegangen, dass DQS auf einem lokalen Server installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d7a53-113">This lesson assumes that you have DQS installed on a local server.</span></span>  
  
6.  <span data-ttu-id="d7a53-114">Klicken Sie auf **Verbindung testen** , um die Verbindung mit dem DQS-Server zu testen.</span><span class="sxs-lookup"><span data-stu-id="d7a53-114">Click **Test Connection** to test the connection to DQS server.</span></span>  
  
7.  <span data-ttu-id="d7a53-115">Klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="d7a53-115">Click **OK** to close the dialog box.</span></span>  
  
8.  <span data-ttu-id="d7a53-116">Wählen Sie **Suppliers** für die **Data Quality-Wissensdatenbank**aus.</span><span class="sxs-lookup"><span data-stu-id="d7a53-116">Select **Suppliers** for the **Data Quality Knowledge Base**.</span></span>  
  
     <span data-ttu-id="d7a53-117">![Transformations-Editor für die DQS-Bereinigung – Lieferanten (KB)](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-02.jpg "Transformations-Editor für die DQS-Bereinigung – Lieferanten (KB)")</span><span class="sxs-lookup"><span data-stu-id="d7a53-117">![DQS Cleansing Transformation Editor - Suppliers KB](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-02.jpg "DQS Cleansing Transformation Editor - Suppliers KB")</span></span>  
  
9. <span data-ttu-id="d7a53-118">Wechseln Sie oben zur Registerkarte **Zuordnung** .</span><span class="sxs-lookup"><span data-stu-id="d7a53-118">Switch to the **Mapping** tab at the top.</span></span>  
  
10. <span data-ttu-id="d7a53-119">Wählen Sie unter **Verfügbare Eingabe Spalten**die Option **Lieferanten Name**, **contactemailaddress**, **Adresszeile**, **Ort**, **Bundes** **Land, Land**und **Postleitzahl** aus, indem Sie die Kontrollkästchen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d7a53-119">From **Available Input Columns**, select **Supplier Name**, **ContactEmailAddress**, **Address Line**, **City**, **State**, **Country**, and **Zip Code** by selecting the check boxes.</span></span>  
  
     <span data-ttu-id="d7a53-120">![Transformations-Editor für die DQS-Bereinigung – Zuordnungen](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-03.jpg "Transformations-Editor für die DQS-Bereinigung – Zuordnungen")</span><span class="sxs-lookup"><span data-stu-id="d7a53-120">![DQS Cleansing Transformation Editor - Mappings](../../2014/tutorials/media/et-addingdqscleansingtransformtothedataflow-03.jpg "DQS Cleansing Transformation Editor - Mappings")</span></span>  
  
11. <span data-ttu-id="d7a53-121">Ordnen Sie diese Spalten im unteren Bereich mithilfe von Dropdown Listen in der Spalte **Domäne** zu:</span><span class="sxs-lookup"><span data-stu-id="d7a53-121">In the bottom pane, map these columns by using drop-down lists in the **Domain** column:</span></span>  
  
    |<span data-ttu-id="d7a53-122">Column</span><span class="sxs-lookup"><span data-stu-id="d7a53-122">Column</span></span>|<span data-ttu-id="d7a53-123">Domain</span><span class="sxs-lookup"><span data-stu-id="d7a53-123">Domain</span></span>|  
    |------------|------------|  
    |<span data-ttu-id="d7a53-124">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="d7a53-124">Supplier Name</span></span>|<span data-ttu-id="d7a53-125">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="d7a53-125">Supplier Name</span></span>|  
    |<span data-ttu-id="d7a53-126">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="d7a53-126">ContactEmailAddress</span></span>|<span data-ttu-id="d7a53-127">Kontakt-E-Mail</span><span class="sxs-lookup"><span data-stu-id="d7a53-127">Contact Email</span></span>|  
    |<span data-ttu-id="d7a53-128">Adresszeile</span><span class="sxs-lookup"><span data-stu-id="d7a53-128">Address Line</span></span>|<span data-ttu-id="d7a53-129">Adresszeile</span><span class="sxs-lookup"><span data-stu-id="d7a53-129">Address Line</span></span>|  
    |<span data-ttu-id="d7a53-130">City</span><span class="sxs-lookup"><span data-stu-id="d7a53-130">City</span></span>|<span data-ttu-id="d7a53-131">City</span><span class="sxs-lookup"><span data-stu-id="d7a53-131">City</span></span>|  
    |<span data-ttu-id="d7a53-132">State</span><span class="sxs-lookup"><span data-stu-id="d7a53-132">State</span></span>|<span data-ttu-id="d7a53-133">State</span><span class="sxs-lookup"><span data-stu-id="d7a53-133">State</span></span>|  
    |<span data-ttu-id="d7a53-134">Land</span><span class="sxs-lookup"><span data-stu-id="d7a53-134">Country</span></span>|<span data-ttu-id="d7a53-135">Land</span><span class="sxs-lookup"><span data-stu-id="d7a53-135">Country</span></span>|  
    |<span data-ttu-id="d7a53-136">Zip Code</span><span class="sxs-lookup"><span data-stu-id="d7a53-136">Zip Code</span></span>|<span data-ttu-id="d7a53-137">Zip</span><span class="sxs-lookup"><span data-stu-id="d7a53-137">Zip</span></span>|  
  
12. <span data-ttu-id="d7a53-138">Klicken Sie zum Schließen des Dialog Felds **Transformations-Editor für DQS-Bereinigung** auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="d7a53-138">Click **OK** to close the **DQS Cleansing Transformation Editor** dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="d7a53-139">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d7a53-139">Next Step</span></span>  
 [<span data-ttu-id="d7a53-140">Aufgabe 8: Hinzufügen der Transformation „Bedingtes Teilen“ zur Teilung der Bereinigungsausgabe</span><span class="sxs-lookup"><span data-stu-id="d7a53-140">Task 8: Adding Conditional Split Transform to Split Cleansing Output</span></span>](../../2014/tutorials/task-8-adding-conditional-split-transform-to-split-cleansing-output.md)  
  
  
