---
title: MSSQLSERVER_7901 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 7901 (Database Engine error)
ms.assetid: 2d0d19b9-947b-4474-9ff8-7e03019ab93d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: fae6e55cbe7170f795aff85400da2c5cdaef780a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618011"
---
# <a name="mssqlserver_7901"></a><span data-ttu-id="d41d0-102">MSSQLSERVER_7901</span><span class="sxs-lookup"><span data-stu-id="d41d0-102">MSSQLSERVER_7901</span></span>
    
## <a name="details"></a><span data-ttu-id="d41d0-103">Details</span><span class="sxs-lookup"><span data-stu-id="d41d0-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d41d0-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="d41d0-104">Product Name</span></span>|<span data-ttu-id="d41d0-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="d41d0-105">SQL Server</span></span>|  
|<span data-ttu-id="d41d0-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="d41d0-106">Event ID</span></span>|<span data-ttu-id="d41d0-107">7901</span><span class="sxs-lookup"><span data-stu-id="d41d0-107">7901</span></span>|  
|<span data-ttu-id="d41d0-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="d41d0-108">Event Source</span></span>|<span data-ttu-id="d41d0-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="d41d0-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="d41d0-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="d41d0-110">Component</span></span>|<span data-ttu-id="d41d0-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="d41d0-111">SQLEngine</span></span>|  
|<span data-ttu-id="d41d0-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="d41d0-112">Symbolic Name</span></span>|<span data-ttu-id="d41d0-113">DBCC2_DATABASE_IN_EMERGENCY_MODE</span><span class="sxs-lookup"><span data-stu-id="d41d0-113">DBCC2_DATABASE_IN_EMERGENCY_MODE</span></span>|  
|<span data-ttu-id="d41d0-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="d41d0-114">Message Text</span></span>|<span data-ttu-id="d41d0-115">Die REPAIR-Anweisung wurde nicht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="d41d0-115">The repair statement was not processed.</span></span> <span data-ttu-id="d41d0-116">Diese Reparaturstufe wird nicht unterstützt, wenn sich die Datenbank im Notfallmodus befindet.</span><span class="sxs-lookup"><span data-stu-id="d41d0-116">This level of repair is not supported when the database is in emergency mode.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d41d0-117">Erklärung</span><span class="sxs-lookup"><span data-stu-id="d41d0-117">Explanation</span></span>  
 <span data-ttu-id="d41d0-118">Die Datenbank befindet sich im Notfallmodus, und eine andere Reparaturstufe als REPAIR_ALLOW_DATA_LOSS wurde angegeben.</span><span class="sxs-lookup"><span data-stu-id="d41d0-118">The database is in emergency mode and a repair level other than REPAIR_ALLOW_DATA_LOSS has been specified.</span></span> <span data-ttu-id="d41d0-119">Reparaturen können nicht im Notfallmodus durchgeführt werden, außer wenn REPAIR_ALLOW_DATA_LOSS angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="d41d0-119">Repairs cannot be made in emergency mode unless REPAIR_ALLOW_DATA_LOSS is specified.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d41d0-120">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="d41d0-120">User Action</span></span>  
 <span data-ttu-id="d41d0-121">Führen Sie den Befehl erneut aus, und geben Sie die REPAIR_ALLOW_DATA_LOSS-Option an.</span><span class="sxs-lookup"><span data-stu-id="d41d0-121">Rerun the command and specify the REPAIR_ALLOW_DATA_LOSS option.</span></span>  
  
  
