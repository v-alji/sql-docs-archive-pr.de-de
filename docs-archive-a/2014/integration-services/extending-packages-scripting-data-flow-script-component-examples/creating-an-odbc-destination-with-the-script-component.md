---
title: Erstellen eines ODBC-Ziels mit der Skriptkomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- Script component [Integration Services], destination components
- ODBC destination [Integration Services]
- destinations [Integration Services], components
- Script component [Integration Services], examples
ms.assetid: d198c866-78f4-4a50-ae15-333160645815
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 10adff11a7e1db24d9a244c3e83949a010b606c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619219"
---
# <a name="creating-an-odbc-destination-with-the-script-component"></a><span data-ttu-id="0d94c-102">Erstellen eines ODBC-Ziels mit der Skriptkomponente</span><span class="sxs-lookup"><span data-stu-id="0d94c-102">Creating an ODBC Destination with the Script Component</span></span>
  <span data-ttu-id="0d94c-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] werden Daten in der Regel mithilfe eines [!INCLUDE[vstecado](../../includes/vstecado-md.md)]-Ziels und des [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Datenanbieters für ODBC in einem ODBC-Ziel gespeichert.</span><span class="sxs-lookup"><span data-stu-id="0d94c-103">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)], you typically save data to an ODBC destination by using an [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination and the [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider for ODBC.</span></span> <span data-ttu-id="0d94c-104">Sie können jedoch auch ein Ad-hoc-ODBC-Ziel für die Verwendung in einem einzelnen Paket erstellen.</span><span class="sxs-lookup"><span data-stu-id="0d94c-104">However, you can also create an ad hoc ODBC destination for use in a single package.</span></span> <span data-ttu-id="0d94c-105">Zur Erstellung dieses Ad-hoc-ODBC-Ziels verwenden Sie die Skriptkomponente, wie in dem folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="0d94c-105">To create this ad hoc ODBC destination, you use the Script component as shown in the following example.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0d94c-106">Wenn Sie eine Komponente erstellen möchten, die Sie einfacher in mehreren Datenflusstasks und Paketen wiederverwenden können, empfiehlt es sich, den Code in diesem Skriptkomponentenbeispiel als Ausgangspunkt für eine benutzerdefinierte Datenflusskomponente zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0d94c-106">If you want to create a component that you can more easily reuse across multiple Data Flow tasks and multiple packages, consider using the code in this Script component sample as the starting point for a custom data flow component.</span></span> <span data-ttu-id="0d94c-107">Weitere Informationen finden Sie unter [Entwickeln einer benutzerdefinierten Datenflusskomponente](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="0d94c-107">For more information, see [Developing a Custom Data Flow Component](../extending-packages-custom-objects/data-flow/developing-a-custom-data-flow-component.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0d94c-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0d94c-108">Example</span></span>  
 <span data-ttu-id="0d94c-109">Im folgenden Beispiel wird veranschaulicht, wie eine Zielkomponente erstellt wird, die einen vorhandenen ODBC-Verbindungs-Manager zum Speichern von Daten aus dem Datenfluss in einer [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d94c-109">The following example demonstrates how to create a destination component that uses an existing ODBC connection manager to save data from the data flow into a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>  
  
 <span data-ttu-id="0d94c-110">Dieses Beispiel ist eine modifizierte Version des benutzerdefinierten [!INCLUDE[vstecado](../../includes/vstecado-md.md)]-Ziels, das im Thema [Erstellen eines Ziels mit der Skriptkomponente](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md) veranschaulicht wurde.</span><span class="sxs-lookup"><span data-stu-id="0d94c-110">This example is a modified version of the custom [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination that was demonstrated in the topic, [Creating a Destination with the Script Component](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md).</span></span> <span data-ttu-id="0d94c-111">In diesem Beispiel wurde das benutzerdefinierte [!INCLUDE[vstecado](../../includes/vstecado-md.md)]-Ziel jedoch so geändert, dass es mit einem ODBC-Verbindungs-Manager funktioniert und Daten in einem ODBC-Ziel speichert.</span><span class="sxs-lookup"><span data-stu-id="0d94c-111">However, in this example, the custom [!INCLUDE[vstecado](../../includes/vstecado-md.md)] destination has been modified to work with an ODBC connection manager and save data to an ODBC destination.</span></span> <span data-ttu-id="0d94c-112">Die Modifizierungen umfassen die folgenden Änderungen:</span><span class="sxs-lookup"><span data-stu-id="0d94c-112">These modifications also include the following changes:</span></span>  
  
-   <span data-ttu-id="0d94c-113">Sie können die `AcquireConnection`-Methode des ODBC-Verbindungs-Managers nicht aus verwaltetem Code aufrufen, da dadurch ein systemeigenes Objekt zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0d94c-113">You cannot call the `AcquireConnection` method of the ODBC connection manager from managed code, because it returns a native object.</span></span> <span data-ttu-id="0d94c-114">In diesem Beispiel wird daher die Verbindungszeichenfolge des Verbindungs-Managers verwendet, um eine direkte Verbindung mit der Datenquelle mithilfe des verwalteten ODBC-[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]-Datenanbieters herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0d94c-114">Therefore, this sample uses the connection string of the connection manager to connect to the data source directly by using the managed ODBC [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Data Provider.</span></span>  
  
-   <span data-ttu-id="0d94c-115">Von `OdbcCommand` werden Positionsparameter erwartet.</span><span class="sxs-lookup"><span data-stu-id="0d94c-115">The `OdbcCommand` expects positional parameters.</span></span> <span data-ttu-id="0d94c-116">Die Position von Parametern wird durch die Fragezeichen (?) im Text des Befehls angegeben.</span><span class="sxs-lookup"><span data-stu-id="0d94c-116">The positions of the parameters are indicated by the question marks (?) in the text of the command.</span></span> <span data-ttu-id="0d94c-117">(Im Gegensatz dazu werden von `SqlCommand` benannte Parameter erwartet.)</span><span class="sxs-lookup"><span data-stu-id="0d94c-117">(In contrast, a `SqlCommand` expects named parameters.)</span></span>  
  
 <span data-ttu-id="0d94c-118">In diesem Beispiel wird die Tabelle **Person.Address** in der **AdventureWorks**-Beispieldatenbank verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d94c-118">This example uses the **Person.Address** table in the **AdventureWorks** sample database.</span></span> <span data-ttu-id="0d94c-119">Im Beispiel werden die erste und die vierte Spalte, die Spalten **int \* adressssid**\* und **nvarchar (30) City** , durch den Datenfluss weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="0d94c-119">The example passes the first and fourth columns, the **int\*AddressID**\* and **nvarchar(30)City** columns, of this table through the data flow.</span></span> <span data-ttu-id="0d94c-120">Die gleichen Daten werden in den Beispielen für die Quelle, die Transformation und das Ziel im Thema [Developing Specific Types of Script Components](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md) (Entwickeln bestimmter Typen von Skriptkomponenten) verwendet.</span><span class="sxs-lookup"><span data-stu-id="0d94c-120">This same data is used in the source, transformation, and destination samples in the topic, [Developing Specific Types of Script Components](../extending-packages-scripting-data-flow-script-component-types/developing-specific-types-of-script-components.md).</span></span>  
  
#### <a name="to-configure-this-script-component-example"></a><span data-ttu-id="0d94c-121">So konfigurieren Sie dieses Skriptkomponentenbeispiel</span><span class="sxs-lookup"><span data-stu-id="0d94c-121">To configure this Script Component example</span></span>  
  
1.  <span data-ttu-id="0d94c-122">Erstellen Sie einen ODBC-Verbindungs-Manager, der eine Verbindung mit der **AdventureWorks**-Datenbank herstellt.</span><span class="sxs-lookup"><span data-stu-id="0d94c-122">Create an ODBC connection manager that connects to the **AdventureWorks** database.</span></span>  
  
2.  <span data-ttu-id="0d94c-123">Erstellen Sie eine Zieltabelle, indem Sie den folgenden Transact-SQL-Befehl in der **AdventureWorks**-Datenbank ausführen:</span><span class="sxs-lookup"><span data-stu-id="0d94c-123">Create a destination table by running the following Transact-SQL command in the **AdventureWorks** database:</span></span>  
  
    ```  
    CREATE TABLE [Person].[Address2]([AddressID] [int] NOT NULL,  
        [City] [nvarchar](30) NOT NULL)  
    ```  
  
3.  <span data-ttu-id="0d94c-124">Fügen Sie der Oberfläche des Datenfluss-Designers eine neue Skriptkomponente hinzu, und konfigurieren Sie sie als Ziel.</span><span class="sxs-lookup"><span data-stu-id="0d94c-124">Add a new Script component to the Data Flow designer surface and configure it as a destination.</span></span>  
  
4.  <span data-ttu-id="0d94c-125">Verbinden Sie die Ausgabe einer Upstreamquelle oder Transformation mit der Zielkomponente im [!INCLUDE[ssIS](../../includes/ssis-md.md)]-Designer.</span><span class="sxs-lookup"><span data-stu-id="0d94c-125">Connect the output of an upstream source or transformation to the destination component in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer.</span></span> <span data-ttu-id="0d94c-126">(Sie können eine Quelle ohne Transformationen direkt mit einem Ziel verbinden.) Um sicherzustellen, dass dieses Beispiel funktioniert, muss die Ausgabe der Upstreamkomponente zumindest die Spalten **AddressID** und **City** aus der **Person.Address**-Tabelle der **AdventureWorks**-Beispieldatenbank enthalten.</span><span class="sxs-lookup"><span data-stu-id="0d94c-126">(You can connect a source directly to a destination without any transformations.) To ensure that this sample works, the output of the upstream component must include at least the **AddressID** and **City** columns from the **Person.Address** table of the **AdventureWorks** sample database.</span></span>  
  
5.  <span data-ttu-id="0d94c-127">Öffnen Sie den **Transformations-Editor für Skripterstellung**.</span><span class="sxs-lookup"><span data-stu-id="0d94c-127">Open the **Script Transformation Editor**.</span></span> <span data-ttu-id="0d94c-128">Wählen Sie auf der Seite **Eingabespalten** die Spalten **AddressID** und **City** aus.</span><span class="sxs-lookup"><span data-stu-id="0d94c-128">On the **Input Columns** page, select the **AddressID** and **City** columns.</span></span>  
  
6.  <span data-ttu-id="0d94c-129">Geben Sie der Eingabe auf der Seite **Eingaben und Ausgaben** einen aussagekräftigeren Namen, z.B. **MyAddressInput**.</span><span class="sxs-lookup"><span data-stu-id="0d94c-129">On the **Inputs and Outputs** page, rename the input with a more descriptive name such as **MyAddressInput**.</span></span>  
  
7.  <span data-ttu-id="0d94c-130">Fügen Sie auf der Seite **Verbindungs-Manager** den ODBC-Verbindungs-Manager hinzu, oder erstellen Sie diesen, und geben Sie ihm einen aussagekräftigen Namen, z.B. **MyODBCConnectionManager**.</span><span class="sxs-lookup"><span data-stu-id="0d94c-130">On the **Connection Managers** page, add or create the ODBC connection manager with a descriptive name such as **MyODBCConnectionManager**.</span></span>  
  
8.  <span data-ttu-id="0d94c-131">Klicken Sie auf der Seite **Skript** auf **Skript bearbeiten**, und geben Sie dann das unten gezeigte Skript in der- `ScriptMain` Klasse ein.</span><span class="sxs-lookup"><span data-stu-id="0d94c-131">On the **Script** page, click **Edit Script**, and then enter the script shown below in the `ScriptMain` class.</span></span>  
  
9. <span data-ttu-id="0d94c-132">Schließen Sie anschließend die Skriptentwicklungsumgebung und den **Transformations-Editor für Skripterstellung**, und führen Sie das Beispiel aus.</span><span class="sxs-lookup"><span data-stu-id="0d94c-132">Close the script development environment, close the **Script Transformation Editor**, and then run the sample.</span></span>  
  
    ```vb  
    Imports System.Data.Odbc  
    ...  
    Public Class ScriptMain  
        Inherits UserComponent  
  
        Dim odbcConn As OdbcConnection  
        Dim odbcCmd As OdbcCommand  
        Dim odbcParam As OdbcParameter  
  
        Public Overrides Sub AcquireConnections(ByVal Transaction As Object)  
  
            Dim connectionString As String  
            connectionString = Me.Connections.MyODBCConnectionManager.ConnectionString  
            odbcConn = New OdbcConnection(connectionString)  
            odbcConn.Open()  
  
        End Sub  
  
        Public Overrides Sub PreExecute()  
  
            odbcCmd = New OdbcCommand("INSERT INTO Person.Address2(AddressID, City) " & _  
                "VALUES(?, ?)", odbcConn)  
            odbcParam = New OdbcParameter("@addressid", OdbcType.Int)  
            odbcCmd.Parameters.Add(odbcParam)  
            odbcParam = New OdbcParameter("@city", OdbcType.NVarChar, 30)  
            odbcCmd.Parameters.Add(odbcParam)  
  
        End Sub  
  
        Public Overrides Sub MyAddressInput_ProcessInputRow(ByVal Row As MyAddressInputBuffer)  
  
            With odbcCmd  
                .Parameters("@addressid").Value = Row.AddressID  
                .Parameters("@city").Value = Row.City  
                .ExecuteNonQuery()  
            End With  
  
        End Sub  
  
        Public Overrides Sub ReleaseConnections()  
  
            odbcConn.Close()  
  
        End Sub  
  
    End Class  
    ```  
  
    ```csharp  
    using System.Data.Odbc;  
    ...  
    public class ScriptMain :  
        UserComponent  
    {  
        OdbcConnection odbcConn;  
        OdbcCommand odbcCmd;  
        OdbcParameter odbcParam;  
  
        public override void AcquireConnections(object Transaction)  
        {  
  
            string connectionString;  
            connectionString = this.Connections.MyODBCConnectionManager.ConnectionString;  
            odbcConn = new OdbcConnection(connectionString);  
            odbcConn.Open();  
  
        }  
  
        public override void PreExecute()  
        {  
  
            odbcCmd = new OdbcCommand("INSERT INTO Person.Address2(AddressID, City) " +  
                "VALUES(?, ?)", odbcConn);  
            odbcParam = new OdbcParameter("@addressid", OdbcType.Int);  
            odbcCmd.Parameters.Add(odbcParam);  
            odbcParam = new OdbcParameter("@city", OdbcType.NVarChar, 30);  
            odbcCmd.Parameters.Add(odbcParam);  
  
        }  
  
        public override void MyAddressInput_ProcessInputRow(MyAddressInputBuffer Row)  
        {  
  
            {  
                odbcCmd.Parameters["@addressid"].Value = Row.AddressID;  
                odbcCmd.Parameters["@city"].Value = Row.City;  
                odbcCmd.ExecuteNonQuery();  
            }  
  
        }  
  
        public override void ReleaseConnections()  
        {  
  
            odbcConn.Close();  
  
        }  
    }  
    ```  
  
<span data-ttu-id="0d94c-133">![Integration Services Symbol (klein)](../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="0d94c-133">![Integration Services icon (small)](../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="0d94c-134">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="0d94c-134">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="0d94c-135">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="0d94c-135">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="0d94c-136">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0d94c-136">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d94c-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0d94c-137">See Also</span></span>  
 [<span data-ttu-id="0d94c-138">Creating a Destination with the Script Component (Erstellen eines Ziels mit der Skriptkomponente)</span><span class="sxs-lookup"><span data-stu-id="0d94c-138">Creating a Destination with the Script Component</span></span>](../extending-packages-scripting-data-flow-script-component-types/creating-a-destination-with-the-script-component.md)  
  
  
