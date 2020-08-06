---
title: SQL-Skript generieren (Replikationsobjekte) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.generatesqlscript.f1
helpviewer_keywords:
- Generate SQL Script dialog box
ms.assetid: b7ccc34e-1c22-44b8-8eb5-f6423af3164e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 31a4b318eb3a4c0e5d9f79f43efdcf97c42957f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609089"
---
# <a name="generate-sql-script-replication-objects"></a><span data-ttu-id="eff77-102">SQL-Skript generieren (Replikationsobjekte)</span><span class="sxs-lookup"><span data-stu-id="eff77-102">Generate SQL Script (Replication Objects)</span></span>
  <span data-ttu-id="eff77-103">Ein Replikationsskript enthält die gespeicherten [!INCLUDE[tsql](../../includes/tsql-md.md)] -Systemprozeduren, die zur Implementierung der Replikationskomponenten, für die Skripts erstellt wurden, erforderlich sind. Dazu gehören eine Veröffentlichung oder ein Abonnement.</span><span class="sxs-lookup"><span data-stu-id="eff77-103">A replication script contains the [!INCLUDE[tsql](../../includes/tsql-md.md)] system stored procedures necessary to implement the replication components scripted, such as a publication or subscription.</span></span> <span data-ttu-id="eff77-104">Für die Replikationskomponenten in einer Topologie sollten im Rahmen des Plans zur Wiederherstellung im Notfall Skripts erstellt werden; diese können dann auch zur Automatisierung sich wiederholender Tasks verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eff77-104">All replication components in a topology should be scripted as part of a disaster recovery plan, and scripts can also be used to automate repetitive tasks.</span></span> <span data-ttu-id="eff77-105">Die Replikation stellt zum Erstellen von Skripts für Replikationsobjekte zwei Dialogfelder bereit:</span><span class="sxs-lookup"><span data-stu-id="eff77-105">Replication offers two dialog boxes for scripting replication objects:</span></span>  
  
-   <span data-ttu-id="eff77-106">**SQL-Skript generieren:** Dieses Dialogfeld kann über das Kontextmenü des Ordners **Replikation** sowie über alle untergeordneten Ordner in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="eff77-106">**Generate SQL Script**, which is available from the context menu of the **Replication** folder and all subfolders in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="eff77-107">Mithilfe dieses Dialogfelds können Sie Skripts für alle Replikationsobjekte einer Instanz von [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erstellen.</span><span class="sxs-lookup"><span data-stu-id="eff77-107">This dialog box allows you to script all replication objects on an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="eff77-108">**SQL-Skript generieren\<ObjectName>** : Dieses Dialogfeld kann über das Kontextmenü für Veröffentlichungen und Abonnements aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="eff77-108">**Generate SQL Script \<ObjectName>**, which is available from the context menu for publications and subscriptions.</span></span> <span data-ttu-id="eff77-109">Mithilfe dieses Dialogfelds können Sie Skripts für einzelne Objekte erstellen.</span><span class="sxs-lookup"><span data-stu-id="eff77-109">This dialog box allows you to script individual objects.</span></span>  
  
 <span data-ttu-id="eff77-110">In diesen Dialogfeldern werden Skripts für Objekte einer einzelnen Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]erstellt; es werden keine Verbindungen mit anderen Instanzen hergestellt, um Skripts für verknüpfte Objekte zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eff77-110">These dialog boxes script objects on a single instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; they do not connect to other instances to script related objects.</span></span>  
  
