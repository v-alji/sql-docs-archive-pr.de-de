---
title: Entfernen einer Instanz von SQL Server aus dem SQL Server-Hilfsprogramm | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.utility.remove.f1
ms.assetid: ae1d126a-46d2-47bf-b339-17c743df6491
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 6c09897fcd3ac6d82308288391cf54176eef49d9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622635"
---
# <a name="remove-an-instance-of-sql-server-from-the-sql-server-utility"></a><span data-ttu-id="b5f8f-102">Entfernen einer Instanz von SQL Server aus dem SQL Server-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="b5f8f-102">Remove an Instance of SQL Server from the SQL Server Utility</span></span>
  <span data-ttu-id="b5f8f-103">Führen Sie die folgenden Schritte aus, um eine verwaltete Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-103">Use the following steps to remove a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="b5f8f-104">Mit diesem Verfahren wird die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus der UCP-Listenansicht entfernt und die Datensammlung des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramms beendet.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-104">This procedure removes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the UCP list view and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection stops.</span></span> <span data-ttu-id="b5f8f-105">Die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird nicht deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-105">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not uninstalled.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="b5f8f-106">Bevor Sie eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mithilfe dieses Verfahrens aus dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm entfernen können, stellen Sie sicher, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und SQL Server-Agent-Dienste auf der zu entfernenden Instanz ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-106">Before you use this procedure to remove an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility, make sure that the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and SQL Server Agent services are running on the instance to remove.</span></span>  
  
1.  <span data-ttu-id="b5f8f-107">Klicken Sie im Hilfsprogramm-Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]auf **Verwaltete Instanzen**.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-107">From the Utility Explorer in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], click on **Managed Instances**.</span></span> <span data-ttu-id="b5f8f-108">Achten Sie im Inhaltsbereich des Hilfsprogramm-Explorers auf die Listenansicht verwalteter [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanzen.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-108">Observe the list view of managed instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in the Utility Explorer content pane.</span></span>  
  
2.  <span data-ttu-id="b5f8f-109">Wählen Sie in der Spalte **Name der SQL Server-Instanz** der Listenansicht die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz aus, die aus dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm entfernt werden soll.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-109">In the **SQL Server Instance Name** column of the list view, select the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance to remove from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="b5f8f-110">Klicken Sie mit der rechten Maustaste auf die zu entfernende Instanz, und wählen Sie **Verwaltete Instanz entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-110">Right-click on the instance to remove, and select **Remove Managed Instance...**.</span></span>  
  
3.  <span data-ttu-id="b5f8f-111">Geben Sie Anmeldeinformationen mit Administratorrechten für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz an: Klicken Sie auf **Verbinden**, überprüfen Sie die Informationen im Dialogfeld **Verbindung mit Server herstellen**, und klicken Sie dann auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-111">Specify credentials with administrator privileges for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]: Click **Connect...**, verify the information in the **Connect to Server** dialog box, then click **Connect**.</span></span> <span data-ttu-id="b5f8f-112">Sie sehen die Anmeldeinformationen im Dialogfeld **Verwaltete Instanz entfernen** .</span><span class="sxs-lookup"><span data-stu-id="b5f8f-112">You will see the login information on the **Remove Managed Instance** dialog.</span></span>  
  
4.  <span data-ttu-id="b5f8f-113">Um das Entfernen zu bestätigen, klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-113">To confirm the operation, click **OK**.</span></span> <span data-ttu-id="b5f8f-114">Um den Vorgang zu beenden, klicken Sie auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-114">To quit the operation, click **Cancel**.</span></span>  
  
## <a name="manually-remove-a-managed-instance-of-sql-server-from-a-sql-server-utility"></a><span data-ttu-id="b5f8f-115">Manuelles Entfernen einer verwalteten Instanz von SQL Server aus einem SQL Server-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="b5f8f-115">Manually Remove a Managed Instance of SQL Server from a SQL Server Utility</span></span>  
 <span data-ttu-id="b5f8f-116">Mit diesem Verfahren wird die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus der UCP-Listenansicht entfernt und die Datensammlung des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramms beendet.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-116">This procedure removes the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the UCP list view and stops [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility data collection.</span></span> <span data-ttu-id="b5f8f-117">Die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird nicht deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-117">The instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is not uninstalled.</span></span>  
  
 <span data-ttu-id="b5f8f-118">So verwenden Sie PowerShell, um eine verwaltete Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-118">To use PowerShell to remove a managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="b5f8f-119">Dieses Skript führt die folgenden Vorgänge aus:</span><span class="sxs-lookup"><span data-stu-id="b5f8f-119">This script performs the following operations:</span></span>  
  
