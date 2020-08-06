---
title: SQL Server-Fehlerprotokolle konfigurieren (Seite Allgemein) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: configuration
ms.topic: conceptual
f1_keywords:
- sql12.swb.configurelogs.configureerrorlogs.f1
ms.assetid: 03f0d463-9b0b-4af9-a853-da936d75e5af
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 8acc27150f42049384e2789ef83ae66a737da9bd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622890"
---
# <a name="configure-sql-server-error-logs"></a><span data-ttu-id="7efbb-102">Konfigurieren von SQL Server-Fehlerprotokollen</span><span class="sxs-lookup"><span data-stu-id="7efbb-102">Configure SQL Server Error Logs</span></span>
  <span data-ttu-id="7efbb-103">In diesem Thema wird beschrieben, wie Sie [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlerprotokolle anzeigen oder deren Wiederverwendung ändern.</span><span class="sxs-lookup"><span data-stu-id="7efbb-103">This topic describes how to view or modify the way [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error logs are recycled.</span></span>  
  
## <a name="to-open-the-configure-sql-server-error-logs-dialog-box"></a><span data-ttu-id="7efbb-104">So öffnen Sie das Dialogfeld SQL Server-Fehlerprotokolle konfigurieren</span><span class="sxs-lookup"><span data-stu-id="7efbb-104">To open the Configure SQL Server Error Logs dialog box</span></span>  
  
1.  <span data-ttu-id="7efbb-105">Erweitern Sie im Objekt-Explorer die SQL Server-Instanz und anschließend **Verwaltung**. Klicken Sie anschließend mit der rechten Maustaste auf **Server-Protokolle**, und klicken Sie anschließend auf **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="7efbb-105">In Object Explorer, expand the instance of SQL Server, expand **Management**, right-click **SQL Server Logs**, and then click **Configure**.</span></span>  
  
2.  <span data-ttu-id="7efbb-106">Wählen Sie im Dialogfeld **SQL Server-Fehlerprotokolle konfigurieren** zwischen den folgenden Optionen aus.</span><span class="sxs-lookup"><span data-stu-id="7efbb-106">In the **Configure SQL Server Error Logs** dialog box, choose from the following options.</span></span>  
  
     <span data-ttu-id="7efbb-107">**Beschränken Sie die Anzahl der Fehlerprotokolldateien vor der Wiederverwendung**</span><span class="sxs-lookup"><span data-stu-id="7efbb-107">**Limit the number of the error log files before they are recycled**</span></span>  
     <span data-ttu-id="7efbb-108">Überprüft die Anzahl der bereits erstellten Fehlerprotokolle, bevor diese wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7efbb-108">Check to limit the number of error logs created before they are recycled.</span></span> <span data-ttu-id="7efbb-109">Bei jedem Start einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird ein neues Fehlerprotokoll erstellt.</span><span class="sxs-lookup"><span data-stu-id="7efbb-109">A new error log is created each time an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="7efbb-110">behält Sicherungen der vorherigen sechs Protokolle bei, außer wenn Sie diese Option aktivieren und eine andere maximale Anzahl von Fehlerprotokolldateien angeben.</span><span class="sxs-lookup"><span data-stu-id="7efbb-110">retains backups of the previous six logs, unless you check this option, and specify a different maximum number of error log files below.</span></span>  
  
     <span data-ttu-id="7efbb-111">**Maximale Anzahl von Fehlerprotokolldateien**</span><span class="sxs-lookup"><span data-stu-id="7efbb-111">**Maximum number of error log files**</span></span>  
     <span data-ttu-id="7efbb-112">Gibt die maximale Anzahl der erstellten Fehlerprotokolldateien vor der Wiederverwendung an.</span><span class="sxs-lookup"><span data-stu-id="7efbb-112">Specify the maximum number of error log files created before they are recycled.</span></span> <span data-ttu-id="7efbb-113">Der Standardwert ist 6. Dies entspricht der Anzahl der vorhergehenden Sicherungsprotokolle, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vor der Wiederverwendung beibehält.</span><span class="sxs-lookup"><span data-stu-id="7efbb-113">The default is 6, which is the number of previous backup logs [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retains before recycling them.</span></span>  
  
  
