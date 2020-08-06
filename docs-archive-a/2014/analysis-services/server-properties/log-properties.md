---
title: Protokoll Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- QueryLogFileSize property
- QueryLogTableName property
- TraceBackgroundDistributionPeriod property
- TraceMaxRowsetSize property
- NullKeyConvertedToUnknown property
- CrashReportsFolder property
- TraceDefinitionFile property
- SQLDumperFlagsOn property
- KeyErrorLimit property
- SnapshotDefinitionFile property
- MinidumpErrorList property
- ErrorLogFileName property
- KeyDuplicate property
- IgnoreDataTruncation property
- logs [Analysis Services]
- Enabled property
- FileSizeMB property
- TraceFileWriteTrailerPeriod property
- TraceQueryResponseTextChunkSize property
- File property
- FileBufferSize property
- TraceRowsetBackgroundFlushPeriod property
- ErrorLogFileSize property
- TraceRequestParameters property
- KeyErrorLimitAction property
- CreateQueryLogTable property
- LogDir property
- TraceBackgroundFlushPeriod property
- TraceFileBufferSize property
- SQLDumperFlagsOff property
- QueryLogConnectionString property
- KeyNotFound property
- KeyErrorLogFile property
- TraceReportFQDN property
- KeyErrorAction property
- QueryLogFileName property
- MessageLogs property
- MiniDumpFlagsOn property
- SnapshotFrequencySec property
- QueryLogSampling property
- CreateAndSendCrashReports property
- LogDurationSec property
ms.assetid: 33fd90ee-cead-48f0-8ff9-9b458994c766
author: minewiskan
ms.author: owend
ms.openlocfilehash: 3761ce3dca232db8968a2a7cba083dcc5554d792
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727166"
---
# <a name="log-properties"></a><span data-ttu-id="3ba13-102">Protokolleigenschaften</span><span class="sxs-lookup"><span data-stu-id="3ba13-102">Log Properties</span></span>
  [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="3ba13-103">werden die in den folgenden Tabellen aufgeführten Protokollservereigenschaften unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3ba13-103">supports the log server properties listed in the following tables.</span></span> <span data-ttu-id="3ba13-104">Weitere Informationen zu zusätzlichen Servereigenschaften und zum Festlegen dieser Eigenschaften finden Sie unter [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="3ba13-104">For more information about additional server properties and how to set them, see [Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md).</span></span>  
  
## <a name="general"></a><span data-ttu-id="3ba13-105">Allgemein</span><span class="sxs-lookup"><span data-stu-id="3ba13-105">General</span></span>  
 `File`  
 <span data-ttu-id="3ba13-106">Eine Zeichenfolge, die den Namen der Serverprotokolldatei anzeigt.</span><span class="sxs-lookup"><span data-stu-id="3ba13-106">A string property that identifies the name of the server log file.</span></span> <span data-ttu-id="3ba13-107">Diese Eigenschaft gilt nur, wenn für die Protokollierung eine Datei auf dem Datenträger anstelle einer Datenbanktabelle (das Standardverhalten) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3ba13-107">This property only applies when a disk file is used for logging, as opposed to a database table (the default behavior).</span></span>  
  
 <span data-ttu-id="3ba13-108">Der Standardwert für diese Eigenschaft ist msmdsrv.log.</span><span class="sxs-lookup"><span data-stu-id="3ba13-108">The default value for this property is msmdsrv.log.</span></span>  
  
 `FileBufferSize`  
 <span data-ttu-id="3ba13-109">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-109">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 `MessageLogs`  
 <span data-ttu-id="3ba13-110">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-110">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="error-log"></a><span data-ttu-id="3ba13-111">Fehlerprotokoll</span><span class="sxs-lookup"><span data-stu-id="3ba13-111">Error Log</span></span>  
 <span data-ttu-id="3ba13-112">Sie können diese Eigenschaften auf Serverinstanzebene festlegen, um die Standardwerte für die Fehlerkonfiguration zu ändern, die in anderen Tools und in Designern verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="3ba13-112">You can set these properties at the server instance level to modify the default values for Error Configuration that appear in other tools and designers.</span></span> <span data-ttu-id="3ba13-113">Weitere Informationen finden Sie [unter Fehler Konfiguration für die Verarbeitung von Cubes, Partitionen und Dimensionen &#40;SSAS-Multidimensional&#41;](../multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md) und <xref:Microsoft.AnalysisServices.MiningStructure.ErrorConfiguration%2A> .</span><span class="sxs-lookup"><span data-stu-id="3ba13-113">See [Error Configuration for Cube, Partition, and Dimension Processing &#40;SSAS - Multidimensional&#41;](../multidimensional-models/error-configuration-for-cube-partition-and-dimension-processing.md) and <xref:Microsoft.AnalysisServices.MiningStructure.ErrorConfiguration%2A> for more information.</span></span>  
  
 <span data-ttu-id="3ba13-114">**ErrorLog\ErrorLogFileName**</span><span class="sxs-lookup"><span data-stu-id="3ba13-114">**ErrorLog\ErrorLogFileName**</span></span>  
 <span data-ttu-id="3ba13-115">Diese Eigenschaft wird standardmäßig während des vom Server ausgeführten Verarbeitungsvorgangs verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ba13-115">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="3ba13-116">**ErrorLog\ErrorLogFileSize**</span><span class="sxs-lookup"><span data-stu-id="3ba13-116">**ErrorLog\ErrorLogFileSize**</span></span>  
 <span data-ttu-id="3ba13-117">Diese Eigenschaft wird standardmäßig während des vom Server ausgeführten Verarbeitungsvorgangs verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ba13-117">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="3ba13-118">**ErrorLog\KeyErrorAction**</span><span class="sxs-lookup"><span data-stu-id="3ba13-118">**ErrorLog\KeyErrorAction**</span></span>  
 <span data-ttu-id="3ba13-119">Gibt die Aktion an, die bei Auftreten eines `KeyNotFound`-Fehlers vom Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3ba13-119">Specifies the action taken by the server when a `KeyNotFound` error occurs.</span></span> <span data-ttu-id="3ba13-120">Gültige Serverreaktionen auf diesen Fehler sind:</span><span class="sxs-lookup"><span data-stu-id="3ba13-120">Valid responses to this error include:</span></span>  
  
-   <span data-ttu-id="3ba13-121">`ConvertToUnknown` weist den Server an, den Fehlerschlüsselwert dem unbekannten Element zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="3ba13-121">`ConvertToUnknown` tells the server to allocate the error key value to the unknown member.</span></span>  
  
-   <span data-ttu-id="3ba13-122">`DiscardRecord` weist den Server an, den Datensatz auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="3ba13-122">`DiscardRecord` tells the server to exclude the record.</span></span>  
  
 <span data-ttu-id="3ba13-123">**ErrorLog\KeyErrorLogFile**</span><span class="sxs-lookup"><span data-stu-id="3ba13-123">**ErrorLog\KeyErrorLogFile**</span></span>  
 <span data-ttu-id="3ba13-124">Dies ist ein benutzerdefinierter Dateiname, der über die Dateierweiterung .log verfügen und in einem Ordner gespeichert sein muss, für den das Dienstkonto Lese-/Schreibberechtigungen besitzt.</span><span class="sxs-lookup"><span data-stu-id="3ba13-124">This is a user-defined filename that must have a .log file extension, located in a folder on which the service account has read-write permissions.</span></span> <span data-ttu-id="3ba13-125">Die Protokolldatei enthält nur Fehler, die während der Verarbeitung generiert wurden.</span><span class="sxs-lookup"><span data-stu-id="3ba13-125">This log file will only contain errors generated during processing.</span></span> <span data-ttu-id="3ba13-126">Verwenden Sie Flight Recorder, wenn Sie ausführlichere Informationen benötigen.</span><span class="sxs-lookup"><span data-stu-id="3ba13-126">Use the Flight Recorder if you require more detailed information.</span></span>  
  
 <span data-ttu-id="3ba13-127">**ErrorLog\KeyErrorLimit**</span><span class="sxs-lookup"><span data-stu-id="3ba13-127">**ErrorLog\KeyErrorLimit**</span></span>  
 <span data-ttu-id="3ba13-128">Dies ist die maximale Anzahl von Datenintegritätsfehlern, die der Server toleriert, bevor die Verarbeitung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="3ba13-128">This is the maximum number of data integrity errors that the server will allow before failing the processing.</span></span> <span data-ttu-id="3ba13-129">Der Wert -1 steht für eine unbegrenzte Anzahl.</span><span class="sxs-lookup"><span data-stu-id="3ba13-129">A value of -1 indicates that there is no limit.</span></span> <span data-ttu-id="3ba13-130">Der Standardwert ist 0 und bewirkt, dass die Verarbeitung nach Auftreten des ersten Fehlers beendet wird.</span><span class="sxs-lookup"><span data-stu-id="3ba13-130">The default is 0, which means processing stops after the first error occurs.</span></span> <span data-ttu-id="3ba13-131">Sie können ihn auch auf eine ganze Zahl festlegen.</span><span class="sxs-lookup"><span data-stu-id="3ba13-131">You can also set it to a whole number.</span></span>  
  
 <span data-ttu-id="3ba13-132">**ErrorLog\KeyErrorLimitAction**</span><span class="sxs-lookup"><span data-stu-id="3ba13-132">**ErrorLog\KeyErrorLimitAction**</span></span>  
 <span data-ttu-id="3ba13-133">Gibt die Aktion an, die vom Server ausgeführt wird, nachdem die Obergrenze von Schlüsselfehlern erreicht wurde.</span><span class="sxs-lookup"><span data-stu-id="3ba13-133">Specifies the action taken by the server when the number of key errors has reached the upper limit.</span></span> <span data-ttu-id="3ba13-134">Gültige Serverreaktionen auf diese Aktion sind:</span><span class="sxs-lookup"><span data-stu-id="3ba13-134">Valid responses to this action include:</span></span>  
  
-   <span data-ttu-id="3ba13-135">`StopProcessing` weist den Server an, die Verarbeitung zu beenden, sobald die Fehlergrenze erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="3ba13-135">`StopProcessing` tells the server to stop processing when the error limit is reached.</span></span>  
  
-   <span data-ttu-id="3ba13-136">`StopLogging` weist den Server an, die Fehlerprotokollierung bei Erreichen der Fehlergrenze zu beenden, die Verarbeitung jedoch weiterhin zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="3ba13-136">`StopLogging` tells the server to stop logging errors when the error limit is reached, but allow processing to continue.</span></span>  
  
 <span data-ttu-id="3ba13-137">**ErrorLog\ LogErrorTypes\KeyNotFound**</span><span class="sxs-lookup"><span data-stu-id="3ba13-137">**ErrorLog\ LogErrorTypes\KeyNotFound**</span></span>  
 <span data-ttu-id="3ba13-138">Gibt die Aktion an, die bei Auftreten eines `KeyNotFound`-Fehlers vom Server ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="3ba13-138">Specifies the action taken by the server when a `KeyNotFound` error occurs.</span></span> <span data-ttu-id="3ba13-139">Gültige Serverreaktionen auf diesen Fehler sind:</span><span class="sxs-lookup"><span data-stu-id="3ba13-139">Valid responses to this error include:</span></span>  
  
-   <span data-ttu-id="3ba13-140">`IgnoreError` weist den Server an, die Verarbeitung fortzusetzen, ohne den Fehler zu protokollieren oder auf den Grenzwert für Schlüsselfehler anzurechnen.</span><span class="sxs-lookup"><span data-stu-id="3ba13-140">`IgnoreError` tells the server to continue processing without logging the error or counting it towards the key error limit.</span></span> <span data-ttu-id="3ba13-141">Wenn Sie den Fehler ignorieren, lassen Sie einfach die weitere Verarbeitung zu, ohne dass die Fehleranzahl erhöht oder der Fehler auf dem Bildschirm angezeigt oder in der Protokolldatei erfasst wird.</span><span class="sxs-lookup"><span data-stu-id="3ba13-141">By ignoring the error, you simply allow processing to continue without adding to the error count or logging it to the screen or log file.</span></span> <span data-ttu-id="3ba13-142">Der betreffende Datensatz weist ein Datenintegritätsproblem auf und kann der Datenbank nicht hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="3ba13-142">The record in question has a data integrity problem and cannot be added to the database.</span></span> <span data-ttu-id="3ba13-143">Der Datensatz wird abhängig von der `KeyErrorAction`-Eigenschaft entweder verworfen oder dem unbekannten Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="3ba13-143">The record will either be discarded or aggregated to Unknown Member, as determined by the `KeyErrorAction` property.</span></span>  
  
-   <span data-ttu-id="3ba13-144">`ReportAndContinue` weist den Server an, den Fehler zu protokollieren, auf den Grenzwert für Schlüsselfehler anzurechnen und die Verarbeitung fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="3ba13-144">`ReportAndContinue` tells the server to log the error, count it towards the key error limit, and continue processing.</span></span> <span data-ttu-id="3ba13-145">Der für den Fehler verantwortliche Datensatz wird verworfen oder in das unbekannte Element konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3ba13-145">The record triggering the error is discarded or converted to Unknown Member.</span></span>  
  
-   <span data-ttu-id="3ba13-146">`ReportAndStop` weist den Server an, den Fehler zu protokollieren und die Verarbeitung unabhängig vom Grenzwert für Schlüsselfehler sofort zu beenden.</span><span class="sxs-lookup"><span data-stu-id="3ba13-146">`ReportAndStop` tells the server to log the error and stop processing immediately, regardless of the key error limit.</span></span> <span data-ttu-id="3ba13-147">Der für den Fehler verantwortliche Datensatz wird verworfen oder in das unbekannte Element konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3ba13-147">The record triggering the error is discarded or converted to Unknown Member.</span></span>  
  
 <span data-ttu-id="3ba13-148">**ErrorLog\ LogErrorTypes\KeyDuplicate**</span><span class="sxs-lookup"><span data-stu-id="3ba13-148">**ErrorLog\ LogErrorTypes\KeyDuplicate**</span></span>  
 <span data-ttu-id="3ba13-149">Gibt die Aktion an, die vom Server ausgeführt wird, wenn ein doppelter Schlüssel gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="3ba13-149">Specifies the action taken by the server when a duplicate key is found.</span></span> <span data-ttu-id="3ba13-150">Folgende Werte sind möglich: `IgnoreError` – die Verarbeitung wird fortgesetzt, als wäre der Fehler nicht aufgetreten; `ReportAndContinue` – der Fehler wird protokolliert und die Verarbeitung fortgesetzt; `ReportAndStop` – der Fehler wird protokolliert und die Verarbeitung sofort beendet, selbst wenn die Fehleranzahl unterhalb der Fehlergrenze liegt.</span><span class="sxs-lookup"><span data-stu-id="3ba13-150">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="3ba13-151">**ErrorLog\ LogErrorTypes\NullKeyConvertedToUnknown**</span><span class="sxs-lookup"><span data-stu-id="3ba13-151">**ErrorLog\ LogErrorTypes\NullKeyConvertedToUnknown**</span></span>  
 <span data-ttu-id="3ba13-152">Gibt die Aktion an, die vom Server ausgeführt wird, wenn ein NULL-Schlüssel in ein unbekanntes Element konvertiert wurde.</span><span class="sxs-lookup"><span data-stu-id="3ba13-152">Specifies the action taken by the server when a null key has been converted to Unknown Member.</span></span> <span data-ttu-id="3ba13-153">Folgende Werte sind möglich: `IgnoreError` – die Verarbeitung wird fortgesetzt, als wäre der Fehler nicht aufgetreten; `ReportAndContinue` – der Fehler wird protokolliert und die Verarbeitung fortgesetzt; `ReportAndStop` – der Fehler wird protokolliert und die Verarbeitung sofort beendet, selbst wenn die Fehleranzahl unterhalb der Fehlergrenze liegt.</span><span class="sxs-lookup"><span data-stu-id="3ba13-153">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="3ba13-154">**ErrorLog\ LogErrorTypes\NullKeyNotAllowed**</span><span class="sxs-lookup"><span data-stu-id="3ba13-154">**ErrorLog\ LogErrorTypes\NullKeyNotAllowed**</span></span>  
 <span data-ttu-id="3ba13-155">Gibt die Aktion an, die vom Server ausgeführt wird, wenn `NullProcessing` für ein Dimensionsattribut auf `Error` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="3ba13-155">Specifies the action taken by the server when `NullProcessing` is set to `Error` for a dimension attribute.</span></span> <span data-ttu-id="3ba13-156">Wenn für ein bestimmtes Attribut kein NULL-Wert zulässig ist, wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="3ba13-156">An error is generated when a null value is not allowed in a given attribute.</span></span> <span data-ttu-id="3ba13-157">Durch diese Fehlerkonfigurationseigenschaft wird der nächste Schritt initiiert, der darin besteht, den Fehler zu melden und die Verarbeitung fortzusetzen, bis die Fehlergrenze erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="3ba13-157">This error configuration property informs the next step, which is to report the error and continue processing until the error limit is reached.</span></span> <span data-ttu-id="3ba13-158">Folgende Werte sind möglich: `IgnoreError` – die Verarbeitung wird fortgesetzt, als wäre der Fehler nicht aufgetreten; `ReportAndContinue` – der Fehler wird protokolliert und die Verarbeitung fortgesetzt; `ReportAndStop` – der Fehler wird protokolliert und die Verarbeitung sofort beendet, selbst wenn die Fehleranzahl unterhalb der Fehlergrenze liegt.</span><span class="sxs-lookup"><span data-stu-id="3ba13-158">Valid values include `IgnoreError` to continue processing as if the error did not occur, `ReportAndContinue` to log the error and continue processing, and `ReportAndStop` to log the error and stop processing immediately, even if the error count is below the error limit.</span></span>  
  
 <span data-ttu-id="3ba13-159">**ErrorLog\ LogErrorTypes\CalculationError**</span><span class="sxs-lookup"><span data-stu-id="3ba13-159">**ErrorLog\ LogErrorTypes\CalculationError**</span></span>  
 <span data-ttu-id="3ba13-160">Diese Eigenschaft wird standardmäßig während des vom Server ausgeführten Verarbeitungsvorgangs verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ba13-160">A property used as a default during processing operation performed by the server.</span></span>  
  
 <span data-ttu-id="3ba13-161">**ErrorLog\IgnoreDataTruncation**</span><span class="sxs-lookup"><span data-stu-id="3ba13-161">**ErrorLog\IgnoreDataTruncation**</span></span>  
 <span data-ttu-id="3ba13-162">Diese Eigenschaft wird standardmäßig während des vom Server ausgeführten Verarbeitungsvorgangs verwendet.</span><span class="sxs-lookup"><span data-stu-id="3ba13-162">A property used as a default during processing operation performed by the server.</span></span>  
  
## <a name="exception"></a><span data-ttu-id="3ba13-163">Ausnahme</span><span class="sxs-lookup"><span data-stu-id="3ba13-163">Exception</span></span>  
 <span data-ttu-id="3ba13-164">**Exception\CreateAndSendCrashReports**</span><span class="sxs-lookup"><span data-stu-id="3ba13-164">**Exception\CreateAndSendCrashReports**</span></span>  
 <span data-ttu-id="3ba13-165">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-165">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-166">**Exception\CrashReportsFolder**</span><span class="sxs-lookup"><span data-stu-id="3ba13-166">**Exception\CrashReportsFolder**</span></span>  
 <span data-ttu-id="3ba13-167">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-167">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-168">**Exception\SQLDumperFlagsOn**</span><span class="sxs-lookup"><span data-stu-id="3ba13-168">**Exception\SQLDumperFlagsOn**</span></span>  
 <span data-ttu-id="3ba13-169">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-169">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-170">**Exception\SQLDumperFlagsOff**</span><span class="sxs-lookup"><span data-stu-id="3ba13-170">**Exception\SQLDumperFlagsOff**</span></span>  
 <span data-ttu-id="3ba13-171">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-171">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-172">**Exception\MiniDumpFlagsOn**</span><span class="sxs-lookup"><span data-stu-id="3ba13-172">**Exception\MiniDumpFlagsOn**</span></span>  
 <span data-ttu-id="3ba13-173">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-173">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-174">**Exception\MinidumpErrorList**</span><span class="sxs-lookup"><span data-stu-id="3ba13-174">**Exception\MinidumpErrorList**</span></span>  
 <span data-ttu-id="3ba13-175">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-175">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="flight-recorder"></a><span data-ttu-id="3ba13-176">Flight Recorder</span><span class="sxs-lookup"><span data-stu-id="3ba13-176">Flight Recorder</span></span>  
 <span data-ttu-id="3ba13-177">**FlightRecorder\Enabled**</span><span class="sxs-lookup"><span data-stu-id="3ba13-177">**FlightRecorder\Enabled**</span></span>  
 <span data-ttu-id="3ba13-178">Eine boolesche Eigenschaft, die anzeigt, ob deie Funktion Flight Recorder aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="3ba13-178">A Boolean property that indicates whether the flight recorder feature is enabled.</span></span>  
  
 <span data-ttu-id="3ba13-179">**FlightRecorder\FileSizeMB**</span><span class="sxs-lookup"><span data-stu-id="3ba13-179">**FlightRecorder\FileSizeMB**</span></span>  
 <span data-ttu-id="3ba13-180">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die Größe der auf dem Datenträger gespeicherten Flight Recorder-Datei in MB definiert.</span><span class="sxs-lookup"><span data-stu-id="3ba13-180">A signed 32-bit integer property that defines the size of the flight recorder disk file, in megabytes.</span></span>  
  
 <span data-ttu-id="3ba13-181">**FlightRecorder\LogDurationSec**</span><span class="sxs-lookup"><span data-stu-id="3ba13-181">**FlightRecorder\LogDurationSec**</span></span>  
 <span data-ttu-id="3ba13-182">Eine ganze 32-Bit-Zahl mit Vorzeichen, die definiert, wie oft der Flight Recorder von neuem beginnt (in Sekunden).</span><span class="sxs-lookup"><span data-stu-id="3ba13-182">A signed 32-bit integer property that defines the frequency that the flight recorder is rolled over, in seconds.</span></span>  
  
 <span data-ttu-id="3ba13-183">**FlightRecorder\SnapshotDefinitionFile**</span><span class="sxs-lookup"><span data-stu-id="3ba13-183">**FlightRecorder\SnapshotDefinitionFile**</span></span>  
 <span data-ttu-id="3ba13-184">Eine aus einer Zeichenfolge bestehende Eigenschaft, die den Namen der Momentaufnahmedefinitionsdatei definiert. Diese Datei enthält Ermittlungsbefehle, die beim Erstellen einer Momentaufnahme an den Server ausgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="3ba13-184">A string property that defines the name of the snapshot definition file, containing discover commands that are issued to the server when a snapshot is taken.</span></span>  
  
 <span data-ttu-id="3ba13-185">Der Standardwert für diese Eigenschaft ist leer. Dies bedeutet, dass standardmäßig der Dateiname FlightRecorderSnapshotDef.xml verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3ba13-185">The default value for this property is blank, which in turn defaults to file name FlightRecorderSnapshotDef.xml.</span></span>  
  
 <span data-ttu-id="3ba13-186">**FlightRecorder\SnapshotFrequencySec**</span><span class="sxs-lookup"><span data-stu-id="3ba13-186">**FlightRecorder\SnapshotFrequencySec**</span></span>  
 <span data-ttu-id="3ba13-187">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die Momentaufnahmehäufigkeit in Sekunden angibt.</span><span class="sxs-lookup"><span data-stu-id="3ba13-187">A signed 32-bit integer property that defines the snapshot frequency, in seconds.</span></span>  
  
 <span data-ttu-id="3ba13-188">**FlightRecorder\TraceDefinitionFile**</span><span class="sxs-lookup"><span data-stu-id="3ba13-188">**FlightRecorder\TraceDefinitionFile**</span></span>  
 <span data-ttu-id="3ba13-189">Eine aus einer Zeichenfolge bestehende Eigenschaft, die den Namen der Ablaufverfolgungs-Definitionsdatei für den Flight Recorder angibt.</span><span class="sxs-lookup"><span data-stu-id="3ba13-189">A string property that specifies the name of the flight recorder trace definition file.</span></span>  
  
 <span data-ttu-id="3ba13-190">Der Standardwert für diese Eigenschaft ist leer. Dies bedeutet, dass standardmäßig die Datei FlightRecorderTraceDef.xml verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3ba13-190">The default value for this property is blank, which in turn defaults to FlightRecorderTraceDef.xml.</span></span>  
  
## <a name="query-log"></a><span data-ttu-id="3ba13-191">Abfrageprotokoll</span><span class="sxs-lookup"><span data-stu-id="3ba13-191">Query Log</span></span>  
 <span data-ttu-id="3ba13-192">**Gilt für:** Nur mehrdimensionaler Server Modus</span><span class="sxs-lookup"><span data-stu-id="3ba13-192">**Applies to:** Multidimensional server mode only</span></span>  
  
 <span data-ttu-id="3ba13-193">**QueryLog\QueryLogFileName**</span><span class="sxs-lookup"><span data-stu-id="3ba13-193">**QueryLog\QueryLogFileName**</span></span>  
 <span data-ttu-id="3ba13-194">Eine Zeichenfolge, die den Namen der Abfrageprotokolldatei angibt.</span><span class="sxs-lookup"><span data-stu-id="3ba13-194">A string property that specifies the name of the query log file.</span></span> <span data-ttu-id="3ba13-195">Diese Eigenschaft gilt nur, wenn für die Protokollierung eine Datei auf dem Datenträger anstelle einer Datenbanktabelle (das Standardverhalten) verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="3ba13-195">This property only applies when a disk file is used for logging, as opposed to a database table (the default behavior).</span></span>  
  
 <span data-ttu-id="3ba13-196">**QueryLog\QueryLogSampling**</span><span class="sxs-lookup"><span data-stu-id="3ba13-196">**QueryLog\QueryLogSampling**</span></span>  
 <span data-ttu-id="3ba13-197">Eine ganze 32-Bit-Zahl mit Vorzeichen, die die Stichprobenrate des Abfrageprotokolls angibt.</span><span class="sxs-lookup"><span data-stu-id="3ba13-197">A signed 32-bit integer property that specifies the query log sampling rate.</span></span>  
  
 <span data-ttu-id="3ba13-198">Der Standardwert für diese Eigenschaft ist 10. Dies bedeutet, dass eine von 10 Serverabfragen protokolliert wird.</span><span class="sxs-lookup"><span data-stu-id="3ba13-198">The default value for this property is 10, meaning that 1 out of every 10 server queries is logged.</span></span>  
  
 <span data-ttu-id="3ba13-199">**QueryLog\QueryLogFileSize**</span><span class="sxs-lookup"><span data-stu-id="3ba13-199">**QueryLog\QueryLogFileSize**</span></span>  
 <span data-ttu-id="3ba13-200">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-200">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-201">**QueryLog\QueryLogConnectionString**</span><span class="sxs-lookup"><span data-stu-id="3ba13-201">**QueryLog\QueryLogConnectionString**</span></span>  
 <span data-ttu-id="3ba13-202">Eine Zeichenfolge, die die Verbindung mit der Abfrageprotokolldatenbank angibt.</span><span class="sxs-lookup"><span data-stu-id="3ba13-202">A string property that specifies the connection to the query log database.</span></span>  
  
 <span data-ttu-id="3ba13-203">**QueryLog\QueryLogTableName**</span><span class="sxs-lookup"><span data-stu-id="3ba13-203">**QueryLog\QueryLogTableName**</span></span>  
 <span data-ttu-id="3ba13-204">Eine Zeichenfolge, die den Namen der Abfrageprotokolltabelle angibt.</span><span class="sxs-lookup"><span data-stu-id="3ba13-204">A string property that specifies the name of the query log table.</span></span>  
  
 <span data-ttu-id="3ba13-205">Der Standardwert für diese Eigenschaft ist OlapQueryLog.</span><span class="sxs-lookup"><span data-stu-id="3ba13-205">The default value for this property is OlapQueryLog.</span></span>  
  
 <span data-ttu-id="3ba13-206">**QueryLog\CreateQueryLogTable**</span><span class="sxs-lookup"><span data-stu-id="3ba13-206">**QueryLog\CreateQueryLogTable**</span></span>  
 <span data-ttu-id="3ba13-207">Eine boolesche Eigenschaft, die angibt, ob die Abfrageprotokolltabelle erstellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ba13-207">A Boolean property that specifies whether to create the query log table.</span></span>  
  
 <span data-ttu-id="3ba13-208">Der Standardwert für diese Eigenschaft ist FALSE. Dies bedeutet, dass der Server nicht automatisch die Protokolltabelle erstellt und keine Abfrageereignisse protokolliert.</span><span class="sxs-lookup"><span data-stu-id="3ba13-208">The default value for this property is false, which indicates the server will not automatically create the log table and will not log query events.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3ba13-209">Weitere Informationen zum Konfigurieren des Abfrage Protokolls finden Sie unter [Protokoll Vorgänge in Analysis Services](../instances/log-operations-in-analysis-services.md).</span><span class="sxs-lookup"><span data-stu-id="3ba13-209">For more information about configuring the query log, see [Log operations in Analysis Services](../instances/log-operations-in-analysis-services.md).</span></span>  
  
## <a name="trace"></a><span data-ttu-id="3ba13-210">Ablaufverfolgung</span><span class="sxs-lookup"><span data-stu-id="3ba13-210">Trace</span></span>  
 <span data-ttu-id="3ba13-211">**Trace\TraceBackgroundDistributionPeriod**</span><span class="sxs-lookup"><span data-stu-id="3ba13-211">**Trace\TraceBackgroundDistributionPeriod**</span></span>  
 <span data-ttu-id="3ba13-212">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-212">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-213">**Trace\TraceBackgroundFlushPeriod**</span><span class="sxs-lookup"><span data-stu-id="3ba13-213">**Trace\TraceBackgroundFlushPeriod**</span></span>  
 <span data-ttu-id="3ba13-214">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-214">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-215">**Trace\TraceFileBufferSize**</span><span class="sxs-lookup"><span data-stu-id="3ba13-215">**Trace\TraceFileBufferSize**</span></span>  
 <span data-ttu-id="3ba13-216">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-216">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-217">**Trace\TraceFileWriteTrailerPeriod**</span><span class="sxs-lookup"><span data-stu-id="3ba13-217">**Trace\TraceFileWriteTrailerPeriod**</span></span>  
 <span data-ttu-id="3ba13-218">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-218">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-219">**Trace\TraceMaxRowsetSize**</span><span class="sxs-lookup"><span data-stu-id="3ba13-219">**Trace\TraceMaxRowsetSize**</span></span>  
 <span data-ttu-id="3ba13-220">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-220">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-221">**Trace\TraceProtocolTraffic**</span><span class="sxs-lookup"><span data-stu-id="3ba13-221">**Trace\TraceProtocolTraffic**</span></span>  
 <span data-ttu-id="3ba13-222">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-222">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-223">**Trace\TraceQueryResponseTextChunkSize**</span><span class="sxs-lookup"><span data-stu-id="3ba13-223">**Trace\TraceQueryResponseTextChunkSize**</span></span>  
 <span data-ttu-id="3ba13-224">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-224">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-225">**Trace\TraceReportFQDN**</span><span class="sxs-lookup"><span data-stu-id="3ba13-225">**Trace\TraceReportFQDN**</span></span>  
 <span data-ttu-id="3ba13-226">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-226">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-227">**Trace\TraceRequestParameters**</span><span class="sxs-lookup"><span data-stu-id="3ba13-227">**Trace\TraceRequestParameters**</span></span>  
 <span data-ttu-id="3ba13-228">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-228">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
 <span data-ttu-id="3ba13-229">**Trace\TraceRowsetBackgroundFlushPeriod**</span><span class="sxs-lookup"><span data-stu-id="3ba13-229">**Trace\TraceRowsetBackgroundFlushPeriod**</span></span>  
 <span data-ttu-id="3ba13-230">Eine erweiterte Eigenschaft, die nur mithilfe der Schritte in [!INCLUDE[msCoName](../../includes/msconame-md.md)] geändert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="3ba13-230">An advanced property that you should not change, except under the guidance of [!INCLUDE[msCoName](../../includes/msconame-md.md)] support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ba13-231">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3ba13-231">See Also</span></span>  
 <span data-ttu-id="3ba13-232">[Konfigurieren von Server Eigenschaften in Analysis Services](server-properties-in-analysis-services.md) </span><span class="sxs-lookup"><span data-stu-id="3ba13-232">[Configure Server Properties in Analysis Services](server-properties-in-analysis-services.md) </span></span>  
 [<span data-ttu-id="3ba13-233">Bestimmen des Servermodus einer Analysis Services-Instanz</span><span class="sxs-lookup"><span data-stu-id="3ba13-233">Determine the Server Mode of an Analysis Services Instance</span></span>](../instances/determine-the-server-mode-of-an-analysis-services-instance.md)  
  
  
