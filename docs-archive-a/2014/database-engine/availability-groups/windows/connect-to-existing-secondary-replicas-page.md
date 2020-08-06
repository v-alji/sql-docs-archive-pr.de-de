---
title: Seite mit vorhandenen sekundären Replikaten verbinden (Assistent zum Hinzufügen von Replikaten und Datenbanken hinzufügen Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
f1_keywords:
- sql12.swb.addreplicawizard.connecttoreplicas.f1
- sql12.swb.adddatabasewizard.connecttoreplicas.f1
ms.assetid: 850f1bc8-d7d0-425c-bd7b-03f0e9d3348e
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 80af8dfebd6e23a923ddf67438edabf9ab0e2f65
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697189"
---
# <a name="connect-to-existing-secondary-replicas-page-add-replica-wizard-and-add-databases-wizard"></a><span data-ttu-id="55493-102">Seite „Mit vorhandenen sekundären Replikaten verbinden“ (Assistent zum Hinzufügen von Replikaten und Assistent zum Hinzufügen von Datenbanken)</span><span class="sxs-lookup"><span data-stu-id="55493-102">Connect to Existing Secondary Replicas Page (Add Replica Wizard and Add Databases Wizard)</span></span>
  <span data-ttu-id="55493-103"> In diesem Hilfethema werden die Optionen auf der Seite **Mit vorhandenen sekundären Replikaten verbinden** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="55493-103">This help topic describes the options of the **Connect to Existing Secondary Replicas** page.</span></span> <span data-ttu-id="55493-104">Dieses Thema wird unter [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] sowohl von [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] als auch von [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)]verwendet.</span><span class="sxs-lookup"><span data-stu-id="55493-104">This topic is used by the [!INCLUDE[ssAoAddRepWiz](../../../includes/ssaoaddrepwiz-md.md)] and [!INCLUDE[ssAoAddDbWiz](../../../includes/ssaoadddbwiz-md.md)] of [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)].</span></span>  
  
 <span data-ttu-id="55493-105">**Rasterspalten:**</span><span class="sxs-lookup"><span data-stu-id="55493-105">**Grid columns:**</span></span>  
 <span data-ttu-id="55493-106">**Serverinstanz**</span><span class="sxs-lookup"><span data-stu-id="55493-106">**Server Instance**</span></span>  
 <span data-ttu-id="55493-107">Zeigt den Namen der Serverinstanz an, die als Host für das Verfügbarkeitsreplikat fungiert.</span><span class="sxs-lookup"><span data-stu-id="55493-107">Displays the name of the server instance that will host the availability replica.</span></span>  
  
 <span data-ttu-id="55493-108">**Verbunden als**</span><span class="sxs-lookup"><span data-stu-id="55493-108">**Connected As**</span></span>  
 <span data-ttu-id="55493-109">Zeigt das Konto an, das mit der Serverinstanz verbunden ist, nachdem die Verbindung hergestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="55493-109">Displays the account that is connected to the server instance, once the connection has been established.</span></span> <span data-ttu-id="55493-110">Wenn in dieser Spalte für eine bestimmte Serverinstanz "**Nicht verbunden**" angezeigt wird, müssen Sie auf die Schaltfläche **Verbinden** bzw. **Alle verbinden** klicken.</span><span class="sxs-lookup"><span data-stu-id="55493-110">If this column displays "**Not Connected**" for a given server instance, you will need to click either the **Connect** or **Connect All** button.</span></span>  
  
 <span data-ttu-id="55493-111">**Herstellen einer Verbindung**</span><span class="sxs-lookup"><span data-stu-id="55493-111">**Connect**</span></span>  
 <span data-ttu-id="55493-112">Klicken Sie auf diese Schaltfläche, wenn diese Serverinstanz unter einem anderen Konto als andere Serverinstanzen ausgeführt wird, mit denen Sie eine Verbindung herstellen müssen.</span><span class="sxs-lookup"><span data-stu-id="55493-112">Click if this server instance is running under a different account than other server instances to which you need to connect.</span></span>  
  
 <span data-ttu-id="55493-113">**Alle verbinden**</span><span class="sxs-lookup"><span data-stu-id="55493-113">**Connect All**</span></span>  
 <span data-ttu-id="55493-114">Klicken Sie nur auf diese Schaltfläche, wenn alle Instanzen von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , mit denen Sie eine Verbindung herstellen müssen, als Dienst im gleichen Benutzerkonto ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="55493-114">Click only if every instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which you need to connect is running as a service in the same user account.</span></span>  
  
 <span data-ttu-id="55493-115">**Abbrechen**</span><span class="sxs-lookup"><span data-stu-id="55493-115">**Cancel**</span></span>  
 <span data-ttu-id="55493-116">Klicken Sie, um den Assistenten abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="55493-116">Click to cancel the wizard.</span></span> <span data-ttu-id="55493-117">Wenn Sie den Assistenten auf der Seite **Mit vorhandenen sekundären Replikaten verbinden** abbrechen, wird dieser beendet, ohne dass Aktionen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="55493-117">On the **Connect to Existing Secondary Replica** page, cancelling the wizard cause it to exit without performing any actions.</span></span>  
  

  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="55493-118">Verwandte Aufgaben</span><span class="sxs-lookup"><span data-stu-id="55493-118">Related Tasks</span></span>  
  
-   [<span data-ttu-id="55493-119">Verwenden des Assistenten zum Hinzufügen von Replikaten zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="55493-119">Use the Add Replica to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-add-replica-to-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="55493-120">Verwenden des Assistenten zum Hinzufügen von Datenbanken zu Verfügbarkeitsgruppen &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="55493-120">Use the Add Database to Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](availability-group-add-database-to-group-wizard.md)  
  

  
## <a name="see-also"></a><span data-ttu-id="55493-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="55493-121">See Also</span></span>  
 [<span data-ttu-id="55493-122">Übersicht über AlwaysOn-Verfügbarkeitsgruppen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="55493-122">Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](overview-of-always-on-availability-groups-sql-server.md)  
  
  
