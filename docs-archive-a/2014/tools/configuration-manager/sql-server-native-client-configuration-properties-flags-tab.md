---
title: SQL Server Native Client-Konfigurationseigenschaften (Registerkarte „Flags“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: 59af121d-c8b9-4faa-91a1-b664f2c9b441
author: stevestein
ms.author: sstein
ms.openlocfilehash: b3ca7b87963fc3848bbb933a5c21f9d608d37d18
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621752"
---
# <a name="sql-server-native-client-configuration-properties-flags-tab"></a><span data-ttu-id="89ce2-102">SQL Server Native Client-Konfigurationseigenschaften (Registerkarte Flags)</span><span class="sxs-lookup"><span data-stu-id="89ce2-102">SQL Server Native Client Configuration Properties (Flags Tab)</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="89ce2-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Clients auf diesem Computer kommunizieren mithilfe der Protokolle der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-Bibliotheksdatei mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Servern.</span><span class="sxs-lookup"><span data-stu-id="89ce2-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] clients on this machine, communicate with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] servers using the protocols provided in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client library file.</span></span> <span data-ttu-id="89ce2-104">Mithilfe dieser Seite wird der Clientcomputer so konfiguriert, dass die Anforderung einer verschlüsselten Verbindung mit Secure Sockets Layer (SSL) möglich ist.</span><span class="sxs-lookup"><span data-stu-id="89ce2-104">This page provides configures the client computer to request an encrypted connection using Secure Sockets Layer (SSL).</span></span> <span data-ttu-id="89ce2-105">Wenn keine verschlüsselte Verbindung hergestellt werden kann, führt dies zu einem Verbindungsfehler.</span><span class="sxs-lookup"><span data-stu-id="89ce2-105">If an encrypted connection cannot be established, the connection will fail.</span></span>  
  
 <span data-ttu-id="89ce2-106">Der Anmeldeprozess ist immer verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="89ce2-106">The login process is always encrypted.</span></span> <span data-ttu-id="89ce2-107">Die unten genannten Optionen gelten nur für verschlüsselte Daten.</span><span class="sxs-lookup"><span data-stu-id="89ce2-107">The options below apply only to encrypting data.</span></span> <span data-ttu-id="89ce2-108">Weitere Informationen zur Verschlüsselungsart der Kommunikation von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] und zu Konfigurationsanweisungen für den Client, damit dieser die Stammzertifizierungsstelle des Serverzertifikats als vertrauenswürdig einstuft, finden Sie unter „Verschlüsseln von Verbindungen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]“ und „Gewusst wie: Aktivieren von Verschlüsselungsverbindungen für [!INCLUDE[ssDE](../../includes/ssde-md.md)] ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Konfigurations-Manager)“ in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Onlinedokumentation.</span><span class="sxs-lookup"><span data-stu-id="89ce2-108">For more information about how [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] encrypts communication and for instructions on how to configure the client to trust the root authority of the server certificate, see "Encrypting Connections to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]" and "How to: Enable Encrypted Connections to the [!INCLUDE[ssDE](../../includes/ssde-md.md)] ([!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Configuration Manager)" in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Books Online.</span></span>  
  
## <a name="options"></a><span data-ttu-id="89ce2-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="89ce2-109">Options</span></span>  
 <span data-ttu-id="89ce2-110">**ForceEncryption**</span><span class="sxs-lookup"><span data-stu-id="89ce2-110">**Force protocol encryption**</span></span>  
 <span data-ttu-id="89ce2-111">Fordern Sie eine Verbindung über SSL an.</span><span class="sxs-lookup"><span data-stu-id="89ce2-111">Request a connection using SSL.</span></span>  
  
 <span data-ttu-id="89ce2-112">**TrustServerCertificate**</span><span class="sxs-lookup"><span data-stu-id="89ce2-112">**Trust Server Certificate**</span></span>  
 <span data-ttu-id="89ce2-113">Wenn diese Option auf **Nein**festgelegt ist, versucht der Clientprozess, das Serverzertifikat zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="89ce2-113">When set to **No**, the client process attempts to validate the server certificate.</span></span> <span data-ttu-id="89ce2-114">Client und Server müssen jeweils über ein Zertifikat von einer öffentlichen Zertifizierungsstelle verfügen.</span><span class="sxs-lookup"><span data-stu-id="89ce2-114">The client and server must have each have a certificate issues from a public certification authority.</span></span> <span data-ttu-id="89ce2-115">Wenn dieses Zertifikat auf dem Clientcomputer nicht vorhanden ist oder bei der Überprüfung des Zertifikats ein Fehler erzeugt wird, wird die Verbindung beendet.</span><span class="sxs-lookup"><span data-stu-id="89ce2-115">If the certificate is not present on the client computer, or if the validation of the certificate fails, the connection is terminated.</span></span>  
  
 <span data-ttu-id="89ce2-116">Wenn diese Option auf **Ja**festgelegt ist, überprüft der Client das Serverzertifikat nicht. Dadurch wird die Verwendung eines selbstsignierten Zertifikats ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="89ce2-116">When set to **Yes**, the client does not validate the server certificate, thereby enabling the use of a self-signed certificate.</span></span>  
  
 <span data-ttu-id="89ce2-117">Das**TrustServerCertificate** -Flag ist nur verfügbar, wenn das **ForceEncryption** -Flag auf **Ja**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="89ce2-117">**Trust Server Certificate** is only available if **Force protocol encryption** is set to **Yes**.</span></span>  
  
  
