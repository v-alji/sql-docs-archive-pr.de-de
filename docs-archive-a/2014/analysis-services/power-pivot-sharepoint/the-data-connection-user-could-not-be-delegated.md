---
title: 'Die Datenverbindung verwendet die Windows-Authentifizierung, und Benutzeranmeldeinformationen konnten nicht delegiert werden. Die folgenden Verbindungen wurden nicht aktualisiert: Power Pivot-Daten | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: d2006df1-d244-4786-b272-49d8996cc88c
author: minewiskan
ms.author: owend
ms.openlocfilehash: be4c61ad4514f3aa4f6f1eda1fe44ad97c4c064f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616248"
---
# <a name="the-data-connection-uses-windows-authentication-and-user-credentials-could-not-be-delegated-the-following-connections-failed-to-refresh-powerpivot-data"></a><span data-ttu-id="15d86-103">Die Datenverbindung verwendet die Windows-Authentifizierung, und Benutzeranmeldeinformationen konnten nicht delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="15d86-103">The data connection uses Windows Authentication and user credentials could not be delegated.</span></span> <span data-ttu-id="15d86-104">Die folgenden Verbindungen wurden nicht aktualisiert: PowerPivot-Daten</span><span class="sxs-lookup"><span data-stu-id="15d86-104">The following connections failed to refresh: PowerPivot Data</span></span>
  <span data-ttu-id="15d86-105">Für Excel-Arbeitsmappen, die PowerPivot-Daten enthalten, gibt Excel Services diesen Fehler zurück, wenn keine Verbindung mit einer PowerPivot-Serverinstanz in SharePoint hergestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="15d86-105">For Excel workbooks that contain PowerPivot data, Excel Services returns this error if it cannot connect to a PowerPivot server instance in SharePoint.</span></span>  
  
## <a name="details"></a><span data-ttu-id="15d86-106">Details</span><span class="sxs-lookup"><span data-stu-id="15d86-106">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="15d86-107">Gilt für:</span><span class="sxs-lookup"><span data-stu-id="15d86-107">Applies to</span></span>|<span data-ttu-id="15d86-108">PowerPivot für SharePoint</span><span class="sxs-lookup"><span data-stu-id="15d86-108">PowerPivot for SharePoint</span></span>|  
|<span data-ttu-id="15d86-109">Produktversion</span><span class="sxs-lookup"><span data-stu-id="15d86-109">Product Version</span></span>|[!INCLUDE[ssKilimanjaro](../../includes/sskilimanjaro-md.md)]<span data-ttu-id="15d86-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15d86-110">, [!INCLUDE[ssSQL11](../../includes/sssql11-md.md)], [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]</span></span>|  
|<span data-ttu-id="15d86-111">Ursache</span><span class="sxs-lookup"><span data-stu-id="15d86-111">Cause</span></span>|<span data-ttu-id="15d86-112">Verbindungsfehler beim Versuch, einen PowerPivot-Datenanbieter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="15d86-112">Connection failed when attempting to use a PowerPivot data provider.</span></span>|  
|<span data-ttu-id="15d86-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="15d86-113">Message Text</span></span>|<span data-ttu-id="15d86-114">Die Datenverbindung verwendet die Windows-Authentifizierung, und Benutzeranmeldeinformationen konnten nicht delegiert werden.</span><span class="sxs-lookup"><span data-stu-id="15d86-114">The data connection uses Windows Authentication and user credentials could not be delegated.</span></span> <span data-ttu-id="15d86-115">Die folgenden Verbindungen wurden nicht aktualisiert: PowerPivot-Daten</span><span class="sxs-lookup"><span data-stu-id="15d86-115">The following connections failed to refresh: PowerPivot Data</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="15d86-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="15d86-116">Explanation</span></span>  
 <span data-ttu-id="15d86-117">Es gibt mehrere Ursachen für diese Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="15d86-117">There are multiple causes for this error message.</span></span> <span data-ttu-id="15d86-118">Alle haben gemeinsam, dass Excel Services keine gültige Windows-Benutzeridentität von einem Claims-Token in SharePoint abrufen können.</span><span class="sxs-lookup"><span data-stu-id="15d86-118">The common factor behind all of them is that Excel Services cannot get a valid Windows user identity from a claims token in SharePoint.</span></span> <span data-ttu-id="15d86-119">Bei Excel-Arbeitsmappen, die PowerPivot-Daten enthalten, tritt dieser Fehler auf, wenn eine der folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="15d86-119">In the case of Excel workbooks that contain PowerPivot data, this error occurs when any of the following conditions exist:</span></span>  
  
-   <span data-ttu-id="15d86-120">c2WTS (Claims to Windows Token Service) wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="15d86-120">The Claims to Windows Token Service is not running.</span></span> <span data-ttu-id="15d86-121">Sie können die Ursache dieses Fehlers überprüfen, indem Sie die SharePoint-Protokolldatei anzeigen.</span><span class="sxs-lookup"><span data-stu-id="15d86-121">You can confirm the cause of this error by viewing the SharePoint log file.</span></span> <span data-ttu-id="15d86-122">Wenn die SharePoint-Protokolle die Meldung enthalten, dass der Pipeendpunkt "net.pipe://localhost/s4u/022694f3-9fbd-422b-b4b2-312e25dae2a2" auf dem lokalen Computer nicht gefunden wurde, wird c2WTS (Claims to Windows Token Service) nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="15d86-122">If the SharePoint logs include the message "The pipe endpoint 'net.pipe://localhost/s4u/022694f3-9fbd-422b-b4b2-312e25dae2a2' could not be found on your local machine", the Claims to Windows Token Service is not running.</span></span> <span data-ttu-id="15d86-123">Um ihn zu starten, verwenden Sie die Zentraladministration und überprüfen dann, ob der Dienst in der Konsolenanwendung Dienste ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="15d86-123">To start it, use Central Administration and then verify the service is running in the Services console application.</span></span>  
  
