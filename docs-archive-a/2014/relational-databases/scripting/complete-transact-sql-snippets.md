---
title: Abschließen von Transact-SQL-Ausschnitten
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- IntelliSense [SQL Server], completing snippets
- snippets [Transact-SQL], completing
- Transact-SQL snippets, completing
ms.assetid: a8316a58-bb57-485e-845f-84c23360314c
author: rothja
ms.author: jroth
ms.openlocfilehash: d90c77f72ba8ce80d26503645d9b04d795f5e503
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616446"
---
# <a name="complete-transact-sql-snippets"></a><span data-ttu-id="fe32a-102">Abschließen von Transact-SQL-Ausschnitten</span><span class="sxs-lookup"><span data-stu-id="fe32a-102">Complete Transact-SQL Snippets</span></span>
  <span data-ttu-id="fe32a-103">Sobald ein [!INCLUDE[tsql](../../includes/tsql-md.md)] -Codeausschnitt in ein Skript eingefügt wurde, bearbeiten Sie den Inhalt des Ausschnitts, um eine vollständige [!INCLUDE[tsql](../../includes/tsql-md.md)] -Anweisung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fe32a-103">Once a [!INCLUDE[tsql](../../includes/tsql-md.md)] code snippet has been inserted into a script, you edit the contents of the snippet to build a complete [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
## <a name="completing-snippets"></a><span data-ttu-id="fe32a-104">Vervollständigen von Ausschnitten</span><span class="sxs-lookup"><span data-stu-id="fe32a-104">Completing Snippets</span></span>  
 <span data-ttu-id="fe32a-105">Wenn Sie dem Skript einen [!INCLUDE[tsql](../../includes/tsql-md.md)] -Ausschnitt hinzufügen, enthält die eingefügte Ausschnittanweisung einen oder mehrere Ersetzungspunkte, die hervorgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="fe32a-105">When you add a [!INCLUDE[tsql](../../includes/tsql-md.md)] snippet to your script, the inserted snippet statement has one or more replacement points, which are highlighted.</span></span> <span data-ttu-id="fe32a-106">Wenn Sie mit der Maus auf einen Ersetzungspunkt zeigen, wird eine QuickInfo mit einer Beschreibung des Syntaxelements angezeigt, das Sie angeben können.</span><span class="sxs-lookup"><span data-stu-id="fe32a-106">If you rest your mouse pointer on a replacement point, a tooltip appears with a description of the syntax element you can specify.</span></span> <span data-ttu-id="fe32a-107">Der [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor erkennt den Ausschnitt als vom umgebenden Skript separaten Code, bis Sie die Quelldatei schließen.</span><span class="sxs-lookup"><span data-stu-id="fe32a-107">The [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor recognizes the snippet as separate from the surrounding script until you close the source file.</span></span> <span data-ttu-id="fe32a-108">Die Ersetzungspunkte bleiben aktiv, bis Sie die Quelldatei schließen.</span><span class="sxs-lookup"><span data-stu-id="fe32a-108">The replacement points remain active until you close the source file.</span></span>  
  
 <span data-ttu-id="fe32a-109">Sie können auch dem durch einen Ausschnitt eingefügten Vorlagencode zusätzliche Syntaxelemente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe32a-109">You can also add additional syntax elements to the template code inserted by a snippet.</span></span> <span data-ttu-id="fe32a-110">Beispielsweise werden mit der Ausschnittvorlage Tabelle erstellen zwei Spaltendefinitionen hinzugefügt. Sie müssen weitere Spaltendefinitionen hinzufügen, um eine Tabelle mit mehr als zwei Spalten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fe32a-110">For example, the Create Table snippet template generates two column definitions; you must add additional column definitions to create a table with more than two columns.</span></span>  
  
#### <a name="completing-the-snippet-statement"></a><span data-ttu-id="fe32a-111">Vervollständigen der Ausschnittanweisung</span><span class="sxs-lookup"><span data-stu-id="fe32a-111">Completing the Snippet Statement</span></span>  
  
1.  <span data-ttu-id="fe32a-112">Wechseln Sie mithilfe der TAB-TASTE von einem Ersetzungspunkt zum nächsten Ersetzungspunkt.</span><span class="sxs-lookup"><span data-stu-id="fe32a-112">Use the TAB key to move from one replacement point to the next.</span></span> <span data-ttu-id="fe32a-113">Mit UMSCHALT+TAB wechseln Sie zum vorherigen Ersetzungspunkt.</span><span class="sxs-lookup"><span data-stu-id="fe32a-113">Use SHIFT+TAB to move to the previous replacement point.</span></span>  
  
2.  <span data-ttu-id="fe32a-114">Drücken Sie STRG+LEERTASTE, um IntelliSense aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="fe32a-114">Click CTRL+SPACE to invoke IntelliSense.</span></span>  
  
3.  <span data-ttu-id="fe32a-115">Wählen Sie aus der Liste ein Element aus, oder geben Sie eine gewünschte Ersetzung ein.</span><span class="sxs-lookup"><span data-stu-id="fe32a-115">Select an item from the list, or type a replacement of your choice.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe32a-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fe32a-116">See Also</span></span>  
 <span data-ttu-id="fe32a-117">[Einfügen von Transact-SQL-Ausschnitten](insert-transact-sql-snippets.md) </span><span class="sxs-lookup"><span data-stu-id="fe32a-117">[Insert Transact-SQL Snippets](insert-transact-sql-snippets.md) </span></span>  
 [<span data-ttu-id="fe32a-118">Einfügen von Transact-SQL-Umschließungsausschnitten</span><span class="sxs-lookup"><span data-stu-id="fe32a-118">Insert Surround-with Transact-SQL snippets</span></span>](insert-surround-with-transact-sql-snippets.md)  
  
  
