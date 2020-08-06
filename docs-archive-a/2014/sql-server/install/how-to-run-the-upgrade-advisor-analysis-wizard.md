---
title: 'Vorgehensweise: Ausführen des Analyse-Assistenten für den Upgrade Advisor | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- Upgrade Advisor Analysis Wizard
ms.assetid: d7d2a1e2-1179-4c05-9b0f-555b04dd1199
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 7c3e5e8a52c3b166b076aedb122e68f860037edf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621842"
---
# <a name="how-to-run-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="2e17e-102">Gewusst wie: Ausführen des Analyse-Assistenten des Upgrade Advisors</span><span class="sxs-lookup"><span data-stu-id="2e17e-102">How to: Run the Upgrade Advisor Analysis Wizard</span></span>
  <span data-ttu-id="2e17e-103">Der Analyse-Assistent des Upgrade Advisors wird über die Startseite des Upgrade Advisors gestartet.</span><span class="sxs-lookup"><span data-stu-id="2e17e-103">You start the Upgrade Advisor Analysis Wizard from the Upgrade Advisor start page.</span></span> <span data-ttu-id="2e17e-104">In diesem Thema wird beschrieben, wie Sie den Analyse-Assistenten des Upgrade Advisors ausführen.</span><span class="sxs-lookup"><span data-stu-id="2e17e-104">This topic describes how to run the Upgrade Advisor Analysis Wizard.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="2e17e-105">Wenn Sie den Analyse-Assistenten des Upgrade Advisors ausführen, speichert Upgrade Advisor die Berichte im Standardberichtsordner.</span><span class="sxs-lookup"><span data-stu-id="2e17e-105">When you run the Upgrade Advisor Analysis Wizard, Upgrade Advisor saves the reports in the default report folder.</span></span> <span data-ttu-id="2e17e-106">Der Berichts-Viewer zeigt jedoch nur die fünf zuletzt gespeicherten Berichte an.</span><span class="sxs-lookup"><span data-stu-id="2e17e-106">However, the report viewer displays only the five latest saved reports.</span></span> <span data-ttu-id="2e17e-107">Der Standard Speicherort für die Berichte lautet meine Dokumente \\ [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade advisor\110\reports.</span><span class="sxs-lookup"><span data-stu-id="2e17e-107">The default location for the reports is My Documents\\[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Upgrade Advisor\110\Reports.</span></span>  
  
### <a name="to-run-the-upgrade-advisor-analysis-wizard"></a><span data-ttu-id="2e17e-108">So führen Sie den Analyse-Assistenten des Upgrade Advisors aus</span><span class="sxs-lookup"><span data-stu-id="2e17e-108">To run the Upgrade Advisor Analysis Wizard</span></span>  
  
1.  <span data-ttu-id="2e17e-109">Klicken Sie auf der Startseite des Upgrade Advisors auf **Analyse-Assistenten des Upgrade Advisors starten**.</span><span class="sxs-lookup"><span data-stu-id="2e17e-109">On the Upgrade Advisor start page, click **Launch Upgrade Advisor Analysis Wizard**.</span></span>  
  
2.  <span data-ttu-id="2e17e-110">Geben Sie auf der Seite \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Komponenten\*\* den Namen des zu überprüfenden Servers in das Feld **Servername** ein, und klicken Sie dann auf **erkennen**.</span><span class="sxs-lookup"><span data-stu-id="2e17e-110">On the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Components** page, enter the name of the server to scan in the **Server name** box, and then click **Detect**.</span></span> <span data-ttu-id="2e17e-111">Verwenden Sie die folgenden Richtlinien für den Servernamen:</span><span class="sxs-lookup"><span data-stu-id="2e17e-111">Use the following guidelines for the server name:</span></span>  
  
    -   <span data-ttu-id="2e17e-112">Um nicht gruppierte Instanzen zu scannen, geben Sie den Computernamen ein.</span><span class="sxs-lookup"><span data-stu-id="2e17e-112">To scan nonclustered instances, enter the computer name.</span></span>  
  
    -   <span data-ttu-id="2e17e-113">Um gruppierte Instanzen zu scannen, geben Sie den virtuellen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Namen ein.</span><span class="sxs-lookup"><span data-stu-id="2e17e-113">To scan clustered instances, enter the virtual [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] name.</span></span>  
  
    -   <span data-ttu-id="2e17e-114">Um nicht gruppierte Komponenten zu scannen, die auf einem Knoten eines Clusters installiert sind, geben Sie den Knoten Namen ein.</span><span class="sxs-lookup"><span data-stu-id="2e17e-114">To scan nonclustered components that are installed on a node of a cluster, enter the node name.</span></span>  
  
    > [!WARNING]  
    >  <span data-ttu-id="2e17e-115">Verbindungen mit einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz, die nicht auf den Standardport für Client-Verbindungen (1433) festgelegt ist, werden vom Upgrade Advisor nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2e17e-115">Upgrade Advisor does not support connecting to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that is not set to use the standard port (1433) for client connections.</span></span> <span data-ttu-id="2e17e-116">Wenn Sie eine Verbindung mit einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz herstellen möchten, die nicht den Standardport (1433) verwendet, erstellen Sie einen Alias mithilfe die IP-Adresse und des Ports.</span><span class="sxs-lookup"><span data-stu-id="2e17e-116">If you want to connect to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance that does not use the standard port (1433), create an alias using the IP address and the port.</span></span> <span data-ttu-id="2e17e-117">Weitere Informationen zum Konfigurieren von Client Protokollen und Erstellen eines Alias für- [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Instanzen finden Sie unter [Konfigurieren von Client Protokollen](../../database-engine/configure-windows/configure-client-protocols.md).</span><span class="sxs-lookup"><span data-stu-id="2e17e-117">For more information about configuring client protocols and creating an alias for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instances, see [Configure Client Protocols](../../database-engine/configure-windows/configure-client-protocols.md).</span></span>  
    >   
    >  <span data-ttu-id="2e17e-118">Wenn Sie nicht [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auf dem Computer installiert haben, auf dem Sie den Upgrade Advisor ausführen, klicken Sie auf **Start**und dann auf Ausführen `cliconfg` .</span><span class="sxs-lookup"><span data-stu-id="2e17e-118">If you do not have [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installed on the computer on which you are running Upgrade Advisor, click **Start**, and then run  `cliconfg`.</span></span> <span data-ttu-id="2e17e-119">Dadurch wird das Dialogfeld \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Netzwerk-Hilfsprogramm\*\* geöffnet.</span><span class="sxs-lookup"><span data-stu-id="2e17e-119">This opens the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Network Utility** dialog box.</span></span> <span data-ttu-id="2e17e-120">Verwenden Sie die Registerkarte **Alias** , um den Alias zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2e17e-120">Use the **Alias** tab to create the alias.</span></span>  
  
3.  <span data-ttu-id="2e17e-121">Überprüfen Sie die Liste der erkannten Komponenten, ändern Sie die Auswahl nach Bedarf, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="2e17e-121">Review the list of components detected, modify the selections as necessary, and then click **Next**.</span></span>  
  
4.  <span data-ttu-id="2e17e-122">Wählen Sie auf der Seite **Verbindungsparameter** die Instanz von aus, die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Sie scannen möchten, wählen Sie die Authentifizierungsmethode aus, und geben Sie ggf. Benutzername und Kennwort ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="2e17e-122">On the **Connection Parameters** page, select the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] you want to scan, select the authentication method and, if necessary, enter user name and password information, and then click **Next**.</span></span>  
  
     <span data-ttu-id="2e17e-123">Der Name der Standardinstanz lautet MSSQLSERVER.</span><span class="sxs-lookup"><span data-stu-id="2e17e-123">The default instance name is MSSQLSERVER.</span></span>  
  
5.  <span data-ttu-id="2e17e-124">Geben Sie für ausgewählte Komponenten die angeforderten Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="2e17e-124">For selected components, enter the requested information.</span></span> <span data-ttu-id="2e17e-125">Weitere Informationen zu einzelnen Dialogfeldern finden Sie unter [Referenz zur Benutzeroberfläche des Upgrade Advisors](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span><span class="sxs-lookup"><span data-stu-id="2e17e-125">For more information about individual dialog boxes, see [Upgrade Advisor User Interface Reference](../../../2014/sql-server/install/upgrade-advisor-user-interface-reference.md).</span></span>  
  
6.  <span data-ttu-id="2e17e-126">Überprüfen Sie auf der Seite **Upgrade Advisor-Einstellungen bestätigen** die von Ihnen eingegebenen Informationen.</span><span class="sxs-lookup"><span data-stu-id="2e17e-126">On the **Confirm Upgrade Advisor Setting** page, review the information that you entered.</span></span> <span data-ttu-id="2e17e-127">Wenn Sie den Upgradebericht einreichen möchten, können Sie \*\*Berichte Senden an [!INCLUDE[msCoName](../../includes/msconame-md.md)] \*\* auswählen.</span><span class="sxs-lookup"><span data-stu-id="2e17e-127">You can select **Send reports to [!INCLUDE[msCoName](../../includes/msconame-md.md)]** if you want to submit your upgrade report.</span></span> <span data-ttu-id="2e17e-128">Sie können auch die Datenschutzrichtlinie überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2e17e-128">You can also review the privacy policy.</span></span>  
  
7.  <span data-ttu-id="2e17e-129">Klicken Sie auf **Ausführen** , um die Instanz von zu analysieren [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="2e17e-129">Click **Run** to analyze the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
8.  <span data-ttu-id="2e17e-130">Wenn die Analyse abgeschlossen ist, klicken Sie auf **Bericht starten** , um die erkannten Upgradeprobleme anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2e17e-130">When the analysis is finished, click **Launch Report** to view the detected upgrade issues.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e17e-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2e17e-131">See Also</span></span>  
 <span data-ttu-id="2e17e-132">[Vorgehensweise: Starten des Upgrade Advisors](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span><span class="sxs-lookup"><span data-stu-id="2e17e-132">[How to: Launch Upgrade Advisor](../../../2014/sql-server/install/how-to-launch-upgrade-advisor.md) </span></span>  
 <span data-ttu-id="2e17e-133">[Ausführen des Upgrade Advisors &#40;Benutzeroberfläche&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span><span class="sxs-lookup"><span data-stu-id="2e17e-133">[Running Upgrade Advisor &#40;User Interface&#41;](../../../2014/sql-server/install/running-upgrade-advisor-user-interface.md) </span></span>  
 [<span data-ttu-id="2e17e-134">Arbeiten mit dem Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="2e17e-134">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
