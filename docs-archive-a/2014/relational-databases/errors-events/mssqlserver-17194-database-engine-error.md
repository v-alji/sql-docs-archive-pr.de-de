---
title: MSSQLSERVER_17194 | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- "17194"
helpviewer_keywords:
- 17194 (Database Engine error)
ms.assetid: 0d03eb20-28a7-4ceb-8903-7f9420a620f7
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d3f56a104841c4825bba1f60b3588fadd63555c6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617081"
---
# <a name="mssqlserver_17194"></a><span data-ttu-id="1fd3d-102">MSSQLSERVER_17194</span><span class="sxs-lookup"><span data-stu-id="1fd3d-102">MSSQLSERVER_17194</span></span>
    
## <a name="details"></a><span data-ttu-id="1fd3d-103">Details</span><span class="sxs-lookup"><span data-stu-id="1fd3d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="1fd3d-104">Produktname</span><span class="sxs-lookup"><span data-stu-id="1fd3d-104">Product Name</span></span>|<span data-ttu-id="1fd3d-105">SQL Server</span><span class="sxs-lookup"><span data-stu-id="1fd3d-105">SQL Server</span></span>|  
|<span data-ttu-id="1fd3d-106">Ereignis-ID</span><span class="sxs-lookup"><span data-stu-id="1fd3d-106">Event ID</span></span>|<span data-ttu-id="1fd3d-107">17194</span><span class="sxs-lookup"><span data-stu-id="1fd3d-107">17194</span></span>|  
|<span data-ttu-id="1fd3d-108">Ereignisquelle</span><span class="sxs-lookup"><span data-stu-id="1fd3d-108">Event Source</span></span>|<span data-ttu-id="1fd3d-109">MSSQLSERVER</span><span class="sxs-lookup"><span data-stu-id="1fd3d-109">MSSQLSERVER</span></span>|  
|<span data-ttu-id="1fd3d-110">Komponente</span><span class="sxs-lookup"><span data-stu-id="1fd3d-110">Component</span></span>|<span data-ttu-id="1fd3d-111">SQLEngine</span><span class="sxs-lookup"><span data-stu-id="1fd3d-111">SQLEngine</span></span>|  
|<span data-ttu-id="1fd3d-112">Symbolischer Name</span><span class="sxs-lookup"><span data-stu-id="1fd3d-112">Symbolic Name</span></span>||  
|<span data-ttu-id="1fd3d-113">Meldungstext</span><span class="sxs-lookup"><span data-stu-id="1fd3d-113">Message Text</span></span>|<span data-ttu-id="1fd3d-114">Der Server konnte die für das Anmelden erforderliche SSL-Anbieterbibliothek nicht laden. Die Verbindung wurde geschlossen.</span><span class="sxs-lookup"><span data-stu-id="1fd3d-114">The server was unable to load the SSL provider library needed to log in; the connection has been closed.</span></span> <span data-ttu-id="1fd3d-115">SSL wird zum Verschlüsseln der Anmeldesequenz oder der gesamten Kommunikation verwendet, je nach der vom Administrator festgelegten Serverkonfiguration.</span><span class="sxs-lookup"><span data-stu-id="1fd3d-115">SSL is used to encrypt either the login sequence or all communications, depending on how the administrator has configured the server.</span></span> <span data-ttu-id="1fd3d-116">Weitere Informationen zu dieser Fehlermeldung finden Sie in der Onlinedokumentation:  0xXXXX.</span><span class="sxs-lookup"><span data-stu-id="1fd3d-116">See Books Online for information on this error message:  0xXXXX.</span></span> <span data-ttu-id="1fd3d-117">[CLIENT: 11.11.11.11]</span><span class="sxs-lookup"><span data-stu-id="1fd3d-117">[CLIENT: 11.11.11.11]</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="1fd3d-118">Erklärung</span><span class="sxs-lookup"><span data-stu-id="1fd3d-118">Explanation</span></span>  
 <span data-ttu-id="1fd3d-119">Mit diesem Fehler wird angegeben, dass die Verbindung vom Client geschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="1fd3d-119">This error indicates that the client has closed the connection.</span></span> <span data-ttu-id="1fd3d-120">Dieser Fehler ist möglicherweise darauf zurückzuführen, dass das Verbindungstimeout abgelaufen ist.</span><span class="sxs-lookup"><span data-stu-id="1fd3d-120">This error could occur because the connection time-out has expired.</span></span> <span data-ttu-id="1fd3d-121">In der Fehlermeldung wird ein Wert des Betriebssystems angezeigt, mit dem das zugrunde liegende Problem beschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="1fd3d-121">The error message displays a value from the operating system that describes the underlying problem.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="1fd3d-122">Benutzeraktion</span><span class="sxs-lookup"><span data-stu-id="1fd3d-122">User Action</span></span>  
 <span data-ttu-id="1fd3d-123">Wenn der Fehlercode in der Meldung 0x2746 lautet (Dezimalwert 10054), bedeutet dies, dass die Verbindung durch den Client zurückgesetzt wurde. Dies ist normalerweise auf ein Timeout zurückzuführen. Wenn Sie den Fehler beheben möchten, erhöhen Sie das Verbindungstimeout für den Client bzw. das aufrufende Programm.</span><span class="sxs-lookup"><span data-stu-id="1fd3d-123">If the error code in the message is 0x2746 (decimal value 10054), this means that the connection was reset by the client, typically because of a time-out. To resolve the error, increase the connection time-out on the client or calling program.</span></span>  
  
 <span data-ttu-id="1fd3d-124">Verwenden Sie zum Bestimmen einer möglichen Lösung für weitere Fehlermeldungswerte den Betriebssystembefehl **net helpmsg**, und geben Sie den Dezimalwert des Fehlercodes an.</span><span class="sxs-lookup"><span data-stu-id="1fd3d-124">To determine a possible solution for other error message values, use the operating system command **net helpmsg** and specify the decimal value of the error code.</span></span>  
  
 <span data-ttu-id="1fd3d-125">Weitere Informationen zum Herstellen einer Verbindung mit einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] finden Sie unter [Server-Netzwerkkonfiguration](../../database-engine/configure-windows/server-network-configuration.md) und [Client-Netzwerkkonfiguration](../../database-engine/configure-windows/client-network-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="1fd3d-125">For more information about how to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Server Network Configuration](../../database-engine/configure-windows/server-network-configuration.md) and [Client Network Configuration](../../database-engine/configure-windows/client-network-configuration.md).</span></span>  
  
## <a name="internal-only"></a><span data-ttu-id="1fd3d-126">Nur intern</span><span class="sxs-lookup"><span data-stu-id="1fd3d-126">Internal-Only</span></span>  
  
