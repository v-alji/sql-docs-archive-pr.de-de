---
title: Ändern einer gespeicherten Prozedur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.technology: stored-procedures
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- modifying stored procedures
- editing stored procedures
- stored procedures [SQL Server], modifying
ms.assetid: 13396239-6100-48ce-aa34-461358d99c92
author: stevestein
ms.author: sstein
ms.openlocfilehash: 906f0e06650da505094d18774ce86dab53d53f38
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695486"
---
# <a name="modify-a-stored-procedure"></a><span data-ttu-id="f39b9-102">Ändern einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="f39b9-102">Modify a Stored Procedure</span></span>
    
##  <a name="this-topic-describes-how-to-modify-a-stored-procedure-in-sscurrent-by-using-ssmanstudiofull-or-tsql"></a><a name="Top"></a> <span data-ttu-id="f39b9-103">In diesem Thema wird beschrieben, wie eine gespeicherte Prozedur mit [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] oder [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] in [!INCLUDE[tsql](../../includes/tsql-md.md)]geändert wird.</span><span class="sxs-lookup"><span data-stu-id="f39b9-103">This topic describes how to modify a stored procedure in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
-   <span data-ttu-id="f39b9-104">**Vorbereitungen:**  [Beschränkungen](#Restrictions), [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="f39b9-104">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="f39b9-105">**So ändern Sie eine Prozedur mithilfe von:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span><span class="sxs-lookup"><span data-stu-id="f39b9-105">**To alter a procedure, using:**  [SQL Server Management Studio](#SSMSProcedure), [Transact-SQL](#TsqlProcedure)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="f39b9-106">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="f39b9-106">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="f39b9-107">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="f39b9-107">Limitations and Restrictions</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)] <span data-ttu-id="f39b9-108">-gespeicherte Prozeduren können nicht in CLR-gespeicherte Prozeduren geändert werden und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="f39b9-108">stored procedures cannot be modified to be CLR stored procedures and vice versa.</span></span>  
  
 <span data-ttu-id="f39b9-109">Wenn die vorherige Prozedurdefinition mit WITH ENCRYPTION oder WITH RECOMPILE erstellt wurde, sind diese Optionen nur dann aktiviert, wenn sie in der ALTER PROCEDURE-Anweisung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="f39b9-109">If the previous procedure definition was created using WITH ENCRYPTION or WITH RECOMPILE, these options are enabled only if they are included in the ALTER PROCEDURE statement.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="f39b9-110">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f39b9-110">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f39b9-111">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="f39b9-111">Permissions</span></span>  
 <span data-ttu-id="f39b9-112">Erfordert ALTER PROCEDURE-Berechtigung für die Prozedur.</span><span class="sxs-lookup"><span data-stu-id="f39b9-112">Requires ALTER PROCEDURE permission on the procedure.</span></span>  
  
##  <a name="how-to-modify-a-stored-procedure"></a><a name="Procedures"></a> <span data-ttu-id="f39b9-113">Vorgehensweise: Ändern einer gespeicherten Prozedur</span><span class="sxs-lookup"><span data-stu-id="f39b9-113">How to Modify a Stored Procedure</span></span>  
 <span data-ttu-id="f39b9-114">Sie können eine der folgenden Anwendungen verwenden:</span><span class="sxs-lookup"><span data-stu-id="f39b9-114">You can use one of the following:</span></span>  
  
-   [<span data-ttu-id="f39b9-115">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f39b9-115">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
-   [<span data-ttu-id="f39b9-116">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f39b9-116">Transact-SQL</span></span>](#TsqlProcedure)  
  
###  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="f39b9-117">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="f39b9-117">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="f39b9-118">**So ändern Sie eine Prozedur in Management Studio**</span><span class="sxs-lookup"><span data-stu-id="f39b9-118">**To modify a procedure in Management Studio**</span></span>  
  
1.  <span data-ttu-id="f39b9-119">Stellen Sie im Objekt-Explorer eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="f39b9-119">In Object Explorer, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f39b9-120">Erweitern Sie **Datenbanken**, erweitern Sie die Datenbank, zu der die Prozedur gehört, und erweitern Sie dann **Programmierbarkeit**.</span><span class="sxs-lookup"><span data-stu-id="f39b9-120">Expand **Databases**, expand the database in which the procedure belongs, and then expand **Programmability**.</span></span>  
  
3.  <span data-ttu-id="f39b9-121">Erweitern Sie **Gespeicherte Prozeduren**, klicken Sie mit der rechten Maustaste auf die zu ändernde Prozedur, und klicken Sie dann auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="f39b9-121">Expand **Stored Procedures**, right-click the procedure to modify, and then click **Modify**.</span></span>  
  
4.  <span data-ttu-id="f39b9-122">Ändern Sie den Text der gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="f39b9-122">Modify the text of the stored procedure.</span></span>  
  
5.  <span data-ttu-id="f39b9-123">Zum Testen der Syntax klicken Sie im Menü **Abfrage** auf **Analysieren**.</span><span class="sxs-lookup"><span data-stu-id="f39b9-123">To test the syntax, on the **Query** menu, click **Parse**.</span></span>  
  
6.  <span data-ttu-id="f39b9-124">Um die Änderungen an der Prozedurdefinition zu speichern, klicken Sie im Menü **Abfrage** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f39b9-124">To save the modifications to the procedure definition, on the **Query** menu, click **Execute**.</span></span>  
  
7.  <span data-ttu-id="f39b9-125">Um die aktualisierte Prozedurdefinition als [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript zu speichern, klicken Sie im Menü **Datei** auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="f39b9-125">To save the updated procedure definition as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="f39b9-126">Nehmen Sie den Dateinamen an oder ersetzen Sie ihn durch einen neuen Namen, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f39b9-126">Accept the file name or replace it with a new name, and then click **Save**.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="f39b9-127">Überprüfen Sie alle Benutzereingaben.</span><span class="sxs-lookup"><span data-stu-id="f39b9-127">Validate all user input.</span></span> <span data-ttu-id="f39b9-128">Verketten Sie keine Benutzereingaben, bevor Sie sie überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="f39b9-128">Do not concatenate user input before you validate it.</span></span> <span data-ttu-id="f39b9-129">Führen Sie niemals Befehle aus, die sich aus nicht überprüften Benutzereingaben zusammensetzen.</span><span class="sxs-lookup"><span data-stu-id="f39b9-129">Never execute a command constructed from unvalidated user input.</span></span>  
  
###  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="f39b9-130">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="f39b9-130">Using Transact-SQL</span></span>  
 <span data-ttu-id="f39b9-131">**So ändern Sie eine Prozedur im Abfrage-Editor**</span><span class="sxs-lookup"><span data-stu-id="f39b9-131">**To modify a procedure in Query Editor**</span></span>  
  
1.  <span data-ttu-id="f39b9-132">Stellen Sie im **Objekt-Explorer**eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] her, und erweitern Sie dann diese Instanz.</span><span class="sxs-lookup"><span data-stu-id="f39b9-132">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)] and then expand that instance.</span></span>  
  
2.  <span data-ttu-id="f39b9-133">Erweitern Sie **Datenbanken**, und erweitern Sie die Datenbank, der die Prozedur angehört.</span><span class="sxs-lookup"><span data-stu-id="f39b9-133">Expand **Databases**, expand the database in which the procedure belongs.</span></span> <span data-ttu-id="f39b9-134">Oder wählen Sie die Datenbank über die Symbolleiste aus der Liste der verfügbaren Datenbanken aus.</span><span class="sxs-lookup"><span data-stu-id="f39b9-134">Or, from the tool bar, select the database from the list of available databases.</span></span> <span data-ttu-id="f39b9-135">Wählen Sie für dieses Beispiel die [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] -Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="f39b9-135">For this example, select the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
3.  <span data-ttu-id="f39b9-136">Klicken Sie im Menü **Datei** auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="f39b9-136">On the **File** menu, click **New Query**.</span></span>  
  
4.  <span data-ttu-id="f39b9-137">Kopieren Sie das folgenden Beispiel, und fügen Sie es in den Abfrage-Editor ein.</span><span class="sxs-lookup"><span data-stu-id="f39b9-137">Copy and paste the following example into the query editor.</span></span> <span data-ttu-id="f39b9-138">Im ersten Beispiel wird die `uspVendorAllInfo` -Prozedur erstellt. Diese Prozedur gibt die Namen, die gelieferten Produkte, die Bonität und die Verfügbarkeit aller Hersteller in der [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] -Datenbank, die das Unternehmen beliefern, zurück.</span><span class="sxs-lookup"><span data-stu-id="f39b9-138">The example creates the `uspVendorAllInfo` procedure, which returns the names of all the vendors in the [!INCLUDE[ssSampleDBCoFull](../../includes/sssampledbcofull-md.md)] database, the products they supply, their credit ratings, and their availability.</span></span>  
  
    ```  
  
    IF OBJECT_ID ( 'Purchasing.uspVendorAllInfo', 'P' ) IS NOT NULL   
        DROP PROCEDURE Purchasing.uspVendorAllInfo;  
    GO  
    CREATE PROCEDURE Purchasing.uspVendorAllInfo  
    WITH EXECUTE AS CALLER  
    AS  
        SET NOCOUNT ON;  
        SELECT v.Name AS Vendor, p.Name AS 'Product name',   
          v.CreditRating AS 'Rating',   
          v.ActiveFlag AS Availability  
        FROM Purchasing.Vendor v   
        INNER JOIN Purchasing.ProductVendor pv  
          ON v.BusinessEntityID = pv.BusinessEntityID   
        INNER JOIN Production.Product p  
          ON pv.ProductID = p.ProductID   
        ORDER BY v.Name ASC;  
    GO  
  
    ```  
  
5.  <span data-ttu-id="f39b9-139">Klicken Sie im Menü **Datei** auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="f39b9-139">On the **File** menu, click **New Query**.</span></span>  
  
6.  <span data-ttu-id="f39b9-140">Kopieren Sie das folgenden Beispiel, und fügen Sie es in den Abfrage-Editor ein.</span><span class="sxs-lookup"><span data-stu-id="f39b9-140">Copy and paste the following example into the query editor.</span></span> <span data-ttu-id="f39b9-141">Im Beispiel wird die `uspVendorAllInfo` -Prozedur geändert.</span><span class="sxs-lookup"><span data-stu-id="f39b9-141">The example modifies the `uspVendorAllInfo` procedure.</span></span> <span data-ttu-id="f39b9-142">Die EXECUTE AS CALLER-Klausel wird entfernt, und der Textkörper der Prozedur wird so geändert, dass nur Hersteller zurückgegeben werden, die das angegebene Produkt liefern.</span><span class="sxs-lookup"><span data-stu-id="f39b9-142">The EXECUTE AS CALLER clause is removed and the body of the procedure is modified to return only those vendors that supply the specified product.</span></span> <span data-ttu-id="f39b9-143">Mit den Funktionen `LEFT` und `CASE` wird die Darstellung des Resultsets angepasst.</span><span class="sxs-lookup"><span data-stu-id="f39b9-143">The `LEFT` and `CASE` functions customize the appearance of the result set.</span></span>  
  
    ```  
    ALTER PROCEDURE Purchasing.uspVendorAllInfo  
        @Product varchar(25)   
    AS  
        SET NOCOUNT ON;  
        SELECT LEFT(v.Name, 25) AS Vendor, LEFT(p.Name, 25) AS 'Product name',   
        'Rating' = CASE v.CreditRating   
            WHEN 1 THEN 'Superior'  
            WHEN 2 THEN 'Excellent'  
            WHEN 3 THEN 'Above average'  
            WHEN 4 THEN 'Average'  
            WHEN 5 THEN 'Below average'  
            ELSE 'No rating'  
            END  
        , Availability = CASE v.ActiveFlag  
            WHEN 1 THEN 'Yes'  
            ELSE 'No'  
            END  
        FROM Purchasing.Vendor AS v   
        INNER JOIN Purchasing.ProductVendor AS pv  
          ON v.BusinessEntityID = pv.BusinessEntityID   
        INNER JOIN Production.Product AS p   
          ON pv.ProductID = p.ProductID   
        WHERE p.Name LIKE @Product  
        ORDER BY v.Name ASC;  
    GO  
  
    ```  
  
7.  <span data-ttu-id="f39b9-144">Um die Änderungen an der Prozedurdefinition zu speichern, klicken Sie im Menü **Abfrage** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="f39b9-144">To save the modifications to the procedure definition, on the **Query** menu, click **Execute**.</span></span>  
  
8.  <span data-ttu-id="f39b9-145">Um die aktualisierte Prozedurdefinition als [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript zu speichern, klicken Sie im Menü **Datei** auf **Speichern unter**.</span><span class="sxs-lookup"><span data-stu-id="f39b9-145">To save the updated procedure definition as a [!INCLUDE[tsql](../../includes/tsql-md.md)] script, on the **File** menu, click **Save As**.</span></span> <span data-ttu-id="f39b9-146">Nehmen Sie den Dateinamen an oder ersetzen Sie ihn durch einen neuen Namen, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f39b9-146">Accept the file name or replace it with a new name, and then click **Save**.</span></span>  
  
9. <span data-ttu-id="f39b9-147">Um die geänderte gespeicherte Prozedur auszuführen, führen Sie das folgende Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="f39b9-147">To run the modified stored procedure, execute the following example.</span></span>  
  
    ```  
    EXEC Purchasing.uspVendorAllInfo N'LL Crankarm';  
    GO  
  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="f39b9-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f39b9-148">See Also</span></span>  
 [<span data-ttu-id="f39b9-149">ALTER PROCEDURE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f39b9-149">ALTER PROCEDURE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-procedure-transact-sql)  
  
  
