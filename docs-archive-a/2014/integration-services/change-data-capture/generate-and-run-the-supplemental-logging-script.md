---
title: Generieren und Ausführen des ergänzenden Protokollierungsskripts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- supLog
ms.assetid: 6e940d93-12c6-4cda-9333-5489b245f0e4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1437a4b0f790376268095d8e52afa981af865b44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695989"
---
# <a name="generate-and-run-the-supplemental-logging-script"></a><span data-ttu-id="1ebdd-102">Generieren und Ausführen des ergänzenden Protokollierungsskripts</span><span class="sxs-lookup"><span data-stu-id="1ebdd-102">Generate and Run the Supplemental Logging Script</span></span>
  <span data-ttu-id="1ebdd-103">Verwenden Sie die Seite Set up Tables for Capturing Changes, um ein Skript für die Oracle-Quelldatenbank auszuführen, mit dem die ergänzende Protokollierung eingerichtet wird.</span><span class="sxs-lookup"><span data-stu-id="1ebdd-103">Use the Set up Tables for Capturing Changes page to run a script on the Oracle source database that will set up supplemental logging.</span></span>  
  
 <span data-ttu-id="1ebdd-104">**So führen Sie die ergänzenden Protokollierungsskripts aus**</span><span class="sxs-lookup"><span data-stu-id="1ebdd-104">**To run the supplemental logging scripts**</span></span>  
  
 <span data-ttu-id="1ebdd-105">Klicken Sie auf **Run Script** , um das ergänzende Protokollierungsskript für die Tabellen auszuführen, die für die CDC-Instanz definiert sind.</span><span class="sxs-lookup"><span data-stu-id="1ebdd-105">Click **Run Script** to run the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="1ebdd-106">Dieses Skript weist die Oracle-Datenbank an, beim Protokollieren von UPDATE-Vorgängen zu aufgezeichneten Tabellen alle wichtigen Spalten in ihre Transaktionsprotokolle zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="1ebdd-106">This script instructs the Oracle database to write all columns of interest to its transaction logs when logging UPDATE operations to captured tables.</span></span> <span data-ttu-id="1ebdd-107">Dieses Skript wird normalerweise von einem Oracle-Systemadministrator geprüft und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="1ebdd-107">This script is normally examined and executed by an Oracle system administrator.</span></span>  
  
 <span data-ttu-id="1ebdd-108">Sie können die Skripts mit SQL\*Plus auch manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="1ebdd-108">You can also run the scripts manually using SQL \* Plus.</span></span>  
  
 <span data-ttu-id="1ebdd-109">**So führen Sie Skripts manuell aus**</span><span class="sxs-lookup"><span data-stu-id="1ebdd-109">**To run the scripts manually**</span></span>  
  
 <span data-ttu-id="1ebdd-110">Klicken Sie auf **Kopieren** , um das Skript in die Zwischenablage einzufügen.</span><span class="sxs-lookup"><span data-stu-id="1ebdd-110">Click **Copy** to paste the script to the clipboard.</span></span> <span data-ttu-id="1ebdd-111">Öffnen Sie SQL\*Plus, und greifen Sie auf das Verzeichnis mit der Oracle-Quelldatenbank zu.</span><span class="sxs-lookup"><span data-stu-id="1ebdd-111">Open SQL\* Plus and go to the directory with your Oracle source database.</span></span> <span data-ttu-id="1ebdd-112">Fügen Sie das Skript in SQL\*Plus ein, um es auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1ebdd-112">Paste the script into SQL\*Plus to run it.</span></span>  
  
 <span data-ttu-id="1ebdd-113">Um das ergänzende Protokollierungsskript in einer Textdatei zu speichern, klicken Sie auf **Speichern unter** und greifen auf den Speicherort zu, an dem Sie die Datei speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="1ebdd-113">To save the supplemental logging script in a text file, click **Save as** and browse to the location where you want to save the file.</span></span> <span data-ttu-id="1ebdd-114">Geben Sie der Datei einen Namen, und klicken Sie auf **Speichern** , um die Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="1ebdd-114">Give the file a name and click **Save** to save the file.</span></span>  
  
 <span data-ttu-id="1ebdd-115">Klicken Sie auf **Weiter** , um den Schritt [Generate Mirror Tables and CDC Capture Instances](generate-mirror-tables-and-cdc-capture-instances.md)auszuführen.</span><span class="sxs-lookup"><span data-stu-id="1ebdd-115">Click **Next** to [Generate Mirror Tables and CDC Capture Instances](generate-mirror-tables-and-cdc-capture-instances.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ebdd-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1ebdd-116">See Also</span></span>  
 <span data-ttu-id="1ebdd-117">[Erstellen der Instanz für die SQL Server-Änderungsdatenbank](how-to-create-the-sql-server-change-database-instance.md) </span><span class="sxs-lookup"><span data-stu-id="1ebdd-117">[How to Create the SQL Server Change Database Instance](how-to-create-the-sql-server-change-database-instance.md) </span></span>  
 [<span data-ttu-id="1ebdd-118">Überprüfen und Generieren ergänzender Protokollierungsskripts</span><span class="sxs-lookup"><span data-stu-id="1ebdd-118">Review and Generate Supplemental Logging Scripts</span></span>](review-and-generate-supplemental-logging-scripts.md)  
  
  
