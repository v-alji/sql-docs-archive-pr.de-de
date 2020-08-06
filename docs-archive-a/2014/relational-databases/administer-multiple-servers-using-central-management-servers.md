---
title: Verwalten mehrerer Server mithilfe von zentralen Verwaltungsservern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
helpviewer_keywords:
- multiserver queries
- central management server
- multiserver administration [SQL Server]
- master servers [SQL Server], central management servers
- target configuration [SQL Server]
- server configuration [SQL Server]
ms.assetid: 427911a7-57d4-4542-8846-47c3267a5d9c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 3906165b595f6faa15812f70377a3bc0f550e52e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699837"
---
# <a name="administer-multiple-servers-using-central-management-servers"></a><span data-ttu-id="05227-102">Verwalten mehrerer Server mithilfe von zentralen Verwaltungsservern</span><span class="sxs-lookup"><span data-stu-id="05227-102">Administer Multiple Servers Using Central Management Servers</span></span>
  <span data-ttu-id="05227-103">Sie können mehrere Server verwalten, indem Sie zentrale Verwaltungsserver festlegen und Servergruppen erstellen.</span><span class="sxs-lookup"><span data-stu-id="05227-103">You can administer multiple servers by designating Central Management Servers and creating server groups.</span></span>  
  
## <a name="benefits-of-central-management-servers-and-server-groups"></a><span data-ttu-id="05227-104">Vorteile von zentralen Verwaltungsservern und Servergruppen</span><span class="sxs-lookup"><span data-stu-id="05227-104">Benefits of Central Management Servers and Server Groups</span></span>  
 <span data-ttu-id="05227-105">Eine Instanz von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], die als zentraler Verwaltungsserver festgelegt wurde, verwaltet die Servergruppen, die die Verbindungsinformationen für Instanzen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] enthalten.</span><span class="sxs-lookup"><span data-stu-id="05227-105">An instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that is designated as a Central Management Server maintains server groups that contain the connection information for one or more instances of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> [!INCLUDE[tsql](../includes/tsql-md.md)]<span data-ttu-id="05227-106">-Anweisungen und Richtlinien der richtlinienbasierten Verwaltung können gleichzeitig für Servergruppen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="05227-106">statements and Policy-Based Management policies can be executed at the same time against server groups.</span></span> <span data-ttu-id="05227-107">Sie können auch die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Protokolldateien in Instanzen anzeigen, die von einem zentralen Verwaltungsserver verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="05227-107">You can also view the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] log files on instances that are managed through a Central Management Server.</span></span> <span data-ttu-id="05227-108">Versionen von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , die älter sind als [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] , können nicht als zentraler Verwaltungsserver festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="05227-108">Versions of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] that are earlier than [!INCLUDE[ssKatmai](../includes/sskatmai-md.md)] cannot be designated as a Central Management Server.</span></span>  
  
 [!INCLUDE[tsql](../includes/tsql-md.md)] <span data-ttu-id="05227-109">-Anweisungen können auch für lokale Servergruppen in registrierten Servern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="05227-109">statements can also be executed against local server groups in Registered Servers.</span></span>  
  
### <a name="related-tasks"></a><span data-ttu-id="05227-110">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="05227-110">Related Tasks</span></span>  
 <span data-ttu-id="05227-111">Um einen zentralen Verwaltungsserver und Servergruppen zu erstellen, verwenden Sie das Fenster **Registrierte Server** in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="05227-111">To create a Central Management Server and server groups, use the **Registered Servers** window in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="05227-112">Beachten Sie, dass der zentrale Verwaltungsserver nicht Mitglied einer Gruppe sein kann, die er verwaltet.</span><span class="sxs-lookup"><span data-stu-id="05227-112">Note that the Central Management Server cannot be a member of a group that it maintains.</span></span> <span data-ttu-id="05227-113">Weitere Informationen zum Erstellen von zentralen Verwaltungsservern und Servergruppen finden Sie unter [Erstellen eines zentralen Verwaltungsservers und einer Servergruppe &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md).</span><span class="sxs-lookup"><span data-stu-id="05227-113">For more information about how to create Central Management Servers and server groups, see [Create a Central Management Server and Server Group &#40;SQL Server Management Studio&#41;](../ssms/register-servers/create-a-central-management-server-and-server-group.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05227-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="05227-114">See Also</span></span>  
 [<span data-ttu-id="05227-115">Verwalten von Servern mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="05227-115">Administer Servers by Using Policy-Based Management</span></span>](policy-based-management/administer-servers-by-using-policy-based-management.md)  
  
  
