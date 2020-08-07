---
title: Ziel-Editor für ODBC (Seite Verbindungs-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.odbcdest.connection.f1
ms.assetid: f6d9c6c2-e4c4-468b-9e0d-af7b9609614d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6e4fc1073bb187c0864d2991459a358a7f81d066
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718583"
---
# <a name="odbc-destination-editor-connection-manager-page"></a><span data-ttu-id="c87a1-102">Ziel-Editor für ODBC (Verbindungs-Manager-Seite)</span><span class="sxs-lookup"><span data-stu-id="c87a1-102">ODBC Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="c87a1-103">Auf der Seite **Verbindungs-Manager** des Dialogfelds **Ziel-Editor für ODBC** können Sie den ODBC-Verbindungs-Manager für das Ziel auswählen.</span><span class="sxs-lookup"><span data-stu-id="c87a1-103">Use the **Connection Manager** page of the **ODBC Destination Editor** dialog box to select the ODBC connection manager for the destination.</span></span> <span data-ttu-id="c87a1-104">Außerdem können Sie auf dieser Seite eine Tabelle oder Sicht aus der Datenbank auswählen.</span><span class="sxs-lookup"><span data-stu-id="c87a1-104">This page also lets you select a table or view from the database</span></span>  
  
 <span data-ttu-id="c87a1-105">Weitere Informationen zum ODBC-Ziel finden Sie unter [ODBC Destination](data-flow/odbc-destination.md).</span><span class="sxs-lookup"><span data-stu-id="c87a1-105">For more information about the ODBC destination, see [ODBC Destination](data-flow/odbc-destination.md).</span></span>  
  
 <span data-ttu-id="c87a1-106">**So öffnen Sie die Seite "Verbindungs-Manager" des Ziel-Editors für ODBC**</span><span class="sxs-lookup"><span data-stu-id="c87a1-106">**To open the ODBC Destination Editor Connection Manager Page**</span></span>  
  
## <a name="task-list"></a><span data-ttu-id="c87a1-107">Aufgabenliste</span><span class="sxs-lookup"><span data-stu-id="c87a1-107">Task List</span></span>  
  
-   <span data-ttu-id="c87a1-108">Öffnen Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]das [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] -Paket, das das ODBC-Ziel enthält.</span><span class="sxs-lookup"><span data-stu-id="c87a1-108">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], open the [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] package that has the ODBC destination.</span></span>  
  
-   <span data-ttu-id="c87a1-109">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf das ODBC-Ziel.</span><span class="sxs-lookup"><span data-stu-id="c87a1-109">On the **Data Flow** tab, double-click the ODBC destination.</span></span>  
  
-   <span data-ttu-id="c87a1-110">Klicken Sie im **Ziel-Editor für ODBC**auf **Verbindungs-Manager**.</span><span class="sxs-lookup"><span data-stu-id="c87a1-110">In the **ODBC Destination Editor**, click **Connection Manager**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c87a1-111">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c87a1-111">Options</span></span>  
  
### <a name="connection-manager"></a><span data-ttu-id="c87a1-112">Ziel-Editor für Dimensionsverarbeitung</span><span class="sxs-lookup"><span data-stu-id="c87a1-112">Connection manager</span></span>  
 <span data-ttu-id="c87a1-113">Wählen Sie in der Liste einen vorhandenen ODBC-Verbindungs-Manager aus, oder klicken Sie auf Neu, um eine neue Verbindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c87a1-113">Select an existing ODBC connection manager from the list, or click New to create a new connection.</span></span> <span data-ttu-id="c87a1-114">Sie können eine Verbindung mit jeder von ODBC unterstützten Datenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="c87a1-114">The connection can be to any ODBC-supported database.</span></span>  
  
### <a name="new"></a><span data-ttu-id="c87a1-115">Neu</span><span class="sxs-lookup"><span data-stu-id="c87a1-115">New</span></span>  
 <span data-ttu-id="c87a1-116">Klicken Sie auf **Neu**.</span><span class="sxs-lookup"><span data-stu-id="c87a1-116">Click **New**.</span></span> <span data-ttu-id="c87a1-117">Das Dialogfeld **ODBC-Verbindungs-Manager konfigurieren** , in dem Sie einen neuen Verbindungs-Manager erstellen können, wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="c87a1-117">The **Configure ODBC Connection Manager Editor** dialog box opens where you can create a new connection manager.</span></span>  
  
### <a name="data-access-mode"></a><span data-ttu-id="c87a1-118">Datenzugriffsmodus</span><span class="sxs-lookup"><span data-stu-id="c87a1-118">Data Access Mode</span></span>  
 <span data-ttu-id="c87a1-119">Wählen Sie die Methode zum Laden von Daten in das Ziel aus.</span><span class="sxs-lookup"><span data-stu-id="c87a1-119">Select the method for loading data to the destination.</span></span> <span data-ttu-id="c87a1-120">Die Optionen sind in der folgenden Tabelle aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="c87a1-120">The options are shown in the following table:</span></span>  
  