-   <span data-ttu-id="15d86-124">Es ist kein Domänencontroller verfügbar, um die Benutzeridentität zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="15d86-124">A domain controller is not available to validate the user identity.</span></span> <span data-ttu-id="15d86-125">c2WTS (Claims to Windows Token Service) verwendet keine zwischengespeicherten Anmeldeinformationen.</span><span class="sxs-lookup"><span data-stu-id="15d86-125">The Claims to Windows Token Service does not use cached credentials.</span></span> <span data-ttu-id="15d86-126">Er überprüft die Benutzeridentität für jede Verbindung.</span><span class="sxs-lookup"><span data-stu-id="15d86-126">It validates the user identity for each connection.</span></span> <span data-ttu-id="15d86-127">Sie können die Ursache dieses Fehlers überprüfen, indem Sie die SharePoint-Protokolldatei anzeigen.</span><span class="sxs-lookup"><span data-stu-id="15d86-127">You can confirm the cause of this error by viewing the SharePoint log file.</span></span> <span data-ttu-id="15d86-128">Wenn die SharePoint-Protokolle die Meldung "Fehler beim Abrufen von WindowsIdentity aus IClaimsIdentity" enthalten, konnte die Benutzeridentität nicht authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="15d86-128">If the SharePoint logs include the message "Failed to get WindowsIdentity from IClaimsIdentity", the user identity could not be authenticated.</span></span>  
  
-   <span data-ttu-id="15d86-129">Die Computer müssen Mitglieder derselben Domäne oder mehrerer Domänen sein, die sich gegenseitig vertrauen.</span><span class="sxs-lookup"><span data-stu-id="15d86-129">The computers must be members of the same domain or in domains that have a two-way trust relationship.</span></span>  
  
-   <span data-ttu-id="15d86-130">Sie müssen Windows-Domänenbenutzerkonten verwenden.</span><span class="sxs-lookup"><span data-stu-id="15d86-130">You must use Windows domain user accounts.</span></span> <span data-ttu-id="15d86-131">Die Konten müssen über einen Universal Principal Name (UPN) verfügen.</span><span class="sxs-lookup"><span data-stu-id="15d86-131">The accounts must have a Universal Principal Name (UPN).</span></span>  
  
-   <span data-ttu-id="15d86-132">Das Excel Services-Dienstkonto muss über Active Directory-Berechtigungen zur Abfrage des Objekts verfügen.</span><span class="sxs-lookup"><span data-stu-id="15d86-132">The Excel Services service account must have Active Directory permissions to query the object.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="15d86-133">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="15d86-133">User Action</span></span>  
 <span data-ttu-id="15d86-134">Befolgen Sie die nachfolgenden Anweisungen, um den Status von c2WTS (Claims to Windows Token Service) zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="15d86-134">Use the following instructions to check the status of the Claims to Windows Token Service.</span></span>  
  
 <span data-ttu-id="15d86-135">Wenden Sie sich in allen anderen Fällen an den Netzwerkadministrator.</span><span class="sxs-lookup"><span data-stu-id="15d86-135">For all other scenarios, check with your network administrator.</span></span>  
  
#### <a name="enable-claims-to-windows-token-service"></a><span data-ttu-id="15d86-136">Aktivieren von c2WTS (Claims to Windows Token Service)</span><span class="sxs-lookup"><span data-stu-id="15d86-136">Enable Claims to Windows Token Service</span></span>  
  
1.  <span data-ttu-id="15d86-137">Klicken Sie in der Zentraladministration unter Systemeinstellungen auf **Dienste auf dem Server verwalten**.</span><span class="sxs-lookup"><span data-stu-id="15d86-137">In Central Administration, in System Settings, click **Manage services on server**.</span></span>  
  
2.  <span data-ttu-id="15d86-138">Wählen Sie **Claims to Windows Token Service**aus, und klicken Sie dann auf **Starten**.</span><span class="sxs-lookup"><span data-stu-id="15d86-138">Select **Claims to Windows Token Service**, and then click **Start**.</span></span>  
  
3.  <span data-ttu-id="15d86-139">Überprüfen Sie, ob der Dienst auch in der Konsole Dienste ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="15d86-139">Verify the service is also running in the Services console:</span></span>  
  
    1.  <span data-ttu-id="15d86-140">Klicken Sie unter Verwaltung auf Dienste.</span><span class="sxs-lookup"><span data-stu-id="15d86-140">In Administrative Tools, click Services.</span></span>  
  
    2.  <span data-ttu-id="15d86-141">Starten Sie c2WTS (Claims to Windows Token Service), falls er nicht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="15d86-141">Start the Claims to Windows Token Service if it is not running.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15d86-142">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="15d86-142">See Also</span></span>  
 [<span data-ttu-id="15d86-143">Konfigurieren von PowerPivot-Dienstkonten</span><span class="sxs-lookup"><span data-stu-id="15d86-143">Configure PowerPivot Service Accounts</span></span>](configure-power-pivot-service-accounts.md)  
  
  
