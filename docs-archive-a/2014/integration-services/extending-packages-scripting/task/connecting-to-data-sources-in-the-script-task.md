---
title: Herstellen einer Verbindung mit Datenquellen im Skripttask | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
helpviewer_keywords:
- connections [Integration Services], scripts
- Integration Services packages, connections
- connection managers [Integration Services], scripts
- scripts [Integration Services], connections
- SSIS packages, connections
- packages [Integration Services], connections
- Script task [Integration Services], connections
- Connections property
- SQL Server Integration Services packages, connections
- SSIS Script task, connections
ms.assetid: 9c008380-715b-455b-9da7-22572d67c388
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 2c8374271c7972498361a83e4bbe87ad12265827
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700052"
---
# <a name="connecting-to-data-sources-in-the-script-task"></a><span data-ttu-id="05e0c-102">Herstellen einer Verbindung zu Datenquellen im Skripttask</span><span class="sxs-lookup"><span data-stu-id="05e0c-102">Connecting to Data Sources in the Script Task</span></span>
  <span data-ttu-id="05e0c-103">Verbindungs-Manager bieten Zugriff auf Datenquellen, die im Paket konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="05e0c-103">Connection managers provide access to data sources that have been configured in the package.</span></span> <span data-ttu-id="05e0c-104">Weitere Informationen finden Sie unter [Integration Services-Verbindungen &#40;SSIS&#41;](../../connection-manager/integration-services-ssis-connections.md).</span><span class="sxs-lookup"><span data-stu-id="05e0c-104">For more information, see [Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md).</span></span>  
  
 <span data-ttu-id="05e0c-105">Der Skripttask kann auf diese Verbindungs-Manager über die <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A>-Eigenschaft des **Dts**-Objekts zugreifen.</span><span class="sxs-lookup"><span data-stu-id="05e0c-105">The Script task can access these connection managers through the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> property of the **Dts** object.</span></span> <span data-ttu-id="05e0c-106">Jeder Verbindungs-Manager in der <xref:Microsoft.SqlServer.Dts.Runtime.Connections>-Auflistung speichert Informationen darüber, wie eine Verbindung mit der zugrunde liegenden Datenquelle hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="05e0c-106">Each connection manager in the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection stores information about how to connect to the underlying data source.</span></span>  
  
 <span data-ttu-id="05e0c-107">Wenn Sie die <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A>-Methode eines Verbindungs-Managers aufrufen, stellt der Verbindungs-Manager eine Verbindung zur Datenquelle her (falls diese nicht bereits besteht), und gibt die entsprechenden Verbindungsinformationen zur Verwendung im Skripttaskcode zurück.</span><span class="sxs-lookup"><span data-stu-id="05e0c-107">When you call the <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager.AcquireConnection%2A> method of a connection manager, the connection manager connects to the data source, if it is not already connected, and returns the appropriate connection or connection information for you to use in your Script task code.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="05e0c-108">Sie müssen den vom Verbindungs-Manager zurückgegebenen Verbindungstyp kennen, bevor Sie aufrufen `AcquireConnection` .</span><span class="sxs-lookup"><span data-stu-id="05e0c-108">You must know the type of connection returned by the connection manager before calling `AcquireConnection`.</span></span> <span data-ttu-id="05e0c-109">Da für den Skripttask `Option Strict` aktiviert ist, müssen Sie die Verbindung, die als `Object`-Typ zurückgegeben wird, vor ihrer Verwendung in den richtigen Verbindungstyp umwandeln.</span><span class="sxs-lookup"><span data-stu-id="05e0c-109">Because the Script task has `Option Strict` enabled, you must cast the connection, which is returned as type `Object`, to the appropriate connection type before you can use it.</span></span>  
  
 <span data-ttu-id="05e0c-110">Sie können die <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Contains%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Runtime.Connections>-Auflistung verwenden, die von der <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A>-Eigenschaft zurückgegeben wird, um nach einer vorhandenen Verbindung zu suchen, bevor Sie diese Verbindung im Code verwenden.</span><span class="sxs-lookup"><span data-stu-id="05e0c-110">You can use the <xref:Microsoft.SqlServer.Dts.Runtime.Connections.Contains%2A> method of the <xref:Microsoft.SqlServer.Dts.Runtime.Connections> collection returned by the <xref:Microsoft.SqlServer.Dts.Tasks.ScriptTask.ScriptObjectModel.Connections%2A> property to look for an existing connection before using the connection in your code.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="05e0c-111">Sie können die AcquireConnection-Methode von Verbindungs-Managern, die nicht verwaltete Objekte zurückgeben (z.B. der OLE DB-Verbindungs-Manager und der Excel-Verbindungs-Manager) nicht im verwalteten Code eines Skripttasks aufrufen.</span><span class="sxs-lookup"><span data-stu-id="05e0c-111">You cannot call the AcquireConnection method of connection managers that return unmanaged objects, such as the OLE DB connection manager and the Excel connection manager, in the managed code of a Script task.</span></span> <span data-ttu-id="05e0c-112">Sie können jedoch die ConnectionString-Eigenschaft dieser Verbindungs-Manager lesen und direkt im Code eine Verbindung mit der Datenquelle herstellen, indem Sie die Verbindungs Zeichenfolge mit einem `OledbConnection` aus dem **System. Data. OleDb** -Namespace verwenden.</span><span class="sxs-lookup"><span data-stu-id="05e0c-112">However, you can read the ConnectionString property of these connection managers, and connect to the data source directly in your code by using the connection string with an `OledbConnection` from the **System.Data.OleDb** namespace.</span></span>  
>   
>  <span data-ttu-id="05e0c-113">Wenn Sie die AcquireConnection-Methode eines Verbindungs-Managers aufrufen müssen, der nicht verwaltete Objekte zurückgibt, verwenden Sie einen [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]-Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="05e0c-113">If you must call the AcquireConnection method of a connection manager that returns an unmanaged object, use an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager.</span></span> <span data-ttu-id="05e0c-114">Wenn Sie den [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]-Verbindungs-Manager zur Verwendung eines OLE DB-Anbieters konfigurieren, stellt er über den [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)]-Datenanbieter für OLE DB eine Verbindung her.</span><span class="sxs-lookup"><span data-stu-id="05e0c-114">When you configure the [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager to use an OLE DB provider, it connects by using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] Data Provider for OLE DB.</span></span> <span data-ttu-id="05e0c-115">In diesem Fall gibt die AcquireConnection-Methode `System.Data.OleDb.OleDbConnection` anstelle eines nicht verwalteten Objekts zurück.</span><span class="sxs-lookup"><span data-stu-id="05e0c-115">In this case, the AcquireConnection method returns a `System.Data.OleDb.OleDbConnection` instead of an unmanaged object.</span></span> <span data-ttu-id="05e0c-116">Zur Konfiguration eines [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]-Verbindungs-Managers zur Verwendung mit einer Excel-Datenquelle wählen Sie den [!INCLUDE[msCoName](../../../includes/msconame-md.md)] OLE DB-Anbieter für Jet aus, geben eine Excel-Datei an und geben dann `Excel 8.0` (für Excel 97 und höher) als Wert für **Erweiterte Eigenschaften** auf der Seite **Alle** des Dialogfelds **Verbindungs-Manager** ein.</span><span class="sxs-lookup"><span data-stu-id="05e0c-116">To configure an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager for use with an Excel data source, select the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] OLE DB Provider for Jet, specify an Excel file, and enter `Excel 8.0` (for Excel 97 and later) as the value of **Extended Properties** on the **All** page of the **Connection Manager** dialog box.</span></span>  
  
