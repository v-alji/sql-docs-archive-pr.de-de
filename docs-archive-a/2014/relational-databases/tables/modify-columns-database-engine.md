---
title: Ändern von Spalten (Datenbank-Engine) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: table-view-index
ms.topic: conceptual
helpviewer_keywords:
- modifying data types
- column data types [SQL Server]
- data types [SQL Server], columns
ms.assetid: b67b95c5-61ef-4bd8-9a3e-1640eb7583ac
author: stevestein
ms.author: sstein
ms.openlocfilehash: a73c25d91b742f1cc1f7edcc8a95cdf226b2683c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619030"
---
# <a name="modify-columns-database-engine"></a><span data-ttu-id="094b6-102">Ändern von Spalten (Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="094b6-102">Modify Columns (Database Engine)</span></span>
  <span data-ttu-id="094b6-103">Sie können den Datentyp einer Spalte in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder [!INCLUDE[tsql](../../includes/tsql-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="094b6-103">You can modify the data type of a column in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="094b6-104">Das Ändern des Datentyps einer Spalte, die bereits Daten enthält, kann zu einem dauerhaften Datenverlust führen, wenn die vorhandenen Daten in den neuen Typ konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="094b6-104">Modifying the data type of a column that already contains data can result in the permanent loss of data when the existing data is converted to the new type.</span></span> <span data-ttu-id="094b6-105">Außerdem können Code und Anwendungen, die von der geänderten Spalte abhängen, womöglich nicht mehr ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="094b6-105">In addition, code and applications that depend on the modified column may fail.</span></span> <span data-ttu-id="094b6-106">Dies schließt Abfragen, Sichten, gespeicherte Prozeduren, benutzerdefinierte Funktionen und Clientanwendungen ein.</span><span class="sxs-lookup"><span data-stu-id="094b6-106">These include queries, views, stored procedures, user-defined functions, and client applications.</span></span> <span data-ttu-id="094b6-107">Beachten Sie, dass dabei ein Fehler durch Verkettung weitere Fehler nach sich ziehen kann.</span><span class="sxs-lookup"><span data-stu-id="094b6-107">Note that these failures will cascade.</span></span> <span data-ttu-id="094b6-108">Beispielsweise kann eine gespeicherte Prozedur, die eine von der geänderten Spalte abhängige benutzerdefinierte Funktion aufruft, möglicherweise nicht mehr ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="094b6-108">For example, a stored procedure that calls a user-defined function that depends on the modified column may fail.</span></span> <span data-ttu-id="094b6-109">Bedenken Sie sorgfältig die Konsequenzen, bevor Sie Änderungen an einer Spalte vornehmen.</span><span class="sxs-lookup"><span data-stu-id="094b6-109">Carefully consider any changes you want to make to a column before making it.</span></span>  
  
 <span data-ttu-id="094b6-110">**In diesem Thema**</span><span class="sxs-lookup"><span data-stu-id="094b6-110">**In This Topic**</span></span>  
  
-   <span data-ttu-id="094b6-111">**Vorbereitungen:**</span><span class="sxs-lookup"><span data-stu-id="094b6-111">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="094b6-112">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="094b6-112">Security</span></span>](#Security)  
  
-   <span data-ttu-id="094b6-113">**So ändern Sie den Datentyp einer Spalte mit:**</span><span class="sxs-lookup"><span data-stu-id="094b6-113">**To modify the data type of a column, using:**</span></span>  
  
     [<span data-ttu-id="094b6-114">SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="094b6-114">SQL Server Management Studio</span></span>](#SSMSProcedure)  
  
     [<span data-ttu-id="094b6-115">Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="094b6-115">Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="094b6-116">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="094b6-116">Before You Begin</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="094b6-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="094b6-117">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="094b6-118">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="094b6-118">Permissions</span></span>  
 <span data-ttu-id="094b6-119">Erfordert die ALTER-Berechtigung für die Tabelle.</span><span class="sxs-lookup"><span data-stu-id="094b6-119">Requires ALTER permission on the table.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="094b6-120">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="094b6-120">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-modify-the-data-type-of-a-column"></a><span data-ttu-id="094b6-121">So ändern Sie den Datentyp einer Spalte</span><span class="sxs-lookup"><span data-stu-id="094b6-121">To modify the data type of a column</span></span>  
  
1.  <span data-ttu-id="094b6-122">Klicken Sie im **Objekt-Explorer**mit der rechten Maustaste auf die Tabelle mit den Spalten, für die Sie Dezimalstellen ändern möchten, und klicken Sie auf **Entwerfen**.</span><span class="sxs-lookup"><span data-stu-id="094b6-122">In **Object Explorer**, right-click the table with columns for which you want to change the scale and click **Design**.</span></span>  
  
2.  <span data-ttu-id="094b6-123">Wählen Sie die Spalte aus, deren Datentyp Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="094b6-123">Select the column for which you want to modify the data type.</span></span>  
  
3.  <span data-ttu-id="094b6-124">Klicken Sie auf der Registerkarte **Spalteneigenschaften** auf die Datenblattzelle der Eigenschaft **Datentyp** , und wählen Sie aus der Dropdownliste einen neuen Datentyp aus.</span><span class="sxs-lookup"><span data-stu-id="094b6-124">In the **Column Properties** tab, click the grid cell for the **Data Type** property and choose a new data type from the drop-down list.</span></span>  
  
4.  <span data-ttu-id="094b6-125">Klicken Sie im Menü **Datei** auf _Tabellenname_**speichern**.</span><span class="sxs-lookup"><span data-stu-id="094b6-125">On the **File** menu, click **Save**_table name_.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="094b6-126">Wenn Sie den Datentyp einer Spalte ändern, wendet der Tabellen-Designer die Standardlänge des neuen Datentyps an, auch wenn Sie zuvor eine andere Länge angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="094b6-126">When you modify the data type of a column, Table Designer applies the default length of the data type you selected, even if you have already specified another.</span></span> <span data-ttu-id="094b6-127">Legen Sie deshalb die Datentyplänge erst nach dem Ändern des Datentyps fest.</span><span class="sxs-lookup"><span data-stu-id="094b6-127">Always set the data type length for to the desired value after specifying the data type.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="094b6-128">Wenn Sie versuchen, den Datentyp einer Spalte zu ändern, die sich auf andere Tabellen bezieht, fordert Tabellen-Designer Sie auf zu bestätigen, dass die Änderung auch an den Spalten in den anderen Tabellen vorgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="094b6-128">If you attempt to modify the data type of a column that relates to other tables, Table Designer asks you to confirm that the change should be made to the columns in the other tables as well.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="094b6-129">Verwenden von Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="094b6-129">Using Transact-SQL</span></span>  
  
#### <a name="to-modify-the-data-type-of-a-column"></a><span data-ttu-id="094b6-130">So ändern Sie den Datentyp einer Spalte</span><span class="sxs-lookup"><span data-stu-id="094b6-130">To modify the data type of a column</span></span>  
  
1.  <span data-ttu-id="094b6-131">Stellen Sie im **Objekt-Explorer** eine Verbindung mit einer [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Instanz her.</span><span class="sxs-lookup"><span data-stu-id="094b6-131">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
2.  <span data-ttu-id="094b6-132">Klicken Sie in der Standardleiste auf **Neue Abfrage**.</span><span class="sxs-lookup"><span data-stu-id="094b6-132">On the Standard bar, click **New Query**.</span></span>  
  
3.  <span data-ttu-id="094b6-133">Kopieren Sie das folgende Beispiel, fügen Sie es in das Abfragefenster ein, und klicken Sie auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="094b6-133">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    CREATE TABLE dbo.doc_exy (column_a INT ) ;  
    GO  
    INSERT INTO dbo.doc_exy (column_a) VALUES (10) ;  
    GO  
    ALTER TABLE dbo.doc_exy ALTER COLUMN column_a DECIMAL (5, 2) ;  
    GO  
  
    ```  
  
 <span data-ttu-id="094b6-134">Weitere Informationen finden Sie unter [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="094b6-134">For more information, see [ALTER TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-table-transact-sql)</span></span>  
  
  
