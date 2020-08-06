---
title: Editor für den Task ' SQL ausführen ' (Seite Resultset) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.executesqltask.resultset.f1
helpviewer_keywords:
- Execute SQL Task Editor
ms.assetid: d27000c8-8d91-4e1c-b45e-bca9a3c12f6d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 027f3c77e84b47958e9fb6567acdb308c14eb1e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616122"
---
# <a name="execute-sql-task-editor-result-set-page"></a><span data-ttu-id="e408c-102">Editor für den Task 'SQL ausführen' (Seite Resultset)</span><span class="sxs-lookup"><span data-stu-id="e408c-102">Execute SQL Task Editor (Result Set Page)</span></span>
  <span data-ttu-id="e408c-103">Mithilfe der Seite **Resultset** des Dialogfelds **Editor für den Task 'SQL ausführen'** können Sie das Ergebnis der SQL-Anweisung neuen oder vorhandenen Variablen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="e408c-103">Use the **Result Set** page of the **Execute SQL Task Editor** dialog to map the result of the SQL statement to new or existing variables.</span></span> <span data-ttu-id="e408c-104">Die Optionen in diesem Dialogfeld sind deaktiviert, wenn auf der Seite Allgemein für **ResultSet** der Wert **Keine**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e408c-104">The options in this dialog box are disabled if **ResultSet** on the General page is set to **None**.</span></span>  
  
 <span data-ttu-id="e408c-105">Weitere Informationen zu diesem Task finden Sie unter [SQL ausführen (Task)](control-flow/execute-sql-task.md) und [Resultsets im Task „SQL ausführen“](../../2014/integration-services/result-sets-in-the-execute-sql-task.md).</span><span class="sxs-lookup"><span data-stu-id="e408c-105">For more information about this task, see [Execute SQL Task](control-flow/execute-sql-task.md) and [Result Sets in the Execute SQL Task](../../2014/integration-services/result-sets-in-the-execute-sql-task.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="e408c-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="e408c-106">Options</span></span>  
 <span data-ttu-id="e408c-107">**Ergebnisname**</span><span class="sxs-lookup"><span data-stu-id="e408c-107">**Result Name**</span></span>  
 <span data-ttu-id="e408c-108">Nachdem Sie durch Klicken auf **Hinzufügen**eine Resultsetzuordnung hinzugefügt haben, geben Sie einen Namen für das Ergebnis an.</span><span class="sxs-lookup"><span data-stu-id="e408c-108">After you have added a result set mapping set by clicking **Add**, provide a name for the result.</span></span> <span data-ttu-id="e408c-109">Je nach Resultsettyp müssen Sie bestimmte Ergebnisnamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e408c-109">Depending on the result set type, you must use specific result names.</span></span>  
  
 <span data-ttu-id="e408c-110">Für den Resultsettyp **Einzelne Zeile**können Sie entweder den Namen einer von der Abfrage zurückgegebenen Spalte verwenden oder die Zahl, die die Position einer Spalte in der von der Abfrage zurückgegebenen Spaltenliste angibt.</span><span class="sxs-lookup"><span data-stu-id="e408c-110">If the result set type is **Single row**, you can use either the name of a column returned by the query or the number that represents the position of a column in the column list of a column returned by the query.</span></span>  
  
 <span data-ttu-id="e408c-111">Für den Resultsettyp **Vollständiges Resultset** oder **XML**müssen Sie 0 als Resultsetnamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e408c-111">If the result set type is **Full result set** or **XML**, you must use 0 as the result set name.</span></span>  
  
 <span data-ttu-id="e408c-112">**Verwandte Themen**: [Konfigurieren von Resultsets im Task „SQL ausführen“](../../2014/integration-services/result-sets-in-the-execute-sql-task.md)</span><span class="sxs-lookup"><span data-stu-id="e408c-112">**Related Topics**: [Result Sets in the Execute SQL Task](../../2014/integration-services/result-sets-in-the-execute-sql-task.md)</span></span>  
  
 <span data-ttu-id="e408c-113">**Variablenname**</span><span class="sxs-lookup"><span data-stu-id="e408c-113">**Variable Name**</span></span>  
 <span data-ttu-id="e408c-114">Ordnen Sie das Resultset einer Variablen zu, indem Sie eine Variable auswählen, oder klicken Sie auf \<**New variable...**>, um mithilfe des Dialogfelds **Variable hinzufügen** eine neue Variable hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e408c-114">Map the result set to a variable by selecting a variable or click \<**New variable...**> to add a new variable by using the **Add Variable** dialog box.</span></span>  
  
 <span data-ttu-id="e408c-115">**Add (Hinzufügen)**</span><span class="sxs-lookup"><span data-stu-id="e408c-115">**Add**</span></span>  
 <span data-ttu-id="e408c-116">Klicken Sie auf diese Option, um eine Resultsetzuordnung hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e408c-116">Click to add a result set mapping.</span></span>  
  
 <span data-ttu-id="e408c-117">**Remove**</span><span class="sxs-lookup"><span data-stu-id="e408c-117">**Remove**</span></span>  
 <span data-ttu-id="e408c-118">Wählen Sie eine Resultsetzuordnung aus der Liste aus, und klicken Sie anschließend auf **Entfernen**.</span><span class="sxs-lookup"><span data-stu-id="e408c-118">Select a result set mapping in the list and then click **Remove**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e408c-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e408c-119">See Also</span></span>  
 <span data-ttu-id="e408c-120">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="e408c-120">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="e408c-121">[Editor für den Task ' SQL ausführen ' &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="e408c-121">[Execute SQL Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="e408c-122">[Editor für den Task ' SQL ausführen ' &#40;Seite Parameter Zuordnung&#41;](../../2014/integration-services/execute-sql-task-editor-parameter-mapping-page.md) </span><span class="sxs-lookup"><span data-stu-id="e408c-122">[Execute SQL Task Editor &#40;Parameter Mapping Page&#41;](../../2014/integration-services/execute-sql-task-editor-parameter-mapping-page.md) </span></span>  
 [<span data-ttu-id="e408c-123">Transact-SQL-Referenz &#40;Datenbank-Engine&#41;</span><span class="sxs-lookup"><span data-stu-id="e408c-123">Transact-SQL Reference &#40;Database Engine&#41;</span></span>](/sql/t-sql/language-reference)  
  
  
