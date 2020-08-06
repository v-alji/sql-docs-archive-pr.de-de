---
title: Vorgehensweisen für OLE DB | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, how-to topics
ms.assetid: fbfab1b0-433d-497e-ae07-9b21a5c6903c
author: rothja
ms.author: jroth
ms.openlocfilehash: 006962c1a28cc4a21f3e2efaa63b45b0871e208f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616974"
---
# <a name="ole-db-how-to-topics"></a><span data-ttu-id="14042-102">Vorgehensweisen für OLE DB</span><span class="sxs-lookup"><span data-stu-id="14042-102">OLE DB How-to Topics</span></span>
  <span data-ttu-id="14042-103">Wenn Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-OLE DB-Anbieter verwenden möchten, müssen Sie wissen, wie Sie eine Verbindung mit dem Server herstellen, den Befehl ausführen und die Ergebnisse verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="14042-103">To use the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider, you have to understand how to make a connection to the server, execute the command, and process the results.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="14042-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="14042-104">In This Section</span></span>  
  
-   [<span data-ttu-id="14042-105">Vorgehensweisen zum Verarbeiten von Ergebnissen &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="14042-105">Processing Results How-to Topics &#40;OLE DB&#41;</span></span>](results/processing-results-how-to-topics-ole-db.md)  
  
-   [<span data-ttu-id="14042-106">Festlegen großer Datenmengen &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="14042-106">Set Large Data &#40;OLE DB&#41;</span></span>](set-large-data-ole-db.md)  
  
-   [<span data-ttu-id="14042-107">Auflisten von OLE DB-Datenquellen &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="14042-107">Enumerate OLE DB Data Sources &#40;OLE DB&#41;</span></span>](enumerate-ole-db-data-sources-ole-db.md)  
  
-   [<span data-ttu-id="14042-108">Massenkopieren von Daten mithilfe von IRowsetFastLoad &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="14042-108">Bulk Copy Data Using IRowsetFastLoad &#40;OLE DB&#41;</span></span>](../native-client-ole-db-interfaces/irowsetfastload-ole-db.md)  
  
-   [<span data-ttu-id="14042-109">Abrufen eines FAST_FORWARD-Cursors</span><span class="sxs-lookup"><span data-stu-id="14042-109">Obtain a FAST_FORWARD Cursor</span></span>](obtain-a-fast-forward-cursor.md)  
  
-   [<span data-ttu-id="14042-110">Abrufen von Zeilen mithilfe von Lesezeichen &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="14042-110">Retrieve Rows Using Bookmarks &#40;OLE DB&#41;</span></span>](retrieve-rows-using-bookmarks-ole-db.md)  
  
-   [<span data-ttu-id="14042-111">Abrufen von Spalten mithilfe von IRow::GetColumns &#40;oder IRow::Open&#41; und ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="14042-111">Fetch Columns Using IRow::GetColumns &#40;or IRow::Open&#41; and ISequentialStream</span></span>](fetch-columns-using-irow-getcolumns-or-irow-open-and-isequentialstream.md)  
  
-   [<span data-ttu-id="14042-112">Abrufen von Spalten mithilfe von IRow::GetColumns &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="14042-112">Fetch Columns Using IRow::GetColumns &#40;OLE DB&#41;</span></span>](fetch-columns-using-irow-getcolumns-ole-db.md)  
  
-   [<span data-ttu-id="14042-113">Ändern eines SQL Server-Authentifizierungsbenutzerkennworts &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="14042-113">Change a SQL Server Authentication User Password &#40;OLE DB&#41;</span></span>](change-a-sql-server-authentication-user-password-ole-db.md)  
  
-   [<span data-ttu-id="14042-114">Verwenden von erweiterten Datums- und Uhrzeitfeatures &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="14042-114">Use Enhanced Date and Time Features &#40;OLE DB&#41;</span></span>](use-enhanced-date-and-time-features-ole-db.md)  
  
-   [<span data-ttu-id="14042-115">FILESTREAM und OLE DB</span><span class="sxs-lookup"><span data-stu-id="14042-115">Filestream and OLE DB</span></span>](filestream/filestream-and-ole-db.md)  
  
-   [<span data-ttu-id="14042-116">Senden von BLOB-Daten an SQL SERVER mit IROWSETFASTLOAD und ISEQUENTIALSTREAM &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="14042-116">Send BLOB Data to SQL SERVER Using IROWSETFASTLOAD and ISEQUENTIALSTREAM &#40;OLE DB&#41;</span></span>](send-blob-data-to-sql-server-using-irowsetfastload-and-isequentialstream-ole-db.md)  
  
-   [<span data-ttu-id="14042-117">Verwenden von großen CLR-UDTs &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="14042-117">Use Large CLR UDTs &#40;OLE DB&#41;</span></span>](use-large-clr-udts-ole-db.md)  
  
-   [<span data-ttu-id="14042-118">Anzeigen von Spalten- und Katalogmetadaten für Sparsespalten &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="14042-118">Display Column and Catalog Metadata for Sparse Columns &#40;OLE DB&#41;</span></span>](display-column-and-catalog-metadata-for-sparse-columns-ole-db.md)  
  
-   [<span data-ttu-id="14042-119">Integrierte Kerberos-Authentifizierung &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="14042-119">Integrated Kerberos Authentication &#40;OLE DB&#41;</span></span>](integrated-kerberos-authentication-ole-db.md)  
  
-   [<span data-ttu-id="14042-120">Verwenden von Tabellenwertparametern &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="14042-120">Use Table-Valued Parameters &#40;OLE DB&#41;</span></span>](../native-client-ole-db-table-valued-parameters/table-valued-parameters-ole-db.md)  
  
## <a name="see-also"></a><span data-ttu-id="14042-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14042-121">See Also</span></span>  
 [<span data-ttu-id="14042-122">Programmierung für SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="14042-122">SQL Server Native Client Programming</span></span>](../native-client/sql-server-native-client-programming.md)  
  
  
