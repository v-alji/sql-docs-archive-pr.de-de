---
title: Grundlagen des Besitzes von Datenbankdiagrammen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.diagnostic.CannotOpenWithInvalidOwner
helpviewer_keywords:
- diagrams [SQL Server], ownership
- database diagrams [SQL Server], ownership
- owners [SQL Server], database diagrams
ms.assetid: 4a27a48e-c4ef-4017-82b8-0cac4d0bbcac
author: stevestein
ms.author: sstein
ms.openlocfilehash: 21d0f6f006328d8843bbbe12ee066a8564fb722a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719297"
---
# <a name="understand-database-diagram-ownership-visual-database-tools"></a><span data-ttu-id="7182c-102">Grundlagen des Besitzes von Datenbankdiagrammen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="7182c-102">Understand Database Diagram Ownership (Visual Database Tools)</span></span>
  <span data-ttu-id="7182c-103">Der Datenbankdiagramm-Designer kann erst verwendet werden, nachdem er von einem Mitglied der db_owner-Rolle (eine Rolle von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbanken) für den Zugriff auf Diagramme eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="7182c-103">To use Database Diagram Designer it must first be set up by a member of the db_owner role (a role of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] databases) to control access to diagrams.</span></span> <span data-ttu-id="7182c-104">Jedes Diagramm hat nur einen einzigen Besitzer, und zwar den Benutzer, der das Diagramm erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="7182c-104">Each diagram has one and only one owner, the user who created it.</span></span> <span data-ttu-id="7182c-105">Weitere Informationen zum Einrichten der Diagramm Erstellung finden [Sie unter Einrichten des Daten Bank Diagramm-Designers &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7182c-105">For more information on setting up diagramming see [Set Up Database Diagram Designer &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="7182c-106">Es folgen einige Punkte, die Sie beim Besitz von Diagrammen beachten sollten:</span><span class="sxs-lookup"><span data-stu-id="7182c-106">Some points to keep in mind about diagram ownership:</span></span>  
  
-   <span data-ttu-id="7182c-107">Obwohl jeder beliebige Benutzer mit Zugriff auf eine Datenbank ein Diagramm erstellen kann, können nur der Ersteller des Diagramms und alle Mitglieder der Rolle db_owner das Diagramm anzeigen.</span><span class="sxs-lookup"><span data-stu-id="7182c-107">Although any user with access to a database can create a diagram, once the diagram has been created, the only users who can see it are the diagram's creator and any member of the db_owner role.</span></span>  
  
-   <span data-ttu-id="7182c-108">Der Besitz von Diagrammen kann nur an Mitglieder der Rolle db_owner übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="7182c-108">Ownership of diagrams can only be transferred to members of the db_owner role.</span></span> <span data-ttu-id="7182c-109">Und dies ist auch nur dann möglich, wenn der vorherige Besitzer des Diagramms aus der Datenbank entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="7182c-109">This is only possible if the previous owner of the diagram has been removed from the database.</span></span>  
  
-   <span data-ttu-id="7182c-110">Wenn der Besitzer eines Diagramms aus der Datenbank entfernt wurde, bleibt das Diagramm in der Datenbank, bis ein Mitglied der Rolle db_owner versucht, das Diagramm zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7182c-110">If the owner of a diagram has been removed from the database, the diagram will remain in the database until a member of the db_owner role attempts to open it.</span></span> <span data-ttu-id="7182c-111">Zu diesem Zeitpunkt kann das Mitglied von db_owner entscheiden, den Besitz des Diagramms zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="7182c-111">At that point the db_owner member can choose to take over ownership of the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7182c-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7182c-112">See Also</span></span>  
 <span data-ttu-id="7182c-113">[Arbeiten mit Daten Bank Diagrammen &#40;Visual Database Tools&#41;](work-with-database-diagrams-visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="7182c-113">[Work with Database Diagrams &#40;Visual Database Tools&#41;](work-with-database-diagrams-visual-database-tools.md) </span></span>  
 [<span data-ttu-id="7182c-114">Einrichten im Datenbankdiagramm-Designer &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="7182c-114">Set Up Database Diagram Designer &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
