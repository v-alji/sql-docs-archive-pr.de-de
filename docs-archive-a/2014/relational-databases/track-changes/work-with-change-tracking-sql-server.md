---
title: Verwenden der Änderungsnachverfolgung (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- change tracking [SQL Server], making changes
- change tracking [SQL Server], troubleshooting
- updating data [SQL Server]
- troubleshooting [SQL Server], change tracking
- data changes [SQL Server]
- tracking data changes [SQL Server]
- data [SQL Server], changing
- change tracking [SQL Server], data restore
- change tracking [SQL Server], ensuring consistent results
- change tracking [SQL Server], handling changes
ms.assetid: 5aec22ce-ae6f-4048-8a45-59ed05f04dc5
author: rothja
ms.author: jroth
ms.openlocfilehash: bdb8205a789894caf8c8e2d3c3f491751757bab6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621954"
---
# <a name="work-with-change-tracking-sql-server"></a><span data-ttu-id="3c13b-102">Verwenden der Änderungsnachverfolgung (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="3c13b-102">Work with Change Tracking (SQL Server)</span></span>
  <span data-ttu-id="3c13b-103">Anwendungen, die die Änderungsnachverfolgung verwenden, müssen in der Lage sein,  Überarbeitungen abzurufen, diese auf einen anderen Datenspeicher anzuwenden und die Quelldatenbank zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3c13b-103">Applications that use change tracking must be able to obtain tracked changes, apply these changes to another data store, and update the source database.</span></span> <span data-ttu-id="3c13b-104">In diesem Thema wird beschrieben, wie diese Tasks ausgeführt werden. Zudem wird beschrieben, welche Rolle die Änderungsnachverfolgung spielt, wenn ein Failover auftritt und eine Datenbank von einer Sicherung wiederhergestellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="3c13b-104">This topic describes how to perform these tasks, and also the role change tracking plays when a failover occurs and a database must be restored from a backup.</span></span>  
  
##  <a name="obtain-changes-by-using-change-tracking-functions"></a><a name="Obtain"></a> <span data-ttu-id="3c13b-105">Abrufen von Änderungen mithilfe der Änderungsnachverfolgungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="3c13b-105">Obtain Changes by Using Change Tracking Functions</span></span>  
 <span data-ttu-id="3c13b-106">Beschreibt, wie mithilfe der Änderungsnachverfolgungsfunktionen Änderungen und Informationen zu den in einer Datenbank vorgenommenen Änderungen abgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="3c13b-106">Describes how to use the change tracking functions to obtain changes and information about the changes that were made to a database.</span></span>  
  
### <a name="about-the-change-tracking-functions"></a><span data-ttu-id="3c13b-107">Informationen zu Änderungsnachverfolgungsfunktionen</span><span class="sxs-lookup"><span data-stu-id="3c13b-107">About the Change Tracking Functions</span></span>  
 <span data-ttu-id="3c13b-108">Anwendungen können mit den folgenden Funktionen die in einer Datenbank vorgenommenen Änderungen sowie die Informationen zu diesen Änderungen abrufen:</span><span class="sxs-lookup"><span data-stu-id="3c13b-108">Applications can use the following functions to obtain the changes that are made in a database and information about the changes:</span></span>  
  
 <span data-ttu-id="3c13b-109">CHANGETABLE(CHANGES ...)-Funktion</span><span class="sxs-lookup"><span data-stu-id="3c13b-109">CHANGETABLE(CHANGES ...) function</span></span>  
 <span data-ttu-id="3c13b-110">Diese Rowsetfunktion wird verwendet, um Änderungsinformationen abzufragen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-110">This rowset function is used to query for change information.</span></span> <span data-ttu-id="3c13b-111">Die Funktion fragt die in den internen Änderungsnachverfolgungstabellen gespeicherten Daten ab.</span><span class="sxs-lookup"><span data-stu-id="3c13b-111">The function queries the data stored in the internal change tracking tables.</span></span> <span data-ttu-id="3c13b-112">Die Funktion gibt ein Resultset zurück, das die Primärschlüssel der Zeilen enthält, die sich geändert haben. Außerdem werden weitere Informationen zurückgegeben, z. B. der Vorgang, die aktualisierten Spalten und die Version der Zeile.</span><span class="sxs-lookup"><span data-stu-id="3c13b-112">The function returns a results set that contains the primary keys of rows that have changed together with other change information such as the operation, columns updated and version for the row.</span></span>  
  
 <span data-ttu-id="3c13b-113">CHANGETABLE(CHANGES ...) verwendet die letzte Synchronisierungsversion als Argument.</span><span class="sxs-lookup"><span data-stu-id="3c13b-113">CHANGETABLE(CHANGES ...) takes a last synchronization version as an argument.</span></span> <span data-ttu-id="3c13b-114">Die letzte Synchronisierungsversion wird mit der `@last_synchronization_version` -Variablen abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-114">The last sychronization version is obtained using the `@last_synchronization_version` variable.</span></span> <span data-ttu-id="3c13b-115">Die Semantik der letzten Synchronisierungsversion lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="3c13b-115">The semantics of the last synchronization version are as follows:</span></span>  
  
-   <span data-ttu-id="3c13b-116">Der aufrufende Client hat alle Änderungen bis zur letzten Synchronisierungsversion (einschließlich) abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-116">The calling client has obtained changes and knows about all changes up to and including the last synchronization version.</span></span>  
  
-   <span data-ttu-id="3c13b-117">CHANGETABLE(CHANGES ...) gibt also alle Änderungen zurück, die nach der letzten Synchronisierungsversion vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-117">CHANGETABLE(CHANGES ...) will therefore return all changes that have occurred after the last synchronization version.</span></span>  
  
     <span data-ttu-id="3c13b-118">Die folgende Abbildung zeigt, wie CHANGETABLE(CHANGES ...) verwendet wird, um Änderungen abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-118">The following illustration shows how CHANGETABLE(CHANGES ...) is used to obtain changes.</span></span>  
  
     <span data-ttu-id="3c13b-119">![Beispiel einer Ausgabe einer Änderungsnachverfolgungs-Abfrage](../../database-engine/media/queryoutput.gif "Beispiel einer Ausgabe einer Änderungsnachverfolgungs-Abfrage")</span><span class="sxs-lookup"><span data-stu-id="3c13b-119">![Example of change tracking query output](../../database-engine/media/queryoutput.gif "Example of change tracking query output")</span></span>  
  
 <span data-ttu-id="3c13b-120">CHANGE_TRACKING_CURRENT_VERSION()-Funktion</span><span class="sxs-lookup"><span data-stu-id="3c13b-120">CHANGE_TRACKING_CURRENT_VERSION() function</span></span>  
 <span data-ttu-id="3c13b-121">Diese Funktion wird zum Abrufen der aktuellen Version verwendet. Diese wird das nächste Mal verwendet, wenn Änderungen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-121">Is used to obtain the current version that will be used the next time when querying changes.</span></span> <span data-ttu-id="3c13b-122">Diese Version stellt die Version der letzten Transaktion dar, für die ein Commit ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="3c13b-122">This version represents the version of the last committed transaction.</span></span>  
  
 <span data-ttu-id="3c13b-123">CHANGE_TRACKING_MIN_VALID_VERSION()-Funktion</span><span class="sxs-lookup"><span data-stu-id="3c13b-123">CHANGE_TRACKING_MIN_VALID_VERSION()function</span></span>  
 <span data-ttu-id="3c13b-124">Diese Funktion wird verwendet, um die minimal gültige Version abzurufen, über die ein Client verfügen muss, damit CHANGETABLE() gültige Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="3c13b-124">Is used to obtain the minimum valid version that a client can have and still obtain valid results from CHANGETABLE().</span></span> <span data-ttu-id="3c13b-125">Der Client muss die Version der letzten Synchronisierung mit dem Wert abgleichen, der von dieser Funktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3c13b-125">The client should check the last synchronization version against the value thatis returned by this function.</span></span> <span data-ttu-id="3c13b-126">Wenn die Version der letzten Synchronisierung niedriger ist als die von dieser Funktion zurückgegebene Version, kann der Client keine gültigen Ergebnisse von CHANGETABLE() abrufen und muss neu initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-126">If the last synchronization version is less than the version returned by this function, the client will be unable to obtain valid results from CHANGETABLE() and will have to reinitialize.</span></span>  
  
### <a name="obtaining-initial-data"></a><span data-ttu-id="3c13b-127">Abrufen der Anfangsdaten</span><span class="sxs-lookup"><span data-stu-id="3c13b-127">Obtaining Initial Data</span></span>  
 <span data-ttu-id="3c13b-128">Damit eine Anwendung Änderungen abrufen kann, muss sie zunächst die Anfangsdaten und die Synchronisierungsversion abfragen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-128">Before an application can obtain changes for the first time, the application must send a query to obtain the initial data and the synchronization version.</span></span> <span data-ttu-id="3c13b-129">Die Anwendung muss die entsprechenden Daten direkt aus der Tabelle abrufen und dann CHANGE_TRACKING_CURRENT_VERSION() zum Abrufen der Anfangsversion verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-129">The application must obtain the appropriate data directly from the table, and then use CHANGE_TRACKING_CURRENT_VERSION() to obtain the initial version.</span></span> <span data-ttu-id="3c13b-130">Diese Version wird beim ersten Abrufen von Änderungen an CHANGETABLE(CHANGES ...) übergeben.</span><span class="sxs-lookup"><span data-stu-id="3c13b-130">This version will be passed to CHANGETABLE(CHANGES ...) the first time that changes are obtained.</span></span>  
  
 <span data-ttu-id="3c13b-131">Das folgende Beispiel zeigt, wie die Anfangsversion der Synchronisierung und das Anfangsdataset abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-131">The following example shows how to obtain the initial synchronization version and the initial data set.</span></span>  
  
```sql  
    -- Obtain the current synchronization version. This will be used next time that changes are obtained.  
    SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION();  
  
    -- Obtain initial data set.  
    SELECT  
        P.ProductID, P.Name, P.ListPrice  
    FROM  
        SalesLT.Product AS P  
```  
  
### <a name="using-the-change-tracking-functions-to-obtain-changes"></a><span data-ttu-id="3c13b-132">Verwenden der Änderungsnachverfolgungsfunktionen zum Abrufen von Änderungen</span><span class="sxs-lookup"><span data-stu-id="3c13b-132">Using the Change Tracking Functions to Obtain Changes</span></span>  
 <span data-ttu-id="3c13b-133">Verwenden Sie die Funktion CHANGETABLE(CHANGES ...), um die geänderten Zeilen einer Tabelle und die zugehörigen Änderungsinformationen abzurufen. Beispielsweise werden mit der folgenden Abfrage die Änderungen für die `SalesLT.Product` -Tabelle abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-133">To obtain the changed rows for a table and information about the changes, use CHANGETABLE(CHANGES...). For example, the following query obtains changes for the `SalesLT.Product` table.</span></span>  
  
```sql  
SELECT  
    CT.ProductID, CT.SYS_CHANGE_OPERATION,  
    CT.SYS_CHANGE_COLUMNS, CT.SYS_CHANGE_CONTEXT  
FROM  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
  
```  
  
 <span data-ttu-id="3c13b-134">In der Regel möchte ein Client nicht nur die Primärschlüssel, sondern die neuesten Daten für eine Zeile abrufen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-134">Usually, a client will want to obtain the latest data for a row instead of only the primary keys for the row.</span></span> <span data-ttu-id="3c13b-135">In diesem Fall führt eine Anwendung die Ergebnisse der CHANGETABLE(CHANGES ...)-Funktion mit den Daten in der Benutzertabelle zusammen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-135">Therefore, an application would join the results from CHANGETABLE(CHANGES ...) with the data in the user table.</span></span> <span data-ttu-id="3c13b-136">Beispiel: Bei der folgenden Abfrage wird die Funktion mit der `SalesLT.Product` -Tabelle verknüpft, um die Werte der `Name` -Spalte und der `ListPrice` -Spalte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-136">For example, the following query joins with the `SalesLT.Product` table to obtain the values for the `Name` and `ListPrice` columns.</span></span> <span data-ttu-id="3c13b-137">Beachten Sie, dass `OUTER JOIN`verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3c13b-137">Note the use of `OUTER JOIN`.</span></span> <span data-ttu-id="3c13b-138">Dies ist erforderlich, um sicherzustellen, dass die Änderungsinformationen für die Zeilen zurückgegeben werden, die aus der Benutzertabelle gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-138">This is required to make sure that the change information is returned for those rows that have been deleted from the user table.</span></span>  
  
```sql  
SELECT  
    CT.ProductID, P.Name, P.ListPrice,  
    CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
    CT.SYS_CHANGE_CONTEXT  
FROM  
    SalesLT.Product AS P  
RIGHT OUTER JOIN  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
    P.ProductID = CT.ProductID  
```  
  
 <span data-ttu-id="3c13b-139">Verwenden Sie die CHANGE_TRACKING_CURRENT_VERSION()-Funktion wie im folgenden Beispiel gezeigt, um die in der nächsten Änderungsenumeration zu verwendende Version abzurufen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-139">To obtain the version for use in the next change enumeration, use CHANGE_TRACKING_CURRENT_VERSION(), as shown in the following example.</span></span>  
  
```sql  
SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION()  
```  
  
 <span data-ttu-id="3c13b-140">Beim Abrufen von Änderungen muss eine Anwendung sowohl CHANGETABLE(CHANGES ...) als auch CHANGE_TRACKING_CURRENT_VERSION() verwenden, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3c13b-140">When an application obtains changes, it must use both CHANGETABLE(CHANGES...) and CHANGE_TRACKING_CURRENT_VERSION(), as shown in the following example.</span></span>  
  
```sql  
-- Obtain the current synchronization version. This will be used the next time CHANGETABLE(CHANGES...) is called.  
SET @synchronization_version = CHANGE_TRACKING_CURRENT_VERSION();  
  
-- Obtain incremental changes by using the synchronization version obtained the last time the data was synchronized.  
SELECT  
    CT.ProductID, P.Name, P.ListPrice,  
    CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
    CT.SYS_CHANGE_CONTEXT  
FROM  
    SalesLT.Product AS P  
RIGHT OUTER JOIN  
    CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
    P.ProductID = CT.ProductID  
```  
  
### <a name="version-numbers"></a><span data-ttu-id="3c13b-141">Versionsnummern</span><span class="sxs-lookup"><span data-stu-id="3c13b-141">Version Numbers</span></span>  
 <span data-ttu-id="3c13b-142">Eine Datenbank mit aktivierter Änderungsnachverfolgung verfügt über einen Versionszähler, der hochgezählt wird, wenn Änderungen an den nachverfolgten Tabellen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-142">A database that has change tracking enabled has a version counter that increases as changes are made to change tracked tables.</span></span> <span data-ttu-id="3c13b-143">Jede geänderte Zeile verfügt über eine ihr zugeordnete Versionsnummer.</span><span class="sxs-lookup"><span data-stu-id="3c13b-143">Each changed row has a version number that is associated with it.</span></span> <span data-ttu-id="3c13b-144">Wenn eine Anforderung zur Abfrage von Änderungen an eine Anwendung gesendet wird, wird eine Funktion aufgerufen, die eine Versionsnummer angibt.</span><span class="sxs-lookup"><span data-stu-id="3c13b-144">When a request is sent to an application to query for changes, a function is called that supplies a version number.</span></span> <span data-ttu-id="3c13b-145">Die Funktion gibt Informationen über alle Änderungen zurück, die ab dieser Version vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-145">The function returns information about all the changes that have been made since that version.</span></span> <span data-ttu-id="3c13b-146">In gewisser Hinsicht entspricht die Änderungsnachverfolgungsversion dem Konzept des `rowversion`-Datentyps.</span><span class="sxs-lookup"><span data-stu-id="3c13b-146">In some ways, change tracking version is similar in concept to the `rowversion` data type.</span></span>  
  
### <a name="validating-the-last-synchronized-version"></a><span data-ttu-id="3c13b-147">Überprüfen der letzten Synchronisierungsversion</span><span class="sxs-lookup"><span data-stu-id="3c13b-147">Validating the Last Synchronized Version</span></span>  
 <span data-ttu-id="3c13b-148">Informationen über Änderungen werden für einen beschränkten Zeitraum beibehalten.</span><span class="sxs-lookup"><span data-stu-id="3c13b-148">Information about changes is maintained for a limited time.</span></span> <span data-ttu-id="3c13b-149">Dieser Zeitraum wird mit dem CHANGE_RETENTION-Parameter festgelegt, der als Teil von ALTER DATABASE angegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="3c13b-149">The length of time is controlled by the CHANGE_RETENTION parameter that can be specified as part of the ALTER DATABASE.</span></span>  
  
 <span data-ttu-id="3c13b-150">Beachten Sie, dass der mit CHANGE_RETENTION angegebene Zeitraum festlegt, wie häufig alle Anwendungen Änderungen von der Datenbank anfordern müssen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-150">Be aware that the time specified for CHANGE_RETENTION determines how frequently all applications must request changes from the database.</span></span> <span data-ttu-id="3c13b-151">Wenn der Wert für *last_synchronization_version* einer Anwendung älter ist als die minimal gültige Synchronisierungsversion für eine Tabelle, kann diese Anwendung keine gültige Änderungsenumeration ausführen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-151">If an application has a value for *last_synchronization_version* that is older than the minimum valid synchronization version for a table, that application cannot perform valid change enumeration.</span></span> <span data-ttu-id="3c13b-152">Das liegt daran, dass einige Änderungsinformationen möglicherweise bereinigt wurden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-152">This is because some change information might have been cleaned up.</span></span> <span data-ttu-id="3c13b-153">Vor dem Abrufen von Änderungen mit CHANGETABLE(CHANGES ...) muss eine Anwendung also den Wert von *last_synchronization_version*, der an CHANGETABLE(CHANGES ...) übergeben werden soll, überprüfen. Wenn der Wert von *last_synchronization_version* nicht gültig ist, müssen alle Daten von der Anwendung neu initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-153">Before an application obtains changes by using CHANGETABLE(CHANGES ...), the application must validate the value for *last_synchronization_version* that it plans to pass to CHANGETABLE(CHANGES ...). If the value of *last_synchronization_version* is not valid, that application must reinitialize all the data.</span></span>  
  
 <span data-ttu-id="3c13b-154">Im folgenden Beispiel wird gezeigt, wie die Gültigkeit des `last_synchronization_version` -Werts für die einzelnen Tabellen überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="3c13b-154">The following example shows how to verify the validity of the value of `last_synchronization_version` for each table.</span></span>  
  
```sql  
-- Check individual table.  
IF (@last_synchronization_version < CHANGE_TRACKING_MIN_VALID_VERSION(  
                                   OBJECT_ID('SalesLT.Product')))  
BEGIN  
  -- Handle invalid version and do not enumerate changes.  
  -- Client must be reinitialized.  
END  
```  
  
 <span data-ttu-id="3c13b-155">Wie im folgenden Beispiel gezeigt, kann die Gültigkeit des `last_synchronization_version` -Werts für alle Tabellen in der Datenbank überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-155">As the following example shows, the validity of the value of `last_synchronization_version` can be checked against all tables in the database.</span></span>  
  
```sql  
-- Check all tables with change tracking enabled  
IF EXISTS (  
  SELECT COUNT(*) FROM sys.change_tracking_tables  
  WHERE min_valid_version > @last_synchronization_version )  
BEGIN  
  -- Handle invalid version & do not enumerate changes  
  -- Client must be reinitialized  
END  
```  
  
### <a name="using-column-tracking"></a><span data-ttu-id="3c13b-156">Verwenden der Spaltennachverfolgung</span><span class="sxs-lookup"><span data-stu-id="3c13b-156">Using Column Tracking</span></span>  
 <span data-ttu-id="3c13b-157">Die Spaltennachverfolgung ermöglicht Anwendungen, Daten statt für die gesamte Zeile nur für die Spalten abzurufen, die geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-157">Column tracking enables applications to obtain the data for only the columns that have changed instead of the whole row.</span></span> <span data-ttu-id="3c13b-158">Nehmen Sie z. B. an, eine Tabelle hat ein oder mehrere große Spalten, in denen selten Änderungen vorgenommen werden, sowie andere Spalten, in denen häufig Änderungen vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-158">For example, consider the scenario in which a table has one or more columns that are large, but rarely change; and also has other columns that frequently change.</span></span> <span data-ttu-id="3c13b-159">Ohne die Spaltennachverfolgung kann eine Anwendung nur die Änderung einer Zeile erkennen, sodass alle Daten, einschließlich der Daten in den großen Spalten, synchronisiert werden müssten.</span><span class="sxs-lookup"><span data-stu-id="3c13b-159">Without column tracking, an application can only determine that a row has changed and would have to synchronize all the data that includes the large column data.</span></span> <span data-ttu-id="3c13b-160">Mit der Spaltennachverfolgung kann eine Anwendung ermitteln, in welcher Spalte Daten geändert wurden, und nur die geänderten Daten synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="3c13b-160">However, by using column tracking, an application can determine whether the large column data changed and only synchronize the data if it has changed.</span></span>  
  
 <span data-ttu-id="3c13b-161">Die Spaltennachverfolgungsinformationen sind in der SYS_CHANGE_COLUMNS-Spalte enthalten, die von der CHANGETABLE(CHANGES ...)-Funktion zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3c13b-161">Column tracking information appears in the SYS_CHANGE_COLUMNS column that is returned by the CHANGETABLE(CHANGES ...) function.</span></span>  
  
 <span data-ttu-id="3c13b-162">Die Spaltennachverfolgung kann so verwendet werden, dass NULL für Spalten ohne Änderungen zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3c13b-162">Column tracking can be used so that NULL is returned for a column that has not changed.</span></span> <span data-ttu-id="3c13b-163">Wenn die Spalte in NULL geändert werden kann, muss eine separate Spalte zurückgegeben werden, um anzugeben, ob die Spalte geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="3c13b-163">If the column can be changed to NULL, a separate column must be returned to indicate whether the column changed.</span></span>  
  
 <span data-ttu-id="3c13b-164">Im folgenden Beispiel wird für die Spalte `CT_ThumbnailPhoto` der Wert `NULL` zurückgegeben, wenn diese nicht geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="3c13b-164">In the following example, the `CT_ThumbnailPhoto` column will be `NULL` if that column did not change.</span></span> <span data-ttu-id="3c13b-165">Der Wert dieser Spalte kann jedoch auch `NULL` lauten, da sie in `NULL` geändert werden kann. In diesem Fall kann die Anwendung mit der Spalte `CT_ThumbNailPhoto_Changed` angeben, ob die Spalte geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="3c13b-165">This column could also be `NULL` because it was changed to `NULL` - the application can use the `CT_ThumbNailPhoto_Changed` column to determine whether the column changed.</span></span>  
  
```sql  
DECLARE @PhotoColumnId int = COLUMNPROPERTY(  
    OBJECT_ID('SalesLT.Product'),'ThumbNailPhoto', 'ColumnId')  
  
SELECT  
    CT.ProductID, P.Name, P.ListPrice, -- Always obtain values.  
    CASE  
           WHEN CHANGE_TRACKING_IS_COLUMN_IN_MASK(  
                     @PhotoColumnId, CT.SYS_CHANGE_COLUMNS) = 1  
            THEN ThumbNailPhoto  
            ELSE NULL  
      END AS CT_ThumbNailPhoto,  
      CHANGE_TRACKING_IS_COLUMN_IN_MASK(  
                     @PhotoColumnId, CT.SYS_CHANGE_COLUMNS) AS  
                                   CT_ThumbNailPhoto_Changed  
     CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS,  
     CT.SYS_CHANGE_CONTEXT  
FROM  
     SalesLT.Product AS P  
INNER JOIN  
     CHANGETABLE(CHANGES SalesLT.Product, @last_synchronization_version) AS CT  
ON  
     P.ProductID = CT.ProductID AND  
     CT.SYS_CHANGE_OPERATION = 'U'  
```  
  
### <a name="obtaining-consistent-and-correct-results"></a><span data-ttu-id="3c13b-166">Abrufen von konsistenten und richtigen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="3c13b-166">Obtaining Consistent and Correct Results</span></span>  
 <span data-ttu-id="3c13b-167">Zum Abrufen der Änderungsdaten für eine Tabelle sind mehrere Schritte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3c13b-167">Obtaining the changed data for a table requires multiple steps.</span></span> <span data-ttu-id="3c13b-168">Beachten Sie, dass möglicherweise inkonsistente oder falsche Ergebnisse zurückgegeben werden, wenn Sie bestimmte Vorgänge nicht berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-168">Be aware that inconsistent or incorrect results could be returned if certain issues are not considered and handled.</span></span>  
  
 <span data-ttu-id="3c13b-169">Beispiel: Zum Abrufen der Änderungen in einer Tabelle mit dem Namen Sales und einer Tabelle mit dem Namen SalesOrders führt eine Anwendung die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="3c13b-169">For example, to obtain the changes that were made to a Sales table and SalesOrders table, an application would perform the following steps:</span></span>  
  
1.  <span data-ttu-id="3c13b-170">Überprüfung der letzten Synchronisierungsversion mit CHANGE_TRACKING_MIN_VALID_VERSION()</span><span class="sxs-lookup"><span data-stu-id="3c13b-170">Validate the last synchronized version by using CHANGE_TRACKING_MIN_VALID_VERSION().</span></span>  
  
2.  <span data-ttu-id="3c13b-171">Abrufen der Version, die beim nächsten Abrufen von Änderungen verwendet werden kann, mit CHANGE_TRACKING_CURRENT_VERSION()</span><span class="sxs-lookup"><span data-stu-id="3c13b-171">Obtain the version that can be used to obtain change the next time by using CHANGE_TRACKING_CURRENT_VERSION().</span></span>  
  
3.  <span data-ttu-id="3c13b-172">Rufen Sie die Änderungen für die Tabelle Sales mit CHANGETABLE(CHANGES ...) ab.</span><span class="sxs-lookup"><span data-stu-id="3c13b-172">Obtain the changes for the Sales table by using CHANGETABLE(CHANGES ...).</span></span>  
  
4.  <span data-ttu-id="3c13b-173">Rufen Sie die Änderungen für die Tabelle SalesOrders mit CHANGETABLE(CHANGES ...) ab.</span><span class="sxs-lookup"><span data-stu-id="3c13b-173">Obtain the changes for the SalesOrders table by using CHANGETABLE(CHANGES ...).</span></span>  
  
 <span data-ttu-id="3c13b-174">In der Datenbank werden zwei Prozesse ausgeführt, die sich auf die von den oben genannten Schritten zurückgegebenen Ergebnisse auswirken können:</span><span class="sxs-lookup"><span data-stu-id="3c13b-174">Two processes are occurring in the database that can affect the results that are returned by the previous steps:</span></span>  
  
-   <span data-ttu-id="3c13b-175">Der im Hintergrund ausgeführte Cleanupprozess entfernt Änderungsnachverfolgungsinformationen, die älter sind als die angegebene Beibehaltungsdauer.</span><span class="sxs-lookup"><span data-stu-id="3c13b-175">The cleanup process runs in the background and removes change tracking information that is older than the specified retention period.</span></span>  
  
     <span data-ttu-id="3c13b-176">Beim Cleanupprozess handelt es sich um einen eigenen, im Hintergrund ausgeführten Prozess, der die Beibehaltungsdauer verwendet, die bei der Konfiguration der Änderungsnachverfolgung für die Datenbank angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3c13b-176">The cleanup process is a separate background process that uses the retention period that is specified when you configure change tracking for the database.</span></span> <span data-ttu-id="3c13b-177">Das Problem liegt darin, dass der Cleanupprozess genau in dem Zeitraum nach der Überprüfung der letzten Synchronisierungsversion und vor dem Aufruf von CHANGETABLE(CHANGES ...) ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="3c13b-177">The issue is that the cleanup process can occur in the time between when the last synchronization version was validated and when the call to CHANGETABLE(CHANGES...) is made.</span></span> <span data-ttu-id="3c13b-178">In diesem Fall kann es vorkommen, dass die gerade für gültig befundene letzte Synchronisierungsversion beim Abruf der Änderungen nicht mehr gültig ist.</span><span class="sxs-lookup"><span data-stu-id="3c13b-178">A last synchronization version that was just valid might no longer be valid by the time the changes are obtained.</span></span> <span data-ttu-id="3c13b-179">Aus diesem Grund kann es hier zu falschen Ergebnissen kommen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-179">Therefore, incorrect results might be returned.</span></span>  
  
-   <span data-ttu-id="3c13b-180">In den Tabellen Sales und SalesOrders werden fortlaufende DML-Vorgänge ausgeführt, wie z. B. folgende:</span><span class="sxs-lookup"><span data-stu-id="3c13b-180">Ongoing DML operations are occurring in the Sales and SalesOrders tables, such as the following operations:</span></span>  
  
    -   <span data-ttu-id="3c13b-181">Mit der CHANGE_TRACKING_CURRENT_VERSION()-Funktion können Änderungen an den Tabellen vorgenommen werden, nachdem die Version für die nächste Aufzählung von Änderungen abgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="3c13b-181">Changes can be made to the tables after the version for next time has been obtained by using CHANGE_TRACKING_CURRENT_VERSION().</span></span> <span data-ttu-id="3c13b-182">In diesem Fall werden möglicherweise mehr Änderungen zurückgegeben als erwartet.</span><span class="sxs-lookup"><span data-stu-id="3c13b-182">Therefore, more changes can be returned than expected.</span></span>  
  
    -   <span data-ttu-id="3c13b-183">Ein Commit für eine Transaktion kann in dem Zeitraum zwischen dem Aufruf der Funktion zum Abrufen der Änderungen in der Tabelle Sales und dem Aufruf der Funktion zum Abrufen der Änderungen in der Tabelle SalesOrders ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-183">A transaction could commit in the time between the call to obtain changes from the Sales table and the call to obtain changes from the SalesOrders table.</span></span> <span data-ttu-id="3c13b-184">In diesem Fall enthalten die Ergebnisse für die Tabelle SalesOrders möglicherweise einen Fremdschlüsselwert, der in der Tabelle Sales nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="3c13b-184">Therefore, the results for the SalesOrder table could have foreign key value that does not exist in the Sales table.</span></span>  
  
 <span data-ttu-id="3c13b-185">Zur Handhabung dieser aufgelisteten Fälle wird die Verwendung der Momentaufnahmeisolation empfohlen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-185">To overcome the previously listed challenges, we recommend that you use snapshot isolation.</span></span> <span data-ttu-id="3c13b-186">Hierdurch können Sie die Konsistenz der Änderungsinformationen sicherstellen und Racebedingungen im Zusammenhang mit dem im Hintergrund ausgeführten Cleanupprozess vermeiden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-186">This will help to ensure consistency of change information and avoid race conditions that are related to the background cleanup task.</span></span> <span data-ttu-id="3c13b-187">Ohne die Verwendung von Momentaufnahmetransaktionen ist die Entwicklung einer Anwendung, die die Änderungsnachverfolgung verwendet, mit erheblich mehr Aufwand verbunden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-187">If you do not use snapshot transactions, developing an application that uses change tracking could require significantly more effort.</span></span>  
  
#### <a name="using-snapshot-isolation"></a><span data-ttu-id="3c13b-188">Verwenden der Momentaufnahmeisolation</span><span class="sxs-lookup"><span data-stu-id="3c13b-188">Using Snapshot Isolation</span></span>  
 <span data-ttu-id="3c13b-189">Die Änderungsnachverfolgung wurde für die Verwendung mit der Momentaufnahmeisolation optimiert.</span><span class="sxs-lookup"><span data-stu-id="3c13b-189">Change tracking has been designed to work well with snapshot isolation.</span></span> <span data-ttu-id="3c13b-190">Die Momentaufnahmeisolation muss für die Datenbank aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-190">Snapshot isolation must be enabled for the database.</span></span> <span data-ttu-id="3c13b-191">Alle zum Abrufen von Änderungen erforderlichen Schritte müssen in eine Momentaufnahmetransaktion eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-191">All the steps that are required to obtain changes must be included inside a snapshot transaction.</span></span> <span data-ttu-id="3c13b-192">Hierdurch können Sie sicherstellen, dass die während des Abrufens von Änderungen an den Daten vorgenommenen Änderungen für die Abfragen in der Momentaufnahmetransaktion nicht sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="3c13b-192">This will ensure that all changes that are made to data while obtaining changes will not be visible to the queries inside the snapshot transaction.</span></span>  
  
 <span data-ttu-id="3c13b-193">Führen Sie die folgenden Schritte aus, um Daten in einer Momentaufnahmetransaktion abzurufen:</span><span class="sxs-lookup"><span data-stu-id="3c13b-193">To obtain data inside a snapshot transaction, perform the following steps:</span></span>  
  
1.  <span data-ttu-id="3c13b-194">Legen Sie die Transaktionsisolationsstufe auf MOMENTAUFNAHME fest, und starten Sie die Transaktion.</span><span class="sxs-lookup"><span data-stu-id="3c13b-194">Set the transaction isolation level to snapshot and start a transaction.</span></span>  
  
2.  <span data-ttu-id="3c13b-195">Überprüfen Sie die letzte Synchronisierungsversion mit CHANGE_TRACKING_MIN_VALID_VERSION().</span><span class="sxs-lookup"><span data-stu-id="3c13b-195">Validate the last synchronization version by using CHANGE_TRACKING_MIN_VALID_VERSION().</span></span>  
  
3.  <span data-ttu-id="3c13b-196">Rufen Sie die Version, die bei der nächsten Aufzählung von Änderungen verwendet wird, mit CHANGE_TRACKING_CURRENT_VERSION() ab.</span><span class="sxs-lookup"><span data-stu-id="3c13b-196">Obtain the version to be used the next time by using CHANGE_TRACKING_CURRENT_VERSION().</span></span>  
  
4.  <span data-ttu-id="3c13b-197">Rufen Sie die Änderungen für die Tabelle Sales mit CHANGETABLE(CHANGES ...) ab.</span><span class="sxs-lookup"><span data-stu-id="3c13b-197">Obtain the changes for the Sales table by using CHANGETABLE(CHANGES ...)</span></span>  
  
5.  <span data-ttu-id="3c13b-198">Rufen Sie die Änderungen für die Tabelle SalesOrders mit CHANGETABLE(CHANGES ...) ab.</span><span class="sxs-lookup"><span data-stu-id="3c13b-198">Obtain the changes for the Salesorders table by using CHANGETABLE(CHANGES ...)</span></span>  
  
6.  <span data-ttu-id="3c13b-199">Führen Sie einen Commit für die Transaktion aus.</span><span class="sxs-lookup"><span data-stu-id="3c13b-199">Commit the transaction.</span></span>  
  
 <span data-ttu-id="3c13b-200">Folgendes ist zu beachten, wenn alle Schritte zum Abrufen von Änderungen innerhalb einer Momentaufnahmetransaktion erfolgen:</span><span class="sxs-lookup"><span data-stu-id="3c13b-200">Some points to remember as all steps to obtain changes are inside a snapshot transaction:</span></span>  
  
-   <span data-ttu-id="3c13b-201">Wenn nach der Überprüfung der letzten Synchronisierungsversion eine Bereinigung durchgeführt wird, sind die Ergebnisse der CHANGETABLE(CHANGES ...)-Funktion dennoch gültig, da die vom Cleanupprozess durchgeführten Löschvorgänge innerhalb der Transaktion nicht sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="3c13b-201">If cleanup occurs after the last synchronization version is validated, the results from CHANGETABLE(CHANGES ...) will still be valid as the delete operations performed by cleanup will not be visible inside the transaction.</span></span>  
  
-   <span data-ttu-id="3c13b-202">Alle Änderungen, die nach dem Abrufen der nächsten Synchronisierungsversion an den Tabellen Sales und SalesOrders vorgenommen werden, sind nicht sichtbar, und der Aufruf der CHANGETABLE(CHANGES ...)-Funktion gibt keine Änderungen mit Versionen zurück, die neuer sind als die von der CHANGE_TRACKING_CURRENT_VERSION()-Funktion zurückgegebene Version.</span><span class="sxs-lookup"><span data-stu-id="3c13b-202">Any changes that are made to the Sales table or the SalesOrders table after the next synchronization version is obtained will not be visible, and the calls to CHANGETABLE(CHANGES ...) will never return changes with a version later than that returned by CHANGE_TRACKING_CURRENT_VERSION().</span></span> <span data-ttu-id="3c13b-203">Die Konsistenz zwischen den Tabellen Sales und SalesOrders wird ebenfalls sichergestellt, da die Transaktionen, für die ein Commit zwischen den Aufrufen der CHANGETABLE(CHANGES ...)-Funktion ausgeführt wird, nicht sichtbar sind.</span><span class="sxs-lookup"><span data-stu-id="3c13b-203">Consistency between the Sales table and the SalesOrders table will also be maintained, because the transactions that were committed in the time between calls to CHANGETABLE(CHANGES ...) will not be visible.</span></span>  
  
 <span data-ttu-id="3c13b-204">Das folgende Beispiel zeigt, wie die Momentaufnahmeisolation für eine Datenbank aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="3c13b-204">The following example shows how snapshot isolation is enabled for a database.</span></span>  
  
```sql  
-- The database must be configured to enable snapshot isolation.  
ALTER DATABASE AdventureWorksLT  
    SET ALLOW_SNAPSHOT_ISOLATION ON;  
```  
  
 <span data-ttu-id="3c13b-205">Eine Momentaufnahmetransaktion wird wie folgt verwendet:</span><span class="sxs-lookup"><span data-stu-id="3c13b-205">A snapshot transaction is used as follows:</span></span>  
  
```sql  
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;  
BEGIN TRAN  
  -- Verify that version of the previous synchronization is valid.  
  -- Obtain the version to use next time.  
  -- Obtain changes.  
COMMIT TRAN  
```  
  
 <span data-ttu-id="3c13b-206">Weitere Informationen über Momentaufnahmentransaktion finden Sie unter [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="3c13b-206">For more information about snapshot transactions, see [SET TRANSACTION ISOLATION LEVEL &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-transaction-isolation-level-transact-sql).</span></span>  
  
#### <a name="alternatives-to-using-snapshot-isolation"></a><span data-ttu-id="3c13b-207">Alternativen zur Verwendung der Momentaufnahmeisolation</span><span class="sxs-lookup"><span data-stu-id="3c13b-207">Alternatives to Using Snapshot Isolation</span></span>  
 <span data-ttu-id="3c13b-208">Es gibt Alternativen zur Verwendung der Momentaufnahmeisolation, die jedoch einen größeren Aufwand erfordern, um sicherzustellen, dass alle Anwendungsanforderungen erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-208">There are alternatives to using snapshot isolation, but they require more work to make sure all application requirements are met.</span></span> <span data-ttu-id="3c13b-209">Gehen Sie wie folgt vor, um sicherzustellen, dass der Wert *last_synchronization_version* gültig ist und dass vor dem Abrufen der Änderungen keine Daten durch den Cleanupprozess entfernt werden:</span><span class="sxs-lookup"><span data-stu-id="3c13b-209">To make sure the *last_synchronization_version* is valid and data is not removed by the cleanup process before changes are obtained, do the following:</span></span>  
  
1.  <span data-ttu-id="3c13b-210">Überprüfen Sie den Wert *last_synchronization_version* nach dem Aufrufen der CHANGETABLE()-Funktion.</span><span class="sxs-lookup"><span data-stu-id="3c13b-210">Check *last_synchronization_version* after the calls to CHANGETABLE().</span></span>  
  
2.  <span data-ttu-id="3c13b-211">Überprüfen Sie den Wert *last_synchronization_version* bei jeder Abfrage zum Abrufen von Änderungen mit CHANGETABLE().</span><span class="sxs-lookup"><span data-stu-id="3c13b-211">Check *last_synchronization_version* as part of each query to obtain changes by using CHANGETABLE().</span></span>  
  
 <span data-ttu-id="3c13b-212">Änderungen können nach dem Abrufen der Synchronisierungsversion für die nächste Aufzählung auftreten.</span><span class="sxs-lookup"><span data-stu-id="3c13b-212">Changes can occur after the synchronization version for the next enumeration has been obtained.</span></span> <span data-ttu-id="3c13b-213">Dieses Problem lässt sich auf zwei Arten lösen:</span><span class="sxs-lookup"><span data-stu-id="3c13b-213">There are two ways to handle this situation.</span></span> <span data-ttu-id="3c13b-214">Welche Option Sie verwenden, hängt von der Anwendung ab und wie diese die Nebeneffekte des jeweiligen Ansatzes handhabt:</span><span class="sxs-lookup"><span data-stu-id="3c13b-214">The option that is used depends on the application and how it can handle the side-effects of each approach:</span></span>  
  
-   <span data-ttu-id="3c13b-215">Ignorieren Sie Änderungen, deren Version neuer ist als die neue Synchronisierungsversion.</span><span class="sxs-lookup"><span data-stu-id="3c13b-215">Ignore changes that have a version larger than the new synchronization version.</span></span>  
  
     <span data-ttu-id="3c13b-216">Dieser Ansatz hat den Nebeneffekt, dass eine neue oder aktualisierte Zeile übersprungen wird, wenn diese vor der neuen Synchronisierungsversion erstellt oder aktualisiert wurde und danach ebenfalls aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="3c13b-216">This approach has the side effect that a new or updated row would be skipped if it was created or updated before the new synchronization version, but then updated afterward.</span></span> <span data-ttu-id="3c13b-217">Bei einer neuen Zeile kann ein Problem mit der referenziellen Integrität auftreten, wenn eine erstellte Zeile in einer anderen Tabelle auf die übersprungene Zeile verweist.</span><span class="sxs-lookup"><span data-stu-id="3c13b-217">If there is a new row, a referential integrity problem might occur if there was a row in another table that was created that referenced the skipped row.</span></span> <span data-ttu-id="3c13b-218">Eine aktualisierte Zeile wird übersprungen und erst beim nächsten Mal synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="3c13b-218">If there is an updated existing row, the row will be skipped and not synchronized until the next time.</span></span>  
  
-   <span data-ttu-id="3c13b-219">Berücksichtigen Sie alle Änderungen, auch die, deren Version neuer ist als die neue Synchronisierungsversion.</span><span class="sxs-lookup"><span data-stu-id="3c13b-219">Include all changes, even those that have a version larger than the new synchronization version.</span></span>  
  
     <span data-ttu-id="3c13b-220">Die Zeilen, deren Version neuer ist als die neue Synchronisierungsversion, werden bei der nächsten Synchronisation erneut abgerufen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-220">The rows that have a version larger than the new synchronization version will be obtained again on the next synchronization.</span></span> <span data-ttu-id="3c13b-221">Dies muss von der Anwendung entsprechend berücksichtigt werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-221">This must be expected and handled by the application.</span></span>  
  
 <span data-ttu-id="3c13b-222">Zusätzlich zu den beiden oben genannten Optionen können Sie abhängig vom Vorgang einen Ansatz entwerfen, der beide Optionen kombiniert.</span><span class="sxs-lookup"><span data-stu-id="3c13b-222">In addition to the previous two options, you can devise approach that combines both options, depending on the operation.</span></span> <span data-ttu-id="3c13b-223">Sie können beispielsweise eine Anwendung entwickeln, für die es am besten ist, dass Änderungen mit einer neueren Version als die nächste Synchronisierungsversion ignoriert werden, bei denen es sich um Erstellungs- oder Löschvorgänge handelt, Updatevorgänge jedoch nicht ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-223">For example, you might want an application for which it is best to ignore changes newer than the next synchronization version in which the row was created or deleted, but updates are not ignored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3c13b-224">Zur Auswahl des richtigen Ansatzes für die Anwendung, wenn Sie die Änderungsnachverfolgung (oder benutzerdefinierte Nachverfolgungsmechanismen) verwenden, sind umfangreiche Analysen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="3c13b-224">Choosing the approach that will work for the application when you are using change tracking (or any custom tracking mechanism), requires significant analysis.</span></span> <span data-ttu-id="3c13b-225">Aus diesem Grund ist es viel einfacher, die Momentaufnahmeisolation zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-225">Therefore, it is much simpler to use snapshot isolation.</span></span>  
  
##  <a name="how-change-tracking-handles-changes-to-a-database"></a><a name="Handles"></a><span data-ttu-id="3c13b-226">So verarbeitet Änderungsnachverfolgung Änderungen an einer Datenbank</span><span class="sxs-lookup"><span data-stu-id="3c13b-226">How Change Tracking Handles Changes to a Database</span></span>  
 <span data-ttu-id="3c13b-227">Einige Anwendungen, die die Änderungsnachverfolgung verwenden, führen die bidirektionale Synchronisierung mit einem anderen Datenspeicher aus.</span><span class="sxs-lookup"><span data-stu-id="3c13b-227">Some applications that use change tracking perform two-way synchronization with another data store.</span></span> <span data-ttu-id="3c13b-228">Das heißt, der andere Datenspeicher wird mit den in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank vorgenommenen Änderungen aktualisiert, und die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank wird mit den in dem anderen Datenspeicher vorgenommenen Änderungen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3c13b-228">That is, changes that are made in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database are updated in the other data store, and changes that are made in the other store are updated in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database.</span></span>  
  
 <span data-ttu-id="3c13b-229">Zur Aktualisierung der lokalen Datenbank mit Änderungen von einem anderen Datenspeicher muss die Anwendung die folgenden Vorgänge ausführen:</span><span class="sxs-lookup"><span data-stu-id="3c13b-229">When an application updates the local database with changes from another data store, the application must perform the following operations:</span></span>  
  
-   <span data-ttu-id="3c13b-230">Überprüfung auf Konflikte.</span><span class="sxs-lookup"><span data-stu-id="3c13b-230">Check for conflicts.</span></span>  
  
     <span data-ttu-id="3c13b-231">Zu einem Konflikt kommt es, wenn die gleichen Daten in beiden Datenspeichern gleichzeitig geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-231">A conflict occurs when the same data is changed at the same time in both data stores.</span></span> <span data-ttu-id="3c13b-232">Die Anwendung muss überprüfen können, ob solche Konflikte vorliegen, und genügend Informationen erfassen, um den Konflikt zu beheben.</span><span class="sxs-lookup"><span data-stu-id="3c13b-232">The application must be able to check for a conflict and obtain enough information to enable the conflict to be resolved.</span></span>  
  
-   <span data-ttu-id="3c13b-233">Speichern von Anwendungskontextinformationen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-233">Store application context information.</span></span>  
  
     <span data-ttu-id="3c13b-234">Die Anwendung speichert Daten mit Änderungsnachverfolgungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-234">The application stores data that has the change tracking information.</span></span> <span data-ttu-id="3c13b-235">Diese Informationen stehen beim Abrufen von Änderungen aus der lokalen Datenbank neben anderen Änderungsnachverfolgungsinformationen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3c13b-235">This information would be available together with other change tracking information when changes were obtained from the local database.</span></span> <span data-ttu-id="3c13b-236">Ein gängiges Beispiel dieser Kontextinformationen ist die ID des Datenspeichers, in dem die Änderung vorgenommen wurde.</span><span class="sxs-lookup"><span data-stu-id="3c13b-236">A common example of this contextual information is an identifier for the data store that was the source of the change.</span></span>  
  
 <span data-ttu-id="3c13b-237">Zur Ausführung der oben genannten Vorgänge kann eine Synchronisierungsanwendung die folgenden Funktionen verwenden:</span><span class="sxs-lookup"><span data-stu-id="3c13b-237">To perform the previous operations, a synchronization application can use the following functions:</span></span>  
  
-   <span data-ttu-id="3c13b-238">CHANGETABLE(VERSION...)</span><span class="sxs-lookup"><span data-stu-id="3c13b-238">CHANGETABLE(VERSION...)</span></span>  
  
     <span data-ttu-id="3c13b-239">Beim Vornehmen von Änderungen kann eine Anwendung diese Funktion zur Überprüfung auf Konflikte verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-239">When an application is making changes, it can use this function to check for conflicts.</span></span> <span data-ttu-id="3c13b-240">Die Funktion ruft die letzten Änderungsnachverfolgungsinformationen für eine angegebene Zeile in einer änderungsnachverfolgten Tabelle ab.</span><span class="sxs-lookup"><span data-stu-id="3c13b-240">The function obtains the latest change tracking information for a specified row in a change tracked table.</span></span> <span data-ttu-id="3c13b-241">Die Änderungsnachverfolgungsinformationen schließen die Version der letzten Änderung der Zeile ein.</span><span class="sxs-lookup"><span data-stu-id="3c13b-241">The change tracking information includes the version of the row that was last changed.</span></span> <span data-ttu-id="3c13b-242">Die Anwendung kann dann mithilfe dieser Informationen ermitteln, ob die Zeile seit der letzten Synchronisierung der Anwendung geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="3c13b-242">This information enables an application to determine whether the row was changed after the last time that the application was synchronized.</span></span>  
  
-   <span data-ttu-id="3c13b-243">WITH CHANGE_TRACKING_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="3c13b-243">WITH CHANGE_TRACKING_CONTEXT</span></span>  
  
     <span data-ttu-id="3c13b-244">Eine Anwendung kann diese Klausel verwenden, um Kontextdaten zu speichern.</span><span class="sxs-lookup"><span data-stu-id="3c13b-244">An application can use this clause to store context data.</span></span>  
  
### <a name="checking-for-conflicts"></a><span data-ttu-id="3c13b-245">Überprüfung auf Konflikte</span><span class="sxs-lookup"><span data-stu-id="3c13b-245">Checking for Conflicts</span></span>  
 <span data-ttu-id="3c13b-246">Bei der bidirektionalen Synchronisierung muss die Clientanwendung ermitteln, ob eine Zeile seit dem letzten Abrufen der Änderungen durch die Anwendung aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3c13b-246">In a two-way synchronization scenario, the client application must determine whether a row has not been updated since the application last obtained the changes.</span></span>  
  
 <span data-ttu-id="3c13b-247">Das folgende Beispiel zeigt, wie die Überprüfung auf Konflikte mit der CHANGETABLE(VERSION ...)-Funktion effizient und ohne separate Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3c13b-247">The following example shows how to use the CHANGETABLE(VERSION ...) function to check for conflicts in the most efficient way, without a separate query.</span></span> <span data-ttu-id="3c13b-248">Im Beispiel wird von `CHANGETABLE(VERSION ...)` die `SYS_CHANGE_VERSION` für die von `@product id`bestimmte Zeile angegeben.</span><span class="sxs-lookup"><span data-stu-id="3c13b-248">In the example, `CHANGETABLE(VERSION ...)` determines the `SYS_CHANGE_VERSION` for the row specified by `@product id`.</span></span> <span data-ttu-id="3c13b-249">`CHANGETABLE(CHANGES ...)` kann die gleichen Informationen abrufen, aber das wäre weniger effizient.</span><span class="sxs-lookup"><span data-stu-id="3c13b-249">`CHANGETABLE(CHANGES ...)` can obtain the same information, but that would be less efficient.</span></span> <span data-ttu-id="3c13b-250">Wenn der Wert von `SYS_CHANGE_VERSION` für die Zeile größer ist als der Wert von `@last_sync_version`, liegt ein Konflikt vor.</span><span class="sxs-lookup"><span data-stu-id="3c13b-250">If the value of `SYS_CHANGE_VERSION` for the row is larger than the value of `@last_sync_version`, there is a conflict.</span></span> <span data-ttu-id="3c13b-251">Wenn ein Konflikt vorliegt, wird die Zeile nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3c13b-251">If there is a conflict, the row will not be updated.</span></span> <span data-ttu-id="3c13b-252">Die `ISNULL()` -Prüfung ist erforderlich, da möglicherweise keine Änderungsinformationen für die Zeile verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3c13b-252">The `ISNULL()` check is required because there might be no change information available for the row.</span></span> <span data-ttu-id="3c13b-253">Es sind keine Änderungsinformationen vorhanden, wenn die Zeile seit der Aktivierung der Änderungsverfolgung oder seit der Bereinigung der Änderungsinformationen nicht aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3c13b-253">No change information would exist if the row had not been updated since change tracking was enabled or since the change information was cleaned up.</span></span>  
  
```sql  
-- Assumption: @last_sync_version has been validated.  
  
UPDATE  
    SalesLT.Product  
SET  
    ListPrice = @new_listprice  
FROM  
    SalesLT.Product AS P  
WHERE  
    ProductID = @product_id AND  
    @last_sync_version >= ISNULL (  
        SELECT CT.SYS_CHANGE_VERSION  
        FROM CHANGETABLE(VERSION SalesLT.Product,  
                        (ProductID), (P.ProductID)) AS CT),  
        0)  
```  
  
 <span data-ttu-id="3c13b-254">Mit dem folgenden Code kann die Anzahl der aktualisierten Zeilen überprüft werden, und es können weitere Informationen über den Konflikt ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-254">The following code can check the updated row count and can identify more information about the conflict.</span></span>  
  
```sql  
-- If the change cannot be made, find out more information.  
IF (@@ROWCOUNT = 0)  
BEGIN  
    -- Obtain the complete change information for the row.  
    SELECT  
        CT.SYS_CHANGE_VERSION, CT.SYS_CHANGE_CREATION_VERSION,  
        CT.SYS_CHANGE_OPERATION, CT.SYS_CHANGE_COLUMNS  
    FROM  
        CHANGETABLE(CHANGES SalesLT.Product, @last_sync_version) AS CT  
    WHERE  
        CT.ProductID = @product_id;  
  
    -- Check CT.SYS_CHANGE_VERSION to verify that it really was a conflict.  
    -- Check CT.SYS_CHANGE_OPERATION to determine the type of conflict:  
    -- update-update or update-delete.  
    -- The row that is specified by @product_id might no longer exist   
    -- if it has been deleted.  
END  
```  
  
### <a name="setting-context-information"></a><span data-ttu-id="3c13b-255">Speichern von Kontextinformationen</span><span class="sxs-lookup"><span data-stu-id="3c13b-255">Setting Context Information</span></span>  
 <span data-ttu-id="3c13b-256">Die WITH CHANGE_TRACKING_CONTEXT-Klausel ermöglicht die Speicherung von Kontextinformationen zusammen mit den Änderungsinformationen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-256">By using the WITH CHANGE_TRACKING_CONTEXT clause, an application can store context information together with the change information.</span></span> <span data-ttu-id="3c13b-257">Diese Informationen können dann aus der Spalte SYS_CHANGE_CONTEXT abgerufen werden, die von CHANGETABLE(CHANGES ...) zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3c13b-257">This information can then be obtained from the SYS_CHANGE_CONTEXT column that is returned by CHANGETABLE(CHANGES ...).</span></span>  
  
 <span data-ttu-id="3c13b-258">Kontextinformationen werden in der Regel verwendet, um die Quelle der Änderungen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="3c13b-258">Context information is typically used to identify the source of the changes.</span></span> <span data-ttu-id="3c13b-259">Wenn die Quelle einer Änderung identifiziert werden kann, können diese Informationen von einem Datenspeicher verwendet werden, um das Abrufen von Änderungen bei der nächsten Synchronisierung zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-259">If the source of the change can be identified, that information can be used by a data store to avoid obtaining changes when it synchronizes again.</span></span>  
  
```sql  
  -- Try to update the row and check for a conflict.  
  WITH CHANGE_TRACKING_CONTEXT (@source_id)  
  UPDATE  
     SalesLT.Product  
  SET  
      ListPrice = @new_listprice  
  FROM  
      SalesLT.Product AS P  
  WHERE  
     ProductID = @product_id AND  
     @last_sync_version >= ISNULL (  
         (SELECT CT.SYS_CHANGE_VERSION FROM CHANGETABLE(VERSION SalesLT.Product,  
         (ProductID), (P.ProductID)) AS CT),  
         0)  
```  
  
### <a name="ensuring-consistent-and-correct-results"></a><span data-ttu-id="3c13b-260">Sicherstellen von konsistenten und richtigen Ergebnissen</span><span class="sxs-lookup"><span data-stu-id="3c13b-260">Ensuring Consistent and Correct Results</span></span>  
 <span data-ttu-id="3c13b-261">Eine Anwendung muss bei der Überprüfung des Werts von @last_sync_version den Cleanupprozess berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-261">An application must consider the cleanup process when it validates the value of @last_sync_version.</span></span> <span data-ttu-id="3c13b-262">Grund hierfür ist, dass Daten möglicherweise nach dem Aufruf von CHANGE_TRACKING_MIN_VALID_VERSION(), jedoch vor Durchführung des Updates entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-262">This is because data could have been removed after CHANGE_TRACKING_MIN_VALID_VERSION() was called, but before the update was made.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="3c13b-263">Wir empfehlen die Verwendung der Momentaufnahmeisolation und das Vornehmen der Änderungen in einer Momentaufnahmetransaktion.</span><span class="sxs-lookup"><span data-stu-id="3c13b-263">We recommend that you use snapshot isolation and make the changes within a snapshot transaction.</span></span>  
  
```sql  
-- Prerequisite is to ensure ALLOW_SNAPSHOT_ISOLATION is ON for the database.  
  
SET TRANSACTION ISOLATION LEVEL SNAPSHOT;  
BEGIN TRAN  
    -- Verify that last_sync_version is valid.  
    IF (@last_sync_version <  
CHANGE_TRACKING_MIN_VALID_VERSION(OBJECT_ID('SalesLT.Product')))  
    BEGIN  
       RAISERROR (N'Last_sync_version too old', 16, -1);  
    END  
    ELSE  
    BEGIN  
        -- Try to update the row.  
        -- Check @@ROWCOUNT and check for a conflict.  
    END  
COMMIT TRAN  
```  
  
> [!NOTE]  
>  <span data-ttu-id="3c13b-264">Es besteht die Möglichkeit, dass die bei der Momentaufnahmetransaktion aktualisierte Zeile bereits in einer anderen Transaktion aktualisiert wurde, nachdem die Momentaufnahmetransaktion gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="3c13b-264">There is a possibility that the row being updated within the snapshot transaction could have been updated in another transaction after the snapshot transaction was started.</span></span> <span data-ttu-id="3c13b-265">In diesem Fall tritt ein Momentaufnahmeisolations-Updatekonflikt auf und bewirkt, dass die Transaktion beendet wird.</span><span class="sxs-lookup"><span data-stu-id="3c13b-265">In this case, a snapshot isolation update conflict will occur and lead to the transaction being terminated.</span></span> <span data-ttu-id="3c13b-266">Wiederholen Sie in diesem Fall das Update.</span><span class="sxs-lookup"><span data-stu-id="3c13b-266">If this happens, retry the update.</span></span> <span data-ttu-id="3c13b-267">Dies führt dann dazu, dass ein Änderungsnachverfolgungskonflikt erkannt wird und keine Zeilen geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3c13b-267">This will then lead to a change tracking conflict being detected and no rows being changed.</span></span>  
  
##  <a name="change-tracking-and-data-restore"></a><a name="DataRestore"></a><span data-ttu-id="3c13b-268">Änderungsnachverfolgung und Datenwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="3c13b-268">Change Tracking and Data Restore</span></span>  
 <span data-ttu-id="3c13b-269">Bei Anwendungen, für die eine Synchronisierung erforderlich ist, muss der Fall berücksichtigt werden, dass eine für die Änderungsnachverfolgung aktivierte Datenbank eine frühere Version der Daten wiederherstellt.</span><span class="sxs-lookup"><span data-stu-id="3c13b-269">Applications that require synchronization must consider the case in which a database that has change tracking enabled reverts to an earlier version of the data.</span></span> <span data-ttu-id="3c13b-270">Dies kann auftreten, wenn eine Datenbank aus einer Sicherung wiederhergestellt wird, wenn ein Failover zu einer asynchronen Spiegeldatenbank besteht oder wenn beim Protokollversand ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="3c13b-270">This can occur after a database is restored from a backup, when there is a failover to an asynchronous database mirror, or when there is a failure when using log shipping.</span></span> <span data-ttu-id="3c13b-271">Das folgende Beispiel veranschaulicht dieses Szenario:</span><span class="sxs-lookup"><span data-stu-id="3c13b-271">The following scenario illustrates the issue:</span></span>  
  
1.  <span data-ttu-id="3c13b-272">Für Tabelle T1 werden Änderungen nachverfolgt, und die minimal gültige Version für die Tabelle ist 50.</span><span class="sxs-lookup"><span data-stu-id="3c13b-272">Table T1 is change tracked, and the minimum valid version for table is 50.</span></span>  
  
2.  <span data-ttu-id="3c13b-273">Eine Clientanwendung synchronisiert die Daten bei Version 100 und ruft Informationen über alle Änderungen zwischen Version 50 und 100 ab.</span><span class="sxs-lookup"><span data-stu-id="3c13b-273">A client application synchronizes data at version 100 and obtains information about all changes between versions 50 and 100.</span></span>  
  
3.  <span data-ttu-id="3c13b-274">Nach Version 100 werden zusätzliche Änderungen an der Tabelle T1 vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-274">Additional changes are made to table T1 after version 100.</span></span>  
  
4.  <span data-ttu-id="3c13b-275">Bei Version 120 tritt ein Fehler auf, und der Datenbankadministrator stellt die Datenbank mit Datenverlust wieder her.</span><span class="sxs-lookup"><span data-stu-id="3c13b-275">At version 120, there is a failure and the database administrator restores the database with data loss.</span></span> <span data-ttu-id="3c13b-276">Nach der Wiederherstellung enthält die Tabelle Daten bis einschließlich Version 70, und die minimale synchronisierte Version ist weiterhin 50.</span><span class="sxs-lookup"><span data-stu-id="3c13b-276">After the restore operation, the table contains data up through version 70, and the minimum synchronized version is still 50.</span></span>  
  
     <span data-ttu-id="3c13b-277">Dies bedeutet, dass der synchronisierte Datenspeicher über Daten verfügt, die nicht mehr im primären Datenspeicher vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="3c13b-277">This means that the synchronized data store has data that no longer exists in the primary data store.</span></span>  
  
5.  <span data-ttu-id="3c13b-278">T1 wird häufig aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="3c13b-278">T1 is updated many times.</span></span> <span data-ttu-id="3c13b-279">Die aktuelle Version ist daher 130.</span><span class="sxs-lookup"><span data-stu-id="3c13b-279">This brings the current version to 130.</span></span>  
  
6.  <span data-ttu-id="3c13b-280">Die Clientanwendung synchronisiert erneut und gibt als zuletzt synchronisierte Version 100 aus.</span><span class="sxs-lookup"><span data-stu-id="3c13b-280">The client application synchronizes again and supplies a last-synchronized version of 100.</span></span> <span data-ttu-id="3c13b-281">Die Überprüfung dieser Version durch den Client ist erfolgreich, da 100 größer als 50 ist.</span><span class="sxs-lookup"><span data-stu-id="3c13b-281">The client validates this number successfully because 100 is greater than 50.</span></span>  
  
     <span data-ttu-id="3c13b-282">Der Client ruft die Änderungen zwischen Version 100 und 130 ab.</span><span class="sxs-lookup"><span data-stu-id="3c13b-282">The client obtains changes between version 100 and 130.</span></span> <span data-ttu-id="3c13b-283">Zu diesem Zeitpunkt weiß der Client nicht, dass die Änderungen zwischen Version 70 und 100 nicht die gleichen wie zuvor sind.</span><span class="sxs-lookup"><span data-stu-id="3c13b-283">At this point, the client is not aware that the changes between 70 and 100 are not the same as before.</span></span> <span data-ttu-id="3c13b-284">Die Daten auf dem Client und dem Server sind nicht synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="3c13b-284">The data on the client and server are not synchronized.</span></span>  
  
 <span data-ttu-id="3c13b-285">Beachten Sie, dass es keine Probleme bei der Synchronisierung gäbe, wenn die Datenbank auf einen Punkt nach Version 100 wiederhergestellt würde.</span><span class="sxs-lookup"><span data-stu-id="3c13b-285">Note that if the database was recovered to a point after version 100, there would be no problems with synchronization.</span></span> <span data-ttu-id="3c13b-286">Der Client und der Server würden während des nächsten Synchronisierungsintervalls Daten ordnungsgemäß synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="3c13b-286">The client and server would synchronize data correctly during the next synchronization interval.</span></span>  
  
 <span data-ttu-id="3c13b-287">Die Änderungsnachverfolgung bietet keine Unterstützung bei der Wiederherstellung nach einem Datenverlust.</span><span class="sxs-lookup"><span data-stu-id="3c13b-287">Change tracking does not provide support for recovering from the loss of data.</span></span> <span data-ttu-id="3c13b-288">Es gibt jedoch zwei Optionen zum Erkennen dieser Art von Synchronisierungsproblemen:</span><span class="sxs-lookup"><span data-stu-id="3c13b-288">However, there are two options for detecting these types of synchronization issues:</span></span>  
  
-   <span data-ttu-id="3c13b-289">Speichern Sie eine Datenbankversions-ID auf dem Server, und aktualisieren Sie diesen Wert immer dann, wenn eine Datenbank wiederhergestellt wird oder auf sonstige Weise ein Datenverlust auftritt.</span><span class="sxs-lookup"><span data-stu-id="3c13b-289">Store a database version ID on the server, and update this value whenever a database is recovered or otherwise loses data.</span></span> <span data-ttu-id="3c13b-290">Die ID würde in jeder Clientanwendung gespeichert, und jeder Client müsste diese ID beim Synchronisieren der Daten überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-290">Each client application would store the ID, and each client would have to validate this ID when it synchronizes data.</span></span> <span data-ttu-id="3c13b-291">Wenn Datenverlust auftritt, stimmen die IDs nicht überein, und die Clients würden eine Neuinitialisierung durchführen.</span><span class="sxs-lookup"><span data-stu-id="3c13b-291">If data loss occurs, the IDs will not match and the clients would reinitialize.</span></span> <span data-ttu-id="3c13b-292">Ein Nachteil besteht darin, dass der Client eine unnötige Neuinitialisierung durchführt, wenn der Datenverlust nicht über die letzte Synchronisierungsgrenze hinaus erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="3c13b-292">One drawback is if the data loss had not crossed the last synchronized boundary, the client might do unnecessary reinitialization.</span></span>  
  
-   <span data-ttu-id="3c13b-293">Zeichnen Sie die Versionsnummer der letzten Synchronisierung auf dem Server auf, wenn ein Client Änderungen abfragt.</span><span class="sxs-lookup"><span data-stu-id="3c13b-293">When a client queries for changes, record the last synchronization version number for each client on the server.</span></span> <span data-ttu-id="3c13b-294">Wenn ein Problem mit den Daten vorliegt, stimmen die Versionsnummern der letzten Synchronisierung nicht überein.</span><span class="sxs-lookup"><span data-stu-id="3c13b-294">If there is a problem with the data, the last synchronized version numbers would not match.</span></span> <span data-ttu-id="3c13b-295">Dies weist darauf hin, dass eine Neuinitialisierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="3c13b-295">This indicates that a reinitialization is required.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c13b-296">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3c13b-296">See Also</span></span>  
 <span data-ttu-id="3c13b-297">[Nachverfolgen von Datenänderungen &#40;SQL Server&#41;](../track-changes/track-data-changes-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3c13b-297">[Track Data Changes &#40;SQL Server&#41;](../track-changes/track-data-changes-sql-server.md) </span></span>  
 <span data-ttu-id="3c13b-298">[Informationen zur Änderungsnachverfolgung &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3c13b-298">[About Change Tracking &#40;SQL Server&#41;](../track-changes/about-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="3c13b-299">[Verwalten Sie Änderungsnachverfolgung &#40;SQL Server&#41;](../track-changes/manage-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3c13b-299">[Manage Change Tracking &#40;SQL Server&#41;](../track-changes/manage-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="3c13b-300">[Aktivieren und deaktivieren Sie Änderungsnachverfolgung &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3c13b-300">[Enable and Disable Change Tracking &#40;SQL Server&#41;](../track-changes/enable-and-disable-change-tracking-sql-server.md) </span></span>  
 <span data-ttu-id="3c13b-301">[CHANGETABLE &#40;Transact-SQL-&#41;](/sql/relational-databases/system-functions/changetable-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c13b-301">[CHANGETABLE &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/changetable-transact-sql) </span></span>  
 <span data-ttu-id="3c13b-302">[CHANGE_TRACKING_MIN_VALID_VERSION &#40;Transact-SQL-&#41;](/sql/relational-databases/system-functions/change-tracking-min-valid-version-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c13b-302">[CHANGE_TRACKING_MIN_VALID_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-min-valid-version-transact-sql) </span></span>  
 <span data-ttu-id="3c13b-303">[CHANGE_TRACKING_CURRENT_VERSION &#40;Transact-SQL-&#41;](/sql/relational-databases/system-functions/change-tracking-current-version-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3c13b-303">[CHANGE_TRACKING_CURRENT_VERSION &#40;Transact-SQL&#41;](/sql/relational-databases/system-functions/change-tracking-current-version-transact-sql) </span></span>  
 [<span data-ttu-id="3c13b-304">WITH CHANGE_TRACKING_CONTEXT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3c13b-304">WITH CHANGE_TRACKING_CONTEXT &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-functions/with-change-tracking-context-transact-sql)  
  
  
