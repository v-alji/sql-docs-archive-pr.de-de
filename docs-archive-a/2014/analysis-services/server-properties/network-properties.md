---
title: Netzwerk Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- LingerTimeout property
- EnableNagleAlgorithm property
- MinPendingAcceptExCount property
- MaxPendingSendCount property
- EnableBinaryXML property
- MinPendingReceiveCount property
- MaxCompletedReceiveCount property
- DisableNonblockingMode property
- RequestSizeThreshold property
- CompressionLevel property
- ReceiveBufferSize property
- EnableCompression property
- ServerSendTimeout property
- IPV4Support property
- MaxPendingReceiveCount property
- MaxPendingAcceptExCount property
- IPV6Support property
- MaxAllowedRequestSize property
- ServerReceiveTimeout property
- EnableLingerOnClose property
- InitialConnectTimeout property
- SendBufferSize property
- ScatterReceiveMultiplier property
- network properties [Analysis Services]
ms.assetid: ef4251e2-abe5-4c5b-9868-7549782d0244
author: minewiskan
ms.author: owend
ms.openlocfilehash: 10ad5bbbcffdfc3d3c4fefe3111e4c4425919915
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617308"
---
# <a name="network-properties"></a><span data-ttu-id="e4525-102">Netzwerkeigenschaften</span><span class="sxs-lookup"><span data-stu-id="e4525-102">Network Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="e4525-103">unterstützt die in den folgenden Tabellen aufgeführten Servereigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e4525-103">supports the server properties listed in the following tables.</span></span> <span data-ttu-id="e4525-104">Weitere Informationen zu zusätzlichen Servereigenschaften und zum Festlegen dieser Eigenschaften finden Sie unter [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="e4525-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
 <span data-ttu-id="e4525-105">**Gilt für:** mehrdimensionalen und Tabellenservermodus</span><span class="sxs-lookup"><span data-stu-id="e4525-105">**Applies to:** Multidimensional and Tabular server mode</span></span>  
  
## <a name="general"></a><span data-ttu-id="e4525-106">Allgemein</span><span class="sxs-lookup"><span data-stu-id="e4525-106">General</span></span>  
 `ListenOnlyOnLocalConnections`  
 <span data-ttu-id="e4525-107">Eine boolesche Eigenschaft, die anzeigt, ob nur lokale Verbindungen, z. B. localhost, überwacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e4525-107">A Boolean property that identifies whether to listen only on local connections, for example localhost.</span></span>  
  
## <a name="listener"></a><span data-ttu-id="e4525-108">Listener</span><span class="sxs-lookup"><span data-stu-id="e4525-108">Listener</span></span>  
 `IPV4Support`  
 <span data-ttu-id="e4525-109">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die Unterstützung für das IPv4-Protokoll definiert.</span><span class="sxs-lookup"><span data-stu-id="e4525-109">A signed 32-bit integer property that defines support for IPv4 protocol.</span></span> <span data-ttu-id="e4525-110">Diese Eigenschaft hat einen der in der folgenden Tabelle aufgeführten Werte:</span><span class="sxs-lookup"><span data-stu-id="e4525-110">This property has one of the values listed in the following table:</span></span>  
  
|<span data-ttu-id="e4525-111">Wert</span><span class="sxs-lookup"><span data-stu-id="e4525-111">Value</span></span>|<span data-ttu-id="e4525-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e4525-112">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4525-113">*0*</span><span class="sxs-lookup"><span data-stu-id="e4525-113">*0*</span></span>|<span data-ttu-id="e4525-114">IPv4 ist deaktiviert; Clients können keine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="e4525-114">IPv4 disabled; clients can't connect.</span></span>|  
|<span data-ttu-id="e4525-115">*1*</span><span class="sxs-lookup"><span data-stu-id="e4525-115">*1*</span></span>|<span data-ttu-id="e4525-116">(Standard) IPv4 ist erforderlich; Server startet nicht, wenn eine Überwachung von IPv4 nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="e4525-116">(Default) IPv4 is required; server won't start if it cannot listen to IPv4.</span></span>|  
|<span data-ttu-id="e4525-117">*2*</span><span class="sxs-lookup"><span data-stu-id="e4525-117">*2*</span></span>|<span data-ttu-id="e4525-118">IPv4 ist optional; Server versucht, IPv4 zu überwachen, startet aber auch, wenn dies nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="e4525-118">IPv4 is optional; server tries to listen to IPv4 but starts even if unable to.</span></span>|  
  
 `IPV6Support`  
 <span data-ttu-id="e4525-119">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die Unterstützung für das IPv6-Protokoll definiert.</span><span class="sxs-lookup"><span data-stu-id="e4525-119">A signed 32-bit integer property that defines support for IPv6 protocol.</span></span> <span data-ttu-id="e4525-120">Diese Eigenschaft hat einen der in der folgenden Tabelle aufgeführten Werte:</span><span class="sxs-lookup"><span data-stu-id="e4525-120">This property has one of the values listed in the following table:</span></span>  
  
