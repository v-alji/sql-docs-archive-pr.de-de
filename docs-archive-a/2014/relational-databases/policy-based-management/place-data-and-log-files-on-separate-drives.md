---
title: Platzieren von Daten- und Protokolldateien auf separaten Laufwerken | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 6cbedc27-4d77-44ad-bed2-c23b628475a7
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: d3f972ea29322a046c09657e2ed2499655c82aed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619768"
---
# <a name="place-data-and-log-files-on-separate-drives"></a><span data-ttu-id="b6856-102">Platzieren von Daten- und Protokolldateien auf separaten Laufwerken</span><span class="sxs-lookup"><span data-stu-id="b6856-102">Place Data and Log Files on Separate Drives</span></span>
  <span data-ttu-id="b6856-103">Diese Regel überprüft, ob Daten- und Protokolldateien auf separaten logischen Laufwerken platziert werden.</span><span class="sxs-lookup"><span data-stu-id="b6856-103">This rule checks whether data and log files are placed on separate logical drives.</span></span> <span data-ttu-id="b6856-104">Wenn Daten- und Protokolldateien auf demselben Gerät platziert werden, können bei diesem Gerät Konflikte und eine schlechte Leistung die Folge sein.</span><span class="sxs-lookup"><span data-stu-id="b6856-104">Placing both data and log files on the same device can cause contention for that device and result in poor performance.</span></span> <span data-ttu-id="b6856-105">Wenn die Dateien auf separaten Laufwerken platziert werden, kann die E/A-Aktivität sowohl für die Daten- als auch die Protokolldateien gleichzeitig stattfinden.</span><span class="sxs-lookup"><span data-stu-id="b6856-105">Placing the files on separate drives allows the I/O activity to occur at the same time for both the data and log files.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="b6856-106">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="b6856-106">Best Practices Recommendations</span></span>  
 <span data-ttu-id="b6856-107">Wenn Sie eine neue Datenbank erstellen, geben Sie separate Laufwerke für die Daten und das Protokoll an.</span><span class="sxs-lookup"><span data-stu-id="b6856-107">When you create a new database, specify separate drives for the data and log.</span></span> <span data-ttu-id="b6856-108">Die Datenbank muss offline geschaltet werden, um Dateien nach Erstellen der Datenbank zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="b6856-108">To move files after the database is created, the database must be taken offline.</span></span> <span data-ttu-id="b6856-109">Verschieben Sie die Dateien mithilfe einer der folgenden Methoden:</span><span class="sxs-lookup"><span data-stu-id="b6856-109">Move the files by using one of the following methods:</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b6856-110">Diese Richtlinie kann separate physische Geräte nicht durch Einbindungspunkte erkennen.</span><span class="sxs-lookup"><span data-stu-id="b6856-110">This policy cannot detect separate physical devices through mount points</span></span>  
  
-   <span data-ttu-id="b6856-111">Stellen Sie die Datenbank über die Sicherung wieder her. Verwenden Sie dazu die RESTORE DATABASE-Anweisung mit der WITH MOVE-Option.</span><span class="sxs-lookup"><span data-stu-id="b6856-111">Restore the database from backup by using the RESTORE DATABASE statement with the WITH MOVE option.</span></span>  
  
-   <span data-ttu-id="b6856-112">Trennen Sie die Datenbank, und fügen Sie sie anschließend wieder an. Geben Sie dabei separate Speicherorte für das Daten- und das Protokollgerät an.</span><span class="sxs-lookup"><span data-stu-id="b6856-112">Detach and then attach the database specifying separate locations for the data and log devices.</span></span>  
  
-   <span data-ttu-id="b6856-113">Geben Sie einen neuen Speicherort an. Führen Sie dazu die ALTER DATABASE-Anweisung mit der MODIFY FILE-Option aus, und starten Sie die Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]neu.</span><span class="sxs-lookup"><span data-stu-id="b6856-113">Specify a new location by running the ALTER DATABASE statement with the MODIFY FILE option, and then restarting the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="b6856-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6856-114">For More Information</span></span>  
 [<span data-ttu-id="b6856-115">Verschieben von Datenbankdateien</span><span class="sxs-lookup"><span data-stu-id="b6856-115">Move Database Files</span></span>](../databases/move-database-files.md)  
  
 [<span data-ttu-id="b6856-116">Verschieben von Benutzerdatenbanken</span><span class="sxs-lookup"><span data-stu-id="b6856-116">Move User Databases</span></span>](../databases/move-user-databases.md)  
  
 [<span data-ttu-id="b6856-117">Anfügen und Trennen von Datenbanken &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b6856-117">Database Detach and Attach &#40;SQL Server&#41;</span></span>](../databases/database-detach-and-attach-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="b6856-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6856-118">See Also</span></span>  
 [<span data-ttu-id="b6856-119">Überwachen und Erzwingen von Best Practices mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="b6856-119">Monitor and Enforce Best Practices by Using Policy-Based Management</span></span>](monitor-and-enforce-best-practices-by-using-policy-based-management.md)  
  
  
