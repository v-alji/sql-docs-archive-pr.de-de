---
title: SetValue-Methode (ClientSettingsGeneralFlag-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetValue Method (ClientSettingsGeneralFlag Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetValue method
ms.assetid: 34443689-a0e0-4668-a811-17532c6fd271
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: fffa44bd8743f96a43ca4d1787d8d2afaad5e6cc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696661"
---
# <a name="setvalue-method-clientsettingsgeneralflag-class"></a><span data-ttu-id="1ccef-102">SetValue-Methode (ClientSettingsGeneralFlag-Klasse)</span><span class="sxs-lookup"><span data-stu-id="1ccef-102">SetValue Method (ClientSettingsGeneralFlag Class)</span></span>
  <span data-ttu-id="1ccef-103">Legt alle Werte des Flags fest, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="1ccef-103">Sets all the values of the referenced flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ccef-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1ccef-104">Syntax</span></span>  
  
```  
  
object  
.SetValue(  
Value  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="1ccef-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="1ccef-105">Parts</span></span>  
 <span data-ttu-id="1ccef-106">*object*</span><span class="sxs-lookup"><span data-stu-id="1ccef-106">*object*</span></span>  
 <span data-ttu-id="1ccef-107">Ein Objekt der [ClientSettingsGeneralFlag-Klasse](clientsettingsgeneralflag-class.md) , das ein allgemeines Flag für die Servereinstellungen darstellt.</span><span class="sxs-lookup"><span data-stu-id="1ccef-107">A [ClientSettingsGeneralFlag Class](clientsettingsgeneralflag-class.md) object that represents a general flag for the server settings.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="1ccef-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ccef-108">Parameters</span></span>  
  
|<span data-ttu-id="1ccef-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="1ccef-109">Parameter</span></span>|<span data-ttu-id="1ccef-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1ccef-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1ccef-111">*Wert*</span><span class="sxs-lookup"><span data-stu-id="1ccef-111">*Value*</span></span>|<span data-ttu-id="1ccef-112">Ein boleescher Wert, der den Wert des Flags angibt.</span><span class="sxs-lookup"><span data-stu-id="1ccef-112">A Boolean value that specifies the value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1ccef-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1ccef-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="1ccef-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="1ccef-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ccef-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1ccef-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ccef-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ccef-116">See Also</span></span>  
 [<span data-ttu-id="1ccef-117">Konfigurieren von Clientprotokollen</span><span class="sxs-lookup"><span data-stu-id="1ccef-117">Configure Client Protocols</span></span>](https://technet.microsoft.com/library/ms181035.aspx)  
  
  
