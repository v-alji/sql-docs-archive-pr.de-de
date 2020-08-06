---
title: ODBC-Verbindungs-Manager | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- connections [Integration Services], ODBC
- ODBC connection manager
- data sources [Integration Services], connections
- connection managers [Integration Services], ODBC
ms.assetid: e8c77aa7-6772-485e-918e-cef9eeb18c58
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e1069e31f3f8ffaf14dde091d913ff6d9f8fa7cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616631"
---
# <a name="odbc-connection-manager"></a><span data-ttu-id="e1288-102">ODBC-Verbindungs-Manager</span><span class="sxs-lookup"><span data-stu-id="e1288-102">ODBC Connection Manager</span></span>
  <span data-ttu-id="e1288-103">Mit einem ODBC-Verbindungs-Manager kann ein Paket eine Verbindung mit einer Reihe von Datenbank-Managementsystemen mithilfe der ODBC-Spezifikation (Open Database Connectivity) herstellen.</span><span class="sxs-lookup"><span data-stu-id="e1288-103">An ODBC connection manager enables a package to connect to a variety of database management systems using the Open Database Connectivity specification (ODBC).</span></span>  
  
 <span data-ttu-id="e1288-104">Wenn Sie einem Paket eine ODBC-Verbindung hinzufügen und die Eigenschaften des Verbindungs-Managers festlegen, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] erstellt einen Verbindungs-Manager und fügt der-Auflistung des Pakets den Verbindungs-Manager hinzu `Connections` .</span><span class="sxs-lookup"><span data-stu-id="e1288-104">When you add an ODBC connection to a package and set the connection manager properties, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] creates a connection manager and adds the connection manager to the `Connections` collection of the package.</span></span> <span data-ttu-id="e1288-105">Zur Laufzeit wird der Verbindungs-Manager als physische ODBC-Verbindung aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="e1288-105">At run time the connection manager is resolved as a physical ODBC connection.</span></span>  
  
 <span data-ttu-id="e1288-106">Die `ConnectionManagerType`-Eigenschaft des Verbindungs-Managers ist auf `ODBC` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e1288-106">The `ConnectionManagerType` property of the connection manager is set to `ODBC`.</span></span>  
  
 <span data-ttu-id="e1288-107">Es gibt folgende Möglichkeiten, um den ODBC-Verbindungs-Manager zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="e1288-107">You can configure the ODBC connection manager in the following ways:</span></span>  
  
-   <span data-ttu-id="e1288-108">Geben Sie eine Verbindungszeichenfolge an, die auf einen Benutzer- oder System-Datenquellennamen verweist.</span><span class="sxs-lookup"><span data-stu-id="e1288-108">Provide a connection string that references a user or system data source name.</span></span>  
  
-   <span data-ttu-id="e1288-109">Geben Sie den Server für die Verbindungsherstellung an.</span><span class="sxs-lookup"><span data-stu-id="e1288-109">Specify the server to connect to.</span></span>  
  
-   <span data-ttu-id="e1288-110">Geben Sie an, ob die Verbindung zur Laufzeit beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="e1288-110">Indicate whether the connection is retained at run time.</span></span>  
  
## <a name="configuration-of-the-odbc-connection-manager"></a><span data-ttu-id="e1288-111">Konfiguration des ODBC-Verbindungs-Managers</span><span class="sxs-lookup"><span data-stu-id="e1288-111">Configuration of the ODBC Connection Manager</span></span>  
 <span data-ttu-id="e1288-112">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="e1288-112">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="e1288-113">Klicken Sie auf das folgende Thema, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer festlegen können:</span><span class="sxs-lookup"><span data-stu-id="e1288-113">For more information about the properties that you can set in [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer, click one of the following topic:</span></span>  
  
-   [<span data-ttu-id="e1288-114">ODBC-Verbindungs-Manager: Referenz zur Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="e1288-114">ODBC Connection Manager UI Reference</span></span>](../odbc-connection-manager-ui-reference.md)  
  
 <span data-ttu-id="e1288-115">Weitere Informationen zum programmgesteuerten Konfigurieren eines Verbindungs-Managers finden Sie unter <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> und [Programmgesteuertes Hinzufügen von Verbindungen](../building-packages-programmatically/adding-connections-programmatically.md)festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e1288-115">For information about configuring a connection manager programmatically, see <xref:Microsoft.SqlServer.Dts.Runtime.ConnectionManager> and [Adding Connections Programmatically](../building-packages-programmatically/adding-connections-programmatically.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1288-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e1288-116">See Also</span></span>  
 [<span data-ttu-id="e1288-117">Integration Services-Verbindungen &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="e1288-117">Integration Services &#40;SSIS&#41; Connections</span></span>](integration-services-ssis-connections.md)  
  
  
