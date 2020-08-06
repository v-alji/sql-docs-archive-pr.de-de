---
title: PauseService-Methode (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- PauseService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- PauseService method
ms.assetid: 5c3a8feb-58b8-4385-b4c8-bf33cf4d276d
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 8286e123bbbc279ba461336c5716eeb208c5b238
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617842"
---
# <a name="pauseservice-method-sqlservice-class"></a><span data-ttu-id="b1883-102">PauseService-Methode (SqlService-Klasse)</span><span class="sxs-lookup"><span data-stu-id="b1883-102">PauseService Method (SqlService Class)</span></span>
  <span data-ttu-id="b1883-103">Versucht, den Dienst anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="b1883-103">Attempts to place the service in the paused state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b1883-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b1883-104">Syntax</span></span>  
  
```  
  
object  
.PauseService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="b1883-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="b1883-105">Parts</span></span>  
 <span data-ttu-id="b1883-106">*object*</span><span class="sxs-lookup"><span data-stu-id="b1883-106">*object*</span></span>  
 <span data-ttu-id="b1883-107">Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="b1883-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b1883-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b1883-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="b1883-109">Ein uint32-Wert, der 0 beträgt, wenn der Dienst erfolgreich angehalten wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="b1883-109">A uint32 value, which is 0 if the service was successfully stopped, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b1883-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b1883-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1883-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b1883-111">See Also</span></span>  
 <span data-ttu-id="b1883-112">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="b1883-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
