---
title: Mapping-Datentypen (ODBC) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- mapping data types [ODBC]
- result sets [ODBC], data types
- ODBC data types, mapping
- SQL Server Native Client ODBC driver, result sets
- ODBC applications, result sets
- data types [ODBC], mapping
- sql_variant data type
- SQL Server Native Client ODBC driver, data types
ms.assetid: 4ba0924d-9fca-4c48-aced-0a8d817b3dde
author: rothja
ms.author: jroth
ms.openlocfilehash: 545e738afb6b3283b2ff2f3830921da8ed13202f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725654"
---
# <a name="mapping-data-types-odbc"></a><span data-ttu-id="d0196-102">Zuordnen von Datentypen (ODBC)</span><span class="sxs-lookup"><span data-stu-id="d0196-102">Mapping Data Types (ODBC)</span></span>
  <span data-ttu-id="d0196-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber ordnet [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL-Datentypen ODBC-SQL-Datentypen zu.</span><span class="sxs-lookup"><span data-stu-id="d0196-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver maps [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL data types to ODBC SQL data types.</span></span> <span data-ttu-id="d0196-104">In den folgenden Abschnitten werden die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-SQL-Datentypen sowie die ODBC-SQL-Datentypen, denen sie zugeordnet werden, erläutert.</span><span class="sxs-lookup"><span data-stu-id="d0196-104">The sections below discuss the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] SQL data types and the ODBC SQL data types to which they map.</span></span> <span data-ttu-id="d0196-105">Außerdem werden die ODBC-SQL-Datentypen und die zugehörigen ODBC-C-Datentypen sowie die unterstützten und standardmäßigen Konvertierungen erklärt.</span><span class="sxs-lookup"><span data-stu-id="d0196-105">They also discuss the ODBC SQL data types and their corresponding ODBC C data types, and the supported and default conversions.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d0196-106">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] **Zeitstempel** -Datentyp wird dem SQL_BINARY oder SQL_VARBINARY ODBC-Datentyp zugeordnet, da die Werte in **Zeitstempel** -Spalten keine **DateTime** -Werte sind, sondern **binäre (8)** oder **varbinary (8)** -Werte, die die Sequenz der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Aktivität in der Zeile angeben.</span><span class="sxs-lookup"><span data-stu-id="d0196-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]**timestamp** data type maps to the SQL_BINARY or SQL_VARBINARY ODBC data type because the values in **timestamp** columns are not **datetime** values, but **binary(8)** or **varbinary(8)** values that indicate the sequence of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] activity on the row.</span></span> <span data-ttu-id="d0196-107">Wenn der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber einen SQL_C_WCHAR-Wert (Unicode) erkennt, der eine ungerade Anzahl von Bytes enthält, wird das letzte ungerade Byte abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="d0196-107">If the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver encounters a SQL_C_WCHAR (Unicode) value that is an odd number of bytes, the trailing odd byte is truncated.</span></span>  
  
## <a name="dealing-with-sql_variant-data-type-in-odbc"></a><span data-ttu-id="d0196-108">Arbeiten mit dem 'sql_variant'-Datentyp in ODBC</span><span class="sxs-lookup"><span data-stu-id="d0196-108">Dealing with sql_variant Data Type in ODBC</span></span>  
 <span data-ttu-id="d0196-109">Die **sql_variant** -Datentyp Spalte kann beliebige Datentypen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit Ausnahme von großen Objekten (LOB) enthalten, z. b. **Text**, **ntext**und **Image**.</span><span class="sxs-lookup"><span data-stu-id="d0196-109">The **sql_variant** data type column can contain any of the data types in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] except large objects (LOBs), such as **text**, **ntext**, and **image**.</span></span> <span data-ttu-id="d0196-110">Beispielsweise könnte die Spalte **smallint** -Werte für einige Zeilen, **float** -Werte für andere Zeilen und **char/nchar-** Werte im Rest enthalten.</span><span class="sxs-lookup"><span data-stu-id="d0196-110">For example, the column could contain **smallint** values for some rows, **float** values for other rows, and **char/nchar** values in the remainder.</span></span>  
  
 <span data-ttu-id="d0196-111">Der **sql_variant** -Datentyp ähnelt dem **Variant** -Datentyp in Microsoft Visual Basic??.</span><span class="sxs-lookup"><span data-stu-id="d0196-111">The **sql_variant** data type is similar to the **Variant** data type in Microsoft Visual Basic??.</span></span>  
  
