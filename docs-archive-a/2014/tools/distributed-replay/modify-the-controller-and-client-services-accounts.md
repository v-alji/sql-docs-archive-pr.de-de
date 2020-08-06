---
title: Ändern des Controllers und der Clientdienstkonten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: 44a73ddb-18ad-415c-bfbe-126ab2e3290b
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 62a054749f1d53323bde5c9d05a1e7632b1dda85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719267"
---
# <a name="modify-the-controller-and-client-services-accounts"></a><span data-ttu-id="1bdcf-102">Ändern von Controller- und Clientdienstkonten</span><span class="sxs-lookup"><span data-stu-id="1bdcf-102">Modify the Controller and Client Services Accounts</span></span>
  <span data-ttu-id="1bdcf-103">In diesem Thema werden Änderungen der Distributed Replay Controller- und Clientdienstkonten und die erneute Anwendung der Zugriffssteuerungslisten (Access Control List, ACL) behandelt.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-103">In this topic, you will learn how to modify the Distributed Replay controller and client service accounts, and then reapply the access control lists (ACLs).</span></span>  
  
### <a name="to-start-or-stop-the-distributed-replay-services-using-computer-management"></a><span data-ttu-id="1bdcf-104">So starten oder beenden Sie die Distributed Replay-Dienste über die Computerverwaltung</span><span class="sxs-lookup"><span data-stu-id="1bdcf-104">To start or stop the Distributed Replay services using Computer Management</span></span>  
  
1.  <span data-ttu-id="1bdcf-105">Geben Sie auf dem Computer mit den Distributed Replay-Diensten an der Eingabeaufforderung `dcomcnfg` ein.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-105">On the computer on which the Distributed Replay services are installed, from the command prompt, type `dcomcnfg`.</span></span>  
  
