---
title: OLE DB-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- OLE DB connection manager
- data sources [Integration Services], connections
- connection managers [Integration Services], OLE DB
- connections [Integration Services], OLE DB
ms.assetid: 91e3622e-4b1a-439a-80c7-a00b90d66979
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5431de956a1039c2978688982792f190b0abc544
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619265"
---
# <a name="ole-db-connection-manager"></a><span data-ttu-id="4b686-102">OLE DB-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="4b686-102">OLE DB Connection Manager</span></span>
  <span data-ttu-id="4b686-103">Durch einen OLE DB-Verbindungs-Manager kann ein Paket mithilfe eines OLE DB-Anbieters eine Verbindung mit einer Datenquelle herstellen.</span><span class="sxs-lookup"><span data-stu-id="4b686-103">An OLE DB connection manager enables a package to connect to a data source by using an OLE DB provider.</span></span> <span data-ttu-id="4b686-104">Beispielsweise kann ein OLE DB-Verbindungs-Manager, der eine Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] herstellt, den [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB-Anbieter für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="4b686-104">For example, an OLE DB connection manager that connects to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can use the [!INCLUDE[msCoName](../../includes/msconame-md.md)] OLE DB Provider for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4b686-105">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 11.0 OLEDB-Anbieter unterstützt die neuen Schlüsselwörter für Verbindungszeichenfolgen (MultiSubnetFailover=True) für Multisubnetz-Failoverclustering nicht.</span><span class="sxs-lookup"><span data-stu-id="4b686-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client 11.0 OLEDB provider does not support the new connection string key words (MultiSubnetFailover=True) for Multi-Subnet Failover Clustering.</span></span> <span data-ttu-id="4b686-106">Weitere Informationen finden Sie in den [Anmerkungen](https://go.microsoft.com/fwlink/?LinkId=247824) zu dieser Version von SQL Server und im Blogbeitrag [AlwaysOn-multisubnetz-Failover und SSIS](https://www.mattmasson.com/2012/03/alwayson-multi-subnet-failover-and-ssis/)auf www.mattmasson.com.</span><span class="sxs-lookup"><span data-stu-id="4b686-106">For more information, see the [SQL Server Release  Notes](https://go.microsoft.com/fwlink/?LinkId=247824) and the blog post, [AlwaysOn Multi-Subnet Failover and SSIS](https://www.mattmasson.com/2012/03/alwayson-multi-subnet-failover-and-ssis/), on www.mattmasson.com.</span></span>  
  
 <span data-ttu-id="4b686-107">Mehrere [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] Tasks und Datenfluss Komponenten verwenden einen OLE DB-Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="4b686-107">Several [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] tasks and data flow components use an OLE DB connection manager.</span></span> <span data-ttu-id="4b686-108">Beispielsweise extrahieren und laden die OLE DB-Quelle und das OLE DB-Ziel mit diesem Verbindungs-Manager Daten. Und der Task SQL ausführen kann damit eine Verbindung mit einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank herstellen, um Abfragen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4b686-108">For example, the OLE DB source and OLE DB destination use this connection manager to extract and load data, and the Execute SQL task can use this connection manager to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database to run queries.</span></span>  
  
 <span data-ttu-id="4b686-109">Der OLE DB-Verbindungs-Manager wird auch für den Zugriff auf OLE DB-Datenquellen in benutzerdefinierten Tasks verwendet, die in nicht verwaltetem Code und einer Programmiersprache wie z. B. C++ geschrieben sind.</span><span class="sxs-lookup"><span data-stu-id="4b686-109">The OLE DB connection manager is also used to access OLE DB data sources in custom tasks written in unmanaged code that uses a language such as C++.</span></span>  
  
 <span data-ttu-id="4b686-110">Wenn Sie einem Paket einen OLE DB-Verbindungs-Manager hinzufügen, erstellt [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] einen Verbindungs-Manager, der zur Laufzeit in eine OLE DB-Verbindung aufgelöst wird, die Eigenschaften des Verbindungs-Managers festlegt und der `Connections`-Auflistung im Paket den Verbindungs-Manager hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="4b686-110">When you add an OLE DB connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to an OLE DB connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="4b686-111">Die `ConnectionManagerType`-Eigenschaft des Verbindungs-Managers ist auf `OLEDB` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="4b686-111">The `ConnectionManagerType` property of the connection manager is set to `OLEDB`.</span></span>  
  
 <span data-ttu-id="4b686-112">Der OLE DB-Verbindungs-Manager kann wie folgt konfiguriert werden:</span><span class="sxs-lookup"><span data-stu-id="4b686-112">The OLE DB connection manager can be configured in the following ways:</span></span>  
  
-   <span data-ttu-id="4b686-113">Stellen Sie eine Verbindungszeichenfolge bereit, die die Anforderungen des ausgewählten Anbieters erfüllt.</span><span class="sxs-lookup"><span data-stu-id="4b686-113">Provide a specific connection string configured to meet the requirements of the selected provider.</span></span>  
  
-   <span data-ttu-id="4b686-114">Schließen Sie in Abhängigkeit vom Anbieter den Namen der Datenquelle ein, mit der eine Verbindung hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="4b686-114">Depending on the provider, include the name of the data source to connect to.</span></span>  
  
-   <span data-ttu-id="4b686-115">Stellen Sie entsprechende Sicherheitsanmeldeinformationen für den ausgewählten Anbieter bereit.</span><span class="sxs-lookup"><span data-stu-id="4b686-115">Provide security credentials as appropriate for the selected provider.</span></span>  
  
-   <span data-ttu-id="4b686-116">Geben Sie an, ob die im Verbindungs-Manager erstellte Verbindung zur Laufzeit beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="4b686-116">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
## <a name="logging"></a><span data-ttu-id="4b686-117">Protokollierung</span><span class="sxs-lookup"><span data-stu-id="4b686-117">Logging</span></span>  
 <span data-ttu-id="4b686-118">Sie können die vom OLE DB-Verbindungs-Manager an externe Datenanbieter gerichteten Aufrufe protokollieren.</span><span class="sxs-lookup"><span data-stu-id="4b686-118">You can log the calls that the OLE DB connection manager makes to external data providers.</span></span> <span data-ttu-id="4b686-119">Mithilfe dieser Protokollierungsfunktionen können Sie Probleme bei Verbindungen behandeln, die vom OLE DB-Verbindungs-Manager mit externen Datenquellen hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4b686-119">You can use this logging capability to troubleshoot the connections that the OLE DB connection manager makes to external data sources.</span></span> <span data-ttu-id="4b686-120">Aktivieren Sie zum Protokollieren der vom OLE DB-Verbindungs-Manager an externe Datenanbieter gerichteten Aufrufe die Paketprotokollierung, und wählen Sie das **Diagnostic** -Ereignis auf Paketebene aus.</span><span class="sxs-lookup"><span data-stu-id="4b686-120">To log the calls that the OLE DB connection manager makes to external data providers, enable package logging and select the **Diagnostic** event at the package level.</span></span> <span data-ttu-id="4b686-121">Weitere Informationen finden Sie unter [Behandeln von Problemen mit Paketausführungstools](../troubleshooting/troubleshooting-tools-for-package-execution.md).</span><span class="sxs-lookup"><span data-stu-id="4b686-121">For more information, see [Troubleshooting Tools for Package Execution](../troubleshooting/troubleshooting-tools-for-package-execution.md).</span></span>  
  
## <a name="configuration-of-the-oledb-connection-manager"></a><span data-ttu-id="4b686-122">Konfiguration des OLEDB-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="4b686-122">Configuration of the OLEDB Connection Manager</span></span>  
 <span data-ttu-id="4b686-123">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="4b686-123">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span> <span data-ttu-id="4b686-124">Weitere Informationen zu den Eigenschaften, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können, finden Sie unter [Konfigurieren des OLE DB-Verbindungs-Managers](../configure-ole-db-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="4b686-124">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, see [Configure OLE DB Connection Manager](../configure-ole-db-connection-manager.md).</span></span> <span data-ttu-id="4b686-125">Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie in der Dokumentation zur **T:Microsoft.SqlServer.Dts.Runtime.ConnectionManager** -Klasse im Entwicklerhandbuch.</span><span class="sxs-lookup"><span data-stu-id="4b686-125">For information about configuring a connection manager programmatically, see the documentation for **T:Microsoft.SqlServer.Dts.Runtime.ConnectionManager** class in the Developer Guide.</span></span>  
  
## <a name="related-content"></a><span data-ttu-id="4b686-126">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="4b686-126">Related Content</span></span>  
  
-   <span data-ttu-id="4b686-127">Wiki-Artikel [SSIS mit Oracle-Connectors](https://go.microsoft.com/fwlink/?LinkId=220670) auf Social.technet.Microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="4b686-127">Wiki article, [SSIS with Oracle Connectors](https://go.microsoft.com/fwlink/?LinkId=220670) on social.technet.microsoft.com.</span></span>  
  
-   <span data-ttu-id="4b686-128">Technischer Artikel, [Connection Strings for OLE DB Providers](https://go.microsoft.com/fwlink/?LinkId=220744)(Verbindungszeichenfolgen für OLE DB-Anbieter), auf carlprothman.net.</span><span class="sxs-lookup"><span data-stu-id="4b686-128">Technical article, [Connection Strings for OLE DB Providers](https://go.microsoft.com/fwlink/?LinkId=220744), on carlprothman.net.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b686-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4b686-129">See Also</span></span>  
 <span data-ttu-id="4b686-130">[OLE DB-Quelle](../data-flow/ole-db-source.md) </span><span class="sxs-lookup"><span data-stu-id="4b686-130">[OLE DB Source](../data-flow/ole-db-source.md) </span></span>  
 <span data-ttu-id="4b686-131">[OLE DB-Ziel](../data-flow/ole-db-destination.md) </span><span class="sxs-lookup"><span data-stu-id="4b686-131">[OLE DB Destination](../data-flow/ole-db-destination.md) </span></span>  
 <span data-ttu-id="4b686-132">[SQL ausführen (Task)](../control-flow/execute-sql-task.md) </span><span class="sxs-lookup"><span data-stu-id="4b686-132">[Execute SQL Task](../control-flow/execute-sql-task.md) </span></span>  
 [<span data-ttu-id="4b686-133">Integration Services-Verbindungen &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="4b686-133">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
