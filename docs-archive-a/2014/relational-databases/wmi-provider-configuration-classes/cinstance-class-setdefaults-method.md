---
title: SetDefaults-Methode (CInstance-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (CInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: ed9e99c2-3e28-4ee8-bc20-61ca05984973
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 5e589796f973592d7f9f549bffbbf8dfbe49cc27
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607583"
---
# <a name="setdefaults-method-cinstance-class"></a><span data-ttu-id="548eb-102">SetDefaults-Methode (CInstance-Klasse)</span><span class="sxs-lookup"><span data-stu-id="548eb-102">SetDefaults Method (CInstance Class)</span></span>
  <span data-ttu-id="548eb-103">Legt alle Standardwerte für die Instanz des- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Clients fest, wobei die Option zum Überschreiben vorhandener Daten besteht.</span><span class="sxs-lookup"><span data-stu-id="548eb-103">Sets all the default values for the instance of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="548eb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="548eb-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="548eb-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="548eb-105">Parts</span></span>  
 <span data-ttu-id="548eb-106">*object*</span><span class="sxs-lookup"><span data-stu-id="548eb-106">*object*</span></span>  
 <span data-ttu-id="548eb-107">Ein [CInstance-Klassenobjekt](cinstance-class.md) , das eine [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Clientinstanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="548eb-107">A [CInstance Class](cinstance-class.md) object that represents a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="548eb-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="548eb-108">Parameters</span></span>  
  
|<span data-ttu-id="548eb-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="548eb-109">Parameter</span></span>|<span data-ttu-id="548eb-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="548eb-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="548eb-111">*Overschreiteall*</span><span class="sxs-lookup"><span data-stu-id="548eb-111">*OverwriteAll*</span></span>|<span data-ttu-id="548eb-112">Ein boleescher Wert, der angibt, ob vorhandene Werte in der Instanz des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Clients überschreiben werden sollen: `true` zum Überschreiben bestehender Daten oder `false`, wenn vorhandene Daten nicht überschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="548eb-112">A Boolean value that specifies whether to overwrite existing values on the instance of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client: `true` to overwrite existing data, or `false` if existing data is not to be overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="548eb-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="548eb-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="548eb-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="548eb-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="548eb-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="548eb-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="548eb-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="548eb-116">See Also</span></span>  
 [<span data-ttu-id="548eb-117">Konfigurieren von Clientprotokollen</span><span class="sxs-lookup"><span data-stu-id="548eb-117">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
