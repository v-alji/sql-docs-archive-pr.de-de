---
title: Verteilungsdatenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configuredistributionwizard.distributiondatabase.f1
ms.assetid: 5b42a083-7a11-41d8-9e3f-320c7c907237
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: d98a80be52ae77cbdaf1581a5b3397f9d11af4fb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609124"
---
# <a name="distribution-database"></a><span data-ttu-id="c516f-102">Verteilungsdatenbank</span><span class="sxs-lookup"><span data-stu-id="c516f-102">Distribution Database</span></span>
  <span data-ttu-id="c516f-103">Die Verteilungsdatenbank speichert Metadaten und Verlaufsdaten für alle Replikationstypen und Transaktionen für die Transaktionsreplikation.</span><span class="sxs-lookup"><span data-stu-id="c516f-103">The distribution database stores metadata and history data for all types of replication, and transactions for transactional replication.</span></span>  
  
 <span data-ttu-id="c516f-104">In vielen Fällen reicht eine Verteilungsdatenbank aus.</span><span class="sxs-lookup"><span data-stu-id="c516f-104">In many cases, a single distribution database is sufficient.</span></span> <span data-ttu-id="c516f-105">Wenn jedoch mehrere Verleger einen Verteiler verwenden, sollten Sie die Erstellung einer Verteilungsdatenbank für jeden Verleger in Betracht ziehen.</span><span class="sxs-lookup"><span data-stu-id="c516f-105">However, if multiple Publishers use a single Distributor, consider creating a distribution database for each Publisher.</span></span> <span data-ttu-id="c516f-106">Auf diese Weise stellen Sie sicher, dass die durch jede Verteilungsdatenbank fließenden Daten eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="c516f-106">Doing so ensures that the data flowing through each distribution database is distinct.</span></span> <span data-ttu-id="c516f-107">Mit dem Verteilungskonfigurations-Assistenten können Sie eine Verteilungsdatenbank für den Verteiler angeben.</span><span class="sxs-lookup"><span data-stu-id="c516f-107">You can specify one distribution database for the Distributor using the Configure Distribution Wizard.</span></span> <span data-ttu-id="c516f-108">Geben Sie bei Bedarf im Dialogfeld **Verteilereigenschaften** weitere Verteilungsdatenbanken an.</span><span class="sxs-lookup"><span data-stu-id="c516f-108">If necessary, specify additional distribution databases in the **Distributor Properties** dialog box.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c516f-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c516f-109">Options</span></span>  
 <span data-ttu-id="c516f-110">**Name der Verteilungsdatenbank**</span><span class="sxs-lookup"><span data-stu-id="c516f-110">**Distribution database name**</span></span>  
 <span data-ttu-id="c516f-111">Geben Sie einen Namen für die Verteilungsdatenbank ein.</span><span class="sxs-lookup"><span data-stu-id="c516f-111">Enter a name for the distribution database.</span></span> <span data-ttu-id="c516f-112">Der Standardname für die Verteilungsdatenbank lautet 'distribution'.</span><span class="sxs-lookup"><span data-stu-id="c516f-112">The default name for the distribution database is 'distribution'.</span></span> <span data-ttu-id="c516f-113">Wenn Sie einen Namen angeben, darf dieser maximal 128 Zeichen umfassen, und es muss sich um einen innerhalb der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Instanz eindeutigen Namen handeln, der den Regeln für Bezeichner entspricht.</span><span class="sxs-lookup"><span data-stu-id="c516f-113">If you specify a name, the name can be a maximum of 128 characters, must be unique within an instance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], and must conform to the rules for identifiers.</span></span> <span data-ttu-id="c516f-114">Weitere Informationen finden Sie unter [Datenbankbezeichner](../databases/database-identifiers.md).</span><span class="sxs-lookup"><span data-stu-id="c516f-114">For more information, see [Database Identifiers](../databases/database-identifiers.md).</span></span>  
  
 <span data-ttu-id="c516f-115">**Ordner für die Verteilungs-Datenbankdatei** und **Ordner für die Verteilungsdatenbank-Protokolldatei**</span><span class="sxs-lookup"><span data-stu-id="c516f-115">**Folder for the distribution database file** and **Folder for the distribution database log file**</span></span>  
 <span data-ttu-id="c516f-116">Geben Sie den Pfad für die Verteilungsdatenbank und die Protokolldateien ein.</span><span class="sxs-lookup"><span data-stu-id="c516f-116">Enter the path for the distribution database and log files.</span></span> <span data-ttu-id="c516f-117">Pfade müssen auf Datenträger verweisen, die für den Verteiler lokal sind, und mit einem lokalen Laufwerkbuchstaben und Doppelpunkt (z. B. C:) beginnen.</span><span class="sxs-lookup"><span data-stu-id="c516f-117">Paths must refer to disks that are local to the Distributor and begin with a local drive letter and colon (for example, C:).</span></span> <span data-ttu-id="c516f-118">Zugeordnete Laufwerkbuchstaben und Netzwerkpfade sind ungültig.</span><span class="sxs-lookup"><span data-stu-id="c516f-118">Mapped drive letters and network paths are not valid.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c516f-119">Sie können Schreibvorgänge für Transaktionen beschleunigen und die Replikationsleistung verbessern, indem Sie das Verteilungsdatenbankprotokoll nicht auf dem gleichen Datenträger wie die Verteilungsdatenbank speichern.</span><span class="sxs-lookup"><span data-stu-id="c516f-119">You can decrease the time it takes to write transactions and improve the performance of replication by placing the distribution database log on a separate disk drive from the distribution database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c516f-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c516f-120">See Also</span></span>  
 <span data-ttu-id="c516f-121">[Verteilung konfigurieren](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="c516f-121">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="c516f-122">[Konfigurieren der Veröffentlichung und der Verteilung](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="c516f-122">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 [<span data-ttu-id="c516f-123">Anzeigen und Ändern der Verteiler- und Verlegereigenschaften</span><span class="sxs-lookup"><span data-stu-id="c516f-123">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)  
  
  
