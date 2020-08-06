---
title: Bindungs Parameter | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, parameters
- parameters [SQL Server Native Client], ODBC
- statements [ODBC], parameters
- binding parameters [SQL Server Native Client]
- parameter markers [ODBC]
- unbound parameter markers
- SQLBindParameter function
- ODBC applications, parameters
- bound parameter markers [SQL Server Native Client]
ms.assetid: d6c69739-8f89-475f-a60a-b2f6c06576e2
author: rothja
ms.author: jroth
ms.openlocfilehash: 3402a7efce43d0ce94a20c93504ac1dcb2c7b48f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608600"
---
# <a name="binding-parameters"></a><span data-ttu-id="3ec89-102">Binden von Parametern</span><span class="sxs-lookup"><span data-stu-id="3ec89-102">Binding Parameters</span></span>
  <span data-ttu-id="3ec89-103">Jede Parametermarkierung in einer SQL-Anweisung muss mit einer Variablen in der Anwendung verknüpft oder an diese gebunden werden, bevor die Anweisung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3ec89-103">Each parameter marker in an SQL statement must be associated, or bound, to a variable in the application before the statement can be executed.</span></span> <span data-ttu-id="3ec89-104">Dies erfolgt durch Aufrufen der [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) -Funktion.</span><span class="sxs-lookup"><span data-stu-id="3ec89-104">This is done by calling the [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) function.</span></span> <span data-ttu-id="3ec89-105">**SQLBindParameter** beschreibt die Programm Variable (Adresse, C-Datentyp usw.) für den Treiber.</span><span class="sxs-lookup"><span data-stu-id="3ec89-105">**SQLBindParameter** describes the program variable (address, C data type, and so on) to the driver.</span></span> <span data-ttu-id="3ec89-106">Ferner identifiziert sie die Parametermarkierung durch Angabe ihres Ordinalwerts und beschreibt anschließend die Eigenschaften des SQL-Objekts, das sie darstellt (SQL-Datentyp, Genauigkeit usw.).</span><span class="sxs-lookup"><span data-stu-id="3ec89-106">It also identifies the parameter marker by indicating its ordinal value and then describes the characteristics of the SQL object it represents (SQL data type, precision, and so on).</span></span>

 <span data-ttu-id="3ec89-107">Parametermarkierungen können vor der Ausführung einer Anweisung jederzeit gebunden bzw. neu gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="3ec89-107">Parameter markers can be bound or rebound at any time before a statement is executed.</span></span> <span data-ttu-id="3ec89-108">Eine Parameterbindung bleibt wirksam, bis eines der folgenden Ereignisse eintritt:</span><span class="sxs-lookup"><span data-stu-id="3ec89-108">A parameter binding remains in effect until one of the following occurs:</span></span>

-   <span data-ttu-id="3ec89-109">Ein [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) -Befehl, bei dem der *Option* -Parameter auf festgelegt ist SQL_RESET_PARAMS gibt alle an das Anweisungs Handle gebundenen Parameter frei.</span><span class="sxs-lookup"><span data-stu-id="3ec89-109">A call to [SQLFreeStmt](../native-client-odbc-api/sqlfreestmt.md) with the *Option* parameter set to SQL_RESET_PARAMS frees all parameters bound to the statement handle.</span></span>

-   <span data-ttu-id="3ec89-110">Ein **SQLBindParameter** -Befehl, bei dem *ParameterNumber* auf die Ordinalzahl eines gebundenen Parameter Markers festgelegt ist, gibt automatisch die vorherige Bindung frei.</span><span class="sxs-lookup"><span data-stu-id="3ec89-110">A call to **SQLBindParameter** with *ParameterNumber* set to the ordinal of a bound parameter marker automatically releases the previous binding.</span></span>

 <span data-ttu-id="3ec89-111">Eine Anwendung kann ferner Parameter an Arrays von Programmvariablen binden, um eine SQL-Anweisung batchweise zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="3ec89-111">An application can also bind parameters to arrays of program variables to process an SQL statement in batches.</span></span> <span data-ttu-id="3ec89-112">Es gibt zwei Arten der Arraybindung:</span><span class="sxs-lookup"><span data-stu-id="3ec89-112">There are two types of array binding:</span></span>

-   <span data-ttu-id="3ec89-113">Die spaltenweise Bindung ist fertig gestellt, wenn jeder einzelne Parameter an sein eigenes Array von Variablen gebunden wurde.</span><span class="sxs-lookup"><span data-stu-id="3ec89-113">Column-wise binding is done when each individual parameter is bound to its own array of variables.</span></span>

     <span data-ttu-id="3ec89-114">Die spaltenweise Bindung wird angegeben, indem [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) aufgerufen wird, wobei *Attribute* auf SQL_ATTR_PARAM_BIND_TYPE und *ValuePtr* auf SQL_PARAM_BIND_BY_COLUMN festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3ec89-114">Column-wise binding is specified by calling [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) with *Attribute* set to SQL_ATTR_PARAM_BIND_TYPE and *ValuePtr* set to SQL_PARAM_BIND_BY_COLUMN.</span></span>

