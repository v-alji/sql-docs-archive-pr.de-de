---
title: SQL Server-Ziel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlserverdest.f1
helpviewer_keywords:
- SQL Server destination
- loading data
- destinations [Integration Services], SQL Server
- inserting data
- bulk load [Integration Services]
ms.assetid: a0227cd8-6944-4547-87e8-7b2507e26442
author: chugugrace
ms.author: chugu
ms.openlocfilehash: fcd65007e1e6af36386cb2ceba1f7242305b81a5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697033"
---
# <a name="sql-server-destination"></a><span data-ttu-id="8f205-102">SQL Server-Ziel</span><span class="sxs-lookup"><span data-stu-id="8f205-102">SQL Server Destination</span></span>
  <span data-ttu-id="8f205-103">Das SQL Server-Ziel stellt eine Verbindung mit einer lokalen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank her und kopiert Daten per Massenladen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Tabellen und -Sichten.</span><span class="sxs-lookup"><span data-stu-id="8f205-103">The SQL Server destination connects to a local [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database and bulk loads data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables and views.</span></span> <span data-ttu-id="8f205-104">Sie können das SQL Server-Ziel nicht in Paketen verwenden, die auf eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank auf einem Remoteserver zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8f205-104">You cannot use the SQL Server destination in packages that access a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database on a remote server.</span></span> <span data-ttu-id="8f205-105">Die Pakete sollten stattdessen ein OLE DB-Ziel verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f205-105">Instead, the packages should use the OLE DB destination.</span></span> <span data-ttu-id="8f205-106">Weitere Informationen finden Sie unter [OLE DB Destination](ole-db-destination.md).</span><span class="sxs-lookup"><span data-stu-id="8f205-106">For more information, see [OLE DB Destination](ole-db-destination.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="8f205-107">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8f205-107">Permissions</span></span>  
 <span data-ttu-id="8f205-108">Benutzer, die Pakete ausführen, die das SQL Server-Ziel einschließen, müssen über die Berechtigung "Erstellen globaler Objekte" verfügen.</span><span class="sxs-lookup"><span data-stu-id="8f205-108">Users who execute packages that include the SQL Server destination require the "Create global objects" permission.</span></span> <span data-ttu-id="8f205-109">Sie können diese Berechtigung Benutzern erteilen, indem Sie das Tool Lokale Sicherheitsrichtlinie im Menü **Verwaltung** verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f205-109">You can grant this permission to users by using the Local Security Policy tool opened from the **Administrative Tools** menu.</span></span> <span data-ttu-id="8f205-110">Wenn Sie beim Ausführen eines Pakets, das das SQL Server-Ziel verwendet, eine Fehlermeldung erhalten, sollten Sie sicherstellen, dass das Konto, mit dem das Paket ausgeführt wird, über die Berechtigung "Erstellen globaler Objekte" verfügt.</span><span class="sxs-lookup"><span data-stu-id="8f205-110">If you receive an error message when executing a package that uses the SQL Server destination, make sure that the account running the package has the "Create global objects" permission.</span></span>  
  
## <a name="bulk-inserts"></a><span data-ttu-id="8f205-111">Masseneinfügungen</span><span class="sxs-lookup"><span data-stu-id="8f205-111">Bulk Inserts</span></span>  
 <span data-ttu-id="8f205-112">Wenn Sie versuchen, das SQL Server-Ziel zum Massenladen von Daten in eine Remote-Datenbank von SQL Server zu verwenden, wird eine Fehlermeldung der folgenden Form angezeigt: "Ein OLE DB-Datensatz ist verfügbar."</span><span class="sxs-lookup"><span data-stu-id="8f205-112">If you attempt to use the SQL Server destination to bulk load data into a remote SQL Server database, you may see an error message similar to the following: "An OLE DB record is available.</span></span> <span data-ttu-id="8f205-113">Quelle: "Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client" Hresult: 0x80040E14 Beschreibung: "Massenladen war nicht möglich, weil das SSIS-Dateizuordnungsobjekt 'Global\DTSQLIMPORT' nicht geöffnet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="8f205-113">Source: "Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client" Hresult: 0x80040E14 Description: "Could not bulk load because SSIS file mapping object 'Global\DTSQLIMPORT ' could not be opened.</span></span> <span data-ttu-id="8f205-114">Betriebssystemfehlercode 2 (Die angegebene Datei wurde nicht gefunden.).</span><span class="sxs-lookup"><span data-stu-id="8f205-114">Operating system error code 2 (The system cannot find the file specified.).</span></span> <span data-ttu-id="8f205-115">Stellen Sie sicher, dass Sie auf einen lokalen Server mit der Windows-Sicherheit zugreifen.""</span><span class="sxs-lookup"><span data-stu-id="8f205-115">Make sure you are accessing a local server via Windows security.""</span></span>  
  
 <span data-ttu-id="8f205-116">Das SQL Server-Ziel bietet das gleiche Hochgeschwindigkeitseinfügen von Daten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wie der Masseneinfügungstask. Mit dem SQL Server-Ziel kann jedoch ein Paket Transformationen auf Spaltendaten anwenden, bevor die Daten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]geladen werden.</span><span class="sxs-lookup"><span data-stu-id="8f205-116">The SQL Server destination offers the same high-speed insertion of data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that the Bulk Insert task provides; however, by using the SQL Server destination, a package can apply transformations to column data before the data is loaded into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="8f205-117">Zum Laden von Daten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]sollten Sie das Verwenden des SQL Server-Ziels anstelle des OLE DB-Ziels in Erwägung ziehen.</span><span class="sxs-lookup"><span data-stu-id="8f205-117">For loading data into [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you should consider using the SQL Server destination instead of the OLE DB destination.</span></span>  
  
### <a name="bulk-insert-options"></a><span data-ttu-id="8f205-118">Masseneinfügungsoptionen</span><span class="sxs-lookup"><span data-stu-id="8f205-118">Bulk Insert Options</span></span>  
 <span data-ttu-id="8f205-119">Falls das SQL Server-Ziel einen Datenzugriffsmodus für schnelles Laden verwendet, können Sie die folgenden Optionen für schnelles Laden angeben:</span><span class="sxs-lookup"><span data-stu-id="8f205-119">If the SQL Server destination uses a fast-load data access mode, you can specify the following fast load options:</span></span>  
  
-   <span data-ttu-id="8f205-120">Identitätswerte aus der importierten Datendatei beibehalten oder von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]zugewiesene eindeutige Werte verwenden.</span><span class="sxs-lookup"><span data-stu-id="8f205-120">Retain identity values from the imported data file, or use unique values assigned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="8f205-121">NULL-Werte während des Massenladevorgangs beibehalten.</span><span class="sxs-lookup"><span data-stu-id="8f205-121">Retain null values during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="8f205-122">Während des Massenimportvorgangs Einschränkungen der Zieltabelle oder -sicht überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8f205-122">Verify constraints on the target table or view during the bulk import operation.</span></span>  
  
