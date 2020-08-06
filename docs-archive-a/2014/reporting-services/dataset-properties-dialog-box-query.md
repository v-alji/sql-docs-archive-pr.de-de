---
title: Dataseteigenschaften (Dialog Feld), Abfrage | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
f1_keywords:
- "10160"
- sql12.rtp.rptdesigner.datasetproperties.query.f1
ms.assetid: 1fa34a4b-7de0-4e92-99fa-bc28a206773f
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bffb14155d37e67333eb626747e1fcc54e618bbe
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622440"
---
# <a name="dataset-properties-dialog-box-query"></a><span data-ttu-id="6cd63-102">Dataseteigenschaften (Dialogfeld), Abfrage</span><span class="sxs-lookup"><span data-stu-id="6cd63-102">Dataset Properties Dialog Box, Query</span></span>
  <span data-ttu-id="6cd63-103">Wählen Sie im Dialogfeld **Dataseteigenschaften** die Option **Abfrage** aus, um eine Datenquelle auszuwählen und eine Abfrage zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6cd63-103">Select **Query** on the **Dataset Properties** dialog box to choose a data source and create a query.</span></span>  
  
 <span data-ttu-id="6cd63-104">Im Dialogfeld **Dataseteigenschaften** ist Folgendes enthalten:</span><span class="sxs-lookup"><span data-stu-id="6cd63-104">The **Dataset Properties** dialog box includes the following:</span></span>  
  
-   [<span data-ttu-id="6cd63-105">Dataseteigenschaften (Dialogfeld), Parameter</span><span class="sxs-lookup"><span data-stu-id="6cd63-105">Dataset Properties Dialog Box, Parameters</span></span>](report-data/dataset-properties-dialog-box-parameters.md)  
  
-   [<span data-ttu-id="6cd63-106">Dataseteigenschaften (Dialogfeld), Felder</span><span class="sxs-lookup"><span data-stu-id="6cd63-106">Dataset Properties Dialog Box, Fields</span></span>](../../2014/reporting-services/dataset-properties-dialog-box-fields.md)  
  
-   [<span data-ttu-id="6cd63-107">Dataseteigenschaften (Dialogfeld), Optionen</span><span class="sxs-lookup"><span data-stu-id="6cd63-107">Dataset Properties Dialog Box, Options</span></span>](../../2014/reporting-services/dataset-properties-dialog-box-options.md)  
  
-   [<span data-ttu-id="6cd63-108">Dataset Properties Dialog Box, Filters (Dataseteigenschaften (Dialogfeld), Filter)</span><span class="sxs-lookup"><span data-stu-id="6cd63-108">Dataset Properties Dialog Box, Filters</span></span>](report-data/dataset-properties-dialog-box-filters.md)  
  
