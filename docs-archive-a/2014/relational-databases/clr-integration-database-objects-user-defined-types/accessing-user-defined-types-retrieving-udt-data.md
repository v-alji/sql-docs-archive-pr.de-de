---
title: Abrufen von UDT-Daten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: clr
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SqlDataReader object
- ADO.NET [CLR integration]
- binding UDTs [CLR integration]
- UDTs [CLR integration], ADO.NET
- assemblies [CLR integration], user-defined types
- query parameters [CLR integration]
- user-defined types [CLR integration], ADO.NET
- bytes [CLR integration]
ms.assetid: 6a98ac8c-0e69-4c03-83a4-2062cb782049
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9133ea45069f76e7590f6b74d3c1e1cb98c7bc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619879"
---
# <a name="retrieving-udt-data"></a><span data-ttu-id="d7ebe-102">Abrufen von UDT-Daten</span><span class="sxs-lookup"><span data-stu-id="d7ebe-102">Retrieving UDT Data</span></span>
  <span data-ttu-id="d7ebe-103">Zum Erstellen eines benutzerdefinierten Typs (User-Defined Type, UDT) auf dem Client muss die zuvor in einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbank als UDT registrierte Assembly für die Clientanwendung verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-103">In order to create a user-defined type (UDT) on the client, the assembly that was registered as a UDT in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database must be available to the client application.</span></span> <span data-ttu-id="d7ebe-104">Die UDT-Assembly kann in dasselbe Verzeichnis gelegt werden wie die Anwendung oder in den globalen Assemblycache (GAC).</span><span class="sxs-lookup"><span data-stu-id="d7ebe-104">The UDT assembly can be placed in the same directory with the application, or in the Global Assembly Cache (GAC).</span></span> <span data-ttu-id="d7ebe-105">Sie können auch in Ihrem Projekt einen Verweis auf die Assembly festlegen.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-105">You can also set a reference to the assembly in your project.</span></span>  
  
## <a name="requirements-for-using-udts-in-adonet"></a><span data-ttu-id="d7ebe-106">Anforderungen zum Verwenden von UDTs in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d7ebe-106">Requirements for Using UDTs in ADO.NET</span></span>  
 <span data-ttu-id="d7ebe-107">Die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] geladene Assembly und die Assembly auf dem Client müssen kompatibel sein, damit der UDT auf dem Client erstellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-107">The assembly loaded in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and the assembly on the client must be compatible in order for the UDT to be created on the client.</span></span> <span data-ttu-id="d7ebe-108">Bei mit dem `Native`-Serialisierungsformat definierten UDTs müssen die Assemblys strukturell kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-108">For UDTs defined with the `Native` serialization format, the assemblies must be structurally compatible.</span></span> <span data-ttu-id="d7ebe-109">Bei mit dem `UserDefined`-Format definierten Assemblys muss die Assembly auf dem Client verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-109">For assemblies defined with the `UserDefined` format, the assembly must be available on the client.</span></span>  
  
 <span data-ttu-id="d7ebe-110">Sie brauchen keine Kopie der UDT-Assembly auf dem Client, um die Rohdaten aus einer UDT-Spalte einer Tabelle abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-110">You do not need a copy of the UDT assembly on the client in order to retrieve the raw data from a UDT column in a table.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7ebe-111">**SqlClient** kann beim Laden eines UDTs im Fall von nicht übereinstimmenden UDT-Versionen oder anderen Problemen einen UDT möglicherweise nicht laden.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-111">**SqlClient** may fail to load a UDT in the event of mismatched UDT versions or other problems.</span></span> <span data-ttu-id="d7ebe-112">Wenden Sie in diesem Fall die üblichen Maßnahmen zur Problembehandlung an, um zu ermitteln, aus welchem Grund die Assembly, die den UDT enthält, nicht von der aufrufenden Anwendung gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-112">In this case, use regular troubleshooting mechanisms to determine why the assembly containing the UDT cannot be found by the calling application.</span></span> <span data-ttu-id="d7ebe-113">Weitere Informationen finden Sie im Thema "Diagnostizieren von Fehlern mit Assistenten für verwaltetes Debuggen" in der .NET Framework-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-113">For more information, read the topic titled "Diagnosing Errors with Managed Debugging Assistants" in the .NET Framework documentation.</span></span>  
  
