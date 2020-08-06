---
title: Daten Bank Darstellung (tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 16a233fb-f83b-4ca1-acb5-6186eca0a62c
author: minewiskan
ms.author: owend
ms.openlocfilehash: c327e07685e98e6fa9f992025510e869d909e5ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616229"
---
# <a name="database-representationtabular"></a><span data-ttu-id="1752c-102">Datenbankdarstellung (tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="1752c-102">Database Representation(Tabular)</span></span>
  <span data-ttu-id="1752c-103">Im tabellarischen Modus ist die Datenbank der Container für alle Objekte im tabellarischen Modell.</span><span class="sxs-lookup"><span data-stu-id="1752c-103">In Tabular Mode, the database is the container for all objects in the tabular model.</span></span>  
  
## <a name="database-representation"></a><span data-ttu-id="1752c-104">Datenbankdarstellung</span><span class="sxs-lookup"><span data-stu-id="1752c-104">Database Representation</span></span>  
 <span data-ttu-id="1752c-105">Die Datenbank ist die Stelle, an der sich alle Objekte befinden, die ein tabellarisches Modell bilden.</span><span class="sxs-lookup"><span data-stu-id="1752c-105">The database is the place where all objects that form a tabular model reside.</span></span> <span data-ttu-id="1752c-106">In der Datenbank findet der Entwickler Objekte wie Verbindungen, Tabellen, Rollen u.v.m. vor.</span><span class="sxs-lookup"><span data-stu-id="1752c-106">Contained by the database, the developer finds objects like connections, tables, roles and many more.</span></span>  
  
### <a name="database-in-amo"></a><span data-ttu-id="1752c-107">Datenbank in AMO</span><span class="sxs-lookup"><span data-stu-id="1752c-107">Database in AMO</span></span>  
 <span data-ttu-id="1752c-108">Wenn eine tabellarische Modelldatenbank mithilfe von AMO verwaltet wird, entspricht das <xref:Microsoft.AnalysisServices.Database>-Objekt in AMO 1:1 dem logischen Datenbankobjekt in einem tabellarischen Modell.</span><span class="sxs-lookup"><span data-stu-id="1752c-108">When using AMO to manage a tabular model database, the <xref:Microsoft.AnalysisServices.Database> object in AMO matches one-to-one the database logical object in a tabular model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1752c-109">Um Zugriff auf ein Datenbankobjekt in AMO zu erhalten, benötigt der Benutzer Zugriff auf ein Serverobjekt und muss eine Verbindung damit herstellen.</span><span class="sxs-lookup"><span data-stu-id="1752c-109">In order to gain access to a database object, in AMO, the user needs to have access to a server object and connect to it.</span></span>  
  
### <a name="database-in-adomdnet"></a><span data-ttu-id="1752c-110">Datenbank in ADOMD.Net</span><span class="sxs-lookup"><span data-stu-id="1752c-110">Database in ADOMD.Net</span></span>  
 <span data-ttu-id="1752c-111">Wenn ADOMD verwendet wird, um eine tabellarische Modelldatenbank abzufragen, wird die Verbindung mit einer bestimmten Datenbank durch das <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection>-Objekt erreicht.</span><span class="sxs-lookup"><span data-stu-id="1752c-111">When using ADOMD to consult and query a tabular model database, connection to a specific database is obtained through the <xref:Microsoft.AnalysisServices.AdomdClient.AdomdConnection> object.</span></span>  
  
 <span data-ttu-id="1752c-112">Mit dem folgenden Codeabschnitt können Sie direkt eine Verbindung zu einer bestimmten Datenbank herstellen:</span><span class="sxs-lookup"><span data-stu-id="1752c-112">You can connect directly to a certain database using the following code snippet:</span></span>  
  
```csharp  
using ADOMD = Microsoft.AnalysisServices.AdomdClient;  
...  
   ADOMD.AdomdConnection currrentCnx = new ADOMD.AdomdConnection("Data Source=<<server\instance>>;Catalog=<<database>>");  
   currrentCnx.Open();  
...  
  
```  
  
 <span data-ttu-id="1752c-113">Über ein vorhandenes Verbindungsobjekt (das nicht geschlossen wurde) können Sie auch von der aktuellen Datenbank zu einer anderen Datenbank wechseln, wie im folgenden Codeausschnitt gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1752c-113">Also, over an existing connection object (that hasn't been closed), you can change the current database to another as shown in the following code snippet:</span></span>  
  
```csharp  
currentCnx.ChangeDatabase("myOtherDatabase");  
  
```  
  
## <a name="database-in-amo"></a><span data-ttu-id="1752c-114">Datenbank in AMO</span><span class="sxs-lookup"><span data-stu-id="1752c-114">Database in AMO</span></span>  
 <span data-ttu-id="1752c-115">Wenn Sie AMO verwenden, um ein Datenbankobjekt zu verwalten, beginnen Sie mit einem <xref:Microsoft.AnalysisServices.Server>-Objekt.</span><span class="sxs-lookup"><span data-stu-id="1752c-115">When using AMO to manage a database object, start with a <xref:Microsoft.AnalysisServices.Server> object.</span></span> <span data-ttu-id="1752c-116">Suchen Sie dann Ihre Datenbank in der Datenbankauflistung, oder erstellen Sie eine neue Datenbank, indem Sie sie der Auflistung hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1752c-116">Then search for your database in the databases collection or create a new database by adding one to the collection.</span></span>  
  
 <span data-ttu-id="1752c-117">Der folgende Code Ausschnitt zeigt die Schritte zum Herstellen einer Verbindung mit einem Server und zum Erstellen einer leeren Datenbank nach der Überprüfung, dass die Datenbank nicht vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="1752c-117">The following code snippet shows the steps to connect to a server and create an empty database, after checking the database doesn't exist:</span></span>  
  
```  
  
AMO.Server CurrentServer = new AMO.Server();  
try  
{  
    CurrentServer.Connect(currentServerName);  
}  
catch (Exception cnxException)  
{  
    MessageBox.Show(string.Format("Error while trying to connect to server: [{0}]\nError message: {1}", currentServerName, cnxException.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
    return;  
}  
newDatabaseName = DatabaseName.Text;  
if (CurrentServer.Databases.Contains(newDatabaseName))  
{  
    return;  
}  
try  
{  
    AMO.Database newDatabase = CurrentServer.Databases.Add(newDatabaseName);  
  
    CurrentServer.Update();  
}  
catch (Exception createDBxc)  
{  
    MessageBox.Show(String.Format("Database [{0}] couldn't be created.\n{1}", newDatabaseName, createDBxc.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Error);  
    newDatabaseAvailable = false;  
}  
  
```  
  
 <span data-ttu-id="1752c-118">Um ein praktisches Verständnis für die Verwendung von AMO zur Erstellung und Bearbeitung von Datenbankdarstellungen zu gewinnen, können Sie den Quellcode im Tabular AMO 2012-Beispiel einsehen. Prüfen Sie insbesondere die Quelldatei: Database.cs.</span><span class="sxs-lookup"><span data-stu-id="1752c-118">For a practical understanding on how to use AMO to create and manipulate database representations, see source code in the Tabular AMO 2012 sample; specifically check in the following source file: Database.cs.</span></span> <span data-ttu-id="1752c-119">Beispielcode wird nur zur Verdeutlichung der hier erläuterten logischen Konzepte bereitgestellt und sollte nicht in einer Produktionsumgebung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1752c-119">Sample code is provided only as a support to the logical concepts explained here, and should not be used in a production environment.</span></span>  
  
  
