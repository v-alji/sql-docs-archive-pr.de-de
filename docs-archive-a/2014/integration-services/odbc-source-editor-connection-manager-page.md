---
title: Quellen-Editor für ODBC (Seite Verbindungs-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcsource.connection.f1
ms.assetid: e2c8dc83-6394-4d6c-9232-97e94be72431
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c8b54ce4a1c1b3fea0afb51f1cbf7447971ccab4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718565"
---
# <a name="odbc-source-editor-connection-manager-page"></a><span data-ttu-id="efc3d-102">Quellen-Editor für ODBC (Seite Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="efc3d-102">ODBC Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="efc3d-103">Auf der Seite **Verbindungs-Manager** des Dialogfelds **Quellen-Editor für ODBC** können Sie den ODBC-Verbindungs-Manager für die Quelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="efc3d-103">Use the **Connection Manager** page of the **ODBC Source Editor** dialog box to select the ODBC connection manager for the source.</span></span> <span data-ttu-id="efc3d-104">Außerdem können Sie auf dieser Seite eine Tabelle oder Sicht aus der Datenbank auswählen.</span><span class="sxs-lookup"><span data-stu-id="efc3d-104">This page also lets you select a table or view from the database.</span></span>  
  
 <span data-ttu-id="efc3d-105">Weitere Informationen zur ODBC-Quelle finden Sie unter [ODBC Source](data-flow/odbc-source.md).</span><span class="sxs-lookup"><span data-stu-id="efc3d-105">For more information about the ODBC source, see [ODBC Source](data-flow/odbc-source.md).</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="efc3d-106">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="efc3d-106">Task List</span></span>  
 <span data-ttu-id="efc3d-107">**So öffnen Sie die Seite "Verbindungs-Manager" des Quellen-Editors für ODBC**</span><span class="sxs-lookup"><span data-stu-id="efc3d-107">**To open the ODBC Source Editor Connection Manager Page**</span></span>  
  
-   <span data-ttu-id="efc3d-108">Öffnen Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]das [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] -Paket, das die ODBC-Quelle enthält.</span><span class="sxs-lookup"><span data-stu-id="efc3d-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC source.</span></span>  
  
-   <span data-ttu-id="efc3d-109">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die ODBC-Quelle.</span><span class="sxs-lookup"><span data-stu-id="efc3d-109">On the **Data Flow** tab, double-click the ODBC source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="efc3d-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="efc3d-110">Options</span></span>  
  
### <a name="connection-manager"></a><span data-ttu-id="efc3d-111">Ziel-Editor für Dimensionsverarbeitung</span><span class="sxs-lookup"><span data-stu-id="efc3d-111">Connection manager</span></span>  
 <span data-ttu-id="efc3d-112">Wählen Sie einen vorhandenen ODBC-Verbindungs-Manager aus der Liste aus, oder klicken Sie auf **neu** , um eine neue Verbindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="efc3d-112">Select an existing ODBC connection manager from the list, or click **New** to create a new connection.</span></span> <span data-ttu-id="efc3d-113">Sie können eine Verbindung mit jeder von ODBC unterstützten Datenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="efc3d-113">The connection can be to any ODBC-supported database.</span></span>  
  
### <a name="new"></a><span data-ttu-id="efc3d-114">Neu</span><span class="sxs-lookup"><span data-stu-id="efc3d-114">New</span></span>  
 <span data-ttu-id="efc3d-115">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="efc3d-115">Click **New**.</span></span> <span data-ttu-id="efc3d-116">Das Dialogfeld **ODBC-Verbindungs-Manager konfigurieren** , in dem Sie einen neuen ODBC-Verbindungs-Manager erstellen können, wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="efc3d-116">The **Configure ODBC Connection Manager Editor** dialog box opens where you can create a new ODBC connection manager.</span></span>  
  
### <a name="data-access-mode"></a><span data-ttu-id="efc3d-117">Datenzugriffsmodus</span><span class="sxs-lookup"><span data-stu-id="efc3d-117">Data Access Mode</span></span>  
 <span data-ttu-id="efc3d-118">Wählen Sie die Methode für die Auswahl von Daten aus der Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="efc3d-118">Select the method for selecting data from the source.</span></span> <span data-ttu-id="efc3d-119">Die Optionen sind in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="efc3d-119">The options are shown in the following table:</span></span>  
  
