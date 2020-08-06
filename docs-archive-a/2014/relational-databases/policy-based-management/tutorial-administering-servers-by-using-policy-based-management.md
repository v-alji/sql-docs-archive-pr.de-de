---
title: 'Tutorial: Verwalten von Servern mit der richtlinienbasierten Verwaltung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- tutorials [Policy-Based Management]
- Policy-Based Management, tutorials
ms.assetid: 7de96e7b-9fb8-4cc8-8d85-61345d68a1e8
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9b707a5ecd362c6b3b54e853f89d79e25a9e1428
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615994"
---
# <a name="tutorial-administering-servers-by-using-policy-based-management"></a><span data-ttu-id="68a78-102">Tutorial: Verwalten von Servern mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="68a78-102">Tutorial: Administering Servers by Using Policy-Based Management</span></span>
  <span data-ttu-id="68a78-103">Willkommen beim Lernprogramm zum Verwalten von Servern mit richtlinienbasierten Verwaltungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="68a78-103">Welcome to the Administering Servers by Using Policy-Based Management Policies tutorial.</span></span> <span data-ttu-id="68a78-104">Dieses Lernprogramm richtet sich an Benutzer, die mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vertraut sind, die richtlinienbasierte Verwaltung jedoch noch nicht kennen.</span><span class="sxs-lookup"><span data-stu-id="68a78-104">This tutorial is intended for users who are familiar with [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but new to the Policy-Based Management.</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="68a78-105">Lernziele</span><span class="sxs-lookup"><span data-stu-id="68a78-105">What You Will Learn</span></span>  
 <span data-ttu-id="68a78-106">In diesem Lernprogramm wird eine Richtlinie für das Verwalten Ihres Servers erstellt. Außerdem wird eine Richtlinie erstellt, die für eine einzelne Datenbank gilt.</span><span class="sxs-lookup"><span data-stu-id="68a78-106">This tutorial creates a policy to administer your server and a policy that applies to a single database.</span></span> <span data-ttu-id="68a78-107">Eine Richtlinie wird bedarfsgesteuert ausgeführt, um die Einhaltung der Richtlinie zu testen.</span><span class="sxs-lookup"><span data-stu-id="68a78-107">One policy is run on demand to test for compliance.</span></span> <span data-ttu-id="68a78-108">Die andere Richtlinie erzwingt die zukünftige Einhaltung dieser Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="68a78-108">The other policy enforces future compliance.</span></span>  
  
 <span data-ttu-id="68a78-109">Dieses Lernprogramm ist in zwei Lektionen aufgeteilt:</span><span class="sxs-lookup"><span data-stu-id="68a78-109">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="68a78-110">Lektion 1: Erstellen und Anwenden der Richtlinie „Standardmäßig deaktiviert“</span><span class="sxs-lookup"><span data-stu-id="68a78-110">Lesson 1: Create and Apply an Off By Default Policy</span></span>](lesson-1-create-and-apply-an-off-by-default-policy.md)  
 <span data-ttu-id="68a78-111">In dieser Lektion wird eine Richtlinie erstellt, die festlegt, dass Datenbank-E-Mail nicht auf dem Server aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="68a78-111">This lesson creates a policy that specifies that Database Mail is not enabled on the server.</span></span> <span data-ttu-id="68a78-112">Anschließend überprüft die Richtlinie, ob der Server diese Richtlinie einhält, und konfiguriert den Server, indem Datenbank-E-Mail deaktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="68a78-112">Then, it checks to see whether your server complies with the policy, and configures the server by disabling Database Mail.</span></span>  
  
 [<span data-ttu-id="68a78-113">Lektion 2: Erstellen und Anwenden einer Richtlinie für Benennungsstandards</span><span class="sxs-lookup"><span data-stu-id="68a78-113">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
 <span data-ttu-id="68a78-114">In dieser Lektion wird eine Richtlinie erstellt, die einen Benennungsstandard für Tabellen definiert und erzwingt.</span><span class="sxs-lookup"><span data-stu-id="68a78-114">This lesson creates a policy that defines and enforces a naming standard for tables.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68a78-115">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="68a78-115">Requirements</span></span>  
 <span data-ttu-id="68a78-116">Für diese Lektion benötigen Sie grundlegende Datenbankkenntnisse und grundlegende Kenntnisse von [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="68a78-116">This lesson requires basic database knowledge and a basic understanding of [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="68a78-117">Um das Lernprogramm verwenden zu können, muss auf Ihrem System [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] installiert sein.</span><span class="sxs-lookup"><span data-stu-id="68a78-117">To use this tutorial, your system must have [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] installed.</span></span>  
  
## <a name="start-the-tutorial"></a><span data-ttu-id="68a78-118">Lernprogramm starten</span><span class="sxs-lookup"><span data-stu-id="68a78-118">Start the Tutorial</span></span>  
 [<span data-ttu-id="68a78-119">Lektion 1: Erstellen und Anwenden der Richtlinie „Standardmäßig deaktiviert“</span><span class="sxs-lookup"><span data-stu-id="68a78-119">Lesson 1: Create and Apply an Off By Default Policy</span></span>](lesson-1-create-and-apply-an-off-by-default-policy.md)  
  
## <a name="see-also"></a><span data-ttu-id="68a78-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68a78-120">See Also</span></span>  
 [<span data-ttu-id="68a78-121">Verwalten von Servern mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="68a78-121">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
