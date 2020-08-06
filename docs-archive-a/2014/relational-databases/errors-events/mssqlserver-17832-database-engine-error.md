---
title: MSSQLSERVER_17832 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/29/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- 17828 (Database Engine error)
- maxtokensize
- 17832 (Database Engine error)
- login packet (bad)
ms.assetid: bd56ffe4-0855-4ada-8aca-251fbc6ff2ce
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: dba214e2cce04ff2583e12ae7cee9b54373390a6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696902"
---
# <a name="mssqlserver_17832"></a><span data-ttu-id="7ba26-102">MSSQLSERVER_17832</span><span class="sxs-lookup"><span data-stu-id="7ba26-102">MSSQLSERVER_17832</span></span>
    
## <a name="details"></a><span data-ttu-id="7ba26-103">Details</span><span class="sxs-lookup"><span data-stu-id="7ba26-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="7ba26-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="7ba26-104">Product Name</span></span>|[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]|  
|<span data-ttu-id="7ba26-105">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="7ba26-105">Event ID</span></span>|<span data-ttu-id="7ba26-106">17832</span><span class="sxs-lookup"><span data-stu-id="7ba26-106">17832</span></span>|  
|<span data-ttu-id="7ba26-107">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="7ba26-107">Event Source</span></span>|<span data-ttu-id="7ba26-108">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="7ba26-108">MSSQLSERVER</span></span>|  
|<span data-ttu-id="7ba26-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="7ba26-109">Component</span></span>|<span data-ttu-id="7ba26-110">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="7ba26-110">SQLEngine</span></span>|  
|<span data-ttu-id="7ba26-111">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="7ba26-111">Symbolic Name</span></span>|<span data-ttu-id="7ba26-112">SRV_BAD_LOGIN_PKT</span><span class="sxs-lookup"><span data-stu-id="7ba26-112">SRV_BAD_LOGIN_PKT</span></span>|  
|<span data-ttu-id="7ba26-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="7ba26-113">Message Text</span></span>|<span data-ttu-id="7ba26-114">Das zum Öffnen der Verbindung verwendete Anmeldungspaket weist eine ungültige Struktur auf. Die Verbindung wurde geschlossen.</span><span class="sxs-lookup"><span data-stu-id="7ba26-114">The login packet used to open the connection is structurally invalid; the connection has been closed.</span></span> <span data-ttu-id="7ba26-115">Wenden Sie sich an den Hersteller der Clientbibliothek.%\*ls</span><span class="sxs-lookup"><span data-stu-id="7ba26-115">Please contact the vendor of the client library.%.\*ls</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="7ba26-116">Erklärung</span><span class="sxs-lookup"><span data-stu-id="7ba26-116">Explanation</span></span>  
 <span data-ttu-id="7ba26-117">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Computer konnte das Clientanmeldepaket nicht verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="7ba26-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer was unable to process the client login packet.</span></span> <span data-ttu-id="7ba26-118">Das liegt möglicherweise daran, dass das Paket nicht ordnungsgemäß erstellt wurde oder dass das Paket während der Übertragung beschädigt wurde.</span><span class="sxs-lookup"><span data-stu-id="7ba26-118">This may be because the packet was created improperly or because the packet was damaged during transmission.</span></span> <span data-ttu-id="7ba26-119">Es kann auch durch die Konfiguration des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Computers verursacht werden.</span><span class="sxs-lookup"><span data-stu-id="7ba26-119">It can also be caused by the configuration of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="7ba26-120">Die aufgeführte IP-Adresse ist die Adresse des Clientcomputers.</span><span class="sxs-lookup"><span data-stu-id="7ba26-120">The IP address listed is the address of the client computer.</span></span>  
  
