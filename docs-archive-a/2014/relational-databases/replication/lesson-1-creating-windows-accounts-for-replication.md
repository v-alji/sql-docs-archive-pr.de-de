---
title: 'Lektion 1: Erstellen von Windows-Konten für die Replikation | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- replication [SQL Server], tutorials
- replication [SQL Server], administering
ms.assetid: 65c3816b-47f0-448c-a4a4-ebd3e2a58820
author: rothja
ms.author: jroth
ms.openlocfilehash: 29f1008338b3ba728066ed611108477586a4c899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609068"
---
# <a name="lesson-1-creating-windows-accounts-for-replication"></a><span data-ttu-id="d02ad-102">Lektion 1: Erstellen von Windows-Konten für die Replikation</span><span class="sxs-lookup"><span data-stu-id="d02ad-102">Lesson 1: Creating Windows Accounts for Replication</span></span>
  <span data-ttu-id="d02ad-103">In dieser Lektion erstellen Sie Windows-Konten zum Ausführen von Replikations-Agents.</span><span class="sxs-lookup"><span data-stu-id="d02ad-103">In this lesson, you will create Windows accounts to run replication agents.</span></span> <span data-ttu-id="d02ad-104">Sie erstellen für die folgenden Agents ein separates Windows-Konto auf dem lokalen Server:</span><span class="sxs-lookup"><span data-stu-id="d02ad-104">You will create a separate Windows account on the local server for the following agents:</span></span>  
  
|<span data-ttu-id="d02ad-105">Agent</span><span class="sxs-lookup"><span data-stu-id="d02ad-105">Agent</span></span>|<span data-ttu-id="d02ad-106">Standort</span><span class="sxs-lookup"><span data-stu-id="d02ad-106">Location</span></span>|<span data-ttu-id="d02ad-107">Kontoname</span><span class="sxs-lookup"><span data-stu-id="d02ad-107">Account name</span></span>|  
|-----------|--------------|------------------|  
|<span data-ttu-id="d02ad-108">Momentaufnahme-Agent</span><span class="sxs-lookup"><span data-stu-id="d02ad-108">Snapshot Agent</span></span>|<span data-ttu-id="d02ad-109">Herausgeber</span><span class="sxs-lookup"><span data-stu-id="d02ad-109">Publisher</span></span>|<span data-ttu-id="d02ad-110">\<*machine_name*>\ repl_snapshot</span><span class="sxs-lookup"><span data-stu-id="d02ad-110">\<*machine_name*>\repl_snapshot</span></span>|  
|<span data-ttu-id="d02ad-111">Protokolllese-Agent</span><span class="sxs-lookup"><span data-stu-id="d02ad-111">Log Reader Agent</span></span>|<span data-ttu-id="d02ad-112">Herausgeber</span><span class="sxs-lookup"><span data-stu-id="d02ad-112">Publisher</span></span>|<span data-ttu-id="d02ad-113">\<*machine_name*>\ repl_logreader</span><span class="sxs-lookup"><span data-stu-id="d02ad-113">\<*machine_name*>\repl_logreader</span></span>|  
|<span data-ttu-id="d02ad-114">Verteilungs-Agent</span><span class="sxs-lookup"><span data-stu-id="d02ad-114">Distribution Agent</span></span>|<span data-ttu-id="d02ad-115">Verleger und Abonnent</span><span class="sxs-lookup"><span data-stu-id="d02ad-115">Publisher and Subscriber</span></span>|<span data-ttu-id="d02ad-116">\<*machine_name*>\ repl_distribution</span><span class="sxs-lookup"><span data-stu-id="d02ad-116">\<*machine_name*>\repl_distribution</span></span>|  
|<span data-ttu-id="d02ad-117">Merge-Agent</span><span class="sxs-lookup"><span data-stu-id="d02ad-117">Merge Agent</span></span>|<span data-ttu-id="d02ad-118">Verleger und Abonnent</span><span class="sxs-lookup"><span data-stu-id="d02ad-118">Publisher and Subscriber</span></span>|<span data-ttu-id="d02ad-119">\<*machine_name*>\ repl_merge</span><span class="sxs-lookup"><span data-stu-id="d02ad-119">\<*machine_name*>\repl_merge</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="d02ad-120">In den Replikationslernprogrammen wird für Verleger und Verteiler dieselbe Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gemeinsam verwendet.</span><span class="sxs-lookup"><span data-stu-id="d02ad-120">In the replication tutorials, the Publisher and Distributor share the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="d02ad-121">Verleger und Abonnent können dieselbe Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gemeinsam verwenden; dies ist jedoch keine Anforderung.</span><span class="sxs-lookup"><span data-stu-id="d02ad-121">The Publisher and Subscriber may share the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but it is not a requirement.</span></span> <span data-ttu-id="d02ad-122">Wenn der Verleger und Abonnent dieselbe Instanz verwenden, sind die Schritte zum Erstellen von Konten auf dem Verleger nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d02ad-122">If the Publisher and Subscriber share the same instance, the steps that are used to create accounts at the Subscriber are not required.</span></span>  
  