-   <span data-ttu-id="b5f8f-120">Ruft den UCP nach dem Serverinstanznamen ab.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-120">Gets the UCP by server instance name.</span></span>  
  
-   <span data-ttu-id="b5f8f-121">Entfernt die verwaltete Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus dem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-121">Removes the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span>  
  
```powershell
# Get Ucp connection  
$UcpServerInstanceName = "ComputerName\InstanceName";  
$UtilityInstance = new-object -Type Microsoft.SqlServer.Management.Smo.Server $UcpServerInstanceName;  
$UcpConnection = new-object -Type Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection $UtilityInstance.ConnectionContext.SqlConnectionObject;  
$Utility = [Microsoft.SqlServer.Management.Utility.Utility]::Connect($UcpConnection);  
  
# Now remove the ManagedInstance from the SQL Server Utility  
$ServerInstanceName = "ComputerName\InstanceName";  
$Instance = new-object -Type Microsoft.SqlServer.Management.Smo.Server $ServerInstanceName;  
$InstanceConnection = new-object -Type Microsoft.SqlServer.Management.Sdk.Sfc.SqlStoreConnection $Instance.ConnectionContext.SqlConnectionObject;  
$ManagedInstance = $Utility.ManagedInstances[$ServerInstanceName];  
$ManagedInstance.Remove($InstanceConnection);  
```  
  
<span data-ttu-id="b5f8f-122">Es ist wichtig, auf den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instanznamen genau so zu verweisen, wie er in gespeichert ist [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b5f8f-122">It's important to refer to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance name exactly as it is stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="b5f8f-123">Bei einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], bei der Groß-/Kleinschreibung beachtet wird, müssen Sie den Instanznamen mit genau der Groß-/Kleinschreibung angeben, die von @@SERVERNAME zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-123">On a case-sensitive instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you must specify the instance name using the exact casing as returned by @@SERVERNAME.</span></span> 

<span data-ttu-id="b5f8f-124">Um den Instanznamen für die verwaltete Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]abzurufen, führen Sie die folgende Abfrage für die verwaltete Instanz aus:</span><span class="sxs-lookup"><span data-stu-id="b5f8f-124">To get the instance name for the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], run this query on the managed instance:</span></span>  
  
```sql
select @@SERVERNAME AS instance_name  
```  
  
 <span data-ttu-id="b5f8f-125">An diesem Punkt wird die verwaltete Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vollständig aus dem UCP entfernt.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-125">At this point, the managed instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is fully removed from the UCP.</span></span> <span data-ttu-id="b5f8f-126">Sie wird nicht mehr in der Listenansicht angezeigt, wenn Sie das nächste Mal Daten für das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Hilfsprogramm aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-126">It disappears from the list view the next time you refresh data for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Utility.</span></span> <span data-ttu-id="b5f8f-127">Das Ergebnis ist genauso, als würde ein Benutzer den Vorgang zum Entfernen verwalteter Instanzen erfolgreich in der SSMS-Benutzeroberfläche abschließen.</span><span class="sxs-lookup"><span data-stu-id="b5f8f-127">This state is identical to a user successfully going through the remove managed instance operation in the SSMS user interface.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5f8f-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5f8f-128">See Also</span></span>  
 <span data-ttu-id="b5f8f-129">[Verwenden des Hilfsprogramm-Explorers zum Verwalten des SQL Server-Hilfsprogramms](use-utility-explorer-to-manage-the-sql-server-utility.md) </span><span class="sxs-lookup"><span data-stu-id="b5f8f-129">[Use Utility Explorer to Manage the SQL Server Utility](use-utility-explorer-to-manage-the-sql-server-utility.md) </span></span>  
 [<span data-ttu-id="b5f8f-130">Problembehandlung beim SQL Server-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="b5f8f-130">Troubleshoot the SQL Server Utility</span></span>](../../database-engine/troubleshoot-the-sql-server-utility.md)  
