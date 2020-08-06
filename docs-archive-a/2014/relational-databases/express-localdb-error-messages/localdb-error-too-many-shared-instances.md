---
title: LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: reference
ms.assetid: c1595263-6264-4a43-9535-5eb76ece3a57
author: stevestein
ms.author: sstein
ms.openlocfilehash: 0896f3e70e6c65a1fcd0de4169249fb622e6b5f8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608676"
---
# <a name="localdb_error_too_many_shared_instances"></a><span data-ttu-id="ec302-102">LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES</span><span class="sxs-lookup"><span data-stu-id="ec302-102">LOCALDB_ERROR_TOO_MANY_SHARED_INSTANCES</span></span>
    
## <a name="details"></a><span data-ttu-id="ec302-103">Details</span><span class="sxs-lookup"><span data-stu-id="ec302-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="ec302-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="ec302-104">Product Name</span></span>|<span data-ttu-id="ec302-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="ec302-105">SQL Server</span></span>|  
|<span data-ttu-id="ec302-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="ec302-106">Event ID</span></span>|<span data-ttu-id="ec302-107">287</span><span class="sxs-lookup"><span data-stu-id="ec302-107">287</span></span>|  
|<span data-ttu-id="ec302-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="ec302-108">Event Source</span></span>|<span data-ttu-id="ec302-109">Lokale SQL Server-Datenbanklaufzeit 12.0</span><span class="sxs-lookup"><span data-stu-id="ec302-109">SQL Server Local Database Runtime 12.0</span></span>|  
|<span data-ttu-id="ec302-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="ec302-110">Component</span></span>|<span data-ttu-id="ec302-111">Laufzeit-API der lokalen Datenbank</span><span class="sxs-lookup"><span data-stu-id="ec302-111">Local Database Runtime API</span></span>|  
|<span data-ttu-id="ec302-112">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="ec302-112">Message Text</span></span>|<span data-ttu-id="ec302-113">Es gibt zu viele freigegebene Instanzen, und wir können keinen eindeutigen Benutzerinstanznamen generieren.</span><span class="sxs-lookup"><span data-stu-id="ec302-113">There are too many shared instance and we cannot generate unique User Instance Name.</span></span> <span data-ttu-id="ec302-114">Heben Sie die Freigabe von einigen der vorhandenen freigegebenen Instanzen auf.</span><span class="sxs-lookup"><span data-stu-id="ec302-114">Unshare some of the existing shared instances.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="ec302-115">Erklärung</span><span class="sxs-lookup"><span data-stu-id="ec302-115">Explanation</span></span>  
 <span data-ttu-id="ec302-116">Es gibt zu viele freigegebene Instanzen, und wir können keinen eindeutigen Benutzerinstanznamen generieren.</span><span class="sxs-lookup"><span data-stu-id="ec302-116">There are too many shared instance and we cannot generate unique User Instance Name.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ec302-117">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="ec302-117">User Action</span></span>  
 <span data-ttu-id="ec302-118">Heben Sie die Freigabe einer oder mehrerer freigegebener lokaler Datenbanklaufzeitinstanzen auf, und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="ec302-118">Unshare one or more of the shared Local Database Runtime instances and try again.</span></span>  
  
  
