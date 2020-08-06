---
title: Angeben der Weitergabemethode für Änderungen bei Transaktionsartikeln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
helpviewer_keywords:
- transactional replication, propagation methods
ms.assetid: a10c5001-22cc-4667-8f0b-3d0818dca2e9
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 72d377ba89f1d393eab48bd9c918012b0f503f9c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699440"
---
# <a name="specify-how-changes-are-propagated-for-transactional-articles"></a><span data-ttu-id="da6a1-102">Angeben der Weitergabemethode für Änderungen bei Transaktionsartikeln</span><span class="sxs-lookup"><span data-stu-id="da6a1-102">Specify How Changes Are Propagated for Transactional Articles</span></span>
  <span data-ttu-id="da6a1-103">Bei der Transaktionsreplikation können Sie angeben, wie Datenänderungen vom Verleger an den Abonnenten weitergegeben werden.</span><span class="sxs-lookup"><span data-stu-id="da6a1-103">Transactional replication allows you to specify how data changes are propagated from the Publisher to Subscribers.</span></span> <span data-ttu-id="da6a1-104">Für jede veröffentlichte Tabelle können Sie eine von vier Methoden angeben, mit der jeder Vorgang (INSERT, UPDATE oder DELETE) an den Abonnenten weitergegeben werden soll:</span><span class="sxs-lookup"><span data-stu-id="da6a1-104">For each published table, you can specify one of four ways that each operation (INSERT, UPDATE, or DELETE) should be propagated to the Subscriber:</span></span>  
  
-   <span data-ttu-id="da6a1-105">Angeben, dass die Transaktionsreplikation eine gespeicherte Prozedur zur Weitergabe von Änderungen an die Abonnenten ausgibt und anschließend aufruft (Standardeinstellung).</span><span class="sxs-lookup"><span data-stu-id="da6a1-105">Specify that transactional replication should script out and subsequently call a stored procedure to propagate changes to Subscribers (the default).</span></span>  
  
