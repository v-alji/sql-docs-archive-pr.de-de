---
title: Warnung zur Client seitigen Verwendung von Geometry, Geography und hierarchyid | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: 500ee6b3-2154-45d2-a3cf-8760166d9413
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 66898aa056800c0a7573b5afa73762785706ff7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617407"
---
# <a name="warning-about-client-side-usage-of-geometry-geography-and-hierarchyid"></a><span data-ttu-id="c741b-102">Warnung zur clientseitigen Verwendung von GEOMETRY, GEOGRAPHY und HIERARCHYID</span><span class="sxs-lookup"><span data-stu-id="c741b-102">Warning about client side usage of GEOMETRY, GEOGRAPHY and HIERARCHYID</span></span>
  <span data-ttu-id="c741b-103">Die Assembly **Microsoft.SqlServer.Types.dll**, die die räumlichen Datentypen enthält, wurde von Version 10,0 auf Version 11,0 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c741b-103">The assembly **Microsoft.SqlServer.Types.dll**, which contains the spatial data types, has been upgraded from version 10.0 to version 11.0.</span></span> <span data-ttu-id="c741b-104">Benutzerdefinierte Anwendungen, die auf diese Assembly verweisen, schlagen möglicherweise fehl, wenn bestimmte Bedingungen den Wert "true" aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c741b-104">Custom applications that reference this assembly may fail when certain conditions are true.</span></span>  
  
## <a name="component"></a><span data-ttu-id="c741b-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="c741b-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="description"></a><span data-ttu-id="c741b-106">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c741b-106">Description</span></span>  
 <span data-ttu-id="c741b-107">Die Assembly **Microsoft.SqlServer.Types.dll**, die die räumlichen Datentypen enthält, wurde von Version 10,0 auf Version 11,0 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="c741b-107">The assembly **Microsoft.SqlServer.Types.dll**, which contains the spatial data types, has been upgraded from version 10.0 to version 11.0.</span></span> <span data-ttu-id="c741b-108">Benutzerdefinierte Anwendungen, die auf diese Assembly verweisen, schlagen möglicherweise fehl, wenn die folgenden Bedingungen den Wert "true" aufweisen.</span><span class="sxs-lookup"><span data-stu-id="c741b-108">Custom applications that reference this assembly may fail when the following conditions are true.</span></span>  
  
