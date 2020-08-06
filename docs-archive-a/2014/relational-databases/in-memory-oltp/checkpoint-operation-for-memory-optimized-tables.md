---
title: Prüfpunktvorgang für speicheroptimierte Tabellen
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: in-memory-oltp
ms.topic: conceptual
ms.assetid: 47975bd5-373f-43cd-946a-da8e8088b610
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 07560ea0bf147198fb759f6769ae1c6d5c68a71e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724694"
---
# <a name="checkpoint-operation-for-memory-optimized-tables"></a><span data-ttu-id="71133-102">Prüfpunktvorgang für speicheroptimierte Tabellen</span><span class="sxs-lookup"><span data-stu-id="71133-102">Checkpoint Operation for Memory-Optimized Tables</span></span>
  <span data-ttu-id="71133-103">Für speicheroptimierte Daten in Daten- und Änderungsdateien muss in regelmäßigen Abständen ein Prüfpunkt erstellt werden, um den aktiven Teil des Transaktionsprotokolls fortzuführen.</span><span class="sxs-lookup"><span data-stu-id="71133-103">A checkpoint needs to occur periodically for memory-optimized data in data and delta files to advance the active part of transaction log.</span></span> <span data-ttu-id="71133-104">Der Prüfpunkt ermöglicht die Wiederherstellung speicheroptimierter Tabellen am letzten erfolgreichen Prüfpunkt. Anschließend wird der aktive Teil des Transaktionsprotokolls angewendet, um die speicheroptimierten Tabellen zu aktualisieren und die Wiederherstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="71133-104">The checkpoint allows memory-optimized tables to restore or recover to the last successful checkpoint and then the active portion of transaction log is applied to update the memory-optimized tables to complete the recovery.</span></span> <span data-ttu-id="71133-105">Bei den Prüfpunktvorgängen für datenträgerbasierte und speicheroptimierte Tabellen handelt es sich um unterschiedliche Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="71133-105">The checkpoint operation for disk-based tables and memory-optimized tables are distinct operations.</span></span> <span data-ttu-id="71133-106">Im Folgenden werden verschiedene Szenarien und das Prüfpunktverhalten für datenträgerbasierte und speicheroptimierte Tabellen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="71133-106">The following describes different scenarios and the checkpoint behavior for disk-based and memory-optimized tables:</span></span>  
  
## <a name="manual-checkpoint"></a><span data-ttu-id="71133-107">Manueller Prüfpunkt</span><span class="sxs-lookup"><span data-stu-id="71133-107">Manual Checkpoint</span></span>  
 <span data-ttu-id="71133-108">Bei Ausgabe eines manuellen Prüfpunkts wird der Prüfpunkt sowohl für datenträgerbasierte als auch für speicheroptimierte Tabellen geschlossen.</span><span class="sxs-lookup"><span data-stu-id="71133-108">When you issue a manual checkpoint, it closes the checkpoint for both disk-based and memory-optimized tables.</span></span> <span data-ttu-id="71133-109">Die aktive Datendatei wird geschlossen, obwohl sie möglicherweise teilweise gefüllt ist.</span><span class="sxs-lookup"><span data-stu-id="71133-109">The active data file is closed even though it may be partially filled.</span></span>  
  
## <a name="automatic-checkpoint"></a><span data-ttu-id="71133-110">Automatischer Prüfpunkt</span><span class="sxs-lookup"><span data-stu-id="71133-110">Automatic Checkpoint</span></span>  
 <span data-ttu-id="71133-111">Automatische Prüfpunkte werden für datenträgerbasierte und speicheroptimierte Tabellen unterschiedlich implementiert, da die Beibehaltung der Daten sich bei diesen beiden Tabellentypen unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="71133-111">Automatic checkpoint is implemented differently for disk-based and memory-optimized tables because of the different ways the data is persisted.</span></span>  
  
 <span data-ttu-id="71133-112">Für datenträgerbasierte Tabellen wird ein automatischer Prüfpunkt basierend auf der Konfigurationsoption Wiederherstellungsintervall erstellt. (Weitere Informationen finden Sie unter [Ändern der Zielwiederherstellungszeit einer Datenbank &#40;SQL Server&#41;](../logs/change-the-target-recovery-time-of-a-database-sql-server.md).)</span><span class="sxs-lookup"><span data-stu-id="71133-112">For disk-based tables, an automatic checkpoint is taken based on the recovery interval configuration option (for more information, see [Change the Target Recovery Time of a Database &#40;SQL Server&#41;](../logs/change-the-target-recovery-time-of-a-database-sql-server.md)).</span></span>  
  
 <span data-ttu-id="71133-113">Bei Speicher optimierten Tabellen wird ein automatischer Prüfpunkt erstellt, wenn die Transaktionsprotokoll Datei seit dem letzten Prüfpunkt größer als 512 MB ist.</span><span class="sxs-lookup"><span data-stu-id="71133-113">For memory-optimized tables, an automatic checkpoint is taken when transaction log file becomes bigger than 512 MB since the last checkpoint.</span></span> <span data-ttu-id="71133-114">512 MB enthält Transaktionsprotokoll-Datensätze sowohl für Datenträger basierte als auch für Speicher optimierte Tabellen.</span><span class="sxs-lookup"><span data-stu-id="71133-114">512 MB includes transaction log records for both disk-based and memory-optimized tables.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="71133-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="71133-115">See Also</span></span>  
 [<span data-ttu-id="71133-116">Erstellen und Verwalten von Speicher für speicheroptimierte Objekte</span><span class="sxs-lookup"><span data-stu-id="71133-116">Creating and Managing Storage for Memory-Optimized Objects</span></span>](creating-and-managing-storage-for-memory-optimized-objects.md)  
  
  