-   <span data-ttu-id="3ec89-115">Die zeilenweise Beendung ist fertig gestellt, wenn alle Parameter in der SQL-Anweisung als Einheit an ein Array von Strukturen gebunden wurden, die die einzelnen Variablen für die Parameter enthalten.</span><span class="sxs-lookup"><span data-stu-id="3ec89-115">Row-wise binding is done when all of the parameters in the SQL statement are bound as a unit to an array of structures that contain the individual variables for the parameters.</span></span>

     <span data-ttu-id="3ec89-116">Die zeilenweise Bindung wird angegeben, indem **SQLSetStmtAttr** aufgerufen wird, wobei *Attribute* auf SQL_ATTR_PARAM_BIND_TYPE festgelegt ist und *ValuePtr* auf die Größe der Struktur festgelegt ist, die die Programmvariablen enthält.</span><span class="sxs-lookup"><span data-stu-id="3ec89-116">Row-wise binding is specified by calling **SQLSetStmtAttr** with *Attribute* set to SQL_ATTR_PARAM_BIND_TYPE and *ValuePtr* set to the size of the structure holding the program variables.</span></span>

 <span data-ttu-id="3ec89-117">Wenn der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber Zeichen-oder Binär Zeichenfolgen-Parameter an den Server sendet, werden die Werte in die im **SQLBindParameter** *ColumnSize* -Parameter angegebene Länge aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="3ec89-117">When the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver sends character or binary string parameters to the server, it pads the values to the length specified in **SQLBindParameter** *ColumnSize* parameter.</span></span> <span data-ttu-id="3ec89-118">Wenn eine ODBC 2. x-Anwendung 0 für *ColumnSize*angibt, füllt der Treiber den Parameterwert auf die Genauigkeit des Datentyps auf.</span><span class="sxs-lookup"><span data-stu-id="3ec89-118">If an ODBC 2.x application specifies 0 for *ColumnSize*, the driver pads the parameter value to the precision of the data type.</span></span> <span data-ttu-id="3ec89-119">Die Genauigkeit beträgt bei einer Verbindung zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 8000, bei einer Verbindung zu älteren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] 255.</span><span class="sxs-lookup"><span data-stu-id="3ec89-119">The precision is 8000 when connected to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servers, 255 when connected to earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="3ec89-120">*ColumnSize* ist für Variant-Spalten in Bytes.</span><span class="sxs-lookup"><span data-stu-id="3ec89-120">*ColumnSize* is in bytes for variant columns.</span></span>

 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="3ec89-121">unterstützt definierende Namen für gespeicherte Prozedurparameter.</span><span class="sxs-lookup"><span data-stu-id="3ec89-121">supports defining names for stored procedure parameters.</span></span> <span data-ttu-id="3ec89-122">ODBC 3.5 hat ebenfalls Unterstützung für benannte Parameter eingeführt, die verwendet werden, wenn in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] gespeicherte Prozeduren aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="3ec89-122">ODBC 3.5 also introduced support for named parameters used when calling [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures.</span></span> <span data-ttu-id="3ec89-123">Diese Unterstützung kann für Folgendes verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="3ec89-123">This support can be used to:</span></span>

-   <span data-ttu-id="3ec89-124">Zum Aufrufen einer gespeicherten Prozedur und Eingeben von Werten für eine Teilmenge der für die gespeicherte Prozedur definierten Parameter</span><span class="sxs-lookup"><span data-stu-id="3ec89-124">Call a stored procedure and provide values for a subset of the parameters defined for the stored procedure.</span></span>

-   <span data-ttu-id="3ec89-125">Zum Angeben der Parameter in einer anderen Reihenfolge in der Anwendung als in der Reihenfolge, in der sie bei der Erstellung der gespeicherten Prozedur angegeben wurden</span><span class="sxs-lookup"><span data-stu-id="3ec89-125">Specify the parameters in a different order in the application than the order specified when the stored procedure was created.</span></span>

 <span data-ttu-id="3ec89-126">Benannte Parameter werden nur unterstützt, wenn die- [!INCLUDE[tsql](../../includes/tsql-md.md)] `EXECUTE` Anweisung oder die ODBC-Rückruf-Escapesequenz zum Ausführen einer gespeicherten Prozedur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3ec89-126">Named parameters are only supported when using the [!INCLUDE[tsql](../../includes/tsql-md.md)] `EXECUTE` statement or the ODBC CALL escape sequence to execute a stored procedure.</span></span>

 <span data-ttu-id="3ec89-127">Wenn `SQL_DESC_NAME` für einen gespeicherten Prozedurparameter festgelegt wird, sollten alle gespeicherten Prozedurparameter in der Abfrage ebenfalls `SQL_DESC_NAME` festlegen.</span><span class="sxs-lookup"><span data-stu-id="3ec89-127">If `SQL_DESC_NAME` is set for a stored procedure parameter, all stored procedure parameters in the query should also set `SQL_DESC_NAME`.</span></span>  <span data-ttu-id="3ec89-128">Wenn Literale in Aufrufen gespeicherter Prozeduren verwendet werden, `SQL_DESC_NAME` für die Parameter festgelegt wurden, sollten die Literale das Format *' Name* = *value*' verwenden, wobei *Name* der Parameter Name der gespeicherten Prozedur (z @p1 . b.) ist.</span><span class="sxs-lookup"><span data-stu-id="3ec89-128">If literals are used in stored procedure calls, where parameters have `SQL_DESC_NAME` set, the literals should use the format *'name*=*value*', where *name* is the stored procedure parameter name (for example, @p1).</span></span> <span data-ttu-id="3ec89-129">Weitere Informationen finden Sie unter [Binden von Parametern anhand des Namens (benannte Parameter)](https://go.microsoft.com/fwlink/?LinkId=167215).</span><span class="sxs-lookup"><span data-stu-id="3ec89-129">For more information, see [Binding Parameters by Name (Named Parameters)](https://go.microsoft.com/fwlink/?LinkId=167215).</span></span>

## <a name="see-also"></a><span data-ttu-id="3ec89-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ec89-130">See Also</span></span>
 [<span data-ttu-id="3ec89-131">Verwenden von Anweisungsparametern</span><span class="sxs-lookup"><span data-stu-id="3ec89-131">Using Statement Parameters</span></span>](using-statement-parameters.md)


