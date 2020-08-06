---
title: State-Eigenschaft (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- State Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- State property
ms.assetid: 9e09f419-947c-4d4b-9a49-2d3396c847cd
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a7456113d9ec4444507d1057892a65adf241992f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717602"
---
# <a name="state-property-sqlservice-class"></a><span data-ttu-id="bfe48-102">State-Eigenschaft (SqlService-Klasse)</span><span class="sxs-lookup"><span data-stu-id="bfe48-102">State Property (SqlService Class)</span></span>
  <span data-ttu-id="bfe48-103">Ruft den aktuellen Zustand des Diensts ab oder legt diesen fest.</span><span class="sxs-lookup"><span data-stu-id="bfe48-103">Gets or sets the current state of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfe48-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="bfe48-104">Syntax</span></span>  
  
```  
  
object  
.State [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="bfe48-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="bfe48-105">Parts</span></span>  
 <span data-ttu-id="bfe48-106">*object*</span><span class="sxs-lookup"><span data-stu-id="bfe48-106">*object*</span></span>  
 <span data-ttu-id="bfe48-107">Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="bfe48-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="bfe48-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="bfe48-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="bfe48-109">Ein uint32-Wert, der den Zustand des Diensts angibt.</span><span class="sxs-lookup"><span data-stu-id="bfe48-109">A uint32 value that specifies the state of the service.</span></span>  
  
 <span data-ttu-id="bfe48-110">Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="bfe48-110">Values can be one of the following.</span></span>  
  
 <span data-ttu-id="bfe48-111">1</span><span class="sxs-lookup"><span data-stu-id="bfe48-111">1</span></span>  
 <span data-ttu-id="bfe48-112">Beendet.</span><span class="sxs-lookup"><span data-stu-id="bfe48-112">Stopped.</span></span> <span data-ttu-id="bfe48-113">Der -Dienst wurde beendet.</span><span class="sxs-lookup"><span data-stu-id="bfe48-113">The service is stopped.</span></span>  
  
 <span data-ttu-id="bfe48-114">2</span><span class="sxs-lookup"><span data-stu-id="bfe48-114">2</span></span>  
 <span data-ttu-id="bfe48-115">Start steht aus.</span><span class="sxs-lookup"><span data-stu-id="bfe48-115">Start Pending.</span></span> <span data-ttu-id="bfe48-116">Der Dienst wartet darauf, gestartet zu werden.</span><span class="sxs-lookup"><span data-stu-id="bfe48-116">The service is waiting to start.</span></span>  
  
 <span data-ttu-id="bfe48-117">3</span><span class="sxs-lookup"><span data-stu-id="bfe48-117">3</span></span>  
 <span data-ttu-id="bfe48-118">Beenden steht aus.</span><span class="sxs-lookup"><span data-stu-id="bfe48-118">Stop Pending.</span></span> <span data-ttu-id="bfe48-119">Der Dienst wartet darauf, beendet zu werden.</span><span class="sxs-lookup"><span data-stu-id="bfe48-119">The service is waiting to stop.</span></span>  
  
 <span data-ttu-id="bfe48-120">4</span><span class="sxs-lookup"><span data-stu-id="bfe48-120">4</span></span>  
 <span data-ttu-id="bfe48-121">Wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bfe48-121">Running.</span></span> <span data-ttu-id="bfe48-122">Der Dienst wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bfe48-122">The service is running.</span></span>  
  
 <span data-ttu-id="bfe48-123">5</span><span class="sxs-lookup"><span data-stu-id="bfe48-123">5</span></span>  
 <span data-ttu-id="bfe48-124">Fortsetzung steht aus.</span><span class="sxs-lookup"><span data-stu-id="bfe48-124">Continue Pending.</span></span> <span data-ttu-id="bfe48-125">Der Dienst wartet darauf, fortgesetzt zu werden.</span><span class="sxs-lookup"><span data-stu-id="bfe48-125">The service is waiting to continue.</span></span>  
  
 <span data-ttu-id="bfe48-126">6</span><span class="sxs-lookup"><span data-stu-id="bfe48-126">6</span></span>  
 <span data-ttu-id="bfe48-127">Anhalten steht aus.</span><span class="sxs-lookup"><span data-stu-id="bfe48-127">Pause Pending.</span></span> <span data-ttu-id="bfe48-128">Der Dienst wartet darauf, angehalten zu werden.</span><span class="sxs-lookup"><span data-stu-id="bfe48-128">The service is waiting to pause.</span></span>  
  
 <span data-ttu-id="bfe48-129">7</span><span class="sxs-lookup"><span data-stu-id="bfe48-129">7</span></span>  
 <span data-ttu-id="bfe48-130">Angehalten.</span><span class="sxs-lookup"><span data-stu-id="bfe48-130">Paused.</span></span> <span data-ttu-id="bfe48-131">Der Dienst wurde angehalten.</span><span class="sxs-lookup"><span data-stu-id="bfe48-131">The service is paused.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfe48-132">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="bfe48-132">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfe48-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bfe48-133">See Also</span></span>  
 <span data-ttu-id="bfe48-134">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="bfe48-134">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
