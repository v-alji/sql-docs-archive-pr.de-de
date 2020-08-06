---
title: MSSQLSERVER_3151 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 3151 (Database Engine error)
ms.assetid: a8657a91-ec75-4649-a09a-21920e0030ff
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: c34414754ea9d25ad89f6aba767197eb1dfc10d0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618028"
---
# <a name="mssqlserver_3151"></a><span data-ttu-id="d25b1-102">MSSQLSERVER_3151</span><span class="sxs-lookup"><span data-stu-id="d25b1-102">MSSQLSERVER_3151</span></span>
    
## <a name="details"></a><span data-ttu-id="d25b1-103">Details</span><span class="sxs-lookup"><span data-stu-id="d25b1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d25b1-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d25b1-104">Product Name</span></span>|<span data-ttu-id="d25b1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d25b1-105">SQL Server</span></span>|  
|<span data-ttu-id="d25b1-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d25b1-106">Event ID</span></span>|<span data-ttu-id="d25b1-107">3151</span><span class="sxs-lookup"><span data-stu-id="d25b1-107">3151</span></span>|  
|<span data-ttu-id="d25b1-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d25b1-108">Event Source</span></span>|<span data-ttu-id="d25b1-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d25b1-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d25b1-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="d25b1-110">Component</span></span>|<span data-ttu-id="d25b1-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d25b1-111">SQLEngine</span></span>|  
|<span data-ttu-id="d25b1-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="d25b1-112">Symbolic Name</span></span>|<span data-ttu-id="d25b1-113">LDDB_MASTER_LOAD_FAILED</span><span class="sxs-lookup"><span data-stu-id="d25b1-113">LDDB_MASTER_LOAD_FAILED</span></span>|  
|<span data-ttu-id="d25b1-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d25b1-114">Message Text</span></span>|<span data-ttu-id="d25b1-115">Fehler beim Wiederherstellen der master-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="d25b1-115">Failed to restore master database.</span></span> <span data-ttu-id="d25b1-116">SQL Server wird heruntergefahren.</span><span class="sxs-lookup"><span data-stu-id="d25b1-116">Shutting down SQL Server.</span></span> <span data-ttu-id="d25b1-117">Überprüfen Sie die Fehlerprotokolle, und erstellen Sie die master-Datenbank neu.</span><span class="sxs-lookup"><span data-stu-id="d25b1-117">Check the error logs, and rebuild the master database.</span></span> <span data-ttu-id="d25b1-118">Weitere Informationen zum Neuerstellen der master-Datenbank finden Sie in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="d25b1-118">For more information about how to rebuild the master database, see SQL Server Books Online.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d25b1-119">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d25b1-119">Explanation</span></span>  
 <span data-ttu-id="d25b1-120">Dies ist eine allgemeine Fehlermeldung, die auf verschiedene Probleme bei der **master**-Datenbank verweist.</span><span class="sxs-lookup"><span data-stu-id="d25b1-120">This is a general error message indicating various problems with the **master** database.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d25b1-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d25b1-121">User Action</span></span>  
 <span data-ttu-id="d25b1-122">Überprüfen Sie das Fehlerprotokoll auf weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="d25b1-122">Check the error logs for more information.</span></span> <span data-ttu-id="d25b1-123">Führen Sie zum Erstellen einer verwendbaren **master**-Datenbank Setup.exe mit der Option REBUILDDATABASE aus.</span><span class="sxs-lookup"><span data-stu-id="d25b1-123">To create a usable **master** database, run Setup.exe with the REBUILDDATABASE option.</span></span> <span data-ttu-id="d25b1-124">Weitere Informationen finden Sie weiter unten in diesem Thema im Abschnitt „Vorgehensweise: Installieren von SQL Server von der Eingabeaufforderung“ in der SQL Server-Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="d25b1-124">For more information see "How to: Install SQL Server from the Command Prompt" in SQL Server Books Online.</span></span>  
  
  
