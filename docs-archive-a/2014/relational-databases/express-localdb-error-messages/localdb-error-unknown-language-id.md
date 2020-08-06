---
title: LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: fa082dca-bf88-46e7-b61e-7ac8835a3493
author: stevestein
ms.author: sstein
ms.openlocfilehash: e71f7b443a1999a5edbb17dc11ee4d578834faf4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619126"
---
# <a name="localdb_error_unknown_language_id"></a><span data-ttu-id="2b512-102">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span><span class="sxs-lookup"><span data-stu-id="2b512-102">LOCALDB_ERROR_UNKNOWN_LANGUAGE_ID</span></span>
    
## <a name="details"></a><span data-ttu-id="2b512-103">Details</span><span class="sxs-lookup"><span data-stu-id="2b512-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="2b512-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="2b512-104">Product Name</span></span>|<span data-ttu-id="2b512-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="2b512-105">SQL Server</span></span>|  
|<span data-ttu-id="2b512-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="2b512-106">Event ID</span></span>|<span data-ttu-id="2b512-107">270</span><span class="sxs-lookup"><span data-stu-id="2b512-107">270</span></span>|  
|<span data-ttu-id="2b512-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="2b512-108">Event Source</span></span>|<span data-ttu-id="2b512-109">Lokale SQL Server-Datenbanklaufzeit 12.0</span><span class="sxs-lookup"><span data-stu-id="2b512-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="2b512-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="2b512-110">Component</span></span>|<span data-ttu-id="2b512-111">Laufzeit-API der lokalen Datenbank</span><span class="sxs-lookup"><span data-stu-id="2b512-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="2b512-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="2b512-112">Message Text</span></span>|<span data-ttu-id="2b512-113">Fehler beim Abrufen der lokalisierten Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="2b512-113">Error getting the localized error message.</span></span> <span data-ttu-id="2b512-114">Die im LanguageID-Parameter angegebene Sprache ist unbekannt.</span><span class="sxs-lookup"><span data-stu-id="2b512-114">The language specified by 'Language ID' parameter is unknown.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="2b512-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="2b512-115">Explanation</span></span>  
 <span data-ttu-id="2b512-116">Die angeforderte Sprache für die Laufzeitfehlermeldung der lokalen Datenbank ist unbekannt oder wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2b512-116">The requested language for the Local Database Runtime error message is unknown or not supported.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="2b512-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="2b512-117">User Action</span></span>  
 <span data-ttu-id="2b512-118">Versuchen Sie, eine der unterstützten Sprachen für Laufzeitfehlermeldungen der lokalen Datenbank oder eine Standardsprache anzufordern.</span><span class="sxs-lookup"><span data-stu-id="2b512-118">Try requesting one of the supported languages for Local Database Runtime error messages, or a default language.</span></span>  
  
  
