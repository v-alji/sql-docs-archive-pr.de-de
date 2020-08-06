---
title: SetDefaults-Methode (SInstance-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetDefaults Method (SInstance Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetDefaults method
ms.assetid: dc3c6a85-0711-4688-bf4f-91168c57af28
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: c581834d3c97bed622d16fbb35e48704f8679531
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696590"
---
# <a name="setdefaults-method-sinstance-class"></a><span data-ttu-id="8bc84-102">SetDefaults-Methode (SInstance-Klasse)</span><span class="sxs-lookup"><span data-stu-id="8bc84-102">SetDefaults Method (SInstance Class)</span></span>
  <span data-ttu-id="8bc84-103">Legt alle Standardwerte für die Instanz von fest [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , wobei die Option zum Überschreiben vorhandener Daten vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8bc84-103">Sets all the default values for the instance of [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] with the option to overwrite existing data.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bc84-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="8bc84-104">Syntax</span></span>  
  
```  
  
object  
.SetDefaults(  
OverwriteAll  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="8bc84-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="8bc84-105">Parts</span></span>  
 <span data-ttu-id="8bc84-106">*object*</span><span class="sxs-lookup"><span data-stu-id="8bc84-106">*object*</span></span>  
 <span data-ttu-id="8bc84-107">Ein [SInstance-Klassenobjekt](sinstance-class.md) , das eine Serverinstanz darstellt.</span><span class="sxs-lookup"><span data-stu-id="8bc84-107">An [SInstance Class](sinstance-class.md) object that represents a server instance.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="8bc84-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="8bc84-108">Parameters</span></span>  
  
|<span data-ttu-id="8bc84-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="8bc84-109">Parameter</span></span>|<span data-ttu-id="8bc84-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8bc84-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="8bc84-111">*Overschreiteall*</span><span class="sxs-lookup"><span data-stu-id="8bc84-111">*OverwriteAll*</span></span>|<span data-ttu-id="8bc84-112">Ein boleescher Wert, der angibt, ob vorhandene Werte in der Instanz des [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Clients überschreiben werden sollen: `true`, wenn vorhandene Daten überschrieben werden, bzw. `false`, wenn vorhandene Daten nicht überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="8bc84-112">A Boolean value that specifies whether to overwrite existing value on the instance of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] client: `true` if existing data is overwritten, or `false` if existing data is not overwritten.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="8bc84-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="8bc84-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="8bc84-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="8bc84-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bc84-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8bc84-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bc84-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8bc84-116">See Also</span></span>  
 <span data-ttu-id="8bc84-117">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="8bc84-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