## <a name="connections-example"></a><span data-ttu-id="05e0c-117">Verbindungsbeispiel</span><span class="sxs-lookup"><span data-stu-id="05e0c-117">Connections Example</span></span>  
 <span data-ttu-id="05e0c-118">Im folgenden Beispiel wird veranschaulicht, wie Verbindungs-Manager innerhalb des Skripttasks aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="05e0c-118">The following example demonstrates how to access connection managers from within the Script task.</span></span> <span data-ttu-id="05e0c-119">In diesem Beispiel wird davon ausgegangen, dass Sie einen [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]-Verbindungs-Manager namens **Test ADO.NET Connection** und einen Verbindungs-Manager für Flatfiles namens **Test Flat File Connection** erstellt und konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="05e0c-119">The sample assumes that you have created and configured an [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager named **Test ADO.NET Connection** and a Flat File connection manager named **Test Flat File Connection**.</span></span> <span data-ttu-id="05e0c-120">Beachten Sie, dass der [!INCLUDE[vstecado](../../../includes/vstecado-md.md)]-Verbindungs-Manager ein `SqlConnection`-Objekt zurückgibt, das Sie sofort zur Verbindung mit der Datenquelle verwenden können.</span><span class="sxs-lookup"><span data-stu-id="05e0c-120">Note that the [!INCLUDE[vstecado](../../../includes/vstecado-md.md)] connection manager returns a `SqlConnection` object that you can use immediately to connect to the data source.</span></span> <span data-ttu-id="05e0c-121">Der Verbindungs-Manager für Flatfiles gibt im Gegensatz dazu nur eine Zeichenfolge mit Pfad und Dateinamen zurück.</span><span class="sxs-lookup"><span data-stu-id="05e0c-121">The Flat File connection manager, on the other hand, returns only a string that contains the path and file name.</span></span> <span data-ttu-id="05e0c-122">Sie müssen Methoden aus dem `System.IO`-Namespace verwenden, um die Flatfile zu öffnen und mit ihr zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="05e0c-122">You must use methods from the `System.IO` namespace to open and work with the flat file.</span></span>  
  
```vb  
Public Sub Main()  
  
    Dim myADONETConnection As SqlClient.SqlConnection  
    myADONETConnection = _  
        DirectCast(Dts.Connections("Test ADO.NET Connection").AcquireConnection(Dts.Transaction), _  
        SqlClient.SqlConnection)  
    MsgBox(myADONETConnection.ConnectionString, _  
        MsgBoxStyle.Information, "ADO.NET Connection")  
  
    Dim myFlatFileConnection As String  
    myFlatFileConnection = _  
        DirectCast(Dts.Connections("Test Flat File Connection").AcquireConnection(Dts.Transaction), _  
        String)  
    MsgBox(myFlatFileConnection, MsgBoxStyle.Information, "Flat File Connection")  
  
    Dts.TaskResult = ScriptResults.Success  
  
End Sub  
```  
  
```csharp  
using System;  
using System.Data.SqlClient;  
using Microsoft.SqlServer.Dts.Runtime;  
using System.Windows.Forms;  
  
public class ScriptMain  
{  
  
        public void Main()  
        {  
            SqlConnection myADONETConnection = new SqlConnection();  
            myADONETConnection = (SqlConnection)(Dts.Connections["Test ADO.NET Connection"].AcquireConnection(Dts.Transaction)as SqlConnection);  
            MessageBox.Show(myADONETConnection.ConnectionString, "ADO.NET Connection");  
  
            string myFlatFileConnection;  
            myFlatFileConnection = (string)(Dts.Connections["Test Flat File Connection"].AcquireConnection(Dts.Transaction) as String);  
            MessageBox.Show(myFlatFileConnection, "Flat File Connection");  
  
            Dts.TaskResult = (int)ScriptResults.Success;  
  
        }  
  
}  
  
```  
  
<span data-ttu-id="05e0c-123">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="05e0c-123">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="05e0c-124">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="05e0c-124">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="05e0c-125">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="05e0c-125">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="05e0c-126">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="05e0c-126">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05e0c-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05e0c-127">See Also</span></span>  
 <span data-ttu-id="05e0c-128">[Integration Services &#40;SSIS-&#41; Verbindungen](../../connection-manager/integration-services-ssis-connections.md) </span><span class="sxs-lookup"><span data-stu-id="05e0c-128">[Integration Services &#40;SSIS&#41; Connections](../../connection-manager/integration-services-ssis-connections.md) </span></span>  
 [<span data-ttu-id="05e0c-129">Erstellen von Verbindungs-Managern</span><span class="sxs-lookup"><span data-stu-id="05e0c-129">Create Connection Managers</span></span>](../../create-connection-managers.md)  
  
  