## <a name="accessing-udts-with-a-sqldatareader"></a><span data-ttu-id="d7ebe-114">UDT-Zugriff über SqlDataReader</span><span class="sxs-lookup"><span data-stu-id="d7ebe-114">Accessing UDTs with a SqlDataReader</span></span>  
 <span data-ttu-id="d7ebe-115">`System.Data.SqlClient.SqlDataReader` kann im Client-Code verwendet werden, um ein Resultset mit einer UDT-Spalte abzurufen, die als Instanz des Objekts verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-115">A `System.Data.SqlClient.SqlDataReader` can be used from client code to retrieve a result set that contains a UDT column, which is exposed as an instance of the object.</span></span>  
  
### <a name="example"></a><span data-ttu-id="d7ebe-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7ebe-116">Example</span></span>  
 <span data-ttu-id="d7ebe-117">Dieses Beispiel zeigt, wie Sie die `Main`-Methode verwenden, um ein neues `SqlDataReader`-Objekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-117">This example shows how to use the `Main` method to create a new `SqlDataReader` object.</span></span> <span data-ttu-id="d7ebe-118">In diesem Codebeispiel werden die folgenden Aktionen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="d7ebe-118">The following actions occur within the code example:</span></span>  
  
1.  <span data-ttu-id="d7ebe-119">Die Main-Methode erstellt ein neues `SqlDataReader`-Objekt und ruft die Werte aus der Points-Tabelle ab. Diese Tabelle enthält eine UDT-Spalte namens Point.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-119">The Main method creates a new `SqlDataReader` object and retrieves the values from the Points table, which has a UDT column named Point.</span></span>  
  
2.  <span data-ttu-id="d7ebe-120">Der Point-UDT macht die als ganze Zahlen definierten X- und Y-Koordinaten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-120">The Point UDT exposes X and Y coordinates defined as integers.</span></span>  
  
3.  <span data-ttu-id="d7ebe-121">Der UDT definiert eine `Distance`-Methode und eine `GetDistanceFromXY`-Methode.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-121">The UDT defines a `Distance` method and a `GetDistanceFromXY` method.</span></span>  
  
4.  <span data-ttu-id="d7ebe-122">Der Beispielcode ruft die Werte des Primärschlüssels und der UDT-Spalten ab, um die Möglichkeiten des UDT darzustellen.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-122">The sample code retrieves the values of the primary key and UDT columns in order to demonstrate the capabilities of the UDT.</span></span>  
  
5.  <span data-ttu-id="d7ebe-123">Der Beispielcode ruft die `Point.Distance`-Methode und die `Point.GetDistanceFromXY`-Methode auf.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-123">The sample code calls the `Point.Distance` and `Point.GetDistanceFromXY` methods.</span></span>  
  
6.  <span data-ttu-id="d7ebe-124">Die Ergebnisse werden im Konsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-124">The results are displayed in the console window.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7ebe-125">Die Anwendung muss bereits einen Verweis auf die UDT-Assembly aufweisen.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-125">The application must already have a reference to the UDT assembly.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
  
Module ReadPoints  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Retrieve the value of the UDT  
                Dim pnt As Point = CType(rdr(1), Point)  
  
             ' You can also use GetSqlValue and GetValue  
             ' Dim pnt As Point = CType(rdr.GetSqlValue(1), Point)  
             ' Dim pnt As Point = CType(rdr.GetValue(1), Point)  
  
                ' Print values  
                Console.WriteLine( _  
                 "ID={0} Point={1} X={2} Y={3} DistanceFromXY={4} Distance={5}", _  
                  id, pnt, pnt.X, pnt.Y, pnt.DistanceFromXY(1, 9), pnt.Distance())  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
         & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
  
