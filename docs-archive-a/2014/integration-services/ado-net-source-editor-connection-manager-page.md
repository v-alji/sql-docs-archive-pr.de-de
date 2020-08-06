---
title: ADO NET-Quellen-Editor (Seite Verbindungs-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.adonetsource.connection.f1
ms.assetid: 7de3f438-bdd6-49b5-937a-47369e754943
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 19dd9c256f15bc9022f7267cb38b6f91bd4d8a5c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721685"
---
# <a name="ado-net-source-editor-connection-manager-page"></a><span data-ttu-id="65f09-102">ADO.NET-Quellen-Editor (Seite 'Verbindungs-Manager')</span><span class="sxs-lookup"><span data-stu-id="65f09-102">ADO NET Source Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="65f09-103">Auf der Seite **Verbindungs-Manager** des Dialogfelds **ADO.NET-Quellen-Editor** wählen Sie den [!INCLUDE[vstecado](../includes/vstecado-md.md)] -Verbindungs-Manager für die Quelle aus.</span><span class="sxs-lookup"><span data-stu-id="65f09-103">Use the **Connection Manager** page of the **ADO NET Source Editor** dialog box to select the [!INCLUDE[vstecado](../includes/vstecado-md.md)] connection manager for the source.</span></span> <span data-ttu-id="65f09-104">Außerdem können Sie auf dieser Seite eine Tabelle oder Sicht aus der Datenbank auswählen.</span><span class="sxs-lookup"><span data-stu-id="65f09-104">This page also lets you select a table or view from the database.</span></span>  
  
 <span data-ttu-id="65f09-105">Weitere Informationen zur ADO NET-Quelle finden Sie unter [ADO NET Source](data-flow/ado-net-source.md).</span><span class="sxs-lookup"><span data-stu-id="65f09-105">To learn more about the ADO NET source, see [ADO NET Source](data-flow/ado-net-source.md).</span></span>  
  
 <span data-ttu-id="65f09-106">**So öffnen Sie die Seite "Verbindungs-Manager"**</span><span class="sxs-lookup"><span data-stu-id="65f09-106">**To open the Connection Manager page**</span></span>  
  
1.  <span data-ttu-id="65f09-107">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket, das ADO.NET als Quelle hat.</span><span class="sxs-lookup"><span data-stu-id="65f09-107">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that has the ADO NET source.</span></span>  
  
2.  <span data-ttu-id="65f09-108">Doppelklicken Sie auf der Registerkarte **Datenfluss** auf die ADO.NET-Quelle.</span><span class="sxs-lookup"><span data-stu-id="65f09-108">On the **Data Flow** tab, double-click the ADO NET source.</span></span>  
  
3.  <span data-ttu-id="65f09-109">Klicken Sie im **ADO.NET-Quellen-Editor**auf **Verbindungs-Manager**.</span><span class="sxs-lookup"><span data-stu-id="65f09-109">In the **ADO NET Source Editor**, click **Connection Manager**.</span></span>  
  
## <a name="static-options"></a><span data-ttu-id="65f09-110">Statische Optionen</span><span class="sxs-lookup"><span data-stu-id="65f09-110">Static Options</span></span>  
 <span data-ttu-id="65f09-111">**ADO.NET-Verbindungs-Manager**</span><span class="sxs-lookup"><span data-stu-id="65f09-111">**ADO.NET connection manager**</span></span>  
 <span data-ttu-id="65f09-112">Wählen Sie in der Liste einen vorhandenen Verbindungs-Manager aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="65f09-112">Select an existing connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="65f09-113">**Neu**</span><span class="sxs-lookup"><span data-stu-id="65f09-113">**New**</span></span>  
 <span data-ttu-id="65f09-114">Erstellen Sie mithilfe des Dialogfelds **ADO.NET-Verbindungs-Manager konfigurieren** einen neuen Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="65f09-114">Create a new connection manager by using the **Configure ADO.NET Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="65f09-115">**Datenzugriffsmodus**</span><span class="sxs-lookup"><span data-stu-id="65f09-115">**Data access mode**</span></span>  
 <span data-ttu-id="65f09-116">Geben Sie die Methode für die Auswahl von Daten aus der Quelle an.</span><span class="sxs-lookup"><span data-stu-id="65f09-116">Specify the method for selecting data from the source.</span></span>  
  
|<span data-ttu-id="65f09-117">Option</span><span class="sxs-lookup"><span data-stu-id="65f09-117">Option</span></span>|<span data-ttu-id="65f09-118">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="65f09-118">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="65f09-119">Tabelle oder Sicht</span><span class="sxs-lookup"><span data-stu-id="65f09-119">Table or view</span></span>|<span data-ttu-id="65f09-120">Rufen Sie Daten aus einer Tabelle oder Sicht in der [!INCLUDE[vstecado](../includes/vstecado-md.md)] -Datenquelle ab.</span><span class="sxs-lookup"><span data-stu-id="65f09-120">Retrieve data from a table or view in the [!INCLUDE[vstecado](../includes/vstecado-md.md)] data source.</span></span>|  
|<span data-ttu-id="65f09-121">SQL-Befehl</span><span class="sxs-lookup"><span data-stu-id="65f09-121">SQL command</span></span>|<span data-ttu-id="65f09-122">Rufen Sie mit SQL-Abfrage Daten aus der [!INCLUDE[vstecado](../includes/vstecado-md.md)] -Datenquelle ab.</span><span class="sxs-lookup"><span data-stu-id="65f09-122">Retrieve data from the [!INCLUDE[vstecado](../includes/vstecado-md.md)] data source by using a SQL query.</span></span>|  
  
 <span data-ttu-id="65f09-123">**Vorschau**</span><span class="sxs-lookup"><span data-stu-id="65f09-123">**Preview**</span></span>  
 <span data-ttu-id="65f09-124">Zeigen Sie mithilfe des Dialogfelds **Datenansicht** eine Vorschau der Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="65f09-124">Preview results by using the **Data View** dialog box.</span></span> <span data-ttu-id="65f09-125">In der**Vorschau** können bis zu 200 Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="65f09-125">**Preview** can display up to 200 rows.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="65f09-126">In der Datenvorschau enthalten Spalten mit einem CLR-benutzerdefinierten Typ keine Daten.</span><span class="sxs-lookup"><span data-stu-id="65f09-126">When you preview data, columns with a CLR user-defined type do not contain data.</span></span> <span data-ttu-id="65f09-127">Stattdessen werden die Werte \<value too big to display> oder „System.Byte[]“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65f09-127">Instead the values \<value too big to display> or System.Byte[] display.</span></span> <span data-ttu-id="65f09-128">Der erste Wert wird angezeigt, wenn mithilfe des [!INCLUDE[vstecado](../includes/vstecado-md.md)] -Anbieters auf die Datenquelle zugegriffen wird. Der zweite Wert wird bei Verwendung des [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client-Anbieters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="65f09-128">The former displays when the data source is accessed by using the [!INCLUDE[vstecado](../includes/vstecado-md.md)] provider, the latter when using the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Native Client provider.</span></span>  
  
## <a name="data-access-mode-dynamic-options"></a><span data-ttu-id="65f09-129">Dynamische Optionen (Datenzugriffsmodus)</span><span class="sxs-lookup"><span data-stu-id="65f09-129">Data Access Mode Dynamic Options</span></span>  
  
### <a name="data-access-mode--table-or-view"></a><span data-ttu-id="65f09-130">Datenzugriffsmodus = Tabelle oder Sicht</span><span class="sxs-lookup"><span data-stu-id="65f09-130">Data access mode = Table or view</span></span>  
 <span data-ttu-id="65f09-131">**Name der Tabelle oder Sicht**</span><span class="sxs-lookup"><span data-stu-id="65f09-131">**Name of the table or the view**</span></span>  
 <span data-ttu-id="65f09-132">Wählen Sie den Namen der Tabelle oder Sicht aus einer Liste der verfügbaren Namen in der Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="65f09-132">Select the name of the table or view from a list of those available in the data source.</span></span>  
  
### <a name="data-access-mode--sql-command"></a><span data-ttu-id="65f09-133">Datenzugriffsmodus = SQL-Befehl</span><span class="sxs-lookup"><span data-stu-id="65f09-133">Data access mode = SQL command</span></span>  
 <span data-ttu-id="65f09-134">**SQL-Befehlstext**</span><span class="sxs-lookup"><span data-stu-id="65f09-134">**SQL command text**</span></span>  
 <span data-ttu-id="65f09-135">Geben Sie den Text einer SQL-Abfrage ein, und erstellen Sie die Abfrage, indem Sie auf **Abfrage erstellen**klicken, oder suchen Sie nach der Datei, die den Abfragetext enthält, indem Sie auf **Durchsuchen**klicken.</span><span class="sxs-lookup"><span data-stu-id="65f09-135">Enter the text of a SQL query, build the query by clicking **Build Query**, or locate the file that contains the query text by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="65f09-136">**Abfrage erstellen**</span><span class="sxs-lookup"><span data-stu-id="65f09-136">**Build query**</span></span>  
 <span data-ttu-id="65f09-137">Mithilfe des Dialogfelds **Abfrage-Generator** können Sie die SQL-Abfrage visuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="65f09-137">Use the **Query Builder** dialog box to construct the SQL query visually.</span></span>  
  
 <span data-ttu-id="65f09-138">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="65f09-138">**Browse**</span></span>  
 <span data-ttu-id="65f09-139">Mithilfe des Dialogfelds **Öffnen** können Sie nach der Datei suchen, die den Text der SQL-Abfrage enthält.</span><span class="sxs-lookup"><span data-stu-id="65f09-139">Use the **Open** dialog box to locate the file that contains the text of the SQL query.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65f09-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="65f09-140">See Also</span></span>  
 <span data-ttu-id="65f09-141">[ADO.net-Quellen-Editor &#40;Seite "Spalten"&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="65f09-141">[ADO NET Source Editor &#40;Columns Page&#41;](../../2014/integration-services/ado-net-source-editor-columns-page.md) </span></span>  
 <span data-ttu-id="65f09-142">[ADO NET-Quellen-Editor &#40;Seite "Fehlerausgabe"&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="65f09-142">[ADO NET Source Editor &#40;Error Output Page&#41;](../../2014/integration-services/ado-net-source-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="65f09-143">ADO.NET-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="65f09-143">ADO.NET Connection Manager</span></span>](connection-manager/ado-net-connection-manager.md)  
  
  