2.  <span data-ttu-id="1bdcf-106">Doppelklicken Sie auf **Dienste**, Scrollen Sie nach unten, und klicken Sie mit der rechten Maustaste **Stop**auf \*\* [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay \<service name> \*\*, und klicken Sie dann auf **starten** oder</span><span class="sxs-lookup"><span data-stu-id="1bdcf-106">Double-click **Services**, scroll down and right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay \<service name>**, and then click **Start** or **Stop**.</span></span>  
  
### <a name="to-modify-the-distributed-replay-controller-service"></a><span data-ttu-id="1bdcf-107">So ändern Sie den Distributed Replay Controller-Dienst</span><span class="sxs-lookup"><span data-stu-id="1bdcf-107">To modify the Distributed Replay controller service</span></span>  
  
1.  <span data-ttu-id="1bdcf-108">Beenden Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller-Dienst auf dem Controllercomputer.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-108">On the controller computer, stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay controller service.</span></span>  
  
2.  <span data-ttu-id="1bdcf-109">Klicken Sie unter **Dienste**mit der rechten Maustaste auf **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller**, und wählen Sie dann **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-109">Under **Services**, right-click **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller**, and then select **Properties**.</span></span>  
  
3.  <span data-ttu-id="1bdcf-110">Wählen Sie im Fenster **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller** auf der Registerkarte **Anmelden** die Option **Dieses Konto**aus, geben Sie das neue Anmeldekonto ein, oder klicken Sie auf **Durchsuchen** , um dieses zu suchen. Klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-110">In the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Controller Properties** window, on the **Log On** tab, select **This account**, type or click **Browse** to enter the new logon account, and then click **OK**.</span></span>  
  
     <span data-ttu-id="1bdcf-111">**Wichtig**: Wenn Sie den Distributed Replay-Controller konfigurieren, können Sie mindestens ein Benutzerkonto angeben, das zum Ausführen der Distributed Replay-Clientdienste verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-111">**Important**: When you configure Distributed Replay Controller, you can specify one or more user accounts that will be used to run the Distributed Replay Client services.</span></span> <span data-ttu-id="1bdcf-112">Die folgenden Kontotypen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-112">The following is the list of supported accounts:</span></span>  
  
    -   <span data-ttu-id="1bdcf-113">Domänenbenutzerkonto</span><span class="sxs-lookup"><span data-stu-id="1bdcf-113">Domain user account</span></span>  
  
    -   <span data-ttu-id="1bdcf-114">Vom Benutzer erstelltes lokales Benutzerkonto</span><span class="sxs-lookup"><span data-stu-id="1bdcf-114">User created local user account</span></span>  
  
    -   <span data-ttu-id="1bdcf-115">Administrator</span><span class="sxs-lookup"><span data-stu-id="1bdcf-115">Administrator</span></span>  
  
    -   <span data-ttu-id="1bdcf-116">Virtuelles Konto und verwaltetes Dienstkonto (Managed Service Account, MSA)</span><span class="sxs-lookup"><span data-stu-id="1bdcf-116">Virtual account and MSA (Managed Service Account)</span></span>  
  
    -   <span data-ttu-id="1bdcf-117">Netzwerkdienste, lokale Dienste und System</span><span class="sxs-lookup"><span data-stu-id="1bdcf-117">Network Services, Local Services, and System</span></span>  
  
     <span data-ttu-id="1bdcf-118">Gruppenkonten (lokales oder Domänenbenutzerkonto) und andere integrierte Konten (wie "Jeder") werden nicht akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-118">Group accounts (local or domain) and other built-in accounts (like Everyone) are not accepted.</span></span>  
  
4.  <span data-ttu-id="1bdcf-119">Starten Sie den Distributed Replay Controller-Dienst.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-119">Start the Distributed Replay controller service.</span></span>  
  
### <a name="to-modify-the-distributed-replay-client-service"></a><span data-ttu-id="1bdcf-120">So ändern Sie den Distributed Replay Client-Dienst</span><span class="sxs-lookup"><span data-stu-id="1bdcf-120">To modify the Distributed Replay client service</span></span>  
  
1.  <span data-ttu-id="1bdcf-121">Bevor Sie den Distributed Replay Client-Dienst ändern, sollten Sie sicherstellen, dass das zu ändernde Clientdienstkonto (auf dem Controllercomputer im CTLRUSERS-Parameter) während des Setupvorgangs angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-121">Before you modify the Distributed Replay client service, make sure the client service account you are changing was specified during setup (in the CTLRUSERS parameter on the controller computer).</span></span> <span data-ttu-id="1bdcf-122">Wenn das Clientdienstkonto, das Sie ändern, während des Setups nicht angegeben wurde, müssen Sie zuerst die folgenden Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="1bdcf-122">If the client service account you are changing was not specified during setup, you must perform the following steps first:</span></span>  
  
    1.  <span data-ttu-id="1bdcf-123">Beenden Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay-Controllerdienst.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-123">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay controller service.</span></span>  
  
    2.  <span data-ttu-id="1bdcf-124">Geben Sie auf dem Controllercomputer, auf dem der Controllerdienst installiert ist, an der Eingabeaufforderung `dcomcnfg` ein.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-124">On the controller computer on which the controller service is installed, from the command prompt, type `dcomcnfg`.</span></span>  
  
    3.  <span data-ttu-id="1bdcf-125">Navigieren Sie im Fenster **Komponentendienste** zu **Konsolenstamm > Komponentendienste > Computer > Arbeitsplatz > DCOM Config > DReplayController**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-125">In the **Component Services** window, navigate to **Console Root -> Component Services -> Computers -> My Computer -> DCOM Config ->DReplayController**.</span></span>  
  
    4.  <span data-ttu-id="1bdcf-126">Klicken Sie mit der rechten Maustaste auf **DReplayController**, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-126">Right-click **DReplayController**, and then click **Properties**.</span></span>  
  
    5.  <span data-ttu-id="1bdcf-127">Klicken Sie im Fenster **Eigenschaften von DReplayController** auf der Registerkarte **Sicherheit** im Abschnitt **Start- und Aktivierungsberechtigungen** auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="1bdcf-127">In the **DReplayController Properties** window, on the **Security** tab, click **Edit** in the **Launch and Activation Permissions** section.</span></span>  
  
    6.  <span data-ttu-id="1bdcf-128">Erteilen Sie die dem neuen Clientdienst-Anmeldekonto die Berechtigungen **Lokale Aktivierung** und Remoteaktivierung, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-128">Grant the new client service logon account **Local and Remote activation** permissions, and then click **OK**.</span></span>  
  
    7.  <span data-ttu-id="1bdcf-129">Klicken Sie im Abschnitt **Zugriffsberechtigungen** auf **Bearbeiten** , gewähren Sie dem neuen Clientdienst-Anmeldekonto die Berechtigungen **Lokaler Zugriff** und Remotezugriff, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-129">Click **Edit** in the **Access Permissions** section, and grant the new client service logon account **Local and Remote access** permissions, and then click **OK**.</span></span>  
  
    8.  <span data-ttu-id="1bdcf-130">Klicken Sie auf **OK** , um das Fenster **Eigenschaften von DReplayController** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-130">Click **OK** to close the **DReplayController Properties** window.</span></span>  
  
    9. <span data-ttu-id="1bdcf-131">Fügen Sie auf dem Controllercomputer der Gruppe **Distributed COM-Benutzer** das geänderte Clientdienst-Anmeldekonto hinzu.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-131">On the controller computer, add the changed client service logon account to the **Distributed COM Users** group.</span></span>  
  
    10. <span data-ttu-id="1bdcf-132">Starten Sie den SQL Server Distributed Replay Controller-Dienst.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-132">Start the SQL Server Distributed Replay controller service.</span></span>  
  
2.  <span data-ttu-id="1bdcf-133">Beenden Sie den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Client-Dienst.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-133">Stop the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay client service.</span></span>  
  
3.  <span data-ttu-id="1bdcf-134">Wählen Sie im Fenster **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Client** auf der Registerkarte **Anmelden** die Option **Dieses Konto**aus, geben Sie das neue Anmeldekonto ein, oder klicken Sie auf **Durchsuchen** , um dieses zu suchen. Klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-134">In the **[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributed Replay Client Properties** window, on the **Log On** tab, select **This account**, type or click **Browse** to enter the new logon account, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="1bdcf-135">Starten Sie den Distributed Replay Client-Dienst.</span><span class="sxs-lookup"><span data-stu-id="1bdcf-135">Start the Distributed Replay client service.</span></span>  
  
  
