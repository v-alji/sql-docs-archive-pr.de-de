---
title: Abonnenteneigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql12.rep.configdistwizard.subscribers.f1
helpviewer_keywords:
- Subscriber Properties dialog box
ms.assetid: 32aa0347-64e4-4aa4-ac57-6bd3e5d52070
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 81ab9cf5f277ccfe1044e5a7083f019db9d843ff
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724485"
---
# <a name="subscriber-properties"></a><span data-ttu-id="5b89a-102">Abonnenteneigenschaften</span><span class="sxs-lookup"><span data-stu-id="5b89a-102">Subscriber Properties</span></span>
  <span data-ttu-id="5b89a-103">Das Dialogfeld **Abonnenteneigenschaften** enthält Informationen zu den Abonnenten, die [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Versionen verwenden, die älter als [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] sind.</span><span class="sxs-lookup"><span data-stu-id="5b89a-103">The **Subscriber Properties** dialog box contains information relevant to Subscribers running versions of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
## <a name="options"></a><span data-ttu-id="5b89a-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="5b89a-104">Options</span></span>  
 <span data-ttu-id="5b89a-105">**Agentverbindung mit dem Abonnenten**</span><span class="sxs-lookup"><span data-stu-id="5b89a-105">**Agent Connection to the Subscriber**</span></span>  
 <span data-ttu-id="5b89a-106">Der Kontext, in dem der Verteilungs-Agent und der Merge-Agent die Verbindung vom Verteiler zum Abonnenten herstellen. Dieser gilt nur für Versionen vor [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5b89a-106">The context under which the Distribution Agent and Merge Agent connect from the Distributor to the Subscriber This applies only to versions before [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="5b89a-107">Wählen Sie die Option **Identität des Agentprozesskontos annehmen** , um unter Verwendung des Kontexts des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Agent-Kontos auf Verteilerebene Verbindungen zum Abonnenten herzustellen. Geben Sie alternativ die **SQL Server-Authentifizierung**an, und geben Sie dann einen Wert für die **Anmeldung** und das **Kennwort**ein.</span><span class="sxs-lookup"><span data-stu-id="5b89a-107">Select **Impersonate agent process account** to make connections to the Subscriber using the context of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Agent account at the Distributor, or specify **SQL Server Authentication**, and then enter a value for **Login** and **Password**.</span></span> [!INCLUDE[msCoName](../../includes/msconame-md.md)] <span data-ttu-id="5b89a-108">empfiehlt die Auswahl von **Identität des Agentprozesskontos annehmen**.</span><span class="sxs-lookup"><span data-stu-id="5b89a-108">recommends that you select **Impersonate agent process account**.</span></span>  
  
 <span data-ttu-id="5b89a-109">In [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] und höheren Versionen werden die Verbindungsinformationen für jedes Abonnement im Assistent für neue Abonnements angegeben. Die Informationen können im Dialogfeld **Abonnementeigenschaften** geändert werden.</span><span class="sxs-lookup"><span data-stu-id="5b89a-109">For [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] and later versions, connection information is specified for each subscription in the New Subscription Wizard and can be changed in the **Subscription Properties** dialog box.</span></span>  
  
 <span data-ttu-id="5b89a-110">**Standardzeitpläne für Agent**</span><span class="sxs-lookup"><span data-stu-id="5b89a-110">**Default Agent Schedules**</span></span>  
 <span data-ttu-id="5b89a-111">Der Standardzeitplan, der im Assistenten für neue Abonnements für Abonnenten verwendet wird, auf denen Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vor [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)]ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5b89a-111">The default schedule used in the New Subscription Wizard for Subscribers running versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] before [!INCLUDE[ssVersion2000](../../includes/ssversion2000-md.md)].</span></span>  
  
 <span data-ttu-id="5b89a-112">**Verschiedenes**</span><span class="sxs-lookup"><span data-stu-id="5b89a-112">**Miscellaneous**</span></span>  
 <span data-ttu-id="5b89a-113">Enthält Informationen zum Abonnenten und zum Typ des Abonnenten.</span><span class="sxs-lookup"><span data-stu-id="5b89a-113">Includes information on the Subscriber and Subscriber type.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b89a-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b89a-114">See Also</span></span>  
 [<span data-ttu-id="5b89a-115">Anzeigen und Ändern der Verteiler- und Verlegereigenschaften</span><span class="sxs-lookup"><span data-stu-id="5b89a-115">View and Modify Distributor and Publisher Properties</span></span>](view-and-modify-distributor-and-publisher-properties.md)   

 [<span data-ttu-id="5b89a-116">Abonnieren von Veröffentlichungen</span><span class="sxs-lookup"><span data-stu-id="5b89a-116">Subscribe to Publications</span></span>](subscribe-to-publications.md)  
  
  
