---
title: Führen Sie die Schritte nach der Installation aus. Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 0a788a2a-9b4f-4bfc-b1b5-83eeb1ea9ab2
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1e9aae3dccaa409bcebc473213286f3edf19e7f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618956"
---
# <a name="complete-the-post-installation-steps"></a><span data-ttu-id="5a75f-102">Ausführen der Schritte nach der Installation</span><span class="sxs-lookup"><span data-stu-id="5a75f-102">Complete the Post-Installation Steps</span></span>
  <span data-ttu-id="5a75f-103">Nach der Installation von Distributed Replay müssen Sie die Distributed Replay Controller und -Client-Dienstkonten ändern.</span><span class="sxs-lookup"><span data-stu-id="5a75f-103">After you install Distributed Replay you must modify the Distributed Replay controller and client services accounts.</span></span>  
  
### <a name="to-complete-the-post-installation-steps"></a><span data-ttu-id="5a75f-104">So führen Sie die Schritte nach der Installation aus</span><span class="sxs-lookup"><span data-stu-id="5a75f-104">To complete the post-installation steps</span></span>  
  
1.  <span data-ttu-id="5a75f-105">**Erstellen von Firewallregeln:** Auf den Controller- und Clientcomputern müssen Sie für den entsprechenden Dienst den eingehenden Datenverkehr durch die Firewall zulassen.</span><span class="sxs-lookup"><span data-stu-id="5a75f-105">**Create firewall rules**: On the controller and client computers, you must allow inbound traffic through the firewall for the corresponding service.</span></span> <span data-ttu-id="5a75f-106">Geben Sie die Firewallregeln für die ausführbaren Dienstdateien an, die sich in den Installationsordnern befinden.</span><span class="sxs-lookup"><span data-stu-id="5a75f-106">Specify the firewall rules for the service executables, located in the installation folders.</span></span>  
  
    1.  <span data-ttu-id="5a75f-107">Erstellen Sie für den Controllerdienst eine Regel für **DReplayController.exe**. Diese Datei befindet sich im Installationsordner.</span><span class="sxs-lookup"><span data-stu-id="5a75f-107">For the controller service, create a rule for **DReplayController.exe**, located in the installation folder.</span></span> <span data-ttu-id="5a75f-108">Mit dem folgenden Befehl aktivieren Sie beispielsweise diese Regel, wobei `%InstallPath%` den Installationsordner des Diensts darstellt:</span><span class="sxs-lookup"><span data-stu-id="5a75f-108">For example, the following command enables this rule, where `%InstallPath%` is the installation folder of the service:</span></span>  
  
         `netsh advfirewall firewall add rule name="allow dreplay controller" dir=in program="%InstallPath%\DReplayController\DReplayController.exe" action=allow`  
  
    2.  <span data-ttu-id="5a75f-109">Erstellen Sie für den Clientdienst auf jedem Clientcomputer eine Regel für **DReplayClient.exe**. Diese Datei befindet sich im Installationsordner.</span><span class="sxs-lookup"><span data-stu-id="5a75f-109">For the client service, on each client computer, create a rule for **DReplayClient.exe**, located in the installation folder.</span></span> <span data-ttu-id="5a75f-110">Mit dem folgenden Befehl aktivieren Sie beispielsweise diese Regel, wobei `%InstallPath%` den Installationsordner des Diensts darstellt:</span><span class="sxs-lookup"><span data-stu-id="5a75f-110">For example, the following command enables this rule, where `%InstallPath%` is the installation folder of the service:</span></span>  
  
         `netsh advfirewall firewall add rule name="allow dreplay client" dir=in program="%InstallPath%\DReplayClient\DReplayClient.exe" action=allow`  
  
2.  <span data-ttu-id="5a75f-111">**Jedem Client Berechtigungen für den Zielserver erteilen:** Wenn Sie die Installation des Clientdiensts auf den Clientcomputern abgeschlossen haben, müssen Sie der sysadmin-Rolle für die Zielinstanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] manuell die Clientdienstkonten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5a75f-111">**Grant each client permissions on the target server**: After you have completed installing the client service on the client computers, you must manually add the client service accounts to the sysadmin role on the target instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="5a75f-112">.NET Framework-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="5a75f-112">.NET Framework Security</span></span>  
 <span data-ttu-id="5a75f-113">Sie müssen über Administratorberechtigungen verfügen, um eine der Distributed Replay-Funktionen zu installieren.</span><span class="sxs-lookup"><span data-stu-id="5a75f-113">You must have administrative permissions in order to install any of the Distributed Replay features.</span></span> <span data-ttu-id="5a75f-114">Nur bei einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Anmeldung mit sysadmin-Berechtigungen können der sysadmin-Serverrolle des Testservers die Clientdienstkonten hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="5a75f-114">Only a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login having sysadmin permissions can add the client service accounts to the sysadmin server role of the test server.</span></span> <span data-ttu-id="5a75f-115">Weitere Informationen zu Sicherheitsüberlegungen für Distributed Replay finden Sie unter [Distributed Replay Security](distributed-replay-security.md).</span><span class="sxs-lookup"><span data-stu-id="5a75f-115">For more information about Distributed Replay security considerations, see [Distributed Replay Security](distributed-replay-security.md).</span></span>  
  
  
