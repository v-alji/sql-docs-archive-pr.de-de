---
title: Momentaufnahmeordner | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/30/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.replicationutilities.specifysnapshotfolder.f1
ms.assetid: 3eb1b73f-ddb3-4d09-be6e-811c414698e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 48b490c65662edf65018e98dd1bc3339f6aae6b6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622536"
---
# <a name="snapshot-folder"></a><span data-ttu-id="f5c04-102">Momentaufnahmeordner</span><span class="sxs-lookup"><span data-stu-id="f5c04-102">Snapshot Folder</span></span>
  <span data-ttu-id="f5c04-103">Die Seite **Momentaufnahmeordner** wird im Verteilungskonfigurations-Assistenten und im Assistenten für neue Veröffentlichung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5c04-103">The **Snapshot Folder** page appears in the Configure Distribution Wizard and in the New Publication Wizard.</span></span> <span data-ttu-id="f5c04-104">Der von Ihnen für den Momentaufnahmeordner angegebene Speicherort wird als Standardvorgabe für alle in diesem Assistenten aktivierten Verleger verwendet (der standardmäßige Momentaufnahmeordner gilt nicht für Verleger, die später mithilfe des Dialogfelds **Verteilereigenschaften** aktiviert werden).</span><span class="sxs-lookup"><span data-stu-id="f5c04-104">The location you specify for the snapshot folder will be used as the default for all Publishers enabled in this wizard (the default snapshot folder does not apply to Publishers that are later enabled using the **Distributor Properties** dialog box).</span></span> <span data-ttu-id="f5c04-105">Sie können diese Standardeinstellung für jeden Verleger auf der Seite **Verleger** des Verteilungskonfigurations-Assistenten oder im Dialogfeld **Verteilereigenschaften** überschreiben.</span><span class="sxs-lookup"><span data-stu-id="f5c04-105">You can override this default for any Publisher on the **Publishers** page of the Configure Distribution Wizard or the **Distributor Properties** dialog box.</span></span>  
  
 <span data-ttu-id="f5c04-106">Der Momentaufnahmeordner ist lediglich ein von Ihnen freigegebenes Verzeichnis. Agents, die aus diesem Ordner lesen bzw. in den Ordner schreiben, benötigen ausreichende Zugriffsberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="f5c04-106">The snapshot folder is simply a directory that you have designated as a share; agents that read from and write to this folder must have sufficient permissions to access it.</span></span> <span data-ttu-id="f5c04-107">Weitere Informationen zum Sichern des Ordners finden Sie unter [Sichern des Momentaufnahmeordners](security/secure-the-snapshot-folder.md).</span><span class="sxs-lookup"><span data-stu-id="f5c04-107">For more information about securing the folder appropriately, see [Secure the Snapshot Folder](security/secure-the-snapshot-folder.md).</span></span> <span data-ttu-id="f5c04-108">Testen Sie vor der Implementierung der Replikation, ob die Replikations-Agents eine Verbindung mit dem Momentaufnahmeordner herstellen können.</span><span class="sxs-lookup"><span data-stu-id="f5c04-108">Prior to implementing replication, test that the replication agents will be able to connect to the snapshot folder.</span></span> <span data-ttu-id="f5c04-109">Melden Sie sich unter dem von dem jeweiligen Agenten verwendeten Konto an, und versuchen Sie, auf den Momentaufnahmeordner zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f5c04-109">Log on under the account that will be used by each agent and then attempt to access the snapshot folder.</span></span>  
  
## <a name="options"></a><span data-ttu-id="f5c04-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="f5c04-110">Options</span></span>  
 <span data-ttu-id="f5c04-111">**Momentaufnahmeordner**</span><span class="sxs-lookup"><span data-stu-id="f5c04-111">**Snapshot folder**</span></span>  
 <span data-ttu-id="f5c04-112">Geben Sie den Pfad für den Ordner an, in dem Momentaufnahmedateien gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="f5c04-112">Enter the path for the folder where you want snapshot files stored.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="f5c04-113">empfiehlt die Verwendung einer Netzwerkfreigabe als Speicherort des Momentaufnahmeordners.</span><span class="sxs-lookup"><span data-stu-id="f5c04-113">recommends that you use a network share as a snapshot folder location.</span></span> <span data-ttu-id="f5c04-114">Auf lokale Pfade (beginnend mit einem Laufwerksbuchstaben, z.B. C:\\) können Agents und andere Computer nicht zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f5c04-114">Local paths (those starting with a drive letter, such as C:\\) are not accessible to agents on other computers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5c04-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f5c04-115">See Also</span></span>  
 <span data-ttu-id="f5c04-116">[Alternative Speicherorte für Momentaufnahme Ordner](alternate-snapshot-folder-locations.md) </span><span class="sxs-lookup"><span data-stu-id="f5c04-116">[Alternate Snapshot Folder Locations](alternate-snapshot-folder-locations.md) </span></span>  
 <span data-ttu-id="f5c04-117">[Verteilung konfigurieren](configure-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="f5c04-117">[Configure Distribution](configure-distribution.md) </span></span>  
 <span data-ttu-id="f5c04-118">[Konfigurieren der Veröffentlichung und der Verteilung](configure-publishing-and-distribution.md) </span><span class="sxs-lookup"><span data-stu-id="f5c04-118">[Configure Publishing and Distribution](configure-publishing-and-distribution.md) </span></span>  
 <span data-ttu-id="f5c04-119">[Anzeigen und Ändern der Verteiler- und Verlegereigenschaften](view-and-modify-distributor-and-publisher-properties.md) </span><span class="sxs-lookup"><span data-stu-id="f5c04-119">[View and Modify Distributor and Publisher Properties](view-and-modify-distributor-and-publisher-properties.md) </span></span>  
 [<span data-ttu-id="f5c04-120">Initialisieren eines Abonnements mit einer Momentaufnahme</span><span class="sxs-lookup"><span data-stu-id="f5c04-120">Initialize a Subscription with a Snapshot</span></span>](initialize-a-subscription-with-a-snapshot.md)  
  
  
