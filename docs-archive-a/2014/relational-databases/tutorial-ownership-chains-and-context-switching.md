---
title: 'Tutorial: Besitzketten und Kontextwechsel | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- context switching [SQL Server], tutorials
- ownership chains [SQL Server]
ms.assetid: db5d4cc3-5fc5-4cf5-afc1-8d4edc1d512b
author: rothja
ms.author: jroth
ms.openlocfilehash: 1e9072a68dd3179e5900fda06d4fea58b484a37e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615908"
---
# <a name="tutorial-ownership-chains-and-context-switching"></a><span data-ttu-id="4809c-102">Tutorial: Ownership Chains and Context Switching</span><span class="sxs-lookup"><span data-stu-id="4809c-102">Tutorial: Ownership Chains and Context Switching</span></span>
  <span data-ttu-id="4809c-103">Anhand des Szenarios in diesem Lernprogramm werden [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Sicherheitskonzepte verdeutlicht, die Besitzketten und Kontextwechsel umfassen.</span><span class="sxs-lookup"><span data-stu-id="4809c-103">This tutorial uses a scenario to illustrate [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] security concepts involving ownership chains and user context switching.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4809c-104">Damit Sie den Code ausführen können, der in diesem Lernprogramm enthalten ist, müssen Sie die Sicherheit für den gemischte Modus konfiguriert und die [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] -Datenbank installiert haben.</span><span class="sxs-lookup"><span data-stu-id="4809c-104">To run the code in this tutorial you must have both Mixed Mode security configured and the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database installed.</span></span> <span data-ttu-id="4809c-105">Weitere Informationen zur Sicherheit für den gemischte Modus finden Sie unter [Auswählen eines Authentifizierungsmodus](security/choose-an-authentication-mode.md).</span><span class="sxs-lookup"><span data-stu-id="4809c-105">For more information about Mixed Mode security, see [Choose an Authentication Mode](security/choose-an-authentication-mode.md).</span></span>  
  
## <a name="scenario"></a><span data-ttu-id="4809c-106">Szenario</span><span class="sxs-lookup"><span data-stu-id="4809c-106">Scenario</span></span>  
 <span data-ttu-id="4809c-107">In diesem Szenario benötigen zwei Benutzer Konten, über die sie auf die Bestellungsdaten zugreifen können, die in der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] -Datenbank gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4809c-107">In this scenario, two users need accounts to access purchase order data stored in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span> <span data-ttu-id="4809c-108">Es gelten folgende Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="4809c-108">The requirements are as follows:</span></span>  
  
-   <span data-ttu-id="4809c-109">Über das erste Konto (TestManagerUser) muss es möglich sein, alle Details in jeder Bestellung anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="4809c-109">The first account (TestManagerUser) must be able to see all details in every purchase order.</span></span>  
  
-   <span data-ttu-id="4809c-110">Über das zweite Konto (TestEmployeeUser) muss es möglich sein, für Artikel, für die Teillieferungen eingegangen sind, folgende Informationen anzeigen zu können: Bestellnummer, Bestelldatum, Versanddatum, Produktnummern sowie die pro Bestellung bestellten und eingegangenen Artikel.</span><span class="sxs-lookup"><span data-stu-id="4809c-110">The second account (TestEmployeeUser) must be able to see the purchase order number, order date, shipping date, product ID numbers, and the ordered and received items per purchase order, by purchase order number, for items where partial shipments have been received.</span></span>  
  
-   <span data-ttu-id="4809c-111">Alle anderen Konten müssen ihre aktuellen Berechtigungen behalten.</span><span class="sxs-lookup"><span data-stu-id="4809c-111">All other accounts must retain their current permissions.</span></span>  
  
 <span data-ttu-id="4809c-112">Damit die Anforderungen dieses Szenarios erfüllt werden können, ist dieses Beispiel in vier Abschnitte unterteilt, in denen die Konzepte für Besitzketten und Kontextwechsel dargestellt werden:</span><span class="sxs-lookup"><span data-stu-id="4809c-112">To fulfill the requirements of this scenario, the example is broken into four parts that demonstrate the concepts of ownership chains and context switching:</span></span>  
  
