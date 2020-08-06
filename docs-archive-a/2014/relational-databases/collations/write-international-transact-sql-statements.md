---
title: Schreiben internationaler Transact-SQL-Anweisungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- writing international statements
- Transact-SQL international considerations
- international considerations [SQL Server], Transact-SQL
- Database Engine international considerations [SQL Server], Transact-SQL
- statements [SQL Server], international
- database international considerations [SQL Server], Transact-SQL
- dates [SQL Server], international considerations
ms.assetid: f0b10fee-27f7-45fe-aece-ccc3f63bdcdb
author: stevestein
ms.author: sstein
ms.openlocfilehash: 1888d1045e43e0a9839fd76a21c51500af63539a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622687"
---
# <a name="write-international-transact-sql-statements"></a><span data-ttu-id="99c9a-102">Schreiben internationaler Transact-SQL-Anweisungen</span><span class="sxs-lookup"><span data-stu-id="99c9a-102">Write International Transact-SQL Statements</span></span>
  <span data-ttu-id="99c9a-103">Datenbanken und Datenbankanwendungen, die [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen verwenden, können leichter von einer Sprache in eine andere übertragen werden bzw. unterstützen mehrere Sprachen, wenn die folgenden Richtlinien eingehalten werden:</span><span class="sxs-lookup"><span data-stu-id="99c9a-103">Databases and database applications that use [!INCLUDE[tsql](../../includes/tsql-md.md)] statements will become more portable from one language to another, or will support multiple languages, if the following guidelines are followed:</span></span>  
  
-   <span data-ttu-id="99c9a-104">Ersetzen Sie alle Vorkommen der Datentypen `char`, `varchar` und `text` durch `nchar`, `nvarchar` und `nvarchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="99c9a-104">Replace all uses of the `char`, `varchar`, and `text` data types with `nchar`, `nvarchar`, and `nvarchar(max)`.</span></span> <span data-ttu-id="99c9a-105">Auf diese Weise müssen Sie keine Schwierigkeiten mit der Codepagekonvertierung berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="99c9a-105">By doing this, you do not have to consider code page conversion issues.</span></span> <span data-ttu-id="99c9a-106">Weitere Informationen finden Sie unter [Collation and Unicode Support](collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="99c9a-106">For more information, see [Collation and Unicode Support](collation-and-unicode-support.md).</span></span>  
  
-   <span data-ttu-id="99c9a-107">Wenn Vergleiche und Vorgänge in bestimmten Monaten oder an bestimmten Arbeitstagen ausgeführt werden, verwenden Sie die numerischen Datumseinheiten anstelle der Namenszeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="99c9a-107">When you perform month and day-of-week comparisons and operations, use the numeric date parts instead of the name strings.</span></span> <span data-ttu-id="99c9a-108">Unterschiedliche Spracheinstellungen geben verschiedene Namen für Monate und Arbeitstage zurück.</span><span class="sxs-lookup"><span data-stu-id="99c9a-108">Different language settings return different names for the months and weekdays.</span></span> <span data-ttu-id="99c9a-109">Beispielsweise gibt DATENAME(MONTH,GETDATE()) den Monat May zurück, wenn die Sprache auf US- Englisch festgelegt ist, beim Festlegen der Sprache Deutsch wird Mai und beim Festlegen der Sprache Französisch mai zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="99c9a-109">For example, DATENAME(MONTH,GETDATE()) returns May when the language is set to U.S. English, returns Mai when the language is set to German, and returns mai when the language is set to French.</span></span> <span data-ttu-id="99c9a-110">Verwenden Sie stattdessen eine Funktion wie DATEPART, die die Monatszahl anstelle des Namens verwendet.</span><span class="sxs-lookup"><span data-stu-id="99c9a-110">Instead, use a function such as DATEPART that uses the number of the month instead of the name.</span></span> <span data-ttu-id="99c9a-111">Verwenden Sie DATEPART-Namen, wenn Sie Resultsets erstellen, die für einen Benutzer angezeigt werden sollen, da Datumsbezeichnungen häufig aussagekräftiger sind als eine numerische Darstellung.</span><span class="sxs-lookup"><span data-stu-id="99c9a-111">Use the DATEPART names when you build result sets to be displayed to a user, because the date names are frequently more meaningful than a numeric representation.</span></span> <span data-ttu-id="99c9a-112">Kopieren Sie jedoch keine logischen Befehle, die davon abhängen, dass die angezeigten Namen aus einer bestimmten Sprache stammen.</span><span class="sxs-lookup"><span data-stu-id="99c9a-112">However, do not code any logic that depends on the displayed names being from a specific language.</span></span>  
  
-   <span data-ttu-id="99c9a-113">Wenn Sie Datumseingaben in Vergleichen oder als Eingabe in INSERT- oder UPDATE-Anweisungen angeben, verwenden Sie Konstanten, die in allen Spracheinstellungen gleich interpretiert werden:</span><span class="sxs-lookup"><span data-stu-id="99c9a-113">When you specify dates in comparisons or for input to INSERT or UPDATE statements, use constants that are interpreted the same way for all language settings:</span></span>  
  
    -   <span data-ttu-id="99c9a-114">ADO-, OLE DB- und ODBC-Anwendungen sollten folgende ODBC-Timestamps und folgende ESCAPE-Klauseln für Datum und Zeit verwenden:</span><span class="sxs-lookup"><span data-stu-id="99c9a-114">ADO, OLE DB, and ODBC applications should use the ODBC timestamp, date, and time escape clauses of:</span></span>  
  
         <span data-ttu-id="99c9a-115">**{TS '** JJJJ **-** _mm_ **-** _DDHH_**:**_mm_**:**_SS_[**.** _fff_] **'}** Beispiel: **{TS '** 1998 **-** 09 **-** 24 10 **:** 02 **:** 20 **'}**</span><span class="sxs-lookup"><span data-stu-id="99c9a-115">**{ ts'** yyyy**-**_mm_**-**_ddhh_**:**_mm_**:**_ss_[**.**_fff_] **'}** such as: **{ ts'** 1998**-** 09**-** 24 10 **:** 02 **:** 20 **' }**</span></span>  
  
         <span data-ttu-id="99c9a-116">**{ d'** _yyyy_ **-** _mm_ **-** _dd_ **'}** Beispiel: **{ d'** 1998**-** 09**-** 24 **'}**</span><span class="sxs-lookup"><span data-stu-id="99c9a-116">**{ d'** _yyyy_ **-** _mm_ **-** _dd_ **'}** such as: **{ d'** 1998**-** 09**-** 24 **'}**</span></span>  
  
         <span data-ttu-id="99c9a-117">**{t '** _HH_ **:** _mm_ **:** _SS_ **'}** Beispiel: **{t '** 10:02:20 **'}**</span><span class="sxs-lookup"><span data-stu-id="99c9a-117">**{ t'** _hh_ **:** _mm_ **:** _ss_ **'}** such as: **{ t'** 10:02:20 **'}**</span></span>  
  
    -   <span data-ttu-id="99c9a-118">Anwendungen, die andere APIs verwenden, oder [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skripts, gespeicherte Prozedure und Trigger sollten unstrukturierte Zeichenfolgen verwenden.</span><span class="sxs-lookup"><span data-stu-id="99c9a-118">Applications that use other APIs, or [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, stored procedures, and triggers, should use the unseparated numeric strings.</span></span> <span data-ttu-id="99c9a-119">Zum Beispiel *yyyymmdd* für 19980924.</span><span class="sxs-lookup"><span data-stu-id="99c9a-119">For example, *yyyymmdd* as 19980924.</span></span>  
  
    -   <span data-ttu-id="99c9a-120">Anwendungen, die andere APIs oder [!INCLUDE[tsql](../../includes/tsql-md.md)] Skripts, gespeicherte Prozeduren und Trigger verwenden, sollten die Convert-Anweisung mit einem expliziten Formatvorlagen Parameter für alle Konvertierungen zwischen den Daten `time` `date` Typen,,, `smalldate` `datetime` , **datetime2**und `datetimeoffset` Datentypen und Zeichen folgen-Datentypen verwenden.</span><span class="sxs-lookup"><span data-stu-id="99c9a-120">Applications that use other APIs, or [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts, stored procedures, and triggers should use the CONVERT statement with an explicit style parameter for all conversions between the `time`, `date`, `smalldate`, `datetime`, **datetime2**, and `datetimeoffset` data types and character string data types.</span></span> <span data-ttu-id="99c9a-121">Die folgende Anweisung wird beispielsweise für alle Verbindungseinstellungen für Sprach- oder Datumsformate gleich interpretiert:</span><span class="sxs-lookup"><span data-stu-id="99c9a-121">For example, the following statement is interpreted in the same way for all language or date format connection settings:</span></span>  
  
        ```  
        SELECT *  
        FROM AdventureWorks2012.Sales.SalesOrderHeader  
        WHERE OrderDate = CONVERT(DATETIME, '20060719', 101)  
        ```  
  
         <span data-ttu-id="99c9a-122">Weitere Informationen finden Sie unter [CAST und CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="99c9a-122">For more information, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
  
