---
title: Nicht-SQL Server-Abonnenten hinzufügen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.newsubwizard.addnonsqlsubscriber.f1
ms.assetid: 21beeaa0-4b9e-48da-be63-1b9ff14e03d2
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: e36d048b11fcc71b27ab0ab2ee815b0284187c4d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618665"
---
# <a name="add-non-sql-server-subscriber"></a><span data-ttu-id="d282a-102">Nicht-SQL Server-Abonnenten hinzufügen</span><span class="sxs-lookup"><span data-stu-id="d282a-102">Add Non-SQL Server Subscriber</span></span>
  <span data-ttu-id="d282a-103">Die Replikation unterstützt das Erstellen von Pushabonnements für Momentaufnahme- und Transaktionsveröffentlichungen für Oracle und IBM DB2-Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="d282a-103">Replication supports creating push subscriptions to snapshot and transactional publications for Oracle and IBM DB2 Subscribers.</span></span>  
  
## <a name="options"></a><span data-ttu-id="d282a-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="d282a-104">Options</span></span>  
 <span data-ttu-id="d282a-105">**Typ des hinzuzufügenden Abonnenten**</span><span class="sxs-lookup"><span data-stu-id="d282a-105">**Type of Subscriber to add**</span></span>  
 <span data-ttu-id="d282a-106">Wählen Sie einen Oracle-Abonnenten oder einen IBM DB2-Abonnenten aus.</span><span class="sxs-lookup"><span data-stu-id="d282a-106">Select an Oracle Subscriber or IBM DB2 Subscriber.</span></span> <span data-ttu-id="d282a-107">Weitere Informationen zur Unterstützung für diese Abonnenten finden Sie unter [Nicht-SQL Server-Abonnenten](non-sql/non-sql-server-subscribers.md).</span><span class="sxs-lookup"><span data-stu-id="d282a-107">For more information about support for these Subscribers, see [Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md).</span></span>  
  
 <span data-ttu-id="d282a-108">**Datenquellenname**</span><span class="sxs-lookup"><span data-stu-id="d282a-108">**Data source name**</span></span>  
 <span data-ttu-id="d282a-109">Der Name, der verwendet wird, um die Datenbank in einem Netzwerk zu suchen.</span><span class="sxs-lookup"><span data-stu-id="d282a-109">The name used to locate the database on a network.</span></span> <span data-ttu-id="d282a-110">Die Replikation erzeugt eine Verbindungszeichenfolge für die Datenbank mithilfe des Datenquellennamens, der mit dem Anmeldenamen, dem Kennwort und den Verbindungsoptionen kombiniert wird, die Sie auf der Seite **Sicherheit für den Verteilungs-Agent** in diesem Assistenten angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="d282a-110">Replication produces a connection string for the database using the data source name, combined with the login, password, and any connection options you specify in the **Distribution Agent Security** page in this wizard.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d282a-111">Der Datenquellenname und die Verbindungszeichenfolge werden nicht durch [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] überprüft, bevor der Verteilungs-Agent versucht, das Abonnement zu initialisieren.</span><span class="sxs-lookup"><span data-stu-id="d282a-111">The data source name and connection string are not validated by [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] until the Distribution Agent attempts to initialize the subscription.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d282a-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d282a-112">See Also</span></span>  
 <span data-ttu-id="d282a-113">[Erstellen eines Abonnements für einen Nicht-SQL Server-Abonnenten](create-a-subscription-for-a-non-sql-server-subscriber.md) </span><span class="sxs-lookup"><span data-stu-id="d282a-113">[Create a Subscription for a Non-SQL Server Subscriber](create-a-subscription-for-a-non-sql-server-subscriber.md) </span></span>  
 <span data-ttu-id="d282a-114">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span><span class="sxs-lookup"><span data-stu-id="d282a-114">[Non-SQL Server Subscribers](non-sql/non-sql-server-subscribers.md) </span></span>  
 [<span data-ttu-id="d282a-115">Abonnieren von Veröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="d282a-115">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
