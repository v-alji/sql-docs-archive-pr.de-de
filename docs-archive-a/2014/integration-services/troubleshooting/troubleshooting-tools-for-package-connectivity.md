---
title: Problembehandlung bei Tools Paket Konnektivität | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- SQL Server Integration Services packages, troubleshooting
- SSIS packages, troubleshooting
- Integration Services, troubleshooting
- connectivity [Integration Services], troubleshooting
- errors [Integration Services], troubleshooting
- packages [Integration Services], troubleshooting
ms.assetid: 08a019f5-8ba7-4527-97c1-e9846d4022ff
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1baac9af5a30fdc0f5b15e8ac56eb5badacc0edb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87699999"
---
# <a name="troubleshooting-tools-package-connectivity"></a><span data-ttu-id="b0a98-102">Tools zur Behandlung von Problemen mit Paketverbindungen</span><span class="sxs-lookup"><span data-stu-id="b0a98-102">Troubleshooting Tools Package Connectivity</span></span>
  [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] <span data-ttu-id="b0a98-103">enthält Funktionen und Tools, mit denen Sie Verbindungsprobleme zwischen Paketen und den Datenquellen behandeln können, aus denen Daten von Paketen extrahiert und geladen werden.</span><span class="sxs-lookup"><span data-stu-id="b0a98-103">includes features and tools that you can use to troubleshoot connectivity between packages and the data sources from which packages extract and load data.</span></span>  
  
## <a name="troubleshooting-issues-with-external-data-providers"></a><span data-ttu-id="b0a98-104">Behandlung von Problemen mit externen Datenanbietern</span><span class="sxs-lookup"><span data-stu-id="b0a98-104">Troubleshooting Issues with External Data Providers</span></span>  
 <span data-ttu-id="b0a98-105">Viele Paketfehler treten während Interaktionen mit externen Datenanbietern auf.</span><span class="sxs-lookup"><span data-stu-id="b0a98-105">Many packages fail during interactions with external data providers.</span></span> <span data-ttu-id="b0a98-106">Die von diesen Anbietern an [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] zurückgegebenen Meldungen bieten jedoch häufig nicht genug Informationen, um mit der Problembehandlung der Interaktion zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="b0a98-106">However, the messages that those providers return to [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] frequently do not provide enough information to start troubleshooting the interaction.</span></span> <span data-ttu-id="b0a98-107">Damit die Problembehandlung vorgenommen werden kann, enthält [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] neue Meldungen für die Protokollierung, die Sie zur Problembehandlung der Interaktion eines Pakets mit externen Datenquellen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="b0a98-107">To address this troubleshooting need, [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] includes logging messages that you can use to troubleshoot a package's interaction with external data sources.</span></span>  
  
