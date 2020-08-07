---
title: Herstellen einer Verbindung mit SQL Server über einen Proxy Server (SQL Server-Konfigurations-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/22/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
helpviewer_keywords:
- Remote WinSock
- RWS
- LATs
- proxy servers [SQL Server]
- connections [SQL Server], proxy server
- Microsoft Proxy Server [SQL Server]
- local address tables [SQL Server]
ms.assetid: 39714de0-2a1f-4179-9091-5c3fa4612545
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: de22ad6043c509f08471a6bea40c0efa18d76842
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619326"
---
# <a name="connect-to-sql-server-through-a-proxy-server-sql-server-configuration-manager"></a><span data-ttu-id="d6a53-102">Verbindungsaufbau mit SQL Server über einen Proxyserver (SQL Server-Konfigurations-Manager)</span><span class="sxs-lookup"><span data-stu-id="d6a53-102">Connect to SQL Server Through a Proxy Server (SQL Server Configuration Manager)</span></span>
  <span data-ttu-id="d6a53-103">In diesem Thema wird beschrieben, wie Sie über einen Proxyserver in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mithilfe des SQL Server-Konfigurations-Managers eine Verbindung zu SQL Server herstellen.</span><span class="sxs-lookup"><span data-stu-id="d6a53-103">This topic describes how to connect to SQL Server through a proxy server in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using SQL Server Configuration Manager.</span></span> <span data-ttu-id="d6a53-104">Für die Remoteüberwachung über Remote WinSock (RWS) definieren Sie die lokale Adresstabelle (LAT, Local Address Table) für den Proxyserver so, dass sich die Überwachungsknotenadresse außerhalb des Bereichs der lokalen Adresstabelleneinträge befindet.</span><span class="sxs-lookup"><span data-stu-id="d6a53-104">To listen remotely by way of Remote WinSock (RWS), define the local address table (LAT) for the proxy server so that the listening node address is outside the range of LAT entries.</span></span>  
  
##  <a name="using-sql-server-configuration-manager"></a><a name="SSMSProcedure"></a> <span data-ttu-id="d6a53-105">Verwenden des SQL Server-Konfigurations-Managers</span><span class="sxs-lookup"><span data-stu-id="d6a53-105">Using SQL Server Configuration Manager</span></span>  
  
#### <a name="to-enable-connections-to-sql-server-through-microsoft-proxy-server"></a><span data-ttu-id="d6a53-106">So ermöglichen Sie Verbindungen mit SQL Server über Microsoft Proxy Server</span><span class="sxs-lookup"><span data-stu-id="d6a53-106">To enable connections to SQL Server through Microsoft Proxy Server</span></span>  
  
1.  <span data-ttu-id="d6a53-107">Führen Sie die Schritte in [Vorgehensweise: Konfigurieren eines Servers zur Überwachung eines bestimmten TCP-Ports &#40;SQL Server-Konfigurations-Manager&#41;](configure-a-server-to-listen-on-a-specific-tcp-port.md), um zu bestimmen, welche TCP/IP-Ports vom [!INCLUDE[ssDE](../../includes/ssde-md.md)] verwendet werden, oder um das [!INCLUDE[ssDE](../../includes/ssde-md.md)] zu konfigurieren, um einen gewünschten Port zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d6a53-107">Follow the steps in [Configure a Server to Listen on a Specific TCP Port &#40;SQL Server Configuration Manager&#41;](configure-a-server-to-listen-on-a-specific-tcp-port.md) to determine which TCP/IP ports are used by the [!INCLUDE[ssDE](../../includes/ssde-md.md)], or to configure the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to use a desired port.</span></span>  
  
2.  <span data-ttu-id="d6a53-108">Definieren Sie auf Ihrem Proxyserver die lokale Adresstabelle (LAT) für den Proxyserver so, dass sich die Überwachungsknotenadresse außerhalb des Bereichs der lokalen Adresstabelleneinträge befindet.</span><span class="sxs-lookup"><span data-stu-id="d6a53-108">In your proxy server define the local address table (LAT) for the proxy server so that the listening node address is outside the range of LAT entries.</span></span> <span data-ttu-id="d6a53-109">Weitere Informationen finden Sie in der Proxyserver-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="d6a53-109">For more information, see your proxy server documentation.</span></span>  
  
  