|<span data-ttu-id="e4525-121">Wert</span><span class="sxs-lookup"><span data-stu-id="e4525-121">Value</span></span>|<span data-ttu-id="e4525-122">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e4525-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e4525-123">*0*</span><span class="sxs-lookup"><span data-stu-id="e4525-123">*0*</span></span>|<span data-ttu-id="e4525-124">IPv6 ist deaktiviert; Clients können keine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="e4525-124">IPv6 disabled; clients can't connect.</span></span>|  
|<span data-ttu-id="e4525-125">*1*</span><span class="sxs-lookup"><span data-stu-id="e4525-125">*1*</span></span>|<span data-ttu-id="e4525-126">(Standard) IPv6 ist erforderlich; Server startet nicht, wenn eine Überwachung von IPv6 nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="e4525-126">(Default) IPv6 is required; server won't start if it cannot listen to IPv6.</span></span>|  
|<span data-ttu-id="e4525-127">*2*</span><span class="sxs-lookup"><span data-stu-id="e4525-127">*2*</span></span>|<span data-ttu-id="e4525-128">IPv6 ist optional; Server versucht, IPv6 zu überwachen, startet aber auch, wenn dies nicht möglich ist.</span><span class="sxs-lookup"><span data-stu-id="e4525-128">IPv6 is optional; server tries to listen to IPv6 but starts even if unable to.</span></span>|  
  
 `MaxAllowedRequestSize`  
 <span data-ttu-id="e4525-129">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-129">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `RequestSizeThreshold`  
 <span data-ttu-id="e4525-130">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-130">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ServerReceiveTimeout`  
 <span data-ttu-id="e4525-131">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-131">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ServerSendTimeout`  
 <span data-ttu-id="e4525-132">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-132">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="requests"></a><span data-ttu-id="e4525-133">Requests</span><span class="sxs-lookup"><span data-stu-id="e4525-133">Requests</span></span>  
 `EnableBinaryXML`  
 <span data-ttu-id="e4525-134">Eine boolesche Eigenschaft, die angibt, ob der Server Anforderungen im Format Binary XML erkennt.</span><span class="sxs-lookup"><span data-stu-id="e4525-134">A Boolean property that specifies whether the server will recognize requests binary xml format.</span></span>  
  
 `EnableCompression`  
 <span data-ttu-id="e4525-135">Eine boolesche Eigenschaft, die angibt, ob für Anforderungen die Komprimierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e4525-135">A Boolean property that specifies whether compression is enabled for requests.</span></span>  
  
## <a name="responses"></a><span data-ttu-id="e4525-136">Antworten</span><span class="sxs-lookup"><span data-stu-id="e4525-136">Responses</span></span>  
 `CompressionLevel`  
 <span data-ttu-id="e4525-137">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-137">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `EnableBinaryXML`  
 <span data-ttu-id="e4525-138">Eine boolesche Eigenschaft, die angibt, ob der Server für Antworten im Format Binary XML aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e4525-138">A Boolean property that specifies whether the server is enabled for binary xml responses.</span></span>  
  
 `EnableCompression`  
 <span data-ttu-id="e4525-139">Eine boolesche Eigenschaft, die angibt, ob für Antworten auf Clientanforderungen die Komprimierung aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e4525-139">A Boolean property that specifies whether compression is enabled for responses to client requests.</span></span>  
  
## <a name="tcp"></a><span data-ttu-id="e4525-140">TCP</span><span class="sxs-lookup"><span data-stu-id="e4525-140">TCP</span></span>  
 `InitialConnectTimeout`  
 <span data-ttu-id="e4525-141">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-141">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxCompletedReceiveCount`  
 <span data-ttu-id="e4525-142">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-142">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingAcceptExCount`  
 <span data-ttu-id="e4525-143">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-143">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingReceiveCount`  
 <span data-ttu-id="e4525-144">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-144">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MaxPendingSendCount`  
 <span data-ttu-id="e4525-145">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-145">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinPendingAcceptExCount`  
 <span data-ttu-id="e4525-146">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-146">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MinPendingReceiveCount`  
 <span data-ttu-id="e4525-147">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-147">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `ScatterReceiveMultiplier`  
 <span data-ttu-id="e4525-148">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-148">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ DisableNonblockingMode`  
 <span data-ttu-id="e4525-149">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-149">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ EnableLingerOnClose`  
 <span data-ttu-id="e4525-150">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-150">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\EnableNagleAlgorithm`  
 <span data-ttu-id="e4525-151">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-151">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ LingerTimeout`  
 <span data-ttu-id="e4525-152">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-152">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ ReceiveBufferSize`  
 <span data-ttu-id="e4525-153">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-153">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `SocketOptions\ SendBufferSize`  
 <span data-ttu-id="e4525-154">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="e4525-154">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4525-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e4525-155">See Also</span></span>  
 <span data-ttu-id="e4525-156">[Konfigurieren von Server Eigenschaften in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="e4525-156">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="e4525-157">Bestimmen des Servermodus einer Analysis Services-Instanz</span><span class="sxs-lookup"><span data-stu-id="e4525-157">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