### <a name="retrieving-data-from-the-server"></a><span data-ttu-id="d0196-112">Abrufen von Daten vom Server</span><span class="sxs-lookup"><span data-stu-id="d0196-112">Retrieving Data from the Server</span></span>  
 <span data-ttu-id="d0196-113">ODBC weist kein Konzept von Variant-Typen auf, was die Verwendung des **sql_variant** -Datentyps mit einem ODBC-Treiber in einschränkt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d0196-113">ODBC does not have a concept of variant types, limiting the use of the **sql_variant** data type with an ODBC driver in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d0196-114">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]Wenn in eine Bindung angegeben ist, muss der **sql_variant** Datentyp an einen der dokumentierten ODBC-Datentypen gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="d0196-114">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], if binding is specified, the **sql_variant** data type must be bound to one of the documented ODBC data types.</span></span> <span data-ttu-id="d0196-115">**SQL_CA_SS_VARIANT_TYPE**, ein für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber spezifisches Attribut, gibt den Datentyp einer Instanz in der **sql_variant** Spalte an den Benutzer zurück.</span><span class="sxs-lookup"><span data-stu-id="d0196-115">**SQL_CA_SS_VARIANT_TYPE**, a new attribute specific to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, returns the data type of an instance in the **sql_variant** column to the user.</span></span>  
  
 <span data-ttu-id="d0196-116">Wenn keine Bindung angegeben wird, kann die [SQLGetData](../native-client-odbc-api/sqlgetdata.md) -Funktion verwendet werden, um den Datentyp einer Instanz in der **sql_variant** Spalte zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="d0196-116">If no binding is specified, the [SQLGetData](../native-client-odbc-api/sqlgetdata.md) function can be used to determine the data type of an instance in the **sql_variant** column.</span></span>  
  
 <span data-ttu-id="d0196-117">Führen Sie die folgenden Schritte aus, um **sql_variant** Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d0196-117">To retrieve **sql_variant** data follow these steps.</span></span>  
  
1.  <span data-ttu-id="d0196-118">Rufen Sie **SQLFetch** auf, um zu der abgerufenen Zeile zu positionieren.</span><span class="sxs-lookup"><span data-stu-id="d0196-118">Call **SQLFetch** to position to the row retrieved.</span></span>  
  
2.  <span data-ttu-id="d0196-119">Aufrufen von **SQLGetData**, angeben von SQL_C_BINARY für den-Typ und 0 für die Daten Länge.</span><span class="sxs-lookup"><span data-stu-id="d0196-119">Call **SQLGetData**, specifying SQL_C_BINARY for the type and 0 for the data length.</span></span> <span data-ttu-id="d0196-120">Dadurch wird der Treiber gezwungen, den **sql_variant** -Header zu lesen.</span><span class="sxs-lookup"><span data-stu-id="d0196-120">This forces the driver to read the **sql_variant** header.</span></span> <span data-ttu-id="d0196-121">Der-Header gibt den Datentyp dieser Instanz in der **sql_variant** Spalte an.</span><span class="sxs-lookup"><span data-stu-id="d0196-121">The header provides the data type of that instance in the **sql_variant** column.</span></span> <span data-ttu-id="d0196-122">**SQLGetData** gibt die Größe (in Bytes) des Werts zurück.</span><span class="sxs-lookup"><span data-stu-id="d0196-122">**SQLGetData** returns the size (in bytes) of the value.</span></span>  
  
3.  <span data-ttu-id="d0196-123">Führen Sie [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) aus, indem Sie **SQL_CA_SS_VARIANT_TYPE** als Attribut Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="d0196-123">Call [SQLColAttribute](../native-client-odbc-api/sqlcolattribute.md) by specifying **SQL_CA_SS_VARIANT_TYPE** as its attribute value.</span></span> <span data-ttu-id="d0196-124">Diese Funktion gibt den C-Datentyp der Instanz in der **sql_variant** Spalte an den Client zurück.</span><span class="sxs-lookup"><span data-stu-id="d0196-124">This function will return the C data type of the instance in the **sql_variant** column to the client.</span></span>  
  
 <span data-ttu-id="d0196-125">Im folgenden Codesegment werden die vorhergehenden Schritte gezeigt.</span><span class="sxs-lookup"><span data-stu-id="d0196-125">Here is a code segment showing the preceding steps.</span></span>  
  
