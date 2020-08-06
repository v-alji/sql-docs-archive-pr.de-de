---
title: StartMode-Eigenschaft (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StartMode Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StartMode property
ms.assetid: c0c2c7f8-d4ae-44f2-ad8e-aecfcb7c2878
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: bafffcc3c8f82f69896d0a22e9b0a9060e04cd10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717620"
---
# <a name="startmode-property-sqlservice-class"></a><span data-ttu-id="9eac8-102">StartMode-Eigenschaft (SqlService-Klasse)</span><span class="sxs-lookup"><span data-stu-id="9eac8-102">StartMode Property (SqlService Class)</span></span>
  <span data-ttu-id="9eac8-103">Ruft den Startmodus des Dienstes ab.</span><span class="sxs-lookup"><span data-stu-id="9eac8-103">Gets the start mode of the service.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9eac8-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="9eac8-104">Syntax</span></span>  
  
```  
  
object  
.StartMode [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="9eac8-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="9eac8-105">Parts</span></span>  
 <span data-ttu-id="9eac8-106">*object*</span><span class="sxs-lookup"><span data-stu-id="9eac8-106">*object*</span></span>  
 <span data-ttu-id="9eac8-107">Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="9eac8-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="9eac8-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="9eac8-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="9eac8-109">Ein uint32-Wert, der den Modus des Diensts angibt.</span><span class="sxs-lookup"><span data-stu-id="9eac8-109">A uint32 value that specifies the mode of the service.</span></span>  
  
 <span data-ttu-id="9eac8-110">Folgende Werte sind möglich:</span><span class="sxs-lookup"><span data-stu-id="9eac8-110">Values can be one of the following.</span></span>  
  
 <span data-ttu-id="9eac8-111">Start</span><span class="sxs-lookup"><span data-stu-id="9eac8-111">Boot</span></span>  
 <span data-ttu-id="9eac8-112">Wert = 0.</span><span class="sxs-lookup"><span data-stu-id="9eac8-112">Value = 0.</span></span> <span data-ttu-id="9eac8-113">Dienst wurde durch das Betriebssystemladeprogramm gestartet.</span><span class="sxs-lookup"><span data-stu-id="9eac8-113">Service started by the operating system loader.</span></span> <span data-ttu-id="9eac8-114">Diese Option ist nur für Treiberdienste gültig.</span><span class="sxs-lookup"><span data-stu-id="9eac8-114">This option is valid only for driver services.</span></span>  
  
 <span data-ttu-id="9eac8-115">System</span><span class="sxs-lookup"><span data-stu-id="9eac8-115">System</span></span>  
 <span data-ttu-id="9eac8-116">Wert = 1.</span><span class="sxs-lookup"><span data-stu-id="9eac8-116">Value = 1.</span></span> <span data-ttu-id="9eac8-117">Der Dienst wurde durch die `IoInitSystem`-Methode gestartet.</span><span class="sxs-lookup"><span data-stu-id="9eac8-117">Service started by the `IoInitSystem` method.</span></span> <span data-ttu-id="9eac8-118">Diese Option ist nur für Treiberdienste gültig.</span><span class="sxs-lookup"><span data-stu-id="9eac8-118">This option is valid only for driver services.</span></span>  
  
 <span data-ttu-id="9eac8-119">Automatisch</span><span class="sxs-lookup"><span data-stu-id="9eac8-119">Automatic</span></span>  
 <span data-ttu-id="9eac8-120">Wert = 2.</span><span class="sxs-lookup"><span data-stu-id="9eac8-120">Value = 2.</span></span> <span data-ttu-id="9eac8-121">Der Dienst soll während des Systemstarts automatisch vom Dienstkontroll-Manager gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="9eac8-121">Service to be started automatically by the service control manager during system startup.</span></span>  
  
 <span data-ttu-id="9eac8-122">Manuell</span><span class="sxs-lookup"><span data-stu-id="9eac8-122">Manual</span></span>  
 <span data-ttu-id="9eac8-123">Wert = 3.</span><span class="sxs-lookup"><span data-stu-id="9eac8-123">Value = 3.</span></span> <span data-ttu-id="9eac8-124">Der Dienst soll vom Computer-manager gestartet werden, wenn ein Prozess die `StartService`-Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="9eac8-124">Service to be started by the Computer Manager when a process calls the `StartService` method.</span></span>  
  
 <span data-ttu-id="9eac8-125">Disabled</span><span class="sxs-lookup"><span data-stu-id="9eac8-125">Disabled</span></span>  
 <span data-ttu-id="9eac8-126">Wert = 4.</span><span class="sxs-lookup"><span data-stu-id="9eac8-126">Value = 4.</span></span> <span data-ttu-id="9eac8-127">Der Dienst kann nicht gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="9eac8-127">Service cannot be started.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9eac8-128">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9eac8-128">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9eac8-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9eac8-129">See Also</span></span>  
 <span data-ttu-id="9eac8-130">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="9eac8-130">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
