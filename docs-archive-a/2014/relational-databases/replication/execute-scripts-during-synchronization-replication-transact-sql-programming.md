---
title: Ausführen von Skripts während der Synchronisierung (Replikationsprogrammierung mit Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
dev_langs:
- TSQL
helpviewer_keywords:
- synchronization [SQL Server replication], scripts
- scripts [SQL Server replication], synchronization and
- sp_addscriptexec
ms.assetid: b58a0877-4e43-4fab-a281-24e6022d3fb1
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4bc217ad160a0238cc4247600d65eb32f156071f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609102"
---
# <a name="execute-scripts-during-synchronization-replication-transact-sql-programming"></a><span data-ttu-id="08c73-102">Ausführen von Skripts während der Synchronisierung (Replikationsprogrammierung mit Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="08c73-102">Execute Scripts During Synchronization (Replication Transact-SQL Programming)</span></span>
  <span data-ttu-id="08c73-103">Die Replikation unterstützt die bedarfsgesteuerte Ausführung von Skripts für Abonnenten von Transaktions- und Mergeveröffentlichungen.</span><span class="sxs-lookup"><span data-stu-id="08c73-103">Replication supports on demand script execution for Subscribers to transactional and merge publications.</span></span> <span data-ttu-id="08c73-104">Diese Funktionalität kopiert das Skript in das Replikationsarbeitsverzeichnis und wendet das Skript dann mithilfe von **sqlcmd** auf dem Abonnenten an.</span><span class="sxs-lookup"><span data-stu-id="08c73-104">This functionality copies the script to the replication working directory and then uses **sqlcmd** to apply the script at the Subscriber.</span></span> <span data-ttu-id="08c73-105">Standardmäßig wird der Verteilungs-Agent beendet, wenn beim Anwenden des Skripts auf ein Abonnement für eine Transaktionsveröffentlichung ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="08c73-105">By default, if there is a failure when applying the script for a subscription to a transactional publication, the Distribution Agent will stop.</span></span> <span data-ttu-id="08c73-106">Mithilfe von gespeicherten Replikationsprozeduren können Sie ein [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript angeben, das programmgesteuert ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="08c73-106">You can specify a [!INCLUDE[tsql](../../includes/tsql-md.md)] script to execute programmatically using replication stored procedures.</span></span>  
  
### <a name="to-specify-a-script-to-run-for-all-subscribers-to-a-snapshot-transactional-or-merge-publication"></a><span data-ttu-id="08c73-107">So geben Sie ein Skript an, das für alle Abonnenten einer Momentaufnahme-, Transaktions- oder Mergeveröffentlichung ausgeführt werden soll</span><span class="sxs-lookup"><span data-stu-id="08c73-107">To specify a script to run for all Subscribers to a snapshot, transactional or merge publication</span></span>  
  
1.  <span data-ttu-id="08c73-108">Erstellen und testen Sie das [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript, das bedarfsgesteuert ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="08c73-108">Compose and test the [!INCLUDE[tsql](../../includes/tsql-md.md)] script that will be executed on demand.</span></span>  
  
2.  <span data-ttu-id="08c73-109">Speichern Sie die Skriptdatei an einem Speicherort, auf den der Momentaufnahme-Agent für die Veröffentlichung zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="08c73-109">Save the script file to a location where it can be accessed by the Snapshot Agent for the publication.</span></span>  
  
3.  <span data-ttu-id="08c73-110">Führen Sie auf dem Verleger für die Veröffentlichungsdatenbank [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql) aus.</span><span class="sxs-lookup"><span data-stu-id="08c73-110">At the Publisher on the publication database, execute [sp_addscriptexec &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addscriptexec-transact-sql).</span></span> <span data-ttu-id="08c73-111">Geben Sie die \*\* \@ Veröffentlichung**, den Namen der Skriptdatei mit dem vollständigen UNC-Pfad, der in Schritt 2 für \*\* \@ scriptfile**erstellt wurde, und einen der folgenden Werte für " \*\* \@ SkipError\*\*" an:</span><span class="sxs-lookup"><span data-stu-id="08c73-111">Specify **\@publication**, the name of the script file with full UNC path created in step 2 for **\@scriptfile**, and one of the following values for **\@skiperror**:</span></span>  
  
    -   <span data-ttu-id="08c73-112">**0** &ndash; der Agent beendet die Ausführung des Skripts, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="08c73-112">**0** - the agent will stop executing the script if an error is encountered.</span></span>  
  
    -   <span data-ttu-id="08c73-113">**1** &ndash; der Agent protokolliert Fehler und setzt die Ausführung des Skripts fort, wenn Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="08c73-113">**1** - the agent will log errors and continue executing the script when errors are encountered.</span></span>  
  
4.  <span data-ttu-id="08c73-114">Das angegebene Skript wird auf jedem Abonnenten ausgeführt, wenn der Agent das nächste Mal zur Synchronisierung des Abonnements ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="08c73-114">The specified script will be executed at each Subscriber when the agent next runs to synchronize the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08c73-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="08c73-115">See Also</span></span>  
 [<span data-ttu-id="08c73-116">Synchronisieren von Daten</span><span class="sxs-lookup"><span data-stu-id="08c73-116">Synchronize Data</span></span>](synchronize-data.md)  
  
  
