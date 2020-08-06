---
title: Quellen-Editor für OLE DB (Seite Verbindungs-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.oledbsourceadapter.connection.f1
helpviewer_keywords:
- OLE DB Source Editor
ms.assetid: 53699902-8699-4547-b56b-a5b2079e98b6
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e6b9d841ff902107847a9d85779af41f476315db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621592"
---
# <a name="ole-db-source-editor-connection-manager-page"></a><span data-ttu-id="56e96-102">Quellen-Editor für OLE DB (Seite Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="56e96-102">OLE DB Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="56e96-103">Auf der Seite **Verbindungs-Manager** des Dialogfelds **Quellen-Editor für OLE DB** wählen Sie den OLE DB-Verbindungs-Manager für die Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="56e96-103">Use the **Connection Manager** page of the **OLE DB Source Editor** dialog box to select the OLE DB connection manager for the source.</span></span> <span data-ttu-id="56e96-104">Außerdem können Sie auf dieser Seite eine Tabelle oder Sicht aus der Datenbank auswählen.</span><span class="sxs-lookup"><span data-stu-id="56e96-104">This page also lets you select a table or view from the database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56e96-105">Verwenden Sie zum Laden von Daten aus einer Datenquelle, für die [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2007 verwendet wird, eine OLE DB-Quelle.</span><span class="sxs-lookup"><span data-stu-id="56e96-105">To load data from a data source that uses [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2007, use an OLE DB source.</span></span> <span data-ttu-id="56e96-106">Sie können eine Excel-Quelle nicht zum Laden von Daten aus einer Excel 2007-Datenquelle verwenden.</span><span class="sxs-lookup"><span data-stu-id="56e96-106">You cannot use an Excel source to load data from an Excel 2007 data source.</span></span> <span data-ttu-id="56e96-107">Weitere Informationen finden Sie unter [Configure OLE DB Connection Manager](configure-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="56e96-107">For more information, see [Configure OLE DB Connection Manager](configure-ole-db-connection-manager.md).</span></span>  
>   
>  <span data-ttu-id="56e96-108">Verwenden Sie zum Laden von Daten aus einer Datenquelle, für die [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2003 oder eine frühere Version verwendet wird, eine Excel-Quelle.</span><span class="sxs-lookup"><span data-stu-id="56e96-108">To load data from a data source that uses [!INCLUDE[msCoName](../includes/msconame-md.md)] Office Excel 2003 or earlier, use an Excel source.</span></span> <span data-ttu-id="56e96-109">Weitere Informationen finden Sie unter [Quellen-Editor für Excel &#40;Seite „Verbindungs-Manager“&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="56e96-109">For more information, see [Excel Source Editor &#40;Connection Manager Page&#41;](../../2014/integration-services/excel-source-editor-connection-manager-page.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56e96-110">Die- `CommandTimeout` Eigenschaft der OLE DB Quelle ist nicht im Quellen- **Editor für OLE DB**verfügbar, kann jedoch mit dem **Erweiterter Editor**festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="56e96-110">The `CommandTimeout` property of the OLE DB source is not available in the **OLE DB Source Editor**, but can be set by using the **Advanced Editor**.</span></span> <span data-ttu-id="56e96-111">Weitere Informationen zu dieser Eigenschaft finden Sie im Abschnitt Excel-Quelle von [OLE DB Custom Properties](data-flow/ole-db-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="56e96-111">For more information on this property, see the Excel Source section of [OLE DB Custom Properties](data-flow/ole-db-custom-properties.md).</span></span>  
  
 <span data-ttu-id="56e96-112">Weitere Informationen zur OLE DB-Quelle finden Sie unter [OLE DB Source](data-flow/ole-db-source.md).</span><span class="sxs-lookup"><span data-stu-id="56e96-112">To learn more about the OLE DB source, see [OLE DB Source](data-flow/ole-db-source.md).</span></span>  
  
## <a name="open-the-ole-db-source-editor-connection-manager-page"></a><span data-ttu-id="56e96-113">Öffnen des Quellen-Editors für OLE DB (Seite "Verbindungs-Manager")</span><span class="sxs-lookup"><span data-stu-id="56e96-113">Open the OLE DB Source Editor (Connection Manager Page</span></span>  
  
1.  <span data-ttu-id="56e96-114">Fügen Sie die OLE DB-Quelle dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] Paket in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]hinzu.</span><span class="sxs-lookup"><span data-stu-id="56e96-114">Add the OLE DB source to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="56e96-115">Klicken Sie mit der rechten Maustaste auf die Quellkomponente, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="56e96-115">Right-click the source component and when click **Edit**.</span></span>  
  
3.  <span data-ttu-id="56e96-116">Klicken Sie auf **Verbindungs-Manager**.</span><span class="sxs-lookup"><span data-stu-id="56e96-116">Click **Connection Manager**.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="56e96-117">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="56e96-117">Static Options</span></span>  
 <span data-ttu-id="56e96-118">**Teilcache**</span><span class="sxs-lookup"><span data-stu-id="56e96-118">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="56e96-119">Wählen Sie in der Liste einen vorhandenen Verbindungs-Manager aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="56e96-119">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="56e96-120">**Neu**</span><span class="sxs-lookup"><span data-stu-id="56e96-120">**New**</span></span>  
 <span data-ttu-id="56e96-121">Erstellen Sie mithilfe des Dialogfelds **OLE DB-Verbindungs-Manager konfigurieren** einen neuen Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="56e96-121">Create a new connection manager by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="56e96-122">**Datenzugriffsmodus**</span><span class="sxs-lookup"><span data-stu-id="56e96-122">**Data access mode**</span></span>  
 <span data-ttu-id="56e96-123">Geben Sie die Methode für die Auswahl von Daten aus der Quelle an.</span><span class="sxs-lookup"><span data-stu-id="56e96-123">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="56e96-124">Option</span><span class="sxs-lookup"><span data-stu-id="56e96-124">Option</span></span>|<span data-ttu-id="56e96-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="56e96-125">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="56e96-126">Tabelle oder Sicht</span><span class="sxs-lookup"><span data-stu-id="56e96-126">Table or view</span></span>|<span data-ttu-id="56e96-127">Rufen Sie Daten aus einer Tabelle oder Sicht in der OLE DB-Datenquelle ab.</span><span class="sxs-lookup"><span data-stu-id="56e96-127">Retrieve data from a table or view in the OLE DB data source.</span></span>|  
|<span data-ttu-id="56e96-128">Variable für Tabellenname oder Sichtname</span><span class="sxs-lookup"><span data-stu-id="56e96-128">Table name or view name variable</span></span>|<span data-ttu-id="56e96-129">Gibt den Namen der Tabelle oder Sicht in einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="56e96-129">Specify the table or view name in a variable.</span></span><br /><br /> <span data-ttu-id="56e96-130">**Verwandte Informationen**: [Verwenden von Variablen in Paketen](../../2014/integration-services/use-variables-in-packages.md)</span><span class="sxs-lookup"><span data-stu-id="56e96-130">**Related information:** [Use Variables in Packages](../../2014/integration-services/use-variables-in-packages.md)</span></span>|  
|<span data-ttu-id="56e96-131">SQL-Befehl</span><span class="sxs-lookup"><span data-stu-id="56e96-131">SQL command</span></span>|<span data-ttu-id="56e96-132">Rufen Sie mit SQL-Abfrage Daten aus der OLE DB-Datenquelle ab.</span><span class="sxs-lookup"><span data-stu-id="56e96-132">Retrieve data from the OLE DB data source by using a SQL query.</span></span>|  
|<span data-ttu-id="56e96-133">SQL-Befehl aus Variable</span><span class="sxs-lookup"><span data-stu-id="56e96-133">SQL command from variable</span></span>|<span data-ttu-id="56e96-134">Gibt den SQL-Abfragetext in einer Variablen an.</span><span class="sxs-lookup"><span data-stu-id="56e96-134">Specify the SQL query text in a variable.</span></span>|  
  
 <span data-ttu-id="56e96-135">**Vorschau**</span><span class="sxs-lookup"><span data-stu-id="56e96-135">**Preview**</span></span>  
 <span data-ttu-id="56e96-136">Zeigen Sie mithilfe des Dialogfelds **Datenansicht** eine Vorschau der Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="56e96-136">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="56e96-137">In der**Vorschau** können bis zu 200 Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="56e96-137">**Preview** can display up to 200 rows.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="56e96-138">In der Datenvorschau enthalten Spalten mit einem CLR-benutzerdefinierten Typ keine Daten.</span><span class="sxs-lookup"><span data-stu-id="56e96-138">When you preview data, columns with a CLR user-defined type do not contain data.</span></span> <span data-ttu-id="56e96-139">Stattdessen werden die Werte \<value too big to display> oder „System.Byte[]“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="56e96-139">Instead the values \<value too big to display> or System.Byte[] display.</span></span> <span data-ttu-id="56e96-140">Der erste Wert wird angezeigt, wenn mithilfe des SQL-OLE DB-Anbieters auf die Datenquelle zugegriffen wird. Der zweite Wert wird bei Verwendung des [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client-Anbieters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="56e96-140">The former displays when the data source is accessed using the SQL OLE DB provider, the latter when using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client provider.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="56e96-141">Dynamische Optionen (Datenzugriffsmodus)</span><span class="sxs-lookup"><span data-stu-id="56e96-141">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="56e96-142">Datenzugriffsmodus = Tabelle oder Sicht</span><span class="sxs-lookup"><span data-stu-id="56e96-142">Data access mode = Table or view</span></span>  
 <span data-ttu-id="56e96-143">**Name der Tabelle oder Sicht**</span><span class="sxs-lookup"><span data-stu-id="56e96-143">**Name of the table or the view**</span></span>  
 <span data-ttu-id="56e96-144">Wählen Sie den Namen der Tabelle oder Sicht aus einer Liste der verfügbaren Namen in der Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="56e96-144">Select the name of the table or view from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--table-name-or-view-name-variable"></a><span data-ttu-id="56e96-145">Datenzugriffsmodus = Variable für Tabellenname oder Sichtname</span><span class="sxs-lookup"><span data-stu-id="56e96-145">Data access mode = Table name or view name variable</span></span>  
 <span data-ttu-id="56e96-146">**Variablenname**</span><span class="sxs-lookup"><span data-stu-id="56e96-146">**Variable name**</span></span>  
 <span data-ttu-id="56e96-147">Wählen Sie die Variable aus, die den Namen der Tabelle oder Sicht enthält.</span><span class="sxs-lookup"><span data-stu-id="56e96-147">Select the variable that contains the name of the table or view.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="56e96-148">Datenzugriffsmodus = SQL-Befehl</span><span class="sxs-lookup"><span data-stu-id="56e96-148">Data access mode = SQL command</span></span>  
 <span data-ttu-id="56e96-149">**SQL-Befehlstext**</span><span class="sxs-lookup"><span data-stu-id="56e96-149">**SQL command text**</span></span>  
 <span data-ttu-id="56e96-150">Geben Sie den Text einer SQL-Abfrage ein, und erstellen Sie die Abfrage, indem Sie auf **Abfrage erstellen**klicken, oder suchen Sie nach der Datei, die den Abfragetext enthält, indem Sie auf **Durchsuchen**klicken.</span><span class="sxs-lookup"><span data-stu-id="56e96-150">Enter the text of a SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="56e96-151">**Parameter**</span><span class="sxs-lookup"><span data-stu-id="56e96-151">**Parameters**</span></span>  
 <span data-ttu-id="56e96-152">Wenn Sie eine parametrisierte Abfrage eingeben und im Abfragetext ?</span><span class="sxs-lookup"><span data-stu-id="56e96-152">If you have entered a parameterized query by using ?</span></span> <span data-ttu-id="56e96-153">als Parameterplatzhalter verwenden, können Sie den Paketvariablen mithilfe des Dialogfelds **Abfrageparameter festlegen** Abfrageeingabeparameter zuordnen.</span><span class="sxs-lookup"><span data-stu-id="56e96-153">as a parameter placeholder in the query text, use the **Set Query Parameters** dialog box to map query input parameters to package variables.</span></span>  
  
 <span data-ttu-id="56e96-154">**Abfrage erstellen**</span><span class="sxs-lookup"><span data-stu-id="56e96-154">**Build query**</span></span>  
 <span data-ttu-id="56e96-155">Mithilfe des Dialogfelds **Abfrage-Generator** können Sie die SQL-Abfrage visuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="56e96-155">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="56e96-156">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="56e96-156">**Browse**</span></span>  
 <span data-ttu-id="56e96-157">Mithilfe des Dialogfelds **Öffnen** können Sie nach der Datei suchen, die den Text der SQL-Abfrage enthält.</span><span class="sxs-lookup"><span data-stu-id="56e96-157">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
 <span data-ttu-id="56e96-158">**Abfrage analysieren**</span><span class="sxs-lookup"><span data-stu-id="56e96-158">**Parse query**</span></span>  
 <span data-ttu-id="56e96-159">Überprüft die Syntax des Abfragetexts.</span><span class="sxs-lookup"><span data-stu-id="56e96-159">Verify the syntax of the query text.</span></span>  
  
### <a name="data-access-mode--sql-command-from-variable"></a><span data-ttu-id="56e96-160">Datenzugriffsmodus = SQL-Befehl aus Variable</span><span class="sxs-lookup"><span data-stu-id="56e96-160">Data access mode = SQL command from variable</span></span>  
 <span data-ttu-id="56e96-161">**Variablenname**</span><span class="sxs-lookup"><span data-stu-id="56e96-161">**Variable name**</span></span>  
 <span data-ttu-id="56e96-162">Wählen Sie die Variable aus, die den Text für die SQL-Abfrage enthält.</span><span class="sxs-lookup"><span data-stu-id="56e96-162">Select the variable that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56e96-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56e96-163">See Also</span></span>  
 <span data-ttu-id="56e96-164">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="56e96-164">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="56e96-165">[OLE DB &#40;Seite "Spalten" des Quellen-Editors&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="56e96-165">[OLE DB Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ole-db-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="56e96-166">[OLE DB Quellen-Editor &#40;Seite Fehlerausgabe&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="56e96-166">[OLE DB Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ole-db-source-editor-error-output-page.md) </span></span>  
 <span data-ttu-id="56e96-167">[Extrahieren von Daten mithilfe der OLE DB Quelle](data-flow/extract-data-by-using-the-ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="56e96-167">[Extract Data by Using the OLE DB Source](data-flow/extract-data-by-using-the-ole-db-source.md) </span></span>  
 [<span data-ttu-id="56e96-168">OLE DB-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="56e96-168">OLE DB Connection Manager</span></span>](connection-manager/ole-db-connection-manager.md)  
  
  