## <a name="options"></a><span data-ttu-id="6cd63-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6cd63-109">Options</span></span>  
 <span data-ttu-id="6cd63-110">**Name**</span><span class="sxs-lookup"><span data-stu-id="6cd63-110">**Name**</span></span>  
 <span data-ttu-id="6cd63-111">Geben Sie einen Namen für das Dataset ein.</span><span class="sxs-lookup"><span data-stu-id="6cd63-111">Type a name for the dataset.</span></span> <span data-ttu-id="6cd63-112">Der Name darf nicht mit dem Namen eines Datenbereichs oder einer Gruppe im Bericht identisch sein.</span><span class="sxs-lookup"><span data-stu-id="6cd63-112">The name cannot be the same as a name for any data region or group in the report.</span></span>  
  
 <span data-ttu-id="6cd63-113">**Data Source**</span><span class="sxs-lookup"><span data-stu-id="6cd63-113">**Data Source**</span></span>  
 <span data-ttu-id="6cd63-114">Wählen Sie eine Datenquelle als Basis für das Dataset aus.</span><span class="sxs-lookup"><span data-stu-id="6cd63-114">Select the data source on which to base the dataset.</span></span> <span data-ttu-id="6cd63-115">Klicken Sie auf **Neu**, um eine neue Datenquelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6cd63-115">To create a new data source, click **New**.</span></span>  
  
 <span data-ttu-id="6cd63-116">**Abfragetyp**</span><span class="sxs-lookup"><span data-stu-id="6cd63-116">**Query type**</span></span>  
 <span data-ttu-id="6cd63-117">Wählen Sie den Typ von Befehl oder Abfrage aus, der für das Dataset verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="6cd63-117">Select the type of command or query to use for the dataset.</span></span> <span data-ttu-id="6cd63-118">Wählen Sie **Text** aus, um eine Abfrage auszuführen und Daten von der Datenbank abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6cd63-118">Select **Text** to run a query to retrieve data from the database.</span></span> <span data-ttu-id="6cd63-119">Wählen Sie **Tabelle** aus, um mit der **TableDirect** -Funktion von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] alle Felder innerhalb einer Tabelle auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6cd63-119">Select **Table** to use the **TableDirect** feature of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to select all the fields within a table.</span></span> <span data-ttu-id="6cd63-120">Wählen Sie **Gespeicherte Prozedur** aus, um eine gespeicherte Prozedur nach Namen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6cd63-120">Select **Stored Procedure** to run a stored procedure by name.</span></span> <span data-ttu-id="6cd63-121">Standardmäßig ist**Text** ausgewählt. Diese Einstellung wird für einen Großteil der Abfragen verwendet.</span><span class="sxs-lookup"><span data-stu-id="6cd63-121">**Text** is selected by default and is used for most queries.</span></span> <span data-ttu-id="6cd63-122">Um die ausgewählte Datenquellenabfrage zu bearbeiten, klicken Sie auf **Abfrage-Designer**.</span><span class="sxs-lookup"><span data-stu-id="6cd63-122">To edit the selected data source query, click **Query Designer**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6cd63-123">Nicht alle Abfragetypen werden von allen Datenquellen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6cd63-123">Not all query types are supported by all data sources.</span></span> <span data-ttu-id="6cd63-124">Zum Beispiel wird **Tabelle** nur von den Datenquellentypen **OLE DB** und **ODBC**unterstützt.</span><span class="sxs-lookup"><span data-stu-id="6cd63-124">For example, **Table** is supported only by data source types **OLE DB** and **ODBC**.</span></span>  
  
 <span data-ttu-id="6cd63-125">**Abfrage**</span><span class="sxs-lookup"><span data-stu-id="6cd63-125">**Query**</span></span>  
 <span data-ttu-id="6cd63-126">Diese Option wird angezeigt, wenn Sie die Befehlstypoption **Text** auswählen.</span><span class="sxs-lookup"><span data-stu-id="6cd63-126">This option appears when you choose the **Text** command type option.</span></span> <span data-ttu-id="6cd63-127">Geben Sie eine Abfrage ein, oder importieren Sie eine bereits vorhandene Abfrage, indem Sie auf **Importieren**klicken.</span><span class="sxs-lookup"><span data-stu-id="6cd63-127">Type a query or import a pre-existing query by clicking **Import**.</span></span> <span data-ttu-id="6cd63-128">Klicken Sie auf die **Ausdrucks** Schaltfläche (*FX*), um den Ausdruck zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6cd63-128">Click the **Expression** (*fx*) button to edit the expression.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6cd63-129">Wenn Sie die Abfrage mit einem Abfrage-Designer erstellt haben, wird der Text der Abfrage in diesem Feld angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6cd63-129">If you used a query designer to build a query, the text of the query appears in this box.</span></span>  
  
 <span data-ttu-id="6cd63-130">**Tabellenname**</span><span class="sxs-lookup"><span data-stu-id="6cd63-130">**Table name**</span></span>  
 <span data-ttu-id="6cd63-131">Geben Sie den Namen der Tabelle ein, die Sie als Dataset verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="6cd63-131">Enter the name of the table that you want to use as a dataset.</span></span> <span data-ttu-id="6cd63-132">Diese Option wird angezeigt, wenn Sie **Tabelle**auswählen.</span><span class="sxs-lookup"><span data-stu-id="6cd63-132">This option appears when you select **Table**.</span></span>  
  
 <span data-ttu-id="6cd63-133">**Auswählen oder Eingeben des Namens einer gespeicherten Prozedur**</span><span class="sxs-lookup"><span data-stu-id="6cd63-133">**Select or enter stored procedure name**</span></span>  
 <span data-ttu-id="6cd63-134">Geben Sie den Namen der zu verwendenden gespeicherten Prozedur ein, oder wählen Sie ihn aus.</span><span class="sxs-lookup"><span data-stu-id="6cd63-134">Type or choose the name of the stored procedure that you want to use.</span></span> <span data-ttu-id="6cd63-135">Klicken Sie auf die **Ausdrucks** Schaltfläche (*FX*), um den Ausdruck zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6cd63-135">Click the **Expression** (*fx*) button to edit the expression.</span></span> <span data-ttu-id="6cd63-136">Diese Option wird angezeigt, wenn Sie die Befehlstypoption Gespeicherte Prozedur auswählen.</span><span class="sxs-lookup"><span data-stu-id="6cd63-136">This option appears when you choose the Stored Procedure command type option.</span></span>  
  
 <span data-ttu-id="6cd63-137">**Timeout (in Sekunden)**</span><span class="sxs-lookup"><span data-stu-id="6cd63-137">**Time out (in seconds)**</span></span>  
 <span data-ttu-id="6cd63-138">Geben Sie die Anzahl von Sekunden bis zum Timeout der Abfrage ein. Der Standardwert ist 30 Sekunden.</span><span class="sxs-lookup"><span data-stu-id="6cd63-138">Type the number of seconds until the query times out. The default is 30 seconds.</span></span> <span data-ttu-id="6cd63-139">Der angegebene Wert für **Timeout** muss leer oder größer als null sein.</span><span class="sxs-lookup"><span data-stu-id="6cd63-139">The value for **Time out** must be empty or greater than zero.</span></span> <span data-ttu-id="6cd63-140">Wird das Feld leer gelassen, gibt es für die Abfrage kein Timeout.</span><span class="sxs-lookup"><span data-stu-id="6cd63-140">If it is empty, the query does not time out.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cd63-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6cd63-141">See Also</span></span>  
 <span data-ttu-id="6cd63-142">[Datenverbindungen, Datenquellen und Verbindungs Zeichenfolgen in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span><span class="sxs-lookup"><span data-stu-id="6cd63-142">[Data Connections, Data Sources, and Connection Strings in Reporting Services](../../2014/reporting-services/data-connections-data-sources-and-connection-strings-in-reporting-services.md) </span></span>  
 <span data-ttu-id="6cd63-143">[Hinzufügen von Daten zu einem Bericht &#40;Berichts-Generator und SSRS&#41;](report-data/report-datasets-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="6cd63-143">[Add Data to a Report &#40;Report Builder and SSRS&#41;](report-data/report-datasets-ssrs.md) </span></span>  
 <span data-ttu-id="6cd63-144">[Abfrage-Designer &#40;Berichts-Generator&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span><span class="sxs-lookup"><span data-stu-id="6cd63-144">[Query Designers &#40;Report Builder&#41;](../../2014/reporting-services/query-designers-report-builder.md) </span></span>  
 [<span data-ttu-id="6cd63-145">Abfrage-Designer in Reporting Services</span><span class="sxs-lookup"><span data-stu-id="6cd63-145">Reporting Services Query Designers</span></span>](../../2014/reporting-services/reporting-services-query-designers.md)  
  
  
