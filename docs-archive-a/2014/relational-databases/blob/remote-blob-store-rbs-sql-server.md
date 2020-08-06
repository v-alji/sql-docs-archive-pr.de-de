---
title: Remote Blob Store (RBS) (SQL Server) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.technology: filestream
ms.reviewer: ''
ms.topic: conceptual
helpviewer_keywords:
- Remote Blob Store (RBS) [SQL Server]
- RBS (Remote Blob Store) [SQL Server]
ms.assetid: 31c947cf-53e9-4ff4-939b-4c1d034ea5b1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8f3425474ec3b9013355536424ffcf55d9426b9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695729"
---
# <a name="remote-blob-store-rbs-sql-server"></a><span data-ttu-id="0c032-102">Remote Blob Store (RBS) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="0c032-102">Remote Blob Store (RBS) (SQL Server)</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0c032-103">Remote BLOB-Speicher (RBS) ist eine optionale Add-On-Komponente, mit der Datenbankadministratoren Binary Large Objects in Speicherlösungen statt direkt auf dem Hauptdatenbankserver speichern können.</span><span class="sxs-lookup"><span data-stu-id="0c032-103">Remote BLOB Store (RBS) is an optional add-on component that lets database administrators store binary large objects in commodity storage solutions instead of directly on the main database server.</span></span>  
  
 <span data-ttu-id="0c032-104">RBS ist nicht auf den [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Installationsmedien enthalten. Er wird auch nicht über das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Setupprogram installiert.</span><span class="sxs-lookup"><span data-stu-id="0c032-104">RBS is included on the [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] installation media, but is not installed by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Setup program.</span></span>  
  
 <span data-ttu-id="0c032-105">Weitere Informationen zu RBS finden Sie in diesem Thema unter [RSB-Ressourcen](#rbsresources) .</span><span class="sxs-lookup"><span data-stu-id="0c032-105">For more information about RBS, see [RBS Resources](#rbsresources) in this topic.</span></span>  
  
## <a name="benefits-of-rbs"></a><span data-ttu-id="0c032-106">Vorteile von RBS</span><span class="sxs-lookup"><span data-stu-id="0c032-106">Benefits of RBS</span></span>  
 <span data-ttu-id="0c032-107">RBS bietet die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="0c032-107">RBS provides the following benefits:</span></span>  
  
### <a name="optimized-database-storage-and-performance"></a><span data-ttu-id="0c032-108">Optimierte Datenbankspeicher und optimierte Datenbankleistung</span><span class="sxs-lookup"><span data-stu-id="0c032-108">Optimized database storage and performance</span></span>  
 <span data-ttu-id="0c032-109">Durch das Speichern von BLOBs in der Datenbank können große Mengen an Dateispeicherplatz sowie teure Serverressourcen belegt werden.</span><span class="sxs-lookup"><span data-stu-id="0c032-109">Storing BLOBs in the database can consume large amounts of file space and expensive server resources.</span></span> <span data-ttu-id="0c032-110">RBS überträgt auf effiziente Weise BLOBs auf eine dedizierte Speicherlösung Ihrer Wahl und speichert Verweise auf diese in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0c032-110">RBS efficiently transfers the BLOBs to a dedicated storage solution of your choosing, and stores references to them in the database.</span></span> <span data-ttu-id="0c032-111">Dadurch werden Serverspeicher für strukturierte Daten und Serverressourcen für Datenbankoperationen freigegeben.</span><span class="sxs-lookup"><span data-stu-id="0c032-111">This frees server storage for structured data, and frees server resources for database operations.</span></span>  
  
### <a name="efficient-management-of-blobs"></a><span data-ttu-id="0c032-112">Effiziente Verwaltung von BLOBs</span><span class="sxs-lookup"><span data-stu-id="0c032-112">Efficient management of BLOBs</span></span>  
 <span data-ttu-id="0c032-113">Mehrere RBS-Funktionen unterstützen die bequeme Verwaltung von gespeicherten BLOBs:</span><span class="sxs-lookup"><span data-stu-id="0c032-113">Several RBS features support the convenient management of stored BLOBs:</span></span>  
  
-   <span data-ttu-id="0c032-114">BLOBs werden mithilfe von ACID-Transaktionen (atomic consistency isolation durable; Unteilbarkeit, Konsistenz, Isolation, Dauerhaftigkeit) verwaltet.</span><span class="sxs-lookup"><span data-stu-id="0c032-114">BLOBS are managed with ACID (atomic consistency isolation durable) transactions.</span></span>  
  
-   <span data-ttu-id="0c032-115">BLOBs sind in Auflistungen unterteilt.</span><span class="sxs-lookup"><span data-stu-id="0c032-115">BLOBs are organized into collections.</span></span>  
  
-   <span data-ttu-id="0c032-116">Automatische Speicherbereinigung, Konsistenzüberprüfung und andere Wartungsfunktionen sind enthalten.</span><span class="sxs-lookup"><span data-stu-id="0c032-116">Garbage collection, consistency checking, and other maintenance functions are included.</span></span>  
  
### <a name="standardized-api"></a><span data-ttu-id="0c032-117">Standardisierte API</span><span class="sxs-lookup"><span data-stu-id="0c032-117">Standardized API</span></span>  
 <span data-ttu-id="0c032-118">RBS definiert einen Satz von APIs, die ein standardisiertes Programmiermodell für Anwendungen bereitstellen, um auf BLOB-Speicher zuzugreifen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0c032-118">RBS defines a set of APIs that provide a standardized programming model for applications to access and modify any BLOB store.</span></span> <span data-ttu-id="0c032-119">Jeder BLOB-Speicher kann eine eigene Anbieterbibliothek angeben, die an die RBS-Clientbibliothek angeschlossen wird und angibt, wie BLOBs gespeichert werden und auf sie zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="0c032-119">Each BLOB store can specify its own provider library, which plugs into the RBS client library and specifies how BLOBs are stored and accessed.</span></span>  
  
 <span data-ttu-id="0c032-120">Eine Reihe von Speicherlösungen von Drittanbietern haben RBS-Anbieter entwickelt, die diesen Standard-APIs entsprechen und BLOB-Speicherung auf verschiedenen Speicherplattformen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="0c032-120">A number of third-party storage solution vendors have developed RBS providers that conform to these standard APIs and support BLOB storage on various storage platforms.</span></span>  
  
## <a name="rbs-requirements"></a><span data-ttu-id="0c032-121">RSB-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="0c032-121">RBS Requirements</span></span>  
 <span data-ttu-id="0c032-122">RSB erfordert [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise für den Hauptdatenbankserver, in dem die BLOB-Metadaten gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="0c032-122">RBS requires [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Enterprise for the main database server in which the BLOB metadata is stored.</span></span> <span data-ttu-id="0c032-123">Wenn Sie jedoch den bereitgestellten FILESTREAM-Anbieter verwenden, können Sie die BLOBs selbst auf [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Standard speichern.</span><span class="sxs-lookup"><span data-stu-id="0c032-123">However, if you use the supplied FILESTREAM provider, you can store the BLOBs themselves on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Standard.</span></span>  
  
 <span data-ttu-id="0c032-124">RBS beinhaltet einen FILESTREAM-Anbieter, mit dem Sie BLOBs mithilfe von RBS auf einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]speichern können.</span><span class="sxs-lookup"><span data-stu-id="0c032-124">RBS includes a FILESTREAM provider that lets you use RBS to store BLOBs on an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="0c032-125">Wenn Sie BLOBs mithilfe von RBS in einer anderen Speicherlösung speichern möchten, müssen Sie einen für diese Speicherlösung entwickelten RSB-Anbieter eines Drittanbieters verwenden oder einen benutzerdefinierten RBS-Anbieter mithilfe der RBS-API entwickeln.</span><span class="sxs-lookup"><span data-stu-id="0c032-125">If you want use RBS to store BLOBs in a different storage solution, you have to use a third party RBS provider developed for that storage solution, or develop a custom RBS provider using the RBS API.</span></span> <span data-ttu-id="0c032-126">Ein Beispielanbieter, der BLOBs im NTFS-Dateisystem speichert, steht als Lernressource auf [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190)zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="0c032-126">A sample provider that stores BLOBs in the NTFS file system is available as a learning resource on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190).</span></span>  
  
## <a name="rbs-security"></a><span data-ttu-id="0c032-127">RSB-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="0c032-127">RBS Security</span></span>  
 <span data-ttu-id="0c032-128">Wenn Sie einen benutzerdefinierten Anbieter verwenden, um BLOBs außerhalb von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu speichern, stehen diese möglicherweise auch anderen Prozessen, die das[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Sicherheitssystem umgehen, zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="0c032-128">When you use a custom provider to store BLOBs outside of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], they may be available to other processes that bypass the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] security system.</span></span> <span data-ttu-id="0c032-129">Stellen Sie sicher, dass die gespeicherten BLOBs anhand von Berechtigungen und Verschlüsselungsoptionen geschützt sind, die für das vom benutzerdefinierten Anbieter verwendete Speichermedium geeignet sind.</span><span class="sxs-lookup"><span data-stu-id="0c032-129">Make sure that you protect the stored BLOBs with permissions and encryption options that are appropriate to the storage medium used by the custom provider.</span></span>  
  
##  <a name="rbs-resources"></a><a name="rbsresources"></a><span data-ttu-id="0c032-130">RSB-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="0c032-130">RBS Resources</span></span>  
 <span data-ttu-id="0c032-131">**RBS-Dokumentation**</span><span class="sxs-lookup"><span data-stu-id="0c032-131">**RBS documentation**</span></span>  
 <span data-ttu-id="0c032-132">Die RBS-Dokumentation ist im Windows Installer-Paket enthalten.</span><span class="sxs-lookup"><span data-stu-id="0c032-132">The RBS documentation is included in the Windows installer package.</span></span> <span data-ttu-id="0c032-133">Wenn Sie die RBS-Dokumentation durchlesen möchten, ohne RBS zu installieren, können Sie die [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] -Version der Dokumentation auch [online in der MSDN Library](https://go.microsoft.com/fwlink/?LinkId=210192)anzeigen.</span><span class="sxs-lookup"><span data-stu-id="0c032-133">If you want to review the RBS documentation without installing RBS, you can view the [!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)] version of the documentation [online in the MSDN Library](https://go.microsoft.com/fwlink/?LinkId=210192).</span></span>  
  
 <span data-ttu-id="0c032-134">**RSB-Whitepaper**</span><span class="sxs-lookup"><span data-stu-id="0c032-134">**RBS white paper**</span></span>  
 <span data-ttu-id="0c032-135">Das Whitepaper [Remote BLOB Storage](https://go.microsoft.com/fwlink/?LinkId=210422), das als Microsoft Word-Dokument in englischer Sprache zum Download zur Verfügung steht, bietet ausführliche Informationen zur Installation und Konfiguration von RBS.</span><span class="sxs-lookup"><span data-stu-id="0c032-135">The white paper "[Remote BLOB Storage](https://go.microsoft.com/fwlink/?LinkId=210422)", which is available for download as a Microsoft Word document, provides detailed information about installing and configuring RBS.</span></span>  
  
 <span data-ttu-id="0c032-136">**RSB-Beispiele**</span><span class="sxs-lookup"><span data-stu-id="0c032-136">**RBS samples**</span></span>  
 <span data-ttu-id="0c032-137">In den auf [CodePlex](https://go.microsoft.com/fwlink/?LinkId=210190) verfügbaren RSB-Beispielen wird veranschaulicht, wie Sie eine RBS-Anwendung entwickeln und einen benutzerdefinierten RBS-Anbieter installieren.</span><span class="sxs-lookup"><span data-stu-id="0c032-137">The RBS samples available on [Codeplex](https://go.microsoft.com/fwlink/?LinkId=210190) demonstrate how to develop an RBS application, and how to develop and install a custom RBS provider.</span></span>  
  
 <span data-ttu-id="0c032-138">**RBS-Blog**</span><span class="sxs-lookup"><span data-stu-id="0c032-138">**RBS blog**</span></span>  
 <span data-ttu-id="0c032-139">Der [RBS-Blog](https://go.microsoft.com/fwlink/?LinkId=210315) bietet zusätzliche Informationen, durch die Sie RBS besser verstehen, bereitstellen und verwalten können.</span><span class="sxs-lookup"><span data-stu-id="0c032-139">The [RBS blog](https://go.microsoft.com/fwlink/?LinkId=210315) provides additional information to help you understand, deploy, and maintain RBS.</span></span>  
  
  
