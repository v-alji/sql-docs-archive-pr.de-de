---
title: MSSQLSERVER_948 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "948"
helpviewer_keywords:
- 948 (Database Engine error)
ms.assetid: 95c4ad45-a518-4165-a5c4-6e6b932b0570
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e8461069a3fceb7bdca318b82a522f7f51af83d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617036"
---
# <a name="mssqlserver_948"></a><span data-ttu-id="dc74c-102">MSSQLSERVER_948</span><span class="sxs-lookup"><span data-stu-id="dc74c-102">MSSQLSERVER_948</span></span>
    
## <a name="details"></a><span data-ttu-id="dc74c-103">Details</span><span class="sxs-lookup"><span data-stu-id="dc74c-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="dc74c-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="dc74c-104">Product Name</span></span>|<span data-ttu-id="dc74c-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="dc74c-105">SQL Server</span></span>|  
|<span data-ttu-id="dc74c-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="dc74c-106">Event ID</span></span>|<span data-ttu-id="dc74c-107">948</span><span class="sxs-lookup"><span data-stu-id="dc74c-107">948</span></span>|  
|<span data-ttu-id="dc74c-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="dc74c-108">Event Source</span></span>|<span data-ttu-id="dc74c-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="dc74c-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="dc74c-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="dc74c-110">Component</span></span>|<span data-ttu-id="dc74c-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="dc74c-111">SQLEngine</span></span>|  
|<span data-ttu-id="dc74c-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="dc74c-112">Symbolic Name</span></span>|<span data-ttu-id="dc74c-113">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="dc74c-113">NA</span></span>|  
|<span data-ttu-id="dc74c-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="dc74c-114">Message Text</span></span>|<span data-ttu-id="dc74c-115">Die '%.\*ls'-Datenbank kann nicht geöffnet werden, weil sie die Version %d aufweist.</span><span class="sxs-lookup"><span data-stu-id="dc74c-115">The database '%.\*ls' cannot be opened because it is version %d.</span></span> <span data-ttu-id="dc74c-116">Dieser Server unterstützt Version %d und früher.</span><span class="sxs-lookup"><span data-stu-id="dc74c-116">This server supports version %d and earlier.</span></span> <span data-ttu-id="dc74c-117">Ein Herabstufungspfad wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="dc74c-117">A downgrade path is not supported.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="dc74c-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="dc74c-118">Explanation</span></span>  
 <span data-ttu-id="dc74c-119">Bestimmte funktionen in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wirken sich auf die Struktur der Datenbankdateien aus.</span><span class="sxs-lookup"><span data-stu-id="dc74c-119">Certain features in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] affect the structure of the database files.</span></span> <span data-ttu-id="dc74c-120">Wenn Sie eine Datenbank an eine andere Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] anfügen, ist das Dateiformat möglicherweise mit einer anderen Version von [!INCLUDE[ssDE](../../includes/ssde-md.md)] nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="dc74c-120">When you attach a database to another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the file format might not be compatible with a different version of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
 <span data-ttu-id="dc74c-121">Dieser Fehler kann beispielsweise verursacht werden, wenn das vardecimal-Speicherformat in einer höheren Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] verwendet wird und dann versucht wird, die Datenbankdateien in einer niedrigeren Version als [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2 anzufügen.</span><span class="sxs-lookup"><span data-stu-id="dc74c-121">For example, this error can be caused by using the vardecimal storage format in a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and then trying to attach the database files in a version earlier than [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] Service Pack 2.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="dc74c-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="dc74c-122">User Action</span></span>  
 <span data-ttu-id="dc74c-123">Ermitteln Sie die Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], die auf dem ursprünglichen Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dc74c-123">Determine the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that is running on the originating server.</span></span> <span data-ttu-id="dc74c-124">[!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]Klicken Sie in entweder mit der rechten Maustaste auf den Server, und klicken Sie dann auf **Eigenschaften** , oder geben Sie `SELECT @@VERSION` ein Abfragefenster ein.</span><span class="sxs-lookup"><span data-stu-id="dc74c-124">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], either right-click the server and then click **Properties** or type `SELECT @@VERSION` in a query window.</span></span> <span data-ttu-id="dc74c-125">Öffnen Sie die Datenbank mithilfe der ursprünglichen Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="dc74c-125">Open the database by using the original version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dc74c-126">Ermitteln Sie die funktionen, die für die ursprüngliche Datenbank in der Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aktiviert sind.</span><span class="sxs-lookup"><span data-stu-id="dc74c-126">Investigate the features that are enabled on the original database in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="dc74c-127">Ändern Sie diese Einstellungen, um mit der Version von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu arbeiten, in der die Datenbank angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="dc74c-127">Modify these settings to work with the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in which the database will be attached.</span></span>  
  
  
