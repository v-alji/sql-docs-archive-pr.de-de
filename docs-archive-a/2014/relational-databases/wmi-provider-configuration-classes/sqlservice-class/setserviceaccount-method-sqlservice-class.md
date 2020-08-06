---
title: SetServiceAccount-Methode (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- SetServiceAccount Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- SetServiceAccount method
ms.assetid: d5782892-e9d8-4d48-92af-b3afe9610f84
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6087a531802a7752ea794a44147c79fb7c3fa3ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696553"
---
# <a name="setserviceaccount-method-sqlservice-class"></a><span data-ttu-id="1c4fb-102">SetServiceAccount-Methode (SqlService-Klasse)</span><span class="sxs-lookup"><span data-stu-id="1c4fb-102">SetServiceAccount Method (SqlService Class)</span></span>
  <span data-ttu-id="1c4fb-103">Versucht, den Benutzernamen und das Kennwort zu ändern, unter denen die Dienstinstanz ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1c4fb-103">Attempts to change the user name and password that the service instance runs under.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c4fb-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c4fb-104">Syntax</span></span>  
  
```  
  
object  
.SetServiceAccount(  
ServiceStartName , ServiceStartPassword  
)  
  
```  
  
## <a name="parts"></a><span data-ttu-id="1c4fb-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="1c4fb-105">Parts</span></span>  
 <span data-ttu-id="1c4fb-106">*object*</span><span class="sxs-lookup"><span data-stu-id="1c4fb-106">*object*</span></span>  
 <span data-ttu-id="1c4fb-107">Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="1c4fb-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
#### <a name="parameters"></a><span data-ttu-id="1c4fb-108">Parameter</span><span class="sxs-lookup"><span data-stu-id="1c4fb-108">Parameters</span></span>  
 <span data-ttu-id="1c4fb-109">*Servicestartname*</span><span class="sxs-lookup"><span data-stu-id="1c4fb-109">*ServiceStartName*</span></span>  
 <span data-ttu-id="1c4fb-110">Ein Zeichenfolgenwert, der den Kontonamen angibt, unter dem der Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1c4fb-110">A string value that specifies the account name that the service runs under.</span></span> <span data-ttu-id="1c4fb-111">Abhängig vom Diensttyp könnte der Kontoname die Form "DomainName\Username" aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1c4fb-111">Depending on the service type, the account name might be in the form of DomainName\Username.</span></span> <span data-ttu-id="1c4fb-112">Wenn er ausgeführt wird, wird der Dienstprozess in einer von zwei Formen protokolliert:</span><span class="sxs-lookup"><span data-stu-id="1c4fb-112">When it runs, the service process will be logged using one of two forms:</span></span>  
  
-   <span data-ttu-id="1c4fb-113">Wenn das Konto zur integrierten Domäne gehört, kann "\Username" angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="1c4fb-113">If the account belongs to the built-in domain, \Username can be specified.</span></span>  
  
-   <span data-ttu-id="1c4fb-114">Wenn NULL angegeben wird, wird der Dienst als **LocalSystem** -Konto angemeldet.</span><span class="sxs-lookup"><span data-stu-id="1c4fb-114">If NULL is specified, the service will be logged on as the **LocalSystem** account.</span></span>  
  
 <span data-ttu-id="1c4fb-115">Bei Kernel- oder Systemtreibern enthält *StartName* den Treiberobjektnamen, entweder "\FileSystem\Rdr" oder "\Driver\Xns", den das E/A-System zum Laden des Gerätetreibers verwendet.</span><span class="sxs-lookup"><span data-stu-id="1c4fb-115">For kernel or system-level drivers, *StartName* contains the driver object name, either \FileSystem\Rdr or \Driver\Xns, which the I/O system uses to load the device driver.</span></span> <span data-ttu-id="1c4fb-116">Bei Angabe von NULL wird der Treiber mit einem Standardobjektnamen ausgeführt, den das E/A-System auf Basis des Dienstnamens erstellt, zum Beispiel "DWDOM\Admin".</span><span class="sxs-lookup"><span data-stu-id="1c4fb-116">If NULL is specified, the driver runs with a default object name created by the I/O system based on the service name, for example, DWDOM\Admin.</span></span>  
  
 <span data-ttu-id="1c4fb-117">*Servicestartpassword*</span><span class="sxs-lookup"><span data-stu-id="1c4fb-117">*ServiceStartPassword*</span></span>  
 <span data-ttu-id="1c4fb-118">Ein Zeichenfolgenwert, der das Kennwort für den Kontonamen im *StartName* -Parameter angibt.</span><span class="sxs-lookup"><span data-stu-id="1c4fb-118">A string value that specifies the password for the account name in the *StartName* parameter.</span></span> <span data-ttu-id="1c4fb-119">Geben Sie NULL an, wenn Sie das Kennwort nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="1c4fb-119">Specify NULL if you are not changing the password.</span></span> <span data-ttu-id="1c4fb-120">Geben Sie eine leere Zeichenfolge an, wenn der Dienst kein Kennwort besitzt.</span><span class="sxs-lookup"><span data-stu-id="1c4fb-120">Specify an empty string if the service has no password.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="1c4fb-121">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="1c4fb-121">Property Value/Return Value</span></span>  
 <span data-ttu-id="1c4fb-122">Ein `uint32`-Wert, der 0 beträgt, wenn der Dienst erfolgreich geändert wurde. Der Wert beträgt 1, wenn die Anforderung nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="1c4fb-122">A `uint32` value, which is 0 if the service was successfully modified or 1 if the request is not supported.</span></span> <span data-ttu-id="1c4fb-123">Jede andere Zahl gibt einen Fehler an.</span><span class="sxs-lookup"><span data-stu-id="1c4fb-123">Any other number indicates an error.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1c4fb-124">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1c4fb-124">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c4fb-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1c4fb-125">See Also</span></span>  
 <span data-ttu-id="1c4fb-126">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="1c4fb-126">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
