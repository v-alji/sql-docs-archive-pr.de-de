---
title: Kopieren von Tabellen von einem Daten Bank Diagramm in ein anderes (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- copying tables
- duplicating tables
ms.assetid: 155a4f09-9321-4887-a7d4-aa2ce6b51277
author: stevestein
ms.author: sstein
ms.openlocfilehash: 7e90c8f324e80f7c59674def06a77e93a5bf0cb1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695130"
---
# <a name="copy-tables-from-one-database-diagrams-to-another-visual-database-tools"></a><span data-ttu-id="4c71d-102">Kopieren von Tabellen von einem Datenbankdiagramm in ein anderes Datenbankdiagramm (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="4c71d-102">Copy Tables from One Database Diagrams to Another (Visual Database Tools)</span></span>
  <span data-ttu-id="4c71d-103">Sie können eine Tabelle innerhalb derselben Datenbank von einem Datenbankdiagramm in ein anderes kopieren.</span><span class="sxs-lookup"><span data-stu-id="4c71d-103">You can copy a table from one database diagram to another in the same database.</span></span>  
  
 <span data-ttu-id="4c71d-104">Durch das Kopieren einer Tabelle von einem Datenbankdiagramm in ein anderes Diagramm wird letzterem ein Verweis auf die Tabelle hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4c71d-104">Copying a table from one database diagram to another diagram adds a reference to the table in the second diagram.</span></span> <span data-ttu-id="4c71d-105">Die Tabelle wird jedoch nicht in die Datenbank dupliziert.</span><span class="sxs-lookup"><span data-stu-id="4c71d-105">The table is not duplicated in your database.</span></span> <span data-ttu-id="4c71d-106">Wenn Sie beispielsweise die Tabelle `authors` von einem Datenbankdiagramm in ein anderes kopieren, verweisen beide Diagramme auf dieselbe Tabelle `authors` in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="4c71d-106">For example, if you copy the `authors` table from one database diagram to another, each diagram references the same `authors` table in the database.</span></span>  
  
### <a name="to-copy-a-table-from-another-database-diagram"></a><span data-ttu-id="4c71d-107">So kopieren Sie eine Tabelle von einem anderen Datenbankdiagramm</span><span class="sxs-lookup"><span data-stu-id="4c71d-107">To copy a table from another database diagram</span></span>  
  
1.  <span data-ttu-id="4c71d-108">Vergewissern Sie sich, dass Sie mit der Datenbank verbunden sind, deren Tabelle Sie kopieren möchten.</span><span class="sxs-lookup"><span data-stu-id="4c71d-108">Make sure you are connected to the database whose table you want to copy.</span></span>  
  
2.  <span data-ttu-id="4c71d-109">Öffnen Sie im Ausgangsdiagramm sowohl das Ausgangs- als auch das Zieldiagramm, und markieren Sie die Tabelle, die in das Zieldiagramm kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c71d-109">Open the source and target database diagrams and within the source diagram, select the table that you want to copy to the target diagram.</span></span>  
  
3.  <span data-ttu-id="4c71d-110">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Kopieren** .</span><span class="sxs-lookup"><span data-stu-id="4c71d-110">Click the **Copy** button on the toolbar.</span></span> <span data-ttu-id="4c71d-111">Dadurch wird die ausgewählte Tabellendefinition in die Zwischenablage kopiert.</span><span class="sxs-lookup"><span data-stu-id="4c71d-111">This action places the selected table definition on the Clipboard.</span></span>  
  
4.  <span data-ttu-id="4c71d-112">Wechseln Sie zum Zieldiagramm.</span><span class="sxs-lookup"><span data-stu-id="4c71d-112">Switch to the target diagram.</span></span> <span data-ttu-id="4c71d-113">Dieses Diagramm muss sich in derselben Datenbank befinden wie das Ausgangsdiagramm.</span><span class="sxs-lookup"><span data-stu-id="4c71d-113">This diagram must be in the same database as the source diagram.</span></span>  
  
5.  <span data-ttu-id="4c71d-114">Klicken Sie auf der Symbolleiste auf die Schaltfläche **Einfügen** .</span><span class="sxs-lookup"><span data-stu-id="4c71d-114">Click the **Paste** button on the toolbar.</span></span> <span data-ttu-id="4c71d-115">Der Inhalt der Zwischenablage wird nun an der neuen Stelle angezeigt und bleibt hervorgehoben, bis Sie auf eine andere Stelle klicken.</span><span class="sxs-lookup"><span data-stu-id="4c71d-115">The Clipboard contents appear at the new location and remain highlighted until you click elsewhere.</span></span> <span data-ttu-id="4c71d-116">Wenn Beziehungen zwischen den ausgewählten Tabellen und anderen Tabellen im Zieldiagramm bestehen, werden automatisch Beziehungslinien gezogen.</span><span class="sxs-lookup"><span data-stu-id="4c71d-116">If relationships exist between the selected tables and other tables in the target diagram, relationship lines are automatically drawn.</span></span>  
  
 <span data-ttu-id="4c71d-117">Wenn Sie die Tabelle in einem der beiden Diagramme bearbeiten, wirken sich die Änderungen auf beide Diagramme aus.</span><span class="sxs-lookup"><span data-stu-id="4c71d-117">When you edit the table in either diagram, your changes are reflected in both diagrams.</span></span> <span data-ttu-id="4c71d-118">Ähnliches gilt für das Speichern der Tabelle. Wenn Sie die Tabelle in einem der beiden Diagramme speichern, gilt sie in beiden Diagrammen nicht mehr als "verändert".</span><span class="sxs-lookup"><span data-stu-id="4c71d-118">Similarly, once you save the table in either diagram, the table is no longer considered "modified" in either diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c71d-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c71d-119">See Also</span></span>  
 <span data-ttu-id="4c71d-120">[Arbeiten mit Daten Bank Diagrammen &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="4c71d-120">[Work with Database Diagrams &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="4c71d-121">Hinzufügen von Tabellen zu Diagrammen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="4c71d-121">Add Tables to Diagrams &#40;Visual Database Tools&#41;</span></span>](add-tables-to-diagrams-visual-database-tools.md)  
  
  
