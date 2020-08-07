---
title: Erstellen einer Tabelle (Tutorial) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- creating tables
ms.assetid: 653f2dd3-36a2-4bd5-8703-71a57d244661
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: c772f2527bd5ddb8a6759cbaa72d8aed9277f5cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619481"
---
# <a name="creating-a-table-tutorial"></a><span data-ttu-id="2d277-102">Erstellen einer Tabelle (Lernprogramm)</span><span class="sxs-lookup"><span data-stu-id="2d277-102">Creating a Table (Tutorial)</span></span>
  <span data-ttu-id="2d277-103">Zum Erstellen einer Tabelle müssen Sie einen Tabellennamen sowie die Namen und Datentypen jeder Spalte in der Tabelle angeben.</span><span class="sxs-lookup"><span data-stu-id="2d277-103">To create a table, you must provide a name for the table, and the names and data types of each column in the table.</span></span> <span data-ttu-id="2d277-104">Außerdem empfiehlt es sich, anzugeben, ob NULL-Werte in den einzelnen Spalten zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="2d277-104">It is also a good practice to indicate whether null values are allowed in each column.</span></span>  
  
 <span data-ttu-id="2d277-105">Die meisten Tabellen verfügen über einen Primärschlüssel, der sich aus einer oder mehreren Spalten der Tabelle zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="2d277-105">Most tables have a primary key, made up of one or more columns of the table.</span></span> <span data-ttu-id="2d277-106">Ein Primärschlüssel ist immer eindeutig.</span><span class="sxs-lookup"><span data-stu-id="2d277-106">A primary key is always unique.</span></span> <span data-ttu-id="2d277-107">[!INCLUDE[ssDE](../includes/ssde-md.md)] erzwingt die Einschränkung, dass ein Primärschlüsselwert in der Tabelle nicht wiederholt werden kann.</span><span class="sxs-lookup"><span data-stu-id="2d277-107">The [!INCLUDE[ssDE](../includes/ssde-md.md)] will enforce the restriction that any primary key value cannot be repeated in the table.</span></span>  
  
 <span data-ttu-id="2d277-108">Eine Liste der Datentypen sowie Links zu Beschreibungen der einzelnen Datentypen finden Sie unter [Datentypen &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="2d277-108">For a list of data types and links for a description of each, see [Data Types &#40;Transact-SQL&#41;](/sql/t-sql/data-types/data-types-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2d277-109">[!INCLUDE[ssDE](../includes/ssde-md.md)] kann mit oder ohne Beachtung der Groß-/Kleinschreibung installiert werden.</span><span class="sxs-lookup"><span data-stu-id="2d277-109">The [!INCLUDE[ssDE](../includes/ssde-md.md)] can be installed as case sensitive or non-case sensitive.</span></span> <span data-ttu-id="2d277-110">Wurde [!INCLUDE[ssDE](../includes/ssde-md.md)] so installiert, dass die Groß-/Kleinschreibung beachtet wird, müssen Objektnamen immer die gleiche Groß-/Kleinschreibung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="2d277-110">If the [!INCLUDE[ssDE](../includes/ssde-md.md)] is installed as case sensitive, object names must always have the same case.</span></span> <span data-ttu-id="2d277-111">Beispielsweise unterscheidet sich eine Tabelle namens OrderData von einer Tabelle namens ORDERDATA.</span><span class="sxs-lookup"><span data-stu-id="2d277-111">For example, a table named OrderData is a different table from a table named ORDERDATA.</span></span> <span data-ttu-id="2d277-112">Wurde [!INCLUDE[ssDE](../includes/ssde-md.md)] so installiert, dass die Groß-/Kleinschreibung nicht beachtet wird, bezeichnen diese beiden Tabellennamen die gleiche Tabelle, und der Name kann nur einmal verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d277-112">If the [!INCLUDE[ssDE](../includes/ssde-md.md)] is installed as non-case sensitive, those two table names are considered to be the same table, and that name can only be used one time.</span></span>  
  
### <a name="to-create-a-database-to-contain-the-new-table"></a><span data-ttu-id="2d277-113">So erstellen Sie eine Datenbank, die eine neue Tabelle enthält</span><span class="sxs-lookup"><span data-stu-id="2d277-113">To create a database to contain the new table</span></span>  
  
-   <span data-ttu-id="2d277-114">Geben Sie den folgenden Code in ein Abfrage-Editor-Fenster ein.</span><span class="sxs-lookup"><span data-stu-id="2d277-114">Enter the following code into a Query Editor window.</span></span>  
  
    ```  
    USE master;  
    GO  
  
    --Delete the TestData database if it exists.  
    IF EXISTS(SELECT * from sys.databases WHERE name='TestData')  
    BEGIN  
        DROP DATABASE TestData;  
    END  
  
    --Create a new database called TestData.  
    CREATE DATABASE TestData;  
    Press the F5 key to execute the code and create the database.  
    ```  
  
### <a name="switch-the-query-editor-connection-to-the-testdata-database"></a><span data-ttu-id="2d277-115">Ändern der Verbindung des Abfrage-Editors in die Datenbank TestData</span><span class="sxs-lookup"><span data-stu-id="2d277-115">Switch the Query Editor connection to the TestData database</span></span>  
  
-   <span data-ttu-id="2d277-116">Geben Sie in einem Abfrage-Editorfenster den folgenden Code ein, und führen Sie ihn aus, um die Verbindung in die `TestData` -Datenbank zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2d277-116">In a Query Editor window, type and execute the following code to change your connection to the `TestData` database.</span></span>  
  
    ```  
    USE TestData  
    GO  
    ```  
  
### <a name="to-create-a-table"></a><span data-ttu-id="2d277-117">So erstellen Sie eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="2d277-117">To create a table</span></span>  
  
-   <span data-ttu-id="2d277-118">Geben Sie in einem Abfrage-Editorfenster den folgenden Code ein, und führen Sie ihn aus, um eine einfache Tabelle namens `Products`zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2d277-118">In a Query Editor window, type and execute the following code to create a simple table named `Products`.</span></span> <span data-ttu-id="2d277-119">Die Spalten in der Tabelle heißen `ProductID`, `ProductName`, `Price`und `ProductDescription`.</span><span class="sxs-lookup"><span data-stu-id="2d277-119">The columns in the table are named `ProductID`, `ProductName`, `Price`, and `ProductDescription`.</span></span> <span data-ttu-id="2d277-120">Die `ProductID` -Spalte ist der Primärschlüssel der Tabelle.</span><span class="sxs-lookup"><span data-stu-id="2d277-120">The `ProductID` column is the primary key of the table.</span></span> <span data-ttu-id="2d277-121">`int`, `varchar(25)`, `money`und `text` sind Datentypen.</span><span class="sxs-lookup"><span data-stu-id="2d277-121">`int`, `varchar(25)`, `money`, and `text` are all data types.</span></span> <span data-ttu-id="2d277-122">Nur die Spalten `Price` und `ProductionDescription` dürfen keine Daten enthalten, wenn eine Zeile eingefügt oder geändert wird.</span><span class="sxs-lookup"><span data-stu-id="2d277-122">Only the `Price` and `ProductionDescription` columns can have no data when a row is inserted or changed.</span></span> <span data-ttu-id="2d277-123">Diese Anweisung enthält ein optionales Element (`dbo.`), das als Schema bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="2d277-123">This statement contains an optional element (`dbo.`) called a schema.</span></span> <span data-ttu-id="2d277-124">Das Schema ist das Datenbankobjekt, das die Tabelle besitzt.</span><span class="sxs-lookup"><span data-stu-id="2d277-124">The schema is the database object that owns the table.</span></span> <span data-ttu-id="2d277-125">Wenn Sie Administrator sind, ist `dbo` das Standardschema.</span><span class="sxs-lookup"><span data-stu-id="2d277-125">If you are an administrator, `dbo` is the default schema.</span></span> <span data-ttu-id="2d277-126">`dbo` steht für Datenbankbesitzer (database owner, dbo).</span><span class="sxs-lookup"><span data-stu-id="2d277-126">`dbo` stands for database owner.</span></span>  
  
    ```  
    CREATE TABLE dbo.Products  
       (ProductID int PRIMARY KEY NOT NULL,  
        ProductName varchar(25) NOT NULL,  
        Price money NULL,  
        ProductDescription text NULL)  
    GO  
    ```  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="2d277-127">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="2d277-127">Next Task in Lesson</span></span>  
 [<span data-ttu-id="2d277-128">Einfügen und Aktualisieren von Daten in einer Tabelle &#40;Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="2d277-128">Inserting and Updating Data in a Table &#40;Tutorial&#41;</span></span>](../t-sql/lesson-1-3-inserting-and-updating-data-in-a-table.md)  
  
## <a name="see-also"></a><span data-ttu-id="2d277-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d277-129">See Also</span></span>  
 [<span data-ttu-id="2d277-130">CREATE TABLE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2d277-130">CREATE TABLE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-table-transact-sql)  
  
  