namespace Microsoft.Samples.SqlServer  
{  
class ReadPoints  
{  
static void Main()  
{  
  string connectionString = GetConnectionString();  
  using (SqlConnection cnn = new SqlConnection(connectionString))  
  {  
    cnn.Open();  
    SqlCommand cmd = new SqlCommand(  
       "SELECT ID, Pnt FROM dbo.Points", cnn);  
    SqlDataReader rdr = cmd.ExecuteReader();  
  
    while (rdr.Read())  
    {  
      // Retrieve the value of the Primary Key column  
      int id = rdr.GetInt32(0);  
  
        // Retrieve the value of the UDT  
        Point pnt = (Point)rdr[1];  
  
        // You can also use GetSqlValue and GetValue  
        // Point pnt = (Point)rdr.GetSqlValue(1);  
        // Point pnt = (Point)rdr.GetValue(1);  
  
        Console.WriteLine(  
        "ID={0} Point={1} X={2} Y={3} DistanceFromXY={4} Distance={5}",   
        id, pnt, pnt.X, pnt.Y, pnt.DistanceFromXY(1, 9), pnt.Distance());  
    }  
  rdr.Close();  
  Console.WriteLine("done");  
  }  
  static private string GetConnectionString()  
  {  
    // To avoid storing the connection string in your code,   
    // you can retrieve it from a configuration file.  
    return "Data Source=(local);Initial Catalog=AdventureWorks;"  
        + "Integrated Security=SSPI";  
  }  
}  
```  
  
## <a name="binding-udts-as-bytes"></a><span data-ttu-id="d7ebe-126">Bindung von UDTs als Bytes</span><span class="sxs-lookup"><span data-stu-id="d7ebe-126">Binding UDTs as Bytes</span></span>  
 <span data-ttu-id="d7ebe-127">In bestimmten Situationen bietet es sich an, Rohdaten aus der UDT-Spalte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-127">In some situations, you may want to retrieve the raw data from the UDT column.</span></span> <span data-ttu-id="d7ebe-128">Möglicherweise ist der Typ lokal nicht verfügbar, oder Sie möchten keine Instanz des UDT instanziieren.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-128">Perhaps the type is not available locally, or you do not wish to instantiate an instance of the UDT.</span></span> <span data-ttu-id="d7ebe-129">Sie können die Rohbytes in ein Bytearray lesen, indem Sie die **GetBytes** -Methode eines verwenden `SqlDataReader` .</span><span class="sxs-lookup"><span data-stu-id="d7ebe-129">You can read the raw bytes into a byte array using the **GetBytes** method of a `SqlDataReader`.</span></span> <span data-ttu-id="d7ebe-130">Diese Methode liest, beginnend am angegeben Pufferoffset, einen Datenstrom von Bytes aus dem angegebenen Spaltenoffset in den Puffer eines Arrays.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-130">This method reads a stream of bytes from the specified column offset into the buffer of an array starting at a specified buffer offset.</span></span> <span data-ttu-id="d7ebe-131">Eine andere Möglichkeit besteht darin, eine der **GetSqlBytes** -oder **GetSqlBinary** -Methoden zu verwenden und den gesamten Inhalt in einem einzelnen Vorgang zu lesen.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-131">Another option is to use one of the **GetSqlBytes** or **GetSqlBinary** methods and read all of the contents in a single operation.</span></span> <span data-ttu-id="d7ebe-132">In keinem der beiden Fälle wird das UDT-Objekt instanziiert. Daher brauchen Sie in der Client-Assembly keinen Verweis auf den UDT festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-132">In either case, the UDT object is never instantiated, so you do not need to set a reference to the UDT in the client assembly.</span></span>  
  
### <a name="example"></a><span data-ttu-id="d7ebe-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7ebe-133">Example</span></span>  
 <span data-ttu-id="d7ebe-134">In diesem Beispiel wird gezeigt, wie die **Punkt** Daten als Rohbytes in ein Bytearray mithilfe eines abgerufen werden `SqlDataReader` .</span><span class="sxs-lookup"><span data-stu-id="d7ebe-134">This example shows how to retrieve the **Point** data as raw bytes into a byte array using a `SqlDataReader`.</span></span> <span data-ttu-id="d7ebe-135">Der Code verwendet ein `System.Text.StringBuilder`-Objekt, um die Rohbytes in eine Zeichenfolgendarstellung zu konvertieren, die im Konsolenfenster angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-135">The code uses a `System.Text.StringBuilder` to convert the raw bytes to a string representation to be displayed in the console window.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Text  
  
Module GetRawBytes  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Retrieve the raw bytes into a byte array  
                Dim buffer(31) As Byte  
                Dim byteCount As Integer = _  
                 CInt(rdr.GetBytes(1, 0, buffer, 0, 31))  
  
                ' Format and print bytes   
                Dim str As New StringBuilder  
                str.AppendFormat("ID={0} Point=", id)  
  
                Dim i As Integer  
                For i = 0 To (byteCount - 1)  
                    str.AppendFormat("{0:x}", buffer(i))  
                Next  
                Console.WriteLine(str.ToString)  
  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Text;  
  
class GetRawBytes  
{  
    static void Main()  
    {  
        string connectionString = GetConnectionString();  
        using (SqlConnection cnn = new SqlConnection(connectionString))  
        {  
            cnn.Open();  
            SqlCommand cmd = new SqlCommand("SELECT ID, Pnt FROM dbo.Points", cnn);  
            SqlDataReader rdr = cmd.ExecuteReader();  
  
            while (rdr.Read())  
            {  
                // Retrieve the value of the Primary Key column  
                int id = rdr.GetInt32(0);  
  
                // Retrieve the raw bytes into a byte array  
                byte[] buffer = new byte[32];  
                long byteCount = rdr.GetBytes(1, 0, buffer, 0, 32);  
  
                // Format and print bytes   
                StringBuilder str = new StringBuilder();  
                str.AppendFormat("ID={0} Point=", id);  
  
                for (int i = 0; i < byteCount; i++)  
                    str.AppendFormat("{0:x}", buffer[i]);  
                Console.WriteLine(str.ToString());  
            }  
            rdr.Close();  
            Console.WriteLine("done");  
        }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
### <a name="example-using-getsqlbytes"></a><span data-ttu-id="d7ebe-136">Beispiel: Verwenden von GetSqlBytes</span><span class="sxs-lookup"><span data-stu-id="d7ebe-136">Example Using GetSqlBytes</span></span>  
 <span data-ttu-id="d7ebe-137">In diesem Beispiel wird gezeigt, wie die **Punkt** Daten als Rohdaten Bytes in einem einzelnen Vorgang mithilfe der **gezqlbytes** -Methode abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-137">This example shows how to retrieve the **Point** data as raw bytes in a single operation using the **GetSqlBytes** method.</span></span> <span data-ttu-id="d7ebe-138">Der Code verwendet ein `StringBuilder`-Objekt, um die Rohbytes in eine Zeichenfolgendarstellung zu konvertieren, die im Konsolenfenster angezeigt werden kann.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-138">The code uses a `StringBuilder` to convert the raw bytes to a string representation to be displayed in the console window.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
Imports System.Data.SqlTypes  
Imports System.Text  
  
Module GetRawBytes  
    Sub Main()  
        Dim connectionString As String = GetConnectionString()  
        Using cnn As New SqlConnection(connectionString)  
            cnn.Open()  
            Dim cmd As New SqlCommand( _  
             "SELECT ID, Pnt FROM dbo.Points", cnn)  
            Dim rdr As SqlDataReader  
            rdr = cmd.ExecuteReader  
  
            While rdr.Read()  
                ' Retrieve the value of the Primary Key column  
                Dim id As Int32 = rdr.GetInt32(0)  
  
                ' Use SqlBytes to retrieve raw bytes  
                Dim sb As SqlBytes = rdr.GetSqlBytes(1)  
                Dim byteCount As Long = sb.Length  
  
                ' Format and print bytes   
                Dim str As New StringBuilder  
                str.AppendFormat("ID={0} Point=", id)  
  
                Dim i As Integer  
                For i = 0 To (byteCount - 1)  
                    str.AppendFormat("{0:x}", sb(i))  
                Next  
                Console.WriteLine(str.ToString)  
  
            End While  
            rdr.Close()  
            Console.WriteLine("done")  
        End Using  
    End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data.Sql;  
using System.Data.SqlClient;  
using System.Data.SqlTypes;  
using System.Text;  
  
class GetRawBytes  
{  
    static void Main()  
    {  
         string connectionString = GetConnectionString();  
        using (SqlConnection cnn = new SqlConnection(connectionString))  
        {  
            cnn.Open();  
            SqlCommand cmd = new SqlCommand(  
                "SELECT ID, Pnt FROM dbo.Points", cnn);  
            SqlDataReader rdr = cmd.ExecuteReader();  
  
            while (rdr.Read())  
            {  
                // Retrieve the value of the Primary Key column  
                int id = rdr.GetInt32(0);  
  
                // Use SqlBytes to retrieve raw bytes  
                SqlBytes sb = rdr.GetSqlBytes(1);  
                long byteCount = sb.Length;  
  
                // Format and print bytes   
                StringBuilder str = new StringBuilder();  
                str.AppendFormat("ID={0} Point=", id);  
  
                for (int i = 0; i < byteCount; i++)  
                    str.AppendFormat("{0:x}", sb[i]);  
                Console.WriteLine(str.ToString());  
            }  
            rdr.Close();  
            Console.WriteLine("done");  
        }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
## <a name="working-with-udt-parameters"></a><span data-ttu-id="d7ebe-139">Arbeiten mit UDT-Parametern</span><span class="sxs-lookup"><span data-stu-id="d7ebe-139">Working with UDT Parameters</span></span>  
 <span data-ttu-id="d7ebe-140">UDTs können im ADO.NET-Code sowohl als Eingabe- als auch als Ausgabeparameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-140">UDTs can be used as both input and output parameters in your ADO.NET code.</span></span>  
  
## <a name="using-udts-in-query-parameters"></a><span data-ttu-id="d7ebe-141">Verwenden von UDTs in Abfrageparametern</span><span class="sxs-lookup"><span data-stu-id="d7ebe-141">Using UDTs in Query Parameters</span></span>  
 <span data-ttu-id="d7ebe-142">UDTs können beim Festlegen eines `SqlParameter`-Objekts für ein `System.Data.SqlClient.SqlCommand`-Objekt als Parameterwerte verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-142">UDTs can be used as parameter values when setting up a `SqlParameter` for a `System.Data.SqlClient.SqlCommand` object.</span></span> <span data-ttu-id="d7ebe-143">Die `SqlDbType.Udt`-Enumeration eines `SqlParameter`-Objekts wird beim Aufrufen der `Add`-Methode für die `Parameters` Auflistung verwendet, um anzuzeigen, dass der Parameter ein UDT ist.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-143">The `SqlDbType.Udt` enumeration of a `SqlParameter` object is used to indicate that the parameter is a UDT when calling the `Add` method to the `Parameters` collection.</span></span> <span data-ttu-id="d7ebe-144">Die- `UdtTypeName` Eigenschaft eines- `SqlCommand` Objekts wird verwendet, um den voll qualifizierten Namen des UDT in der Datenbank mithilfe der *Database. schema_name. object_name* -Syntax anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-144">The `UdtTypeName` property of a `SqlCommand` object is used to specify the fully qualified name of the UDT in the database using the *database.schema_name.object_name* syntax.</span></span> <span data-ttu-id="d7ebe-145">Die Angabe des vollqualifizierten Namens ist zwar nicht erforderlich, macht den Code jedoch klarer.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-145">Although it is not required, using the fully qualified name removes ambiguity from your code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d7ebe-146">Eine lokale Kopie der UDT-Assembly muss dem Clientprojekt zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-146">A local copy of the UDT assembly must be available to the client project.</span></span>  
  
### <a name="example"></a><span data-ttu-id="d7ebe-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d7ebe-147">Example</span></span>  
 <span data-ttu-id="d7ebe-148">In diesem Beispielcode wird ein `SqlCommand`-Objekt und ein `SqlParameter`-Objekt erstellt, um Daten in eine UDT-Spalte in einer Tabelle einzufügen.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-148">The code in this example creates `SqlCommand` and `SqlParameter` objects to insert data into a UDT column in a table.</span></span> <span data-ttu-id="d7ebe-149">Der Code verwendet die `SqlDbType.Udt`-Enumeration, um den Datentyp anzugeben, und die `UdtTypeName`-Eigenschaft des `SqlParameter`-Objekts, um den vollqualifizierten Namen des UDT in der Datenbank anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d7ebe-149">The code uses the `SqlDbType.Udt` enumeration to specify the data type, and the `UdtTypeName` property of the `SqlParameter` object to specify the fully qualified name of the UDT in the database.</span></span>  
  
```vb  
Option Explicit On  
Option Strict On  
  
Imports System  
Imports system.Data  
Imports System.Data.Sql  
Imports System.Data.SqlClient  
  
Module Module1  
  
