---
title: 'CreateSSLCertificateBinding-Methode (WMI: MSReportServer_ConfigurationSetting) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- CreateSSLCertificateBinding
ms.assetid: 407d50e4-0a55-43cb-8ddf-2d82714071b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 8b9a5f9394d655f7b0592ea688a46f3ac2b9c153
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616929"
---
# <a name="createsslcertificatebinding-method-wmi-msreportserver_configurationsetting"></a><span data-ttu-id="f19a0-102">CreateSSLCertificateBinding-Methode (WMI: MSReportServer_ConfigurationSetting)</span><span class="sxs-lookup"><span data-stu-id="f19a0-102">CreateSSLCertificateBinding Method (WMI MSReportServer_ConfigurationSetting)</span></span>
  <span data-ttu-id="f19a0-103">Erstellt eine SSL-Zertifikatsbindung</span><span class="sxs-lookup"><span data-stu-id="f19a0-103">Creates an SSL Certificate binding.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f19a0-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="f19a0-104">Syntax</span></span>  
  
```vb  
Public Sub CreateSSLCertificateBinding(ByVal Application As String, _  
    ByVal CertificateHash As String, ByVal IPAddress As String, _  
    ByVal Port As Int32, ByVal lcid As Int32, _  
    ByRef [Error] As String, ByRef HRESULT As Int32)  
```  
  
