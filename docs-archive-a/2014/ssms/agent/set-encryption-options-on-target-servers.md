---
title: Festlegen von Verschlüsselungsoptionen auf Zielservern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Agent, encryption
- target servers [SQL Server], encryption
- multiserver environments [SQL Server], setting encryption options on target servers
ms.assetid: 1a9fd539-e166-4ea8-9f21-ac400ca74dee
author: stevestein
ms.author: sstein
ms.openlocfilehash: cd10d2e05e59015542f41cc123de993e6128f9f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621319"
---
# <a name="set-encryption-options-on-target-servers"></a><span data-ttu-id="d913b-102">Festlegen von Verschlüsselungsoptionen auf Zielservern</span><span class="sxs-lookup"><span data-stu-id="d913b-102">Set Encryption Options on Target Servers</span></span>
  <span data-ttu-id="d913b-103">Wenn Sie für die verschlüsselte SSL-Kommunikation (Secure Sockets Layer) zwischen Masterservern und einigen oder allen Zielservern kein Zertifikat verwenden können, aber den Kanal zwischen diesen verschlüsseln möchten, müssen Sie auf dem Zielserver die erforderliche Sicherheitsstufe konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d913b-103">If you cannot use a certificate for Secure Sockets Layer (SSL) encrypted communications between master servers and some or all of your target servers, but you want to encrypt the channel between them, configure the target server to use the level of security required.</span></span>  
  
 <span data-ttu-id="d913b-104">Legen Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Registrierungs Unterschlüssel **\ HKEY_LOCAL_MACHINE \software\microsoft\microsoft \\ SQL Server** \<*instance_name*> **\SQLServerAgent\MsxEncryptChannelOptions (REG_DWORD)** auf dem Zielserver auf einen der folgenden Werte fest, um die für einen bestimmten Kommunikationskanal zwischen einem Master-und einem Zielserver erforderliche Sicherheitsstufe zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d913b-104">To configure the appropriate level of security required for a specific master server/target server communication channel, set the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent registry subkey **\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Microsoft SQL Server\\**\<*instance_name*>**\SQLServerAgent\MsxEncryptChannelOptions(REG_DWORD)** on the target server to one of the following values.</span></span> <span data-ttu-id="d913b-105">Der Wert von \<*instance_name*> ist **MSSQL.** _n_.</span><span class="sxs-lookup"><span data-stu-id="d913b-105">The value of \<*instance_name*> is **MSSQL.**_n_.</span></span> <span data-ttu-id="d913b-106">Beispiel: **MSSQL.1** oder **MSSQL.3**.</span><span class="sxs-lookup"><span data-stu-id="d913b-106">For example, **MSSQL.1** or **MSSQL.3**.</span></span>  
  
|<span data-ttu-id="d913b-107">Wert</span><span class="sxs-lookup"><span data-stu-id="d913b-107">Value</span></span>|<span data-ttu-id="d913b-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d913b-108">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d913b-109">**0**</span><span class="sxs-lookup"><span data-stu-id="d913b-109">**0**</span></span>|<span data-ttu-id="d913b-110">Deaktiviert die Verschlüsselung zwischen diesem Zielserver und dem Masterserver.</span><span class="sxs-lookup"><span data-stu-id="d913b-110">Disables encryption between this target server and the master server.</span></span> <span data-ttu-id="d913b-111">Wählen Sie diese Option nur aus, wenn der Kanal zwischen Zielserver und Masterserver auf andere Weise gesichert ist.</span><span class="sxs-lookup"><span data-stu-id="d913b-111">Choose this option only when the channel between the target server and master server is secured by another means.</span></span>|  
|<span data-ttu-id="d913b-112">**1**</span><span class="sxs-lookup"><span data-stu-id="d913b-112">**1**</span></span>|<span data-ttu-id="d913b-113">Aktiviert nur die Verschlüsselung zwischen diesem Zielserver und dem Masterserver, eine Zertifikatüberprüfung ist jedoch nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d913b-113">Enables encryption only between this target server and the master server, but no certificate validation is required.</span></span>|  
|<span data-ttu-id="d913b-114">**2**</span><span class="sxs-lookup"><span data-stu-id="d913b-114">**2**</span></span>|<span data-ttu-id="d913b-115">Aktiviert die vollständige SSL-Verschlüsselung und Zertifikatüberprüfung zwischen diesem Zielserver und dem Masterserver.</span><span class="sxs-lookup"><span data-stu-id="d913b-115">Enables full SSL encryption and certificate validation between this target server and the master server.</span></span> <span data-ttu-id="d913b-116">Dies ist die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="d913b-116">This setting is the default.</span></span> <span data-ttu-id="d913b-117">Es wird empfohlen, diesen Wert nicht zu ändern, es sei denn, dafür liegen spezifische Gründe vor.</span><span class="sxs-lookup"><span data-stu-id="d913b-117">Unless you have specific reason to choose a different value, we recommend not changing it.</span></span>|  
  
 <span data-ttu-id="d913b-118">Wenn **1** oder **2** angegeben wird, muss SSL sowohl auf dem Master- als auch auf dem Zielserver aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="d913b-118">If **1** or **2** is specified, you must have SSL enabled on both the master and target servers.</span></span> <span data-ttu-id="d913b-119">Wenn **2** angegeben wird, muss außerdem auf dem Masterserver ein ordnungsgemäß signiertes Zertifikat vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="d913b-119">If **2** is specified, you must also have a properly signed certificate present on the master server.</span></span>  
  
> [!CAUTION]  
>  [!INCLUDE[ssNoteRegistry](../../includes/ssnoteregistry-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d913b-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d913b-120">See Also</span></span>  
 [<span data-ttu-id="d913b-121">Aktivieren von verschlüsselten Verbindungen zur Datenbank-Engine &#40;SQL Server-Konfigurations-Manager&#41;</span><span class="sxs-lookup"><span data-stu-id="d913b-121">Enable Encrypted Connections to the Database Engine &#40;SQL Server Configuration Manager&#41;</span></span>](../../database-engine/configure-windows/enable-encrypted-connections-to-the-database-engine.md)  
  
  
