---
title: Protokolldateien für Standardablaufverfolgung deaktiviert | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: c27761e6-75ed-4ee4-a236-0cbc42e500a1
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0fed8fb006427b4dda9d99c57cbabca8538efcad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616005"
---
# <a name="default-trace-log-files-disabled"></a><span data-ttu-id="e2ed3-102">Protokolldateien für Standardablaufverfolgung deaktiviert</span><span class="sxs-lookup"><span data-stu-id="e2ed3-102">Default Trace Log Files Disabled</span></span>
  <span data-ttu-id="e2ed3-103">Diese Regel überprüft den Wert der Option Standardablaufverfolgung aktiviert der gespeicherten Prozedur sp_configure, um festzustellen, ob die Standardablaufverfolgung auf ON (1) oder OFF (0) festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e2ed3-103">This rule checks the value of the sp_configure stored procedure default trace enabled option to determine whether default trace is set ON (1) or OFF (0).</span></span> <span data-ttu-id="e2ed3-104">Wenn diese Option aktiviert ist, stellt die Standardablaufverfolgung Informationen über Konfigurations- und DDL-Änderungen an [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)]bereit.</span><span class="sxs-lookup"><span data-stu-id="e2ed3-104">When this option is enabled, default tracing provides information about configuration and DDL changes to the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="e2ed3-105">In manchen Fällen sind diese Informationen für Kunden sowie den Kundendienst- und Support von [!INCLUDE[msCoName](../../includes/msconame-md.md)] bei der Behebung von Fehlern bei [!INCLUDE[ssDE](../../includes/ssde-md.md)]hilfreich.</span><span class="sxs-lookup"><span data-stu-id="e2ed3-105">In some cases, this information can be helpful for customers and [!INCLUDE[msCoName](../../includes/msconame-md.md)] Customer Service and Support when they troubleshooting issues with the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="e2ed3-106">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="e2ed3-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="e2ed3-107">Aktivieren Sie die Ablaufverfolgung mit der gespeicherten Prozedur sp_configure, indem Sie den Wert von "Standardablaufverfolgung aktiviert" auf 1 festlegen.</span><span class="sxs-lookup"><span data-stu-id="e2ed3-107">Use the sp_configure stored procedure to enable tracing by setting the value of default trace enabled to 1.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="e2ed3-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2ed3-108">For More Information</span></span>  
 [<span data-ttu-id="e2ed3-109">Serverkonfigurationsoptionen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="e2ed3-109">Server Configuration Options &#40;SQL Server&#41;</span></span>](../../database-engine/configure-windows/server-configuration-options-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="e2ed3-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e2ed3-110">See Also</span></span>  
 [<span data-ttu-id="e2ed3-111">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="e2ed3-111">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
