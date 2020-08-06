---
title: SetStartMode-Methode (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetStartMode Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetStartMode method
ms.assetid: f6f198b4-f9a4-468c-8977-76462ef06e61
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: a9b7310623f526d7b106485ed9681df3aa100129
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608453"
---
# <a name="setstartmode-method-sqlservice-class"></a><span data-ttu-id="7bb9e-102">SetStartMode-Methode (SqlService-Klasse)</span><span class="sxs-lookup"><span data-stu-id="7bb9e-102">SetStartMode Method (SqlService Class)</span></span>
  <span data-ttu-id="7bb9e-103">Ändert den Startmodus der Dienstinstanz.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-103">Modifies the start mode of the service instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7bb9e-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="7bb9e-104">Syntax</span></span>  
  
```  
  
object  
.SetStartMode(  
StartMode  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="7bb9e-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="7bb9e-105">Parts</span></span>  
 <span data-ttu-id="7bb9e-106">*object*</span><span class="sxs-lookup"><span data-stu-id="7bb9e-106">*object*</span></span>  
 <span data-ttu-id="7bb9e-107">Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="7bb9e-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="7bb9e-108">Parameters</span></span>  
 <span data-ttu-id="7bb9e-109">*StartMode*</span><span class="sxs-lookup"><span data-stu-id="7bb9e-109">*StartMode*</span></span>  
 <span data-ttu-id="7bb9e-110">Ein `uint32`-Wert, der den Startmodus der Dienstinstanz angibt.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-110">A `uint32` value that specifies the start mode of the service instance.</span></span>  
  
 <span data-ttu-id="7bb9e-111">Die folgenden Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="7bb9e-111">The valid values are as follows:</span></span>  
  
 <span data-ttu-id="7bb9e-112">Wert = 0.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-112">Value = 0.</span></span> <span data-ttu-id="7bb9e-113">Neustart: Der Dienst wurde durch das Betriebssystemladeprogramm gestartet.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-113">Boot - Device driver started by the operating system loader.</span></span> <span data-ttu-id="7bb9e-114">Dieses Wert ist nur für Treiberdienste gültig.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-114">This value is valid only for driver services.</span></span>  
  
 <span data-ttu-id="7bb9e-115">Wert = 1.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-115">Value = 1.</span></span> <span data-ttu-id="7bb9e-116">System: Der Gerätetreiber wurde durch die `IoInitSystem`-Methode gestartet.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-116">System - Device driver started by the `IoInitSystem` method.</span></span> <span data-ttu-id="7bb9e-117">Dieses Wert ist nur für Treiberdienste gültig.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-117">This value is valid only for driver services.</span></span>  
  
 <span data-ttu-id="7bb9e-118">Wert = 2.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-118">Value = 2.</span></span> <span data-ttu-id="7bb9e-119">Automatisch: Der Dienst soll während des Systemstarts automatisch vom Dienstkontroll-Manager gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-119">Automatic - Service to be started automatically by the service control manager during system startup.</span></span>  
  
 <span data-ttu-id="7bb9e-120">Wert = 3.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-120">Value = 3.</span></span> <span data-ttu-id="7bb9e-121">Manuell: Der Dienst soll vom Computer-Manager gestartet werden, wenn ein Prozess die `StartService`-Methode aufruft.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-121">Manual - Service to be started by the Computer Manager when a process calls the `StartService` method.</span></span>  
  
 <span data-ttu-id="7bb9e-122">Wert = 4.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-122">Value = 4.</span></span> <span data-ttu-id="7bb9e-123">Deaktiviert: Der Dienst kann nicht mehr gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-123">Disabled - Service can no longer be started.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="7bb9e-124">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="7bb9e-124">Property Value/Return Value</span></span>  
 <span data-ttu-id="7bb9e-125">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-125">A `uint32` value, which is 0 if the service was successfully modified or 1 if the request is not supported.</span></span> <span data-ttu-id="7bb9e-126">Jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="7bb9e-126">Any other number indicates an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7bb9e-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="7bb9e-127">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bb9e-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7bb9e-128">See Also</span></span>  
 <span data-ttu-id="7bb9e-129">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="7bb9e-129">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