-   <span data-ttu-id="b0a98-108">**Aktivieren Sie die Protokollierung, und wählen Sie das Diagnostic-Ereignis des Pakets aus, um die Meldungen zur Problembehandlung anzuzeigen**.</span><span class="sxs-lookup"><span data-stu-id="b0a98-108">**Enable logging and select the package's Diagnostic event to see the troubleshooting messages**.</span></span> <span data-ttu-id="b0a98-109">Mit den folgenden Komponenten von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] kann vor und nach jedem Aufruf an einen externen Datenanbieter eine Meldung in das Protokoll geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="b0a98-109">The following [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] components are capable of writing a message to the log before and after every call to an external data provider:</span></span>  
  
    -   <span data-ttu-id="b0a98-110">OLE DB-Verwaltungs-Manager, OLE DB-Quelle und OLE DB-Ziel</span><span class="sxs-lookup"><span data-stu-id="b0a98-110">OLE DB connection manager, OLE DB source, and OLE DB destination</span></span>  
  
    -   [!INCLUDE[vstecado](../../includes/vstecado-md.md)]<span data-ttu-id="b0a98-111">-Verbindungs-Manager und ADO.NET-Quelle</span><span class="sxs-lookup"><span data-stu-id="b0a98-111">connection manager and ADO NET source</span></span>  
  
    -   <span data-ttu-id="b0a98-112">Task SQL ausführen</span><span class="sxs-lookup"><span data-stu-id="b0a98-112">Execute SQL task</span></span>  
  
    -   <span data-ttu-id="b0a98-113">Transformation für Suche, Transformation für OLE DB-Befehl und Transformation für langsam veränderliche Dimensionen</span><span class="sxs-lookup"><span data-stu-id="b0a98-113">Lookup transformation, OLE DB Command transformation, and Slowly Changing Dimension transformation</span></span>  
  
     <span data-ttu-id="b0a98-114">Die Protokollmeldungen enthalten den Namen der aufgerufenen Methode.</span><span class="sxs-lookup"><span data-stu-id="b0a98-114">The log messages include the name of the method being called.</span></span> <span data-ttu-id="b0a98-115">Diese Protokollmeldungen können beispielsweise die `Open`-Methode eines `Connection`-Objekts von OLE DB oder die `ExecuteNonQuery`-Methode eines `Command`-Objekts enthalten.</span><span class="sxs-lookup"><span data-stu-id="b0a98-115">For example, these log messages might include the `Open` method of an OLE DB `Connection` object or the `ExecuteNonQuery` method of a `Command` object.</span></span> <span data-ttu-id="b0a98-116">Die Nachrichten haben das folgende Format, wobei „%1! s!“</span><span class="sxs-lookup"><span data-stu-id="b0a98-116">The messages have the following format, where '%1!s!'</span></span> <span data-ttu-id="b0a98-117">ein Platzhalter für die Methodeninformationen ist:</span><span class="sxs-lookup"><span data-stu-id="b0a98-117">is a placeholder for the method information:</span></span>  
  
    ```  
    ExternalRequest_pre: The object is ready to make the following external request: '%1!s!'.  
    ExternalRequest_post: '%1!s!'. The external request has completed.  
    ```  
  
     <span data-ttu-id="b0a98-118">Überprüfen Sie zur Problembehandlung der Interaktion mit dem externen Datenanbieter, ob für jede „Vorher“-Meldung (`ExternalRequest_pre`) eine entsprechende „Nachher“-Meldung (`ExternalRequest_post`) vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b0a98-118">To troubleshoot the interaction with the external data provider, review the log to see whether every "before" message (`ExternalRequest_pre`) has a corresponding "after" message (`ExternalRequest_post`).</span></span> <span data-ttu-id="b0a98-119">Wenn keine entsprechende "Nachher"-Meldung vorhanden ist, hat der externe Datenanbieter nicht wie erwartet reagiert.</span><span class="sxs-lookup"><span data-stu-id="b0a98-119">If there is no corresponding "after" message, you know that the external data provider did not respond as expected.</span></span>  
  
     <span data-ttu-id="b0a98-120">Im folgenden Beispiel sind einige Beispielzeilen aus einem Protokoll dargestellt, in dem diese Meldungen für die Protokollierung enthalten sind:</span><span class="sxs-lookup"><span data-stu-id="b0a98-120">The following example shows some sample rows from a log that contains these logging messages:</span></span>  
  
    ```  
    ExternalRequest_pre: The object is ready to make the following external request: 'ITransactionJoin::JoinTransaction'.  
    ExternalRequest_post: 'ITransactionJoin::JoinTransaction succeeded'. The external request has completed.  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.Open'.  
    ExternalRequest_post: 'IDbConnection.Open succeeded'. The external request has completed.  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.CreateCommand'.  
    ExternalRequest_post: 'IDbConnection.CreateCommand finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbCommand.ExecuteReader'.  
    ExternalRequest_post: 'IDbCommand.ExecuteReader finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDataReader.GetSchemaTable'.  
    ExternalRequest_post: 'IDataReader.GetSchemaTable finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDataReader.Close'.  
    ExternalRequest_post: 'IDataReader.Close finished'. The external request has completed."  
    ExternalRequest_pre: The object is ready to make the following external request: 'IDbConnection.Close'.  
    ExternalRequest_post: 'IDbConnection.Close finished'. The external request has completed."  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b0a98-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b0a98-121">See Also</span></span>  
 <span data-ttu-id="b0a98-122">[Tools zur Problembehandlung für die Paketentwicklung](troubleshooting-tools-for-package-development.md) </span><span class="sxs-lookup"><span data-stu-id="b0a98-122">[Troubleshooting Tools for Package Development](troubleshooting-tools-for-package-development.md) </span></span>  
 [<span data-ttu-id="b0a98-123">Behandlung von Problemen mit Paketausführungstools</span><span class="sxs-lookup"><span data-stu-id="b0a98-123">Troubleshooting Tools for Package Execution</span></span>](troubleshooting-tools-for-package-execution.md)  
  
  
