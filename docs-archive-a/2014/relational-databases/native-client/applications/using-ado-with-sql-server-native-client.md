---
title: Verwenden von ADO mit SQL Server Native Client | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client, ADO
- data access [SQL Server Native Client], ADO
- ADO [SQL Server Native Client]
- SQLNCLI, ADO
ms.assetid: 118a7cac-4c0d-44fd-b63e-3d542932d239
author: rothja
ms.author: jroth
ms.openlocfilehash: ccd14432aa3541572467a4c651c1f48b1ac957f5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722705"
---
# <a name="using-ado-with-sql-server-native-client"></a><span data-ttu-id="f1a62-102">Verwenden von ADO mit SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="f1a62-102">Using ADO with SQL Server Native Client</span></span>
  <span data-ttu-id="f1a62-103">Um die Vorteile der in eingeführten neuen Funktionen [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] wie Multiple Active Result Sets (Mars), Abfrage Benachrichtigungen, benutzerdefinierte Typen (User-Defined Types, UDTs) oder den neuen **XML** -Datentyp zu nutzen, sollten vorhandene Anwendungen, die ActiveX Data Objects (ADO) verwenden, den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter als Datenzugriffs Anbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1a62-103">In order to take advantage of new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] such as multiple active result sets (MARS), query notifications, user-defined types (UDTs), or the new **xml** data type, existing applications that use ActiveX Data Objects (ADO) should use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider as their data access provider.</span></span>  
  
 <span data-ttu-id="f1a62-104">Wenn keine der neuen Funktionen von [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] erforderlich ist, dann ist es auch nicht notwendig, den OLE DB-Anbieter von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client zu verwenden. Sie können weiterhin mit dem aktuellen Datenzugriffsanbieter (in der Regel SQLOLEDB) arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f1a62-104">If you do not need to use any of the new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], there is no need to use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider; you can continue using your current data access provider, which is typically SQLOLEDB.</span></span> <span data-ttu-id="f1a62-105">Wenn Sie eine bestehende Anwendung erweitern und die neuen Funktionen von [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] verwenden müssen, dann sollten Sie den OLE DB-Anbieter von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1a62-105">If you are enhancing an existing application and you need to use the new features introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], you should use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1a62-106">Wenn Sie eine neue Anwendung entwickeln, wird empfohlen, über ADO.NET und den .NET Framework-Datenanbieter für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] statt über [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client auf die neuen Funktionen der letzten Versionen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f1a62-106">If you are developing a new application, it is recommended that you consider using ADO.NET and the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instead of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to access all the new features of recent versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f1a62-107">Weitere Informationen zum .NET Framework-Datenanbieter für [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] finden Sie in der .NET Framework-SDK-Dokumentation für ADO.NET.</span><span class="sxs-lookup"><span data-stu-id="f1a62-107">For more information about the .NET Framework Data Provider for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], see the .NET Framework SDK documentation for ADO.NET.</span></span>  
  
 <span data-ttu-id="f1a62-108">Damit ADO die neuen Funktionen der letzten Versionen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] nutzen kann, wurde der OLE DB-Anbieter von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, der die Kernfunktionen von OLE DB erweitert, um einige Erweiterungen ergänzt.</span><span class="sxs-lookup"><span data-stu-id="f1a62-108">To enable ADO to use new features of recent versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], some enhancements have been made to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider which extends the core features of OLE DB.</span></span> <span data-ttu-id="f1a62-109">Diese Erweiterungen erlauben es ADO-Anwendungen, neuere [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Features zu verwenden und zwei Datentypen zu verarbeiten, die in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] eingeführt wurden: **XML** und **UDT**.</span><span class="sxs-lookup"><span data-stu-id="f1a62-109">These enhancements allow ADO applications to use newer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] features and to consume two data types introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)]: **xml** and **udt**.</span></span> <span data-ttu-id="f1a62-110">Diese Erweiterungen machen sich auch Erweiterungen der Datentypen **varchar**, **nvarchar** und **varbinary** zunutze.</span><span class="sxs-lookup"><span data-stu-id="f1a62-110">These enhancements also exploit enhancements to the **varchar**, **nvarchar**, and **varbinary** data types.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="f1a62-111">Native Client fügt die Eigenschaft SSPROP_INIT_DATATYPECOMPATIBILITY Initialisierung der Eigenschaft DBPROPSET_SQLSERVERDBINIT hinzu, die für die Verwendung durch ADO-Anwendungen festgelegt wurde, damit die neuen Datentypen in einer mit ADO kompatiblen Methode verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="f1a62-111">Native Client adds the SSPROP_INIT_DATATYPECOMPATIBILITY initialization property to the DBPROPSET_SQLSERVERDBINIT property set for use by ADO applications so that the new data types are exposed in a way compatible with ADO.</span></span> <span data-ttu-id="f1a62-112">Außerdem [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] definiert der Native Client OLE DB-Anbieter auch ein neues Verbindungs Zeichenfolgen-Schlüsselwort mit dem Namen `DataTypeCompatibility` , das in der Verbindungs Zeichenfolge festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="f1a62-112">In addition, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider also defines a new connection string keyword named `DataTypeCompatibility` that is set in the connection string.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f1a62-113">Vorhandene ADO-Anwendungen können über den SQLOLEDB-Anbieter auf XML, UDT, umfangreiche Textwerte und Werte von Binärfeldern zugreifen und diese aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f1a62-113">Existing ADO applications can access and update XML, UDT, and large value text and binary field values using the SQLOLEDB provider.</span></span> <span data-ttu-id="f1a62-114">Die neuen größeren Datentypen **varchar(max)** , **nvarchar(max)** und **varbinary(max)** werden als die ADO-Typen **adLongVarChar**, **adLongVarWChar** bzw. **adLongVarBinary** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f1a62-114">The new larger **varchar(max)**, **nvarchar(max)**, and **varbinary(max)** data types are returned as the ADO types **adLongVarChar**, **adLongVarWChar** and **adLongVarBinary** respectively.</span></span> <span data-ttu-id="f1a62-115">XML-Spalten werden als **adLongVarChar** zurückgegeben, und UDT-Spalten werden als **adVarBinary** zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f1a62-115">XML columns are returned as **adLongVarChar**, and UDT columns are returned as **adVarBinary**.</span></span> <span data-ttu-id="f1a62-116">Wenn Sie jedoch den OLE DB-Anbieter von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client (SQLNCLI11) statt des SQLOLEDB-Anbieters verwenden, müssen Sie sicherstellen, dass das Schlüsselwort `DataTypeCompatibility` mit dem Wert "80" angegeben wird, damit die neuen Datentypen richtig den entsprechenden ADO-Datentypen zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="f1a62-116">However, if you use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider (SQLNCLI11) instead of SQLOLEDB, you need to make sure to set the `DataTypeCompatibility` keyword to "80" so that the new data types will map correctly to the ADO data types.</span></span>  
  
