---
title: SQL Server Compact Edition-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Compact, connection manager
- connections [Integration Services], SQL Server Compact
- connection managers [Integration Services], SQL Server Compact
ms.assetid: ba627d4d-41f4-49fc-a921-f534cde67770
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 5d4feb001cc7c0fd0bd8b6e60d5ab22b33ad2eb9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724866"
---
# <a name="sql-server-compact-edition-connection-manager"></a><span data-ttu-id="ba306-102">SQL Server Compact Edition-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="ba306-102">SQL Server Compact Edition Connection Manager</span></span>
  <span data-ttu-id="ba306-103">Mit einem [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Verbindungs-Manager kann ein Paket eine Verbindung mit einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Datenbank herstellen.</span><span class="sxs-lookup"><span data-stu-id="ba306-103">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager enables a package to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span> <span data-ttu-id="ba306-104">Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Ziel, das [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] enthält, lädt mithilfe dieses Verbindungs-Managers Daten in eine Tabelle einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ba306-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination that [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes uses this connection manager to load data into a table in a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="ba306-105">Auf einem 64-Bit-Computer müssen Sie Pakete, die mit den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Datenquellen verbunden sind, im 32-Bit-Modus ausführen.</span><span class="sxs-lookup"><span data-stu-id="ba306-105">On a 64-bit computer, you must run packages that connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources in 32-bit mode.</span></span> <span data-ttu-id="ba306-106">Der Anbieter von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, der von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] zum Herstellen einer Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Datenquellen verwendet wird, ist lediglich in einer 32-Bit-Version verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ba306-106">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact provider that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] uses to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources is available only in a 32-bit version.</span></span>  
  
## <a name="configuration-the-sql-server-compact-edition-connection-manager"></a><span data-ttu-id="ba306-107">Konfiguration des SQL Server Compact Edition-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="ba306-107">Configuration the SQL Server Compact Edition Connection Manager</span></span>  
 <span data-ttu-id="ba306-108">Wenn Sie einem Paket einen Compact-Verbindungs-Manager hinzufügen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] erstellt einen Verbindungs-Manager, der zur Laufzeit zu einer Compact-Verbindung aufgelöst wird [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] , die Eigenschaften des Verbindungs-Managers festlegt und der-Auflistung im Paket den Verbindungs-Manager hinzufügt `Connections` .</span><span class="sxs-lookup"><span data-stu-id="ba306-108">When you add a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager to a package, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager that will resolve to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection at run time, sets the connection manager properties, and adds the connection manager to the `Connections` collection on the package.</span></span>  
  
 <span data-ttu-id="ba306-109">Die `ConnectionManagerType`-Eigenschaft des Verbindungs-Managers ist auf `SQLMOBILE` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ba306-109">The `ConnectionManagerType` property of the connection manager is set to `SQLMOBILE`.</span></span>  
  
 <span data-ttu-id="ba306-110">Es gibt folgende Möglichkeiten, um den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Verbindungs-Manager zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="ba306-110">You can configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="ba306-111">Stellen Sie eine Verbindungszeichenfolge für den Speicherort der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="ba306-111">Provide a connection string that specifies the location of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact database.</span></span>  
  
-   <span data-ttu-id="ba306-112">Stellen Sie ein Kennwort für eine kennwortgeschützte Datenbank bereit.</span><span class="sxs-lookup"><span data-stu-id="ba306-112">Provide a password for a password-protected database.</span></span>  
  
-   <span data-ttu-id="ba306-113">Geben Sie den Server an, auf dem die Datenbank gespeichert ist.</span><span class="sxs-lookup"><span data-stu-id="ba306-113">Specify the server on which the database is stored.</span></span>  
  
-   <span data-ttu-id="ba306-114">Geben Sie an, ob die im Verbindungs-Manager erstellte Verbindung zur Laufzeit beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="ba306-114">Indicate whether the connection that is created from the connection manager is retained at run time.</span></span>  
  
 <span data-ttu-id="ba306-115">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="ba306-115">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="ba306-116">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="ba306-116">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ba306-117">Verbindungs-Manager-Editor für SQL Server Compact Edition &#40;Seite „Verbindung“&#41;</span><span class="sxs-lookup"><span data-stu-id="ba306-117">SQL Server Compact Edition Connection Manager Editor &#40;Connection Page&#41;</span></span>](../sql-server-compact-edition-connection-manager-editor-connection-page.md)  
  
-   [<span data-ttu-id="ba306-118">Verbindungs-Manager-Editor für SQL Server Compact Edition &#40;Seite „Alle“&#41;</span><span class="sxs-lookup"><span data-stu-id="ba306-118">SQL Server Compact Edition Connection Manager Editor &#40;All Page&#41;</span></span>](../sql-server-compact-edition-connection-manager-editor-all-page.md)  
  
 <span data-ttu-id="ba306-119">Weitere Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> und [Programmgesteuertes Hinzufügen von Verbindungen](../building-packages-programmatically/adding-connections-programmatically.md)festgelegt.</span><span class="sxs-lookup"><span data-stu-id="ba306-119">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
  