```  
while ((retcode = SQLFetch (hstmt))==SQL_SUCCESS)  
{  
    if (retcode != SQL_SUCCESS && retcode != SQL_SUCCESS_WITH_INFO)  
    {  
        SQLError (NULL, NULL, hstmt, NULL,   
                    &lNativeError,szError,MAX_DATA,&sReturned);  
        printf_s ("%s\n",szError);  
        goto Exit;  
    }  
    retcode = SQLGetData (hstmt, 1, SQL_C_BINARY,   
                                pBuff,0,&Indicator);//Figure out the length  
    if (retcode != SQL_SUCCESS_WITH_INFO && retcode != SQL_SUCCESS)  
    {  
        SQLError (NULL, NULL, hstmt, NULL, &lNativeError,   
                    szError,MAX_DATA,&sReturned);  
        printf_s ("%s\n",szError);  
        goto Exit;  
    }  
    printf_s ("Byte length : %d ",Indicator); //Print out the byte length  
  
    int iValue = 0;  
    retcode = SQLColAttribute (hstmt, 1, SQL_CA_SS_VARIANT_TYPE, NULL,   
                                        NULL,NULL,&iValue);  //Figure out the type  
    printf_s ("Sub type = %d ",iValue);//Print the type, the return is C_type of the column]  
  
// Set up a new binding or do the SQLGetData on that column with   
// the appropriate type  
}  
```  
  
 <span data-ttu-id="d0196-126">Wenn der Benutzer die Bindung mithilfe von [SQLBindCol](../native-client-odbc-api/sqlbindcol.md)erstellt, liest der Treiber die Metadaten und die Daten.</span><span class="sxs-lookup"><span data-stu-id="d0196-126">If the user creates the binding using [SQLBindCol](../native-client-odbc-api/sqlbindcol.md), the driver reads the metadata and the data.</span></span> <span data-ttu-id="d0196-127">Der Treiber konvertiert die Daten dann in den entsprechenden in der Bindung angegebenen ODBC-Typ.</span><span class="sxs-lookup"><span data-stu-id="d0196-127">The driver then converts the data to the appropriate ODBC type specified in the binding.</span></span>  
  
### <a name="sending-data-to-the-server"></a><span data-ttu-id="d0196-128">Senden von Daten an den Server</span><span class="sxs-lookup"><span data-stu-id="d0196-128">Sending Data to the Server</span></span>  
 <span data-ttu-id="d0196-129">**SQL_SS_VARIANT**ein neuer Datentyp speziell für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber verwendet wird, wird für Daten verwendet, die an eine **sql_variant** Spalte gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="d0196-129">**SQL_SS_VARIANT**, a new data type specific to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, is used for data sent to an **sql_variant** column.</span></span> <span data-ttu-id="d0196-130">Beim Senden von Daten an den Server mit Parametern (z. b. Insert Into TableName Values (?,?)) wird [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) verwendet, um die Parameterinformationen anzugeben, einschließlich des C-Typs und des entsprechenden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Typs.</span><span class="sxs-lookup"><span data-stu-id="d0196-130">When sending data to the server using parameters (for example, INSERT INTO TableName VALUES (?,?)), [SQLBindParameter](../native-client-odbc-api/sqlbindparameter.md) is used to specify the parameter information including the C type and the corresponding [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type.</span></span> <span data-ttu-id="d0196-131">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber konvertiert den C-Datentyp in einen der entsprechenden **sql_variant** Untertypen.</span><span class="sxs-lookup"><span data-stu-id="d0196-131">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver will convert the C data type to one of the appropriate **sql_variant** subtypes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0196-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0196-132">See Also</span></span>  
 [<span data-ttu-id="d0196-133">Verarbeitungsergebnisse &#40;ODBC-&#41;</span><span class="sxs-lookup"><span data-stu-id="d0196-133">Processing Results &#40;ODBC&#41;</span></span>](processing-results-odbc.md)  
  
  
