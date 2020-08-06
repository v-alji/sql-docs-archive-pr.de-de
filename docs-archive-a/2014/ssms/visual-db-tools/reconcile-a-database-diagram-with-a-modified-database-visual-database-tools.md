---
title: Abgleichen eines Daten Bank Diagramms mit einer geänderten Datenbank (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
helpviewer_keywords:
- updating diagram to match database
- reconciling database diagrams
- diagrams [SQL Server], reconciling changes
- updating database to match diagram
- database diagrams [SQL Server], reconciling changes
ms.assetid: eda8dea2-eedd-43a7-85aa-92bd97783b5f
author: stevestein
ms.author: sstein
ms.openlocfilehash: e5e5127ab613a6f791919a98899e40caa2ddac20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697337"
---
# <a name="reconcile-a-database-diagram-with-a-modified-database-visual-database-tools"></a><span data-ttu-id="2d185-102">Abgleichen eines Datenbankdiagramms mit einer geänderten Datenbank (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2d185-102">Reconcile a Database Diagram with a Modified Database (Visual Database Tools)</span></span>
  <span data-ttu-id="2d185-103">Ein Datenbankdiagramm wird gespeichert, wenn die Datenbank mit dem Diagramm aktualisiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="2d185-103">You save your database diagram when you are ready to update the database to match your diagram.</span></span> <span data-ttu-id="2d185-104">Wenn die Datenbank jedoch von anderen Benutzern aktualisiert wurde, während Ihr Diagramm geöffnet war, können sich die Änderungen der anderen Benutzer auf Ihr Diagramm auswirken und umgekehrt.</span><span class="sxs-lookup"><span data-stu-id="2d185-104">However, if other users have updated the database since you opened your diagram, their changes might affect your diagram and vice versa.</span></span>  
  
 <span data-ttu-id="2d185-105">Beim Speichern des Diagramms wird die Datenbank mit dem Diagramm abgeglichen. Die Änderungen anderer Benutzer werden dabei überschrieben, sodass die Daten in der Datenbank mit Ihrem Diagramm übereinstimmen.</span><span class="sxs-lookup"><span data-stu-id="2d185-105">Saving your diagram will reconcile the database with your diagram by overwriting other users' changes so that the database will match your diagram.</span></span>  
  
### <a name="to-update-a-database-to-match-your-diagram"></a><span data-ttu-id="2d185-106">So aktualisieren Sie eine Datenbank anhand der Daten des Diagramms</span><span class="sxs-lookup"><span data-stu-id="2d185-106">To update a database to match your diagram</span></span>  
  
1.  <span data-ttu-id="2d185-107">Speichern Sie das Datenbankdiagramm.</span><span class="sxs-lookup"><span data-stu-id="2d185-107">Save your database diagram.</span></span>  
  
     <span data-ttu-id="2d185-108">Wenn Sie das Diagramm zum ersten Mal speichern, geben Sie im Dialogfeld **Neue(s) Datenbankdiagramm speichern** einen Namen für das Diagramm ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2d185-108">If you have not previously saved your diagram, type a name for the diagram in the **Save New Database Diagram** dialog box and choose **OK**.</span></span>  
  
2.  <span data-ttu-id="2d185-109">Im Dialogfeld **Speichern** werden die Tabellen aufgeführt, auf die sich das Speichern des Diagramms auswirkt.</span><span class="sxs-lookup"><span data-stu-id="2d185-109">The **Save** dialog box lists the tables that will be affected when you save your diagram.</span></span> <span data-ttu-id="2d185-110">Wählen Sie **Ja** , um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="2d185-110">Choose **Yes** to continue.</span></span>  
  
3.  <span data-ttu-id="2d185-111">Im Dialogfeld **Es wurden Änderungen in der Datenbank festgestellt** werden die Objekte aufgeführt, die bearbeitet wurden und geändert werden müssen, um eine Übereinstimmung mit dem Diagramm zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="2d185-111">The **Database Changes Detected** dialog box lists the objects that were modified and will be changed to match your diagram.</span></span> <span data-ttu-id="2d185-112">Wählen Sie **Ja** , um das Diagramm zu speichern und die Liste der Änderungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="2d185-112">Choose **Yes** to save the diagram and accept the list of changes.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="2d185-113">Wenn das Diagramm Tabellen und Spalten enthält, die in der Datenbank gelöscht wurden, werden beim Speichern des Diagramms nur die zugehörigen Definitionen in der Datenbank neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="2d185-113">If your diagram contains tables and columns that were deleted in the database, only their definitions are recreated in the database when you save your diagram.</span></span> <span data-ttu-id="2d185-114">Die Daten, die diese Objekte vor dem Löschen enthielten, können mit diesem Prozess nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="2d185-114">This process does not restore any data that existed in these objects before their deletion.</span></span>  
  
### <a name="to-update-your-diagram-to-match-a-modified-database"></a><span data-ttu-id="2d185-115">So aktualisieren Sie das Diagramm anhand der Daten einer geänderten Datenbank</span><span class="sxs-lookup"><span data-stu-id="2d185-115">To update your diagram to match a modified database</span></span>  
  
1.  <span data-ttu-id="2d185-116">Schließen Sie das Diagramm, ohne die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2d185-116">Close your diagram without saving changes.</span></span>  
  
2.  <span data-ttu-id="2d185-117">Klicken Sie im Objekt-Explorer mit der rechten Maustaste auf das Diagramm.</span><span class="sxs-lookup"><span data-stu-id="2d185-117">Right-click the diagram in Object Explorer.</span></span>  
  
3.  <span data-ttu-id="2d185-118">Klicken Sie im Kontextmenü auf **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="2d185-118">From the shortcut menu click **Refresh**.</span></span>  
  
4.  <span data-ttu-id="2d185-119">Öffnen Sie das Diagramm erneut.</span><span class="sxs-lookup"><span data-stu-id="2d185-119">Reopen the diagram.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2d185-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2d185-120">See Also</span></span>  
 [<span data-ttu-id="2d185-121">Verwenden von Datenbankdiagrammen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="2d185-121">Work with Database Diagrams &#40;Visual Database Tools&#41;</span></span>](visual-database-tools.md)  
  
  
