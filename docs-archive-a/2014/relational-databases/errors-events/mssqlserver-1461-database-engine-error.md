---
title: MSSQLSERVER_1461 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 1461 (Database Engine error)
ms.assetid: fce10907-4753-441b-b624-f28e00ed7520
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 6667728b2cc134632ddc538b662d73533ee4d6ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620950"
---
# <a name="mssqlserver_1461"></a><span data-ttu-id="6626e-102">MSSQLSERVER_1461</span><span class="sxs-lookup"><span data-stu-id="6626e-102">MSSQLSERVER_1461</span></span>
    
## <a name="details"></a><span data-ttu-id="6626e-103">Details</span><span class="sxs-lookup"><span data-stu-id="6626e-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="6626e-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="6626e-104">Product Name</span></span>|<span data-ttu-id="6626e-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6626e-105">SQL Server</span></span>|  
|<span data-ttu-id="6626e-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="6626e-106">Event ID</span></span>|<span data-ttu-id="6626e-107">1461</span><span class="sxs-lookup"><span data-stu-id="6626e-107">1461</span></span>|  
|<span data-ttu-id="6626e-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="6626e-108">Event Source</span></span>|<span data-ttu-id="6626e-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="6626e-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="6626e-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="6626e-110">Component</span></span>|<span data-ttu-id="6626e-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="6626e-111">SQLEngine</span></span>|  
|<span data-ttu-id="6626e-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="6626e-112">Symbolic Name</span></span>|<span data-ttu-id="6626e-113">DBM_SAFETY_MISMATCH</span><span class="sxs-lookup"><span data-stu-id="6626e-113">DBM_SAFETY_MISMATCH</span></span>|  
|<span data-ttu-id="6626e-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="6626e-114">Message Text</span></span>|<span data-ttu-id="6626e-115">Für die "%.\*ls"-Datenbank wurden bei den Servern unterschiedliche Sicherheitsstufen für die Datenbankspiegelung gefunden.</span><span class="sxs-lookup"><span data-stu-id="6626e-115">Different database mirroring safety levels among servers were detected for database "%.\*ls".</span></span> <span data-ttu-id="6626e-116">Die Sicherheitsstufe FULL wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="6626e-116">The FULL safety level will be used.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="6626e-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="6626e-117">Explanation</span></span>  
 <span data-ttu-id="6626e-118">Die Spiegelungsverbindungen wurden unterbrochen, als die Sicherheitsstufe der Transaktion geändert wurde, da die Sicherheitseinstellungen der Transaktion für die Prinzipal- und Spiegeldatenbank inkonsistent waren.</span><span class="sxs-lookup"><span data-stu-id="6626e-118">Mirroring connections were broken when the transaction safety level was modified because the transaction safety settings were inconsistent on the principal and mirror databases.</span></span> <span data-ttu-id="6626e-119">Es wird die Standardsicherheitseinstellung der Sicherheit für vollständige Transaktionen verwendet.</span><span class="sxs-lookup"><span data-stu-id="6626e-119">The default safety setting of full-transaction safety will be used.</span></span> <span data-ttu-id="6626e-120">Die Sitzung wird im Modus für hohe Sicherheit ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6626e-120">The session will run in high-safety mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="6626e-121">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="6626e-121">User Action</span></span>  
 <span data-ttu-id="6626e-122">Wenn Sie die Transaktionssicherheit initiieren möchten, führen Sie die ALTER DATABASE *Datenbank_Name* SET PARTNER SAFETY OFF-Anweisung für die Prinzipaldatenbank erneut aus.</span><span class="sxs-lookup"><span data-stu-id="6626e-122">To set transaction safety off, rerun the ALTER DATABASE *database_name* SET PARTNER SAFETY OFF statement on the principal database.</span></span>  
  
  
