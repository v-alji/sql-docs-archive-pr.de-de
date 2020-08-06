---
title: Änderungsskript speichern (Dialogfeld) (Visual Database Tools) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ssms
ms.topic: conceptual
f1_keywords:
- vdt.dlgbox.generatechangescript
- vdtsql.chm:65544
ms.assetid: fc9d1639-5efa-44fe-a04f-4d4d0def2833
author: stevestein
ms.author: sstein
ms.openlocfilehash: 19a2bb2ce9a219c195421e2efa203fc115e1ae1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695085"
---
# <a name="save-change-script-dialog-box-visual-database-tools"></a><span data-ttu-id="2f81e-102">Änderungsskript speichern (Dialogfeld) (Visual Database Tools)</span><span class="sxs-lookup"><span data-stu-id="2f81e-102">Save Change Script Dialog Box (Visual Database Tools)</span></span>
  <span data-ttu-id="2f81e-103">Dieses Dialogfeld zeigt das [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skript für die Änderungen an, die Sie seit der letzten Speicherung der Tabelle vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="2f81e-103">This dialog box shows the [!INCLUDE[tsql](../../includes/tsql-md.md)] script for the changes you have made since you last saved the table.</span></span> <span data-ttu-id="2f81e-104">Außerdem können Sie in diesem Dialogfeld das Skript an einem auszuwählenden Speicherort als Textdatei speichern.</span><span class="sxs-lookup"><span data-stu-id="2f81e-104">It also allows you to save the script to a text file at a location you choose.</span></span>  
  
 <span data-ttu-id="2f81e-105">Sie können auf dieses Dialogfeld nach dem Vornehmen nicht gespeicherter Änderungen einer Tabelle im Tabellen-Designer zugreifen.</span><span class="sxs-lookup"><span data-stu-id="2f81e-105">You can access this dialog box after you have made unsaved changes to a table in Table Designer.</span></span> <span data-ttu-id="2f81e-106">Klicken Sie im Menü **Tabellen-Designer** auf **Änderungsskript generieren**.</span><span class="sxs-lookup"><span data-stu-id="2f81e-106">On the **Table Designer** menu, click **Generate Change Script**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="2f81e-107">Änderungsskripts, die von Visual Database Tools zur Verfügung gestellt werden, enthalten keine Fehlerbehandlung.</span><span class="sxs-lookup"><span data-stu-id="2f81e-107">Change scripts provided by Visual Database Tools contain no error handling.</span></span> <span data-ttu-id="2f81e-108">Dabei wird angenommmen, dass seit dem Öffnen des Tools keine Datenbankobjekte geändert wurden, und dass deshalb keine änderungsbezogenen Probleme auftreten werden.</span><span class="sxs-lookup"><span data-stu-id="2f81e-108">They assume that database objects have not changed since the tool was opened, and that change-related problems will therefore not occur.</span></span> <span data-ttu-id="2f81e-109">Vor dem Ausführen des Änderungsskripts sollten Sie die entsprechenden Fehlerbehandlungsanweisungen einschließen.</span><span class="sxs-lookup"><span data-stu-id="2f81e-109">Before running a change script, you should include the appropriate error-handling statements.</span></span>  
  
## <a name="options"></a><span data-ttu-id="2f81e-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="2f81e-110">Options</span></span>  
 <span data-ttu-id="2f81e-111">**Änderungsskript automatisch nach jedem Speichern erstellen**</span><span class="sxs-lookup"><span data-stu-id="2f81e-111">**Automatically generate change script on every save**</span></span>  
 <span data-ttu-id="2f81e-112">Ist dieses Kontrollkästchen aktiviert, wird das Dialogfeld **Änderungsskript speichern** jedes Mal angezeigt, wenn Sie Änderungen an einer Tabelle speichern.</span><span class="sxs-lookup"><span data-stu-id="2f81e-112">If checked, the **Save Change Script** dialog box will appear any time you save changes to a table.</span></span>  
  
 <span data-ttu-id="2f81e-113">**Ja**</span><span class="sxs-lookup"><span data-stu-id="2f81e-113">**Yes**</span></span>  
 <span data-ttu-id="2f81e-114">Öffnen Sie das Dialogfeld **Speichern** , mit dem Sie den Speicherort für die Textdatei auswählen können.</span><span class="sxs-lookup"><span data-stu-id="2f81e-114">Bring up the **Save** dialog box where you can choose the location for the text file.</span></span>  
  
 <span data-ttu-id="2f81e-115">**Nein**</span><span class="sxs-lookup"><span data-stu-id="2f81e-115">**No**</span></span>  
 <span data-ttu-id="2f81e-116">Brechen Sie die Erstellung des Änderungsskripts ab.</span><span class="sxs-lookup"><span data-stu-id="2f81e-116">Cancel the creation of the change script.</span></span>  
  
  
