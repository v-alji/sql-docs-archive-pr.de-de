---
title: MSSQLSERVER_3169 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "3169"
helpviewer_keywords:
- 3169 (Database Engine error)
ms.assetid: 7d4dbed6-bb94-4908-bc03-2040a9cf63bc
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 8b13d9c1c17eddb34648bc4a536e2fccf371b99a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618022"
---
# <a name="mssqlserver_3169"></a><span data-ttu-id="f5944-102">MSSQLSERVER_3169</span><span class="sxs-lookup"><span data-stu-id="f5944-102">MSSQLSERVER_3169</span></span>
    
## <a name="details"></a><span data-ttu-id="f5944-103">Details</span><span class="sxs-lookup"><span data-stu-id="f5944-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="f5944-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="f5944-104">Product Name</span></span>|<span data-ttu-id="f5944-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="f5944-105">SQL Server</span></span>|  
|<span data-ttu-id="f5944-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="f5944-106">Event ID</span></span>|<span data-ttu-id="f5944-107">3169</span><span class="sxs-lookup"><span data-stu-id="f5944-107">3169</span></span>|  
|<span data-ttu-id="f5944-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="f5944-108">Event Source</span></span>|<span data-ttu-id="f5944-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="f5944-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="f5944-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="f5944-110">Component</span></span>|<span data-ttu-id="f5944-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="f5944-111">SQLEngine</span></span>|  
|<span data-ttu-id="f5944-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="f5944-112">Symbolic Name</span></span>|<span data-ttu-id="f5944-113">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="f5944-113">NA</span></span>|  
|<span data-ttu-id="f5944-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="f5944-114">Message Text</span></span>|<span data-ttu-id="f5944-115">Die Datenbank wurde auf einem Server der Version %ls gesichert.</span><span class="sxs-lookup"><span data-stu-id="f5944-115">The database was backed up on a server running version %ls.</span></span> <span data-ttu-id="f5944-116">Diese Version ist mit diesem Server inkompatibel, da auf ihm die Version %ls ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f5944-116">That version is incompatible with this server, which is running version %ls.</span></span> <span data-ttu-id="f5944-117">Stellen Sie die Datenbank auf einem Server wieder her, der die Sicherung unterstützt, oder verwenden Sie eine mit diesem Server kompatible Sicherung.</span><span class="sxs-lookup"><span data-stu-id="f5944-117">Either restore the database on a server that supports the backup, or use a backup that is compatible with this server.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="f5944-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="f5944-118">Explanation</span></span>  
 <span data-ttu-id="f5944-119">Bestimmte funktionen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wirken sich auf die Struktur der Datenbankdateien aus.</span><span class="sxs-lookup"><span data-stu-id="f5944-119">Certain features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affect the structure of the database files.</span></span> <span data-ttu-id="f5944-120">Wenn Sie eine Datenbank auf einer anderen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wiederherstellen, ist das Dateiformat möglicherweise mit einer anderen Version von [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="f5944-120">When you restore a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the file format might not be compatible with a different version of the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span>  
  
 <span data-ttu-id="f5944-121">Dieser Fehler kann beispielsweise verursacht werden, wenn das Vardecimal-Speicherformat in einer höheren Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet wird und dann versucht wird, die Datenbankdateien in einer niedrigeren Version als [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2 wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="f5944-121">For example, this error can be caused by using the vardecimalstorage format in a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then trying to restore the database files in a version earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="f5944-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="f5944-122">User Action</span></span>  
 <span data-ttu-id="f5944-123">Ermitteln Sie die Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], die auf dem ursprünglichen Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f5944-123">Determine the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on the originating server.</span></span> <span data-ttu-id="f5944-124">[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Klicken Sie in entweder mit der rechten Maustaste auf den Server, und klicken Sie dann auf **Eigenschaften** , oder geben Sie `SELECT @@VERSION` ein Abfragefenster ein.</span><span class="sxs-lookup"><span data-stu-id="f5944-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], either right-click the server and then click **Properties** or type `SELECT @@VERSION` in a query window.</span></span> <span data-ttu-id="f5944-125">Öffnen Sie die Datenbank mithilfe der ursprünglichen Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f5944-125">Open the database by using the original version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f5944-126">Ermitteln Sie die funktionen, die für die ursprüngliche Datenbank in der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="f5944-126">Investigate the features that are enabled on the original database in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f5944-127">Ändern Sie diese Einstellungen, um mit der Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu arbeiten, in der die Datenbank wiederhergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f5944-127">Modify these settings to work with the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in which the database will be restored.</span></span>  
  
  
