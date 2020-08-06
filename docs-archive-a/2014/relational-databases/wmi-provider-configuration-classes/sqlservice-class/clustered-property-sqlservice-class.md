---
title: Clustered-Eigenschaft (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- Clustered Property (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- Clustered property
ms.assetid: f714e7f5-c2db-45c6-9536-6ca2cb5b42aa
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 86fdc87bb7b691580f7efd5ccd7b333d88a3aa78
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696557"
---
# <a name="clustered-property-sqlservice-class"></a><span data-ttu-id="ee079-102">Clustered-Eigenschaft (SqlService-Klasse)</span><span class="sxs-lookup"><span data-stu-id="ee079-102">Clustered Property (SqlService Class)</span></span>
  <span data-ttu-id="ee079-103">Ruft den booleschen Eigenschaftswert ab, der angibt, ob der Dienst Teil einer gruppierten Instanz ist.</span><span class="sxs-lookup"><span data-stu-id="ee079-103">Gets the Boolean property value that specifies whether the service is part of a clustered instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ee079-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="ee079-104">Syntax</span></span>  
  
```  
  
object  
.Clustered [= value]  
```  
  
## <a name="parts"></a><span data-ttu-id="ee079-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="ee079-105">Parts</span></span>  
 <span data-ttu-id="ee079-106">*object*</span><span class="sxs-lookup"><span data-stu-id="ee079-106">*object*</span></span>  
 <span data-ttu-id="ee079-107">Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="ee079-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="ee079-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="ee079-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="ee079-109">Ein boleescher Wert, der angibt, ob der Dienst Teil einer gruppierten Instanz ist: `true`, wenn der Dienst Teil einer gruppierten Instanz ist, bzw. `false`, wenn der Dienst nicht Teil einer gruppierten Instanz ist.</span><span class="sxs-lookup"><span data-stu-id="ee079-109">A Boolean value that specifies whether the service is participating in a clustered instance: `true` if the service is participating in a clustered instance, or `false` if the service is not participating in a clustered instance.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ee079-110">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ee079-110">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ee079-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ee079-111">See Also</span></span>  
 <span data-ttu-id="ee079-112">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="ee079-112">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
