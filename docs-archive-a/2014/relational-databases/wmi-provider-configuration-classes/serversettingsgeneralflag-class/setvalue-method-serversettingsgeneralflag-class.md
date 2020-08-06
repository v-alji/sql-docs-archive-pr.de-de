---
title: SetValue-Methode (ServerSettingsGeneralFlag-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetValue Method (ServerSettingsGeneralFlag Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetValue method
ms.assetid: a889feac-c0e0-4635-b506-843863d86967
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 74c4c189b72b7a469794e0828faf062a88cdf46f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726809"
---
# <a name="setvalue-method-serversettingsgeneralflag-class"></a><span data-ttu-id="058ba-102">SetValue-Methode (ServerSettingsGeneralFlag-Klasse)</span><span class="sxs-lookup"><span data-stu-id="058ba-102">SetValue Method (ServerSettingsGeneralFlag Class)</span></span>
  <span data-ttu-id="058ba-103">Legt alle Werte des Flags fest, auf das verwiesen wird.</span><span class="sxs-lookup"><span data-stu-id="058ba-103">Sets all the values of the referenced flag.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="058ba-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="058ba-104">Syntax</span></span>  
  
```  
  
object  
.SetValue(  
Value  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="058ba-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="058ba-105">Parts</span></span>  
 <span data-ttu-id="058ba-106">*object*</span><span class="sxs-lookup"><span data-stu-id="058ba-106">*object*</span></span>  
 <span data-ttu-id="058ba-107">Ein [ServerSettingsGeneralFlag-Klassenobjekt](serversettingsgeneralflag-class.md) , das ein allgemeines Flag für die Servereinstellungen darstellt.</span><span class="sxs-lookup"><span data-stu-id="058ba-107">A [ServerSettingsGeneralFlag Class](serversettingsgeneralflag-class.md) object that represents a general flag for the server settings.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="058ba-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="058ba-108">Parameters</span></span>  
  
|<span data-ttu-id="058ba-109">Parameter</span><span class="sxs-lookup"><span data-stu-id="058ba-109">Parameter</span></span>|<span data-ttu-id="058ba-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="058ba-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="058ba-111">*Wert*</span><span class="sxs-lookup"><span data-stu-id="058ba-111">*Value*</span></span>|<span data-ttu-id="058ba-112">Ein boleescher Wert, der den Wert des Flags angibt.</span><span class="sxs-lookup"><span data-stu-id="058ba-112">A Boolean value that specifies the value of the flag.</span></span>|  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="058ba-113">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="058ba-113">Property Value/Return Value</span></span>  
 <span data-ttu-id="058ba-114">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird; jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="058ba-114">A `uint32` value, which is 0 if the service was successfully modified, 1 if the request is not supported, and any other number to indicate an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="058ba-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="058ba-115">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="058ba-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="058ba-116">See Also</span></span>  
 <span data-ttu-id="058ba-117">[Konfigurieren von Servernetzwerkprotokollen und Netzwerkbibliotheken](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span><span class="sxs-lookup"><span data-stu-id="058ba-117">[Configuring Server Network Protocols and Net-Libraries](https://msdn.microsoft.com/library/ms177485\(v=sql.100\).aspx)</span></span>  
  
  