-   <span data-ttu-id="c741b-109">Wenn Sie eine benutzerdefinierte Anwendung von einem Computer, auf dem [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] installiert wurde, auf einen Computer verschieben, auf dem nur [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installiert ist, schlägt die Anwendung fehl, da die referenzierte Version 10,0 der **SqlTypes** -Assembly nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="c741b-109">When you move a custom application from a computer on which [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] was installed to a computer on which only [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] is installed, the application will fail because the referenced version 10.0 of the **SqlTypes** assembly is not present.</span></span> <span data-ttu-id="c741b-110">Möglicherweise wird folgende Fehlermeldung angezeigt: `"Could not load file or assembly 'Microsoft.SqlServer.Types, Version=10.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The system cannot find the file specified."`</span><span class="sxs-lookup"><span data-stu-id="c741b-110">You may see this error message: `"Could not load file or assembly 'Microsoft.SqlServer.Types, Version=10.0.0.0, Culture=neutral, PublicKeyToken=89845dcd8080cc91' or one of its dependencies. The system cannot find the file specified."`</span></span>  
  
-   <span data-ttu-id="c741b-111">Wenn Sie auf die Version 11,0 der **SqlTypes** -Assembly verweisen und Version 10,0 ebenfalls installiert ist, wird möglicherweise die folgende Fehlermeldung angezeigt:`"System.InvalidCastException: Unable to cast object of type 'Microsoft.SqlServer.Types.SqlGeometry' to type 'Microsoft.SqlServer.Types.SqlGeometry'."`</span><span class="sxs-lookup"><span data-stu-id="c741b-111">When you reference the **SqlTypes** assembly version 11.0, and version 10.0 is also installed, you may see this error message: `"System.InvalidCastException: Unable to cast object of type 'Microsoft.SqlServer.Types.SqlGeometry' to type 'Microsoft.SqlServer.Types.SqlGeometry'."`</span></span>  
  
-   <span data-ttu-id="c741b-112">Wenn Sie von einer benutzerdefinierten Anwendung, die auf .NET 3,5, 4 oder 4,5 ausgerichtet ist, auf die **SqlTypes** -Assemblyversion 11,0 verweisen, schlägt die Anwendung fehl, da SqlClient nach dem Entwurf Version 10,0 der Assembly lädt.</span><span class="sxs-lookup"><span data-stu-id="c741b-112">When you reference the **SqlTypes** assembly version 11.0 from a custom application that targets .NET 3.5, 4, or 4.5, the application will fail because SqlClient by design loads version 10.0 of the assembly.</span></span> <span data-ttu-id="c741b-113">Dieser Fehler tritt auf, wenn die Anwendung eine der folgenden Methoden aufruft:</span><span class="sxs-lookup"><span data-stu-id="c741b-113">This failure occurs when the application calls one of the following methods:</span></span>  
  
    -   <span data-ttu-id="c741b-114">`GetValue`-Methode der `SqlDataReader`-Klasse</span><span class="sxs-lookup"><span data-stu-id="c741b-114">`GetValue` method of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="c741b-115">`GetValues`-Methode der `SqlDataReader`-Klasse</span><span class="sxs-lookup"><span data-stu-id="c741b-115">`GetValues` method of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="c741b-116">Klammerindexoperator [] der `SqlDataReader`-Klasse</span><span class="sxs-lookup"><span data-stu-id="c741b-116">bracket index operator [] of the `SqlDataReader` class</span></span>  
  
    -   <span data-ttu-id="c741b-117">`ExecuteScalar`-Methode der `SqlCommand`-Klasse</span><span class="sxs-lookup"><span data-stu-id="c741b-117">`ExecuteScalar` method of the `SqlCommand` class</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="c741b-118">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="c741b-118">Corrective Action</span></span>  
 <span data-ttu-id="c741b-119">Sie können dieses Problem mithilfe einer der folgenden Methoden umgehen:</span><span class="sxs-lookup"><span data-stu-id="c741b-119">You can work around this issue by using one of the following methods:</span></span>  
  
-   <span data-ttu-id="c741b-120">Sie können dieses Problem im Code umgehen, indem Sie anstelle der oben aufgeführten Get-Methoden die `GetSqlBytes`-Methode aufrufen, um CLR-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Systemtypen abzurufen. Hierzu ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c741b-120">You can work around this issue in your code by calling the `GetSqlBytes` method, instead of the Get methods listed above, to retrieve CLR [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system types, as shown in the following example:</span></span>  
  
    ```csharp  
    string query = "SELECT [SpatialColumn] FROM [SpatialTable]";  
          using (SqlConnection conn = new SqlConnection("..."))  
          {  
                SqlCommand cmd = new SqlCommand(query, conn);  
  
                conn.Open();  
                SqlDataReader reader = cmd.ExecuteReader();  
  
                while (reader.Read())  
                {  
                      // In version 11.0 only  
                      SqlGeometry g =   
    SqlGeometry.Deserialize(reader.GetSqlBytes(0));  
  
                      // In version 10.0 or 11.0  
                      SqlGeometry g2 = new SqlGeometry();  
                      g.Read(new BinaryReader(reader.GetSqlBytes(0).Stream));  
                }  
          }  
    ```  
  
-   <span data-ttu-id="c741b-121">Sie können dieses Problem umgehen, indem Sie eine Assemblyumleitung in der Anwendungskonfigurationsdatei verwenden. Siehe folgendes Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c741b-121">You can work around this issue by using assembly redirection in the application configuration file, as shown in the following example:</span></span>  
  
    ```xml  
    <assemblyBinding xmlns="urn:schemas-microsoft-com:asm.v1">  
        ...  
        <dependentAssembly>  
            <assemblyIdentity name="Microsoft.SqlServer.Types" publicKeyToken="89845dcd8080cc91" culture="neutral" />  
            <bindingRedirect oldVersion="10.0.0.0" newVersion="11.0.0.0" />  
        </dependentAssembly>  
        ...  
    </assemblyBinding>  
    ```  
  
-   <span data-ttu-id="c741b-122">Sie können dieses Problem in der Verbindungszeichenfolge umgehen, indem Sie den Wert "SQL Server 2012" für das Attribut "Typsystemversion" angeben, um SqlClient zu zwingen, Version 11.0 der Assembly zu laden.</span><span class="sxs-lookup"><span data-stu-id="c741b-122">You can work around this issue in your connection string by specifying a value of "SQL Server 2012" for the "Type System Version" attribute to force SqlClient to load version 11.0 of the assembly.</span></span> <span data-ttu-id="c741b-123">Dieses Verbindungszeichenfolgenattribut ist erst ab .NET 4.5 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c741b-123">This connection string attribute is available only in .NET 4.5 and above.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c741b-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c741b-124">See Also</span></span>  
 <span data-ttu-id="c741b-125">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="c741b-125">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="c741b-126">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="c741b-126">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md
)  
  
  