|<span data-ttu-id="efc3d-120">Option</span><span class="sxs-lookup"><span data-stu-id="efc3d-120">Option</span></span>|<span data-ttu-id="efc3d-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="efc3d-121">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="efc3d-122">Tabellenname</span><span class="sxs-lookup"><span data-stu-id="efc3d-122">Table Name</span></span>|<span data-ttu-id="efc3d-123">Ruft Daten aus einer Tabelle oder Sicht in der ODBC-Datenquelle ab.</span><span class="sxs-lookup"><span data-stu-id="efc3d-123">Retrieve data from a table or view in the ODBC data source.</span></span> <span data-ttu-id="efc3d-124">Bei Auswahl dieser Option wählen Sie einen der folgenden Werte in der Liste aus:</span><span class="sxs-lookup"><span data-stu-id="efc3d-124">When you select this option, select a value from the list for the following:</span></span>|  
||<span data-ttu-id="efc3d-125">**Name der Tabelle oder Sicht**: Wählen Sie in der Liste eine verfügbare Tabelle oder Sicht aus, oder geben Sie einen regulären Ausdruck ein, um die Tabelle zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="efc3d-125">**Name of the table or the view**: Select an available table or view from the list or type a regular expression to identify the table.</span></span>|  
||<span data-ttu-id="efc3d-126">Diese Liste enthält nur die ersten 1000 Tabellen.</span><span class="sxs-lookup"><span data-stu-id="efc3d-126">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="efc3d-127">Wenn die Datenbank mehr als 1000 Tabellen enthält, können Sie den Anfang eines Tabellennamens eingeben oder das Platzhalterzeichen (\*) verwenden, um einen beliebigen Teil des Namens einzugeben und die gewünschten Tabellen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="efc3d-127">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>|  
|<span data-ttu-id="efc3d-128">SQL-Befehl</span><span class="sxs-lookup"><span data-stu-id="efc3d-128">SQL command</span></span>|<span data-ttu-id="efc3d-129">Ruft mit einer SQL-Abfrage Daten aus der ODBC-Datenquelle ab.</span><span class="sxs-lookup"><span data-stu-id="efc3d-129">Retrieve data from the ODBC data source by using an SQL query.</span></span> <span data-ttu-id="efc3d-130">Die Abfrage sollte in der Syntax der verwendeten Quelldatenbank geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="efc3d-130">You should write the query in the syntax of the source database you are working with.</span></span> <span data-ttu-id="efc3d-131">Bei Auswahl dieser Option geben Sie anhand einer der folgenden Methoden eine Abfrage ein:</span><span class="sxs-lookup"><span data-stu-id="efc3d-131">When you select this option, enter a query in one of the following ways:</span></span>|  
||<span data-ttu-id="efc3d-132">Geben Sie den Text der SQL-Abfrage im Feld **SQL-Befehlstext** ein.</span><span class="sxs-lookup"><span data-stu-id="efc3d-132">Enter the text of the SQL query in the **SQL command text** field.</span></span>|  
||<span data-ttu-id="efc3d-133">Klicken Sie auf **Durchsuchen** , um die SQL-Abfrage aus einer Textdatei zu laden.</span><span class="sxs-lookup"><span data-stu-id="efc3d-133">Click **Browse** to load the SQL query from a text file.</span></span>|  
||<span data-ttu-id="efc3d-134">Klicken Sie auf **Abfrage analysieren** , um die Syntax des Abfragetextes zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="efc3d-134">Click **Parse query** to verify the syntax of the query text.</span></span>|  
  
### <a name="preview"></a><span data-ttu-id="efc3d-135">Vorschau</span><span class="sxs-lookup"><span data-stu-id="efc3d-135">Preview</span></span>  
 <span data-ttu-id="efc3d-136">Klicken Sie auf **Vorschau** , um die ersten 200 Zeilen (max.) der Daten anzuzeigen, die aus der ausgewählten Tabelle bzw. Sicht extrahiert wurden.</span><span class="sxs-lookup"><span data-stu-id="efc3d-136">Click **Preview** to view up to the first 200 rows of the data extracted from the table or view you selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="efc3d-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="efc3d-137">See Also</span></span>  
 <span data-ttu-id="efc3d-138">[Benutzerdefinierte Eigenschaften der ODBC-Quelle](data-flow/odbc-source-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="efc3d-138">[ODBC Source Custom Properties](data-flow/odbc-source-custom-properties.md) </span></span>  
 <span data-ttu-id="efc3d-139">[Der Quellen-Editor für ODBC &#40;Spalten&#41;](../../2014/integration-services/odbc-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="efc3d-139">[ODBC Source Editor &#40;Columns Page&#41;](../../2014/integration-services/odbc-source-editor-columns-page.md) </span></span>  
 [<span data-ttu-id="efc3d-140">Quellen-Editor für ODBC &#40;Seite „Fehlerausgabe“&#41;</span><span class="sxs-lookup"><span data-stu-id="efc3d-140">ODBC Source Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-source-editor-error-output-page.md)  
  
  
