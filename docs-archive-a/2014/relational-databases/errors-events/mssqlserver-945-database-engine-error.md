---
title: MSSQLSERVER_945 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 945 (Database Engine error)
ms.assetid: ee501d13-0bd9-4627-896c-ed5b1bdb88b3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 51284cdcf48f1bf713a853f9c87457cb5291cc4e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617038"
---
# <a name="mssqlserver_945"></a><span data-ttu-id="7431a-102">MSSQLSERVER_945</span><span class="sxs-lookup"><span data-stu-id="7431a-102">MSSQLSERVER_945</span></span>
    
## <a name="details"></a><span data-ttu-id="7431a-103">Details</span><span class="sxs-lookup"><span data-stu-id="7431a-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7431a-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="7431a-104">Product Name</span></span>|<span data-ttu-id="7431a-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="7431a-105">SQL Server</span></span>|  
|<span data-ttu-id="7431a-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7431a-106">Event ID</span></span>|<span data-ttu-id="7431a-107">945</span><span class="sxs-lookup"><span data-stu-id="7431a-107">945</span></span>|  
|<span data-ttu-id="7431a-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="7431a-108">Event Source</span></span>|<span data-ttu-id="7431a-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7431a-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7431a-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="7431a-110">Component</span></span>|<span data-ttu-id="7431a-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7431a-111">SQLEngine</span></span>|  
|<span data-ttu-id="7431a-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="7431a-112">Symbolic Name</span></span>|<span data-ttu-id="7431a-113">DB_IS_SHUTDOWN</span><span class="sxs-lookup"><span data-stu-id="7431a-113">DB_IS_SHUTDOWN</span></span>|  
|<span data-ttu-id="7431a-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="7431a-114">Message Text</span></span>|<span data-ttu-id="7431a-115">Die '%.\*ls'-Datenbank kann nicht geöffnet werden, da auf einige Dateien nicht zugegriffen werden kann oder nicht genügend Platz im Arbeitsspeicher oder auf dem Datenträger zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="7431a-115">Database '%.\*ls' cannot be opened due to inaccessible files or insufficient memory or disk space.</span></span>  <span data-ttu-id="7431a-116">Ausführliche Informationen finden Sie im SQL Server-Fehlerprotokoll.</span><span class="sxs-lookup"><span data-stu-id="7431a-116">See the SQL Server error log for details.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7431a-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="7431a-117">Explanation</span></span>  
 <span data-ttu-id="7431a-118">Der Zugriff auf die Datenbank war nicht möglich, da Dateien oder andere Ressourcen fehlen.</span><span class="sxs-lookup"><span data-stu-id="7431a-118">The database could not be accessed because files or other resources are missing.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7431a-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="7431a-119">User Action</span></span>  
 <span data-ttu-id="7431a-120">Zusätzliche Informationen zum Platz im Arbeitsspeicher, auf dem Datenträger und zum Berechtigungsfehler finden Sie im Fehlerprotokoll.</span><span class="sxs-lookup"><span data-stu-id="7431a-120">Check the error log for additional information about memory, disk space, or permission failure.</span></span> <span data-ttu-id="7431a-121">Bestätigen Sie den Speicherort der MDF- und NDF-Dateien für die entsprechende Datenbank, und bestätigen Sie, dass das von [!INCLUDE[ssDE](../../includes/ssde-md.md)] verwendete Konto über eine Berechtigung für den Zugriff auf diese Dateien verfügt.</span><span class="sxs-lookup"><span data-stu-id="7431a-121">Confirm the location of the .mdf and .ndf files for the affected database and confirm that the account used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)] has permission to access those files.</span></span> <span data-ttu-id="7431a-122">Starten Sie die Datenbank neu, nachdem das Problem behoben wurde. Verwenden Sie dazu ALTER DATABASE, und legen Sie die Datenbank auf ONLINE fest.</span><span class="sxs-lookup"><span data-stu-id="7431a-122">After correcting the problem, restart the database by using ALTER DATABASE to set it ONLINE.</span></span>  
  
  
