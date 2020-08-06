---
title: Transformations-Editor für Suche (Seite ' Verbindung ') | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.lookuptransformation.referencetable.f1
helpviewer_keywords:
- Lookup Transformation Editor
ms.assetid: e90d6b69-5a26-43c5-8433-5c3c9588e08c
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 381378ac1aca85c6bca825033bc439ebc39fb063
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618103"
---
# <a name="lookup-transformation-editor-connection-page"></a><span data-ttu-id="c919e-102">Transformations-Editor für Suche (Seite 'Verbindung')</span><span class="sxs-lookup"><span data-stu-id="c919e-102">Lookup Transformation Editor (Connection Page)</span></span>
  <span data-ttu-id="c919e-103">Auf der Seite **Verbindung** des Dialogfelds **Transformations-Editor für Suche** können Sie einen Verbindungs-Manager auswählen.</span><span class="sxs-lookup"><span data-stu-id="c919e-103">Use the **Connection** page of the **Lookup Transformation Editor** dialog box to select a connection manager.</span></span> <span data-ttu-id="c919e-104">Wenn Sie einen OLE DB-Verbindungs-Manager auswählen, wählen Sie auch eine Abfrage, Tabelle oder Sicht zum Generieren des Verweisdatasets aus.</span><span class="sxs-lookup"><span data-stu-id="c919e-104">If you select an OLE DB connection manager, you also select a query, table, or view to generate the reference dataset.</span></span>  
  
 <span data-ttu-id="c919e-105">Weitere Informationen zur Transformation für Suche finden Sie unter [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c919e-105">To learn more about the Lookup transformation, see [Lookup Transformation](data-flow/transformations/lookup-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="c919e-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c919e-106">Options</span></span>  
 <span data-ttu-id="c919e-107">Die folgenden Optionen sind verfügbar, wenn Sie im Dialogfeld **Transformations-Editor für Suche** auf der Seite **Allgemein** die Optionen **Vollcache** und Cacheverbindungs-Manager auswählen.</span><span class="sxs-lookup"><span data-stu-id="c919e-107">The following options are available when you select **Full cache** and **Cache connection manager** on the General page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="c919e-108">**Cacheverbindungs-Manager**</span><span class="sxs-lookup"><span data-stu-id="c919e-108">**Cache connection manager**</span></span>  
 <span data-ttu-id="c919e-109">Wählen Sie einen vorhandenen Cacheverbindungs-Manager aus der Liste aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="c919e-109">Select an existing Cache connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="c919e-110">**Neu**</span><span class="sxs-lookup"><span data-stu-id="c919e-110">**New**</span></span>  
 <span data-ttu-id="c919e-111">Erstellen Sie mithilfe des Dialogfelds **Editor für den Cacheverbindungs-Manager** eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="c919e-111">Create a new connection by using the **Cache Connection Manager Editor** dialog box.</span></span>  
  
 <span data-ttu-id="c919e-112">Die folgenden Optionen sind verfügbar, wenn Sie im Dialogfeld **Transformations-Editor für Suche**auf der Seite **Allgemein**die Optionen **Vollcache**, **Teilcache**oder **Kein Cache** und OLE DB-Verbindungs-Manager auswählen.</span><span class="sxs-lookup"><span data-stu-id="c919e-112">The following options are available when you select **Full cache**, **Partial cache**, or **No cache**, and **OLE DB connection manager**, on the General page of the **Lookup Transformation Editor** dialog box.</span></span>  
  
 <span data-ttu-id="c919e-113">**Teilcache**</span><span class="sxs-lookup"><span data-stu-id="c919e-113">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="c919e-114">Wählen Sie einen vorhandenen OLE DB-Verbindungs-Manager aus der Liste aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="c919e-114">Select an existing OLE DB connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="c919e-115">**Neu**</span><span class="sxs-lookup"><span data-stu-id="c919e-115">**New**</span></span>  
 <span data-ttu-id="c919e-116">Erstellen Sie mithilfe des Dialogfelds **OLE DB-Verbindungs-Manager konfigurieren** eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="c919e-116">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="c919e-117">**Tabelle oder Sicht verwenden**</span><span class="sxs-lookup"><span data-stu-id="c919e-117">**Use a table or view**</span></span>  
 <span data-ttu-id="c919e-118">Wählen Sie eine vorhandene Tabelle oder Sicht aus der Liste aus, oder erstellen Sie eine neue Tabelle, indem Sie auf **neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="c919e-118">Select an existing table or view from the list, or create a new table by clicking **New**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c919e-119">Wenn Sie auf der Seite **Erweitert** im **Transformations-Editor für Suche** eine SQL-Anweisung angeben, wird durch diese SQL-Anweisung der hier ausgewählte Tabellenname überschrieben und ersetzt.</span><span class="sxs-lookup"><span data-stu-id="c919e-119">If you specify a SQL statement on the **Advanced** page of the **Lookup Transformation Editor**, that SQL statement overrides and replaces the table name selected here.</span></span> <span data-ttu-id="c919e-120">Weitere Informationen finden Sie unter [Transformations-Editor für Suche &#40;Seite „Erweitert“&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md).</span><span class="sxs-lookup"><span data-stu-id="c919e-120">For more information, see [Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md).</span></span>  
  
 <span data-ttu-id="c919e-121">**Neu**</span><span class="sxs-lookup"><span data-stu-id="c919e-121">**New**</span></span>  
 <span data-ttu-id="c919e-122">Erstellen Sie mithilfe des Dialogfelds **Tabelle erstellen** eine neue Tabelle.</span><span class="sxs-lookup"><span data-stu-id="c919e-122">Create a new table by using the **Create Table** dialog box.</span></span>  
  
 <span data-ttu-id="c919e-123">**Ergebnisse einer SQL-Abfrage verwenden**</span><span class="sxs-lookup"><span data-stu-id="c919e-123">**Use results of an SQL query**</span></span>  
 <span data-ttu-id="c919e-124">Wählen Sie diese Option aus, um nach einer vorhandenen Abfrage zu suchen, eine neue Abfrage zu erstellen, die Abfragesyntax zu überprüfen und eine Vorschau der Abfrageergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c919e-124">Choose this option to browse to a preexisting query, build a new query, check query syntax, and preview query results.</span></span>  
  
 <span data-ttu-id="c919e-125">**Abfrage erstellen**</span><span class="sxs-lookup"><span data-stu-id="c919e-125">**Build query**</span></span>  
 <span data-ttu-id="c919e-126">Erstellen Sie eine auszuführende Transact-SQL-Anweisung mit dem **Abfrage-Generator**, einem grafischen Tool, das verwendet wird, um Abfragen mithilfe des Durchsuchens von Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c919e-126">Create the Transact-SQL statement to run by using **Query Builder**, a graphical tool that is used to create queries by browsing through data.</span></span>  
  
 <span data-ttu-id="c919e-127">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="c919e-127">**Browse**</span></span>  
 <span data-ttu-id="c919e-128">Verwenden Sie diese Option, um nach einer vorhandenen Abfrage zu suchen, die als Datei gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="c919e-128">Use this option to browse to a preexisting query saved as a file.</span></span>  
  
 <span data-ttu-id="c919e-129">**Abfrage analysieren**</span><span class="sxs-lookup"><span data-stu-id="c919e-129">**Parse Query**</span></span>  
 <span data-ttu-id="c919e-130">Überprüft die Syntax der Abfrage.</span><span class="sxs-lookup"><span data-stu-id="c919e-130">Check the syntax of the query.</span></span>  
  
 <span data-ttu-id="c919e-131">**Vorschau**</span><span class="sxs-lookup"><span data-stu-id="c919e-131">**Preview**</span></span>  
 <span data-ttu-id="c919e-132">Zeigen Sie mithilfe des Dialogfelds **Vorschau der Abfrageergebnisse anzeigen** eine Vorschau der Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="c919e-132">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="c919e-133">Diese Option zeigt bis zu 200 Zeilen an.</span><span class="sxs-lookup"><span data-stu-id="c919e-133">This option displays up to 200 rows.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="c919e-134">Externe Ressourcen</span><span class="sxs-lookup"><span data-stu-id="c919e-134">External Resources</span></span>  
 <span data-ttu-id="c919e-135">Blogeintrag [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) (Suchcachemodi) auf blogs.msdn.com</span><span class="sxs-lookup"><span data-stu-id="c919e-135">Blog entry, [Lookup cache modes](https://go.microsoft.com/fwlink/?LinkId=219518) on blogs.msdn.com</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c919e-136">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c919e-136">See Also</span></span>  
 <span data-ttu-id="c919e-137">[Transformations-Editor für Suche &#40;Seite "Allgemein"&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="c919e-137">[Lookup Transformation Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="c919e-138">[Transformations-Editor für Suche &#40;Seite "Spalten"&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span><span class="sxs-lookup"><span data-stu-id="c919e-138">[Lookup Transformation Editor &#40;Columns Page&#41;](../../2014/integration-services/lookup-transformation-editor-columns-page.md) </span></span>  
 <span data-ttu-id="c919e-139">[Transformations-Editor für Suche &#40;Seite "Erweitert"&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="c919e-139">[Lookup Transformation Editor &#40;Advanced Page&#41;](../../2014/integration-services/lookup-transformation-editor-advanced-page.md) </span></span>  
 <span data-ttu-id="c919e-140">[Transformations-Editor für Suche &#40;Seite "Fehlerausgabe"&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span><span class="sxs-lookup"><span data-stu-id="c919e-140">[Lookup Transformation Editor &#40;Error Output Page&#41;](../../2014/integration-services/lookup-transformation-editor-error-output-page.md) </span></span>  
 [<span data-ttu-id="c919e-141">Transformation für Fuzzysuche</span><span class="sxs-lookup"><span data-stu-id="c919e-141">Fuzzy Lookup Transformation</span></span>](data-flow/transformations/fuzzy-lookup-transformation.md)  
  
  
