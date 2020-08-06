---
title: SetDefaults-Methode (ClientSettings-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (ClientSettings Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: 056508f3-a5c8-467c-a196-dc1ef1f5178f
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: b6985ebfa4a9145dd3474cec31f32cdab9c11cdc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621895"
---
# <a name="setdefaults-method-clientsettings-class"></a><span data-ttu-id="2263f-102">SetDefaults-Methode (ClientSettings-Klasse)</span><span class="sxs-lookup"><span data-stu-id="2263f-102">SetDefaults Method (ClientSettings Class)</span></span>
  <span data-ttu-id="2263f-103">Legt alle Standardwerte für die Instanz des- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Clients fest, wobei die Option zum Überschreiben vorhandener Daten besteht.</span><span class="sxs-lookup"><span data-stu-id="2263f-103">Sets all the default values for the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2263f-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="2263f-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="2263f-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="2263f-105">Parts</span></span>  
 <span data-ttu-id="2263f-106">*object*</span><span class="sxs-lookup"><span data-stu-id="2263f-106">*object*</span></span>  
 <span data-ttu-id="2263f-107">Ein `ClientSettings`-Objekt, das eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Clientinstanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="2263f-107">A `ClientSettings` object that represents a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="2263f-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="2263f-108">Parameters</span></span>  
  
|<span data-ttu-id="2263f-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="2263f-109">Parameter</span></span>|<span data-ttu-id="2263f-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="2263f-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2263f-111">*Overschreiteall*</span><span class="sxs-lookup"><span data-stu-id="2263f-111">*OverwriteAll*</span></span>|<span data-ttu-id="2263f-112">Ein boolescher Wert, der angibt, ob vorhandene Werte für die Instanz des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Clients überschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2263f-112">A Boolean value that specifies whether to overwrite existing values on the instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client.</span></span> <span data-ttu-id="2263f-113">`true`, um vorhandene Daten zu überschreiben, `false`, wenn vorhandene Daten nicht überschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2263f-113">`true` to overwrite existing data; `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="2263f-114">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="2263f-114">Property Value/Return Value</span></span>  
 <span data-ttu-id="2263f-115">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="2263f-115">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2263f-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2263f-116">Remarks</span></span>  
  
