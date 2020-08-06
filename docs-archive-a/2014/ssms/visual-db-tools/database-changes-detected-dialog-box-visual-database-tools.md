---
title: Es wurden Änderungen in der Datenbank festgestellt (Dialogfeld) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.schema.databasechangesdetected
- vdtsql.chm:65543
- vdtsql.chm:65554
ms.assetid: 91f13086-371f-46a2-9f46-804c1415f3ed
author: stevestein
ms.author: sstein
ms.openlocfilehash: 91d58e812b93f207d592d245d094b0fbeddcce72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699068"
---
# <a name="database-changes-detected-dialog-box-visual-database-tools"></a><span data-ttu-id="6375b-102">Es wurden Änderungen in der Datenbank festgestellt (Dialogfeld) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="6375b-102">Database Changes Detected Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="6375b-103">Dieses Dialogfeld wird angezeigt, wenn Sie ein Datenbankdiagramm oder ausgewählte Tabellen speichern möchten, jedoch einige der Datenbankobjekte, auf die sich der Speichervorgang auswirkt, in Bezug auf die Datenbank veraltet sind.</span><span class="sxs-lookup"><span data-stu-id="6375b-103">This dialog appears if you attempt to save a database diagram or selected tables but some of the database objects that will be affected by the save action are out of date with the database.</span></span> <span data-ttu-id="6375b-104">Das Übernehmen der in diesem Dialogfeld angezeigten Änderungen führt dazu, dass die Datenbank entsprechend dem Diagramm aktualisiert wird und Änderungen anderer Benutzer überschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="6375b-104">Accepting the changes shown in this dialog box updates the database to match your diagram and overwrites other users' changes.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6375b-105">Die in einer Tabelle oder einem Datenbankdiagramm vorgenommenen Änderungen können zwar nicht rückgängig gemacht werden, doch werden sie erst dann in der Datenbank gespeichert, wenn Sie die Tabelle bzw. das Diagramm speichern.</span><span class="sxs-lookup"><span data-stu-id="6375b-105">Although you cannot undo changes made to a table or database diagram, the changes are not saved to the database until you save the table or diagram.</span></span> <span data-ttu-id="6375b-106">Sie können nicht gespeicherte Änderungen verwerfen, indem Sie **Nein** auswählen und alle geöffneten Diagramme schließen, ohne sie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6375b-106">You can discard any unsaved changes by choosing **No** and closing all open diagrams without saving them.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6375b-107">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6375b-107">Options</span></span>  
 <span data-ttu-id="6375b-108">**Warnung bei Unterschiederkennung**</span><span class="sxs-lookup"><span data-stu-id="6375b-108">**Warn about difference detection**</span></span>  
 <span data-ttu-id="6375b-109">Geben Sie an, ob dieses Dialogfeld beim nächsten Versuch angezeigt wird, ein Datenbankdiagramm oder ausgewählte Tabellen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6375b-109">Specify whether this dialog box appears the next time you attempt to save a database diagram or selected tables.</span></span> <span data-ttu-id="6375b-110">Wenn diese Option aktiviert ist, wird das Dialogfeld weiterhin immer dann angezeigt, wenn Sie ein Diagramm oder eine Tabelle speichern, das bzw. die in Bezug auf die Datenbank veraltet ist.</span><span class="sxs-lookup"><span data-stu-id="6375b-110">Checked means that the dialog box continues to appear each time you save a diagram or table that is out of date with the database.</span></span> <span data-ttu-id="6375b-111">Ist die Option deaktiviert, wird das Dialogfeld nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6375b-111">Unchecked means that the dialog box does not appear.</span></span> <span data-ttu-id="6375b-112">Dieses Kontrollkästchen ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6375b-112">By default, this box is checked.</span></span> <span data-ttu-id="6375b-113">Wenn Sie diese Option deaktivieren, können Sie sie im Dialogfeld **Optionen** erneut aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6375b-113">If you uncheck this option, you can recheck it in the **Options** dialog box.</span></span>  
  
 <span data-ttu-id="6375b-114">**Ja**</span><span class="sxs-lookup"><span data-stu-id="6375b-114">**Yes**</span></span>  
 <span data-ttu-id="6375b-115">Aktualisieren Sie die Datenbank mit allen in der Liste aufgeführten Änderungen.</span><span class="sxs-lookup"><span data-stu-id="6375b-115">Update the database with all the changes shown in the list.</span></span>  
  
 <span data-ttu-id="6375b-116">**Nein**</span><span class="sxs-lookup"><span data-stu-id="6375b-116">**No**</span></span>  
 <span data-ttu-id="6375b-117">Brechen Sie den Speichervorgang ab.</span><span class="sxs-lookup"><span data-stu-id="6375b-117">Cancel the save action.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6375b-118">Um das Diagramm anhand der Datenbank zu aktualisieren, schließen Sie es, ohne Änderungen zu speichern. Klicken Sie im Server-Explorer mit der rechten Maustaste auf das Diagramm, und klicken Sie dann auf Aktualisieren. Öffnen Sie anschließend das Diagramm erneut.</span><span class="sxs-lookup"><span data-stu-id="6375b-118">To refresh your diagram to match the database, close it without saving changes, right-click the diagram in Server Explorer and click Refresh, and then reopen the diagram.</span></span>  
  
 <span data-ttu-id="6375b-119">**Textdatei speichern**</span><span class="sxs-lookup"><span data-stu-id="6375b-119">**Save Text File**</span></span>  
 <span data-ttu-id="6375b-120">Zeigen Sie das Dialogfeld **Speichern unter** an, in dem Sie einen Speicherort für eine Textdatei mit einer Liste der Datenbankänderungen angeben können.</span><span class="sxs-lookup"><span data-stu-id="6375b-120">Display the **Save As** dialog box, letting you specify a location for a text file containing a list of the database changes.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6375b-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6375b-121">See Also</span></span>  
 <span data-ttu-id="6375b-122">[Abstimmen eines Daten Bank Diagramms mit einer geänderten Datenbank &#40;Visual Database Tools&#41;](visual-database-tools.md) </span><span class="sxs-lookup"><span data-stu-id="6375b-122">[Reconcile a Database Diagram with a Modified Database &#40;Visual Database Tools&#41;](visual-database-tools.md) </span></span>  
 [<span data-ttu-id="6375b-123">Mehrbenutzerumgebungen &#40;Visual Database Tools&#41;</span><span class="sxs-lookup"><span data-stu-id="6375b-123">Multiuser Environments &#40;Visual Database Tools&#41;</span></span>](multiuser-environments-visual-database-tools.md)  
  
  
