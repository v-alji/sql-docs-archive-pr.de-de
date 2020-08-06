---
title: Bearbeiten einer vorhandenen Datenquellen Verbindung (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.selexistconn.f1
ms.assetid: 97e63f18-a01d-4c91-a411-e7e6d40a0647
author: minewiskan
ms.author: owend
ms.openlocfilehash: 675a0d1119e25a92231d3e74a79739cb2e96b6d5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621242"
---
# <a name="edit-an-existing-data-source-connection-ssas-tabular"></a><span data-ttu-id="fb8c2-102">Bearbeiten einer vorhandenen Datenquellenverbindung (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="fb8c2-102">Edit an Existing Data Source Connection (SSAS Tabular)</span></span>
  <span data-ttu-id="fb8c2-103">In diesem Thema wird beschrieben, wie Sie die Eigenschaften einer vorhandenen Datenquellenverbindung in einem tabellarischen Modell bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-103">This topic describes how to edit the properties of an existing data source connection in a tabular model.</span></span>  
  
 <span data-ttu-id="fb8c2-104">Nachdem Sie eine Verbindung mit einer externen Datenquelle erstellt haben, können Sie diese Verbindung später wie folgt ändern:</span><span class="sxs-lookup"><span data-stu-id="fb8c2-104">After you have created a connection to an external data source, you can later modify that connection in these ways:</span></span>  
  
-   <span data-ttu-id="fb8c2-105">Sie können die Verbindungsinformationen, einschließlich der verwendeten Quelle (Datei, Feed oder Datenbank), die Verbindungseigenschaften oder andere anbieterspezifische Verbindungsoptionen ändern.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-105">You can change the connection information, including the file, feed, or database used as a source, its properties, or other provider-specific connection options.</span></span>  
  
-   <span data-ttu-id="fb8c2-106">Sie können Tabellen- und Spaltenzuordnungen ändern und Verweise auf Spalten löschen, die nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-106">You can change table and column mappings, and remove references to columns that are no longer used.</span></span>  
  
-   <span data-ttu-id="fb8c2-107">Sie können die Tabellen, Sichten oder Spalten ändern, die aus der externen Datenquelle abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-107">You can change the tables, views, or columns that you get from the external data source.</span></span>  
  
## <a name="modify-a-connection"></a><span data-ttu-id="fb8c2-108">Ändern einer Verbindung</span><span class="sxs-lookup"><span data-stu-id="fb8c2-108">Modify a Connection</span></span>  
 <span data-ttu-id="fb8c2-109">In diesem Verfahren wird beschrieben, wie eine Datenquellenverbindung einer Datenbank geändert wird.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-109">This procedure describes how to modify a database data source connection.</span></span> <span data-ttu-id="fb8c2-110">Einige Optionen zum Arbeiten mit Datenquellen sind vom Datenquellentyp abhängig. Diese Unterschiede sollten jedoch leicht zu erkennen sein.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-110">Some options for working with data sources differ depending on the data source type; however, you should be able to easily identify those differences.</span></span>  
  
#### <a name="to-change-the-external-data-source-used-by-a-current-connection"></a><span data-ttu-id="fb8c2-111">So ändern Sie die von einer aktuellen Verbindung verwendete externe Datenquelle</span><span class="sxs-lookup"><span data-stu-id="fb8c2-111">To change the external data source used by a current connection</span></span>  
  
1.  <span data-ttu-id="fb8c2-112">Klicken Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]im Menü **Modell** auf **Vorhandene Verbindungen**.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-112">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], click the **Model** menu, and then click **Existing Connections**.</span></span>  
  
2.  <span data-ttu-id="fb8c2-113">Wählen Sie die Datenquellenverbindung aus, die Sie ändern möchten, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-113">Select the data source connection you want to modify, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="fb8c2-114">Klicken Sie im Dialogfeld **Verbindung bearbeiten** auf **Durchsuchen** , um eine andere Datenbank vom gleichen Typ, aber mit einem anderen Namen oder Speicherort, zu suchen.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-114">In the **Edit Connection** dialog box, click **Browse** to locate another database of the same type but with a different name or location.</span></span>  
  
     <span data-ttu-id="fb8c2-115">Sobald Sie die Datenbankdatei ändern, wird eine Meldung angezeigt, die Sie darüber informiert, dass Sie die Tabellen speichern und aktualisieren müssen, um die neuen Daten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-115">As soon as you change the database file, a message appears indicating that you need to save and refresh the tables in order to see the new data.</span></span>  
  
4.  <span data-ttu-id="fb8c2-116">Klicken Sie auf **Speichern**und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-116">Click **Save**, and then click **Close**.</span></span>  
  
5.  <span data-ttu-id="fb8c2-117">Klicken Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf das **Modell**, und klicken Sie dann auf **Verarbeiten**und **Alles verarbeiten**.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-117">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Model**, click **Process**, and then click **Process All**.</span></span>  
  
     <span data-ttu-id="fb8c2-118">Die Tabellen werden mit der neuen Datenquelle, jedoch mit der ursprünglichen Datenauswahl, neu verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-118">The tables are re-processed using the new data source, but with the original data selections.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="fb8c2-119">Wenn die neue Datenquelle zusätzliche Tabellen enthält, die in der ursprünglichen Datenquelle nicht vorhanden waren, müssen Sie die geänderte Verbindung erneut öffnen und die Tabellen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-119">If the new data source contains any additional tables that were not present in the original data source, you must re-open the changed connection and add the tables.</span></span>  
  
