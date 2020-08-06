---
title: Erstellen eines Skriptes für eine Tabelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
ms.assetid: ea88d736-849e-4368-b55d-06aeee097bf3
author: stevestein
ms.author: sstein
ms.openlocfilehash: 247c839d83768756c57297d47f952401a1c8fd46
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616299"
---
# <a name="script-a-table"></a><span data-ttu-id="55242-102">Erstellen eines Skriptes für eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="55242-102">Script a Table</span></span>
  [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] <span data-ttu-id="55242-103">können Skripts für das Auswählen, Einfügen, Aktualisieren und Löschen von Tabellen und das Anlegen, Ändern, Löschen und Ausführen von gespeicherten Prozeduren erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="55242-103">can create scripts to select, insert, update, and delete tables, and to create, alter, drop, or execute stored procedures.</span></span>  
  
 <span data-ttu-id="55242-104">Möglicherweise benötigen Sie in einigen Fällen ein Skript mit mehreren Optionen, wie z. B. zum Löschen einer Prozedur und dann zum Anlegen einer Prozedur oder zum Anlegen einer Tabelle und dann zum Ändern einer Tabelle.</span><span class="sxs-lookup"><span data-stu-id="55242-104">Sometimes you want a script with multiple options, such as drop a procedure and then create a procedure, or create a table then alter a table.</span></span> <span data-ttu-id="55242-105">Zum Anlegen kombinierter Skripts speichern Sie das erste Skript in einem Abfrage-Editorfenster und das zweite in der Zwischenablage, sodass Sie es im Fenster nach dem ersten Skript einfügen können.</span><span class="sxs-lookup"><span data-stu-id="55242-105">To create combined scripts, save the first script to a Query Editor window and the second to the clipboard so you can paste it into the window after the first script.</span></span>  
  
## <a name="creating-an-update-script"></a><span data-ttu-id="55242-106">Anlegen eines Updateskripts</span><span class="sxs-lookup"><span data-stu-id="55242-106">Creating an Update Script</span></span>  
  
#### <a name="to-create-the-insert-script-for-a-table"></a><span data-ttu-id="55242-107">So erstellen Sie ein Skript zum Einfügen in eine Tabelle</span><span class="sxs-lookup"><span data-stu-id="55242-107">To create the insert script for a table</span></span>  
  
1.  <span data-ttu-id="55242-108">Erweitern Sie im Objekt-Explorer Ihren Server, erweitern Sie **Datenbanken**, erweitern Sie [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)]und **Tabellen**, klicken Sie mit der rechten Maustaste auf **HumanResources.Employee**, und zeigen Sie anschließend auf **Skript für Tabelle als**.</span><span class="sxs-lookup"><span data-stu-id="55242-108">In Object Explorer, expand your server, expand **Databases**, expand [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)], expand **Tables**, right-click **HumanResources.Employee**, and then point to **Script Table As**.</span></span>  
  
2.  <span data-ttu-id="55242-109">Das Kontextmenü umfasst sieben Optionen für Skripts: **CREATE in**, **DROP in**, **DROP und CREATE in**, **SELECT in**, **INSERT in**, **UPDATE in**und **DELETE in**.</span><span class="sxs-lookup"><span data-stu-id="55242-109">The shortcut menu has seven available scripting options: **CREATE To**, **DROP To**, **DROP and CREATE To**, **SELECT To**, **INSERT To**, **UPDATE To**, and **DELETE To**.</span></span> <span data-ttu-id="55242-110">Zeigen Sie auf **UPDATE in**, und klicken Sie dann auf **Neues Abfrage-Editorfenster**.</span><span class="sxs-lookup"><span data-stu-id="55242-110">Point to **UPDATE To**, and then click **New Query Editor Window**.</span></span>  
  
3.  <span data-ttu-id="55242-111">Ein neues Abfrage-Editorfenster wird geöffnet, eine Verbindung wird hergestellt, und die gesamte Update-Anweisung wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55242-111">A new Query Editor window opens, makes a connection, and presents the entire update statement.</span></span>  
  
     <span data-ttu-id="55242-112">Diese Übung zeigt Ihnen, dass die Funktion zur Skripterstellung mehr bietet als das Schreiben eines Skripts zum Anlegen einer Tabelle oder gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="55242-112">This exercise demonstrates how the scripting feature can do more than just script the creation of a table or stored procedure.</span></span> <span data-ttu-id="55242-113">Diese neue Funktion unterstützt Sie, wenn Sie Ihrem Projekt schnell Skripts für Datenänderungen hinzufügen möchten. Es hilft Ihnen beim einfachen Erstellen von Skripts für die Ausführung gespeicherter Prozeduren.</span><span class="sxs-lookup"><span data-stu-id="55242-113">This new feature can help you quickly add data manipulation scripts to your project and easily script execution of stored procedures.</span></span> <span data-ttu-id="55242-114">So können Sie in vielen Bereichen viel Zeit bei der Arbeit mit Tabellen und Prozeduren sparen.</span><span class="sxs-lookup"><span data-stu-id="55242-114">This can be a big timesaver for tables and procedures with many fields.</span></span>  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="55242-115">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="55242-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="55242-116">Zusammenfassung: Schreiben von Transact-SQL-Code</span><span class="sxs-lookup"><span data-stu-id="55242-116">Summary: Writing Transact-SQL</span></span>](../../tutorials/summary-writing-transact-sql.md)  
  
  