|<span data-ttu-id="c87a1-121">Option</span><span class="sxs-lookup"><span data-stu-id="c87a1-121">Option</span></span>|<span data-ttu-id="c87a1-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c87a1-122">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="c87a1-123">Tabellenname - Batch</span><span class="sxs-lookup"><span data-stu-id="c87a1-123">Table Name - Batch</span></span>|<span data-ttu-id="c87a1-124">Wählen Sie diese Option aus, um das ODBC-Ziel im Batchmodus zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="c87a1-124">Select this option to configure the ODBC destination to work in batch mode.</span></span> <span data-ttu-id="c87a1-125">Bei Auswahl dieser Option sind die folgenden Optionen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="c87a1-125">When you select this option the following options are available:</span></span>|  
||<span data-ttu-id="c87a1-126">**Name der Tabelle oder Sicht**: Wählen Sie in der Liste eine verfügbare Tabelle oder Sicht aus.</span><span class="sxs-lookup"><span data-stu-id="c87a1-126">**Name of the table or the view**: Select an available table or view from the list.</span></span><br /><br /> <span data-ttu-id="c87a1-127">Diese Liste enthält nur die ersten 1000 Tabellen.</span><span class="sxs-lookup"><span data-stu-id="c87a1-127">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="c87a1-128">Wenn die Datenbank mehr als 1000 Tabellen enthält, können Sie den Anfang eines Tabellennamens eingeben oder das Platzhalterzeichen (\*) verwenden, um einen beliebigen Teil des Namens einzugeben und die gewünschten Tabellen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c87a1-128">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span><br /><br /> <span data-ttu-id="c87a1-129">**Batchgröße**: Geben Sie die Größe des Batches für das Massenladen ein.</span><span class="sxs-lookup"><span data-stu-id="c87a1-129">**Batch size**: Type the size of the batch for bulk loading.</span></span> <span data-ttu-id="c87a1-130">Dies ist die Anzahl von Zeilen, die als Batch geladen werden.</span><span class="sxs-lookup"><span data-stu-id="c87a1-130">This is the number of rows loaded as a batch</span></span>|  
|<span data-ttu-id="c87a1-131">Tabellenname - Zeile für Zeile</span><span class="sxs-lookup"><span data-stu-id="c87a1-131">Table Name - Row by Row</span></span>|<span data-ttu-id="c87a1-132">Wählen Sie diese Option aus, um das ODBC-Ziel so zu konfigurieren, dass jede Zeile einzeln in die Zieltabelle eingefügt wird.</span><span class="sxs-lookup"><span data-stu-id="c87a1-132">Select this option to configure the ODBC destination to insert each of the rows into the destination table one at a time.</span></span> <span data-ttu-id="c87a1-133">Bei Auswahl dieser Option ist die folgende Option verfügbar:</span><span class="sxs-lookup"><span data-stu-id="c87a1-133">When you select this option the following option is available:</span></span>|  
||<span data-ttu-id="c87a1-134">**Name der Tabelle oder Sicht**: Wählen Sie in der Liste eine verfügbare Tabelle oder Sicht in der Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="c87a1-134">**Name of the table or the view**: Select an available table or view from the database from the list.</span></span><br /><br /> <span data-ttu-id="c87a1-135">Diese Liste enthält nur die ersten 1000 Tabellen.</span><span class="sxs-lookup"><span data-stu-id="c87a1-135">This list contains the first 1000 tables only.</span></span> <span data-ttu-id="c87a1-136">Wenn die Datenbank mehr als 1000 Tabellen enthält, können Sie den Anfang eines Tabellennamens eingeben oder das Platzhalterzeichen (\*) verwenden, um einen beliebigen Teil des Namens einzugeben und die gewünschten Tabellen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c87a1-136">If your database contains more than 1000 tables, you can type the beginning of a table name or use the (\*) wild card to enter any part of the name to display the table or tables you want to use.</span></span>|  
  
### <a name="preview"></a><span data-ttu-id="c87a1-137">Vorschau</span><span class="sxs-lookup"><span data-stu-id="c87a1-137">Preview</span></span>  
 <span data-ttu-id="c87a1-138">Klicken Sie auf **Vorschau** , um die ersten 200 Zeilen (max.) für die ausgewählte Tabelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c87a1-138">Click **Preview** to view up to 200 rows of data for the table that you selected.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c87a1-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c87a1-139">See Also</span></span>  
 <span data-ttu-id="c87a1-140">[Benutzerdefinierte Eigenschaften des ODBC-Ziels](data-flow/odbc-destination-custom-properties.md) </span><span class="sxs-lookup"><span data-stu-id="c87a1-140">[ODBC Destination Custom Properties](data-flow/odbc-destination-custom-properties.md) </span></span>  
 <span data-ttu-id="c87a1-141">[Ziel-Editor für ODBC &#40;Seite Zuordnungen&#41;](../../2014/integration-services/odbc-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="c87a1-141">[ODBC Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/odbc-destination-editor-mappings-page.md) </span></span>  
 [<span data-ttu-id="c87a1-142">Ziel-Editor für ODBC &#40;Seite „Fehlerausgabe“&#41;</span><span class="sxs-lookup"><span data-stu-id="c87a1-142">ODBC Destination Editor &#40;Error Output Page&#41;</span></span>](../../2014/integration-services/odbc-destination-editor-error-output-page.md)  
  
  
