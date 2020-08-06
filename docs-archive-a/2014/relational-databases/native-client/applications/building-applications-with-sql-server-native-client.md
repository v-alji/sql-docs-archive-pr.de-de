---
title: Entwickeln von Anwendungen mit SQL Server Native Client | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data access [SQL Server Native Client], building applications
- SQLNCLI, building applications
- applications [SQL Server Native Client]
- SQL Server Native Client, building applications
ms.assetid: 254a2b48-f0e3-43b5-a48d-3d666c2a779f
author: rothja
ms.author: jroth
ms.openlocfilehash: d08fe1042ab1a79f6b48648f5a774b4fbac49ead
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619077"
---
# <a name="building-applications-with-sql-server-native-client"></a><span data-ttu-id="e0610-102">Erstellen von Anwendungen mit SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="e0610-102">Building Applications with SQL Server Native Client</span></span>
  <span data-ttu-id="e0610-103">Bei der Entwicklung einer Anwendung, die die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-Bibliothek verwendet, sind eine Reihe von Punkten zu berücksichtigen.</span><span class="sxs-lookup"><span data-stu-id="e0610-103">When developing an application that uses the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client library, there are a number of issues that come into play.</span></span> <span data-ttu-id="e0610-104">Die Themen in diesem Abschnitt beschreiben viele dieser Punkte einschließlich Aktualisieren von MDAC auf [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, Verwenden der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-Header- und Bibliotheksdateien sowie eines Überblicks über die verschiedenen Verbindungszeichenfolgen, die mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e0610-104">The topics in this section discuss many of these issues including upgrading from MDAC to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, using the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header and library files, and an overview of the various connection strings that can be used with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e0610-105">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="e0610-105">In This Section</span></span>  
 [<span data-ttu-id="e0610-106">Installieren von SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="e0610-106">Installing SQL Server Native Client</span></span>](installing-sql-server-native-client.md)  
 <span data-ttu-id="e0610-107">Erläutert die Installation von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client, die Speicherorte zur Installation der verschiedenen Komponenten und die Deinstallation von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="e0610-107">Discusses how [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is installed, the locations that various components are installed to, and how to uninstall [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="e0610-108">Komponenten von SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="e0610-108">Components of SQL Server Native Client</span></span>](components-of-sql-server-native-client.md)  
 <span data-ttu-id="e0610-109">Beschreibt die Komponenten, aus denen sich [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client einschließlich Bibliothek, Ressource, Hilfe und Headerdateien zusammensetzt.</span><span class="sxs-lookup"><span data-stu-id="e0610-109">Discusses the components that make up [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client including library, resource, help, and header files.</span></span>  
  
 [<span data-ttu-id="e0610-110">Verwenden von Schlüsselwörtern für Verbindungszeichenfolgen mit SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="e0610-110">Using Connection String Keywords with SQL Server Native Client</span></span>](using-connection-string-keywords-with-sql-server-native-client.md)  
 <span data-ttu-id="e0610-111">Erläutert die verschiedenen Verbindungszeichenfolgen, die beim Herstellen einer Verbindung zu einer Datenbank mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e0610-111">Discusses the various types of connection strings that can be used when connecting to a database through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="e0610-112">Verwenden der SQL Server Native Client-Header- und Bibliotheksdateien</span><span class="sxs-lookup"><span data-stu-id="e0610-112">Using the SQL Server Native Client Header and Library Files</span></span>](using-the-sql-server-native-client-header-and-library-files.md)  
 <span data-ttu-id="e0610-113">Erläutert die Verwendung der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client-Header- und Bibliotheksdateien innerhalb einer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="e0610-113">Discusses how to use the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client header and library files within an application.</span></span>  
  
 [<span data-ttu-id="e0610-114">Aktualisieren einer Anwendung von MDAC auf SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="e0610-114">Updating an Application to SQL Server Native Client from MDAC</span></span>](updating-an-application-to-sql-server-native-client-from-mdac.md)  
 <span data-ttu-id="e0610-115">Beschreibt die Unterschiede zwischen [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client und MDAC sowie Aspekte, die beim Aktualisieren von MDAC auf [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client zu berücksichtigen sind.</span><span class="sxs-lookup"><span data-stu-id="e0610-115">Discusses the differences between [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and MDAC and issues that should be considered when upgrading from MDAC to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="e0610-116">Aktualisieren einer Anwendung von SQL Server 2005 Native Client</span><span class="sxs-lookup"><span data-stu-id="e0610-116">Updating an Application from SQL Server 2005 Native Client</span></span>](updating-an-application-from-sql-server-2005-native-client.md)  
 <span data-ttu-id="e0610-117">Beschreibt Aspekte, die beim Upgrade von [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Native Client auf [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] zu berücksichtigen sind.</span><span class="sxs-lookup"><span data-stu-id="e0610-117">Discusses issues that should be considered when upgrading from [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)] Native Client to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)].</span></span>  
  
 [<span data-ttu-id="e0610-118">Verwenden von ADO mit SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="e0610-118">Using ADO with SQL Server Native Client</span></span>](using-ado-with-sql-server-native-client.md)  
 <span data-ttu-id="e0610-119">Erläutert, wie ADO mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client auf die [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Funktionen zugreifen und diese verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="e0610-119">Discusses how ADO can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client to access and use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] functionality.</span></span>  
  
 [<span data-ttu-id="e0610-120">Richtlinien zur Unterstützung für SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="e0610-120">Support Policies for SQL Server Native Client</span></span>](support-policies-for-sql-server-native-client.md)  
 <span data-ttu-id="e0610-121">Erklärt die Verwendung verschiedener Datenzugriffskomponenten mit verschiedenen Versionen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="e0610-121">Discusses how various data-access components can be used with different versions of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
 [<span data-ttu-id="e0610-122">Herstellen einer Verbindung mit einer Azure SQL-Datenbank mithilfe von SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="e0610-122">Connecting to an Azure SQL Database Using SQL Server Native Client</span></span>](connecting-to-a-windows-azure-sql-database-using-sql-server-native-client.md)  
 <span data-ttu-id="e0610-123">Erläutert, wie mithilfe von [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] Native Client eine Verbindung mit einer [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e0610-123">Discusses how to connect to a [!INCLUDE[ssSDS](../../../includes/sssds-md.md)] using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0610-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e0610-124">See Also</span></span>  
 <span data-ttu-id="e0610-125">[SQL Server Native Client Programmierung](../sql-server-native-client-programming.md) </span><span class="sxs-lookup"><span data-stu-id="e0610-125">[SQL Server Native Client Programming](../sql-server-native-client-programming.md) </span></span>  
 <span data-ttu-id="e0610-126">[ODBC-Themen zur Vorgehensweise](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span><span class="sxs-lookup"><span data-stu-id="e0610-126">[ODBC How-to Topics](../../native-client-odbc-how-to/odbc-how-to-topics.md) </span></span>  
 [<span data-ttu-id="e0610-127">Vorgehensweisen für OLE DB</span><span class="sxs-lookup"><span data-stu-id="e0610-127">OLE DB How-to Topics</span></span>](../../native-client-ole-db-how-to/ole-db-how-to-topics.md)  
  
  
