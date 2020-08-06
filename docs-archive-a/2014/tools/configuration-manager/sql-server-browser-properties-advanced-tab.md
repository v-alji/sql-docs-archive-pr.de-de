---
title: Eigenschaften von SQL Server-Browser (Registerkarte „Erweitert“) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
ms.assetid: ba79137a-cb72-4bf3-a650-e11d02cfce10
author: stevestein
ms.author: sstein
ms.openlocfilehash: 480cd93c3feca44dd455a1a9ce2fd12994ca6100
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621289"
---
# <a name="sql-server-browser-properties-advanced-tab"></a><span data-ttu-id="fe4e0-102">Eigenschaften von SQL Server-Browser (Registerkarte Erweitert)</span><span class="sxs-lookup"><span data-stu-id="fe4e0-102">SQL Server Browser Properties (Advanced Tab)</span></span>
  <span data-ttu-id="fe4e0-103">Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Browser-Programm wird als Dienst auf dem Server ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fe4e0-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser program runs as a service on the server.</span></span> <span data-ttu-id="fe4e0-104">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Browser lauscht auf eingehende Anforderungen für [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ressourcen und stellt Informationen zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanzen zur Verfügung, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="fe4e0-104">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Browser listens for incoming requests for [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] resources and provides information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances installed on the computer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="fe4e0-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="fe4e0-105">Options</span></span>  
 <span data-ttu-id="fe4e0-106">**Gruppiert**</span><span class="sxs-lookup"><span data-stu-id="fe4e0-106">**Clustered**</span></span>  
 <span data-ttu-id="fe4e0-107">Zeigt an, ob dieser Dienst als Ressource eines gruppierten Servers installiert ist.</span><span class="sxs-lookup"><span data-stu-id="fe4e0-107">Indicates if this service is installed as a resource of a clustered server.</span></span>  
  
 <span data-ttu-id="fe4e0-108">**Berichterstellung für Kundenfeedback**</span><span class="sxs-lookup"><span data-stu-id="fe4e0-108">**Customer Feedback Reporting**</span></span>  
 <span data-ttu-id="fe4e0-109">Gibt an, ob Service Quality Monitoring für diesen Dienst aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="fe4e0-109">Indicates whether Service Quality Monitoring has been enabled on this service.</span></span> <span data-ttu-id="fe4e0-110">Weitere Informationen zu Berichterstellung für Kundenfeedback finden Sie in der Onlinedokumentation unter "Einstellungen für Fehler- und Verwendungsberichte".</span><span class="sxs-lookup"><span data-stu-id="fe4e0-110">For more information on Customer Feedback Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="fe4e0-111">**Speicherverzeichnis**</span><span class="sxs-lookup"><span data-stu-id="fe4e0-111">**Dump Directory**</span></span>  
 <span data-ttu-id="fe4e0-112">Der Speicherort, an dem Speicherabbilder im Falle eines Fehlers abgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="fe4e0-112">The location where memory dumps are placed in case of an error.</span></span>  
  
 <span data-ttu-id="fe4e0-113">**Fehlerberichterstellung**</span><span class="sxs-lookup"><span data-stu-id="fe4e0-113">**Error Reporting**</span></span>  
 <span data-ttu-id="fe4e0-114">Mit der Einstellung **Ja**werden vom Programm Dr. Watson Informationen an [!INCLUDE[msCoName](../../includes/msconame-md.md)] oder den Fehlerberichtsserver weitergeleitet, wenn ein schwerwiegender Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="fe4e0-114">When set to **Yes**, the Dr. Watson program forwards information to either [!INCLUDE[msCoName](../../includes/msconame-md.md)] or your error server if a serious failure occurs.</span></span> <span data-ttu-id="fe4e0-115">Weitere Informationen zur Fehlerberichterstellung finden Sie in der Onlinedokumentation unter "Einstellungen für Fehler- und Verwendungsberichte".</span><span class="sxs-lookup"><span data-stu-id="fe4e0-115">For more information on Error Reporting, search Books Online for the topic, "Error and Usage Report Settings."</span></span>  
  
 <span data-ttu-id="fe4e0-116">**Instanz-ID**</span><span class="sxs-lookup"><span data-stu-id="fe4e0-116">**Instance ID**</span></span>  
 <span data-ttu-id="fe4e0-117">Gibt die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] an, die diese [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Instanz verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="fe4e0-117">Indicates the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that used this [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent instance.</span></span> <span data-ttu-id="fe4e0-118">Die Standardinstanz ist **MSSQL10_50.MSSQLSERVER**.</span><span class="sxs-lookup"><span data-stu-id="fe4e0-118">The default instance is **MSSQL10_50.MSSQLSERVER**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe4e0-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe4e0-119">See Also</span></span>  
 [<span data-ttu-id="fe4e0-120">SQL Server-Browserdienst</span><span class="sxs-lookup"><span data-stu-id="fe4e0-120">SQL Server Browser Service</span></span>](../../../2014/tools/configuration-manager/sql-server-browser-service.md)  
  
  
