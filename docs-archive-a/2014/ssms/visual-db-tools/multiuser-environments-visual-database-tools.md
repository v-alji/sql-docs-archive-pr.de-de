---
title: Mehrbenutzerumgebungen (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- users [SQL Server], multiuser environments
- conflict resolution [Visual Database Tools]
- multiple users making database changes
- multiuser environments [Visual Database Tools]
- database modifications [SQL Server]
- version control [Visual Database Tools]
- Visual Database Tools [SQL Server], multiuser environments
ms.assetid: 330bd48c-9427-4967-b58e-b7c492d5ee36
author: stevestein
ms.author: sstein
ms.openlocfilehash: 2e219ecda25f477aa459de674a43d9c2360376ba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615743"
---
# <a name="multiuser-environments-visual-database-tools"></a><span data-ttu-id="6b091-102">Mehrbenutzerumgebungen (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6b091-102">Multiuser Environments (Visual Database Tools)</span></span>
  <span data-ttu-id="6b091-103">In einer Mehrbenutzerumgebung können andere Benutzer eine Verbindung mit der Datenbank herstellen, in der Sie arbeiten, und Änderungen daran vornehmen.</span><span class="sxs-lookup"><span data-stu-id="6b091-103">A multiuser environment is one in which other users can connect and make changes to the same database that you are working with.</span></span> <span data-ttu-id="6b091-104">Im Ergebnis können mehrere Benutzer ggf. gleichzeitig mit demselben Datenbankobjekt arbeiten.</span><span class="sxs-lookup"><span data-stu-id="6b091-104">As a result, several users might be working with the same database objects at the same time.</span></span> <span data-ttu-id="6b091-105">In einer Mehrbenutzerumgebung kann es daher vorkommen, dass sich die Änderungen anderer Benutzer auf die Datenbank auswirken, während Sie selbst gerade Änderungen vornehmen, und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="6b091-105">Thus, a multiuser environment introduces the possibility of the database being affected by changes made by other users while you are making changes, and vice versa.</span></span>  
  
 <span data-ttu-id="6b091-106">Bei der Arbeit mit Datenbanken in einer Mehrbenutzerumgebung stellen die Zugriffsberechtigungen ein zentrales Thema dar.</span><span class="sxs-lookup"><span data-stu-id="6b091-106">A key issue when working with databases in a multiuser environment is access permissions.</span></span> <span data-ttu-id="6b091-107">Die Berechtigungen, die Sie in einer Datenbank besitzen, spielen die entscheidende Rolle im Hinblick auf die Aufgaben, die Sie in der Datenbank ausführen können.</span><span class="sxs-lookup"><span data-stu-id="6b091-107">The permissions you have for the database determine the extent of the work you can do with the database.</span></span> <span data-ttu-id="6b091-108">Zum Ändern von Objekten in einer Datenbank müssen Sie z. B. die erforderlichen Schreibberechtigungen für die Datenbank besitzen.</span><span class="sxs-lookup"><span data-stu-id="6b091-108">For example, to make changes to objects in a database, you must have the appropriate write permissions for the database.</span></span> <span data-ttu-id="6b091-109">Weitere Informationen über Berechtigungen finden Sie in der Datenbankdokumentation.</span><span class="sxs-lookup"><span data-stu-id="6b091-109">For more information about permissions in your database, see your database documentation.</span></span> <span data-ttu-id="6b091-110">Weitere Informationen finden Sie unter [Berechtigungen und Visual Database Tools &#40;Visual Database Tools&#41;](visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6b091-110">For more information see [Permissions and Visual Database Tools &#40;Visual Database Tools&#41;](visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="6b091-111">Wenn Sie die an einer Tabelle vorgenommenen Änderungen speichern, überprüft der Tabellen-Designer, ob die Datenbank seit Ihrem letzten Speichern von Änderungen modifiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="6b091-111">When you save changes made to tables, Table Designer verifies that the database has not been modified since you last saved changes.</span></span> <span data-ttu-id="6b091-112">Falls ein anderer Benutzer die Datenbank geändert hat, werden Sie darüber benachrichtigt.</span><span class="sxs-lookup"><span data-stu-id="6b091-112">If another user has made changes, you will be notified that the database has been modified.</span></span> <span data-ttu-id="6b091-113">Eventuell müssen Sie diese Änderungen abgleichen.</span><span class="sxs-lookup"><span data-stu-id="6b091-113">You may need to reconcile these changes.</span></span> <span data-ttu-id="6b091-114">Weitere Informationen finden Sie unter [Abstimmen der Änderungen von mehreren Benutzern &#40;Visual Database Tools&#41;](reconcile-changes-made-by-multiple-users-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6b091-114">For more information, see [Reconcile Changes Made by Multiple Users &#40;Visual Database Tools&#41;](reconcile-changes-made-by-multiple-users-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="6b091-115">In einer Mehrbenutzerumgebung sind einige Besonderheiten zu beachten, damit einander widerstreitende Änderungen vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="6b091-115">In a multiuser environment there are special considerations to keep in mind to avoid conflicting changes.</span></span> <span data-ttu-id="6b091-116">Weitere Informationen finden Sie unter [Probleme bei der Datenbankentwicklung &#40;Visual Database Tools&#41;](issues-of-database-evolution-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6b091-116">For more information, see [Issues of Database Evolution &#40;Visual Database Tools&#41;](issues-of-database-evolution-visual-database-tools.md).</span></span>  
  
 <span data-ttu-id="6b091-117">Ein Weg, Probleme zu vermeiden, ist das Arbeiten an einer Kopie der Datenbank, z. B. einer Testdatenbank. Sie können dann ein Änderungsskript erstellen, das Ihre Änderungen enthält und das Sie nach der offline vorgenommenen Klärung auf die Originaldatenbank anwenden.</span><span class="sxs-lookup"><span data-stu-id="6b091-117">One way to avoid problems is to work in a copy of the database, such as a test database, when you make changes, then you can create a change script that you can run to make those changes on the original database after resolving conflicts offline.</span></span> <span data-ttu-id="6b091-118">Weitere Informationen finden Sie unter [Entwicklungs-, Test- und Produktionsdatenbanken &#40;Visual Database Tools&#41;](development-test-and-production-databases-visual-database-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6b091-118">For more information see [Development, Test, and Production Databases &#40;Visual Database Tools&#41;](development-test-and-production-databases-visual-database-tools.md).</span></span>  
  
  
