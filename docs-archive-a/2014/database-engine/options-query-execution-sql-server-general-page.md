---
title: Optionen (Abfrage Ausführung-SQL Server Seite "Allgemein") | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.QueryExecution.SqlServer.SqlExecutionGeneral
ms.assetid: 3f8d59bc-3f97-4e5d-8b86-5ac670d20780
author: rothja
ms.author: jroth
ms.openlocfilehash: eaa95293636d02674fb720dcd1b8146279f78e72
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621642"
---
# <a name="options-query-execution-sql-server-general-page"></a><span data-ttu-id="6f7d2-102">Optionen (Abfrage Ausführung-SQL Server Seite "Allgemein")</span><span class="sxs-lookup"><span data-stu-id="6f7d2-102">Options (Query Execution-SQL Server-General Page)</span></span>
  <span data-ttu-id="6f7d2-103">Auf dieser Seite können Sie die Optionen zum Ausführen von Abfragen in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] angeben.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-103">Use this page to specify the options for running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="6f7d2-104">Die an diesen Optionen vorgenommenen Änderungen werden nur auf neue [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]-Abfragen angewendet.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-104">Changes to these options are only applied to new [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] queries.</span></span> <span data-ttu-id="6f7d2-105">Um diese Optionen für eine aktuelle Abfrage zu ändern, klicken Sie entweder im Menü **Abfrage** auf **Abfrageoptionen**, oder klicken Sie mit der rechten Maustaste in ein Abfragefenster von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], und wählen Sie dann **Abfrageoptionen** aus.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-105">To change the options for a current query, click **Query Options** on the **Query** menu, or in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Query window right-click and select **Query Options**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="6f7d2-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="6f7d2-106">Options</span></span>  
 <span data-ttu-id="6f7d2-107">**SET ROWCOUNT**</span><span class="sxs-lookup"><span data-stu-id="6f7d2-107">**SET ROWCOUNT**</span></span>  
 <span data-ttu-id="6f7d2-108">Der Standardwert 0 zeigt an, dass [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] so lange auf die Ergebnisse wartet, bis alle Ergebnisse übermittelt sind.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-108">The default value of 0 indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will wait for results until all results are received.</span></span> <span data-ttu-id="6f7d2-109">Geben Sie einen Wert größer 0 an, wenn die Abfrage von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] nach Übermittlung einer bestimmten Anzahl von Zeilen abgebrochen werden soll.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-109">Provide a value greater than 0 if you want [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] to halt the query after obtaining the specified number of rows.</span></span> <span data-ttu-id="6f7d2-110">Geben Sie SET ROWCOUNT 0 an, um diese Option zu deaktivieren (sodass alle Zeilen zurückgegeben werden).</span><span class="sxs-lookup"><span data-stu-id="6f7d2-110">To turn this option off (so that all rows are returned), specify SET ROWCOUNT 0.</span></span>  
  
 <span data-ttu-id="6f7d2-111">**SET TEXTSIZE**</span><span class="sxs-lookup"><span data-stu-id="6f7d2-111">**SET TEXTSIZE**</span></span>  
 <span data-ttu-id="6f7d2-112">Der Standardwert 2.147.483.647 Bytes zeigt an, dass [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] vollständige Datenfelder bereitstellt, die maximal der Größe von Datenfeldern vom Typ `text` und `ntext` entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-112">The default value of 2,147,483,647 bytes indicates that [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] will provide complete data fields up to the limit of `text` and `ntext` data fields.</span></span> <span data-ttu-id="6f7d2-113">Geben Sie eine kleinere Zahl an, um Ergebnisse mit großen Werten zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-113">Provide a smaller number to limit results in the case of large values.</span></span> <span data-ttu-id="6f7d2-114">Spalten, deren Größe die angegebene Zahl übersteigt, werden abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-114">Columns greater than the number provided will be truncated.</span></span>  
  
 <span data-ttu-id="6f7d2-115">**Ausführungs Timeout**</span><span class="sxs-lookup"><span data-stu-id="6f7d2-115">**Execution time-out**</span></span>  
 <span data-ttu-id="6f7d2-116">Legt den Standardwert im Dialogfeld **Neue Verbindung** fest.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-116">Sets the default value in the **New Connection** dialog box.</span></span> <span data-ttu-id="6f7d2-117">Mithilfe dieses Drehfelds können Sie angeben, nach wie vielen Sekunden [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] die Abfrage abbrechen soll.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-117">Use this spin box to tell [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] the number of seconds to wait before canceling the query.</span></span> <span data-ttu-id="6f7d2-118">Der Wert 0 gibt eine unbegrenzte Wartezeit oder kein Timeout an. Dieser Wert ist bei einer neuen Installation 0 (null).</span><span class="sxs-lookup"><span data-stu-id="6f7d2-118">A value of 0 indicates an infinite wait, or no time-out. This value is 0 on a new installation.</span></span>  
  
 <span data-ttu-id="6f7d2-119">**Batchtrennzeichen**</span><span class="sxs-lookup"><span data-stu-id="6f7d2-119">**Batch separator**</span></span>  
 <span data-ttu-id="6f7d2-120">Geben Sie ein Wort ein, das verwendet werden soll, um [!INCLUDE[tsql](../includes/tsql-md.md)]-Anweisungen in Batches zu trennen.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-120">Type a word that you use to separate [!INCLUDE[tsql](../includes/tsql-md.md)] statements into batches.</span></span> <span data-ttu-id="6f7d2-121">Der Standardwert ist GO.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-121">The default is GO.</span></span>  
  
 <span data-ttu-id="6f7d2-122">**Standardmäßig neue Abfragen im SQLCMD-Modus öffnen**</span><span class="sxs-lookup"><span data-stu-id="6f7d2-122">**By default, open new queries in SQLCMD Mode**</span></span>  
 <span data-ttu-id="6f7d2-123">Aktivieren Sie dieses Kontrollkästchen, um neue Abfragen im SQLCMD-Modus zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-123">Select this check box to open new queries in SQLCMD mode.</span></span> <span data-ttu-id="6f7d2-124">Weitere Informationen zum SQLCMD-Modus finden Sie unter [Bearbeiten von SQLCMD-Skripts mit dem Abfrage-Editor](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md).</span><span class="sxs-lookup"><span data-stu-id="6f7d2-124">For more information about SQLCMD mode, see [Edit SQLCMD Scripts with Query Editor](../relational-databases/scripting/edit-sqlcmd-scripts-with-query-editor.md).</span></span>  
  
 <span data-ttu-id="6f7d2-125">Beachten Sie die folgenden Einschränkungen, wenn Sie diese Option auswählen:</span><span class="sxs-lookup"><span data-stu-id="6f7d2-125">When you select this option, be aware of the following limitations:</span></span>  
  