1.  <span data-ttu-id="4809c-113">Konfigurieren der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="4809c-113">Configuring the environment.</span></span>  
  
2.  <span data-ttu-id="4809c-114">Erstellen einer gespeicherten Prozedur, damit nach Bestellung auf die Daten zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="4809c-114">Creating a stored procedure to access data by purchase order.</span></span>  
  
3.  <span data-ttu-id="4809c-115">Zugreifen auf die Daten über die gespeicherte Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4809c-115">Accessing the data through the stored procedure.</span></span>  
  
4.  <span data-ttu-id="4809c-116">Zurücksetzen der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="4809c-116">Resetting the environment.</span></span>  
  
 <span data-ttu-id="4809c-117">Jeder Codeblock dieses Beispiels wird jeweils sofort erläutert.</span><span class="sxs-lookup"><span data-stu-id="4809c-117">Each code block in this example is explained in line.</span></span> <span data-ttu-id="4809c-118">Informationen, wie Sie das vollständige Beispiel kopieren können, finden Sie unter [Vollständiges Beispiel](#CompleteExample) am Ende dieses Lernprogramms.</span><span class="sxs-lookup"><span data-stu-id="4809c-118">To copy the complete example, see [Complete Example](#CompleteExample) at the end of this tutorial.</span></span>  
  
## <a name="1-configure-the-environment"></a><span data-ttu-id="4809c-119">1. Konfigurieren der Umgebung</span><span class="sxs-lookup"><span data-stu-id="4809c-119">1. Configure the Environment</span></span>  
 <span data-ttu-id="4809c-120">Verwenden [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] Sie und den folgenden Code, um die Datenbank zu öffnen `AdventureWorks2012` , und verwenden Sie die- `CURRENT_USER` [!INCLUDE[tsql](../includes/tsql-md.md)] Anweisung, um zu überprüfen, ob der dbo-Benutzer als Kontext angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4809c-120">Use [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] and the following code to open the `AdventureWorks2012` database, and use the `CURRENT_USER` [!INCLUDE[tsql](../includes/tsql-md.md)] statement to check that the dbo user is displayed as the context.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
```  
  
 <span data-ttu-id="4809c-121">Weitere Informationen zur CURRENT_USER-Anweisung finden Sie unter [CURRENT_USER &#40;Transact-SQL&#41;](/sql/t-sql/functions/current-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4809c-121">For more information about the CURRENT_USER statement, see [CURRENT_USER &#40;Transact-SQL&#41;](/sql/t-sql/functions/current-user-transact-sql).</span></span>  
  
 <span data-ttu-id="4809c-122">Verwenden Sie diesen Code als Benutzer dbo dazu, auf dem Server und in der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)]-Datenbank zwei Benutzer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4809c-122">Use this code as the dbo user to create two users on the server and in the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
CREATE LOGIN TestManagerUser   
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khx';  
GO  
CREATE USER TestManagerUser   
   FOR LOGIN TestManagerUser  
   WITH DEFAULT_SCHEMA = Purchasing;  
GO   
  
CREATE LOGIN TestEmployeeUser  
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
GO  
CREATE USER TestEmployeeUser   
   FOR LOGIN TestEmployeeUser;  
GO   
```  
  
 <span data-ttu-id="4809c-123">Weitere Informationen zur CREATE USER-Anweisung finden Sie unter [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4809c-123">For more information about the CREATE USER statement, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span> <span data-ttu-id="4809c-124">Weitere Informationen zur CREATE LOGIN-Anweisung finden Sie unter [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4809c-124">For more information about the CREATE LOGIN statement, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
 <span data-ttu-id="4809c-125">Übertragen Sie mit dem folgenden Code den Besitz des `Purchasing` -Schemas auf das Konto `TestManagerUser` .</span><span class="sxs-lookup"><span data-stu-id="4809c-125">Use the following code to change the ownership of the `Purchasing` schema to the `TestManagerUser` account.</span></span> <span data-ttu-id="4809c-126">Dadurch wird es ermöglicht, unter diesem Konto mit allen DML-Anweisungen (Data Manipulation Language, z. B. `SELECT` - und `INSERT` -Berechtigungen) auf die Objekte zuzugreifen, die das Schema enthält.</span><span class="sxs-lookup"><span data-stu-id="4809c-126">This allows that account to use all Data Manipulation Language (DML) statement access (such as `SELECT` and `INSERT` permissions) on the objects it contains.</span></span> <span data-ttu-id="4809c-127">`TestManagerUser` wird auch die Berechtigung zum Erstellen gespeicherter Prozeduren erteilt.</span><span class="sxs-lookup"><span data-stu-id="4809c-127">`TestManagerUser` is also granted the ability to create stored procedures.</span></span>  
  
```  
/* Change owner of the Purchasing Schema to TestManagerUser */  
ALTER AUTHORIZATION   
   ON SCHEMA::Purchasing   
   TO TestManagerUser;  
GO  
  
GRANT CREATE PROCEDURE   
   TO TestManagerUser   
   WITH GRANT OPTION;  
GO  
```  
  
 <span data-ttu-id="4809c-128">Weitere Informationen zur GRANT-Anweisung finden Sie unter [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4809c-128">For more information about the GRANT statement, see [GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-transact-sql).</span></span> <span data-ttu-id="4809c-129">Weitere Informationen zum Aufrufen von gespeicherten Prozeduren finden Sie unter [Gespeicherte Prozeduren &#40;Datenbank-Engine&#41;](stored-procedures/stored-procedures-database-engine.md).</span><span class="sxs-lookup"><span data-stu-id="4809c-129">For more information about stored procedures, see [Stored Procedures &#40;Database Engine&#41;](stored-procedures/stored-procedures-database-engine.md).</span></span> <span data-ttu-id="4809c-130">Ein Poster aller [!INCLUDE[ssDE](../includes/ssde-md.md)] Berechtigungen finden Sie unter [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf) .</span><span class="sxs-lookup"><span data-stu-id="4809c-130">For a poster of all [!INCLUDE[ssDE](../includes/ssde-md.md)] permissions, see [https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf](https://github.com/microsoft/sql-server-samples/blob/master/samples/features/security/permissions-posters/Microsoft_SQL_Server_2017_and_Azure_SQL_Database_permissions_infographic.pdf).</span></span>  
  
## <a name="2-create-a-stored-procedure-to-access-data"></a><span data-ttu-id="4809c-131">2. Erstellen einer gespeicherten Prozedur für Zugriff auf Daten</span><span class="sxs-lookup"><span data-stu-id="4809c-131">2. Create a Stored Procedure to Access Data</span></span>  
 <span data-ttu-id="4809c-132">Um den Kontext innerhalb einer Datenbank zu wechseln, verwenden Sie die EXECUTE AS-Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4809c-132">To switch context within a database, use the EXECUTE AS statement.</span></span> <span data-ttu-id="4809c-133">EXECUTE AS erfordert IMPERSONATE-Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="4809c-133">EXECUTE AS requires IMPERSONATE permissions.</span></span>  
  
 <span data-ttu-id="4809c-134">Im folgenden Code wird die `EXECUTE AS` -Anweisung dazu verwendet, einen Kontextwechsel auf `TestManagerUser` vorzunehmen und eine gespeicherte Prozedur zu erstellen, die nur die Daten anzeigt, die von `TestEmployeeUser`benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="4809c-134">Use the `EXECUTE AS` statement in the following code to change the context to `TestManagerUser` and create a stored procedure showing only the data required by `TestEmployeeUser`.</span></span> <span data-ttu-id="4809c-135">Damit die Anforderungen erfüllt werden, ist die gespeicherte Prozedur wie folgt aufgebaut: Sie nimmt eine Variable für die Bestellnummer entgegen, zeigt keine Finanzinformationen an und enthält eine WHERE-Klausel, die die Ergebnisse auf Teillieferungen beschränkt.</span><span class="sxs-lookup"><span data-stu-id="4809c-135">To satisfy the requirements, the stored procedure accepts one variable for the purchase order number and does not display financial information, and the WHERE clause limits the results to partial shipments.</span></span>  
  
```  
EXECUTE AS LOGIN = 'TestManagerUser'  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
  
/* Note: The user that calls the EXECUTE AS statement must have IMPERSONATE permissions on the target principal */  
CREATE PROCEDURE usp_ShowWaitingItems @ProductID int  
AS  
BEGIN   
   SELECT a.PurchaseOrderID, a.OrderDate, a.ShipDate  
      , b.ProductID, b.OrderQty, b.ReceivedQty  
   FROM Purchasing.PurchaseOrderHeader a  
      INNER JOIN Purchasing.PurchaseOrderDetail b  
         ON a.PurchaseOrderID = b.PurchaseOrderID  
   WHERE b.OrderQty > b.ReceivedQty  
      AND @ProductID = b.ProductID  
   ORDER BY b.ProductID ASC  
END  
GO  
```  
  
 <span data-ttu-id="4809c-136">Momentan kann `TestEmployeeUser` auf keines der Datenbankobjekte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4809c-136">Currently `TestEmployeeUser` does not have access to any database objects.</span></span> <span data-ttu-id="4809c-137">Der folgende Code (nach wie vor im `TestManagerUser` -Kontext) erteilt dem Benutzerkonto die Berechtigung, über die gespeicherte Prozedur Informationen aus den Basistabellen abrufen zu können.</span><span class="sxs-lookup"><span data-stu-id="4809c-137">The following code (still in the `TestManagerUser` context) grants the user account the ability to query base-table information through the stored procedure.</span></span>  
  
```  
GRANT EXECUTE  
   ON OBJECT::Purchasing.usp_ShowWaitingItems  
   TO TestEmployeeUser;  
GO  
```  
  
 <span data-ttu-id="4809c-138">Die gespeicherte Prozedur gehört, obwohl kein Schema explizit angegeben wurde, zum `Purchasing` -Schema, weil `TestManagerUser` standardmäßig dem `Purchasing` -Schema zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="4809c-138">The stored procedure is part of the `Purchasing` schema, even though no schema was explicitly specified, because `TestManagerUser` is assigned by default to the `Purchasing` schema.</span></span> <span data-ttu-id="4809c-139">Wie im folgenden Code gezeigt, können Sie Systemkataloginformationen dazu verwenden, nach Objekten zu suchen.</span><span class="sxs-lookup"><span data-stu-id="4809c-139">You can use system catalog information to locate objects, as shown in the following code.</span></span>  
  
```  
SELECT a.name AS 'Schema'  
   , b.name AS 'Object Name'  
   , b.type AS 'Object Type'  
FROM sys.schemas a  
   INNER JOIN sys.objects b  
      ON a.schema_id = b.schema_id   
WHERE b.name = 'usp_ShowWaitingItems';  
GO  
```  
  
 <span data-ttu-id="4809c-140">Nachdem dieser Abschnitt des Beispiels abgeschlossen ist, wird im Code die `REVERT`-Anweisung dazu verwendet, wieder einen Kontextwechsel auf dbo vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="4809c-140">With this section of the example completed, the code switches context back to dbo using the `REVERT` statement.</span></span>  
  
```  
REVERT;  
GO  
```  
  
 <span data-ttu-id="4809c-141">Weitere Informationen zur REVERT-Anweisung finden Sie unter [REVERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/revert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="4809c-141">For more information about the REVERT statement, see [REVERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/revert-transact-sql).</span></span>  
  
## <a name="3-access-data-through-the-stored-procedure"></a><span data-ttu-id="4809c-142">3. Zugreifen auf Daten über die gespeicherte Prozedur</span><span class="sxs-lookup"><span data-stu-id="4809c-142">3. Access Data Through the Stored Procedure</span></span>  
 <span data-ttu-id="4809c-143">`TestEmployeeUser` hat für die Objekte der [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] -Datenbank keine Berechtigungen, die über eine Anmeldung und die Berechtigungen hinausgehen, die der public-Datenbankrolle zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="4809c-143">`TestEmployeeUser` has no permissions on the [!INCLUDE[ssSampleDBobject](../includes/sssampledbobject-md.md)] database objects other than a login and the rights assigned to the public database role.</span></span> <span data-ttu-id="4809c-144">Der folgende Code gibt einen Fehler zurück, wenn `TestEmployeeUser` versucht, auf eine der Basistabellen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="4809c-144">The following code returns an error when `TestEmployeeUser` attempts to access base tables.</span></span>  
  
```  
EXECUTE AS LOGIN = 'TestEmployeeUser'  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
/* This won't work */  
SELECT *  
FROM Purchasing.PurchaseOrderHeader;  
GO  
SELECT *  
FROM Purchasing.PurchaseOrderDetail;  
GO  
```  
  
 <span data-ttu-id="4809c-145">Über die gespeicherte Prozedur, die im vorherigen Abschnitt erstellt wurde, kann `TestManagerUser` auf die Basistabellen zugreifen, weil sich die Objekte, auf die in der gespeicherten Prozedur verwiesen wird, über den Besitz des `Purchasing` -Schemas im Besitz von `TestEmployeeUser` befinden.</span><span class="sxs-lookup"><span data-stu-id="4809c-145">Because the objects referenced by the stored procedure created in the last section are owned by `TestManagerUser` by virtue of the `Purchasing` schema ownership, `TestEmployeeUser` can access the base tables through the stored procedure.</span></span> <span data-ttu-id="4809c-146">Im folgenden Code, für den weiterhin der `TestEmployeeUser` -Kontext verwendet wird, wird die Bestellnummer 952 als Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="4809c-146">The following code, still using the `TestEmployeeUser` context, passes purchase order 952 as a parameter.</span></span>  
  
```  
EXEC Purchasing.usp_ShowWaitingItems 952  
GO  
```  
  
## <a name="4-reset-the-environment"></a><span data-ttu-id="4809c-147">4. Zurücksetzen der Umgebung</span><span class="sxs-lookup"><span data-stu-id="4809c-147">4. Reset the Environment</span></span>  
 <span data-ttu-id="4809c-148">Im folgenden Code wird der Befehl `REVERT` verwendet, um den Kontext des aktuellen Kontos auf `dbo`zurückzusetzen, und dann die Umgebung zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="4809c-148">The following code uses the `REVERT` command to return the context of the current account to `dbo`, and then resets the environment.</span></span>  
  
```  
REVERT;  
GO  
ALTER AUTHORIZATION   
ON SCHEMA::Purchasing TO dbo;  
GO  
DROP PROCEDURE Purchasing.usp_ShowWaitingItems;  
GO  
DROP USER TestEmployeeUser;  
GO  
DROP USER TestManagerUser;  
GO  
DROP LOGIN TestEmployeeUser;  
GO  
DROP LOGIN TestManagerUser;  
GO  
```  
  
##  <a name="complete-example"></a><a name="CompleteExample"></a><span data-ttu-id="4809c-149">Vervollständigen eines Beispiels</span><span class="sxs-lookup"><span data-stu-id="4809c-149">Complete Example</span></span>  
 <span data-ttu-id="4809c-150">In diesem Abschnitt wird der vollständige Beispielcode angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4809c-150">This section displays the complete example code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4809c-151">Dieser Code enthält nicht die beiden erwarteten Fehler, die verdeutlichen, dass `TestEmployeeUser` keine Informationen aus Basistabellen auswählen kann.</span><span class="sxs-lookup"><span data-stu-id="4809c-151">This code does not include the two expected errors that demonstrate the inability of `TestEmployeeUser` to select from base tables.</span></span>  
  
```  
/*   
Script:       UserContextTutorial.sql  
Author:       Microsoft  
Last Updated: Books Online  
Conditions:   Execute as DBO or sysadmin in the AdventureWorks database  
Section 1:    Configure the Environment   
*/  
USE AdventureWorks2012;  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
/* Create server and database users */  
CREATE LOGIN TestManagerUser   
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khx';  
  
GO  
  
CREATE USER TestManagerUser   
   FOR LOGIN TestManagerUser  
   WITH DEFAULT_SCHEMA = Purchasing;  
GO   
  
CREATE LOGIN TestEmployeeUser  
    WITH PASSWORD = '340$Uuxwp7Mcxo7Khy';  
GO  
CREATE USER TestEmployeeUser   
   FOR LOGIN TestEmployeeUser;  
GO   
  
/* Change owner of the Purchasing Schema to TestManagerUser */  
ALTER AUTHORIZATION   
   ON SCHEMA::Purchasing   
   TO TestManagerUser;  
GO  
  
GRANT CREATE PROCEDURE   
   TO TestManagerUser   
   WITH GRANT OPTION;  
GO  
  
/*   
Section 2: Switch Context and Create Objects  
*/  
EXECUTE AS LOGIN = 'TestManagerUser';  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
  
/* Note: The user that calls the EXECUTE AS statement must have IMPERSONATE permissions on the target principal */  
CREATE PROCEDURE usp_ShowWaitingItems @ProductID int  
AS  
BEGIN   
   SELECT a.PurchaseOrderID, a.OrderDate, a.ShipDate  
      , b.ProductID, b.OrderQty, b.ReceivedQty  
   FROM Purchasing.PurchaseOrderHeader AS a  
      INNER JOIN Purchasing.PurchaseOrderDetail AS b  
         ON a.PurchaseOrderID = b.PurchaseOrderID  
   WHERE b.OrderQty > b.ReceivedQty  
      AND @ProductID = b.ProductID  
   ORDER BY b.ProductID ASC  
END;  
GO  
  
/* Give the employee the ability to run the procedure */  
GRANT EXECUTE   
   ON OBJECT::Purchasing.usp_ShowWaitingItems  
   TO TestEmployeeUser;  
GO   
  
/* Notice that the stored procedure is located in the Purchasing   
schema. This also demonstrates system catalogs */  
SELECT a.name AS 'Schema'  
   , b.name AS 'Object Name'  
   , b.type AS 'Object Type'  
FROM sys.schemas AS a  
   INNER JOIN sys.objects AS b  
      ON a.schema_id = b.schema_id   
WHERE b.name = 'usp_ShowWaitingItems';  
GO  
  
/* Go back to being the dbo user */  
REVERT;  
GO  
  
/*  
Section 3: Switch Context and Observe Security   
*/  
EXECUTE AS LOGIN = 'TestEmployeeUser';  
GO  
SELECT CURRENT_USER AS 'Current User Name';  
GO  
EXEC Purchasing.usp_ShowWaitingItems 952;  
GO  
  
/*   
Section 4: Clean Up Example  
*/  
REVERT;  
GO  
ALTER AUTHORIZATION   
ON SCHEMA::Purchasing TO dbo;  
GO  
DROP PROCEDURE Purchasing.usp_ShowWaitingItems;  
GO  
DROP USER TestEmployeeUser;  
GO  
DROP USER TestManagerUser;  
GO  
DROP LOGIN TestEmployeeUser;  
GO  
DROP LOGIN TestManagerUser;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="4809c-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4809c-152">See Also</span></span>  
 [<span data-ttu-id="4809c-153">Sicherheitscenter für SQL Server-Datenbank-Engine und Azure SQL-Datenbank</span><span class="sxs-lookup"><span data-stu-id="4809c-153">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