-   <span data-ttu-id="8f205-123">Sperre auf Tabellenebene für die Dauer des Massenladevorgangs abrufen.</span><span class="sxs-lookup"><span data-stu-id="8f205-123">Acquire a table-level lock for the duration of the bulk load operation.</span></span>  
  
-   <span data-ttu-id="8f205-124">INSERT-Trigger, die für die Zieltabelle definiert sind, während des Massenladevorgangs ausführen.</span><span class="sxs-lookup"><span data-stu-id="8f205-124">Execute insert triggers defined on the destination table during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="8f205-125">Die Nummer der ersten Zeile in der Eingabe angeben, die während des Masseneinfügungsvorgangs geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="8f205-125">Specify the number of the first row in the input to load during the bulk insert operation.</span></span>  
  
-   <span data-ttu-id="8f205-126">Die Nummer der letzten Zeile in der Eingabe angeben, die während des Masseneinfügungsvorgangs geladen werden soll.</span><span class="sxs-lookup"><span data-stu-id="8f205-126">Specify the number of the last row in the input to load during the bulk insert operation.</span></span>  
  
-   <span data-ttu-id="8f205-127">Die maximal zulässige Anzahl von Fehlern angeben, bevor der Massenladevorgang abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="8f205-127">Specify the maximum number of errors allowed before the bulk load operation is canceled.</span></span> <span data-ttu-id="8f205-128">Jede Zeile, die nicht importiert werden kann, wird als ein Fehler gezählt.</span><span class="sxs-lookup"><span data-stu-id="8f205-128">Each row that cannot be imported is counted as one error.</span></span>  
  
