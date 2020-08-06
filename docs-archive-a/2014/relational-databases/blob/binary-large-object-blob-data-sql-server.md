---
title: Binary Large Object (BLOB)-Daten (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: filestream
ms.topic: conceptual
helpviewer_keywords:
- FILESTREAM [SQL Server], design and implementation
ms.assetid: 97509274-c3f8-43e5-a37c-52f1ffe0961a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: a663dedf34d75a21ee8df6b97979548c04abf7ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621027"
---
# <a name="binary-large-object-blob-data-sql-server"></a><span data-ttu-id="fe224-102">Binary Large Object (BLOB)-Daten (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="fe224-102">Binary Large Object (Blob) Data (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="fe224-103">stellt Lösungen zum Speichern von Dateien und Dokumenten in der Datenbank oder auf Remotespeichergeräten bereit.</span><span class="sxs-lookup"><span data-stu-id="fe224-103">provides solutions for storing files and documents in the database or on remote storage devices.</span></span>  
  
##  <a name="in-this-section"></a><a name="section"></a> <span data-ttu-id="fe224-104">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fe224-104">In This Section</span></span>  
 [<span data-ttu-id="fe224-105">Vergleichen von Optionen zum Speichern von Blobs &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe224-105">Compare Options for Storing Blobs &#40;SQL Server&#41;</span></span>](compare-options-for-storing-blobs-sql-server.md)  
 <span data-ttu-id="fe224-106">Vergleichen Sie die Vorteile von FILESTREAM, FileTables und Remote Blob Store.</span><span class="sxs-lookup"><span data-stu-id="fe224-106">Compare the advantages of FILESTREAM, FileTables, and Remote Blob Store.</span></span>  
  
 [<span data-ttu-id="fe224-107">FILESTREAM &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe224-107">FILESTREAM &#40;SQL Server&#41;</span></span>](filestream-sql-server.md)  
 <span data-ttu-id="fe224-108">FILESTREAM ermöglicht es [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-basierten Anwendungen, nicht strukturierte Daten wie beispielsweise Dokumente und Bilder im Dateisystem zu speichern.</span><span class="sxs-lookup"><span data-stu-id="fe224-108">FILESTREAM enables [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-based applications to store unstructured data, such as documents and images, on the file system.</span></span> <span data-ttu-id="fe224-109">Anwendungen können die umfassenden Streaming-APIs und die Leistung des Dateisystems nutzen und dabei die Transaktionskonsistenz zwischen den nicht strukturierten Daten und den entsprechenden strukturierten Daten erhalten.</span><span class="sxs-lookup"><span data-stu-id="fe224-109">Applications can leverage the rich streaming APIs and performance of the file system and at the same time maintain transactional consistency between the unstructured data and corresponding structured data.</span></span>  
  
 [<span data-ttu-id="fe224-110">FileTables &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe224-110">FileTables &#40;SQL Server&#41;</span></span>](filetables-sql-server.md)  
 <span data-ttu-id="fe224-111">Die FileTable-Funktion bietet für die in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gespeicherten Dateidaten Unterstützung für den Windows-Dateinamespace und die Kompatibilität mit Windows-Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="fe224-111">The FileTable feature brings support for the Windows file namespace and compatibility with Windows applications to the file data stored in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fe224-112">Mit FileTable können das Speichersystem und die Datenverwaltungskomponenten einer Anwendung integriert werden. Zudem werden integrierte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Dienste (z. B. Volltextsuche und semantische Suche) über unstrukturierte Daten und Metadaten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="fe224-112">FileTable lets an application integrate its storage and data management components, and provides integrated [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services - including full-text search and semantic search - over unstructured data and metadata.</span></span>  
  
 <span data-ttu-id="fe224-113">So können Sie Dateien und Dokumente in besonderen Tabellen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] speichern, die als FileTables bezeichnet werden, und auf diese über Windows-Anwendungen zugreifen, so als ob sie im Dateisystem gespeichert wären, ohne Clientanwendungen ändern zu müssen.</span><span class="sxs-lookup"><span data-stu-id="fe224-113">In other words, you can store files and documents in special tables in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] called FileTables, but access them from Windows applications as if they were stored in the file system, without making any changes to your client applications.</span></span>  
  
 [<span data-ttu-id="fe224-114">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="fe224-114">Remote Blob Store &#40;RBS&#41; &#40;SQL Server&#41;</span></span>](remote-blob-store-rbs-sql-server.md)  
 <span data-ttu-id="fe224-115">Der Remote BLOB-Speicher (RBS) für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ermöglicht Datenbankadministratoren, Binary Large Objects (BLOBS) in Speicherlösungen statt auf dem Server direkt zu speichern.</span><span class="sxs-lookup"><span data-stu-id="fe224-115">Remote BLOB store (RBS) for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lets database administrators store binary large objects (BLOBs) in commodity storage solutions instead of directly on the server.</span></span> <span data-ttu-id="fe224-116">Dies spart bedeutend Platz und vermeidet Aufwand für teure Serverhardwareressourcen.</span><span class="sxs-lookup"><span data-stu-id="fe224-116">This saves a significant amount of space and avoids wasting expensive server hardware resources.</span></span> <span data-ttu-id="fe224-117">RBS stellt einen Satz von API-Bibliotheken bereit, die ein standardisiertes Modell für Anwendungen definieren, um auf BLOB-Daten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="fe224-117">RBS provides a set of API libraries that define a standardized model for applications to access BLOB data.</span></span> <span data-ttu-id="fe224-118">Außerdem umfasst RBS Wartungstools wie die automatische Speicherbereinigung, um die Verwaltung von BLOB-Remotedaten zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="fe224-118">RBS also includes maintenance tools, such as garbage collection, to help manage remote BLOB data.</span></span>  
  
 <span data-ttu-id="fe224-119">RBS ist nicht auf den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Installationsmedien enthalten. Er wird auch nicht über das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Setupprogram installiert.</span><span class="sxs-lookup"><span data-stu-id="fe224-119">RBS is included on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media, but is not installed by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program.</span></span>  
  
  
