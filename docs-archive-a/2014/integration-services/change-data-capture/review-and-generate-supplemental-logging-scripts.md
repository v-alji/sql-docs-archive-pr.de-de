---
title: Überprüfen und Generieren ergänzender Protokollierungsskripts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- scripts
ms.assetid: 5c858ae2-37d6-42e8-a252-7f6ed4e628a7
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cb735c0ee318ac68d48c71c09fc76ec305eb2552
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616136"
---
# <a name="review-and-generate-supplemental-logging-scripts"></a><span data-ttu-id="b2f4d-102">Überprüfen und Generieren ergänzender Protokollierungsskripts</span><span class="sxs-lookup"><span data-stu-id="b2f4d-102">Review and Generate Supplemental Logging Scripts</span></span>
  <span data-ttu-id="b2f4d-103">Verwenden Sie die Registerkarte **Skripts** , um ein Skript für die Oracle-Quelldatenbank auszuführen bzw. erneut auszuführen, mit dem die ergänzende Protokollierung eingerichtet wird.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-103">Use the **Scripts** tab to run or re-run a script on the Oracle source database that sets up supplemental logging.</span></span>  
  
 <span data-ttu-id="b2f4d-104">Wählen Sie vor dem Ausführen der Skripts eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="b2f4d-104">Before you run the scripts select one of the following:</span></span>  
  
 <span data-ttu-id="b2f4d-105">**Include changes in this session**</span><span class="sxs-lookup"><span data-stu-id="b2f4d-105">**Include changes in this session**</span></span>  
 <span data-ttu-id="b2f4d-106">Wählen Sie diese Option, um das Skript für alle neuen Tabellen auszuführen, die der CDC-Instanz hinzugefügt wurden, oder für Tabellen, die mit dem Eigenschaften-Editor geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-106">Select this to run the script on any new table that was added to the CDC instance or on tables that were changed in any way using the Properties editor.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="b2f4d-107">Wenn an den Tabellen in der CDC-Instanz keine Änderungen vorgenommen wurden, ist der Bereich des ergänzenden Oracle-Protokollierungsskripts leer.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-107">If no changes were made to the tables in the CDC instance, the Oracle supplemental logging script area will be empty.</span></span>  
  
 <span data-ttu-id="b2f4d-108">**Include all tables/capture instances**</span><span class="sxs-lookup"><span data-stu-id="b2f4d-108">**Include all tables/capture instances**</span></span>  
 <span data-ttu-id="b2f4d-109">Wählen Sie diese Option, um das Skript für alle Tabellen und Aufzeichnungsinstanzen in der CDC-Instanz auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-109">Select this to run the script on all of the tables and capture instances in the CDC instance.</span></span>  
  
 <span data-ttu-id="b2f4d-110">Führen Sie das ergänzende Protokollierungsskript aus, nachdem Sie eine dieser Optionen ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-110">After you select one of these options, run the supplemental logging script.</span></span>  
  
### <a name="to-run-the-supplemental-logging-scripts"></a><span data-ttu-id="b2f4d-111">So führen Sie die ergänzenden Protokollierungsskripts aus</span><span class="sxs-lookup"><span data-stu-id="b2f4d-111">To run the supplemental logging scripts</span></span>  
  
1.  <span data-ttu-id="b2f4d-112">Klicken Sie auf **Run Script** , um das ergänzende Protokollierungsskript für die Tabellen auszuführen, die für die CDC-Instanz definiert sind.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-112">Click **Run Script** to run the supplemental logging script on the tables defined for the CDC instance.</span></span> <span data-ttu-id="b2f4d-113">Dieses Skript weist die Oracle-Datenbank an, beim Protokollieren von UPDATE-Vorgängen zu aufgezeichneten Tabellen alle wichtigen Spalten in ihre Transaktionsprotokolle zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-113">This script instructs the Oracle database to write all columns of interest to its transaction logs when logging UPDATE operations to captured tables.</span></span> <span data-ttu-id="b2f4d-114">Dieses Skript wird normalerweise von einem Oracle-Systemadministrator geprüft und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-114">This script is normally examined and executed by an Oracle system administrator.</span></span>  
  
2.  <span data-ttu-id="b2f4d-115">Wenn Sie die ergänzenden Protokollierungsskripts ausführen, wird das Dialogfeld Oracle Credentials for Running Script geöffnet, in dem Sie einen gültigen Oracle-Benutzernamen und das dazugehörige Kennwort angeben können.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-115">When you run the supplemental logging scripts, the Oracle Credentials for Running Script dialog box opens where you provide a valid Oracle user name and password.</span></span> <span data-ttu-id="b2f4d-116">Informationen zum Bereitstellen der richtigen Oracle-Anmeldeinformationen finden Sie unter [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span><span class="sxs-lookup"><span data-stu-id="b2f4d-116">For information on how to provide the proper Oracle credentials, see [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span></span>  
  
 <span data-ttu-id="b2f4d-117">Bei Bedarf können Sie die Skripts mithilfe von SQL\*Plus auch manuell ausführen.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-117">You can also run the scripts manually using SQL \* Plus, if necessary.</span></span>  
  
### <a name="to-run-the-scripts-manually"></a><span data-ttu-id="b2f4d-118">So führen Sie Skripts manuell aus</span><span class="sxs-lookup"><span data-stu-id="b2f4d-118">To run the scripts manually</span></span>  
  
1.  <span data-ttu-id="b2f4d-119">Klicken Sie auf **Kopieren** , um das Skript in die Zwischenablage einzufügen.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-119">Click **Copy** to paste the script to the clipboard.</span></span> <span data-ttu-id="b2f4d-120">Öffnen Sie SQL\*Plus, und greifen Sie auf das Verzeichnis mit der Oracle-Quelldatenbank zu.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-120">Open SQL\* Plus and go to the directory with your Oracle source database.</span></span> <span data-ttu-id="b2f4d-121">Fügen Sie das Skript in SQL\*Plus ein, um es auszuführen.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-121">Paste the script into SQL\*Plus to run it.</span></span>  
  
### <a name="to-save-the-supplemental-logging-script-in-a-text-file"></a><span data-ttu-id="b2f4d-122">So speichern Sie das ergänzende Protokollierungsskript in einer Textdatei</span><span class="sxs-lookup"><span data-stu-id="b2f4d-122">To save the supplemental logging script in a text file</span></span>  
  
1.  <span data-ttu-id="b2f4d-123">Klicken Sie auf **Speichern unter** , und greifen Sie auf den Speicherort zu, an dem Sie die Datei speichern möchten.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-123">Click **Save as** and browse to the location where you want to save the file.</span></span>  
  
2.  <span data-ttu-id="b2f4d-124">Geben Sie der Datei einen Namen, und klicken Sie auf **Speichern** , um die Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="b2f4d-124">Give the file a name and click **Save** to save the file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2f4d-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2f4d-125">See Also</span></span>  
 <span data-ttu-id="b2f4d-126">[Bearbeiten der CDC-Instanzeigenschaften](how-to-edit-the-cdc-instance-properties.md) </span><span class="sxs-lookup"><span data-stu-id="b2f4d-126">[How to Edit the CDC Instance Properties](how-to-edit-the-cdc-instance-properties.md) </span></span>  
 [<span data-ttu-id="b2f4d-127">Oracle-Anmeldeinformationen zum Ausführen von Skripts</span><span class="sxs-lookup"><span data-stu-id="b2f4d-127">Oracle Credentials for Running Script</span></span>](oracle-credentials-for-running-script.md)  
  
  
