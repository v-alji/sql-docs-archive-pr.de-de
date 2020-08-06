---
title: Aufheben der Unterdrückung von Warnungen für das Ausführen von benutzerdefinierten Berichten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Management Studio [SQL Server], custom reports
ms.assetid: 0deed900-c910-4d12-aac0-6ab9e39eb068
author: stevestein
ms.author: sstein
ms.openlocfilehash: 725362ff7f8a6c282529f652e8813a8083257eb8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695217"
---
# <a name="unsuppress-run-custom-report-warnings"></a><span data-ttu-id="ba60a-102">Aufheben der Unterdrückung von Warnungen für das Ausführen von benutzerdefinierten Berichten</span><span class="sxs-lookup"><span data-stu-id="ba60a-102">Unsuppress Run Custom Report Warnings</span></span>
  <span data-ttu-id="ba60a-103">Für benutzerdefinierte Berichte gibt es zwei Warndialogfelder.</span><span class="sxs-lookup"><span data-stu-id="ba60a-103">There are two warning dialog boxes for custom reports.</span></span> <span data-ttu-id="ba60a-104">In diesem Thema wird beschrieben, wie die Unterdrückung der Anzeige dieser Felder in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]aufgehoben werden kann.</span><span class="sxs-lookup"><span data-stu-id="ba60a-104">This topic describes how to unsuppress the display of these boxes in [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] by using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="ba60a-105">Standardmäßig wird das Dialogfeld **Benutzerdefinierten Bericht ausführen** vor dem Ausführen eines benutzerdefinierten Berichts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba60a-105">By default, the **Run Custom Reports** dialog box appears before a custom report runs.</span></span> <span data-ttu-id="ba60a-106">Wenn Sie das Kontrollkästchen **Diese Meldung nicht mehr anzeigen** aktivieren, wird das Dialogfeld nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba60a-106">If you select the **Please don't show this warning again** check box, the dialog box will no longer appear.</span></span> <span data-ttu-id="ba60a-107">Standardmäßig wird das Dialogfeld **Benutzerdefinierten Bericht ausführen** auch dann angezeigt, wenn Sie einen benutzerdefinierten Bericht öffnen und dann auf einen Link klicken, um einen anderen benutzerdefinierten Bericht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ba60a-107">Also by default, the **Run Custom Reports** dialog box appears when you open a custom report and then click a link to open another custom report.</span></span> <span data-ttu-id="ba60a-108">In diesem Dialogfeld wird der vollständige Pfad zur benutzerdefinierten Drillthroughberichtsdatei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba60a-108">This dialog box displays the fill path to the drill-through custom report file.</span></span> <span data-ttu-id="ba60a-109">Wenn Sie das Kontrollkästchen **Diese Meldung nicht mehr anzeigen** aktivieren, wird das Dialogfeld nicht mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ba60a-109">If you select the **Please don't show this warning again** check box, the dialog box will no longer appear.</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMSProcedure"></a> <span data-ttu-id="ba60a-110">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ba60a-110">Using SQL Server Management Studio</span></span>  
  
#### <a name="to-unsuppress-the-main-custom-report-warning-dialog-box"></a><span data-ttu-id="ba60a-111">So heben Sie die Unterdrückung des Warndialogfelds für den benutzerdefinierten Hauptbericht auf</span><span class="sxs-lookup"><span data-stu-id="ba60a-111">To unsuppress the main custom report warning dialog box</span></span>  
  
1.  <span data-ttu-id="ba60a-112">Stellen Sie eine Verbindung mit \<*Server*> \\ < *Freigabe* >| \<*Drive*> \Dokumente und Einstellungen \\<USERPROFILE \> \Anwendungsdaten\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml her.</span><span class="sxs-lookup"><span data-stu-id="ba60a-112">Connect to \<*Server*>\\<*Share*>|\<*Drive*>\Documents and Settings\\<UserProfile\>\Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span></span>  
  
2.  <span data-ttu-id="ba60a-113">Klicken Sie mit der rechten Maustaste `reports.xml` , und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="ba60a-113">Right-click `reports.xml`, and then click **Edit**.</span></span>  
  
3.  <span data-ttu-id="ba60a-114">Ändern\*\* \<SuppressWarning> \</SuppressWarning> Sie true \<SuppressWarning> in \</SuppressWarning> false\*\*.</span><span class="sxs-lookup"><span data-stu-id="ba60a-114">Change**\<SuppressWarning>true\</SuppressWarning> to \<SuppressWarning>false\</SuppressWarning>**.</span></span>  
  
4.  <span data-ttu-id="ba60a-115">Starten Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] neu.</span><span class="sxs-lookup"><span data-stu-id="ba60a-115">Restart [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-unsuppress-the-drill-through-custom-report-warning-dialog-box"></a><span data-ttu-id="ba60a-116">So heben Sie die Unterdrückung des Warndialogfelds für den benutzerdefinierten Drillthroughbericht auf</span><span class="sxs-lookup"><span data-stu-id="ba60a-116">To unsuppress the drill-through custom report warning dialog box</span></span>  
  
1.  <span data-ttu-id="ba60a-117">Stellen Sie eine Verbindung mit \<*Server*> \\ < *Freigabe* >| \<*Drive*> \Dokumente und Einstellungen \\<USERPROFILE \> \Anwendungsdaten\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml her.</span><span class="sxs-lookup"><span data-stu-id="ba60a-117">Connect to \<*Server*>\\<*Share*>|\<*Drive*>\Documents and Settings\\<UserProfile\>\Application Data\Microsoft\Microsoft SQL Server\120\Tools\Shell\reports.xml.</span></span>  
  
2.  <span data-ttu-id="ba60a-118">Klicken Sie mit der rechten Maustaste `reports.xml` , und klicken Sie auf **Bearbeiten**</span><span class="sxs-lookup"><span data-stu-id="ba60a-118">Right-click `reports.xml`, and click **Edit**.</span></span>  
  
3.  <span data-ttu-id="ba60a-119">Ändern \*\* \<SuppressDrillthroughWarning> \</SuppressDrillthroughWarning> Sie true \<SuppressDrillthroughWarning> in \</SuppressDrillthroughWarning> false\*\*.</span><span class="sxs-lookup"><span data-stu-id="ba60a-119">Change **\<SuppressDrillthroughWarning>true\</SuppressDrillthroughWarning>to \<SuppressDrillthroughWarning>false\</SuppressDrillthroughWarning>**.</span></span>  
  
4.  <span data-ttu-id="ba60a-120">Starten Sie [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] neu.</span><span class="sxs-lookup"><span data-stu-id="ba60a-120">Restart [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ba60a-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ba60a-121">See Also</span></span>  
 <span data-ttu-id="ba60a-122">[Benutzerdefinierte Berichte in Management Studio](custom-reports-in-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="ba60a-122">[Custom Reports in Management Studio](custom-reports-in-management-studio.md) </span></span>  
 <span data-ttu-id="ba60a-123">[Hinzufügen eines benutzerdefinierten Berichts zu Management Studio](add-a-custom-report-to-management-studio.md) </span><span class="sxs-lookup"><span data-stu-id="ba60a-123">[Add a Custom Report to Management Studio](add-a-custom-report-to-management-studio.md) </span></span>  
 [<span data-ttu-id="ba60a-124">Verwenden benutzerdefinierter Berichte mit Eigenschaften von Objekt-Explorer-Knoten</span><span class="sxs-lookup"><span data-stu-id="ba60a-124">Use Custom Reports with Object Explorer Node Properties</span></span>](use-custom-reports-with-object-explorer-node-properties.md)  
  
  
