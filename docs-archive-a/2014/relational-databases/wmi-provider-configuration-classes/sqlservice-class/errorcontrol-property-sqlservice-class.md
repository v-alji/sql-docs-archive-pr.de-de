---
title: ErrorControl-Eigenschaft (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- ErrorControl Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- ErrorControl property
ms.assetid: cbb1e0fa-5bfc-4b1b-a6ed-f7d5cfad4d73
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 73c726af514f2880484cf927282fc0e007f07e2c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722633"
---
# <a name="errorcontrol-property-sqlservice-class"></a><span data-ttu-id="f0e89-102">ErrorControl-Eigenschaft (SqlService-Klasse)</span><span class="sxs-lookup"><span data-stu-id="f0e89-102">ErrorControl Property (SqlService Class)</span></span>
  <span data-ttu-id="f0e89-103">Ruft ab den Schweregrad des Fehlers ab, wenn der Dienst beim Hochfahren nicht gestartet wird, oder ruft diesen ab.</span><span class="sxs-lookup"><span data-stu-id="f0e89-103">Gets or sets the severity of the error if the service fails to start during startup.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0e89-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f0e89-104">Syntax</span></span>  
  
```  
  
object  
.ErrorControl [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="f0e89-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="f0e89-105">Parts</span></span>  
 <span data-ttu-id="f0e89-106">*object*</span><span class="sxs-lookup"><span data-stu-id="f0e89-106">*object*</span></span>  
 <span data-ttu-id="f0e89-107">Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="f0e89-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="f0e89-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f0e89-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="f0e89-109">Ein Zeichenfolgenwert der den gemeldeten Schweregrad des Fehlers angibt, wenn der beim Hochfahren des Diensts ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="f0e89-109">A string value that specifies the error severity reported if the service fails during startup.</span></span> <span data-ttu-id="f0e89-110">In der folgenden Tabelle sind die möglichen Werte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="f0e89-110">The following table shows the possible values.</span></span>  
  
 <span data-ttu-id="f0e89-111">Ignorieren</span><span class="sxs-lookup"><span data-stu-id="f0e89-111">Ignore</span></span>  
 <span data-ttu-id="f0e89-112">Der Benutzer wird nicht benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="f0e89-112">User is not notified.</span></span>  
  
 <span data-ttu-id="f0e89-113">Normal</span><span class="sxs-lookup"><span data-stu-id="f0e89-113">Normal</span></span>  
 <span data-ttu-id="f0e89-114">Der Benutzer wird benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="f0e89-114">User is notified.</span></span>  
  
 <span data-ttu-id="f0e89-115">Schwer</span><span class="sxs-lookup"><span data-stu-id="f0e89-115">Severe</span></span>  
 <span data-ttu-id="f0e89-116">Das System wird mit der letzten bekannten, fehlerfreien Konfiguration neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="f0e89-116">System is restarted with the last-known-good configuration.</span></span>  
  
 <span data-ttu-id="f0e89-117">Kritisch</span><span class="sxs-lookup"><span data-stu-id="f0e89-117">Critical</span></span>  
 <span data-ttu-id="f0e89-118">Das System versucht, mit einer fehlerfreien Konfiguration zu neu starten.</span><span class="sxs-lookup"><span data-stu-id="f0e89-118">System attempts to restart with a good configuration.</span></span>  
  
 <span data-ttu-id="f0e89-119">Unknown</span><span class="sxs-lookup"><span data-stu-id="f0e89-119">Unknown</span></span>  
 <span data-ttu-id="f0e89-120">Der Schweregrad ist unbekannt.</span><span class="sxs-lookup"><span data-stu-id="f0e89-120">The severity is unknown.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0e89-121">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f0e89-121">Remarks</span></span>  
 <span data-ttu-id="f0e89-122">Der Wert gibt die vom Startprogramm ausgeführte Aktion an, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="f0e89-122">The value indicates the action taken by the startup program if a failure occurs.</span></span> <span data-ttu-id="f0e89-123">Alle Fehler werden vom Computersystem protokolliert.</span><span class="sxs-lookup"><span data-stu-id="f0e89-123">All errors are logged by the computer system.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0e89-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f0e89-124">See Also</span></span>  
 <span data-ttu-id="f0e89-125">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f0e89-125">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