  Sub Main()  
    Dim ConnectionString As String = GetConnectionString()  
    Dim cnn As New SqlConnection(ConnectionString)  
    Using cnn  
      Dim cmd As SqlCommand = cnn.CreateCommand()  
      cmd.CommandText = "INSERT INTO dbo.Points (Pnt) VALUES (@Point)"  
      cmd.CommandType = CommandType.Text  
  
      Dim param As New SqlParameter("@Point", SqlDbType.Udt)      param.UdtTypeName = "TestPoint.dbo.Point"      param.Direction = ParameterDirection.Input      param.Value = New Point(5, 6)      cmd.Parameters.Add(param)  
  
      cnn.Open()  
      cmd.ExecuteNonQuery()  
      Console.WriteLine("done")  
    End Using  
  End Sub  
    Private Function GetConnectionString() As String  
        ' To avoid storing the connection string in your code,    
        ' you can retrieve it from a configuration file.  
        Return "Data Source=(local);Initial Catalog=AdventureWorks;" _  
           & "Integrated Security=SSPI;"  
    End Function  
End Module  
```  
  
```csharp  
using System;  
using System.Data;  
using System.Data.Sql;  
using System.Data.SqlClient;  
  
class Class1  
{  
static void Main()  
{  
  string ConnectionString = GetConnectionString();  
     using (SqlConnection cnn = new SqlConnection(ConnectionString))  
     {  
       SqlCommand cmd = cnn.CreateCommand();  
       cmd.CommandText =   
         "INSERT INTO dbo.Points (Pnt) VALUES (@Point)";  
       cmd.CommandType = CommandType.Text;  
  
       SqlParameter param = new SqlParameter("@Point", SqlDbType.Udt);       param.UdtTypeName = "TestPoint.dbo.Point";       param.Direction = ParameterDirection.Input;       param.Value = new Point(5, 6);       cmd.Parameters.Add(param);  
  
       cnn.Open();  
       cmd.ExecuteNonQuery();  
       Console.WriteLine("done");  
     }  
    static private string GetConnectionString()  
    {  
        // To avoid storing the connection string in your code,   
        // you can retrieve it from a configuration file.  
        return "Data Source=(local);Initial Catalog=AdventureWorks;"  
            + "Integrated Security=SSPI";  
    }  
  }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7ebe-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d7ebe-150">See Also</span></span>  
 [<span data-ttu-id="d7ebe-151">Zugreifen auf benutzerdefinierte Typen in ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d7ebe-151">Accessing User-Defined Types in ADO.NET</span></span>](accessing-user-defined-types-in-ado-net.md)  
  
  
