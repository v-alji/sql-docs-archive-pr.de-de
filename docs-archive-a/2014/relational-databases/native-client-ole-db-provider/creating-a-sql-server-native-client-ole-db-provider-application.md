---
title: Erstellen einer SQL Server Native Client OLE DB Anbieter Anwendung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client OLE DB provider, application creation
- applications [SQL Server Native Client]
- OLE DB, creating applications
ms.assetid: f3ae6815-f32d-4913-a1a2-2ba2f20cfd88
author: rothja
ms.author: jroth
ms.openlocfilehash: a661f23cdacc4b581dadbe7625cb6e2ea318857f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698121"
---
# <a name="creating-a-sql-server-native-client-ole-db-provider-application"></a><span data-ttu-id="2f2bb-102">Erstellen einer SQL Server Native Client OLE DB-Anbieteranwendung</span><span class="sxs-lookup"><span data-stu-id="2f2bb-102">Creating a SQL Server Native Client OLE DB Provider Application</span></span>
  <span data-ttu-id="2f2bb-103">Das Erstellen einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter Anwendung umfasst die folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="2f2bb-103">Creating a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider application involves these steps:</span></span>  
  
1.  <span data-ttu-id="2f2bb-104">Herstellen einer Verbindung zu einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="2f2bb-104">Establishing a connection to a data source.</span></span>  
  
2.  <span data-ttu-id="2f2bb-105">Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="2f2bb-105">Executing a command.</span></span>  
  
3.  <span data-ttu-id="2f2bb-106">Verarbeiten der Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="2f2bb-106">Processing the results.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f2bb-107">Verwenden Sie nach Möglichkeit die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2f2bb-107">When possible, use Windows Authentication.</span></span> <span data-ttu-id="2f2bb-108">Wenn die Windows-Authentifizierung nicht verfügbar ist, fordern Sie die Benutzer auf, ihre Anmeldeinformationen zur Laufzeit einzugeben.</span><span class="sxs-lookup"><span data-stu-id="2f2bb-108">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="2f2bb-109">Die Anmeldeinformationen sollten nicht in einer Datei gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="2f2bb-109">Avoid storing credentials in a file.</span></span> <span data-ttu-id="2f2bb-110">Wenn Sie die Anmeldeinformationen persistent speichern müssen, sollten Sie sie mit der [Win32 Crypto-API](https://go.microsoft.com/fwlink/?LinkId=9504)verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="2f2bb-110">If you must persist credentials, you should encrypt them with [the Win32 cryptoAPI](https://go.microsoft.com/fwlink/?LinkId=9504).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2f2bb-111">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="2f2bb-111">In This Section</span></span>  
  
-   [<span data-ttu-id="2f2bb-112">Herstellen einer Verbindung zu einer Datenquelle</span><span class="sxs-lookup"><span data-stu-id="2f2bb-112">Establishing a Connection to a Data Source</span></span>](establishing-a-connection-to-a-data-source.md)  
  
-   [<span data-ttu-id="2f2bb-113">Ausführen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="2f2bb-113">Executing a Command</span></span>](executing-a-command.md)  
  
-   [<span data-ttu-id="2f2bb-114">Ergebnisverarbeitung</span><span class="sxs-lookup"><span data-stu-id="2f2bb-114">Processing Results</span></span>](processing-results.md)  
  
-   [<span data-ttu-id="2f2bb-115">Informationen zu OLE DB-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="2f2bb-115">About OLE DB Properties</span></span>](about-ole-db-properties.md)  
  
-   [<span data-ttu-id="2f2bb-116">Verwenden der OUTPUT-Klausel mit OLE DB in SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="2f2bb-116">Using the OUTPUT Clause with OLE DB in SQL Server Native Client</span></span>](using-the-output-clause-with-ole-db-in-sql-server-native-client.md)  
  
## <a name="see-also"></a><span data-ttu-id="2f2bb-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f2bb-117">See Also</span></span>  
 [<span data-ttu-id="2f2bb-118">SQL Server Native Client &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="2f2bb-118">SQL Server Native Client &#40;OLE DB&#41;</span></span>](../native-client/ole-db/sql-server-native-client-ole-db.md)  
  
  