## <a name="edit-table-and-column-mappings-bindings"></a><span data-ttu-id="fb8c2-120">Bearbeiten von Tabellen- und Spaltenzuordnungen (Bindungen)</span><span class="sxs-lookup"><span data-stu-id="fb8c2-120">Edit Table and Column Mappings (Bindings)</span></span>  
 <span data-ttu-id="fb8c2-121">In diesem Verfahren wird beschrieben, wie die Zuordnungen bearbeitet werden, nachdem eine Datenquelle geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-121">This procedure describes how to edit the mappings after you change a data source.</span></span>  
  
#### <a name="to-edit-column-mappings-when-a-data-source-changes"></a><span data-ttu-id="fb8c2-122">So bearbeiten Sie Spaltenzuordnungen, wenn sich eine Datenquelle ändert</span><span class="sxs-lookup"><span data-stu-id="fb8c2-122">To edit column mappings when a data source changes</span></span>  
  
1.  <span data-ttu-id="fb8c2-123">Wählen Sie im Modell-Designer eine Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-123">In the model designer, select a table.</span></span>  
  
2.  <span data-ttu-id="fb8c2-124">Klicken Sie im Menü **Tabelle** auf **Tabelleneigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-124">Click on the **Table** menu, and then click **Table Properties**.</span></span>  
  
     <span data-ttu-id="fb8c2-125">Der Name der ausgewählten Tabelle wird im Feld **Tabellenname** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-125">The name of the selected table is displayed in the **Table Name** box.</span></span> <span data-ttu-id="fb8c2-126">Das Feld **Quellname** enthält den Namen der Tabelle in der externen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-126">The **Source Name** box contains the name of the table in the external data source.</span></span> <span data-ttu-id="fb8c2-127">Wenn die Spalten in der Quelle und im Modell nicht identisch sind, können Sie zwischen den beiden Sätzen von Spaltennamen wechseln, indem Sie die Optionen **Quelle** oder **Modell**auswählen.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-127">If columns are named differently in the source and in the model, you can toggle between the two sets of column names by selecting the options **Source** or **Model**.</span></span>  
  
3.  <span data-ttu-id="fb8c2-128">Um die Tabelle zu ändern, die als Datenquelle verwendet wird, wählen Sie für **Quellname**eine andere Tabelle als die derzeitige Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-128">To change the table that is used as a data source, for **Source Name**, select a different table than the current one.</span></span>  
  
4.  <span data-ttu-id="fb8c2-129">Ändern Sie die Spaltenzuordnungen nach Bedarf:</span><span class="sxs-lookup"><span data-stu-id="fb8c2-129">Change column mappings if needed:</span></span>  
  
    1.  <span data-ttu-id="fb8c2-130">Um Spalten hinzuzufügen, die in der Quelle vorhanden sind, aber nicht im Modell, aktivieren Sie das Kontrollkästchen neben dem entsprechenden Spaltennamen.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-130">To add columns that are present in the source but not in the model, select the checkbox beside the column name.</span></span>  
  
         <span data-ttu-id="fb8c2-131">Die tatsächlichen Daten werden bei der nächsten Aktualisierung in das Modell geladen.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-131">The actual data will be loaded into the model the next time you refresh.</span></span>  
  
    2.  <span data-ttu-id="fb8c2-132">Wenn einige Spalten im Modell nicht mehr in der aktuellen Datenquelle verfügbar sind, wird im Infobereich eine Meldung angezeigt, in der die ungültigen Spalten aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-132">If some columns in the model are no longer available in the current data source, a message appears in the notification area that lists the invalid columns.</span></span> <span data-ttu-id="fb8c2-133">Weitere Schritte sind nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-133">You do not need to do anything else.</span></span>  
  
5.  <span data-ttu-id="fb8c2-134">Klicken Sie auf **Speichern** , um die Änderungen auf das Modell anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-134">Click **Save** to apply the changes to your model.</span></span>  
  
     <span data-ttu-id="fb8c2-135">Wenn Sie den aktuellen Satz von Tabelleneigenschaften speichern, werden Sie u. U. in einer Meldung darauf hingewiesen, dass die Tabellen verarbeitet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-135">When you save the current set of table properties, a message may appear indicating that you need to process the tables.</span></span> <span data-ttu-id="fb8c2-136">Klicken Sie auf **Verarbeiten** , um aktualisierte Daten in das Modell zu laden.</span><span class="sxs-lookup"><span data-stu-id="fb8c2-136">Click **Process** to load updated data into your model.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb8c2-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fb8c2-137">See Also</span></span>  
 <span data-ttu-id="fb8c2-138">[Verarbeiten von Daten &#40;tabellarischen SSAS-&#41;](process-data-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="fb8c2-138">[Process Data &#40;SSAS Tabular&#41;](process-data-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="fb8c2-139">Unterstützte Datenquellen &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="fb8c2-139">Data Sources Supported &#40;SSAS Tabular&#41;</span></span>](tabular-models/data-sources-supported-ssas-tabular.md)  
  
  
