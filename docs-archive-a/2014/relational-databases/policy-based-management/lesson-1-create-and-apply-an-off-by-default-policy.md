---
title: 'Lektion 1: Erstellen und Anwenden einer Richtlinie „Standardmäßig aus“ | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
ms.assetid: d31367db-b7db-44c4-8df2-f1240474cf78
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 9a76df1a72b93d09c5c1c199cb0246dbb51c9cbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609168"
---
# <a name="lesson-1-create-and-apply-an-off-by-default-policy"></a><span data-ttu-id="222c4-102">Lektion 1: Erstellen und Anwenden der Richtlinie „Standardmäßig deaktiviert“</span><span class="sxs-lookup"><span data-stu-id="222c4-102">Lesson 1: Create and Apply an Off By Default Policy</span></span>
  <span data-ttu-id="222c4-103">Mit richtlinienbasierten Verwaltungsrichtlinien können Sie ein oder mehrere Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], ein oder mehrere Instanzobjekte, Serverinstanzen, ein oder mehrere Datenbanken oder ein oder mehrere Datenbankobjekte verwalten.</span><span class="sxs-lookup"><span data-stu-id="222c4-103">Using Policy-Based Management policies, you can administer one or more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], one or more instance objects, server instances, one or more databases, or one or more database objects.</span></span> <span data-ttu-id="222c4-104">Als Datenbankadministrator möchten Sie sicherstellen, dass auf bestimmten Servern keine Datenbank-E-Mail aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="222c4-104">As the database administrator, you want to ensure that certain servers do not have Database Mail enabled.</span></span> <span data-ttu-id="222c4-105">In dieser Lektion erstellen Sie eine Bedingung und eine Richtlinie, durch die diese Serveroption festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="222c4-105">In this lesson, you will create a condition and a policy that sets that server option.</span></span> <span data-ttu-id="222c4-106">Sie testen den Server, um zu sehen, ob er die Richtlinie einhält.</span><span class="sxs-lookup"><span data-stu-id="222c4-106">You will test the server to see whether it complies with the policy.</span></span> <span data-ttu-id="222c4-107">Anschließend verwenden Sie die Richtlinie, um den Server neu zu konfigurieren, sodass der Server die Richtlinie einhält.</span><span class="sxs-lookup"><span data-stu-id="222c4-107">Then, you will use the policy to reconfigure the server to bring the server into compliance.</span></span>  
  
 <span data-ttu-id="222c4-108">Diese Lektion enthält die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="222c4-108">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="222c4-109">Erstellen der Richtlinie 'Standardmäßig aus'</span><span class="sxs-lookup"><span data-stu-id="222c4-109">Create the Off By Default Policy</span></span>](lesson-1-1-create-the-off-by-default-policy.md)  
  
-   [<span data-ttu-id="222c4-110">Konfigurieren eines Servers für das Ausführen der Richtlinie 'Standardmäßig aus'</span><span class="sxs-lookup"><span data-stu-id="222c4-110">Configure a Server to Run the Off By Default Policy</span></span>](lesson-1-2-configure-a-server-to-run-the-off-by-default-policy.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="222c4-111">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="222c4-111">Next Task in Lesson</span></span>  
 [<span data-ttu-id="222c4-112">Erstellen der Richtlinie 'Standardmäßig aus'</span><span class="sxs-lookup"><span data-stu-id="222c4-112">Create the Off By Default Policy</span></span>](lesson-1-1-create-the-off-by-default-policy.md)  
  
## <a name="next-lesson"></a><span data-ttu-id="222c4-113">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="222c4-113">Next Lesson</span></span>  
 [<span data-ttu-id="222c4-114">Lektion 2: Erstellen und Anwenden einer Richtlinie für Benennungsstandards</span><span class="sxs-lookup"><span data-stu-id="222c4-114">Lesson 2: Create and Apply a Naming Standards Policy</span></span>](lesson-2-create-and-apply-a-naming-standards-policy.md)  
  
  
