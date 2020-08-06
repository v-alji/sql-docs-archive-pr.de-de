---
title: Ausführen von benutzerdefinierten Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- invoking user-defined functions
- user-defined functions [SQL Server], executing
ms.assetid: 0de7744d-9b73-463f-ae80-e31a020004b5
author: rothja
ms.author: jroth
ms.openlocfilehash: 4446f3b3a132488fdac6e859f30abaca40a193d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630580"
---
# <a name="execute-user-defined-functions"></a><span data-ttu-id="66847-102">Ausführen von benutzerdefinierten Funktionen</span><span class="sxs-lookup"><span data-stu-id="66847-102">Execute User-defined Functions</span></span>
  <span data-ttu-id="66847-103">Sie können in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[tsql](../../includes/tsql-md.md)]eine benutzerdefinierte Funktion ausführen.</span><span class="sxs-lookup"><span data-stu-id="66847-103">You can execute a user defined function in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="66847-104">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="66847-104">**In This Topic**</span></span>  
  
-   <span data-ttu-id="66847-105">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="66847-105">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="66847-106">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="66847-106">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="66847-107">Security</span><span class="sxs-lookup"><span data-stu-id="66847-107">Security</span></span>](#Security)  
  
-   <span data-ttu-id="66847-108">**Ausführen einer benutzerdefinierten Funktion mit:**</span><span class="sxs-lookup"><span data-stu-id="66847-108">**To execute a user-defined function, using:**</span></span>  
  
     [<span data-ttu-id="66847-109">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="66847-109">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="66847-110">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="66847-110">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="66847-111">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="66847-111">Limitations and Restrictions</span></span>  
 <span data-ttu-id="66847-112">In Transact-SQL können Parameter entweder mit *value* oder mit dem Wert*parameter_name*=*value.* angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="66847-112">In Transact-SQL, parameters can be supplied either by using *value* or by using @*parameter_name*=*value.*</span></span> <span data-ttu-id="66847-113">angegeben werden. Ein Parameter ist nicht Teil einer Transaktion. Deshalb wird der Wert eines Parameters, der in einer Transaktion geändert wird, nicht wieder auf seinen ursprünglichen Wert zurückgesetzt, wenn für diese Transaktion später ein Rollback ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="66847-113">A parameter is not part of a transaction; therefore, if a parameter is changed in a transaction that is later rolled back, the value of the parameter does not revert to its previous value.</span></span> <span data-ttu-id="66847-114">Der Wert, der an den Aufrufer zurückgegeben wird, ist immer der Wert zu dem Zeitpunkt, zu dem das Modul beendet wird.</span><span class="sxs-lookup"><span data-stu-id="66847-114">The value returned to the caller is always the value at the time the module returns.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="66847-115">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="66847-115">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="66847-116">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="66847-116">Permissions</span></span>  
 <span data-ttu-id="66847-117">Zum Ausführen der EXECUTE-Anweisung sind keine Berechtigungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="66847-117">Permissions are not required to run the EXECUTE statement.</span></span> <span data-ttu-id="66847-118">Es sind jedoch Berechtigungen für die sicherungsfähigen Elemente erforderlich, auf die in der EXECUTE-Zeichenfolge verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="66847-118">However, permissions are required on the securables that are referenced within the EXECUTE string.</span></span> <span data-ttu-id="66847-119">Wenn z. B. die Zeichenfolge eine INSERT-Anweisung enthält, benötigt der Aufrufer der EXECUTE-Anweisung die INSERT-Berechtigung für die Zieltabelle.</span><span class="sxs-lookup"><span data-stu-id="66847-119">For example, if the string contains an INSERT statement, the caller of the EXECUTE statement must have INSERT permission on the target table.</span></span> <span data-ttu-id="66847-120">Berechtigungen werden überprüft, wenn die EXECUTE-Anweisung erreicht wird, selbst wenn die EXECUTE-Anweisung innerhalb eines Moduls enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="66847-120">Permissions are checked at the time EXECUTE statement is encountered, even if the EXECUTE statement is included within a module.</span></span> <span data-ttu-id="66847-121">Weitere Informationen finden Sie unter [Execute &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="66847-121">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql)</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="66847-122">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="66847-122">Using Transact-SQL</span></span>  
  
#### <a name="to-execute-a-user-defined-function"></a><span data-ttu-id="66847-123">So führen Sie eine benutzerdefinierte Funktion aus</span><span class="sxs-lookup"><span data-stu-id="66847-123">To execute a user-defined function</span></span>  
  
1.  <span data-ttu-id="66847-124">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="66847-124">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="66847-125">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="66847-125">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="66847-126">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="66847-126">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    USE AdventureWorks2012;  
    GO  
    -- Declares a variable and sets it to zero.  
    -- This variable is used to return the results of the function.  
    DECLARE @ret nvarchar(15)= NULL;   
  
    -- Executes the dbo.ufnGetSalesOrderStatusText function.  
    --The function requires a value for one parameter, @Status.   
    EXEC @ret = dbo.ufnGetSalesOrderStatusText @Status= 5;   
    --Returns the result in the message tab.  
    PRINT @ret;  
    ```  
  
 <span data-ttu-id="66847-127">Weitere Informationen finden Sie unter [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="66847-127">For more information, see [EXECUTE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/execute-transact-sql).</span></span>  
  
  
