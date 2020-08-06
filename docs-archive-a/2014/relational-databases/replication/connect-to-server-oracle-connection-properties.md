---
title: Verbindung mit Server herstellen (Oracle), Verbindungseigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.oracleconnection.connectionprops.f1
helpviewer_keywords:
- Connect to Server dialog box, replication
ms.assetid: 1bb7396f-cbb2-4f88-b82b-543287ed4172
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 4c76a3058283a098357701a44de48efff917acd7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608577"
---
# <a name="connect-to-server-oracle-connection-properties"></a><span data-ttu-id="3961d-102">Verbindung mit Server herstellen (Oracle), Verbindungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="3961d-102">Connect to Server (Oracle), Connection Properties</span></span>
  <span data-ttu-id="3961d-103">Mithilfe der Registerkarte **Verbindungseigenschaften** des Dialogfelds **Verbindung mit Server herstellen** können Sie eine Veröffentlichungsoption von **Gateway** oder **Vollständig**angeben.</span><span class="sxs-lookup"><span data-stu-id="3961d-103">Use the **Connection Properties** tab of the **Connect to Server** dialog box to specify a publishing option of **Gateway** or **Complete**.</span></span> <span data-ttu-id="3961d-104">Nachdem ein Verleger identifiziert wurde, kann diese Option nicht mehr geändert werden, ohne dass der Verleger gelöscht und neu konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="3961d-104">After a Publisher is identified, this option cannot be changed without dropping and reconfiguring the Publisher.</span></span> <span data-ttu-id="3961d-105">Weitere Informationen finden Sie unter [Konfigurieren eines Oracle-Verlegers](non-sql/configure-an-oracle-publisher.md).</span><span class="sxs-lookup"><span data-stu-id="3961d-105">For more information, see [Configure an Oracle Publisher](non-sql/configure-an-oracle-publisher.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="3961d-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="3961d-106">Options</span></span>  
 <span data-ttu-id="3961d-107">**Herausgebertyp**</span><span class="sxs-lookup"><span data-stu-id="3961d-107">**Publisher type**</span></span>  
 <span data-ttu-id="3961d-108">Wählen Sie **Gateway** oder **Vollständig**aus.</span><span class="sxs-lookup"><span data-stu-id="3961d-108">Select **Gateway** or **Complete**.</span></span> <span data-ttu-id="3961d-109">Mithilfe der Option **Vollständig** kann für Momentaufnahme- und Transaktionsveröffentlichungen der vollständige Satz an unterstützten Funktionen für Oracle-Veröffentlichungen verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="3961d-109">The **Complete** option is designed to provide snapshot and transactional publications with the complete set of supported features for Oracle publishing.</span></span> <span data-ttu-id="3961d-110">Die Option **Gateway** bietet spezielle Designoptimierungen, um die Leistung in Fällen zu verbessern, in denen die Replikation als Gateway zwischen Systemen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3961d-110">The **Gateway** option provides specific design optimizations to improve performance for cases where replication serves as a gateway between systems.</span></span> <span data-ttu-id="3961d-111">Sie können die Option **Gateway** nicht verwenden, wenn Sie planen, dieselbe Tabelle in mehreren Transaktionsveröffentlichungen zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="3961d-111">The **Gateway** option cannot be used if you plan to publish the same table in multiple transactional publications.</span></span> <span data-ttu-id="3961d-112">Wenn Sie **Gateway**auswählen, kann eine Tabelle höchstens in einer Transaktionsveröffentlichung und in einer beliebigen Zahl an Momentaufnahmeveröffentlichungen erscheinen.</span><span class="sxs-lookup"><span data-stu-id="3961d-112">A table can appear in at most one transactional publication and any number of snapshot publications if you select **Gateway**.</span></span>  
  
 <span data-ttu-id="3961d-113">**Timeouts**</span><span class="sxs-lookup"><span data-stu-id="3961d-113">**Timeouts**</span></span>  
 <span data-ttu-id="3961d-114">Geben Sie an, wie lange der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Verteiler versuchen soll, eine Verbindung mit dem Oracle-Verleger herzustellen, bevor ein Timeoutfehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="3961d-114">Specify how long the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Distributor should attempt to connect to the Oracle Publisher before a timeout error occurs.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3961d-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3961d-115">See Also</span></span>  
 <span data-ttu-id="3961d-116">[Begriffe im Zusammenhang mit dem Veröffentlichen von Oracle-Daten](non-sql/glossary-of-terms-for-oracle-publishing.md) </span><span class="sxs-lookup"><span data-stu-id="3961d-116">[Glossary of Terms for Oracle Publishing](non-sql/glossary-of-terms-for-oracle-publishing.md) </span></span>  
 [<span data-ttu-id="3961d-117">Leistungsoptimierung für Oracle-Verleger</span><span class="sxs-lookup"><span data-stu-id="3961d-117">Performance Tuning for Oracle Publishers</span></span>](non-sql/performance-tuning-for-oracle-publishers.md)  
  
  
