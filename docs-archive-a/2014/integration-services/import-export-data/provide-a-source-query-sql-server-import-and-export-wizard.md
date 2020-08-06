---
title: Angeben einer Quellabfrage (SQL Server-Import/Export-Assistent) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.impexpwizard.providesourcequery.f1
ms.assetid: c8cbd07e-b9c3-422f-94b8-d6fc8cf31cf5
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b21100f51c279e9ba764c8f82565af9d6e391ef3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619924"
---
# <a name="provide-a-source-query-sql-server-import-and-export-wizard"></a><span data-ttu-id="b5ae2-102">Quellabfrage angeben (SQL Server-Import/Export-Assistent)</span><span class="sxs-lookup"><span data-stu-id="b5ae2-102">Provide a Source Query (SQL Server Import and Export Wizard)</span></span>
  <span data-ttu-id="b5ae2-103">Verwenden Sie die Seite **Quell Abfrage angeben** , um die SQL-Anweisung einzugeben, mit der die Daten generiert werden, die aus der Datenquelle in das Ziel kopiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b5ae2-103">Use the **Provide a Source Query** page to type the SQL statement that will generate the data to copy from the data source to the destination.</span></span>  
  
 <span data-ttu-id="b5ae2-104">Weitere Informationen zu diesem Assistenten finden Sie unter [SQL Server-Import/Export-Assistenten](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="b5ae2-104">To learn more about this wizard, see [SQL Server Import and Export Wizard](import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span> <span data-ttu-id="b5ae2-105">Weitere Informationen zu den Optionen für das Starten des Assistenten sowie zu den Berechtigungen, die zum erfolgreichen Ausführen des Assistenten erforderlich sind, finden Sie unter [Ausführen des SQL Server-Import/Export-Assistenten](start-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="b5ae2-105">To learn about the options for starting the wizard, as well as the permissions required to run the wizard successfully, see [Run the SQL Server Import and Export Wizard](start-the-sql-server-import-and-export-wizard.md).</span></span>  
  
 <span data-ttu-id="b5ae2-106">Mit dem SQL Server-Import/Export-Assistenten werden Daten aus einer Quelle in ein Ziel kopiert.</span><span class="sxs-lookup"><span data-stu-id="b5ae2-106">The purpose of the SQL Server Import and Export Wizard is to copy data from a source to a destination.</span></span> <span data-ttu-id="b5ae2-107">Mit dem Assistenten können auch eine Zieldatenbank und Zieltabellen erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="b5ae2-107">The wizard can also create a destination database and destination tables for you.</span></span> <span data-ttu-id="b5ae2-108">Wenn Sie jedoch mehrere Datenbanken, Tabellen oder andere Datenbankobjekte kopieren müssen, verwenden Sie stattdessen den Assistenten zum Kopieren von Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="b5ae2-108">However, if you have to copy multiple databases or tables, or other kinds of database objects, you should use the Copy Database Wizard instead.</span></span> <span data-ttu-id="b5ae2-109">Weitere Informationen finden Sie unter [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="b5ae2-109">For more information, see [Use the Copy Database Wizard](../../relational-databases/databases/use-the-copy-database-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="b5ae2-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="b5ae2-110">Options</span></span>  
 <span data-ttu-id="b5ae2-111">**SQL-Anweisung**</span><span class="sxs-lookup"><span data-stu-id="b5ae2-111">**SQL statement**</span></span>  
 <span data-ttu-id="b5ae2-112">Geben Sie eine Abfrageanweisung ein, um die ausgewählten Datenzeilen aus der Quelldatenbank abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b5ae2-112">Type a query statement to retrieve selected rows of data from the source database.</span></span> <span data-ttu-id="b5ae2-113">Die folgende Abfrageanweisung ruft z. B. die Daten **SalesPersonID**, **SalesQuota**und **SalesYTD** aus der AdventureWorks-Datenbank für Verkäufer ab, deren Kommissionsanteil größer als 1.5 Prozent ist.</span><span class="sxs-lookup"><span data-stu-id="b5ae2-113">For example, the following query statement retrieves the **SalesPersonID**, **SalesQuota**, and **SalesYTD** from the AdventureWorks database for sales persons whose commission percentage is more than 1.5 percent.</span></span>  
  
```  
SELECT SalesPersonID, SalesQuota, SalesYTD  
FROM Sales.SalesPerson  
WHERE CommissionPct > 0.015  
```  
  
 <span data-ttu-id="b5ae2-114">**Parse**</span><span class="sxs-lookup"><span data-stu-id="b5ae2-114">**Parse**</span></span>  
 <span data-ttu-id="b5ae2-115">Überprüft die Syntax der SQL-Anweisung im Textfeld **SQL-Anweisung**.</span><span class="sxs-lookup"><span data-stu-id="b5ae2-115">Checks the syntax of the SQL statement in the **SQL statement** text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b5ae2-116">Wenn die für die Prüfung der Anweisungssyntax erforderliche Zeit den Timeoutwert von 30 Sekunden überschreitet, wird die Analyse beendet und ein Fehler ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="b5ae2-116">If the time that is required to check the syntax of the statement exceeds the time-out value of 30 seconds, parsing stops and generates an error.</span></span> <span data-ttu-id="b5ae2-117">Sie können erst nach erfolgreicher Analyse über diese Seite des Assistenten hinaus gelangen.</span><span class="sxs-lookup"><span data-stu-id="b5ae2-117">You will not be able to move past this page of the wizard until parsing succeeds.</span></span> <span data-ttu-id="b5ae2-118">Eine Lösung besteht darin, eine Datenbanksicht basierend auf der Abfrage zu erstellen und die Sicht vom Assistenten abzufragen, statt den Abfragetext direkt einzugeben.</span><span class="sxs-lookup"><span data-stu-id="b5ae2-118">One solution is to create a database view based on the query, and to query the view from the wizard, instead of entering the query text directly.</span></span>  
  
 <span data-ttu-id="b5ae2-119">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="b5ae2-119">**Browse**</span></span>  
 <span data-ttu-id="b5ae2-120">Wählen Sie mithilfe des Dialog Felds **Öffnen** eine Datei aus, die eine SQL-Anweisung enthält.</span><span class="sxs-lookup"><span data-stu-id="b5ae2-120">Select a file containing a SQL statement by using the **Open** dialog box.</span></span> <span data-ttu-id="b5ae2-121">Durch das Auswählen einer Datei wird der Test aus der Datei in das Textfeld **Abfrageanweisung** kopiert.</span><span class="sxs-lookup"><span data-stu-id="b5ae2-121">Selecting a file copies the text from the file into the **Query statement** text box.</span></span>  
  
  
