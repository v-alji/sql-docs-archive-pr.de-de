---
title: Aktivieren der Initialisierung mit einer Sicherung für Transaktions Veröffentlichungen (SQL Server Management Studio) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- manual subscription initialization [SQL Server replication]
- subscriptions [SQL Server replication], initializing
- initializing subscriptions [SQL Server replication], without snapshots
- transactional replication, backup and restore
- backups [SQL Server replication], transactional replication
ms.assetid: 9df00514-aa9d-4ac6-9766-d226c9958175
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: f5e22614c8c4f5250db3966e747b686091512774
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609107"
---
# <a name="enable-initialization-with-a-backup-for-transactional-publications-sql-server-management-studio"></a><span data-ttu-id="b5ccb-102">Aktivieren der Initialisierung von einer Sicherung für Transaktionsveröffentlichungen (SQL Server Management Studio)</span><span class="sxs-lookup"><span data-stu-id="b5ccb-102">Enable Initialization with a Backup for Transactional Publications (SQL Server Management Studio)</span></span>
  <span data-ttu-id="b5ccb-103">Wenn Sie ein Abonnement für eine Transaktionsveröffentlichung von einer Sicherung initialisieren möchten, aktivieren Sie die Veröffentlichung, um das Initialisieren von einer Sicherung zuzulassen. Geben Sie dann beim Erstellen des Abonnements die Sicherungsinformationen ein:</span><span class="sxs-lookup"><span data-stu-id="b5ccb-103">To initialize a subscription to a transactional publication from a backup, enable the publication to allow initialization from a backup, and then specify backup information when creating the subscription:</span></span>  
  
-   <span data-ttu-id="b5ccb-104">Aktivieren Sie die Veröffentlichung auf der Seite **Abonnementoptionen** im Dialogfeld **Veröffentlichungseigenschaften - \<Publication>** .</span><span class="sxs-lookup"><span data-stu-id="b5ccb-104">Enable the publication on the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box.</span></span> <span data-ttu-id="b5ccb-105">Weitere Informationen zum Zugreifen auf dieses Dialogfeld finden Sie unter [View and Modify Publication Properties](publish/view-and-modify-publication-properties.md).</span><span class="sxs-lookup"><span data-stu-id="b5ccb-105">For more information about accessing this dialog box, see [View and Modify Publication Properties](publish/view-and-modify-publication-properties.md).</span></span>  
  
-   <span data-ttu-id="b5ccb-106">Geben Sie mit der gespeicherten Prozedur [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql) Sicherungsinformationen an.</span><span class="sxs-lookup"><span data-stu-id="b5ccb-106">Specify backup information with the stored procedure [sp_addsubscription &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addsubscription-transact-sql).</span></span> <span data-ttu-id="b5ccb-107">Weitere Informationen zu den für **sp_addsubscription** erforderlichen Parametern finden Sie unter [Initialisieren eines Transaktionsabonnements von einer Sicherung &#40;Replikationsprogrammierung mit Transact-SQL&#41;](initialize-a-transactional-subscription-from-a-backup.md).</span><span class="sxs-lookup"><span data-stu-id="b5ccb-107">For more information about the parameters required by **sp_addsubscription**, see [Initialize a Transactional Subscription from a Backup &#40;Replication Transact-SQL Programming&#41;](initialize-a-transactional-subscription-from-a-backup.md).</span></span>  
  
### <a name="to-enable-initialization-with-a-backup"></a><span data-ttu-id="b5ccb-108">So aktivieren Sie die Initialisierung mit einer Sicherung</span><span class="sxs-lookup"><span data-stu-id="b5ccb-108">To enable initialization with a backup</span></span>  
  
1.  <span data-ttu-id="b5ccb-109">Wählen Sie auf der Seite **Abonnementoptionen** im Dialogfeld **Veröffentlichungseigenschaften - \<Publication>** für die Option **Initialisierung aus Sicherungsdateien zulassen** den Wert **Wahr** aus.</span><span class="sxs-lookup"><span data-stu-id="b5ccb-109">On the **Subscription Options** page of the **Publication Properties - \<Publication>** dialog box, select a value of **True** for the **Allow initialization from backup files** option.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b5ccb-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b5ccb-110">See Also</span></span>  
 [<span data-ttu-id="b5ccb-111">Initialisieren eines Transaktionsabonnements ohne Momentaufnahme</span><span class="sxs-lookup"><span data-stu-id="b5ccb-111">Initialize a Transactional Subscription Without a Snapshot</span></span>](initialize-a-transactional-subscription-without-a-snapshot.md)  
  
  
