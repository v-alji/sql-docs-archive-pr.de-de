---
title: Ziel-Editor für SQL (Seite Verbindungs-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdestadapter.connection.f1
helpviewer_keywords:
- SQL Server Destination Editor
ms.assetid: 423e1654-54af-47c6-ab6f-98670534557d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 4f3a552968cb297de337e1f0c406b444d95dc5a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616594"
---
# <a name="sql-destination-editor-connection-manager-page"></a><span data-ttu-id="3807a-102">Ziel-Editor für SQL (Seite Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="3807a-102">SQL Destination Editor (Connection Manager Page)</span></span>
  <span data-ttu-id="3807a-103">Mithilfe der Seite **Verbindungs-Manager** des Dialogfelds **Ziel-Editor für SQL** können Sie Informationen zur Datenquelle angeben und eine Vorschau der Ergebnisse anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3807a-103">Use the **Connection Manager** page of the **SQL Destination Editor** dialog box to specify data source information, and to preview the results.</span></span> <span data-ttu-id="3807a-104">Das [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Ziel lädt Daten in Tabellen oder Sichten in einer- [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Datenbank.</span><span class="sxs-lookup"><span data-stu-id="3807a-104">The [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] destination loads data into tables or views in a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="3807a-105">Weitere Informationen zum SQL Server-Ziel finden Sie unter [SQL Server Destination](data-flow/sql-server-destination.md).</span><span class="sxs-lookup"><span data-stu-id="3807a-105">To learn more about the SQL Server destination, see [SQL Server Destination](data-flow/sql-server-destination.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3807a-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="3807a-106">Options</span></span>  
 <span data-ttu-id="3807a-107">**Teilcache**</span><span class="sxs-lookup"><span data-stu-id="3807a-107">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="3807a-108">Wählen Sie eine vorhandene Verbindung aus der Liste aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="3807a-108">Select an existing connection from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="3807a-109">**Neu**</span><span class="sxs-lookup"><span data-stu-id="3807a-109">**New**</span></span>  
 <span data-ttu-id="3807a-110">Erstellen Sie mithilfe des Dialogfelds **OLE DB-Verbindungs-Manager konfigurieren** eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="3807a-110">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
 <span data-ttu-id="3807a-111">**Tabelle oder Sicht verwenden**</span><span class="sxs-lookup"><span data-stu-id="3807a-111">**Use a table or view**</span></span>  
 <span data-ttu-id="3807a-112">Wählen Sie eine vorhandene Tabelle oder Sicht aus der Liste aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="3807a-112">Select an existing table or view from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="3807a-113">**Neu**</span><span class="sxs-lookup"><span data-stu-id="3807a-113">**New**</span></span>  
 <span data-ttu-id="3807a-114">Erstellen Sie mithilfe des Dialogfelds **Tabelle erstellen** eine neue Tabelle.</span><span class="sxs-lookup"><span data-stu-id="3807a-114">Create a new table by using the **Create Table** dialog box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3807a-115">Wenn Sie auf **Neu**klicken, generiert [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] eine Standard-CREATE TABLE-Anweisung auf Grundlage der verbundenen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="3807a-115">When you click **New**, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] generates a default CREATE TABLE statement based on the connected data source.</span></span> <span data-ttu-id="3807a-116">Diese Standard-CREATE TABLE-Anweisung enthält nicht das FILESTREAM-Attribut, selbst wenn die Quelltabelle eine Spalte mit der Erklärung des FILESTREAM-Attributs enthält.</span><span class="sxs-lookup"><span data-stu-id="3807a-116">This default CREATE TABLE statement will not include the FILESTREAM attribute even if the source table includes a column with the FILESTREAM attribute declared.</span></span> <span data-ttu-id="3807a-117">Um eine [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Komponente mit dem FILESTREAM-Attribut auszuführen, implementieren Sie zunächst die FILESTREAM-Speicherung in der Zieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="3807a-117">To run an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] component with the FILESTREAM attribute, first implement FILESTREAM storage on the destination database.</span></span> <span data-ttu-id="3807a-118">Fügen Sie dann das FILESTREAM-Attribut der CREATE TABLE-Anweisung im Dialogfeld **Tabelle erstellen** hinzu.</span><span class="sxs-lookup"><span data-stu-id="3807a-118">Then, add the FILESTREAM attribute to the CREATE TABLE statement in the **Create Table** dialog box.</span></span> <span data-ttu-id="3807a-119">Weitere Informationen finden Sie unter [Blob-Daten &#40;Binary Large Object, SQL Server&#41;](../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3807a-119">For more information, see [Binary Large Object &#40;Blob&#41; Data &#40;SQL Server&#41;](../relational-databases/blob/binary-large-object-blob-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="3807a-120">**Vorschau**</span><span class="sxs-lookup"><span data-stu-id="3807a-120">**Preview**</span></span>  
 <span data-ttu-id="3807a-121">Zeigen Sie mithilfe des Dialogfelds **Vorschau der Abfrageergebnisse anzeigen** eine Vorschau der Ergebnisse an.</span><span class="sxs-lookup"><span data-stu-id="3807a-121">Preview results by using the **Preview Query Results** dialog box.</span></span> <span data-ttu-id="3807a-122">In der Vorschau können bis zu 200 Zeilen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3807a-122">Preview can display up to 200 rows.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3807a-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3807a-123">See Also</span></span>  
 <span data-ttu-id="3807a-124">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="3807a-124">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="3807a-125">[Ziel-Editor für SQL &#40;Seite "Zuordnungen"&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span><span class="sxs-lookup"><span data-stu-id="3807a-125">[SQL Destination Editor &#40;Mappings Page&#41;](../../2014/integration-services/sql-destination-editor-mappings-page.md) </span></span>  
 <span data-ttu-id="3807a-126">[Ziel-Editor für SQL &#40;Seite "Erweitert"&#41;](../../2014/integration-services/sql-destination-editor-advanced-page.md) </span><span class="sxs-lookup"><span data-stu-id="3807a-126">[SQL Destination Editor &#40;Advanced Page&#41;](../../2014/integration-services/sql-destination-editor-advanced-page.md) </span></span>  
 [<span data-ttu-id="3807a-127">Massenladen von Daten mithilfe des SQL Server-Ziels</span><span class="sxs-lookup"><span data-stu-id="3807a-127">Bulk Load Data by Using the SQL Server Destination</span></span>](data-flow/bulk-load-data-by-using-the-sql-server-destination.md)  
  
  
