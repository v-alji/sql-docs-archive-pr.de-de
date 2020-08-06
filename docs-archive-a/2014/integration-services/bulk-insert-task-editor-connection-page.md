---
title: Massen Einfügungs Task-Editor (Seite Verbindung) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.bulkinserttask.connection.f1
helpviewer_keywords:
- Bulk Insert Task Editor
ms.assetid: 51252c20-8865-4ede-a3fd-bd73a968f47d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b2cd722fd8520ff011c0d57040a55d624178e15e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723001"
---
# <a name="bulk-insert-task-editor-connection-page"></a><span data-ttu-id="dd1c5-102">Masseneinfügungstask-Editor (Seite Verbindung)</span><span class="sxs-lookup"><span data-stu-id="dd1c5-102">Bulk Insert Task Editor (Connection Page)</span></span>
  <span data-ttu-id="dd1c5-103">Mithilfe der Seite **Verbindung** im Dialogfeld **Masseneinfügungstask-Editor** können Sie die Quelle und das Ziel des Masseneinfügevorgangs und das zu verwendende Format angeben.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-103">Use the **Connection** page of the **Bulk Insert Task Editor** dialog box to specify the source and destination of the bulk insert operation and the format to use.</span></span>  
  
 <span data-ttu-id="dd1c5-104">Informationen zum Arbeiten mit Masseneinfügungen finden Sie unter [Masseneinfügungstask](control-flow/bulk-insert-task.md) und [Formatdateien zum Importieren oder Exportieren von Daten &#40;SQL Server&#41;](../relational-databases/import-export/format-files-for-importing-or-exporting-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="dd1c5-104">To learn about working with bulk inserts, see [Bulk Insert Task](control-flow/bulk-insert-task.md) and [Format Files for Importing or Exporting Data &#40;SQL Server&#41;](../relational-databases/import-export/format-files-for-importing-or-exporting-data-sql-server.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="dd1c5-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="dd1c5-105">Options</span></span>  
 <span data-ttu-id="dd1c5-106">**Connection**</span><span class="sxs-lookup"><span data-stu-id="dd1c5-106">**Connection**</span></span>  
 <span data-ttu-id="dd1c5-107">Wählen Sie einen OLE DB-Verbindungs-Manager aus der Liste aus, oder klicken Sie auf \<**New connection...**>, um eine neue Verbindung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-107">Select an OLE DB connection manager in the list, or click \<**New connection...**> to create a new connection.</span></span>  
  
 <span data-ttu-id="dd1c5-108">**Verwandte Themen:** [OLE DB-Verbindungs-Manager](connection-manager/ole-db-connection-manager.md), [OLE DB-Verbindungs-Manager konfigurieren](../../2014/integration-services/configure-ole-db-connection-manager.md)</span><span class="sxs-lookup"><span data-stu-id="dd1c5-108">**Related Topics:** [OLE DB Connection Manager](connection-manager/ole-db-connection-manager.md), [Configure OLE DB Connection Manager](../../2014/integration-services/configure-ole-db-connection-manager.md)</span></span>  
  
 <span data-ttu-id="dd1c5-109">**DestinationTable**</span><span class="sxs-lookup"><span data-stu-id="dd1c5-109">**DestinationTable**</span></span>  
 <span data-ttu-id="dd1c5-110">Geben Sie den Namen der Zieltabelle oder Zielsicht ein, oder wählen Sie aus der Liste eine Tabelle oder Sicht aus.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-110">Type the name of the destination table or view or select a table or view in the list.</span></span>  
  
 <span data-ttu-id="dd1c5-111">**Format**</span><span class="sxs-lookup"><span data-stu-id="dd1c5-111">**Format**</span></span>  
 <span data-ttu-id="dd1c5-112">Wählen Sie die Quelle des Formats für die Masseneinfügung aus.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-112">Select the source of the format for the bulk insert.</span></span> <span data-ttu-id="dd1c5-113">Diese Eigenschaft besitzt die in der folgenden Tabelle aufgeführten Optionen.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-113">This property has the options listed in the following table.</span></span>  
  
|<span data-ttu-id="dd1c5-114">Wert</span><span class="sxs-lookup"><span data-stu-id="dd1c5-114">Value</span></span>|<span data-ttu-id="dd1c5-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="dd1c5-115">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="dd1c5-116">**Use File**</span><span class="sxs-lookup"><span data-stu-id="dd1c5-116">**Use File**</span></span>|<span data-ttu-id="dd1c5-117">Wählen Sie eine Datei mit Formatspezifikationen aus.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-117">Select a file containing the format specification.</span></span> <span data-ttu-id="dd1c5-118">Nach Auswahl dieser Option wird die dynamische Option **FormatFile**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-118">Selecting this option displays the dynamic option, **FormatFile**.</span></span>|  
|<span data-ttu-id="dd1c5-119">**Specify**</span><span class="sxs-lookup"><span data-stu-id="dd1c5-119">**Specify**</span></span>|<span data-ttu-id="dd1c5-120">Geben Sie das Format an.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-120">Specify the format.</span></span> <span data-ttu-id="dd1c5-121">Wenn Sie diese Option auswählen, werden die dynamischen Optionen `RowDelimiter` und angezeigt `ColumnDelimiter` .</span><span class="sxs-lookup"><span data-stu-id="dd1c5-121">Selecting this option displays the dynamic options, `RowDelimiter` and `ColumnDelimiter`.</span></span>|  
  
 <span data-ttu-id="dd1c5-122">**File**</span><span class="sxs-lookup"><span data-stu-id="dd1c5-122">**File**</span></span>  
 <span data-ttu-id="dd1c5-123">Wählen Sie einen Dateiverbindungs-Manager oder Verbindungs-Manager für Flatfiles in der Liste aus, oder klicken Sie auf \<**New connection...**>, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-123">Select a File or Flat File connection manager in the list, or click \<**New connection...**> to create a new connection.</span></span>  
  
 <span data-ttu-id="dd1c5-124">Der Speicherort ist relativ zur SQL Server-Datenbank-Engine, die im Verbindungs-Manager für diesen Task angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-124">The file location is relative to the SQL Server Database Engine specified in the connection manager for this task.</span></span> <span data-ttu-id="dd1c5-125">Die SQL Server-Datenbank-Engine muss auf die Textdatei zugreifen können, und zwar entweder auf einer lokalen Festplatte des Servers oder über eine Freigabe oder einem SQL Server zugeordneten Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-125">The text file must be accessible by the SQL Server Database Engine either on a local hard drive on the server, or via a share or mapped drive to the SQL Server.</span></span> <span data-ttu-id="dd1c5-126">Auf die Datei wird nicht von der SSIS-Laufzeit zugegriffen.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-126">The file is not accessed by the SSIS Runtime.</span></span>  
  
 <span data-ttu-id="dd1c5-127">Wenn Sie auf die Quelldatei mithilfe eines Flatfileverbindungs-Managers zugreifen, verwendet der Masseneinfügungstask nicht das im Flatfileverbindungs-Manager angegebene Format.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-127">If you access the source file by using a Flat File connection manager, the Bulk Insert task does not use the format specified in the Flat File connection manager.</span></span> <span data-ttu-id="dd1c5-128">Stattdessen verwendet der Masseneinfügungstask entweder das in einer Formatdatei angegebene Format oder die Werte der Eigenschaften RowDelimiter und ColumnDelimiter des Tasks.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-128">Instead, the Bulk Insert task uses either the format specified in a format file or the values of the RowDelimiter and ColumnDelimiter properties of the task.</span></span>  
  
 <span data-ttu-id="dd1c5-129">**Verwandte Themen:** [Dateiverbindungs-Manager](connection-manager/file-connection-manager.md), [Dateiverbindungs-Manager-Editor](../../2014/integration-services/file-connection-manager-editor.md), [Verbindungs-Manager für Flatfiles](connection-manager/flat-file-connection-manager.md), [Verbindungs-Manager-Editor für Flatfiles &#40;Seite „Allgemein“&#41;](general-page-of-integration-services-designers-options.md), [Verbindungs-Manager-Editor für Flatfiles &#40;Seite „Spalten“&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md), [Verbindungs-Manager-Editor für Flatfiles &#40;Seite „Erweitert“&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md)</span><span class="sxs-lookup"><span data-stu-id="dd1c5-129">**Related Topics:** [File Connection Manager](connection-manager/file-connection-manager.md), [File Connection Manager Editor](../../2014/integration-services/file-connection-manager-editor.md), [Flat File Connection Manager](connection-manager/flat-file-connection-manager.md), [Flat File Connection Manager Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md), [Flat File Connection Manager Editor &#40;Columns Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-columns-page.md), [Flat File Connection Manager Editor &#40;Advanced Page&#41;](../../2014/integration-services/flat-file-connection-manager-editor-advanced-page.md)</span></span>  
  
 <span data-ttu-id="dd1c5-130">**Tabellen aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="dd1c5-130">**Refresh Tables**</span></span>  
 <span data-ttu-id="dd1c5-131">Aktualisieren Sie die Liste der Tabellen und Sichten.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-131">Refresh the list of tables and views.</span></span>  
  
## <a name="format-dynamic-options"></a><span data-ttu-id="dd1c5-132">Format (dynamische Optionen)</span><span class="sxs-lookup"><span data-stu-id="dd1c5-132">Format Dynamic Options</span></span>  
  
### <a name="format--use-file"></a><span data-ttu-id="dd1c5-133">Format = Use File</span><span class="sxs-lookup"><span data-stu-id="dd1c5-133">Format = Use File</span></span>  
 <span data-ttu-id="dd1c5-134">**FormatFile**</span><span class="sxs-lookup"><span data-stu-id="dd1c5-134">**FormatFile**</span></span>  
 <span data-ttu-id="dd1c5-135">Geben Sie den Pfad der Formatdatei ein, oder klicken Sie auf die Schaltfläche mit den Auslassungspunkten ( **…** ), um nach der Formatdatei zu suchen.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-135">Type the path of the format file or click the ellipsis button **(...)** to locate the format file.</span></span>  
  
### <a name="format--specify"></a><span data-ttu-id="dd1c5-136">Format = Specify</span><span class="sxs-lookup"><span data-stu-id="dd1c5-136">Format = Specify</span></span>  
 `RowDelimiter`  
 <span data-ttu-id="dd1c5-137">Geben Sie das Zeilentrennzeichen in der Quelldatei an.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-137">Specify the row delimiter in the source file.</span></span> <span data-ttu-id="dd1c5-138">Der Standardwert ist **{CR}{LF}** .</span><span class="sxs-lookup"><span data-stu-id="dd1c5-138">The default value is **{CR}{LF}**.</span></span>  
  
 `ColumnDelimiter`  
 <span data-ttu-id="dd1c5-139">Geben Sie das Spaltentrennzeichen in der Quelldatei an.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-139">Specify the column delimiter in the source file.</span></span> <span data-ttu-id="dd1c5-140">Der Standardwert ist **Tabstopp**.</span><span class="sxs-lookup"><span data-stu-id="dd1c5-140">The default is **Tab**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dd1c5-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dd1c5-141">See Also</span></span>  
 <span data-ttu-id="dd1c5-142">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="dd1c5-142">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="dd1c5-143">[Massen Einfügungs Task-Editor &#40;Seite Allgemein&#41;](../../2014/integration-services/bulk-insert-task-editor-general-page.md) </span><span class="sxs-lookup"><span data-stu-id="dd1c5-143">[Bulk Insert Task Editor &#40;General Page&#41;](../../2014/integration-services/bulk-insert-task-editor-general-page.md) </span></span>  
 <span data-ttu-id="dd1c5-144">[Massen Einfügungs Task-Editor &#40;Options Seite&#41;](../../2014/integration-services/bulk-insert-task-editor-options-page.md) </span><span class="sxs-lookup"><span data-stu-id="dd1c5-144">[Bulk Insert Task Editor &#40;Options Page&#41;](../../2014/integration-services/bulk-insert-task-editor-options-page.md) </span></span>  
 <span data-ttu-id="dd1c5-145">[Seite Ausdrücke](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="dd1c5-145">[Expressions Page](expressions/expressions-page.md) </span></span>  
 <span data-ttu-id="dd1c5-146">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="dd1c5-146">[BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql) </span></span>  
 [<span data-ttu-id="dd1c5-147">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="dd1c5-147">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