-   <span data-ttu-id="6f7d2-126">IntelliSense im [!INCLUDE[ssDE](../includes/ssde-md.md)] -Abfrage-Editor ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-126">IntelliSense in the [!INCLUDE[ssDE](../includes/ssde-md.md)] Query Editor is turned off.</span></span>  
  
-   <span data-ttu-id="6f7d2-127">Da der Abfrage-Editor nicht über die Befehlszeile ausgeführt werden kann, ist es nicht möglich, Befehlszeilenparameter, z. B. Variablen, zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-127">Because Query Editor does not run from the command line, you cannot pass in command-line parameters such as variables.</span></span>  
  
-   <span data-ttu-id="6f7d2-128">Da der Abfrage-Editor nicht auf Anforderungen des Betriebssystems reagieren kann, müssen Sie darauf achten, keine interaktiven Anweisungen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-128">Because Query Editor cannot respond to operating-system prompts, you must be careful not to run interactive statements.</span></span>  
  
 <span data-ttu-id="6f7d2-129">**Standard wiederherstellen**</span><span class="sxs-lookup"><span data-stu-id="6f7d2-129">**Reset to Default**</span></span>  
 <span data-ttu-id="6f7d2-130">Klicken Sie hier, um alle auf dieser Seite verfügbaren Werte auf die ursprünglichen Standardwerte zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="6f7d2-130">Click to reset all values on this page to the original default values.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f7d2-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f7d2-131">See Also</span></span>  
 [<span data-ttu-id="6f7d2-132">SQLCMD-Hilfsprogramm</span><span class="sxs-lookup"><span data-stu-id="6f7d2-132">sqlcmd Utility</span></span>](../tools/sqlcmd-utility.md)  
  
  
