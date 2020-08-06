---
title: Datenbank wiederherstellen (Dialog Feld) (Analysis Services Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.sqlserverstudio.Restore.f1
ms.assetid: a3990d47-55e2-424e-8eac-87edc937e806
author: minewiskan
ms.author: owend
ms.openlocfilehash: f45a41eb10e81e1cfe1100045cc4d00353cb11fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727206"
---
# <a name="restore-database-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="e90ef-102">Dialogfeld Datenbank wiederherstellen (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="e90ef-102">Restore Database Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="e90ef-103">Im Dialogfeld **Datenbank wiederherstellen** von [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] können Sie eine Datenbank von [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] aus einer Sicherungsdatei wiederherstellen, die im [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -eigenen Format für Sicherungsdateien (\*.abf) erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="e90ef-103">Use the **Restore Database** dialog box in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] to restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database from a backup file using the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] Backup File (.abf) format.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e90ef-104">Für jede Sicherungsdatei muss der Benutzer, der den Wiederherstellungsbefehl ausführt, über die Berechtigung zum Lesen von dem für jede Datei angegebenen Sicherungsspeicherort verfügen.</span><span class="sxs-lookup"><span data-stu-id="e90ef-104">For each backup file, the user who runs the restore command must have permission to read from the backup location specified for each file.</span></span> <span data-ttu-id="e90ef-105">Zum Wiederherstellen einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank, die nicht auf dem Server installiert ist, muss der Benutzer zusätzlich Mitglied der Serverrolle für die betreffende [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz sein.</span><span class="sxs-lookup"><span data-stu-id="e90ef-105">To restore an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database that is not installed on the server, the user must also be a member of the server role for that [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance.</span></span> <span data-ttu-id="e90ef-106">Zum Überschreiben einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank muss der Benutzer entweder Mitglied der Serverrolle für die [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz oder Mitglied einer Datenbankrolle mit der Berechtigung „Vollzugriff“ (Administrator) für die wiederherzustellende Datenbank sein.</span><span class="sxs-lookup"><span data-stu-id="e90ef-106">To overwrite an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database, the user must have one of the following roles: a member of the server role for the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance, or a member of a database role with Full Control (Administrator) permissions on the database to be restored.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e90ef-107">Nach dem Wiederherstellen einer vorhandenen Datenbank verliert der Benutzer, der die Datenbank wiederhergestellt hat, möglicherweise den Zugriff auf diese Datenbank.</span><span class="sxs-lookup"><span data-stu-id="e90ef-107">After restoring an existing database, the user who restored the database might lose access to the restored database.</span></span> <span data-ttu-id="e90ef-108">Dies ist u. U. der Fall, wenn der Benutzer zum Zeitpunkt der Sicherung kein Mitglied der Serverrolle oder der Datenbankrolle mit der Berechtigung "Vollzugriff (Administrator)" war.</span><span class="sxs-lookup"><span data-stu-id="e90ef-108">This loss of access can occur if, at the time that the backup was performed, the user was not a member of the server role or was not a member of the database role with Full Control (Administrator) permissions.</span></span>  
  
 <span data-ttu-id="e90ef-109">**So zeigen Sie das Dialogfeld Datenbank wiederherstellen an**</span><span class="sxs-lookup"><span data-stu-id="e90ef-109">**To display the Restore Database dialog box**</span></span>  
  
-   <span data-ttu-id="e90ef-110">Klicken Sie in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]mit der rechten Maustaste entweder auf den Ordner **Datenbanken** einer [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Instanz oder auf eine Datenbank im **Objekt-Explorer**, und klicken Sie anschließend auf **Wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="e90ef-110">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], right-click either the **Databases** folder of an [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] instance or a database in **Object Explorer**, and then click **Restore**.</span></span>  
  
 <span data-ttu-id="e90ef-111">Das Dialogfeld **Datenbank wiederherstellen** enthält die folgenden Seiten.</span><span class="sxs-lookup"><span data-stu-id="e90ef-111">The **Restore Database** dialog box contains the following pages.</span></span>  
  
## <a name="pages"></a><span data-ttu-id="e90ef-112">Seiten</span><span class="sxs-lookup"><span data-stu-id="e90ef-112">Pages</span></span>  
 <span data-ttu-id="e90ef-113">**Allgemein**</span><span class="sxs-lookup"><span data-stu-id="e90ef-113">**General**</span></span>  
 <span data-ttu-id="e90ef-114">Auf dieser Seite können Sie die wiederherzustellende Datenbank auswählen sowie die Sicherungsdatei, aus der die Datenbank wiederhergestellt werden soll. Darüber hinaus können Sie einige allgemeine Optionen und das Kennwort festlegen, das beim Wiederherstellen der Datenbank verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e90ef-114">Use this page to select the database to restore, the backup file from which to restore the database, as well as the general options and password to use while restoring the database.</span></span> <span data-ttu-id="e90ef-115">Weitere Informationen zu dieser Seite finden Sie unter [Allgemein &#40;Dialogfeld „Datenbank wiederherstellen“, Analysis Services – mehrdimensionale Daten&#41;](general-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e90ef-115">For more information about this page, see [General &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](general-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
 <span data-ttu-id="e90ef-116">**Partitionen**</span><span class="sxs-lookup"><span data-stu-id="e90ef-116">**Partitions**</span></span>  
 <span data-ttu-id="e90ef-117">Mithilfe dieser Seite können Sie lokale Partitionen an angegebenen Speicherorten wiederherstellen und Remotepartitionen aus Remotesicherungsdateien wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="e90ef-117">Use this page to restore local partitions to specified locations, and to restore remote partitions from remote backup files.</span></span> <span data-ttu-id="e90ef-118">Weitere Informationen zu dieser Seite finden Sie unter [Partitionen &#40;Dialogfeld „Datenbank wiederherstellen“, Analysis Services – mehrdimensionale Daten&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span><span class="sxs-lookup"><span data-stu-id="e90ef-118">For more information about this page, see [Partitions &#40;Restore Database Dialog Box&#41; &#40;Analysis Services - Multidimensional Data&#41;](partitions-restore-database-dialog-box-analysis-services-multidimensional-data.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e90ef-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e90ef-119">See Also</span></span>  
 <span data-ttu-id="e90ef-120">[Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="e90ef-120">[Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;](analysis-services-designers-and-dialog-boxes-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="e90ef-121">Sichern und Wiederherstellen von Analysis Services-Datenbanken</span><span class="sxs-lookup"><span data-stu-id="e90ef-121">Backup and Restore of Analysis Services Databases</span></span>](multidimensional-models/backup-and-restore-of-analysis-services-databases.md)  
  
  
