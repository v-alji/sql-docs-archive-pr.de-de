---
title: Massen Einfügungs Task-Editor (Seite Optionen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.bulkinserttask.options.f1
helpviewer_keywords:
- Bulk Insert Task Editor
ms.assetid: b3702811-3eb8-4b28-9190-5ae7a1a7bb6f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1751d1e0ac01d5459a8c76e6a48626c2ad6deafd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722990"
---
# <a name="bulk-insert-task-editor-options-page"></a><span data-ttu-id="914ee-102">Masseneinfügungstask-Editor (Seite Optionen)</span><span class="sxs-lookup"><span data-stu-id="914ee-102">Bulk Insert Task Editor (Options Page)</span></span>
  <span data-ttu-id="914ee-103">Auf der Seite **Optionen** des Dialogfelds **Masseneinfügungstask-Editor** können Sie Eigenschaften für den Masseneinfügungsvorgang festlegen.</span><span class="sxs-lookup"><span data-stu-id="914ee-103">Use the **Options** page of the **Bulk Insert Task Editor** dialog box to set properties for the bulk insert operation.</span></span> <span data-ttu-id="914ee-104">Durch den Masseneinfügungstask werden große Datenmengen in eine Tabelle oder Sicht von [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] kopiert.</span><span class="sxs-lookup"><span data-stu-id="914ee-104">The Bulk Insert task copies large amounts of data into a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] table or view.</span></span>  
  
 <span data-ttu-id="914ee-105">Weitere Informationen zum Arbeiten mit Masseneinfügungen finden Sie unter [Masseneinfügungstask](control-flow/bulk-insert-task.md) und [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="914ee-105">To learn about working with bulk inserts, see [Bulk Insert Task](control-flow/bulk-insert-task.md) and [BULK INSERT &#40;Transact-SQL&#41;](/sql/t-sql/statements/bulk-insert-transact-sql).</span></span>  
  
## <a name="options"></a><span data-ttu-id="914ee-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="914ee-106">Options</span></span>  
 <span data-ttu-id="914ee-107">**CodePage**</span><span class="sxs-lookup"><span data-stu-id="914ee-107">**CodePage**</span></span>  
 <span data-ttu-id="914ee-108">Geben Sie die Codepage für die in der Datendatei enthaltenen Daten an.</span><span class="sxs-lookup"><span data-stu-id="914ee-108">Specify the code page of the data in the data file.</span></span>  
  
 <span data-ttu-id="914ee-109">**DataFileType**</span><span class="sxs-lookup"><span data-stu-id="914ee-109">**DataFileType**</span></span>  
 <span data-ttu-id="914ee-110">Geben Sie den Wert für den Datentyp an, der beim Ladevorgang verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="914ee-110">Specify the data-type value to use in the load operation.</span></span>  
  
 <span data-ttu-id="914ee-111">**BatchSize**</span><span class="sxs-lookup"><span data-stu-id="914ee-111">**BatchSize**</span></span>  
 <span data-ttu-id="914ee-112">Geben Sie die Anzahl der Zeilen in einem Batch an.</span><span class="sxs-lookup"><span data-stu-id="914ee-112">Specify the number of rows in a batch.</span></span> <span data-ttu-id="914ee-113">Der Standardwert ist die gesamte Datendatei.</span><span class="sxs-lookup"><span data-stu-id="914ee-113">The default is the entire data file.</span></span> <span data-ttu-id="914ee-114">Wenn Sie **BatchSize** auf null festlegen, werden die Daten in einem Batch geladen.</span><span class="sxs-lookup"><span data-stu-id="914ee-114">If you set **BatchSize** to zero, the data is loaded in a single batch.</span></span>  
  
 <span data-ttu-id="914ee-115">**LastRow**</span><span class="sxs-lookup"><span data-stu-id="914ee-115">**LastRow**</span></span>  
 <span data-ttu-id="914ee-116">Geben Sie die letzte zu kopierende Zeile an.</span><span class="sxs-lookup"><span data-stu-id="914ee-116">Specify the last row to copy.</span></span>  
  
 <span data-ttu-id="914ee-117">**FirstRow**</span><span class="sxs-lookup"><span data-stu-id="914ee-117">**FirstRow**</span></span>  
 <span data-ttu-id="914ee-118">Geben Sie die erste zu kopierende Zeile an.</span><span class="sxs-lookup"><span data-stu-id="914ee-118">Specify the first row from which to start copying.</span></span>  
  
 <span data-ttu-id="914ee-119">**Optionen**</span><span class="sxs-lookup"><span data-stu-id="914ee-119">**Options**</span></span>  
 |<span data-ttu-id="914ee-120">Begriff</span><span class="sxs-lookup"><span data-stu-id="914ee-120">Term</span></span>|<span data-ttu-id="914ee-121">Definition</span><span class="sxs-lookup"><span data-stu-id="914ee-121">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="914ee-122">**Check-Einschränkungen**</span><span class="sxs-lookup"><span data-stu-id="914ee-122">**Check constraints**</span></span>|<span data-ttu-id="914ee-123">Wählen Sie diese Option aus, um die Einschränkungen für Tabelle und Spalte zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="914ee-123">Select to check the table and column constraints.</span></span>|  
|<span data-ttu-id="914ee-124">**NULL-Werte beibehalten**</span><span class="sxs-lookup"><span data-stu-id="914ee-124">**Keep nulls**</span></span>|<span data-ttu-id="914ee-125">Wählen Sie diese Option aus, um NULL-Werte während des Masseneinfügungsvorgangs beizubehalten, statt für leere Spalten Standardwerte einzufügen.</span><span class="sxs-lookup"><span data-stu-id="914ee-125">Select to retain null values during the bulk insert operation, instead of inserting any default values for empty columns.</span></span>|  
|<span data-ttu-id="914ee-126">**IDENTITY_INSERT aktivieren**</span><span class="sxs-lookup"><span data-stu-id="914ee-126">**Enable identity insert**</span></span>|<span data-ttu-id="914ee-127">Wählen Sie diese Option aus, um vorhandene Werte in eine Identitätsspalte einzufügen.</span><span class="sxs-lookup"><span data-stu-id="914ee-127">Select to insert existing values into an identity column.</span></span>|  
|<span data-ttu-id="914ee-128">**Tabellensperre**</span><span class="sxs-lookup"><span data-stu-id="914ee-128">**Table lock**</span></span>|<span data-ttu-id="914ee-129">Wählen Sie diese Option aus, um die Tabelle während des Masseneinfügungsvorgangs zu sperren.</span><span class="sxs-lookup"><span data-stu-id="914ee-129">Select to lock the table during the bulk insert.</span></span>|  
|<span data-ttu-id="914ee-130">**Trigger auslösen**</span><span class="sxs-lookup"><span data-stu-id="914ee-130">**Fire triggers**</span></span>|<span data-ttu-id="914ee-131">Wählen Sie diese Option aus, um das Einfügen, Aktualisieren oder Löschen von Triggern für die Tabelle auszulösen.</span><span class="sxs-lookup"><span data-stu-id="914ee-131">Select to fire any insert, update, or delete triggers on the table.</span></span>|  
  
 <span data-ttu-id="914ee-132">**SortedData**</span><span class="sxs-lookup"><span data-stu-id="914ee-132">**SortedData**</span></span>  
 <span data-ttu-id="914ee-133">Geben Sie die ORDER BY-Klausel in der BULK INSERT-Anweisung an.</span><span class="sxs-lookup"><span data-stu-id="914ee-133">Specify the ORDER BY clause in the bulk insert statement.</span></span> <span data-ttu-id="914ee-134">Der Name der angegebenen Spalte muss eine gültige Spalte in der Zieltabelle sein.</span><span class="sxs-lookup"><span data-stu-id="914ee-134">The column name that you supply must be a valid column in the destination table.</span></span> <span data-ttu-id="914ee-135">Der Standardwert lautet `false`.</span><span class="sxs-lookup"><span data-stu-id="914ee-135">The default is `false`.</span></span> <span data-ttu-id="914ee-136">Das bedeutet, dass die Daten nicht durch eine ORDER BY-Klausel sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="914ee-136">This means that the data is not sorted by an ORDER BY clause.</span></span>  
  
 <span data-ttu-id="914ee-137">**MaxErrors**</span><span class="sxs-lookup"><span data-stu-id="914ee-137">**MaxErrors**</span></span>  
 <span data-ttu-id="914ee-138">Geben Sie an, wie viele Fehler maximal auftreten müssen, bevor der Masseneinfügungsvorgang abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="914ee-138">Specify the maximum number of errors that can occur before the bulk insert operation is canceled.</span></span> <span data-ttu-id="914ee-139">Durch den Wert 0 wird gekennzeichnet, dass eine unendliche Anzahl von Fehlern zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="914ee-139">A value of 0 indicates that an infinite number of errors are allowed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="914ee-140">Jede Zeile, die beim Massenladevorgang nicht importiert werden kann, zählt als ein Fehler.</span><span class="sxs-lookup"><span data-stu-id="914ee-140">Each row that cannot be imported by the bulk load operation is counted as one error.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="914ee-141">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="914ee-141">See Also</span></span>  
 <span data-ttu-id="914ee-142">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="914ee-142">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 <span data-ttu-id="914ee-143">[Massen Einfügungs Task-Editor &#40;Seite Allgemein&#41;](general-page-of-integration-services-designers-options.md) </span><span class="sxs-lookup"><span data-stu-id="914ee-143">[Bulk Insert Task Editor &#40;General Page&#41;](general-page-of-integration-services-designers-options.md) </span></span>  
 <span data-ttu-id="914ee-144">[Massen Einfügungs Task-Editor &#40;Verbindungs Seite&#41;](../../2014/integration-services/bulk-insert-task-editor-connection-page.md) </span><span class="sxs-lookup"><span data-stu-id="914ee-144">[Bulk Insert Task Editor &#40;Connection Page&#41;](../../2014/integration-services/bulk-insert-task-editor-connection-page.md) </span></span>  
 <span data-ttu-id="914ee-145">[Seite Ausdrücke](expressions/expressions-page.md) </span><span class="sxs-lookup"><span data-stu-id="914ee-145">[Expressions Page](expressions/expressions-page.md) </span></span>  
 [<span data-ttu-id="914ee-146">Ablaufsteuerung</span><span class="sxs-lookup"><span data-stu-id="914ee-146">Control Flow</span></span>](control-flow/control-flow.md)  
  
  