-   <span data-ttu-id="8f205-129">Die Spalten in der Eingabe angeben, die sortierte Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="8f205-129">Specify the columns in the input that contain sorted data.</span></span>  
  
 <span data-ttu-id="8f205-130">Weitere Informationen zu Massenladeoptionen finden Sie unter [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="8f205-130">For more information about bulk load options, see [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
#### <a name="performance-improvements"></a><span data-ttu-id="8f205-131">Leistungsverbesserungen</span><span class="sxs-lookup"><span data-stu-id="8f205-131">Performance Improvements</span></span>  
 <span data-ttu-id="8f205-132">Sie sollten die Standardoptionen wie folgt ändern, um die Leistung einer Masseneinfügung und des Zugriffs auf Tabellendaten während des Masseneinfügungsvorgangs zu verbessern:</span><span class="sxs-lookup"><span data-stu-id="8f205-132">To improve the performance of a bulk insert and the access to table data during the bulk insert operation, you should change the default options as follows:</span></span>  
  
-   <span data-ttu-id="8f205-133">Überprüfen Sie während des Massenimportvorgangs keine Einschränkungen der Zieltabelle oder -sicht.</span><span class="sxs-lookup"><span data-stu-id="8f205-133">Do not verify constraints on the target table or view during the bulk import operation.</span></span>  
  
-   <span data-ttu-id="8f205-134">Führen Sie während des Massenladevorgangs keine INSERT-Trigger aus, die für die Zieltabelle definiert sind.</span><span class="sxs-lookup"><span data-stu-id="8f205-134">Do not execute insert triggers defined on the destination table during the bulk load operation.</span></span>  
  
-   <span data-ttu-id="8f205-135">Wenden Sie keine Sperre auf die Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="8f205-135">Do not apply a lock to the table.</span></span> <span data-ttu-id="8f205-136">Auf diese Weise ist die Tabelle während des Masseneinfügungsvorgangs weiterhin für andere Benutzer und Anwendungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8f205-136">That way, the table remains available to other users and applications during the bulk insert operation.</span></span>  
  
## <a name="configuration-of-the-sql-server-destination"></a><span data-ttu-id="8f205-137">Konfiguration des SQL Server-Ziels</span><span class="sxs-lookup"><span data-stu-id="8f205-137">Configuration of the SQL Server Destination</span></span>  
 <span data-ttu-id="8f205-138">Es gibt folgende Möglichkeiten, um das SQL Server-Ziel zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="8f205-138">You can configure the SQL Server destination in the following ways:</span></span>  
  
-   <span data-ttu-id="8f205-139">Geben Sie die Tabelle oder Sicht an, in die die Daten massengeladen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8f205-139">Specify the table or view into which to bulk load the data.</span></span>  
  
-   <span data-ttu-id="8f205-140">Passen Sie den Massenladevorgang durch Angeben von Optionen an, wie z. B., ob Einschränkungen überprüft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8f205-140">Customize the bulk load operation by specifying options such as whether to check constraints.</span></span>  
  
-   <span data-ttu-id="8f205-141">Geben Sie an, ob für alle Zeilen ein Commit in einem Batch ausgeführt werden soll, oder legen Sie die maximale Anzahl von Zeilen fest, für die ein Commit als Batch ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8f205-141">Specify whether all rows commit in one batch or set the maximum number of rows to commit as a batch.</span></span>  
  
-   <span data-ttu-id="8f205-142">Geben Sie ein Timeout für den Massenladevorgang an.</span><span class="sxs-lookup"><span data-stu-id="8f205-142">Specify a time-out for the bulk load operation.</span></span>  
  
 <span data-ttu-id="8f205-143">Dieses Ziel verwendet einen OLE DB-Verbindungs-Manager zum Herstellen einer Verbindung mit einer Datenquelle, und der Verbindungs-Manager gibt den zu verwendenden OLE DB-Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="8f205-143">This destination uses an OLE DB connection manager to connect to a data source, and the connection manager specifies the OLE DB provider to use.</span></span> <span data-ttu-id="8f205-144">Weitere Informationen finden Sie unter [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="8f205-144">For more information, see [OLE DB Connection Manager](../connection-manager/ole-db-connection-manager.md).</span></span>  
  
 <span data-ttu-id="8f205-145">Ein [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Projekt stellt auch das Datenquellenobjekt bereit, von dem Sie einen OLE DB-Verbindungs-Manager erstellen können.</span><span class="sxs-lookup"><span data-stu-id="8f205-145">An [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project also provides the data source object from which you can create an OLE DB connection manager.</span></span> <span data-ttu-id="8f205-146">Auf diese Weise sind Datenquellen und Datenquellensichten für das SQL Server-Ziel verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8f205-146">This makes data sources and data source views available to the SQL Server destination.</span></span>  
  
 <span data-ttu-id="8f205-147">Das SQL Server-Ziel besitzt eine Eingabe.</span><span class="sxs-lookup"><span data-stu-id="8f205-147">The SQL Server destination has one input.</span></span> <span data-ttu-id="8f205-148">Eine Fehlerausgabe wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8f205-148">It does not support an error output.</span></span>  
  
 <span data-ttu-id="8f205-149">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="8f205-149">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="8f205-150">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Ziel-Editor für SQL** festlegen können:</span><span class="sxs-lookup"><span data-stu-id="8f205-150">For more information about the properties that you can set in the **SQL Server Destination Editor** dialog box, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="8f205-151">Ziel-Editor für SQL &#40;Seite „Verbindungs-Manager“&#41;</span><span class="sxs-lookup"><span data-stu-id="8f205-151">SQL Destination Editor &#40;Connection Manager Page&#41;</span></span>](../sql-destination-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="8f205-152">Ziel-Editor für SQL &#40;Seite „Zuordnungen“&#41;</span><span class="sxs-lookup"><span data-stu-id="8f205-152">SQL Destination Editor &#40;Mappings Page&#41;</span></span>](../sql-destination-editor-mappings-page.md)  
  
-   [<span data-ttu-id="8f205-153">Ziel-Editor für SQL &#40;Seite „Erweitert“&#41;</span><span class="sxs-lookup"><span data-stu-id="8f205-153">SQL Destination Editor &#40;Advanced Page&#41;</span></span>](../sql-destination-editor-advanced-page.md)  
  
 <span data-ttu-id="8f205-154">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="8f205-154">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="8f205-155">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="8f205-155">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="8f205-156">Common Properties</span><span class="sxs-lookup"><span data-stu-id="8f205-156">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="8f205-157">Benutzerdefinierte Eigenschaften des SQL Server-Ziels</span><span class="sxs-lookup"><span data-stu-id="8f205-157">SQL Server Destination Custom Properties</span></span>](sql-server-destination-custom-properties.md)  
  
 <span data-ttu-id="8f205-158">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zum Festlegen von Eigenschaften anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="8f205-158">For more information about how to set properties, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="8f205-159">Massenladen von Daten mithilfe des SQL Server-Ziels</span><span class="sxs-lookup"><span data-stu-id="8f205-159">Bulk Load Data by Using the SQL Server Destination</span></span>](sql-server-destination.md)  
  
-   [<span data-ttu-id="8f205-160">Festlegen der Eigenschaften einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="8f205-160">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="8f205-161">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="8f205-161">Related Tasks</span></span>  
  
-   [<span data-ttu-id="8f205-162">Massenladen von Daten mithilfe des SQL Server-Ziels</span><span class="sxs-lookup"><span data-stu-id="8f205-162">Bulk Load Data by Using the SQL Server Destination</span></span>](sql-server-destination.md)  
  
-   [<span data-ttu-id="8f205-163">Festlegen der Eigenschaften einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="8f205-163">Set the Properties of a Data Flow Component</span></span>](set-the-properties-of-a-data-flow-component.md)  
  
## <a name="related-content"></a><span data-ttu-id="8f205-164">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="8f205-164">Related Content</span></span>  
  
-   <span data-ttu-id="8f205-165">Technischer Artikel [Möglicherweise wird bei UAC-fähigen Systemen der Fehler "Die SSIS-Masseneinfügung kann zum Einfügen von Daten nicht vorbereitet werden" angezeigt](https://go.microsoft.com/fwlink/?LinkId=199482)auf support.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8f205-165">Technical article, [You may get "Unable to prepare the SSIS bulk insert for data insertion" error on UAC enabled systems](https://go.microsoft.com/fwlink/?LinkId=199482), on support.microsoft.com.</span></span>  
  
-   <span data-ttu-id="8f205-166">Technischer Artikel [The Data Loading Performance Guide (Leistungsleitfaden für das Laden von Daten)](https://go.microsoft.com/fwlink/?LinkId=233700)auf msdn.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8f205-166">Technical article, [The Data Loading Performance Guide](https://go.microsoft.com/fwlink/?LinkId=233700), on msdn.microsoft.com.</span></span>  
  
-   <span data-ttu-id="8f205-167">Technischer Artikel [Using SQL Server Integration Services to Bulk Load Data](https://go.microsoft.com/fwlink/?LinkId=233701)(Verwenden von SQL Server Integration Services für das Massenladen von Daten) auf simple-talk.com.</span><span class="sxs-lookup"><span data-stu-id="8f205-167">Technical article, [Using SQL Server Integration Services to Bulk Load Data](https://go.microsoft.com/fwlink/?LinkId=233701), on simple-talk.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f205-168">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8f205-168">See Also</span></span>  
 [<span data-ttu-id="8f205-169">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="8f205-169">Data Flow</span></span>](data-flow.md)  
  
  
