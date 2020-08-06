---
title: 'Aufgabe 10: Hinzufügen der Transformation für Fuzzygruppierung zum Erkennen von Duplikaten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 90b2b323-babd-464a-8914-9dc5e66aca74
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 086625197850fdfd6381e9c0a4a7deac8ce3ae45
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699002"
---
# <a name="task-10-adding-fuzzy-group-transform-to-identify-duplicates"></a><span data-ttu-id="d825a-102">Aufgabe 10: Hinzufügen der Transformation für Fuzzygruppierung zur Identifizierung von Duplikaten</span><span class="sxs-lookup"><span data-stu-id="d825a-102">Task 10: Adding Fuzzy Group Transform to Identify Duplicates</span></span>
  <span data-ttu-id="d825a-103">In dieser Aufgabe fügen Sie eine Transformation für Fuzzygruppierung zum Datenfluss hinzu.</span><span class="sxs-lookup"><span data-stu-id="d825a-103">In this task, you add a Fuzzy Group Transform to the data flow.</span></span> <span data-ttu-id="d825a-104">Mit der Transformation für Fuzzygruppierung können Duplikate in den Quelldaten identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="d825a-104">The Fuzzy Group transformation can help identify duplicates in the source data.</span></span> <span data-ttu-id="d825a-105">Weitere Informationen finden Sie unter [Transformation für Fuzzygruppierung](../integration-services/data-flow/transformations/fuzzy-grouping-transformation.md) .</span><span class="sxs-lookup"><span data-stu-id="d825a-105">See [Fuzzy Grouping Transformation](../integration-services/data-flow/transformations/fuzzy-grouping-transformation.md) for more details.</span></span>  
  
1.  <span data-ttu-id="d825a-106">Ziehen Sie die Transformation für **Fuzzygruppierung** in **andere Transformationen** der **SSIS-Toolbox** auf die Registerkarte **Datenfluss** unter **richtige und korrigierte Datensätze kombinieren**.</span><span class="sxs-lookup"><span data-stu-id="d825a-106">Drag-drop **Fuzzy Group** transform in **Other Transforms** on the **SSIS Toolbox** to the **Data Flow** tab under **Combine Correct and Corrected Records**.</span></span>  
  
2.  <span data-ttu-id="d825a-107">Klicken Sie in der Registerkarte Datenfluss mit der rechten Maustaste auf Transformation für **Fuzzygruppierung** , **und klicken Sie** **Data Flow**</span><span class="sxs-lookup"><span data-stu-id="d825a-107">Right-click **Fuzzy Group** Transform in the **Data Flow** tab, and click **Rename**.</span></span> <span data-ttu-id="d825a-108">Geben Sie **Group Suppliers with Matching IDs** ein, und drücken **Sie die Eingabe**Taste</span><span class="sxs-lookup"><span data-stu-id="d825a-108">Type **Group Suppliers with matching IDs** and press **ENTER**.</span></span>  
  
3.  <span data-ttu-id="d825a-109">Verbinden Sie **korrekte und korrigierte Datensätze** **mit Gruppen Lieferanten mit übereinstimmenden IDs** , die den blauen Connector verwenden.</span><span class="sxs-lookup"><span data-stu-id="d825a-109">Connect **Combine Correct and Corrected Records** to **Group Suppliers with matching IDs** using the blue connector.</span></span>  
  
     <span data-ttu-id="d825a-110">![Verbinden mit Gruppenlieferanten mit übereinstimmenden IDs](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-01.jpg "Verbinden mit Gruppenlieferanten mit übereinstimmenden IDs")</span><span class="sxs-lookup"><span data-stu-id="d825a-110">![Connection to Group Suppliers with Matching IDs](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-01.jpg "Connection to Group Suppliers with Matching IDs")</span></span>  
  
4.  <span data-ttu-id="d825a-111">Doppelklicken Sie auf **Gruppen Lieferanten mit übereinstimmenden IDs**.</span><span class="sxs-lookup"><span data-stu-id="d825a-111">Double-click **Group Suppliers with matching IDs**.</span></span>  
  
5.  <span data-ttu-id="d825a-112">Klicken Sie im **Transformations-Editor für fuzzygruppen**neben **OLE DB Dropdown Liste Verbindungs-Manager** auf **neu** , um das Dialogfeld **OLE DB Verbindungs** -Manager konfigurieren zu starten.</span><span class="sxs-lookup"><span data-stu-id="d825a-112">In the **Fuzzy Group Transformation Editor**, click **New** next to **OLE DB Connection Manager drop-down list** to launch **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
6.  <span data-ttu-id="d825a-113">Klicken Sie im Dialogfeld auf **neu** , um das Dialogfeld **Verbindungs-Manager** zu starten.</span><span class="sxs-lookup"><span data-stu-id="d825a-113">In the dialog box, click **New** to launch **Connection Manager** dialog box.</span></span>  
  
7.  <span data-ttu-id="d825a-114">Geben Sie **(local)** oder **Period** (.) als Server Namen ein.</span><span class="sxs-lookup"><span data-stu-id="d825a-114">Type **(local)** or **period** (.) for the Server name.</span></span>  
  
