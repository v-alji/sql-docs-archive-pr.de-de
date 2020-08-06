---
title: Replikation über das Internet | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- Web publishing [SQL Server replication], about Web publishing
- Web publishing [SQL Server replication]
- Internet [SQL Server replication]
- Internet [SQL Server replication], publishing
ms.assetid: 04e7f4ed-e244-4bbe-ba12-09c33abea09e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 46c61f8a5383c87d46fa0dbda18876b43ffb7739
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608527"
---
# <a name="replication-over-the-internet"></a><span data-ttu-id="9f628-102">Replikation über das Internet</span><span class="sxs-lookup"><span data-stu-id="9f628-102">Replication over the Internet</span></span>
  <span data-ttu-id="9f628-103">Das Replizieren von Daten über das Internet ermöglicht Remotebenutzern sowie Benutzern, die nicht mit dem Netzwerk verbunden sind, bei Bedarf auf Daten mithilfe einer Verbindung zum Internet zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9f628-103">Replicating data over the Internet allows remote, disconnected users to access data when they need it using a connection to the Internet.</span></span> <span data-ttu-id="9f628-104">Verwenden Sie Folgendes, um Daten über das Internet zu replizieren:</span><span class="sxs-lookup"><span data-stu-id="9f628-104">Replicate data over the Internet using:</span></span>  
  
-   <span data-ttu-id="9f628-105">Ein Virtuelles Privates Netzwerk (VPN).</span><span class="sxs-lookup"><span data-stu-id="9f628-105">A Virtual Private Network (VPN).</span></span> <span data-ttu-id="9f628-106">Weitere Informationen finden Sie unter [Veröffentlichen von Daten über das Internet mithilfe von VPN](publish-data-over-the-internet-using-vpn.md).</span><span class="sxs-lookup"><span data-stu-id="9f628-106">For more information, see [Publish Data over the Internet Using VPN](publish-data-over-the-internet-using-vpn.md).</span></span>  
  
-   <span data-ttu-id="9f628-107">Die Websynchronisierungsoption für die Mergereplikation.</span><span class="sxs-lookup"><span data-stu-id="9f628-107">The Web synchronization option for merge replication.</span></span> <span data-ttu-id="9f628-108">Weitere Informationen finden Sie unter [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span><span class="sxs-lookup"><span data-stu-id="9f628-108">For more information, see [Web Synchronization for Merge Replication](web-synchronization-for-merge-replication.md).</span></span>  
  
 <span data-ttu-id="9f628-109">Bei allen Arten der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Replikation können Daten über ein VPN repliziert werden. Falls Sie eine Mergereplikation verwenden, sollten Sie jedoch die Websynchronisierung in Betracht ziehen.</span><span class="sxs-lookup"><span data-stu-id="9f628-109">All types of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] replication can replicate data over a VPN, but you should consider Web synchronization if you are using merge replication.</span></span>  
  
  