## <a name="generate-sql-script-options"></a><span data-ttu-id="eff77-111">SQL-Skript generieren (Optionen)</span><span class="sxs-lookup"><span data-stu-id="eff77-111">Generate SQL Script Options</span></span>  
 <span data-ttu-id="eff77-112">**Verteilereigenschaften**</span><span class="sxs-lookup"><span data-stu-id="eff77-112">**Distributor properties**</span></span>  
 <span data-ttu-id="eff77-113">Wählen Sie diese Option aus, um Skripts für gespeicherte Prozeduren zu erstellen, um: den Verteiler aktivieren oder deaktivieren, mit dem Verteiler verknüpfte Verleger hinzufügen oder löschen sowie die Verteilungsdatenbank erstellen oder löschen zu können.</span><span class="sxs-lookup"><span data-stu-id="eff77-113">Select to script stored procedures to: enable or disable the Distributor; add or drop Publishers associated with the Distributor; and create or drop the distribution database.</span></span>  
  
 <span data-ttu-id="eff77-114">**Veröffentlichungen in den folgenden Datenquellen**</span><span class="sxs-lookup"><span data-stu-id="eff77-114">**Publications in the following data sources**</span></span>  
 <span data-ttu-id="eff77-115">Wählen Sie diese Option aus, um Skripts für gespeicherte Prozeduren zu erstellen, um: die Veröffentlichung aktivieren oder deaktivieren sowie Veröffentlichungen, Artikel, Pushabonnements und Replikationsaufträge erstellen oder löschen zu können.</span><span class="sxs-lookup"><span data-stu-id="eff77-115">Select to script stored procedures to: enable or disable publishing; and create or drop publications, articles, push subscriptions, and replication jobs.</span></span>  
  
 <span data-ttu-id="eff77-116">**Abonnements in den folgenden Datenquellen**</span><span class="sxs-lookup"><span data-stu-id="eff77-116">**Subscriptions in the following data sources**</span></span>  
 <span data-ttu-id="eff77-117">Durch Auswählen dieser Option können Sie Skripts für gespeicherte Prozeduren erstellen, um Pullabonnements und Replikationsaufträge zu erstellen oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="eff77-117">Select to script stored procedures to create or drop pull subscriptions and replication jobs.</span></span>  
  
 <span data-ttu-id="eff77-118">**Um Komponenten zu erstellen oder zu aktivieren** und **Um Komponenten zu löschen oder zu deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="eff77-118">**To create or enable the components** and **To drop or disable the components**</span></span>  
 <span data-ttu-id="eff77-119">Geben Sie an, ob das Skript Befehle zum Erstellen oder Löschen eines Replikationsobjekts enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="eff77-119">Specify whether the script should include commands for creating or dropping a replication object.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="eff77-120">empfiehlt, das Dialogfeld zu verwenden, um eine Reihe von Skripts zum Aktivieren und Deaktivieren von Komponenten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eff77-120">recommends that you use the dialog box to create a set of scripts for enabling and disabling components.</span></span>  
  
 <span data-ttu-id="eff77-121">**Replikationsaufträge**</span><span class="sxs-lookup"><span data-stu-id="eff77-121">**Replication jobs**</span></span>  
 <span data-ttu-id="eff77-122">Wählen Sie diese Option aus, um neben Skripts für Aufrufe gespeicherter Prozeduren auch Skripts für Replikationsaufträge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eff77-122">Select to script replication jobs in addition to stored procedure calls.</span></span> <span data-ttu-id="eff77-123">Diese Option ist nur verfügbar, wenn Skripts von einem Verteiler aus erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="eff77-123">This option is available only when scripting from a Distributor.</span></span>  
  
 <span data-ttu-id="eff77-124">Bei der Ausführung gespeicherter Replikationsprozeduren werden die erforderlichen Aufträge erstellt, d. h., die Option muss nicht ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="eff77-124">Replication stored procedures create the necessary jobs when they are executed, so it is not required to select this option.</span></span> <span data-ttu-id="eff77-125">Einen Datensatz mit den erstellten Aufträgen zur Verfügung zu haben, kann sich jedoch als nützlich erweisen, falls ein einzelner Auftrag erneut erstellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="eff77-125">However, it can be useful to have a record of the jobs created in case an individual job must be recreated.</span></span>  
  
## <a name="generate-sql-script-objectname-options"></a><span data-ttu-id="eff77-126">SQL-Skript generieren – Optionen für \<ObjectName></span><span class="sxs-lookup"><span data-stu-id="eff77-126">Generate SQL Script \<ObjectName> Options</span></span>  
 <span data-ttu-id="eff77-127">**Um Komponenten zu erstellen oder zu aktivieren** und **Um Komponenten zu löschen oder zu deaktivieren**</span><span class="sxs-lookup"><span data-stu-id="eff77-127">**To create or enable the components** and **To drop or disable the components**</span></span>  
 <span data-ttu-id="eff77-128">Geben Sie an, ob das Skript Befehle zum Erstellen oder Löschen eines Replikationsobjekts enthalten soll.</span><span class="sxs-lookup"><span data-stu-id="eff77-128">Specify whether the script should include commands for creating or dropping a replication object.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="eff77-129">empfiehlt, das Dialogfeld zu verwenden, um eine Reihe von Skripts zum Aktivieren und Deaktivieren von Komponenten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eff77-129">recommends that you use the dialog box, creating a set of scripts for enabling and disabling components.</span></span>  
  
 <span data-ttu-id="eff77-130">**Replikationsaufträge**</span><span class="sxs-lookup"><span data-stu-id="eff77-130">**Replication jobs**</span></span>  
 <span data-ttu-id="eff77-131">Auf diese Option kann im Dialogfeld **SQL-Skript generieren** zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="eff77-131">This option is available only from the **Generate SQL Script** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eff77-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eff77-132">See Also</span></span>  
 [<span data-ttu-id="eff77-133">Erstellen von Skripts für die Replikation</span><span class="sxs-lookup"><span data-stu-id="eff77-133">Scripting Replication</span></span>](scripting-replication.md)  
  
  
