---
title: Überprüfen des Datenträger Eingabe-Ausgabe Subsystems auf Lese Wiederholungs Probleme | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: cedf4097-5b73-4964-9935-74a101847019
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 19809b1554e435600eb4eeae424bed17dc27bdbb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695586"
---
# <a name="check-disk-input-output-subsystem-for-read-retry-problems"></a><span data-ttu-id="879bf-102">Überprüfen des Datenträger-E/A-Subsystems auf Lesewiederholungsprobleme</span><span class="sxs-lookup"><span data-stu-id="879bf-102">Check Disk Input Output Subsystem for Read Retry Problems</span></span>
  <span data-ttu-id="879bf-103">Diese Regel überprüft das Ereignisprotokoll auf die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Fehlermeldung 825.</span><span class="sxs-lookup"><span data-stu-id="879bf-103">This rule checks the event log for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error message 825.</span></span> <span data-ttu-id="879bf-104">Mit dieser Meldung wird angegeben, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] beim ersten Versuch keine Daten vom Datenträger lesen konnte.</span><span class="sxs-lookup"><span data-stu-id="879bf-104">This message indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] was unable to read data from the disk on the first try.</span></span> <span data-ttu-id="879bf-105">Diese Meldung weist auf ein größeres Problem mit dem E/A-Subsystem des Datenträgers hin.</span><span class="sxs-lookup"><span data-stu-id="879bf-105">This message indicates a major problem with the disk I/O subsystem.</span></span> <span data-ttu-id="879bf-106">Diese Meldung deutet aktuell nicht auf ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Problem hin.</span><span class="sxs-lookup"><span data-stu-id="879bf-106">This message does not currently indicate a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] problem.</span></span> <span data-ttu-id="879bf-107">Durch das Datenträgerproblem werden jedoch möglicherweise Datenverluste oder Beschädigungen der Datenbank verursacht, wenn es nicht behoben wird.</span><span class="sxs-lookup"><span data-stu-id="879bf-107">However, the disk problem could cause data loss or database corruption if it is not resolved.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="879bf-108">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="879bf-108">Best Practices Recommendations</span></span>  
 <span data-ttu-id="879bf-109">Mit den folgenden Aktionen können Sie das zugrunde liegende Hardwareproblem möglicherweise ermitteln und lösen:</span><span class="sxs-lookup"><span data-stu-id="879bf-109">The following actions might help you discover and resolve the underlying hardware problem:</span></span>  
  
-   <span data-ttu-id="879bf-110">Beachten Sie das Fehlerprotokoll und den jeweiligen Text in dieser Meldung, um Informationen zu den Ursachen für das Problem zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="879bf-110">Review the error log and the variable text in this message for clues that explain the problem.</span></span>  
  
-   <span data-ttu-id="879bf-111">Prüfen Sie das Datenträgersystem.</span><span class="sxs-lookup"><span data-stu-id="879bf-111">Check the disk system.</span></span> <span data-ttu-id="879bf-112">Das Problem ist möglicherweise auf die Datenträger, Datenträgercontroller, Arraykarten oder Datenträgertreiber zurückzuführen.</span><span class="sxs-lookup"><span data-stu-id="879bf-112">The problem could be related to the disks, the disk controllers, array cards, or disk drivers.</span></span>  
  
-   <span data-ttu-id="879bf-113">Die neuesten Hilfsprogramme zum Überprüfen des Status des Datenträgersystems erhalten Sie beim Hersteller des Datenträgers.</span><span class="sxs-lookup"><span data-stu-id="879bf-113">Contact the disk manufacturer for the latest utilities for checking the status of the disk system.</span></span>  
  
-   <span data-ttu-id="879bf-114">Wenden Sie sich an den Hersteller des Datenträgers, um die neuesten Treiberupdates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="879bf-114">Contact the disk manufacturer for the latest driver updates.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="879bf-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="879bf-115">For More Information</span></span>  
 [<span data-ttu-id="879bf-116">MSSQLSERVER_825</span><span class="sxs-lookup"><span data-stu-id="879bf-116">MSSQLSERVER_825</span></span>](../errors-events/mssqlserver-825-database-engine-error.md)  
  
 <span data-ttu-id="879bf-117">[SQL Server I/O Basics, Chapter 2 (in Englisch)](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="879bf-117">[SQL Server I/O Basics, Chapter 2](/previous-versions/sql/sql-server-2005/administrator/cc917726(v=technet.10))</span></span>  
  
  
