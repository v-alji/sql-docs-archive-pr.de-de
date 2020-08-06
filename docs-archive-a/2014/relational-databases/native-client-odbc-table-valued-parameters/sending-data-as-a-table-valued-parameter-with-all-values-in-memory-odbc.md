---
title: Senden von Daten als Tabellenwert Parameter mit allen Werten im Arbeitsspeicher (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- table-valued parameters (ODBC), sending data to a stored procedure with all values in memory
ms.assetid: 8b96282f-00d5-4e28-8111-0a87ae6d7781
author: rothja
ms.author: jroth
ms.openlocfilehash: f53e129ea49b1faa08be5247c51b5e74353e2f31
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724578"
---
# <a name="sending-data-as-a-table-valued-parameter-with-all-values-in-memory-odbc"></a><span data-ttu-id="56d4a-102">Senden von Daten als Tabellenwertparameter mit allen Werten im Arbeitsspeicher (ODBC)</span><span class="sxs-lookup"><span data-stu-id="56d4a-102">Sending Data as a Table-Valued Parameter with All Values in Memory (ODBC)</span></span>
  <span data-ttu-id="56d4a-103">In diesem Thema wird beschrieben, wie Daten als Tabellenwertparameter an eine gespeicherte Prozedur gesendet werden, wenn alle Werte im Speicher abgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="56d4a-103">This topic describes how to send data to a stored procedure as a table-valued parameter when all values are in memory.</span></span> <span data-ttu-id="56d4a-104">Ein weiteres Beispiel zur Veranschaulichung von Tabellenwert Parametern finden Sie unter [Verwenden von Tabellenwert Parametern &#40;ODBC-&#41;](table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="56d4a-104">For another sample demonstrating table-valued parameters, see [Use Table-Valued Parameters &#40;ODBC&#41;](table-valued-parameters-odbc.md).</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="56d4a-105">Voraussetzung</span><span class="sxs-lookup"><span data-stu-id="56d4a-105">Prerequisite</span></span>  
 <span data-ttu-id="56d4a-106">In dieser Prozedur wird davon ausgegangen, dass der folgende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Befehl auf dem Server ausgeführt wurde:</span><span class="sxs-lookup"><span data-stu-id="56d4a-106">This procedure assumes that the following [!INCLUDE[tsql](../../includes/tsql-md.md)] has been executed on the server:</span></span>  
  
```  
create type TVParam as table(ProdCode integer, Qty integer)  
create procedure TVPOrderEntry(@CustCode varchar(5), @Items TVPParam,   
            @OrdNo integer output, @OrdDate datetime output)  
         as   
         set @OrdDate = GETDATE();  
         insert into TVPOrd (OrdDate, CustCode)   
values (@OrdDate, @CustCode) output OrdNo);   
         select @OrdNo = SCOPE_IDENTITY();   
         insert into TVPItem (OrdNo, ProdCode, Qty)  
select @OrdNo, @Items.ProdCode, @Items.Qty   
from @Items  
```  
  
## <a name="to-send-the-data"></a><span data-ttu-id="56d4a-107">So senden Sie Daten</span><span class="sxs-lookup"><span data-stu-id="56d4a-107">To Send the Data</span></span>  
  
1.  <span data-ttu-id="56d4a-108">Deklarieren Sie Variablen für die SQL-Parameter.</span><span class="sxs-lookup"><span data-stu-id="56d4a-108">Declare variables for the SQL parameters.</span></span> <span data-ttu-id="56d4a-109">In diesem Fall ist der Tabellenwert vollständig im Speicher verfügbar. Daher werden Werte für die Spalten des Tabellenwerts als Arrays deklariert.</span><span class="sxs-lookup"><span data-stu-id="56d4a-109">In this case, the table value is held entirely in memory, so values for the columns of the table value are declared as arrays.</span></span>  
  
    ```  
    SQLRETURN r;  
    // Variables for SQL parameters.  
    #define ITEM_ARRAY_SIZE 20  
  
    SQLCHAR CustCode[6];  
    SQLCHAR *TVP = (SQLCHAR *) "TVParam";  
    SQLINTEGER ProdCode[ITEM_ARRAY_SIZE], Qty[ITEM_ARRAY_SIZE];  
    SQLINTEGER OrdNo;  
    char OrdDate[23];  
  
    // Variables for indicator/length variables associated with parameters.  
    SQLLEN cbCustCode, cbTVP, cbProdCode[ITEM_ARRAY_SIZE], cbQty[ITEM_ARRAY_SIZE], cbOrdNo, cbOrdDate;  
    ```  
  
2.  <span data-ttu-id="56d4a-110">Binden Sie die Parameter.</span><span class="sxs-lookup"><span data-stu-id="56d4a-110">Bind the parameters.</span></span> <span data-ttu-id="56d4a-111">Das Binden von Parametern ist ein Zweiphasenprozess, wenn Tabellenwertparameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="56d4a-111">Binding parameters is a two stage process when table-valued parameters are used.</span></span> <span data-ttu-id="56d4a-112">In der ersten Phase werden Schrittparameter für die gespeicherte Prozedur wie gewohnt gebunden:</span><span class="sxs-lookup"><span data-stu-id="56d4a-112">In the first stage, step parameters for the stored procedure are bound in the normal way, as follows.</span></span>  
  
    ```  
    // Bind parameters for call to TVPOrderEntryDirect.  
    // 1 - Custcode input  
    r = SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT,SQL_VARCHAR, SQL_C_CHAR, 5, 0, CustCode, sizeof(CustCode), &cbCustCode);  
  
    // 2 - Items TVP  
    r = SQLBindParameter(hstmt,   
        2,// ParameterNumber  
        SQL_PARAM_INPUT,// InputOutputType  
        SQL_C_DEFAULT,// ValueType   
        SQL_SS_TABLE,// Parametertype  
        ITEM_ARRAY_SIZE,// ColumnSize: For a table-valued parameter this is the row array size.  
        0,// DecimalDigits: For a table-valued parameter this is always 0.   
        TVP,// ParameterValuePtr: For a table-valued parameter this is the type name of the   
    //table-valued parameter, and also a token returned by SQLParamData.  
        SQL_NTS,// BufferLength: For a table-valued parameter this is the length of the type name or SQL_NTS.  
        &cbTVP);// StrLen_or_IndPtr: For a table-valued parameter this is the number of rows actually used.  
  
    // 3 - OrdNo output  
    r = SQLBindParameter(hstmt, 3, SQL_PARAM_OUTPUT,SQL_INTEGER, SQL_C_LONG, 0, 0, &OrdNo,  
       sizeof(SQLINTEGER), &cbOrdNo);  
    // 4 - OrdDate output  
    r = SQLBindParameter(hstmt, 4, SQL_PARAM_OUTPUT,SQL_TYPE_TIMESTAMP, SQL_C_CHAR, 23, 3, &OrdDate,   
       sizeof(OrdDate), &cbOrdDate);  
    ```  
  
3.  <span data-ttu-id="56d4a-113">In der zweiten Phase der Parameterbindung erfolgt das Binden der Spalten für den Tabellenwertparameter.</span><span class="sxs-lookup"><span data-stu-id="56d4a-113">The second stage of parameter binding is to bind the columns for the table-valued parameter.</span></span> <span data-ttu-id="56d4a-114">Der Parameterfokus wird zunächst auf die Ordnungszahl des Tabellenwertparameters festgelegt.</span><span class="sxs-lookup"><span data-stu-id="56d4a-114">The parameter focus is first set to the ordinal of the table-valued parameter.</span></span> <span data-ttu-id="56d4a-115">Anschließend werden die Spalten des Tabellen Werts mit SQLBindParameter auf dieselbe Weise gebunden, wie Sie wären, wenn Sie Parameter der gespeicherten Prozedur sind, jedoch mit Spalten Ordnungen für ParameterNumber.</span><span class="sxs-lookup"><span data-stu-id="56d4a-115">Then columns of the table value are bound by using SQLBindParameter in the same way as they would be if they were parameters of the stored procedure, but with column ordinals for ParameterNumber.</span></span> <span data-ttu-id="56d4a-116">Wenn es weitere Tabellenwertparameter gäbe, würden wir den Fokus abwechselnd auf jeden einzelnen festlegen und die jeweiligen Spalten binden.</span><span class="sxs-lookup"><span data-stu-id="56d4a-116">If there were more table-valued parameters, we would set the focus to each in turn and bind their columns.</span></span> <span data-ttu-id="56d4a-117">Schließlich wird der Parameterfokus auf 0 (null) zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="56d4a-117">Finally, the parameter focus is reset to 0.</span></span>  
  
    ```  
    // Bind columns for the table-valued parameter (param 2).  
    // First set focus on param 2.  
    r = SQLSetStmtAttr(hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER) 2, SQL_IS_INTEGER);  
  
    // Col 1 - ProdCode  
    r = SQLBindParameter(hstmt, 1, SQL_PARAM_INPUT,SQL_INTEGER, SQL_C_LONG, 0, 0, ProdCode, sizeof(SQLINTEGER), cbProdCode);  
    // Col 2 - Qty  
    r = SQLBindParameter(hstmt, 2, SQL_PARAM_INPUT,SQL_INTEGER, SQL_C_LONG, 0, 0, Qty, sizeof(SQLINTEGER), cbQty);  
  
    // Reset param focus.  
    r = SQLSetStmtAttr(hstmt, SQL_SOPT_SS_PARAM_FOCUS, (SQLPOINTER) 0, SQL_IS_INTEGER);  
    ```  
  
4.  <span data-ttu-id="56d4a-118">Füllen Sie die Parameterpuffer auf.</span><span class="sxs-lookup"><span data-stu-id="56d4a-118">Populate the parameter buffers.</span></span> <span data-ttu-id="56d4a-119">`cbTVP` wird auf die Anzahl der an den Server zu sendenden Zeilen festgelegt.</span><span class="sxs-lookup"><span data-stu-id="56d4a-119">`cbTVP` is set to the number of rows to be sent to the server.</span></span>  
  
    ```  
    // Populate parameters.  
    cbTVP = 0; // Number of rows available for input.  
    strcpy_s((char *) CustCode, sizeof(CustCode), "CUST1"); cbCustCode = SQL_NTS;  
  
    ProdCode[cbTVP] = 1215;cbProdCode[cbTVP] = sizeof(SQLINTEGER);   
    Qty[cbTVP] = 5;cbQty[cbTVP] = sizeof(SQLINTEGER);   
    cbTVP++; // Number of rows available for input  
  
    ProdCode[cbTVP] = 1017;cbProdCode[cbTVP] = sizeof(SQLINTEGER);   
    Qty[cbTVP] = 2;cbQty[cbTVP] = sizeof(SQLINTEGER);   
    cbTVP++; // Number of rows available for input.  
    ```  
  
5.  <span data-ttu-id="56d4a-120">Rufen Sie die Prozedur auf:</span><span class="sxs-lookup"><span data-stu-id="56d4a-120">Call the procedure:</span></span>  
  
    ```  
    // Call the procedure.  
    r = SQLExecDirect(hstmt, (SQLCHAR *) "{call TVPOrderEntry(?, ?, ?, ?)}",SQL_NTS);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="56d4a-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56d4a-121">See Also</span></span>  
 [<span data-ttu-id="56d4a-122">Programmierbeispiele für ODBC-Tabellenwertparameter</span><span class="sxs-lookup"><span data-stu-id="56d4a-122">ODBC Table-Valued Parameter Programming Examples</span></span>](../../database-engine/dev-guide/odbc-table-valued-parameter-programming-examples.md)  
  
  