## <a name="enabling-sql-server-native-client-from-ado"></a><span data-ttu-id="f1a62-117">Aktivieren von SQL Server Native Client über ADO</span><span class="sxs-lookup"><span data-stu-id="f1a62-117">Enabling SQL Server Native Client from ADO</span></span>  
 <span data-ttu-id="f1a62-118">Um die Verwendung von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client zu ermöglichen, müssen ADO-Anwendungen die folgenden Schlüsselwörter in den Verbindungs Zeichenfolgen implementieren:</span><span class="sxs-lookup"><span data-stu-id="f1a62-118">To enable the usage of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, ADO applications will need to implement the following keywords in their connection strings:</span></span>  
  
-   `Provider=SQLNCLI11`  
  
-   `DataTypeCompatibility=80`  
  
 <span data-ttu-id="f1a62-119">Weitere Informationen zu den in Native Client unterstützten ADO-Verbindungs Zeichenfolgen-Schlüsselwörtern [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] finden [Sie unter Verwenden von Schlüssel SQL Server Native Client Wörtern für Verbindungs Zeichenfolgen](using-connection-string-keywords-with-sql-server-native-client.md)</span><span class="sxs-lookup"><span data-stu-id="f1a62-119">For more information about the ADO connections string keywords supported in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, see [Using Connection String Keywords with SQL Server Native Client](using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="f1a62-120">Im folgenden finden Sie ein Beispiel für das Einrichten einer ADO-Verbindungs Zeichenfolge, die vollständig für den Einsatz [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] von Native Client aktiviert ist, einschließlich der Aktivierung der Mars-Funktion:</span><span class="sxs-lookup"><span data-stu-id="f1a62-120">The following is an example of establishing an ADO connection string that is fully enabled to work with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, including the enabling of the MARS feature:</span></span>  
  
```  
Dim con As New ADODB.Connection  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;" _  
         & "MARS Connection=True;"  
con.Open  
```  
  
## <a name="examples"></a><span data-ttu-id="f1a62-121">Beispiele</span><span class="sxs-lookup"><span data-stu-id="f1a62-121">Examples</span></span>  
 <span data-ttu-id="f1a62-122">In den folgenden Abschnitten finden Sie Beispiele für die Verwendung von ADO mit dem [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="f1a62-122">The following sections provide examples of how you can use ADO with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider.</span></span>  
  
### <a name="retrieving-xml-column-data"></a><span data-ttu-id="f1a62-123">Abrufen von XML-Spaltendaten</span><span class="sxs-lookup"><span data-stu-id="f1a62-123">Retrieving XML Column Data</span></span>  
 <span data-ttu-id="f1a62-124">In diesem Beispiel wird ein Recordset verwendet, um die Daten aus einer XML-Spalte der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Beispieldatenbank **AdventureWorks** abzurufen und anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f1a62-124">In this example, a recordset is used to retrieve and display the data from an XML column in the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] **AdventureWorks** sample database.</span></span>  
  
```  
Dim con As New ADODB.Connection  
Dim rst As New ADODB.Recordset  
Dim sXMLResult As String  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _   
         & "DataTypeCompatibility=80;"  
  
con.Open  
  
' Get the xml data as a recordset.  
Set rst.ActiveConnection = con  
rst.Source = "SELECT AdditionalContactInfo FROM Person.Contact " _  
   & "WHERE AdditionalContactInfo IS NOT NULL"  
rst.Open  
  
' Display the data in the recordset.  
While (Not rst.EOF)  
   sXMLResult = rst.Fields("AdditionalContactInfo").Value  
   Debug.Print (sXMLResult)  
   rst.MoveNext  
End While  
  
con.Close  
Set con = Nothing  
```  
  
> [!NOTE]  
>  <span data-ttu-id="f1a62-125">Recordset-Filter werden bei XML-Spalten nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f1a62-125">Recordset filtering is not supported with XML columns.</span></span> <span data-ttu-id="f1a62-126">Wenn sie verwendet werden, wird ein Fehler zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f1a62-126">If used, an error will be returned.</span></span>  
  
### <a name="retrieving-udt-column-data"></a><span data-ttu-id="f1a62-127">Abrufen von UDT-Spaltendaten</span><span class="sxs-lookup"><span data-stu-id="f1a62-127">Retrieving UDT Column Data</span></span>  
 <span data-ttu-id="f1a62-128">In diesem Beispiel wird ein **Command**-Objekt verwendet, um eine SQL-Abfrage auszuführen, die einen UDT zurückgibt. Der UDT wird aktualisiert, und neue Daten werden anschließend wieder in die Datenbank eingefügt.</span><span class="sxs-lookup"><span data-stu-id="f1a62-128">In this example, a **Command** object is used to execute a SQL query that returns a UDT, the UDT data is updated, and then the new data is inserted back into the database.</span></span> <span data-ttu-id="f1a62-129">In diesem Beispiel wird davon ausgegangen, dass der UDT **Point** bereits in der Datenbank registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="f1a62-129">This example assumes that the **Point** UDT has already been registered in the database.</span></span>  
  
```  
Dim con As New ADODB.Connection  
Dim cmd As New ADODB.Command  
Dim rst As New ADODB.Recordset  
Dim strOldUDT As String  
Dim strNewUDT As String  
Dim aryTempUDT() As String  
Dim strTempID As String  
Dim i As Integer  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;"  
  
con.Open  
  
' Get the UDT value.  
Set cmd.ActiveConnection = con  
cmd.CommandText = "SELECT ID, Pnt FROM dbo.Points.ToString()"  
Set rst = cmd.Execute  
strTempID = rst.Fields(0).Value  
strOldUDT = rst.Fields(1).Value  
  
' Do something with the UDT by adding i to each point.  
arytempUDT = Split(strOldUDT, ",")  
i = 3  
strNewUDT = LTrim(Str(Int(aryTempUDT(0)) + i)) + "," + _  
   LTrim(Str(Int(aryTempUDT(1)) + i))  
  
' Insert the new value back into the database.  
cmd.CommandText = "UPDATE dbo.Points SET Pnt = '" + strNewUDT + _  
   "' WHERE ID = '" + strTempID + "'"  
cmd.Execute  
  
con.Close  
Set con = Nothing  
```  
  
### <a name="enabling-and-using-mars"></a><span data-ttu-id="f1a62-130">Aktivieren und Verwenden von MARS</span><span class="sxs-lookup"><span data-stu-id="f1a62-130">Enabling and Using MARS</span></span>  
 <span data-ttu-id="f1a62-131">In diesem Beispiel wird die Verbindungs Zeichenfolge erstellt, um Mars über den [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter zu aktivieren. Anschließend werden zwei Recordset-Objekte erstellt, um Sie mit derselben Verbindung auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f1a62-131">In this example, the connection string is constructed to enable MARS through the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, and then two recordset objects are created to execute using the same connection.</span></span>  
  
```  
Dim con As New ADODB.Connection  
  
con.ConnectionString = "Provider=SQLNCLI11;" _  
         & "Server=(local);" _  
         & "Database=AdventureWorks;" _   
         & "Integrated Security=SSPI;" _  
         & "DataTypeCompatibility=80;" _  
         & "MARS Connection=True;"  
con.Open  
  
Dim recordset1 As New ADODB.Recordset  
Dim recordset2 As New ADODB.Recordset  
  
Dim recordsaffected As Integer  
Set recordset1 =  con.Execute("SELECT * FROM Table1", recordsaffected, adCmdText)  
Set recordset2 =  con.Execute("SELECT * FROM Table2", recordsaffected, adCmdText)  
  
con.Close  
Set con = Nothing  
```  
  
 <span data-ttu-id="f1a62-132">In früheren Versionen des OLE DB-Anbieters hätte dieser Code bewirkt, dass für den zweiten Execute-Aufruf eine Standardverbindung erstellt wird, weil in diesen Versionen nur ein aktives Resultset pro Verbindung geöffnet werden konnte.</span><span class="sxs-lookup"><span data-stu-id="f1a62-132">In prior versions of the OLE DB provider, this code would cause an implicit connection to be created on the second execution because only one active set of results could be opened per a single connection.</span></span> <span data-ttu-id="f1a62-133">Weil die Standardverbindung nicht in den OLE DB-Verbindungspool aufgenommen wurde, bedeutete dies zusätzlichen Aufwand.</span><span class="sxs-lookup"><span data-stu-id="f1a62-133">Because the implicit connection was not pooled in the OLE DB connection pool this would cause additional overhead.</span></span> <span data-ttu-id="f1a62-134">Mit der Mars-Funktion, die vom [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-OLE DB-Anbieter verfügbar gemacht wird, erhalten Sie mehrere aktive Ergebnisse für die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="f1a62-134">With the MARS feature exposed by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider, you get multiple active results on the one connection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1a62-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f1a62-135">See Also</span></span>  
 [<span data-ttu-id="f1a62-136">Erstellen von Anwendungen mit SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="f1a62-136">Building Applications with SQL Server Native Client</span></span>](building-applications-with-sql-server-native-client.md)  
  
  