### <a name="more-information"></a><span data-ttu-id="7ba26-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7ba26-121">More Information</span></span>  
 <span data-ttu-id="7ba26-122">Bei der Verwendung der Windows-Authentifizierung in einer Kerberos-Umgebung empfängt der Client ein Kerberos-Ticket, das ein Zertifikat mit Berechtigungsattributen (Privilege Attribute Certificate, PAC) enthält.</span><span class="sxs-lookup"><span data-stu-id="7ba26-122">When using Windows Authentication in a Kerberos environment, a client receives a Kerberos ticket that contains a Privilege Attribute Certificate (PAC).</span></span> <span data-ttu-id="7ba26-123">Das PAC enthält verschiedene Typen von Autorisierungsdaten einschließlich Gruppen, in denen der Benutzer Mitglied ist, Rechte, über die der Benutzer verfügt, und welche Richtlinien für den Benutzer gelten.</span><span class="sxs-lookup"><span data-stu-id="7ba26-123">The PAC contains various types of authorization data including groups that the user is a member of, rights the user has, and what policies apply to the user.</span></span> <span data-ttu-id="7ba26-124">Wenn der Client das Kerberos-Ticket empfängt, werden die in dem PAC enthaltenen Informationen verwendet, um das Zugriffstoken des Benutzers zu generieren.</span><span class="sxs-lookup"><span data-stu-id="7ba26-124">When the client receives the Kerberos ticket, the information contained in the PAC is used to generate the user's access token.</span></span> <span data-ttu-id="7ba26-125">Der Client stellt das Token für den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Computer als Teil des Anmeldungspakets bereit.</span><span class="sxs-lookup"><span data-stu-id="7ba26-125">The client presents the token to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] computer as part of the login packet.</span></span>  
  
 <span data-ttu-id="7ba26-126">Wenn das Token nicht ordnungsgemäß erstellt wurde oder während der Übertragung beschädigt wurde, kann [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] keine weiteren Informationen über das Problem anbieten.</span><span class="sxs-lookup"><span data-stu-id="7ba26-126">If the token was improperly created or damaged during transmission, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot offer additional information about the problem.</span></span>  
  
 <span data-ttu-id="7ba26-127">Wenn der Benutzer Mitglied zahlreicher Gruppen ist oder über zahlreiche Richtlinien verfügt, kann das Token bei ihrer Auflistung größer als üblich werden.</span><span class="sxs-lookup"><span data-stu-id="7ba26-127">When the user is a member of many groups or has many policies, the token may grow larger than normal to list them all.</span></span> <span data-ttu-id="7ba26-128">Wenn das Token größer als der **MaxTokenSize**-Wert des Servercomputers wird, schlägt die Herstellung einer Verbindung durch den Client mit einem allgemeinen Netzwerkfehler (General Network Error, GNE) fehl, und es kann Fehler 17832 auftreten.</span><span class="sxs-lookup"><span data-stu-id="7ba26-128">If the token grows larger than the **MaxTokenSize** value of the server computer, the client fails to connect with a General Network Error (GNE) and error 17832 can occur.</span></span> <span data-ttu-id="7ba26-129">Dieses Problem beeinflusst möglicherweise nur einige Benutzer: Benutzer mit vielen Gruppen oder Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="7ba26-129">This problem may affect only some users: users with many groups or policies.</span></span> <span data-ttu-id="7ba26-130">Wenn das Problem in dem **MaxTokenSize**-Wert des Servercomputers besteht, wird Fehler 17832 im [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Fehlerprotokoll von einem Fehler mit dem Status 9 begleitet.</span><span class="sxs-lookup"><span data-stu-id="7ba26-130">When the problem is the **MaxTokenSize** value of the server computer, error 17832 in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log will be accompanied by an error with state 9.</span></span> <span data-ttu-id="7ba26-131">Weitere Einzelheiten zu Kerberos und **MaxTokenSize** finden Sie unter [KB327825](https://support.microsoft.com/kb/327825).</span><span class="sxs-lookup"><span data-stu-id="7ba26-131">For additional details about the Kerberos and **MaxTokenSize**, see [KB327825](https://support.microsoft.com/kb/327825).</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="7ba26-132">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="7ba26-132">User Action</span></span>  
 <span data-ttu-id="7ba26-133">Um dieses Problem zu beheben, erhöhen Sie den **MaxTokenSize**-Wert des Servercomputers so weit, dass er das größte Token aller Benutzer in der Organisation enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="7ba26-133">To resolve this problem, increase the **MaxTokenSize** value of the server computer, to a size large enough to contain the largest token of any user in your organization.</span></span> <span data-ttu-id="7ba26-134">Um die richtige Tokengröße für die Organisation zu ermitteln, ziehen Sie die Verwendung der Anwendung **Tokensz** in Erwägung.</span><span class="sxs-lookup"><span data-stu-id="7ba26-134">To research the correct token size for your organization, consider using the **Tokensz** application.</span></span>   
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
 <span data-ttu-id="7ba26-135">**So ändern Sie die maxtekensize auf dem Server Computer**</span><span class="sxs-lookup"><span data-stu-id="7ba26-135">**To change the MaxTokenSize  on the server computer**</span></span>  
  
1.  <span data-ttu-id="7ba26-136">Klicken Sie im Menü **Start** auf **Ausführen**.</span><span class="sxs-lookup"><span data-stu-id="7ba26-136">On the **Start** menu, click **Run**.</span></span>  
  
2.  <span data-ttu-id="7ba26-137">Geben `regedit` Sie ein, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="7ba26-137">Type `regedit`, and then click **OK**.</span></span> <span data-ttu-id="7ba26-138">(Wenn das Dialogfeld **Benutzerkontensteuerung** angezeigt wird, klicken Sie auf **Weiter**.)</span><span class="sxs-lookup"><span data-stu-id="7ba26-138">(If the **User Account Control** dialog box appears, click **Continue**.)</span></span>  
  
3.  <span data-ttu-id="7ba26-139">Navigieren Sie zu **HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Lsa\Kerberos\Parameters**.</span><span class="sxs-lookup"><span data-stu-id="7ba26-139">Navigate to **HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\Lsa\Kerberos\Parameters**.</span></span>  
  
4.  <span data-ttu-id="7ba26-140">Wenn der **MaxTokenSize**-Parameter nicht vorhanden ist, klicken Sie mit der rechten Maustaste auf **Parameter**, zeigen Sie auf **Neu**, und klicken Sie anschließend auf **DWORD (32-Bit)** -Wert.</span><span class="sxs-lookup"><span data-stu-id="7ba26-140">If the **MaxTokenSize** parameter is not present, right-click **Parameters**, point to **New**, and then click **DWORD (32-bit)** Value.</span></span> <span data-ttu-id="7ba26-141">Geben Sie dem Registrierungseintrag die Bezeichnung **MaxTokenSize**.</span><span class="sxs-lookup"><span data-stu-id="7ba26-141">Name the registry entry **MaxTokenSize**.</span></span>  
  
5.  <span data-ttu-id="7ba26-142">Klicken Sie mit der rechten Maustaste auf **MaxTokenSize**, und klicken Sie anschließend auf **Ändern**.</span><span class="sxs-lookup"><span data-stu-id="7ba26-142">Right-click **MaxTokenSize**, and then click **Modify**.</span></span>  
  
6.  <span data-ttu-id="7ba26-143">Geben Sie im Feld **Wertdaten** den gewünschten **MaxTokenSize**-Wert an.</span><span class="sxs-lookup"><span data-stu-id="7ba26-143">In the **Value data** box type the desired **MaxTokenSize** value.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7ba26-144">Der Hexadezimalwert ffff (Dezimalwert 65535) ist die maximale empfohlene Tokengröße.</span><span class="sxs-lookup"><span data-stu-id="7ba26-144">Hexadecimal value ffff (decimal value 65535) is the maximum recommended token size.</span></span> <span data-ttu-id="7ba26-145">Durch die Bereitstellung dieses Werts würde das Problem wahrscheinlich gelöst, dies könnte sich jedoch hinsichtlich der Leistung negativ auf den gesamten Computer auswirken.</span><span class="sxs-lookup"><span data-stu-id="7ba26-145">Providing this value would probably solve the problem, but could have negative computer-wide effects with regard to performance.</span></span> <span data-ttu-id="7ba26-146">Es wird empfohlen, dass Sie den Mindest-**MaxTokenSize**-Wert festlegen, der das größte Token aller Benutzer in der Organisation zulässt, und dass Sie diesen Wert eingeben.</span><span class="sxs-lookup"><span data-stu-id="7ba26-146">We recommend that you establish the minimum **MaxTokenSize** value that allows for the largest token of any user in your organization and enter that value.</span></span>  
  
7.  [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
8.  <span data-ttu-id="7ba26-147">Schließen Sie den **Registrierungs-Editor**.</span><span class="sxs-lookup"><span data-stu-id="7ba26-147">Close **Registry Editor**.</span></span>  
  
9. <span data-ttu-id="7ba26-148">Starten Sie den Computer neu.</span><span class="sxs-lookup"><span data-stu-id="7ba26-148">Restart the computer.</span></span>  
  
  
