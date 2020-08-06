---
title: Anzeigen des Anwendungsprotokolls von Windows (Windows) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: performance
ms.topic: conceptual
helpviewer_keywords:
- viewing logs
- application logs [SQL Server]
- logs [SQL Server], application
- monitoring Windows NT application log [SQL Server]
- Windows NT application logs [SQL Server]
- displaying logs
- monitoring [SQL Server], events
- logs [SQL Server], viewing
ms.assetid: 168a6c6e-12df-46a9-9904-55d63ca8fe14
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 1255e95833d9fc56abd1700f5acb0d2f49ebf77c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699512"
---
# <a name="view-the-windows-application-log-windows"></a><span data-ttu-id="a5b1f-102">Anzeigen des Anwendungsprotokolls von Windows (Windows)</span><span class="sxs-lookup"><span data-stu-id="a5b1f-102">View the Windows Application Log (Windows)</span></span>
  <span data-ttu-id="a5b1f-103">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] für die Verwendung des Windows-Anwendungsprotokolls konfiguriert ist, werden bei jeder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Sitzung neue Ereignisse in das Protokoll geschrieben.</span><span class="sxs-lookup"><span data-stu-id="a5b1f-103">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is configured to use the Windows application log, each [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] session writes new events to that log.</span></span> <span data-ttu-id="a5b1f-104">Im Gegensatz zum Fehlerprotokoll von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird beim Starten einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz nicht jedes Mal ein neues Anwendungsprotokoll erstellt.</span><span class="sxs-lookup"><span data-stu-id="a5b1f-104">Unlike the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log, a new application log is not created each time you start an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="to-view-the-windows-application-log"></a><span data-ttu-id="a5b1f-105">So zeigen Sie das Anwendungsprotokoll von Windows an</span><span class="sxs-lookup"><span data-stu-id="a5b1f-105">To view the Windows application log</span></span>  
  
1.  <span data-ttu-id="a5b1f-106">Zeigen Sie im Menü **Start** auf **Alle Programme**und anschließend auf **Verwaltung**, und klicken Sie dann auf **Ereignisanzeige**.</span><span class="sxs-lookup"><span data-stu-id="a5b1f-106">On the **Start** menu, point to **All Programs**, point to **Administrative Tools**, and then click **Event Viewer**.</span></span>  
  
2.  <span data-ttu-id="a5b1f-107">Klicken Sie in der Ereignisanzeige auf **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="a5b1f-107">In Event Viewer, click **Application**.</span></span>  
  
3.  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="a5b1f-108">-Ereignisse werden in der **Source**-Spalte durch den Eintrag **MSSQLSERVER** identifiziert (benannte Instanzen werden durch **MSSQL$** _<Instanzname>_ identifiziert).</span><span class="sxs-lookup"><span data-stu-id="a5b1f-108">events are identified by the entry **MSSQLSERVER** (named instances are identified with **MSSQL$**_<instance_name>_) in the **Source** column.</span></span> <span data-ttu-id="a5b1f-109">Die Ereignisse des SQL Server-Agents werden durch den Eintrag SQLSERVERAGENT identifiziert (bei benannten Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] werden [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Agent-Ereignisse durch **SQLAgent$** \<*instance_name*> identifiziert).</span><span class="sxs-lookup"><span data-stu-id="a5b1f-109">SQL Server Agent events are identified by the entry SQLSERVERAGENT (for named instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events are identified with **SQLAgent$**\<*instance_name*>).</span></span> <span data-ttu-id="a5b1f-110">Die Ereignisse des Microsoft Search-Dienstes werden durch den Eintrag **Microsoft Search**identifiziert.</span><span class="sxs-lookup"><span data-stu-id="a5b1f-110">Microsoft Search service events are identified by the entry **Microsoft Search**.</span></span>  
  
4.  <span data-ttu-id="a5b1f-111">Klicken Sie mit der rechten Maustaste auf **Ereignisanzeige**, klicken Sie anschließend auf **Verbindung mit anderem Computer herstellen** , und nehmen Sie im Dialogfeld **Computer auswählen**die entsprechenden Einstellungen vor, um das Protokoll eines anderen Computers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a5b1f-111">To view the log of a different computer, right-click **Event Viewer**, click **Connect to another computer,** and complete the **Select Computer**dialog box.</span></span>  
  
5.  <span data-ttu-id="a5b1f-112">Wenn Sie wahlweise nur die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Ereignisse anzeigen möchten, klicken Sie im Menü **Ansicht** auf **Filter**, und wählen Sie in der Liste **Ereignisquelle** den Eintrag **MSSQLSERVER**aus.</span><span class="sxs-lookup"><span data-stu-id="a5b1f-112">Optionally, to display only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] events, on the **View** menu click **Filter**, and in the **Event source** list, select **MSSQLSERVER**.</span></span> <span data-ttu-id="a5b1f-113">Um nur die Ereignisse des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agents anzuzeigen, wählen Sie stattdessen in der Liste **Ereignisquelle** den Eintrag **SQLSERVERAGENT** aus.</span><span class="sxs-lookup"><span data-stu-id="a5b1f-113">To view only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent events, instead select **SQLSERVERAGENT** in the **Event source** list.</span></span>  
  
6.  <span data-ttu-id="a5b1f-114">Um weitere Informationen zu einem bestimmten Ereignis anzuzeigen, doppelklicken Sie auf dieses Ereignis.</span><span class="sxs-lookup"><span data-stu-id="a5b1f-114">To view more information about an event, double-click the event.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5b1f-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a5b1f-115">See Also</span></span>  
 [<span data-ttu-id="a5b1f-116">Anzeigen des SQL Server-Fehlerprotokolls &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="a5b1f-116">View the SQL Server Error Log &#40;SQL Server Management Studio&#41;</span></span>](../../ssms/sql-server-management-studio-ssms.md)  
  
  
