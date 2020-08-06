---
title: Remoteadministratorverbindungen (Serverkonfigurationsoption) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- administrator connections [SQL Server]
- DAC
- connections [SQL Server], dedicated administrator
- remote admin connections option
- dedicated administrator connections [SQL Server]
ms.assetid: bf32b60a-7a48-401f-b6be-b5e2e46c413f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c17cf278d18444c5b93d4f4b7e0a3da8dbfb671e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621174"
---
# <a name="remote-admin-connections-server-configuration-option"></a><span data-ttu-id="1802f-102">Remoteadministratorverbindungen (Serverkonfigurationsoption)</span><span class="sxs-lookup"><span data-stu-id="1802f-102">remote admin connections Server Configuration Option</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="1802f-103">stellt eine dedizierte Administratorverbindung (Dedicated Administrator Connection, DAC) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1802f-103">provides a dedicated administrator connection (DAC).</span></span> <span data-ttu-id="1802f-104">Mit der DAC kann ein Administrator auf einen laufenden Server zugreifen, um Diagnosefunktionen oder [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisungen auszuführen oder um Probleme auf dem Server zu behandeln, selbst wenn der Server gesperrt ist oder nicht in einem normalen Status ausgeführt wird und nicht auf eine [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] -Verbindung antwortet.</span><span class="sxs-lookup"><span data-stu-id="1802f-104">The DAC lets an administrator access a running server to execute diagnostic functions or [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, or to troubleshoot problems on the server, even when the server is locked or running in an abnormal state and not responding to a [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] connection.</span></span> <span data-ttu-id="1802f-105">Standardmäßig ist die DAC nur von einem Client auf dem Server verfügbar.</span><span class="sxs-lookup"><span data-stu-id="1802f-105">By default, the DAC is only available from a client on the server.</span></span> <span data-ttu-id="1802f-106">Verwenden Sie die Option remote admin connections von sp_configure, um zuzulassen, dass Clientanwendungen auf Remotecomputern die DAC verwenden.</span><span class="sxs-lookup"><span data-stu-id="1802f-106">To enable client applications on remote computers to use the DAC, use the remote admin connections option of sp_configure.</span></span>  
  
 <span data-ttu-id="1802f-107">Standardmäßig lauscht die DAC nur an der Loopback-IP-Adresse (127.0.0.1), Port 1434.</span><span class="sxs-lookup"><span data-stu-id="1802f-107">By default, the DAC only listens on the loop-back IP address (127.0.0.1), port 1434.</span></span> <span data-ttu-id="1802f-108">Ist der TCP-Port 1434 nicht verfügbar, wird ein TCP-Port dynamisch zugewiesen, wenn [!INCLUDE[ssDE](../../includes/ssde-md.md)] startet.</span><span class="sxs-lookup"><span data-stu-id="1802f-108">If TCP port 1434 is not available, a TCP port is dynamically assigned when the [!INCLUDE[ssDE](../../includes/ssde-md.md)] starts up.</span></span> <span data-ttu-id="1802f-109">Wenn mehr als eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf einem Computer installiert ist, müssen Sie das Fehlerprotokoll auf die TCP-Portnummer überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1802f-109">When more than one instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is installed on a computer, check the error log for the TCP port number.</span></span>  
  
 <span data-ttu-id="1802f-110">In der folgenden Tabelle sind die möglichen Werte für die Option remote admin connections aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="1802f-110">The following table lists the possible values for the remote admin connections option.</span></span>  
  
|<span data-ttu-id="1802f-111">Wert</span><span class="sxs-lookup"><span data-stu-id="1802f-111">Value</span></span>|<span data-ttu-id="1802f-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1802f-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="1802f-113">0</span><span class="sxs-lookup"><span data-stu-id="1802f-113">0</span></span>|<span data-ttu-id="1802f-114">Nur lokale Verbindungen sind mit der DAC zulässig.</span><span class="sxs-lookup"><span data-stu-id="1802f-114">Indicates only local connections are allowed by using the DAC.</span></span>|  
|<span data-ttu-id="1802f-115">1</span><span class="sxs-lookup"><span data-stu-id="1802f-115">1</span></span>|<span data-ttu-id="1802f-116">Remoteverbindungen sind mit der DAC zulässig.</span><span class="sxs-lookup"><span data-stu-id="1802f-116">Indicates remote connections are allowed by using the DAC.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1802f-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1802f-117">Example</span></span>  
 <span data-ttu-id="1802f-118">Im folgenden Beispiel wird die DAC von einem Remotecomputer aus aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1802f-118">The following example enables the DAC from a remote computer.</span></span>  
  
```  
sp_configure 'remote admin connections', 1;  
GO  
RECONFIGURE;  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="1802f-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1802f-119">See Also</span></span>  
 [<span data-ttu-id="1802f-120">Diagnoseverbindung für Datenbankadministratoren</span><span class="sxs-lookup"><span data-stu-id="1802f-120">Diagnostic Connection for Database Administrators</span></span>](diagnostic-connection-for-database-administrators.md)  
  
  
