---
title: 'SetWindowsServiceIdentity-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
api_name:
- SetWindowsServiceIdentity (WMI MSReportServer_ConfigurationSetting Class)
api_location:
- reportingservices.mof
topic_type:
- apiref
helpviewer_keywords:
- SetWindowsServiceIdentity method
ms.assetid: 9bbc734c-9e69-48c2-8bec-8abe7c6cc987
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 15d1b7fa5fc6d69a963785cdaf976c80623c47f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722353"
---
# <a name="setwindowsserviceidentity-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="a94f6-102">SetWindowsServiceIdentity-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="a94f6-102">SetWindowsServiceIdentity Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="a94f6-103">Lässt den Report Server-Windows-Dienst als einen angegebenen Windows-Benutzer ausführen und gibt diesem Konto die erforderlichen Dateisystemberechtigungen, damit der Berichtsserver ausgeführt werden kann</span><span class="sxs-lookup"><span data-stu-id="a94f6-103">Makes the Report Server Windows service run as a specified Windows user, and grants this account sufficient file system permissions to allow the report server to operate.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a94f6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="a94f6-104">Syntax</span></span>  
  
```vb  
Public Sub SetWindowsServiceIdentity(UseBuiltInAccount as Boolean, _  
    Account as String, Password as String, ByRef HRESULT as Int32)  
```  
  
```csharp  
public void SetWindowsServiceIdentity(boolean UseBuiltInAccount,   
    string Account, string Password, out Int32 HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a94f6-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="a94f6-105">Parameters</span></span>  
 <span data-ttu-id="a94f6-106">*UseBuiltInAccount*</span><span class="sxs-lookup"><span data-stu-id="a94f6-106">*UseBuiltInAccount*</span></span>  
 <span data-ttu-id="a94f6-107">Gibt an, ob das angegebene Konto ein integriertes Windows-Konto ist</span><span class="sxs-lookup"><span data-stu-id="a94f6-107">Indicates whether the specified account is a built-in Windows account.</span></span>  
  
 <span data-ttu-id="a94f6-108">*Konto*</span><span class="sxs-lookup"><span data-stu-id="a94f6-108">*Account*</span></span>  
 <span data-ttu-id="a94f6-109">Das Windows-Konto, das verwendet werden soll, um den Windows-Dienst auszuführen (im Format "DOMAIN\alias")</span><span class="sxs-lookup"><span data-stu-id="a94f6-109">The Windows account to use to run the Windows service, in the format "DOMAIN\alias".</span></span>  
  
 <span data-ttu-id="a94f6-110">*Kennwort*</span><span class="sxs-lookup"><span data-stu-id="a94f6-110">*Password*</span></span>  
 <span data-ttu-id="a94f6-111">Das Kennwort für das Konto</span><span class="sxs-lookup"><span data-stu-id="a94f6-111">The password for the account.</span></span>  
  
 <span data-ttu-id="a94f6-112">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="a94f6-112">*HRESULT*</span></span>  
 <span data-ttu-id="a94f6-113">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="a94f6-113">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a94f6-114">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="a94f6-114">Return Value</span></span>  
 <span data-ttu-id="a94f6-115">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="a94f6-115">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="a94f6-116">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="a94f6-116">A value of 0 indicates that the method call was successful.</span></span> <span data-ttu-id="a94f6-117">Ein Wert ungleich 0 (null) gibt an, dass ein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="a94f6-117">A non-zero value indicates that an error has occurred.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a94f6-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="a94f6-118">Remarks</span></span>  
 <span data-ttu-id="a94f6-119">Wenn der *UseBuiltInAccount* -Parameter auf festgelegt ist `true` und der Berichts Server unter Microsoft [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)] oder Windows XP ausgeführt wird, werden der Wert der Parameter *Name*, *Domäne*und *Kennwort* ignoriert, und das lokale Systemkonto wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="a94f6-119">When the *UseBuiltInAccount* parameter is set to `true` and the report server is running on Microsoft [!INCLUDE[win2kfamily](../../includes/win2kfamily-md.md)] or Windows XP, the value of the *Name*, *Domain*, and *Password* parameters are ignored and the Local system account is used.</span></span>  
  
 <span data-ttu-id="a94f6-120">Wenn der *UseBuiltInAccount* -Parameter auf festgelegt ist `true` und der Berichts Server unter Windows Server 2003 ausgeführt wird, werden die *Domänen* -und Kenn *Wort* Eigenschaften ignoriert, und das Namensfeld muss entweder "Builtin\NetworkService", "Builtin\System" oder "Builtin\LocalService" enthalten.</span><span class="sxs-lookup"><span data-stu-id="a94f6-120">When the *UseBuiltInAccount* parameter is set to `true` and the report server is running on Windows Server 2003, the *Domain* and *Password* properties are ignored, and the name field must contain either "Builtin\NetworkService" or "Builtin\System" or "Builtin\LocalService".</span></span>  
  
 <span data-ttu-id="a94f6-121">Die SetWindowsServiceIdentity-Methode legt Dateiberechtigungen für Dateien und Ordner im Installationsverzeichnis des Berichtsservers fest.</span><span class="sxs-lookup"><span data-stu-id="a94f6-121">The SetWindowsServiceIdentity method sets file permissions on files and folders in the report server installation directory.</span></span>  
  
 <span data-ttu-id="a94f6-122">Das im *Account* -Parameter angegebene Konto erfordert `LogonAsService` Rechte in Windows.</span><span class="sxs-lookup"><span data-stu-id="a94f6-122">The account specified in the *Account* parameter requires `LogonAsService` rights in Windows.</span></span> <span data-ttu-id="a94f6-123">Die Methode gewährt dem angegebenen Konto dieses Recht.</span><span class="sxs-lookup"><span data-stu-id="a94f6-123">The method grants this right to the specified account.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a94f6-124">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="a94f6-124">Requirements</span></span>  
 <span data-ttu-id="a94f6-125">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a94f6-125">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a94f6-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a94f6-126">See Also</span></span>  
 [<span data-ttu-id="a94f6-127">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="a94f6-127">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
