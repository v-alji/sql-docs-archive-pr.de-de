---
title: CDC-Quelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.designer.cdcsource.f1
ms.assetid: 99775608-e177-44ed-bb44-aaccb0f4f327
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 064c25b129364dfcd813d71a462586303dd4ff60
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621622"
---
# <a name="cdc-source"></a><span data-ttu-id="ddac7-102">CDC-Quelle</span><span class="sxs-lookup"><span data-stu-id="ddac7-102">CDC Source</span></span>
  <span data-ttu-id="ddac7-103">Die CDC-Quelle liest einen Bereich mit Änderungsdaten aus [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] -Änderungstabellen und übermittelt die Änderungen an die anderen SSIS-Downstreamkomponenten.</span><span class="sxs-lookup"><span data-stu-id="ddac7-103">The CDC source reads a range of change data from [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] change tables and delivers the changes downstream to other SSIS components.</span></span>  
  
 <span data-ttu-id="ddac7-104">Der Bereich mit Änderungsdaten, der von CDC-Quelle gelesen wird, wird als CDC-Verarbeitungsbereich bezeichnet und mithilfe des CDC-Steuerungstasks bestimmt, der vor Beginn des aktuellen Datenflusses ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ddac7-104">The range of change data read by the CDC source is called the CDC Processing Range and is determine by the CDC Control task that is executed before the current data flow starts.</span></span> <span data-ttu-id="ddac7-105">Der CDC-Verarbeitungsbereich wird aus dem Wert einer Paketvariablen abgeleitet, die den Status der CDC-Verarbeitung für eine Gruppe von Tabellen verwaltet.</span><span class="sxs-lookup"><span data-stu-id="ddac7-105">The CDC Processing Range is derived from the value of a package variable that maintains the state of the CDC processing for a group of tables.</span></span>  
  
 <span data-ttu-id="ddac7-106">Die CDC-Quelle extrahiert Daten mithilfe einer Datenbanktabelle, Sicht oder SQL-Anweisung aus einer [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datenbank.</span><span class="sxs-lookup"><span data-stu-id="ddac7-106">The CDC source extracts data from a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database by using a database table, a view, or an SQL statement.</span></span>  
  
 <span data-ttu-id="ddac7-107">Die CDC-Quelle verwendet die folgenden Konfigurationen:</span><span class="sxs-lookup"><span data-stu-id="ddac7-107">The CDC source uses the following configurations:</span></span>  
  
-   <span data-ttu-id="ddac7-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -ADO.NET-Verbindungs-Manager, um auf die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -CDC-Datenbank zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="ddac7-108">A [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ADO.NET connection manager to access the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC database.</span></span> <span data-ttu-id="ddac7-109">Weitere Informationen zum Konfigurieren der CDC-Quellverbindung finden Sie unter [Quellen-Editor für CDC &#40;Seite „Verbindungs-Manager“&#41;](../cdc-source-editor-connection-manager-page.md).</span><span class="sxs-lookup"><span data-stu-id="ddac7-109">For more information about configuring the CDC source connection, see [CDC Source Editor &#40;Connection Manager Page&#41;](../cdc-source-editor-connection-manager-page.md).</span></span>  
  
-   <span data-ttu-id="ddac7-110">Für CDC aktivierte Tabelle.</span><span class="sxs-lookup"><span data-stu-id="ddac7-110">A table enabled for CDC.</span></span>  
  
-   <span data-ttu-id="ddac7-111">Name der Aufzeichnungsinstanz der ausgewählten Tabelle (falls mehr als eine vorhanden ist).</span><span class="sxs-lookup"><span data-stu-id="ddac7-111">The name of the capture instance of the selected table (if more-than-one exists).</span></span>  
  
-   <span data-ttu-id="ddac7-112">Änderungsverarbeitungsmodus</span><span class="sxs-lookup"><span data-stu-id="ddac7-112">The change processing mode.</span></span>  
  
-   <span data-ttu-id="ddac7-113">Name der CDC-Statuspaketvariablen, auf deren Grundlage der CDC-Verarbeitungsbereich bestimmt wird.</span><span class="sxs-lookup"><span data-stu-id="ddac7-113">The name of the CDC state package variable based on which the CDC Processing range is determined.</span></span> <span data-ttu-id="ddac7-114">Die CDC-Quelle ändert diese Variable nicht.</span><span class="sxs-lookup"><span data-stu-id="ddac7-114">The CDC source does not modify that variable.</span></span>  
  
 <span data-ttu-id="ddac7-115">Die von der CDC-Quelle zurückgegebenen Daten entsprechen den Daten, die von den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-CDC-Funktionen **cdc.fn_cdc_get_all_changes_\<capture-instance-name>** oder **cdc.fn_cdc_get_net_changes_\<capture-instance-name>** (falls verfügbar) zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ddac7-115">The data returned by the CDC Source is the same as that returned by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] CDC functions **cdc.fn_cdc_get_all_changes_\<capture-instance-name>** or **cdc.fn_cdc_get_net_changes_\<capture-instance-name>** (when available).</span></span> <span data-ttu-id="ddac7-116">Die einzige optionale Hinzufügung ist die Spalte **__$initial_processing** , in der angegeben wird, ob sich der aktuelle Verarbeitungsbereich mit einem erstmaligen Ladevorgang der Tabelle überschneiden kann.</span><span class="sxs-lookup"><span data-stu-id="ddac7-116">The only optional addition is the column, **__$initial_processing** that indicates whether the current processing range can overlap with an initial load of the table.</span></span> <span data-ttu-id="ddac7-117">Weitere Informationen zur erstmaligen Verarbeitung finden Sie unter [CDC Control Task](../control-flow/cdc-control-task.md).</span><span class="sxs-lookup"><span data-stu-id="ddac7-117">For more information about initial processing, see [CDC Control Task](../control-flow/cdc-control-task.md).</span></span>  
  
 <span data-ttu-id="ddac7-118">Die CDC-Quelle weist eine reguläre Ausgabe und eine Fehlerausgabe auf.</span><span class="sxs-lookup"><span data-stu-id="ddac7-118">The CDC source has one regular output and one error output.</span></span>  
  
## <a name="error-handling"></a><span data-ttu-id="ddac7-119">Fehlerbehandlung</span><span class="sxs-lookup"><span data-stu-id="ddac7-119">Error Handling</span></span>  
 <span data-ttu-id="ddac7-120">Die CDC-Quelle verfügt über eine Fehlerausgabe.</span><span class="sxs-lookup"><span data-stu-id="ddac7-120">The CDC source has an error output.</span></span> <span data-ttu-id="ddac7-121">Die Komponentenfehlerausgabe enthält die folgenden Ausgabespalten:</span><span class="sxs-lookup"><span data-stu-id="ddac7-121">The component error output includes the following output columns:</span></span>  
  
-   <span data-ttu-id="ddac7-122">**Fehlercode**: Der Wert beträgt immer -1.</span><span class="sxs-lookup"><span data-stu-id="ddac7-122">**Error Code**: The value is always -1.</span></span>  
  
-   <span data-ttu-id="ddac7-123">**Fehlerspalte**: Die Quellspalte, die den Fehler verursacht (für Konvertierungsfehler).</span><span class="sxs-lookup"><span data-stu-id="ddac7-123">**Error Column**: The source column causing the error (for conversion errors).</span></span>  
  
-   <span data-ttu-id="ddac7-124">**Fehlerzeilenspalten**: Die Datensatzdaten, die den Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="ddac7-124">**Error Row Columns**: The record data that causes the error.</span></span>  
  
 <span data-ttu-id="ddac7-125">Je nach Einstellung des Fehlerverhaltens unterstützt die CDC-Quelle das Zurückgeben von Fehlern (Datenkonvertierung, Abschneiden), die während des Extraktionsprozesses in der Fehlerausgabe auftreten.</span><span class="sxs-lookup"><span data-stu-id="ddac7-125">Depending on the error behavior setting, the CDC source supports returning errors (data conversion, truncation) that occur during the extraction process in the error output.</span></span> <span data-ttu-id="ddac7-126">Weitere Informationen finden Sie unter [Quellen-Editor für CDC &#40;Seite „Fehlerausgabe“&#41;](../cdc-source-editor-error-output-page.md).</span><span class="sxs-lookup"><span data-stu-id="ddac7-126">For more information, see [CDC Source Editor &#40;Error Output Page&#41;](../cdc-source-editor-error-output-page.md).</span></span>  
  
## <a name="data-type-support"></a><span data-ttu-id="ddac7-127">Datentypunterstützung</span><span class="sxs-lookup"><span data-stu-id="ddac7-127">Data Type Support</span></span>  
 <span data-ttu-id="ddac7-128">Die CDC-Quellkomponente für Microsoft unterstützt alle [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Datentypen, die den richtigen SSIS-Datentypen zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="ddac7-128">The CDC source component for Microsoft supports all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types, which are mapped to the correct SSIS data types.</span></span>  
  
## <a name="troubleshooting-the-cdc-source"></a><span data-ttu-id="ddac7-129">Problembehandlung der CDC-Quelle</span><span class="sxs-lookup"><span data-stu-id="ddac7-129">Troubleshooting the CDC Source</span></span>  
 <span data-ttu-id="ddac7-130">Unten sind Informationen zum Durchführen einer Problembehandlung für die CDC-Quelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="ddac7-130">The following contains information on troubleshooting the CDC source.</span></span>  
  
### <a name="use-this-script-to-isolate-problems-and-reproduce-them-in-sql-server-management-studio"></a><span data-ttu-id="ddac7-131">Verwenden dieses Skripts zum Isolieren von Problemen und zum Reproduzieren in SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="ddac7-131">Use this script to isolate problems and reproduce them in SQL Server Management Studio</span></span>  
 <span data-ttu-id="ddac7-132">Der CDC-Quellvorgang wird vom Vorgang des CDC-Steuerungstasks gesteuert, der vor dem Aufrufen der CDC-Quelle ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="ddac7-132">The CDC source operation is governed by the operation of the CDC Control task executed before invoking the CDC source.</span></span> <span data-ttu-id="ddac7-133">Der CDC-Steuerungstask bereitet den Wert der CDC-Statuspaketvariablen vor, damit die Start- und End-LSN darin enthalten sein kann.</span><span class="sxs-lookup"><span data-stu-id="ddac7-133">The CDC Control task prepares the value of the CDC state package variable to contain the start and end LSNs.</span></span> <span data-ttu-id="ddac7-134">Es wird eine Funktion ausgeführt, die dem folgenden Skript entspricht:</span><span class="sxs-lookup"><span data-stu-id="ddac7-134">It performs function equivalent to the following script:</span></span>  
  
```  
use <cdc-enabled-database-name>  
               declare @start_lsn binary(10), @end_lsn binary(10)  
               set @start_lsn = sys.fn_cdc_increment_lsn(  
                       convert(binary(10),'0x' + '<value-from-state-cs>', 1))  
               set @end_lsn =   
                       convert(binary(10),'0x' + '<value-from-state-ce>', 1)  
               select * from cdc.fn_cdc_get_net_changes_dbo_Table1(@start_lsn,  
@end_lsn, '<mode>')  
```  
  
 <span data-ttu-id="ddac7-135">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="ddac7-135">where:</span></span>  
  
-   <span data-ttu-id="ddac7-136">\<cdc-enabled-database-name> ist der Name der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbank, die die Änderungstabellen enthält.</span><span class="sxs-lookup"><span data-stu-id="ddac7-136">\<cdc-enabled-database-name> is the name of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database containing the change tables.</span></span>  
  
-   <span data-ttu-id="ddac7-137">\<value-from-state-cs> ist der Wert, der in der CDC-Statusvariablen als CS/\<value-from-state-cs>/ (CS steht für Current-processing-range-Start) angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ddac7-137">\<value-from-state-cs> is the value that appears in the CDC state variable as CS/\<value-from-state-cs>/ (CS stands for Current-processing-range-Start).</span></span>  
  
-   <span data-ttu-id="ddac7-138">\<value-from-state-ce> ist der Wert, der in der CDC-Statusvariablen als CE/\<value-from-state-cs>/ (CE steht für Current-processing-range-End) angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="ddac7-138">\<value-from-state-ce> is the value that appears in the CDC state variable as CE/\<value-from-state-cs>/ (CE stands for Current-processing-range-End).</span></span>  
  
-   <span data-ttu-id="ddac7-139">\<mode> steht für die CDC-Verarbeitungsmodi.</span><span class="sxs-lookup"><span data-stu-id="ddac7-139">\<mode> are the CDC processing modes.</span></span> <span data-ttu-id="ddac7-140">Die Verarbeitungsmodi haben einen der folgenden Werte: **All**, **All with Old Values**, **Net**, **Net with Update Mask**, **Net with Merge**.</span><span class="sxs-lookup"><span data-stu-id="ddac7-140">The processing modes have one of the following values **All**, **All with Old Values**, **Net**, **Net with Update Mask**, **Net with Merge**.</span></span>  
  
 <span data-ttu-id="ddac7-141">Dieses Skript trägt zur Isolierung von Problemen bei, indem sie im [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]reproduziert werden, wo sie leicht reproduziert und identifiziert werden können.</span><span class="sxs-lookup"><span data-stu-id="ddac7-141">This script helps isolate problems by reproducing them in the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], where it is easy to reproduce and identify errors.</span></span>  
  
#### <a name="sql-server-error-message"></a><span data-ttu-id="ddac7-142">SQL Server-Fehlermeldung</span><span class="sxs-lookup"><span data-stu-id="ddac7-142">SQL Server Error Message</span></span>  
 <span data-ttu-id="ddac7-143">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]gibt möglicherweise die folgende Meldung zurück:</span><span class="sxs-lookup"><span data-stu-id="ddac7-143">The following message may be returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
 <span data-ttu-id="ddac7-144">**Für die Prozedur oder Funktion „cdc.fn_cdc_get_net_changes_\<..>“ wurden zu wenig Argumente bereitgestellt.**</span><span class="sxs-lookup"><span data-stu-id="ddac7-144">**An insufficient number of arguments were supplied for the procedure or function cdc.fn_cdc_get_net_changes_\<..>.**</span></span>  
  
 <span data-ttu-id="ddac7-145">Dieser Fehler gibt nicht an, dass ein Argument fehlt.</span><span class="sxs-lookup"><span data-stu-id="ddac7-145">This error does not indicate that an argument is missing.</span></span> <span data-ttu-id="ddac7-146">Die Bedeutung ist, dass die Start- bzw. End-LSN-Werte in der CDC-Statusvariablen ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="ddac7-146">It means that the start or end LSN values in the CDC state variable are invalid.</span></span>  
  
## <a name="configuring-the-cdc-source"></a><span data-ttu-id="ddac7-147">Konfigurieren der CDC-Quelle</span><span class="sxs-lookup"><span data-stu-id="ddac7-147">Configuring the CDC Source</span></span>  
 <span data-ttu-id="ddac7-148">Sie können die CDC-Quelle programmgesteuert oder mit dem SSIS-Designer konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ddac7-148">You can configure the CDC source programmatically or through the SSIS Designer.</span></span>  
  
 <span data-ttu-id="ddac7-149">Weitere Informationen finden Sie in einem der folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ddac7-149">For more information, see one of the following topics:</span></span>  
  
-   [<span data-ttu-id="ddac7-150">Quellen-Editor für CDC &#40;Seite „Verbindungs-Manager“&#41;</span><span class="sxs-lookup"><span data-stu-id="ddac7-150">CDC Source Editor &#40;Connection Manager Page&#41;</span></span>](../cdc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="ddac7-151">Quellen-Editor für CDC &#40;Seite „Spalten“&#41;</span><span class="sxs-lookup"><span data-stu-id="ddac7-151">CDC Source Editor &#40;Columns Page&#41;</span></span>](../cdc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="ddac7-152">Quellen-Editor für CDC &#40;Seite „Fehlerausgabe“&#41;</span><span class="sxs-lookup"><span data-stu-id="ddac7-152">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../cdc-source-editor-error-output-page.md)  
  
 <span data-ttu-id="ddac7-153">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="ddac7-153">The **Advanced Editor** dialog box contains the properties that can be set programmatically.</span></span>  
  
 <span data-ttu-id="ddac7-154">So öffnen Sie das Dialogfeld **Erweiterter Editor** :</span><span class="sxs-lookup"><span data-stu-id="ddac7-154">To open the **Advanced Editor** dialog box:</span></span>  
  
-   <span data-ttu-id="ddac7-155">Klicken Sie auf dem Bildschirm **Datenfluss** des [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] -Projekts mit der rechten Maustaste auf die CDC-Quelle, und wählen Sie **Erweiterten Editor anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="ddac7-155">In the **Data Flow** screen of your [!INCLUDE[ssISCurrent](../../includes/ssiscurrent-md.md)] project, right click the CDC source and select **Show Advanced Editor**.</span></span>  
  
 <span data-ttu-id="ddac7-156">Weitere Informationen zu den Eigenschaften, die Sie im Dialogfeld **Erweiterter Editor** festlegen können, finden Sie unter [CDC Source Custom Properties](cdc-source-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="ddac7-156">For more information about the properties that you can set in the **Advanced Editor** dialog box, see [CDC Source Custom Properties](cdc-source-custom-properties.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ddac7-157">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="ddac7-157">In This Section</span></span>  
  
-   [<span data-ttu-id="ddac7-158">Quellen-Editor für CDC &#40;Seite „Verbindungs-Manager“&#41;</span><span class="sxs-lookup"><span data-stu-id="ddac7-158">CDC Source Editor &#40;Connection Manager Page&#41;</span></span>](../cdc-source-editor-connection-manager-page.md)  
  
-   [<span data-ttu-id="ddac7-159">Quellen-Editor für CDC &#40;Seite „Spalten“&#41;</span><span class="sxs-lookup"><span data-stu-id="ddac7-159">CDC Source Editor &#40;Columns Page&#41;</span></span>](../cdc-source-editor-columns-page.md)  
  
-   [<span data-ttu-id="ddac7-160">Quellen-Editor für CDC &#40;Seite „Fehlerausgabe“&#41;</span><span class="sxs-lookup"><span data-stu-id="ddac7-160">CDC Source Editor &#40;Error Output Page&#41;</span></span>](../cdc-source-editor-error-output-page.md)  
  
-   [<span data-ttu-id="ddac7-161">Benutzerdefinierte Eigenschaften der CDC-Quelle</span><span class="sxs-lookup"><span data-stu-id="ddac7-161">CDC Source Custom Properties</span></span>](cdc-source-custom-properties.md)  
  
-   [<span data-ttu-id="ddac7-162">Extrahieren von Änderungsdaten mithilfe der CDC-Quelle</span><span class="sxs-lookup"><span data-stu-id="ddac7-162">Extract Change Data Using the CDC Source</span></span>](cdc-source.md)  
  
## <a name="related-content"></a><span data-ttu-id="ddac7-163">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="ddac7-163">Related Content</span></span>  
  
-   <span data-ttu-id="ddac7-164">Blogeintrag, [Processing Modes for the CDC Source](https://www.mattmasson.com/2012/01/processing-modes-for-the-cdc-source/), auf mattmasson.com.</span><span class="sxs-lookup"><span data-stu-id="ddac7-164">Blog entry, [Processing Modes for the CDC Source](https://www.mattmasson.com/2012/01/processing-modes-for-the-cdc-source/), on mattmasson.com.</span></span>  
  
  
