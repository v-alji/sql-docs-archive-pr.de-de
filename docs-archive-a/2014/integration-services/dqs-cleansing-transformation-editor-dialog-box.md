---
title: Transformations-Editor für die DQS-Bereinigung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssdqs.designer.cleansing.f1
- SQL12.SSDQS.DESIGNER.DQCONNECTION.F1
ms.assetid: 07e79641-71ee-45d0-a9ba-ed6f9f68f333
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e97cd138bb17ce3cfe476496e5bc576875728224
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608766"
---
# <a name="dqs-cleansing-transformation-editor-dialog-box"></a><span data-ttu-id="c0c51-102">Transformations-Editor für die DQS-Bereinigung (Dialogfeld)</span><span class="sxs-lookup"><span data-stu-id="c0c51-102">DQS Cleansing Transformation Editor Dialog Box</span></span>
  <span data-ttu-id="c0c51-103">Im Dialogfeld **Transformations-Editor für die DQS-Bereinigung** können Sie Daten mithilfe von Data Quality Services (DQS) korrigieren.</span><span class="sxs-lookup"><span data-stu-id="c0c51-103">Use the **DQS Cleansing Transformation Editor** dialog box to correct data using Data Quality Services (DQS).</span></span> <span data-ttu-id="c0c51-104">Weitere Informationen finden Sie unter [Data Quality Services Concepts](../../2014/data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="c0c51-104">For more information, see [Data Quality Services Concepts](../../2014/data-quality-services/data-quality-services-concepts.md).</span></span>  
  
 <span data-ttu-id="c0c51-105">Weitere Informationen zur Transformation finden Sie unter [DQS Cleansing Transformation](data-flow/transformations/dqs-cleansing-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="c0c51-105">To learn more about the transformation, see [DQS Cleansing Transformation](data-flow/transformations/dqs-cleansing-transformation.md).</span></span>  
  
 <span data-ttu-id="c0c51-106">**Was möchten Sie tun?**</span><span class="sxs-lookup"><span data-stu-id="c0c51-106">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="c0c51-107">Öffnen des Transformations-Editors für die DQS-Bereinigung</span><span class="sxs-lookup"><span data-stu-id="c0c51-107">Open the DQS Cleansing Transformation Editor</span></span>](#open)  
  
-   [<span data-ttu-id="c0c51-108">Festlegen der Optionen auf der Registerkarte "Verbindungs-Manager"</span><span class="sxs-lookup"><span data-stu-id="c0c51-108">Set options on the Connection Manager tab</span></span>](#connection)  
  
-   [<span data-ttu-id="c0c51-109">Festlegen von Optionen auf der Registerkarte "Zuordnung"</span><span class="sxs-lookup"><span data-stu-id="c0c51-109">Set options on the Mapping tab</span></span>](#mapping)  
  
-   [<span data-ttu-id="c0c51-110">Festlegen der Optionen auf der Registerkarte "Erweitert"</span><span class="sxs-lookup"><span data-stu-id="c0c51-110">Set options on the Advanced tab</span></span>](#advanced)  
  
-   [<span data-ttu-id="c0c51-111">Festlegen der Optionen im Dialogfeld "Verbindungs-Manager für DQS-Bereinigung"</span><span class="sxs-lookup"><span data-stu-id="c0c51-111">Set the options in the DQS Cleansing Connection Manager dialog box</span></span>](#manager)  
  
##  <a name="open-the-dqs-cleansing-transformation-editor"></a><a name="open"></a> <span data-ttu-id="c0c51-112">Öffnen des Transformations-Editors für die DQS-Bereinigung</span><span class="sxs-lookup"><span data-stu-id="c0c51-112">Open the DQS Cleansing Transformation Editor</span></span>  
  
1.  <span data-ttu-id="c0c51-113">Fügen Sie die DQS-Bereinigungstransformation dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]hinzu.</span><span class="sxs-lookup"><span data-stu-id="c0c51-113">Add the DQS Cleansing Transformation to [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="c0c51-114">Klicken Sie mit der rechten Maustaste auf die Komponente, und klicken Sie anschließend auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="c0c51-114">Right-click the component and then click **Edit**.</span></span>  
  
##  <a name="set-options-on-the-connection-manager-tab"></a><a name="connection"></a><span data-ttu-id="c0c51-115">Festlegen von Optionen auf der Registerkarte "Verbindungs-Manager"</span><span class="sxs-lookup"><span data-stu-id="c0c51-115">Set options on the Connection Manager tab</span></span>  
 <span data-ttu-id="c0c51-116">**Data Quality Services-Verbindungs-Manager**</span><span class="sxs-lookup"><span data-stu-id="c0c51-116">**Data quality connection manager**</span></span>  
 <span data-ttu-id="c0c51-117">Wählen Sie in der Liste einen vorhandenen DQS-Verbindungs-Manager aus, oder erstellen Sie eine neue Verbindung, indem Sie auf **Neu**klicken.</span><span class="sxs-lookup"><span data-stu-id="c0c51-117">Select an existing DQS connection manager from the list, or create a new connection by clicking **New**.</span></span>  
  
 <span data-ttu-id="c0c51-118">**Neu**</span><span class="sxs-lookup"><span data-stu-id="c0c51-118">**New**</span></span>  
 <span data-ttu-id="c0c51-119">Erstellen Sie mithilfe des Dialogfelds **Verbindungs-Manager für DQS-Bereinigung** einen neuen Verbindungs-Manager.</span><span class="sxs-lookup"><span data-stu-id="c0c51-119">Create a new connection manager by using the **DQS Cleansing Connection Manager** dialog box.</span></span> <span data-ttu-id="c0c51-120">Siehe [Festlegen der Optionen im Dialogfeld Verbindungs-Manager für DQS-Bereinigung](#manager)</span><span class="sxs-lookup"><span data-stu-id="c0c51-120">See [Set the options in the DQS Cleansing Connection Manager dialog box](#manager)</span></span>  
  
 <span data-ttu-id="c0c51-121">**Data Quality-Wissensdatenbank**</span><span class="sxs-lookup"><span data-stu-id="c0c51-121">**Data Quality Knowledge Base**</span></span>  
 <span data-ttu-id="c0c51-122">Wählen Sie eine vorhandene DQS-Wissensdatenbank für die verbundene Datenquelle aus.</span><span class="sxs-lookup"><span data-stu-id="c0c51-122">Select an existing DQS knowledge base for the connected data source.</span></span> <span data-ttu-id="c0c51-123">Weitere Informationen zur DQS-Wissensdatenbank finden Sie unter [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="c0c51-123">For more information about the DQS knowledge base, see [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
 <span data-ttu-id="c0c51-124">**Verbindung verschlüsseln**</span><span class="sxs-lookup"><span data-stu-id="c0c51-124">**Encrypt connection**</span></span>  
 <span data-ttu-id="c0c51-125">Geben Sie an, ob die Verbindung verschlüsselt werden soll, um die Datenübertragung zwischen dem DQS-Server und zu verschlüsseln [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c0c51-125">specify whether to encrypt the connection, in order to encrypt the data transfer between the DQS Server and [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="c0c51-126">**Verfügbare Domänen**</span><span class="sxs-lookup"><span data-stu-id="c0c51-126">**Available domains**</span></span>  
 <span data-ttu-id="c0c51-127">Listet die verfügbaren Domänen für die ausgewählte Wissensdatenbank auf.</span><span class="sxs-lookup"><span data-stu-id="c0c51-127">Lists the available domains for the selected knowledge base.</span></span> <span data-ttu-id="c0c51-128">Es gibt zwei Typen von Domänen: einzelne Domänen und Verbunddomänen, die aus mindestens zwei einzelnen Domänen bestehen.</span><span class="sxs-lookup"><span data-stu-id="c0c51-128">There are two types of domains: single domains, and composite domains that contain two or more single domains.</span></span>  
  
 <span data-ttu-id="c0c51-129">Weitere Informationen zum Zuordnen von Spalten zu Verbunddomänen finden Sie unter [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span><span class="sxs-lookup"><span data-stu-id="c0c51-129">For information on how to map columns to composite domains, see [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span></span>  
  
 <span data-ttu-id="c0c51-130">Weitere Informationen zu Domänen finden Sie unter [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span><span class="sxs-lookup"><span data-stu-id="c0c51-130">For more information about domains, see [DQS Knowledge Bases and Domains](../../2014/data-quality-services/dqs-knowledge-bases-and-domains.md).</span></span>  
  
 <span data-ttu-id="c0c51-131">**Konfigurieren der Fehlerausgabe**</span><span class="sxs-lookup"><span data-stu-id="c0c51-131">**Configure Error Output**</span></span>  
 <span data-ttu-id="c0c51-132">Gibt an, wie Fehler auf Zeilenebene verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="c0c51-132">Specify how to handle row-level errors.</span></span> <span data-ttu-id="c0c51-133">Wenn durch die Transformation Daten aus der verbundenen Datenquelle korrigiert werden, können aufgrund unerwarteter Datenwerte oder Überprüfungseinschränkungen Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="c0c51-133">Errors can occur when the transformation corrects data from the connected data source, due to unexpected data values or validation constraints.</span></span>  
  
 <span data-ttu-id="c0c51-134">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="c0c51-134">The following are the valid values:</span></span>  
  
-   <span data-ttu-id="c0c51-135">**Fehler bei Komponente**gibt an, dass die Transformation fehlgeschlagen ist und dass die Eingabedaten nicht in die Data Quality Services-Datenbank eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c0c51-135">**Fail Component**, which indicates that the transformation fails and the input data is not inserted into the Data Quality Services database.</span></span> <span data-ttu-id="c0c51-136">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="c0c51-136">This is the default value.</span></span>  
  
-   <span data-ttu-id="c0c51-137">**Zeile umleiten**gibt an, dass die Eingabedaten nicht in die Data Quality Services-Datenbank eingefügt und an die Fehlerausgabe umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c0c51-137">**Redirect Row**, which indicates that the input data is not inserted into the Data Quality Services database and is redirected to the error output.</span></span>  
  
##  <a name="set-options-on-the-mapping-tab"></a><a name="mapping"></a> <span data-ttu-id="c0c51-138">Festlegen der Optionen auf der Registerkarte "Zuordnung"</span><span class="sxs-lookup"><span data-stu-id="c0c51-138">Set options on the Mapping tab</span></span>  
 <span data-ttu-id="c0c51-139">Weitere Informationen zum Zuordnen von Spalten zu Verbunddomänen finden Sie unter [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span><span class="sxs-lookup"><span data-stu-id="c0c51-139">For information on how to map columns to composite domains, see [Map Columns to Composite Domains](data-flow/transformations/map-columns-to-composite-domains.md).</span></span>  
  
 <span data-ttu-id="c0c51-140">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="c0c51-140">**Available Input Columns**</span></span>  
 <span data-ttu-id="c0c51-141">Listet die Spalten aus der verbundenen Datenquelle auf.</span><span class="sxs-lookup"><span data-stu-id="c0c51-141">Lists the columns from the connected data source.</span></span> <span data-ttu-id="c0c51-142">Wählen Sie Spalten aus, die zu korrigierende Daten enthalten.</span><span class="sxs-lookup"><span data-stu-id="c0c51-142">Select one or more columns that contain data that you want to correct.</span></span>  
  
 <span data-ttu-id="c0c51-143">**Eingabespalte**</span><span class="sxs-lookup"><span data-stu-id="c0c51-143">**Input Column**</span></span>  
 <span data-ttu-id="c0c51-144">Zeigt eine im Bereich **Verfügbare Eingabespalten** ausgewählte Eingabespalte an.</span><span class="sxs-lookup"><span data-stu-id="c0c51-144">Lists an input column that you selected in the **Available Input Columns** area.</span></span>  
  
 <span data-ttu-id="c0c51-145">**Domäne**</span><span class="sxs-lookup"><span data-stu-id="c0c51-145">**Domain**</span></span>  
 <span data-ttu-id="c0c51-146">Wählen Sie eine Domäne aus, die der Eingabespalte zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c0c51-146">Select a domain to map to the input column.</span></span>  
  
 <span data-ttu-id="c0c51-147">**Alias – Quelle**</span><span class="sxs-lookup"><span data-stu-id="c0c51-147">**Source Alias**</span></span>  
 <span data-ttu-id="c0c51-148">Zeigt die Quellspalte an, die den ursprünglichen Spaltenwert enthält.</span><span class="sxs-lookup"><span data-stu-id="c0c51-148">Lists the source column that contains the original column value.</span></span>  
  
 <span data-ttu-id="c0c51-149">Klicken Sie in das Feld, um den Spaltennamen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c0c51-149">Click in the field to modify the column name.</span></span>  
  
 <span data-ttu-id="c0c51-150">**Ausgabealias**</span><span class="sxs-lookup"><span data-stu-id="c0c51-150">**Output Alias**</span></span>  
 <span data-ttu-id="c0c51-151">Zeigt die Spalte an, die vom **Transformations-Editor für die DQS-Bereinigung**ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c0c51-151">Lists the column that is outputted by the **DQS Cleansing Transformation**.</span></span> <span data-ttu-id="c0c51-152">Die Spalte enthält den ursprünglichen Spaltenwert oder den korrigierten Wert.</span><span class="sxs-lookup"><span data-stu-id="c0c51-152">The column contains the original column value or the corrected value.</span></span>  
  
 <span data-ttu-id="c0c51-153">Klicken Sie in das Feld, um den Spaltennamen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c0c51-153">Click in the field to modify the column name.</span></span>  
  
 <span data-ttu-id="c0c51-154">**Alias – Status**</span><span class="sxs-lookup"><span data-stu-id="c0c51-154">**Status Alias**</span></span>  
 <span data-ttu-id="c0c51-155">Zeigt die Spalte an, die Statusinformationen für die korrigierten Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="c0c51-155">Lists the column that contains status information for the corrected data.</span></span> <span data-ttu-id="c0c51-156">Klicken Sie in das Feld, um den Spaltennamen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c0c51-156">Click in the field to modify the column name.</span></span>  
  
##  <a name="set-options-on-the-advanced-tab"></a><a name="advanced"></a><span data-ttu-id="c0c51-157">Festlegen von Optionen auf der Registerkarte "Erweitert"</span><span class="sxs-lookup"><span data-stu-id="c0c51-157">Set options on the Advanced tab</span></span>  
 <span data-ttu-id="c0c51-158">**Ausgabe standardisieren**</span><span class="sxs-lookup"><span data-stu-id="c0c51-158">**Standardize output**</span></span>  
 <span data-ttu-id="c0c51-159">Gibt an, ob die Daten im standardisierten Format auf Grundlage des für Domänen definierten Ausgabeformats ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0c51-159">Indicate whether to output the data in the standardized format based on the output format defined for domains.</span></span> <span data-ttu-id="c0c51-160">Weitere Informationen zum standardisierten Format finden Sie unter [Datenbereinigung](../../2014/data-quality-services/data-cleansing.md).</span><span class="sxs-lookup"><span data-stu-id="c0c51-160">For more information about standardized format, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).</span></span>  
  
 <span data-ttu-id="c0c51-161">**Fi**</span><span class="sxs-lookup"><span data-stu-id="c0c51-161">**Confidence**</span></span>  
 <span data-ttu-id="c0c51-162">Gibt an, ob der Vertrauensgrad für korrigierte Daten eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="c0c51-162">Indicate whether to include the confidence level for corrected data.</span></span> <span data-ttu-id="c0c51-163">Der Vertrauensgrad gibt die DQS-Sicherheitsstufe der Korrektur oder des Vorschlags an.</span><span class="sxs-lookup"><span data-stu-id="c0c51-163">The confidence level indicates the extend of certainty of DQS for the correction or suggestion.</span></span> <span data-ttu-id="c0c51-164">Weitere Informationen zu Vertrauensgraden finden Sie unter [Datenbereinigung](../../2014/data-quality-services/data-cleansing.md).</span><span class="sxs-lookup"><span data-stu-id="c0c51-164">For more information about confidence levels, see [Data Cleansing](../../2014/data-quality-services/data-cleansing.md).</span></span>  
  
 <span data-ttu-id="c0c51-165">**`Reason`**</span><span class="sxs-lookup"><span data-stu-id="c0c51-165">**Reason**</span></span>  
 <span data-ttu-id="c0c51-166">Gibt an, ob der Grund für die Datenkorrektur eingeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="c0c51-166">Indicate whether to include the reason for the data correction.</span></span>  
  
 <span data-ttu-id="c0c51-167">**Angefügte Daten**</span><span class="sxs-lookup"><span data-stu-id="c0c51-167">**Appended Data**</span></span>  
 <span data-ttu-id="c0c51-168">Gibt an, ob weitere, von einem vorhandenen Verweisdatenanbieter empfangene Daten ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c0c51-168">Indicate whether to output additional data that is received from an existing reference data provider.</span></span> <span data-ttu-id="c0c51-169">Weitere Informationen finden Sie unter [Reference Data Services in DQS](../../2014/data-quality-services/reference-data-services-in-dqs.md).</span><span class="sxs-lookup"><span data-stu-id="c0c51-169">For more information, see [Reference Data Services in DQS](../../2014/data-quality-services/reference-data-services-in-dqs.md).</span></span>  
  
 <span data-ttu-id="c0c51-170">**Angefügtes Datenschema**</span><span class="sxs-lookup"><span data-stu-id="c0c51-170">**Appended Data Schema**</span></span>  
 <span data-ttu-id="c0c51-171">Gibt an, ob das Datenschema ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c0c51-171">Indicate whether to output the data schema.</span></span> <span data-ttu-id="c0c51-172">Weitere Informationen finden Sie unter [Anfügen einer Domäne oder Verbund Domäne an Verweis Daten](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span><span class="sxs-lookup"><span data-stu-id="c0c51-172">For more information, see [Attach a Domain or Composite Domain to Reference Data](../../2014/data-quality-services/attach-a-domain-or-composite-domain-to-reference-data.md).</span></span>  
  
##  <a name="set-the-options-in-the-dqs-cleansing-connection-manager-dialog-box"></a><a name="manager"></a><span data-ttu-id="c0c51-173">Festlegen der Optionen im Dialogfeld "Verbindungs-Manager für DQS-Bereinigung"</span><span class="sxs-lookup"><span data-stu-id="c0c51-173">Set the options in the DQS Cleansing Connection Manager dialog box</span></span>  
 <span data-ttu-id="c0c51-174">**Servername**</span><span class="sxs-lookup"><span data-stu-id="c0c51-174">**Server name**</span></span>  
 <span data-ttu-id="c0c51-175">Wählen Sie den Namen des DQS-Servers aus, mit dem Sie eine Verbindung herstellen möchten, oder geben Sie ihn ein.</span><span class="sxs-lookup"><span data-stu-id="c0c51-175">Select or type the name of the DQS server that you want to connect to.</span></span> <span data-ttu-id="c0c51-176">Weitere Informationen zum Server finden Sie unter [DQS Administration](../../2014/data-quality-services/dqs-administration.md).</span><span class="sxs-lookup"><span data-stu-id="c0c51-176">For more information about the server, see [DQS Administration](../../2014/data-quality-services/dqs-administration.md).</span></span>  
  
 <span data-ttu-id="c0c51-177">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="c0c51-177">**Test Connection**</span></span>  
 <span data-ttu-id="c0c51-178">Klicken Sie auf diese Schaltfläche, um zu überprüfen, ob die angegebene Verbindung gültig ist.</span><span class="sxs-lookup"><span data-stu-id="c0c51-178">Click to confirm that the connection that you specified is viable.</span></span>  
  
 <span data-ttu-id="c0c51-179">Sie können das Dialogfeld **Verbindungs-Manager für DQS-Bereinigung** auch wie folgt über den Verbindungsbereich öffnen:</span><span class="sxs-lookup"><span data-stu-id="c0c51-179">You can also open the **DQS Cleansing Connection Manager** dialog box from the connections area, by doing the following:</span></span>  
  
1.  <span data-ttu-id="c0c51-180">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]ein vorhandenes [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt, oder erstellen Sie ein neues Projekt.</span><span class="sxs-lookup"><span data-stu-id="c0c51-180">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open an existing [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project or create a new one.</span></span>  
  
2.  <span data-ttu-id="c0c51-181">Klicken Sie im Verbindungsbereich mit der rechten Maustaste auf **Neue Verbindung**, und klicken Sie anschließend auf **DQS**.</span><span class="sxs-lookup"><span data-stu-id="c0c51-181">Right-click in the connections area, click **New Connection**, and then click **DQS**.</span></span>  
  
3.  <span data-ttu-id="c0c51-182">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c0c51-182">Click **Add**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0c51-183">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c0c51-183">See Also</span></span>  
 [<span data-ttu-id="c0c51-184">Anwenden von Datenqualitätsregeln auf eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="c0c51-184">Apply Data Quality Rules to Data Source</span></span>](data-flow/transformations/apply-data-quality-rules-to-data-source.md)  
  
  
