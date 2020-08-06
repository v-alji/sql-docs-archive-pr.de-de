---
title: Erzwingen des Abrufens des Masterservers durch einen Zielserver | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- forcing master server polling
- polling master servers [SQL Server]
- master servers [SQL Server], polling
- target servers [SQL Server], polling the master server
ms.assetid: f1189a47-5ac3-45e2-9c5f-847810672279
author: stevestein
ms.author: sstein
ms.openlocfilehash: b37bf19bfe8e8fb55c29c8d94c28a341d06df5da
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608218"
---
# <a name="force-a-target-server-to-poll-the-master-server"></a><span data-ttu-id="af13c-102">Force a Target Server to Poll the Master Server</span><span class="sxs-lookup"><span data-stu-id="af13c-102">Force a Target Server to Poll the Master Server</span></span>
  <span data-ttu-id="af13c-103">Dieses Thema beschreibt, wie Sie erzwingen, dass ein Zielserver den Masterserver abruft.</span><span class="sxs-lookup"><span data-stu-id="af13c-103">This topic describes how to force a target server to poll the master server.</span></span> <span data-ttu-id="af13c-104">Der Zielserver muss ein registrierter Server auf dem Masterserver sein.</span><span class="sxs-lookup"><span data-stu-id="af13c-104">The target server must be a registered server on the master server.</span></span>  
  
 <span data-ttu-id="af13c-105">Ein Auftrag ist eine festgelegte Reihe von Aktionen, die der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent ausführt.</span><span class="sxs-lookup"><span data-stu-id="af13c-105">A job is a specified series of actions that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent performs.</span></span> <span data-ttu-id="af13c-106">Ein Multiserverauftrag ist ein Auftrag, der von einem Masterserver auf mindestens einem Zielserver ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="af13c-106">A multiserver job is a job that a master server runs on one or more target servers.</span></span> <span data-ttu-id="af13c-107">Auf jedem Server kann gleichzeitig eine Instanz des gleichen Auftrags ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="af13c-107">Each target server can run one instance of the same job at the same time.</span></span> <span data-ttu-id="af13c-108">Jeder Zielserver ruft in regelmäßigen Abständen den Masterserver ab, lädt eine Kopie aller neuen Aufträge herunter, die dem Zielserver zugewiesen wurden, und trennt dann die Verbindung.</span><span class="sxs-lookup"><span data-stu-id="af13c-108">Each target server periodically polls the master server, downloads a copy of any new jobs assigned to the target server, and then disconnects.</span></span> <span data-ttu-id="af13c-109">Der Zielserver führt den Auftrag lokal aus und stellt dann erneut eine Verbindung mit dem Masterserver her, um den Auftragsergebnisstatus hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="af13c-109">The target server runs the job locally and then reconnects to the master server to upload the job outcome status.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="af13c-110">Wenn der Zielserver versucht, den Auftragsstatus durch Hochladen zu übertragen, und dabei nicht auf den Masterserver zugreifen kann, bleibt der Auftragsstatus so lange im Spooler (in der Warteschlange), bis der Masterserver wieder zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="af13c-110">If the master server is inaccessible when the target server tries to upload job status, the job status is spooled until the master server can be accessed.</span></span>  
  
-   <span data-ttu-id="af13c-111">**Vorbereitungen:**  [Beschränkungen](#Restrictions), [Sicherheit](#Security)</span><span class="sxs-lookup"><span data-stu-id="af13c-111">**Before you begin:**  [Limitations and Restrictions](#Restrictions), [Security](#Security)</span></span>  
  
-   <span data-ttu-id="af13c-112">**Erzwingen, dass ein Zielserver den Masterserver abruft:**  [SQL Server Management Studio](#SSMS)</span><span class="sxs-lookup"><span data-stu-id="af13c-112">**To force a target server to poll the master server, using:**  [SQL Server Management Studio](#SSMS)</span></span>  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="af13c-113">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="af13c-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="af13c-114">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="af13c-114">Limitations and Restrictions</span></span>  
 <span data-ttu-id="af13c-115">Der Zielserver muss ein registrierter Server auf dem Masterserver sein.</span><span class="sxs-lookup"><span data-stu-id="af13c-115">The target server must be a registered server on the master server.</span></span> <span data-ttu-id="af13c-116">Die Anweisungen in diesem Thema müssen auf dem Masterserver ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="af13c-116">You must run the instructions given in this topic from the master server.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="af13c-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="af13c-117">Security</span></span>  
 <span data-ttu-id="af13c-118">Ausführliche Informationen finden Sie unter [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) und [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span><span class="sxs-lookup"><span data-stu-id="af13c-118">For detailed information, see [Implement SQL Server Agent Security](implement-sql-server-agent-security.md) and [Choose the Right SQL Server Agent Service Account for Multiserver Environments](choose-the-right-sql-server-agent-service-account-for-multiserver-environments.md).</span></span>  
  
##  <a name="using-sql-server-management-studio"></a><a name="SSMS"></a> <span data-ttu-id="af13c-119">Verwenden von SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="af13c-119">Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="af13c-120">**So erzwingen Sie, dass ein Zielserver den Masterserver abruft**</span><span class="sxs-lookup"><span data-stu-id="af13c-120">**To force a target server to poll the master server**</span></span>  
  
1.  <span data-ttu-id="af13c-121">Erweitern Sie im **Objekt-Explorer**den Masterserver.</span><span class="sxs-lookup"><span data-stu-id="af13c-121">In **Object Explorer**, expand the master server.</span></span>  
  
2.  <span data-ttu-id="af13c-122">Klicken Sie mit der rechten Maustaste auf **SQL Server-Agent**, zeigen Sie auf **Multiserververwaltung**, und klicken Sie dann auf **Zielserver verwalten**.</span><span class="sxs-lookup"><span data-stu-id="af13c-122">Right-click **SQL Server Agent**, point to **Multi Server Administration**, and then click **Manage Target Servers**.</span></span>  
  
3.  <span data-ttu-id="af13c-123">Klicken Sie auf einen Zielserver und dann auf **Abruf erzwingen**.</span><span class="sxs-lookup"><span data-stu-id="af13c-123">Click a target server, and then click **Force Poll**.</span></span>  
  
  
