---
title: Konfigurieren der Anmeldungsüberwachung (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- auditing [SQL Server]
- audits [SQL Server], logins
- logins [SQL Server], auditing
ms.assetid: 16961116-57ac-4eef-8037-791b26ade548
author: stevestein
ms.author: sstein
ms.openlocfilehash: b7e05f6c254e098a67a5ce00435c009cd450af44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622349"
---
# <a name="configure-login-auditing-sql-server-management-studio"></a><span data-ttu-id="ae9c4-102">Konfigurieren der Anmeldungsüberwachung (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="ae9c4-102">Configure Login Auditing (SQL Server Management Studio)</span></span>
  <span data-ttu-id="ae9c4-103">In diesem Thema wird beschrieben, wie die Anmeldeüberwachung in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] konfiguriert wird, um die [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)]-Anmeldeaktivität zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="ae9c4-103">This topic describes how to configure login auditing in [!INCLUDE[ssCurrent](../includes/sscurrent-md.md)] to monitor [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] login activity.</span></span> <span data-ttu-id="ae9c4-104">Die Anmeldungsüberwachung kann so konfiguriert werden, dass die folgenden Ereignisse im Fehlerprotokoll aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="ae9c4-104">Login auditing can be configured to write to the error log on the following events.</span></span>  
  
-   <span data-ttu-id="ae9c4-105">Fehlgeschlagene Anmeldungen</span><span class="sxs-lookup"><span data-stu-id="ae9c4-105">Failed logins</span></span>  
  
-   <span data-ttu-id="ae9c4-106">Erfolgreiche Anmeldungen</span><span class="sxs-lookup"><span data-stu-id="ae9c4-106">Successful logins</span></span>  
  
-   <span data-ttu-id="ae9c4-107">Erfolgreiche und fehlgeschlagene Anmeldungen</span><span class="sxs-lookup"><span data-stu-id="ae9c4-107">Both failed and successful logins</span></span>  
  
 <span data-ttu-id="ae9c4-108">Sie müssen [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] neu starten, damit die Option wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="ae9c4-108">You must restart [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] before this option will take effect.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ae9c4-109">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ae9c4-109">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-configure-login-auditing"></a><span data-ttu-id="ae9c4-110">So konfigurieren Sie die Anmeldungsüberwachung</span><span class="sxs-lookup"><span data-stu-id="ae9c4-110">To configure login auditing</span></span>  
  
1.  <span data-ttu-id="ae9c4-111">Stellen Sie in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]mithilfe des Objekt-Explorers eine Verbindung mit einer Instanz von [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] her.</span><span class="sxs-lookup"><span data-stu-id="ae9c4-111">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to an instance of the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)] with Object Explorer.</span></span>  
  
2.  <span data-ttu-id="ae9c4-112">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Servernamen, und klicken Sie auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="ae9c4-112">In Object Explorer, right-click the server name, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="ae9c4-113">Wählen Sie auf der Seite **Sicherheit** unter **Anmeldungsüberwachung** die gewünschte Option aus, und schließen Sie die Seite **Servereigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="ae9c4-113">On the **Security** page, under **Login** auditing, click the desired option and close the **Server Properties** page.</span></span>  
  
4.  <span data-ttu-id="ae9c4-114">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf den Servernamen, und klicken Sie dann auf **Neu starten**.</span><span class="sxs-lookup"><span data-stu-id="ae9c4-114">In Object Explorer, right-click the server name, and then click **Restart**.</span></span>  
  
  