8.  <span data-ttu-id="d825a-115">Wählen Sie **MDS** aus, **oder geben Sie ein Feld Datenbankname ein** .</span><span class="sxs-lookup"><span data-stu-id="d825a-115">Select **MDS** for **Select or enter a database name** field.</span></span> <span data-ttu-id="d825a-116">Die MDS-Datenbank wird als temporärer Speicher für die **Transformation für fuzzygruppen**verwendet.</span><span class="sxs-lookup"><span data-stu-id="d825a-116">You will use the MDS database as the temporary storage for the **Fuzzy Group Transform**.</span></span> <span data-ttu-id="d825a-117">Die Transformation für **Fuzzygruppierung** erfordert eine Verbindung mit einer Instanz von SQL Server um die temporären SQL Server Tabellen zu erstellen, die der Transformations Algorithmus für seine Arbeit benötigt.</span><span class="sxs-lookup"><span data-stu-id="d825a-117">The **Fuzzy Grouping** transformation requires a connection to an instance of SQL Server to create the temporary SQL Server tables that the transformation algorithm requires to do its work.</span></span> <span data-ttu-id="d825a-118">Sie können eine Datenbank erstellen oder eine andere vorhandene Datenbank zu diesem Zweck verwenden.</span><span class="sxs-lookup"><span data-stu-id="d825a-118">You can create a database or use another existing database for this purpose.</span></span>  
  
9. <span data-ttu-id="d825a-119">Klicken Sie auf **Verbindung testen** , um die Verbindung zu testen, und klicken Sie im Meldungs Feld auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="d825a-119">Click **Test Connection** to test the connection and click **OK** on the message box.</span></span>  
  
10. <span data-ttu-id="d825a-120">Klicken Sie im Dialogfeld **Verbindungs-Manager** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d825a-120">In the **Connection Manager** dialog box, click **OK**.</span></span>  
  
11. <span data-ttu-id="d825a-121">Wählen Sie **(lokal) aus. MDS** (oder **localhost. MDS**) aus der **Liste der Datenverbindungen** , und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d825a-121">Select **(local).MDS** (or **localhost.MDS**) from the **list of Data Connections** and click **OK**.</span></span>  
  
12. <span data-ttu-id="d825a-122">Bestätigen Sie im **Transformations-Editor für Fuzzygruppierung**, dass **(local) lautet. MDS** oder **localhost. MDS** ist für den **OLE DB-Verbindungs-Manager**ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="d825a-122">In the **Fuzzy Grouping Transformation Editor**, confirm that **(local).MDS** or **localhost.MDS** is selected for the **OLE DB Connection Manager**.</span></span>  
  
13. <span data-ttu-id="d825a-123">Wechseln Sie zur Registerkarte **Spalten** .</span><span class="sxs-lookup"><span data-stu-id="d825a-123">Switch to the **Columns** tab.</span></span>  
  
14. <span data-ttu-id="d825a-124">Aktivieren Sie das Kontrollkästchen (Kontrollkästchen) **SupplierID_Output** aus der Liste der **verfügbaren Eingabe Spalten**.</span><span class="sxs-lookup"><span data-stu-id="d825a-124">Select (check box) **SupplierID_Output** from the list of **Available Input Columns**.</span></span> <span data-ttu-id="d825a-125">Um die Transformation zu konfigurieren, wählen Sie die Eingabespalten für die Identifizierung von Duplikaten aus.</span><span class="sxs-lookup"><span data-stu-id="d825a-125">To configure the transformation, select the input columns to use when identifying duplicates.</span></span> <span data-ttu-id="d825a-126">Verwenden Sie in diesem Schritt zur Vereinfachung nur die SupplierID.</span><span class="sxs-lookup"><span data-stu-id="d825a-126">To keep it simple, you only use the SupplierID in this step.</span></span>  
  
     <span data-ttu-id="d825a-127">![Transformations-Editor für Fuzzygruppierung](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-02.jpg "Transformations-Editor für Fuzzygruppierung")</span><span class="sxs-lookup"><span data-stu-id="d825a-127">![Fuzzy Grouping Transformation Editor](../../2014/tutorials/media/et-addingfgttoidentifyduplicates-02.jpg "Fuzzy Grouping Transformation Editor")</span></span>  
  
15. <span data-ttu-id="d825a-128">Klicken Sie auf **OK** , um den **Transformations-Editor für fuzzygruppen**</span><span class="sxs-lookup"><span data-stu-id="d825a-128">Click **OK** to close the **Fuzzy Group Transformation Editor**.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="d825a-129">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="d825a-129">Next Step</span></span>  
 [<span data-ttu-id="d825a-130">Aufgabe 11: Hinzufügen der Transformation „Bedingtes Teilen“ zur Filterung von Duplikaten</span><span class="sxs-lookup"><span data-stu-id="d825a-130">Task 11: Adding Conditional Split Transform to Filter Duplicates</span></span>](../../2014/tutorials/task-11-adding-conditional-split-transform-to-filter-duplicates.md)  
  
  