-   <span data-ttu-id="da6a1-106">Angeben, dass die Änderungen mithilfe einer INSERT-, UPDATE- oder DELETE-Anweisung weitergegeben werden sollen (Standardeinstellung bei Nicht-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] -Abonnenten).</span><span class="sxs-lookup"><span data-stu-id="da6a1-106">Specify that the change should be propagated using an INSERT, UPDATE, or DELETE statement (the default for non-[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Subscribers).</span></span>  
  
-   <span data-ttu-id="da6a1-107">Angeben, dass eine benutzerdefinierte gespeicherte Prozedur verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="da6a1-107">Specify that a custom stored procedure should be used.</span></span>  
  
-   <span data-ttu-id="da6a1-108">Angeben, dass diese Aktion auf keinem Abonnenten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="da6a1-108">Specify that this action should not be performed at any Subscriber.</span></span> <span data-ttu-id="da6a1-109">Transaktionen dieses Typs werden nicht repliziert.</span><span class="sxs-lookup"><span data-stu-id="da6a1-109">Transactions of that type are not replicated.</span></span>  
  
 <span data-ttu-id="da6a1-110">Standardmäßig gibt die Transaktionsreplikation Änderungen an Abonnenten mithilfe einer Reihe gespeicherter Prozeduren weiter, die auf jedem Abonnenten gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="da6a1-110">By default, transactional replication propagates changes to Subscribers through a set of stored procedures that are installed on each Subscriber.</span></span> <span data-ttu-id="da6a1-111">Wenn eine Einfügung, ein Update oder eine Löschung an einer Tabelle auf dem Verleger vorgenommen wird, wird der Vorgang in einen Aufruf an eine gespeicherte Prozedur auf dem Abonnenten übersetzt.</span><span class="sxs-lookup"><span data-stu-id="da6a1-111">When an insert, update or delete occurs on a table at the Publisher, the operation is translated into a call to a stored procedure at the Subscriber.</span></span> <span data-ttu-id="da6a1-112">Die gespeicherte Prozedur akzeptiert Parameter, die den Spalten in der Tabelle zugeordnet sind, und lässt das Ändern dieser Spalten auf dem Abonnenten zu.</span><span class="sxs-lookup"><span data-stu-id="da6a1-112">The stored procedure accepts parameters that map to the columns in the table, allowing those columns to be changed at the Subscriber.</span></span>  
  
 <span data-ttu-id="da6a1-113">Informationen zum Festlegen der Propagierungsmethode für Datenänderungen an Transaktionsartikeln finden Sie unter [Festlegen der Propagierungsmethode für Datenänderungen an Transaktionsartikeln](../publish/set-the-propagation-method-for-data-changes-to-transactional-articles.md).</span><span class="sxs-lookup"><span data-stu-id="da6a1-113">To set the propagation method for data changes to transactional articles, see [Set the Propagation Method for Data Changes to Transactional Articles](../publish/set-the-propagation-method-for-data-changes-to-transactional-articles.md).</span></span>  
  
## <a name="default-and-custom-stored-procedures"></a><span data-ttu-id="da6a1-114">Standardmäßige und benutzerdefinierte gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="da6a1-114">Default and custom stored procedures</span></span>  
 <span data-ttu-id="da6a1-115">Die folgenden drei Prozeduren werden von der Replikation standardmäßig für jeden Tabellenartikel erstellt:</span><span class="sxs-lookup"><span data-stu-id="da6a1-115">The three procedures that replication creates by default for each table article are:</span></span>  
  
-   <span data-ttu-id="da6a1-116">**sp_MSins_\<** *tablename* **>** behandelt Einfügungen.</span><span class="sxs-lookup"><span data-stu-id="da6a1-116">**sp_MSins_\<** *tablename* **>**, which handles inserts.</span></span>  
  
-   <span data-ttu-id="da6a1-117">**sp_MSupd_\<** *tablename* **>** behandelt Updates.</span><span class="sxs-lookup"><span data-stu-id="da6a1-117">**sp_MSupd_\<** *tablename* **>**, which handles updates.</span></span>  
  
-   <span data-ttu-id="da6a1-118">**sp_MSdel_\<** *tablename* **>** behandelt Löschvorgänge.</span><span class="sxs-lookup"><span data-stu-id="da6a1-118">**sp_MSdel_\<** *tablename* **>**, which handles deletes.</span></span>  
  
 <span data-ttu-id="da6a1-119">Der in der Prozedur verwendete **\<***tablename***>** hängt davon ab, wie der Artikel der Veröffentlichung hinzugefügt wurde und ob die Abonnementdatenbank eine Tabelle mit demselben Namen und einem anderen Besitzer enthält.</span><span class="sxs-lookup"><span data-stu-id="da6a1-119">The **\<***tablename***>** used in the procedure depends on how the article was added to the publication and whether the subscription database contains a table of the same name with a different owner.</span></span>  
  
 <span data-ttu-id="da6a1-120">Jede dieser Prozeduren kann durch eine benutzerdefinierte Prozedur ersetzt werden, die Sie beim Hinzufügen eines Artikels zur Veröffentlichung angeben.</span><span class="sxs-lookup"><span data-stu-id="da6a1-120">Any of these procedures can be replaced with a custom procedure that you specify when adding an article to a publication.</span></span> <span data-ttu-id="da6a1-121">In einer Anwendung verwendete benutzerdefinierte Prozeduren erfordern eine benutzerdefinierte Logik: z. B. das Einfügen von Daten in eine Überwachungstabelle, wenn eine Zeile auf einem Abonnenten aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="da6a1-121">Custom procedures are used if an application requires custom logic, such as inserting data into an audit table when a row is updated at a Subscriber.</span></span> <span data-ttu-id="da6a1-122">Weitere Informationen zum Angeben von benutzerdefinierten gespeicherten Prozeduren finden Sie in den oben aufgeführten Themen.</span><span class="sxs-lookup"><span data-stu-id="da6a1-122">For more information about specifying custom stored procedures, see the how to topics listed above.</span></span>  
  
 <span data-ttu-id="da6a1-123">Wenn Sie die Standardreplikationsprozeduren oder benutzerdefinierten Prozeduren angeben, geben Sie auch eine Aufrufsyntax für jede Prozedur an (bei Verwendung von Standardprozeduren werden diese Prozeduren von der Replikation ausgewählt).</span><span class="sxs-lookup"><span data-stu-id="da6a1-123">If you specify the default replication procedures or custom procedures, you also specify call syntax for each procedure (replication selects defaults if you use the default procedures).</span></span> <span data-ttu-id="da6a1-124">Die Aufrufsyntax legt die Struktur der für die Prozedur bereitgestellten Parameter fest und welche Informationen bei jeder Datenänderung an den Abonnenten gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="da6a1-124">The call syntax determines the structure of the parameters provided to the procedure and how much information is sent to the Subscriber with each data change.</span></span> <span data-ttu-id="da6a1-125">Weitere Informationen finden Sie im Abschnitt zur Aufrufsyntax für gespeicherte Prozeduren in diesem Thema.</span><span class="sxs-lookup"><span data-stu-id="da6a1-125">For more information, see the section "Call Syntax for Stored Procedures" in this topic.</span></span>  
  
### <a name="considerations-for-using-custom-stored-procedures"></a><span data-ttu-id="da6a1-126">Überlegungen zum Verwenden benutzerdefinierter gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="da6a1-126">Considerations for Using Custom Stored Procedures</span></span>  
 <span data-ttu-id="da6a1-127">Berücksichtigen Sie bei der Verwendung benutzerdefinierter gespeicherter Prozeduren die folgenden Überlegungen:</span><span class="sxs-lookup"><span data-stu-id="da6a1-127">Keep the following considerations in mind when using custom stored procedures:</span></span>  
  
-   <span data-ttu-id="da6a1-128">Sie müssen den Support für die Logik der gespeicherten Prozedur selbst übernehmen. [!INCLUDE[msCoName](../../../includes/msconame-md.md)] stellt für benutzerdefinierte Logik keinen Support bereit.</span><span class="sxs-lookup"><span data-stu-id="da6a1-128">You must support the logic in the stored procedure; [!INCLUDE[msCoName](../../../includes/msconame-md.md)] does not provide support for custom logic.</span></span>  
  
-   <span data-ttu-id="da6a1-129">Verwenden Sie keine expliziten Transaktionen in benutzerdefinierten Prozeduren, um Konflikte mit Transaktionen zu vermeiden, die von der Replikation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="da6a1-129">In order to avoid conflicts with the transactions used by replication, explicit transactions should not be used in custom procedures.</span></span>  
  
-   <span data-ttu-id="da6a1-130">Das Schema auf dem Abonnenten ist in der Regel mit dem Schema auf dem Verleger identisch, kann bei Verwendung der Spaltenfilterung jedoch eine Teilmenge des Verlegerschemas sein.</span><span class="sxs-lookup"><span data-stu-id="da6a1-130">The schema at the Subscriber is typically identical to the schema at the Publisher, but can also be a subset of the Publisher schema if column filtering is used.</span></span> <span data-ttu-id="da6a1-131">Wenn Sie jedoch beim Verschieben der Daten das Schema so transformieren, dass das Schema auf dem Abonnenten keine Teilmenge des Schemas auf dem Verleger darstellt, ist [!INCLUDE[ssISCurrent](../../../includes/ssiscurrent-md.md)] die empfohlene Lösung.</span><span class="sxs-lookup"><span data-stu-id="da6a1-131">However, if you need to transform the schema as the data is moved such that the schema on the Subscriber is not a subset of the schema on the Publisher, [!INCLUDE[ssISCurrent](../../../includes/ssiscurrent-md.md)] is the recommended solution.</span></span> <span data-ttu-id="da6a1-132">Weitere Informationen finden Sie unter [SQL Server Integration Services](../../../integration-services/sql-server-integration-services.md).</span><span class="sxs-lookup"><span data-stu-id="da6a1-132">For more information, see [SQL Server Integration Services](../../../integration-services/sql-server-integration-services.md).</span></span>  
  
-   <span data-ttu-id="da6a1-133">Wenn Sie Schemaänderungen an einer veröffentlichten Tabelle vornehmen, müssen die benutzerdefinierten Prozeduren neu generiert werden.</span><span class="sxs-lookup"><span data-stu-id="da6a1-133">If you make schema changes to a published table, the custom procedures must be regenerated.</span></span> <span data-ttu-id="da6a1-134">Weitere Informationen finden Sie unter [Erneutes Generieren von Transaktionsprozeduren zur Erfassung von Schemaänderungen](transactional-articles-regenerate-to-reflect-schema-changes.md).</span><span class="sxs-lookup"><span data-stu-id="da6a1-134">For more information, see [Regenerate Custom Transactional Procedures to Reflect Schema Changes](transactional-articles-regenerate-to-reflect-schema-changes.md).</span></span>  
  
-   <span data-ttu-id="da6a1-135">Wenn Sie einen höheren Wert als 1 für den **-SubscriptionStreams** -Parameter des Verteilungs-Agent verwenden, müssen Sie sicherstellen, dass Updates an der Primärschlüsselspalte erfolgreich sind.</span><span class="sxs-lookup"><span data-stu-id="da6a1-135">If you use a value greater than 1 for **-SubscriptionStreams** parameter of the Distribution Agent, you must ensure that updates to primary key columns are successful.</span></span> <span data-ttu-id="da6a1-136">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="da6a1-136">For example:</span></span>  
  
    ```  
    update ... set pk = 2 where pk = 1 -- update 1  
    update ... set pk = 3 where pk = 2 -- update 2  
    ```  
  
     <span data-ttu-id="da6a1-137">Wenn der Verteilungs-Agent mehrere Verbindungen verwendet, werden diese beiden Updates gegebenenfalls über verschiedene Verbindungen repliziert.</span><span class="sxs-lookup"><span data-stu-id="da6a1-137">If the Distribution Agent uses more than one connection, these two updates might be replicated over different connections.</span></span> <span data-ttu-id="da6a1-138">Wird Update 1 zuerst angewendet, gibt es kein Problem. Wird Update 2 zuerst angewendet, wird '0 Zeilen betroffen' zurückgegeben, da Update 1 noch nicht stattgefunden hat.</span><span class="sxs-lookup"><span data-stu-id="da6a1-138">If update 1 is applied first, there is no problem; if update 2 is applied first it will return '0 rows affected' because update 1 has not yet occurred.</span></span> <span data-ttu-id="da6a1-139">Diese Situation wird von den Standardprozeduren beantwortet. Dabei wird ein Fehler ausgelöst, wenn von einem Update keine Zeilen betroffen sind:</span><span class="sxs-lookup"><span data-stu-id="da6a1-139">This situation is handled in the default procedures by raising an error if no rows are affected on an update:</span></span>  
  
    ```  
    if @@rowcount = 0  
        if @@microsoftversion>0x07320000  
            exec sys.sp_MSreplraiserror 20598  
    ```  
  
     <span data-ttu-id="da6a1-140">Das Auslösen des Fehlers zwingt den Verteilungs-Agent, die Updates erneut über eine einzige Verbindung zu versuchen. Dieser Versuch ist dann erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="da6a1-140">Raising the error forces the Distribution Agent to retry the updates over a single connection, which will succeed.</span></span> <span data-ttu-id="da6a1-141">Benutzerdefinierte gespeicherte Prozeduren müssen eine ähnliche Logik einschließen.</span><span class="sxs-lookup"><span data-stu-id="da6a1-141">Custom stored procedures must include similar logic.</span></span>  
  
### <a name="call-syntax-for-stored-procedures"></a><span data-ttu-id="da6a1-142">Aufrufsyntax für gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="da6a1-142">Call syntax for stored procedures</span></span>  
 <span data-ttu-id="da6a1-143">Es gibt fünf Optionen für die Syntax, mit der die von der Transaktionsreplikation verwendeten Prozeduren aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="da6a1-143">There are five options for the syntax used to call the procedures used by transactional replication:</span></span>  
  
-   <span data-ttu-id="da6a1-144">CALL-Syntax.</span><span class="sxs-lookup"><span data-stu-id="da6a1-144">CALL syntax.</span></span> <span data-ttu-id="da6a1-145">Diese Syntax kann für Einfügungen, Updates und Löschungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="da6a1-145">Can be used for inserts, updates, and deletes.</span></span> <span data-ttu-id="da6a1-146">Die Replikation verwendet diese Syntax standardmäßig für Einfügungen und Löschungen.</span><span class="sxs-lookup"><span data-stu-id="da6a1-146">By default, replication uses this syntax for inserts and deletes.</span></span>  
  
-   <span data-ttu-id="da6a1-147">SCALL-Syntax.</span><span class="sxs-lookup"><span data-stu-id="da6a1-147">SCALL syntax.</span></span> <span data-ttu-id="da6a1-148">Diese Syntax kann nur für Updates verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="da6a1-148">Can be used for updates only.</span></span> <span data-ttu-id="da6a1-149">Die Replikation verwendet diese Syntax standardmäßig für Updates.</span><span class="sxs-lookup"><span data-stu-id="da6a1-149">By default, replication uses this syntax for updates.</span></span>  
  
-   <span data-ttu-id="da6a1-150">MCALL-Syntax.</span><span class="sxs-lookup"><span data-stu-id="da6a1-150">MCALL syntax.</span></span> <span data-ttu-id="da6a1-151">Diese Syntax kann nur für Updates verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="da6a1-151">Can be used for updates only.</span></span>  
  
-   <span data-ttu-id="da6a1-152">XCALL-Syntax.</span><span class="sxs-lookup"><span data-stu-id="da6a1-152">XCALL syntax.</span></span> <span data-ttu-id="da6a1-153">Diese Syntax kann für Updates und Löschungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="da6a1-153">Can be used for updates and deletes.</span></span>  
  
-   <span data-ttu-id="da6a1-154">VCALL.</span><span class="sxs-lookup"><span data-stu-id="da6a1-154">VCALL.</span></span> <span data-ttu-id="da6a1-155">Diese Syntax wird für aktualisierbare Abonnements verwendet.</span><span class="sxs-lookup"><span data-stu-id="da6a1-155">Used for updatable subscriptions.</span></span> <span data-ttu-id="da6a1-156">Nur interne Verwendung.</span><span class="sxs-lookup"><span data-stu-id="da6a1-156">Internal use only.</span></span>  
  
 <span data-ttu-id="da6a1-157">Die einzelnen Methoden unterscheiden sich in der Datenmenge, die an den Abonnenten weitergegeben wird.</span><span class="sxs-lookup"><span data-stu-id="da6a1-157">Each method differs in the amount of data that is propagated to the Subscriber.</span></span> <span data-ttu-id="da6a1-158">SCALL gibt z. B. Werte nur für die Spalten weiter, die tatsächlich von einem Update betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="da6a1-158">For example, SCALL passes in values only for the columns that are actually affected by an update.</span></span> <span data-ttu-id="da6a1-159">XCALL dagegen erfordert alle Spalten (unabhängig davon, ob sie von einem Update betroffen sind) und alle alten Datenwerte für jede Spalte.</span><span class="sxs-lookup"><span data-stu-id="da6a1-159">XCALL, by contrast, requires all columns (whether affected by an update or not) and all the old data values for each column.</span></span> <span data-ttu-id="da6a1-160">In vielen Fällen eignet sich SCALL für Updates. Erfordert die Anwendung jedoch alle Datenwerte bei einem Update, empfiehlt sich die Verwendung von XCALL.</span><span class="sxs-lookup"><span data-stu-id="da6a1-160">In many cases, SCALL is appropriate for updates, but if your application requires all the data values during an update, XCALL allows for this.</span></span>  
  
#### <a name="call-syntax"></a><span data-ttu-id="da6a1-161">CALL-Syntax</span><span class="sxs-lookup"><span data-stu-id="da6a1-161">CALL Syntax</span></span>  
 <span data-ttu-id="da6a1-162">Gespeicherte Prozeduren zu INSERT</span><span class="sxs-lookup"><span data-stu-id="da6a1-162">INSERT stored procedures</span></span>  
 <span data-ttu-id="da6a1-163">Gespeicherte Prozeduren, die INSERT-Anweisungen verarbeiten, übergeben die in allen Spalten eingefügten Werte:</span><span class="sxs-lookup"><span data-stu-id="da6a1-163">Stored procedures handling INSERT statements will be passed the inserted values for all columns:</span></span>  
  
```  
c1, c2, c3,... cn  
```  
  
 <span data-ttu-id="da6a1-164">Gespeicherte Prozeduren zu UPDATE</span><span class="sxs-lookup"><span data-stu-id="da6a1-164">UPDATE stored procedures</span></span>  
 <span data-ttu-id="da6a1-165">Gespeicherte Prozeduren, die UPDATE-Anweisungen verarbeiten, übergeben die aktualisierten Werte für alle in dem Artikel definierten Spaltenwerte, gefolgt von den ursprünglichen Werten der Primärschlüsselspalten (es wird kein Versuch zur Bestimmung der geänderten Spalten unternommen):</span><span class="sxs-lookup"><span data-stu-id="da6a1-165">Stored procedures handling UPDATE statements will be passed the updated values for all columns defined in the article, followed by the original values for the primary key columns (no attempt is made to determine which columns were changed.):</span></span>  
  
```  
c1, c2, c3,... cn, pkc1, pkc2, pkc3,... pkcn  
```  
  
 <span data-ttu-id="da6a1-166">Gespeicherte Prozeduren zu DELETE</span><span class="sxs-lookup"><span data-stu-id="da6a1-166">DELETE stored procedures</span></span>  
 <span data-ttu-id="da6a1-167">Gespeicherte Prozeduren, die DELETE Anweisungen verarbeiten, übergeben die Werte der folgenden Primärschlüsselspalten:</span><span class="sxs-lookup"><span data-stu-id="da6a1-167">Stored procedures handling DELETE statements will be passed values for the primary key columns:</span></span>  
  
```  
pkc1, pkc2, pkc3,... pkcn  
```  
  
#### <a name="scall-syntax"></a><span data-ttu-id="da6a1-168">SCALL-Syntax</span><span class="sxs-lookup"><span data-stu-id="da6a1-168">SCALL Syntax</span></span>  
 <span data-ttu-id="da6a1-169">Gespeicherte Prozeduren zu UPDATE</span><span class="sxs-lookup"><span data-stu-id="da6a1-169">UPDATE stored procedures</span></span>  
 <span data-ttu-id="da6a1-170">Gespeicherte Prozeduren, die UPDATE-Anweisungen verarbeiten, übergeben die aktualisierten Werte nur für die geänderten Spalten, gefolgt von den ursprünglichen Werten der Primärschlüsselspalten, auf die wiederum ein Bitmaskenparameter (`binary(n)`) folgt, der die geänderten Spalten anzeigt.</span><span class="sxs-lookup"><span data-stu-id="da6a1-170">Stored procedures handling UPDATE statements will be passed the updated values only for those columns that have changed, followed by the original values for the primary key columns, followed by a bitmask (`binary(n)`) parameter that indicates the changed columns.</span></span> <span data-ttu-id="da6a1-171">Im folgenden Beispiel wurde die Spalte 2 (c2) nicht geändert:</span><span class="sxs-lookup"><span data-stu-id="da6a1-171">In the following example, column 2 (c2) has not changed:</span></span>  
  
```  
c1, , c3,... cn, pkc1, pkc2, pkc3,... pkcn, bitmask  
```  
  
#### <a name="mcall-syntax"></a><span data-ttu-id="da6a1-172">MCALL-Syntax</span><span class="sxs-lookup"><span data-stu-id="da6a1-172">MCALL Syntax</span></span>  
 <span data-ttu-id="da6a1-173">Gespeicherte Prozeduren zu UPDATE</span><span class="sxs-lookup"><span data-stu-id="da6a1-173">UPDATE stored procedures</span></span>  
 <span data-ttu-id="da6a1-174">Gespeicherte Prozeduren, die UPDATE-Anweisungen verarbeiten, übergeben die aktualisierten Werte für alle in dem Artikel definierten Spaltenwerte, gefolgt von den ursprünglichen Werten der Primärschlüsselspalten, auf die wiederum ein Bitmaskenparameter (`binary(n)`) folgt, der die geänderten Spalten anzeigt:</span><span class="sxs-lookup"><span data-stu-id="da6a1-174">Stored procedures handling UPDATE statements will be passed the updated values for all columns defined in the article, followed by the original values for the primary key columns, followed by a bitmask (`binary(n)`) parameter that indicates the changed columns:</span></span>  
  
```  
c1, c2, c3,... cn, pkc1, pkc2, pkc3,... pkcn, bitmask  
```  
  
#### <a name="xcall-syntax"></a><span data-ttu-id="da6a1-175">XCALL-Syntax</span><span class="sxs-lookup"><span data-stu-id="da6a1-175">XCALL Syntax</span></span>  
 <span data-ttu-id="da6a1-176">Gespeicherte Prozeduren zu UPDATE</span><span class="sxs-lookup"><span data-stu-id="da6a1-176">UPDATE stored procedures</span></span>  
 <span data-ttu-id="da6a1-177">Gespeicherte Prozeduren, die UPDATE-Anweisungen verarbeiten, übergeben die ursprünglichen Werte (das Anfangsimage) für alle in dem Artikel definierten Spalten, gefolgt von den aktualisierten Werten (das Endimage) für alle in dem Artikel definierten Spalten.</span><span class="sxs-lookup"><span data-stu-id="da6a1-177">Stored procedures handling UPDATE statements will be passed the original values (the before image) for all columns defined in the article, followed by the updated values (the after image) for all columns defined in the article:</span></span>  
  
```  
old-c1, old-c2, old-c3,... old-cn, c1, c2, c3,... cn,  
```  
  
 <span data-ttu-id="da6a1-178">Gespeicherte Prozeduren zu DELETE</span><span class="sxs-lookup"><span data-stu-id="da6a1-178">DELETE stored procedures</span></span>  
 <span data-ttu-id="da6a1-179">Gespeicherte Prozeduren, die DELETE-Anweisungen verarbeiten, übergeben die ursprünglichen Werte (das Anfangsimage) für alle in dem Artikel definierten Spalten:</span><span class="sxs-lookup"><span data-stu-id="da6a1-179">Stored procedures handling DELETE statements will be passed the original (the before image) values for all columns defined in the article:</span></span>  
  
```  
old-c1, old-c2, old-c3,... old-cn  
```  
  
> [!NOTE]  
>  <span data-ttu-id="da6a1-180">Beim Verwenden von XCALL wird erwartet, dass die Anfangsimagewerte für **text** - und **image** -Spalten NULL sind.</span><span class="sxs-lookup"><span data-stu-id="da6a1-180">When using XCALL, the before image values for **text** and **image** columns are expected to be NULL.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="da6a1-181">Beispiele</span><span class="sxs-lookup"><span data-stu-id="da6a1-181">Examples</span></span>  
 <span data-ttu-id="da6a1-182">Bei den folgenden Prozeduren handelt es sich um Standardprozeduren, die für die `Vendor Table` in der [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] -Beispieldatenbank erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="da6a1-182">The following procedures are the default procedures created for the `Vendor Table` in the [!INCLUDE[ssSampleDBCoShort](../../../includes/sssampledbcoshort-md.md)] sample database.</span></span>  
  
```  
--INSERT procedure using CALL syntax  
create procedure [sp_MSins_PurchasingVendor]   
  @c1 int,@c2 nvarchar(15),@c3 nvarchar(50),@c4 tinyint,@c5 bit,@c6 bit,@c7 nvarchar(1024),@c8 datetime  
as   
begin   
insert into [Purchasing].[Vendor]([VendorID]  
,[AccountNumber]  
,[Name]  
,[CreditRating]  
,[PreferredVendorStatus]  
,[ActiveFlag]  
,[PurchasingWebServiceURL]  
,[ModifiedDate])  
values (   
 @c1  
,@c2  
,@c3  
,@c4  
,@c5  
,@c6  
,@c7  
,@c8  
 )   
end  
go  
  
--UPDATE procedure using SCALL syntax  
create procedure [sp_MSupd_PurchasingVendor]   
 @c1 int = null,@c2 nvarchar(15) = null,@c3 nvarchar(50) = null,@c4 tinyint = null,@c5 bit = null,@c6 bit = null,@c7 nvarchar(1024) = null,@c8 datetime = null,@pkc1 int  
,@bitmap binary(2)  
as  
begin  
update [Purchasing].[Vendor] set   
 [AccountNumber] = case substring(@bitmap,1,1) & 2 when 2 then @c2 else [AccountNumber] end  
,[Name] = case substring(@bitmap,1,1) & 4 when 4 then @c3 else [Name] end  
,[CreditRating] = case substring(@bitmap,1,1) & 8 when 8 then @c4 else [CreditRating] end  
,[PreferredVendorStatus] = case substring(@bitmap,1,1) & 16 when 16 then @c5 else [PreferredVendorStatus] end  
,[ActiveFlag] = case substring(@bitmap,1,1) & 32 when 32 then @c6 else [ActiveFlag] end  
,[PurchasingWebServiceURL] = case substring(@bitmap,1,1) & 64 when 64 then @c7 else [PurchasingWebServiceURL] end  
,[ModifiedDate] = case substring(@bitmap,1,1) & 128 when 128 then @c8 else [ModifiedDate] end  
where [VendorID] = @pkc1  
if @@rowcount = 0  
    if @@microsoftversion>0x07320000  
        exec sp_MSreplraiserror 20598  
end  
go  
  
--DELETE procedure using CALL syntax  
create procedure [sp_MSdel_PurchasingVendor]   
  @pkc1 int  
as   
begin   
delete [Purchasing].[Vendor]  
where [VendorID] = @pkc1  
if @@rowcount = 0  
    if @@microsoftversion>0x07320000  
        exec sp_MSreplraiserror 20598  
end   
go  
```  
  
## <a name="see-also"></a><span data-ttu-id="da6a1-183">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="da6a1-183">See Also</span></span>  
 [<span data-ttu-id="da6a1-184">Article Options for Transactional Replication</span><span class="sxs-lookup"><span data-stu-id="da6a1-184">Article Options for Transactional Replication</span></span>](article-options-for-transactional-replication.md)  
  
  
