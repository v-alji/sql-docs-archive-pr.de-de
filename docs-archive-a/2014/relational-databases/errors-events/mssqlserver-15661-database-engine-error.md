---
title: MSSQLSERVER_15661 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 15661 (Database Engine error)
ms.assetid: 88b01bfb-74ce-4aa0-aec0-7885261c7ef3
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 966e23e8d970c36eba81253228cc18ed4af3ff77
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607806"
---
# <a name="mssqlserver_15661"></a><span data-ttu-id="5a2cf-102">MSSQLSERVER_15661</span><span class="sxs-lookup"><span data-stu-id="5a2cf-102">MSSQLSERVER_15661</span></span>
    
## <a name="details"></a><span data-ttu-id="5a2cf-103">Details</span><span class="sxs-lookup"><span data-stu-id="5a2cf-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5a2cf-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="5a2cf-104">Product Name</span></span>|<span data-ttu-id="5a2cf-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="5a2cf-105">SQL Server</span></span>|  
|<span data-ttu-id="5a2cf-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="5a2cf-106">Event ID</span></span>|<span data-ttu-id="5a2cf-107">15661</span><span class="sxs-lookup"><span data-stu-id="5a2cf-107">15661</span></span>|  
|<span data-ttu-id="5a2cf-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="5a2cf-108">Event Source</span></span>|<span data-ttu-id="5a2cf-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="5a2cf-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="5a2cf-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="5a2cf-110">Component</span></span>|<span data-ttu-id="5a2cf-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="5a2cf-111">SQLEngine</span></span>|  
|<span data-ttu-id="5a2cf-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="5a2cf-112">Symbolic Name</span></span>|<span data-ttu-id="5a2cf-113">SQLErrorNum15661</span><span class="sxs-lookup"><span data-stu-id="5a2cf-113">SQLErrorNum15661</span></span>|  
|<span data-ttu-id="5a2cf-114">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="5a2cf-114">Message Text</span></span>|<span data-ttu-id="5a2cf-115">Die gespeicherte Prozedur sp_estimate_data_compression_savings kann nicht für temporäre Tabellen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a2cf-115">The sp_estimate_data_compression_savings stored procedure cannot be used for temporary tables.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5a2cf-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="5a2cf-116">Explanation</span></span>  
 <span data-ttu-id="5a2cf-117">Eine temporäre Tabelle wurde als Argument für die gespeicherte Prozedur sp_estimate_data_compression_savings verwendet.</span><span class="sxs-lookup"><span data-stu-id="5a2cf-117">A temporary table was used as an argument for the sp_estimate_data_compression_savings stored procedure.</span></span> <span data-ttu-id="5a2cf-118">Obwohl die Komprimierung von temporären Tabellen unterstützt wird, können Sie sp_estimate_data_compression_savings nicht verwenden, um die Komprimierungseinsparungen zu schätzen.</span><span class="sxs-lookup"><span data-stu-id="5a2cf-118">Although the compression of temporary tables is supported, you cannot use sp_estimate_data_compression_savings to estimate the compression savings.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5a2cf-119">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="5a2cf-119">User Action</span></span>  
 <span data-ttu-id="5a2cf-120">Entfernen Sie die temporäre Tabelle als Argument für sp_estimate_data_compression_savings.</span><span class="sxs-lookup"><span data-stu-id="5a2cf-120">Remove the temporary table as an argument for sp_estimate_data_compression_savings.</span></span>  
  
  