### <a name="to-create-local-windows-accounts-for-replication-agents-at-the-publisher"></a><span data-ttu-id="d02ad-123">So erstellen Sie lokale Windows-Konten für Replikations-Agents auf dem Verleger</span><span class="sxs-lookup"><span data-stu-id="d02ad-123">To create local Windows accounts for replication agents at the Publisher</span></span>  
  
1.  <span data-ttu-id="d02ad-124">Öffnen Sie auf dem Verleger in der Systemsteuerung unter **Verwaltung** die Option **Computer Verwaltung** .</span><span class="sxs-lookup"><span data-stu-id="d02ad-124">At the Publisher, open **Computer Management** from **Administrative Tools** in Control Panel.</span></span>  
  
2.  <span data-ttu-id="d02ad-125">Erweitern Sie unter **System**den Eintrag **Lokale Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="d02ad-125">In **System Tools**, expand **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="d02ad-126">Klicken Sie mit der rechten Maustaste auf **Benutzer** und anschließend auf **neuer Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="d02ad-126">Right-click **Users** and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="d02ad-127">Geben Sie `repl_snapshot` in das Feld **Benutzername** ein, geben Sie das Kennwort und andere relevante Informationen an, und klicken Sie dann auf **Erstellen** , um das repl_snapshot Konto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d02ad-127">Enter `repl_snapshot` in the **User name** box, provide the password and other relevant information, and then click **Create** to create the repl_snapshot account.</span></span>  
  
5.  <span data-ttu-id="d02ad-128">Wiederholen Sie den letzten Schritt, um die Konten repl_logreader, repl_distribution und repl_merge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d02ad-128">Repeat the previous step to create the repl_logreader, repl_distribution, and repl_merge accounts.</span></span>  
  
6.  <span data-ttu-id="d02ad-129">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d02ad-129">Click **Close**.</span></span>  
  
### <a name="to-create-local-windows-accounts-for-replication-agents-at-the-subscriber"></a><span data-ttu-id="d02ad-130">So erstellen Sie lokale Windows-Konten für Replikations-Agents auf dem Abonnenten</span><span class="sxs-lookup"><span data-stu-id="d02ad-130">To create local Windows accounts for replication agents at the Subscriber</span></span>  
  
1.  <span data-ttu-id="d02ad-131">Öffnen Sie auf dem Abonnenten in der Systemsteuerung unter **Verwaltung** die Option **Computer Verwaltung** .</span><span class="sxs-lookup"><span data-stu-id="d02ad-131">At the Subscriber, open **Computer Management** from **Administrative Tools** in Control Panel.</span></span>  
  
2.  <span data-ttu-id="d02ad-132">Erweitern Sie unter **System**den Eintrag **Lokale Benutzer und Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="d02ad-132">In **System Tools**, expand **Local Users and Groups**.</span></span>  
  
3.  <span data-ttu-id="d02ad-133">Klicken Sie mit der rechten Maustaste auf **Benutzer** und anschließend auf **neuer Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="d02ad-133">Right-click **Users** and then click **New User**.</span></span>  
  
4.  <span data-ttu-id="d02ad-134">Geben Sie `repl_distribution` in das Feld **Benutzername** ein, geben Sie das Kennwort und andere relevante Informationen an, und klicken Sie dann auf **Erstellen** , um das repl_distribution Konto zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d02ad-134">Enter `repl_distribution` in the **User name** box, provide the password and other relevant information, and then click **Create** to create the repl_distribution account.</span></span>  
  
5.  <span data-ttu-id="d02ad-135">Wiederholen Sie den letzten Schritt, um das Konto repl_merge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d02ad-135">Repeat the previous step to create the repl_merge account.</span></span>  
  
6.  <span data-ttu-id="d02ad-136">Klicken Sie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="d02ad-136">Click **Close**.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="d02ad-137">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d02ad-137">Next Steps</span></span>  
 <span data-ttu-id="d02ad-138">Sie haben Windows-Konten für Replikations-Agents erfolgreich erstellt.</span><span class="sxs-lookup"><span data-stu-id="d02ad-138">You have successfully created Windows accounts for replication agents.</span></span> <span data-ttu-id="d02ad-139">Als Nächstes konfigurieren Sie den Momentaufnahmeordner.</span><span class="sxs-lookup"><span data-stu-id="d02ad-139">Next, you will configure the snapshot folder.</span></span> <span data-ttu-id="d02ad-140">Weitere Informationen finden Sie unter [Lektion 2: Vorbereiten des Momentaufnahmeordners](lesson-2-preparing-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="d02ad-140">See [Lesson 2: Preparing the Snapshot Folder](lesson-2-preparing-the-snapshot-folder.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d02ad-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d02ad-141">See Also</span></span>  
 [<span data-ttu-id="d02ad-142">Übersicht über Replikations-Agents</span><span class="sxs-lookup"><span data-stu-id="d02ad-142">Replication Agents Overview</span></span>](agents/replication-agents-overview.md)  
  
  
