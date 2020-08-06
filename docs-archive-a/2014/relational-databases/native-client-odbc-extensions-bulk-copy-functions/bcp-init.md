---
title: bcp_init | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- bcp_init
api_location:
- sqlncli11.dll
topic_type:
- apiref
helpviewer_keywords:
- bcp_init function
ms.assetid: 6a25862c-7f31-4873-ab65-30f3abde89d2
author: rothja
ms.author: jroth
ms.openlocfilehash: 72d48b2a07e425e0863084c700c4de93d2776739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616058"
---
# <a name="bcp_init"></a><span data-ttu-id="6adf5-102">bcp_init</span><span class="sxs-lookup"><span data-stu-id="6adf5-102">bcp_init</span></span>
  <span data-ttu-id="6adf5-103">Initialisiert den Massenkopiervorgang.</span><span class="sxs-lookup"><span data-stu-id="6adf5-103">Initializes the bulk copy operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6adf5-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="6adf5-104">Syntax</span></span>  
  
```  
  
RETCODE bcp_init (  
HDBC   
hdbc  
,  
LPCTSTR   
szTable  
,  
LPCTSTR   
szDataFile  
,  
LPCTSTR   
szErrorFile  
,  
INT   
eDirection  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="6adf5-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="6adf5-105">Arguments</span></span>  
 <span data-ttu-id="6adf5-106">*hdbc*</span><span class="sxs-lookup"><span data-stu-id="6adf5-106">*hdbc*</span></span>  
 <span data-ttu-id="6adf5-107">Das für den Massenkopiervorgang aktivierte ODBC-Verbindungshandle.</span><span class="sxs-lookup"><span data-stu-id="6adf5-107">Is the bulk copy-enabled ODBC connection handle.</span></span>  
  
 <span data-ttu-id="6adf5-108">*szTable*</span><span class="sxs-lookup"><span data-stu-id="6adf5-108">*szTable*</span></span>  
 <span data-ttu-id="6adf5-109">Name der Datenbanktabelle, in die bzw. aus der kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6adf5-109">Is the name of the database table to be copied into or out of.</span></span> <span data-ttu-id="6adf5-110">Dieser Name kann auch den Namen der Datenbank oder den Namen des Besitzers enthalten.</span><span class="sxs-lookup"><span data-stu-id="6adf5-110">This name can also include the database name or the owner name.</span></span> <span data-ttu-id="6adf5-111">Beispielsweise **Pubs. Gracie. Titeln**, **Pubs. Titel**, **Gracie. Titeln**und **Titel** sind alle gültigen Tabellennamen.</span><span class="sxs-lookup"><span data-stu-id="6adf5-111">For example, **pubs.gracie.titles**, **pubs..titles**, **gracie.titles**, and **titles** are all legal table names.</span></span>  
  
 <span data-ttu-id="6adf5-112">Wenn *eDirection* DB_OUT ist, kann *szTable* auch der Name einer Daten Bank Sicht sein.</span><span class="sxs-lookup"><span data-stu-id="6adf5-112">If *eDirection* is DB_OUT, *szTable* can also be the name of a database view.</span></span>  
  
 <span data-ttu-id="6adf5-113">Wenn *eDirection* DB_OUT ist und mithilfe [bcp_control](bcp-control.md) eine SELECT-Anweisung angegeben wird, bevor [bcp_exec](bcp-exec.md) aufgerufen wird, muss **bcp_init**_szTable_ auf NULL festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="6adf5-113">If *eDirection* is DB_OUT and a SELECT statement is specified using [bcp_control](bcp-control.md) before [bcp_exec](bcp-exec.md) is called, **bcp_init**_szTable_ must be set to NULL.</span></span>  
  
 <span data-ttu-id="6adf5-114">*szDataFile*</span><span class="sxs-lookup"><span data-stu-id="6adf5-114">*szDataFile*</span></span>  
 <span data-ttu-id="6adf5-115">Name der Benutzerdatei, in die bzw. aus der kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="6adf5-115">Is the name of the user file to be copied into or out of.</span></span> <span data-ttu-id="6adf5-116">Wenn Daten mithilfe von [bcp_sendrow](bcp-sendrow.md)direkt aus Variablen kopiert werden, legen Sie *szDataFile* auf NULL fest.</span><span class="sxs-lookup"><span data-stu-id="6adf5-116">If data is being copied directly from variables by using [bcp_sendrow](bcp-sendrow.md), set *szDataFile* to NULL.</span></span>  
  
 <span data-ttu-id="6adf5-117">*szErrorFile*</span><span class="sxs-lookup"><span data-stu-id="6adf5-117">*szErrorFile*</span></span>  
 <span data-ttu-id="6adf5-118">Der Name der Fehlerdatei, in die Statusmeldungen, Fehlermeldungen und Kopien von Zeilen geschrieben werden sollen, die aus einem bestimmten Grund nicht von einer Benutzerdatei in eine Tabelle kopiert werden konnten.</span><span class="sxs-lookup"><span data-stu-id="6adf5-118">Is the name of the error file to be filled with progress messages, error messages, and copies of any rows that, for any reason, could not be copied from a user file to a table.</span></span> <span data-ttu-id="6adf5-119">Wenn NULL als *szErrorFile*übergeben wird, wird keine Fehler Datei verwendet.</span><span class="sxs-lookup"><span data-stu-id="6adf5-119">If NULL is passed as *szErrorFile*, no error file is used.</span></span>  
  
 <span data-ttu-id="6adf5-120">*eDirection*</span><span class="sxs-lookup"><span data-stu-id="6adf5-120">*eDirection*</span></span>  
 <span data-ttu-id="6adf5-121">Die Richtung der Kopie, entweder DB_IN oder DB_OUT.</span><span class="sxs-lookup"><span data-stu-id="6adf5-121">Is the direction of the copy, either DB_IN or DB_OUT.</span></span> <span data-ttu-id="6adf5-122">DB_IN bedeutet eine Kopie aus Programmvariablen oder aus einer Benutzerdatei in eine Tabelle.</span><span class="sxs-lookup"><span data-stu-id="6adf5-122">DB_IN indicates a copy from program variables or a user file to a table.</span></span> <span data-ttu-id="6adf5-123">DB_OUT bedeutet eine Kopie von einer Datenbanktabelle in eine Benutzerdatei an.</span><span class="sxs-lookup"><span data-stu-id="6adf5-123">DB_OUT indicates a copy from a database table to a user file.</span></span> <span data-ttu-id="6adf5-124">Sie müssen einen Benutzerdateinamen mit DB_OUT angeben.</span><span class="sxs-lookup"><span data-stu-id="6adf5-124">You must specify a user file name with DB_OUT.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="6adf5-125">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="6adf5-125">Returns</span></span>  
 <span data-ttu-id="6adf5-126">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="6adf5-126">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6adf5-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6adf5-127">Remarks</span></span>  
 <span data-ttu-id="6adf5-128">Rufen Sie **bcp_init** auf, bevor Sie eine andere Massen Kopierfunktion aufrufen.</span><span class="sxs-lookup"><span data-stu-id="6adf5-128">Call **bcp_init** before calling any other bulk-copy function.</span></span> <span data-ttu-id="6adf5-129">**bcp_init** führt die erforderlichen Initialisierungen für einen Massen Kopiervorgang von Daten zwischen der Arbeitsstation und aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6adf5-129">**bcp_init** performs the necessary initializations for a bulk copy of data between the workstation and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6adf5-130">Die **bcp_init** -Funktion muss mit einem ODBC-Verbindungs Handle bereitgestellt werden, das für die Verwendung mit Massen Kopierfunktionen aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="6adf5-130">The **bcp_init** function must be provided with an ODBC connection handle enabled for use with bulk copy functions.</span></span> <span data-ttu-id="6adf5-131">Um das Handle zu aktivieren, verwenden Sie [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) , wobei SQL_COPT_SS_BCP auf einem zugeordneten, aber nicht verbundenen Verbindungs Handle auf SQL_BCP_ON festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6adf5-131">To enable the handle, use [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_BCP set to SQL_BCP_ON on an allocated, but not connected, connection handle.</span></span> <span data-ttu-id="6adf5-132">Wenn Sie versuchen, das Attribut einem bereits verbundenen Verbindungshandle zuzuweisen, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="6adf5-132">Attempting to assign the attribute on a connected handle results in an error.</span></span>  
  
 <span data-ttu-id="6adf5-133">Wenn eine Datendatei angegeben wird, untersucht **bcp_init** die Struktur der Datenbankquelle oder der Ziel Tabelle, nicht die Datendatei.</span><span class="sxs-lookup"><span data-stu-id="6adf5-133">When a data file is specified, **bcp_init** examines the structure of the database source or target table, not the data file.</span></span> <span data-ttu-id="6adf5-134">**bcp_init** gibt Datenformat Werte für die Datendatei basierend auf den einzelnen Spalten in der Datenbanktabelle, der Sicht oder dem SELECT-Resultset an.</span><span class="sxs-lookup"><span data-stu-id="6adf5-134">**bcp_init** specifies data format values for the data file based on each column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="6adf5-135">Diese Spezifikation enthält unter anderem den Datentyp jeder Spalte, das Vorhandensein bzw. Nichtvorhandensein eines Längen- oder NULL-Wertindikators und von Bytezeichenfolgen des Abschlusszeichens der Daten, sowie die Breite von Datentypen fester Länge.</span><span class="sxs-lookup"><span data-stu-id="6adf5-135">This specification includes the data type of each column, the presence or absence of a length or null indicator and terminator byte strings in the data, and the width of fixed-length data types.</span></span> <span data-ttu-id="6adf5-136">**bcp_init** legt diese Werte wie folgt fest:</span><span class="sxs-lookup"><span data-stu-id="6adf5-136">**bcp_init** sets these values as follows:</span></span>  
  
-   <span data-ttu-id="6adf5-137">Der angegebene Datentyp entspricht dem Datentyp der Spalte in der Datenbanktabelle, der Sicht oder dem SELECT-Resultset.</span><span class="sxs-lookup"><span data-stu-id="6adf5-137">The data type specified is the data type of the column in the database table, view, or SELECT result set.</span></span> <span data-ttu-id="6adf5-138">Der Datentyp wird von den in der Datei sqlncli.h angegebenen systemeigenen Datentypen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="6adf5-138">The data type is enumerated by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] native data types specified in sqlncli.h.</span></span> <span data-ttu-id="6adf5-139">Die Daten selbst werden in computereigenem Format dargestellt,</span><span class="sxs-lookup"><span data-stu-id="6adf5-139">Data itself is represented in its computer form.</span></span> <span data-ttu-id="6adf5-140">Das heißt, dass Daten aus einer Spalte vom Datentyp **Integer** durch eine 4-Byte-Sequenz dargestellt werden, die auf dem Computer, auf dem die Datendatei erstellt wurde, Big-oder Little-Endian ist.</span><span class="sxs-lookup"><span data-stu-id="6adf5-140">That is, data from a column of **integer** data type is represented by a four-byte sequence that is big-or little-endian based on the computer that created the data file.</span></span>  
  
-   <span data-ttu-id="6adf5-141">Wenn ein Datenbankdatentyp eine feste Länge hat, haben auch die Daten der Datendatei eine feste Länge.</span><span class="sxs-lookup"><span data-stu-id="6adf5-141">If a database data type is fixed in length, the data file data is also fixed in length.</span></span> <span data-ttu-id="6adf5-142">Massen Kopierfunktionen, die Daten verarbeiten (z. b. [bcp_exec](bcp-exec.md)), analysieren Daten Zeilen, die erwarten, dass die Länge der Daten in der Datendatei mit der Länge der Daten identisch ist, die in der Datenbanktabelle, Sicht oder SELECT-Spaltenliste angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="6adf5-142">Bulk-copy functions that process data (for example, [bcp_exec](bcp-exec.md)) parse data rows expecting the length of the data in the data file to be identical to the length of the data specified in the database table, view, or SELECT column list.</span></span> <span data-ttu-id="6adf5-143">Beispielsweise müssen Daten für eine als **char (13)** definierte Daten Bank Spalte für jede Daten Zeile in der Datei 13 Zeichen darstellen.</span><span class="sxs-lookup"><span data-stu-id="6adf5-143">For example, data for a database column defined as **char(13)** must be represented by 13 characters for each row of data in the file.</span></span> <span data-ttu-id="6adf5-144">Für Daten mit fester Länge kann ein NULL-Indikator verwendet werden, wenn die Datenbankspalte NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="6adf5-144">Fixed-length data can be prefixed with a null indicator if the database column allows null values.</span></span>  
  
-   <span data-ttu-id="6adf5-145">Wenn eine Bytesequenz für Abschlusszeichen definiert ist, wird deren Länge auf 0 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6adf5-145">When terminator-byte sequence is defined, the length of the terminator-byte sequence is set to 0.</span></span>  
  
-   <span data-ttu-id="6adf5-146">Zum Kopieren von Daten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] muss die Datendatei für jede Spalte der Datenbanktabelle Daten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="6adf5-146">When copying to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the data file must have data for each column in the database table.</span></span> <span data-ttu-id="6adf5-147">Beim Kopieren aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden Daten aus allen Spalten in der Datenbanktabelle, Sicht oder SELECT-Resultset in die Datendatei kopiert.</span><span class="sxs-lookup"><span data-stu-id="6adf5-147">When copying from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], data from all columns in the database table, view, or SELECT result set are copied to the data file.</span></span>  
  
-   <span data-ttu-id="6adf5-148">Beim Kopieren von Daten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] muss die Ordnungsposition einer Spalte in der Datendatei der Ordnungsposition einer Spalte in der Datenbanktabelle genau entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6adf5-148">When copying to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the ordinal position of a column in the data file must be identical to the ordinal position of the column in the database table.</span></span> <span data-ttu-id="6adf5-149">Beim Kopieren aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] platziert **bcp_exec** Daten auf der Grundlage der Ordnungsposition der Spalte in der Datenbanktabelle.</span><span class="sxs-lookup"><span data-stu-id="6adf5-149">When copying from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], **bcp_exec** places data based on the ordinal position of the column in the database table.</span></span>  
  
-   <span data-ttu-id="6adf5-150">Wenn ein Daten Bank Datentyp eine Variable Länge aufweist (z. b. **varbinary (22)**) oder wenn eine Daten Bank Spalte NULL-Werte enthalten kann, wird den Daten in der Datendatei ein Längen-/NULL-Indikator vorangestellt.</span><span class="sxs-lookup"><span data-stu-id="6adf5-150">If a database data type is variable in length (for example, **varbinary(22)**) or if a database column can contain null values, data in the data file is prefixed by a length/null indicator.</span></span> <span data-ttu-id="6adf5-151">Die Breite des Indikators ändert sich auf der Grundlage des Datentyps und der Version der Massenkopierfunktion.</span><span class="sxs-lookup"><span data-stu-id="6adf5-151">The width of the indicator varies based on the data type and version of bulk copy.</span></span>  
  
 <span data-ttu-id="6adf5-152">Um die für eine Datendatei angegebenen Datenformat Werte zu ändern, müssen [bcp_columns](bcp-columns.md) und [bcp_colfmt](bcp-colfmt.md)aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6adf5-152">To change data format values specified for a data file, call [bcp_columns](bcp-columns.md) and [bcp_colfmt](bcp-colfmt.md).</span></span>  
  
 <span data-ttu-id="6adf5-153">Massenkopiervorgänge in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] können für Tabellen, die keine Indizes enthalten, optimiert werden, indem das Datenbank-Wiederherstellungsmodul auf SIMPLE oder BULK_LOGGED festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="6adf5-153">Bulk copies to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can be optimized for tables that do not contain indexes by setting the database recovery model to SIMPLE or BULK_LOGGED.</span></span> <span data-ttu-id="6adf5-154">Weitere Informationen finden Sie unter [Voraussetzungen für die minimale Protokollierung beim Massen Import](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md) und [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="6adf5-154">For more information, see [Prerequisites for Minimal Logging in Bulk Import](../import-export/prerequisites-for-minimal-logging-in-bulk-import.md) and [ALTER DATABASE](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
 <span data-ttu-id="6adf5-155">Wenn keine Datendatei verwendet wird, müssen Sie [bcp_bind](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) aufzurufen, um das Format und den Speicherort des Daten-fsors für jede Spalte anzugeben, und anschließend Daten Zeilen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe [bcp_sendrow](bcp-sendrow.md)in die kopieren.</span><span class="sxs-lookup"><span data-stu-id="6adf5-155">If no data file is used, you must call [bcp_bind](../../relational-databases/native-client-odbc-extensions-bulk-copy-functions/bcp-bind.md) to specify the format and location in memory of the data fsor each column, then copy data rows to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] using [bcp_sendrow](bcp-sendrow.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6adf5-156">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6adf5-156">Example</span></span>  
 <span data-ttu-id="6adf5-157">Dieses Beispiel zeigt, wie die ODBC-Funktion bcp_init mit einer Formatdatei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6adf5-157">This sample shows how to use the ODBC bcp_init function with a format file.</span></span>  
  
 <span data-ttu-id="6adf5-158">Bevor Sie den C++-Code kompilieren und ausführen, sind folgende Schritte erforderlich:</span><span class="sxs-lookup"><span data-stu-id="6adf5-158">Before you compile and run the C++ code, you need to do the following:</span></span>  
  
-   <span data-ttu-id="6adf5-159">Erstellen einer ODBC-Datenquelle mit dem Namen "Test".</span><span class="sxs-lookup"><span data-stu-id="6adf5-159">Create an ODBC data source called Test.</span></span> <span data-ttu-id="6adf5-160">Sie können diese Datenquelle einer beliebigen Datenbank zuordnen.</span><span class="sxs-lookup"><span data-stu-id="6adf5-160">You can associate this data source with any database.</span></span>  
  
-   <span data-ttu-id="6adf5-161">Führen Sie für die Datenbank die folgende [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisung aus:</span><span class="sxs-lookup"><span data-stu-id="6adf5-161">Run the following [!INCLUDE[tsql](../../includes/tsql-md.md)] on the database:</span></span>  
  
    ```  
    CREATE TABLE BCPDate (cola int, colb datetime);  
    ```  
  
-   <span data-ttu-id="6adf5-162">Fügen Sie dem Verzeichnis, in dem Sie die Anwendung ausführen, eine Datei namens Bcpfmt.fmt hinzu, und fügen Sie Folgendes in die Datei ein:</span><span class="sxs-lookup"><span data-stu-id="6adf5-162">In the directory where you will run the application, add a file called Bcpfmt.fmt, and add this to the file:</span></span>  
  
    ```  
    8.0  
    2  
    1SQLCHAR04"\t"1colaSQL_Latin1_General_Cp437_Bin  
    2SQLCHAR08"\r\n"2colbSQL_Latin1_General_Cp437_Bin  
    ```  
  
-   <span data-ttu-id="6adf5-163">Fügen Sie dem Verzeichnis, in dem Sie die Anwendung ausführen, eine Datei namens Bcpodbc.bcp hinzu, und fügen Sie Folgendes in die Datei ein:</span><span class="sxs-lookup"><span data-stu-id="6adf5-163">In the directory where you will run the application, add a file called Bcpodbc.bcp, and add this to the file:</span></span>  
  
    ```  
    1  
    2  
    ```  
  
 <span data-ttu-id="6adf5-164">Nun sind Sie bereit, C++-Code zu kompilieren und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6adf5-164">Now you are ready to compile and run the C++ code.</span></span>  
  
```  
// compile with: odbc32.lib sqlncli11.lib  
#include <stdio.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
SQLHENV henv = SQL_NULL_HENV;  
HDBC hdbc1 = SQL_NULL_HDBC;   
  
void Cleanup() {  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
   SDWORD cRows;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle, set BCP mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetConnectAttr(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security. Create SQL Server DSN using Windows NT authentication.  
   retcode = SQLConnect(hdbc1, (UCHAR*)"Test", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_IN);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Read the format file.  
   retcode = bcp_readfmt(hdbc1, "BCPFMT.fmt");  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_readfmt(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_exec(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied in = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
```  
  
## <a name="see-also"></a><span data-ttu-id="6adf5-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6adf5-165">See Also</span></span>  
 [<span data-ttu-id="6adf5-166">Bulk Copy Functions</span><span class="sxs-lookup"><span data-stu-id="6adf5-166">Bulk Copy Functions</span></span>](sql-server-driver-extensions-bulk-copy-functions.md)  
  
  
