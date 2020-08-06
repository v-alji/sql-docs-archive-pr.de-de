---
title: LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: a7c5ce08-8841-49a3-b252-116807ba469a
author: stevestein
ms.author: sstein
ms.openlocfilehash: aa6db2af138bb2aeefb1a922e55db56c4ea821f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726969"
---
# <a name="localdb_error_instance_exists_with_lower_version"></a><span data-ttu-id="acfd1-102">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span><span class="sxs-lookup"><span data-stu-id="acfd1-102">LOCALDB_ERROR_INSTANCE_EXISTS_WITH_LOWER_VERSION</span></span>
    
## <a name="details"></a><span data-ttu-id="acfd1-103">Details</span><span class="sxs-lookup"><span data-stu-id="acfd1-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="acfd1-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="acfd1-104">Product Name</span></span>|<span data-ttu-id="acfd1-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="acfd1-105">SQL Server</span></span>|  
|<span data-ttu-id="acfd1-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="acfd1-106">Event ID</span></span>|<span data-ttu-id="acfd1-107">258</span><span class="sxs-lookup"><span data-stu-id="acfd1-107">258</span></span>|  
|<span data-ttu-id="acfd1-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="acfd1-108">Event Source</span></span>|<span data-ttu-id="acfd1-109">Lokale SQL Server-Datenbanklaufzeit 12.0</span><span class="sxs-lookup"><span data-stu-id="acfd1-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="acfd1-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="acfd1-110">Component</span></span>|<span data-ttu-id="acfd1-111">Laufzeit-API der lokalen Datenbank</span><span class="sxs-lookup"><span data-stu-id="acfd1-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="acfd1-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="acfd1-112">Message Text</span></span>|<span data-ttu-id="acfd1-113">Es konnte keine lokale Datenbankinstanz der angegebenen Version erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="acfd1-113">Unable to create the Local Database instance with specified version.</span></span> <span data-ttu-id="acfd1-114">Eine Instanz mit diesem Namen ist zwar bereits vorhanden, aber deren Version ist niedriger als die angegebene Version.</span><span class="sxs-lookup"><span data-stu-id="acfd1-114">An instance with the same name already exists, but it has lower version than the specified version.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="acfd1-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="acfd1-115">Explanation</span></span>  
 <span data-ttu-id="acfd1-116">Die angegebene Instanz ist bereits vorhanden, aber ihre Version ist niedriger als angefordert.</span><span class="sxs-lookup"><span data-stu-id="acfd1-116">The specified instance already exists but its version is lower than requested.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="acfd1-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="acfd1-117">User Action</span></span>  
 <span data-ttu-id="acfd1-118">Löschen Sie die vorhandene Instanz, und wiederholen Sie den Vorgang.</span><span class="sxs-lookup"><span data-stu-id="acfd1-118">Delete the existing instance and retry the operation.</span></span>  
  
  