```csharp  
public void CreateSSLCertificateBinding(string application,   
    string certificateHash, string IPAddress, int Port,   
    int lcid, out string error, out int HRESULT);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f19a0-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="f19a0-105">Parameters</span></span>  
 <span data-ttu-id="f19a0-106">*Anwendung*</span><span class="sxs-lookup"><span data-stu-id="f19a0-106">*Application*</span></span>  
 <span data-ttu-id="f19a0-107">Der Name der Anwendung, für die die Zertifikatsbindung erstellt werden soll</span><span class="sxs-lookup"><span data-stu-id="f19a0-107">The name of application that the certificate binding should be created for.</span></span>  
  
 <span data-ttu-id="f19a0-108">*CertificateHash*</span><span class="sxs-lookup"><span data-stu-id="f19a0-108">*CertificateHash*</span></span>  
 <span data-ttu-id="f19a0-109">Der Hash für das Zertifikat</span><span class="sxs-lookup"><span data-stu-id="f19a0-109">The hash for the certificate.</span></span>  
  
 <span data-ttu-id="f19a0-110">*IPAddress*</span><span class="sxs-lookup"><span data-stu-id="f19a0-110">*IPAddress*</span></span>  
 <span data-ttu-id="f19a0-111">Die IP-Adresse für die Anwendung</span><span class="sxs-lookup"><span data-stu-id="f19a0-111">The IP address for the application.</span></span>  
  
 <span data-ttu-id="f19a0-112">*Port*</span><span class="sxs-lookup"><span data-stu-id="f19a0-112">*Port*</span></span>  
 <span data-ttu-id="f19a0-113">Der SSL-Port, der der Bindung zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="f19a0-113">The SSL port associated with the binding.</span></span>  
  
 <span data-ttu-id="f19a0-114">*Lcid*</span><span class="sxs-lookup"><span data-stu-id="f19a0-114">*Lcid*</span></span>  
 <span data-ttu-id="f19a0-115">Das Gebietsschema, das für die zurückgegebenen Fehlermeldungen verwendet werden soll</span><span class="sxs-lookup"><span data-stu-id="f19a0-115">The locale to use for the error messages returned.</span></span>  
  
 <span data-ttu-id="f19a0-116">*Fehler*</span><span class="sxs-lookup"><span data-stu-id="f19a0-116">*Error*</span></span>  
 <span data-ttu-id="f19a0-117">[out] Die Beschreibung der Fehler, die aufgetreten sind</span><span class="sxs-lookup"><span data-stu-id="f19a0-117">[out] The description of the errors that occurred.</span></span>  
  
 <span data-ttu-id="f19a0-118">*HRESULT*</span><span class="sxs-lookup"><span data-stu-id="f19a0-118">*HRESULT*</span></span>  
 <span data-ttu-id="f19a0-119">[out] Wert, der angibt, ob der Aufruf erfolgreich war oder zu einem Fehler geführt hat.</span><span class="sxs-lookup"><span data-stu-id="f19a0-119">[out] Value indicating whether the call succeeded or failed.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f19a0-120">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="f19a0-120">Return Value</span></span>  
 <span data-ttu-id="f19a0-121">Gibt *HRESULT* zurück, wodurch der Erfolg oder das Fehlschlagen des Methodenaufrufs angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f19a0-121">Returns an *HRESULT* indicating success or failure of the method call.</span></span> <span data-ttu-id="f19a0-122">Der Wert 0 (null) gibt an, dass der Methodenaufruf erfolgreich war. Ein Fehlercode gibt an, dass der Aufruf nicht erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="f19a0-122">A value of 0 indicates that the method call was successful; an error code indicates the call was not successful.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f19a0-123">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f19a0-123">Remarks</span></span>  
 <span data-ttu-id="f19a0-124">Diese Methode fügt rsreportserver.config eine Bindung für die Anwendung hinzu.</span><span class="sxs-lookup"><span data-stu-id="f19a0-124">This method adds a binding to rsreportserver.config for the application.</span></span> <span data-ttu-id="f19a0-125">Wenn HTTP.SYS noch keine Bindung enthält, wird diese dort erstellt.</span><span class="sxs-lookup"><span data-stu-id="f19a0-125">If a binding does not already exist in HTTP.SYS, it is created there.</span></span>  
  
 <span data-ttu-id="f19a0-126">Vor dem Erstellen der Bindung untersucht der Methodenaufruf die URL-Reservierungen für die angegebene Anwendung, um zu überprüfen, ob die SSL-Zertifikatsbindung gültig ist.</span><span class="sxs-lookup"><span data-stu-id="f19a0-126">Before creating the binding, the method call examines the Url Reservations for the specified application to determine if the SSL Certificate Binding is valid.</span></span>  
  
 <span data-ttu-id="f19a0-127">Die folgenden Bedingungen werden überprüft und können Ursache für Fehler sein:</span><span class="sxs-lookup"><span data-stu-id="f19a0-127">The following conditions are validated and can result in errors:</span></span>  
  
1.  <span data-ttu-id="f19a0-128">Das Zertifikat ist nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f19a0-128">Certificate does not exist.</span></span>  
  
2.  <span data-ttu-id="f19a0-129">Die angegebene IPAddress entspricht keiner IPAddress dieses Computers.</span><span class="sxs-lookup"><span data-stu-id="f19a0-129">The IPAddress specified does not correspond to an IPAddress of this computer.</span></span>  
  
3.  <span data-ttu-id="f19a0-130">Die angegebene IP-Adresse ist eine DHCP-IP-Adresse (ändert sich in regelmäßigen Abständen). Verwenden Sie stattdessen die Platzhalter-IP-Adresse (0.0.0.0).</span><span class="sxs-lookup"><span data-stu-id="f19a0-130">The IPAddress specified is a DHCP IPAddress (changes periodically) - use the Wildcard IP address instead (0.0.0.0).</span></span>  
  
4.  <span data-ttu-id="f19a0-131">Die angegebene IP-Adresse entspricht weder der IP-Adresse für URL-Reservierungen noch ist eine Platzhalter- oder Hostnamen-URL-Reservierung vorhanden.</span><span class="sxs-lookup"><span data-stu-id="f19a0-131">IPAddress specified does not match the IP address of a URL reservations AND neither a wildcard or host name URL reservation exist.</span></span>  
  
5.  <span data-ttu-id="f19a0-132">Eine URL-Reservierung, die einen Hostnamen angibt, ist vorhanden, der Hostname stimmt jedoch nicht mit dem Zertifikathostnamen überein.</span><span class="sxs-lookup"><span data-stu-id="f19a0-132">A URL reservation that specifies a host name exists, but the host name does not match the certificate host name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f19a0-133">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="f19a0-133">Requirements</span></span>  
 <span data-ttu-id="f19a0-134">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f19a0-134">**Namespace:** [!INCLUDE[ssRSWMInmspcA](../../includes/ssrswminmspca-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f19a0-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f19a0-135">See Also</span></span>  
 [<span data-ttu-id="f19a0-136">MSReportServer_ConfigurationSetting Members (MSReportServer_ConfigurationSetting-Member)</span><span class="sxs-lookup"><span data-stu-id="f19a0-136">MSReportServer_ConfigurationSetting Members</span></span>](msreportserver-configurationsetting-members.md)  
  
  
