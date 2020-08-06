---
title: ssbdiagnose-Hilfsprogramm (Service Broker) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: tools-other
ms.topic: conceptual
helpviewer_keywords:
- Service Broker, runtime reports
- Service Broker, command prompt utilities
- troubleshooting [Service Broker], conversations
- troubleshooting [Service Broker], configurations
- command prompt utilities [Service Broker]
- Service Broker, troubleshooting
- Service Broker, configuration reports
- Service Broker, tools
- troubleshooting [Service Broker], runtime
- conversations [Service Broker], troubleshooting
- troubleshooting [Service Broker], ssbdiagnose utility
- tools [Service Broker], ssbdiagnose
- Service Broker, ssbdiagnose utility
- ssbdiagnose
ms.assetid: 0c1636e8-a3db-438e-be4c-1ea40d1f4877
author: stevestein
ms.author: sstein
ms.openlocfilehash: 8efc581eebd7d8fa7fa265abb54168af78b57ca2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87720608"
---
# <a name="ssbdiagnose-utility-service-broker"></a><span data-ttu-id="2b23f-102">ssbdiagnose-Hilfsprogramm (Service Broker)</span><span class="sxs-lookup"><span data-stu-id="2b23f-102">ssbdiagnose Utility (Service Broker)</span></span>
  <span data-ttu-id="2b23f-103">Das Hilfsprogramm **ssbdiagnose** meldet Probleme in [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Konversationen oder der Konfiguration von [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Diensten.</span><span class="sxs-lookup"><span data-stu-id="2b23f-103">The **ssbdiagnose** utility reports issues in [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversations or the configuration of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services.</span></span> <span data-ttu-id="2b23f-104">Konfigurationsüberprüfungen können entweder für zwei Dienste oder für einen einzelnen Dienst ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-104">Configuration checks can be made for either two services or a single service.</span></span> <span data-ttu-id="2b23f-105">Probleme werden entweder im Eingabeaufforderungsfenster als für den Benutzer lesbarer Text oder als formatierte XML, die in eine Datei oder ein anderes Programm umgeleitet werden kann, gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-105">Issues are reported either in the command prompt window as human-readable text, or as formatted XML that can be redirected to a file or another program.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b23f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="2b23f-106">Syntax</span></span>  
  
```  
  
      ssbdiagnose   
[ [ -XML ]  
    [ -LEVEL { ERROR | WARNING | INFO } ]  
  [-IGNOREerror_id ] [ ...n]  
    [ <baseconnectionoptions> ]  
  { <configurationreport> | <runtimereport> }  
]  
| -?  
  
<configurationreport> ::=  
    CONFIGURATION  
  { [ FROM SERVICEservice_name  
      [ <fromconnectionoptions> ]  
      [ MIRROR <mirrorconnectionoptions> ]  
    ]  
    [ TO SERVICEservice_name[, broker_id ]  
      [ <toconnectionoptions> ]  
      [ MIRROR <mirrorconnectionoptions> ]  
    ]  
  }  
    ON CONTRACTcontract_name  
  [ ENCRYPTION { ON | OFF | ANONYMOUS } ]  
  
<runtime_report> ::=  
    RUNTIME  
    [-SHOWEVENTS ]  
        [ -NEW  
         [ -ID { conversation_handle  
                | conversation_group_id  
                 | conversation_id  
                  }  
        ] [ ...n]  
        ]  
    [ -TIMEOUTtimeout_interval ]  
    [ <runtimeconnectionoptions> ]  
  
<baseconnectionoptions> ::=  
  <connectionoptions>  
  
<fromconnectionoptions> ::=  
  <connectionoptions>  
  
<toconnectionoptions> ::=  
  <connectionoptions>  
  
<mirrorconnectionoptions> ::=  
  <connectionoptions>  
  
<runtimeconnectionoptions> ::=  
  [ CONNECT TO <connectionoptions> ] [ ...n]  
  
<connectionoptions> ::=  
    [ -E | { -Ulogin_id [ -Ppassword ] } ]  
  [ -Sserver_name[\instance_name] ]  
  [ -ddatabase_name ]  
  [ -llogin_timeout ]  
  
```  
  
## <a name="command-line-options"></a><span data-ttu-id="2b23f-107">Befehlszeilenoptionen</span><span class="sxs-lookup"><span data-stu-id="2b23f-107">Command Line Options</span></span>  
 <span data-ttu-id="2b23f-108">**-XML**</span><span class="sxs-lookup"><span data-stu-id="2b23f-108">**-XML**</span></span>  
 <span data-ttu-id="2b23f-109">Gibt an, dass die Ausgabe von **ssbdiagnose** als formatierte XML generiert wird.</span><span class="sxs-lookup"><span data-stu-id="2b23f-109">Specifies that the **ssbdiagnose** output be generated as formatted XML.</span></span> <span data-ttu-id="2b23f-110">Dieses kann in eine Datei oder in eine andere Anwendung umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-110">This can be redirected to a file or to another application.</span></span> <span data-ttu-id="2b23f-111">Wenn **-XML** nicht angegeben ist, wird die Ausgabe von **ssbdiagnose** als für den Benutzer lesbarer Text formatiert.</span><span class="sxs-lookup"><span data-stu-id="2b23f-111">If **-XML** is not specified, the **ssbdiagnose** output is formatted as human-readable text.</span></span>  
  
 <span data-ttu-id="2b23f-112">**-LEVEL** { **ERROR** | **WARNING** | **INFO**}</span><span class="sxs-lookup"><span data-stu-id="2b23f-112">**-LEVEL** { **ERROR** | **WARNING** | **INFO**}</span></span>  
 <span data-ttu-id="2b23f-113">Gibt die Ebene der Meldungen an, die gemeldet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-113">Specifies the level of messages to report.</span></span>  
  
 <span data-ttu-id="2b23f-114">**ERROR**: Nur Fehler werden gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-114">**ERROR**: report only error messages.</span></span>  
  
 <span data-ttu-id="2b23f-115">**WARNING**: Fehler und Warnungen werden gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-115">**WARNING**: report error and warning messages.</span></span>  
  
 <span data-ttu-id="2b23f-116">**INFO**: Fehler, Warnungen und Informationsmeldungen werden gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-116">**INFO**: report error, warning, and informational messages.</span></span>  
  
 <span data-ttu-id="2b23f-117">Die Standardeinstellung ist **WARNING**.</span><span class="sxs-lookup"><span data-stu-id="2b23f-117">The default setting is **WARNING**.</span></span>  
  
 <span data-ttu-id="2b23f-118">**-IGNORE** *error_id*</span><span class="sxs-lookup"><span data-stu-id="2b23f-118">**-IGNORE** *error_id*</span></span>  
 <span data-ttu-id="2b23f-119">Gibt an, dass Fehler oder Meldungen mit der angegebenen *Fehler-ID* in Berichten nicht eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-119">Specifies that errors or messages that have the specified *error_id* not be included in reports.</span></span> <span data-ttu-id="2b23f-120">Sie können **-IGNORE** mehrmals angeben, um mehrere Meldungs-IDs zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="2b23f-120">You can specify **-IGNORE** multiple times to suppress multiple message IDs.</span></span>  
  
 **\<baseconnectionoptions>**  
 <span data-ttu-id="2b23f-121">Gibt die grundlegenden Verbindungsinformationen an, die von **ssbdiagnose** verwendet werden, wenn eine bestimmte Klausel keine Verbindungsoptionen enthält.</span><span class="sxs-lookup"><span data-stu-id="2b23f-121">Specifies the base connection information that is used by **ssbdiagnose** when connection options are not included in a specific clause.</span></span> <span data-ttu-id="2b23f-122">Die in einer bestimmten Klausel angegebenen Verbindungsinformationen überschreiben die Informationen von **baseconnectionoption** .</span><span class="sxs-lookup"><span data-stu-id="2b23f-122">The connection information that is given in a specific clause overrides the **baseconnectionoption** information.</span></span> <span data-ttu-id="2b23f-123">Dieser Vorgang wird für jeden Parameter separat ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2b23f-123">This is performed separately for each parameter.</span></span> <span data-ttu-id="2b23f-124">Beispiel: Wenn sowohl **-S** als auch **-d** in **baseconnectionoptions**angegeben sind und nur **-d** in **toconnectionoptions**angegeben ist, verwendet **ssbdiagnose** „-S“ aus **baseconnectionoptions** und „-d“ aus **toconnectionoptions**.</span><span class="sxs-lookup"><span data-stu-id="2b23f-124">For example, if both **-S** and **-d** are specified in **baseconnetionoptions**, and only **-d** is specified in **toconnetionoptions**, **ssbdiagnose** uses -S from **baseconnetionoptions** and -d from **toconnetionoptions**.</span></span>  
  
 <span data-ttu-id="2b23f-125">**CONFIGURATION**</span><span class="sxs-lookup"><span data-stu-id="2b23f-125">**CONFIGURATION**</span></span>  
 <span data-ttu-id="2b23f-126">Fordert einen Bericht über Konfigurationsfehler für ein Paar von [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Diensten oder für einen einzelnen Dienst an.</span><span class="sxs-lookup"><span data-stu-id="2b23f-126">Requests a report of configuration errors between a pair of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services, or for a single service.</span></span>  
  
 <span data-ttu-id="2b23f-127">**FROM SERVICE** *service_name*</span><span class="sxs-lookup"><span data-stu-id="2b23f-127">**FROM SERVICE** *service_name*</span></span>  
 <span data-ttu-id="2b23f-128">Gibt den Dienst an, der Konversationen initiiert.</span><span class="sxs-lookup"><span data-stu-id="2b23f-128">Specifies the service that initiates conversations.</span></span>  
  
 **\<fromconnectionoptions>**  
 <span data-ttu-id="2b23f-129">Gibt die Informationen an, die erforderlich sind, um eine Verbindung mit der Datenbank herzustellen, die den Initiatordienst enthält.</span><span class="sxs-lookup"><span data-stu-id="2b23f-129">Specifies the information that is required to connect to the database that holds the initiator service.</span></span> <span data-ttu-id="2b23f-130">Wenn **fromconnectionoptions** nicht angegeben ist, verwendet **ssbdiagnose** die Verbindungsinformationen aus **baseconnectionoptions** , um eine Verbindung mit der Initiatordatenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-130">If **fromconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the initiator database.</span></span> <span data-ttu-id="2b23f-131">Wenn **fromconnectionoptions** angegeben ist, muss darin die Datenbank angegeben sein, die den Initiatordienst enthält.</span><span class="sxs-lookup"><span data-stu-id="2b23f-131">If **fromconnectionoptions** is specified it must include the database that contains the initiator service.</span></span> <span data-ttu-id="2b23f-132">Wenn **fromconnectionoptions** nicht angegeben wird, muss **baseconnectionoptions** die Initiatordatenbank angeben.</span><span class="sxs-lookup"><span data-stu-id="2b23f-132">If **fromconnectionoptions** is not specified, the **baseconnectionoptions** must specify the initiator database.</span></span>  
  
 <span data-ttu-id="2b23f-133">**TO SERVICE** *service_name*[, *broker_id* ]</span><span class="sxs-lookup"><span data-stu-id="2b23f-133">**TO SERVICE** *service_name*[, *broker_id* ]</span></span>  
 <span data-ttu-id="2b23f-134">Gibt den Dienst an, der das Ziel für die Konversationen darstellt.</span><span class="sxs-lookup"><span data-stu-id="2b23f-134">Specifies the service that is the target for the conversations.</span></span>  
  
 <span data-ttu-id="2b23f-135">*Dienstname*: Gibt den Namen des Zieldiensts an.</span><span class="sxs-lookup"><span data-stu-id="2b23f-135">*service_name*: specifies the name of the target service.</span></span>  
  
 <span data-ttu-id="2b23f-136">*Broker-ID*: Gibt die [!INCLUDE[ssSB](../../includes/sssb-md.md)] -ID für die Zieldatenbank an.</span><span class="sxs-lookup"><span data-stu-id="2b23f-136">*broker_id*: specifies the [!INCLUDE[ssSB](../../includes/sssb-md.md)] ID that identifies the target database.</span></span> <span data-ttu-id="2b23f-137">Die*Broker-ID* ist eine GUID.</span><span class="sxs-lookup"><span data-stu-id="2b23f-137">*broker_id* is a GUID.</span></span> <span data-ttu-id="2b23f-138">Sie können die folgende Abfrage in der Zieldatenbank ausführen, um diese zu finden:</span><span class="sxs-lookup"><span data-stu-id="2b23f-138">You can run the following query in the target database to find it:</span></span>  
  
```  
SELECT service_broker_guid  
FROM sys.databases  
WHERE database_id = DB_ID();  
```  
  
 **\<toconnectionoptions>**  
 <span data-ttu-id="2b23f-139">Gibt die Informationen an, die erforderlich sind, um eine Verbindung mit der Datenbank herzustellen, die den Zieldienst enthält.</span><span class="sxs-lookup"><span data-stu-id="2b23f-139">Specifies the information that is required to connect the database that holds the target service.</span></span> <span data-ttu-id="2b23f-140">Wenn **toconnectionoptions** nicht angegeben ist, verwendet **ssbdiagnose** die Verbindungsinformationen aus **baseconnectionoptions** , um eine Verbindung mit der Zieldatenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-140">If **toconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the target database.</span></span>  
  
 <span data-ttu-id="2b23f-141">**MIRROR**</span><span class="sxs-lookup"><span data-stu-id="2b23f-141">**MIRROR**</span></span>  
 <span data-ttu-id="2b23f-142">Gibt an, dass der dazugehörige [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Dienst in einer gespiegelten Datenbank gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="2b23f-142">Specifies that the associated [!INCLUDE[ssSB](../../includes/sssb-md.md)] service is hosted in a mirrored database.</span></span> <span data-ttu-id="2b23f-143">**ssbdiagnose** überprüft, dass die Route zum Dienst eine gespiegelte Route ist, bei der MIRROR_ADDRESS für CREATE ROUTE angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="2b23f-143">**ssbdiagnose** verifies that the route to the service is a mirrored route, where MIRROR_ADDRESS was specified on CREATE ROUTE.</span></span>  
  
 **\<mirrorconnectionoptions>**  
 <span data-ttu-id="2b23f-144">Gibt die Informationen an, die erforderlich sind, um eine Verbindung mit der Spiegeldatenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-144">Specifies the information that is required to connect to the mirror database.</span></span> <span data-ttu-id="2b23f-145">Wenn **mirrorconnectionoptions** nicht angegeben ist, verwendet **ssbdiagnose** die Verbindungsinformationen aus **baseconnectionoptions** , um eine Verbindung mit der Spiegeldatenbank herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-145">If **mirrorconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions** to connect to the mirror database.</span></span>  
  
 <span data-ttu-id="2b23f-146">**ON CONTRACT** *contract_name*</span><span class="sxs-lookup"><span data-stu-id="2b23f-146">**ON CONTRACT** *contract_name*</span></span>  
 <span data-ttu-id="2b23f-147">Fordert an, dass **ssbdiagnose** nur Konfigurationen überprüft, die den angegebenen Vertrag verwenden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-147">Requests that **ssbdiagnose** only check configurations that use the specified contract.</span></span> <span data-ttu-id="2b23f-148">Wenn ON CONTRACT nicht angegeben ist, berichtet **ssbdiagnose** über den Vertrag mit dem Namen DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="2b23f-148">If ON CONTRACT is not specified, **ssbdiagnose** reports on the contract named DEFAULT.</span></span>  
  
 <span data-ttu-id="2b23f-149">**ENCRYPTION** { **ON** | **OFF** | **ANONYMOUS** }</span><span class="sxs-lookup"><span data-stu-id="2b23f-149">**ENCRYPTION** { **ON** | **OFF** | **ANONYMOUS** }</span></span>  
 <span data-ttu-id="2b23f-150">Fordert an, dass überprüft wird, ob der Dialog für die angegebene Ebene der Verschlüsselung ordnungsgemäß konfiguriert ist:</span><span class="sxs-lookup"><span data-stu-id="2b23f-150">Requests verification that the dialog is correctly configured for the specified level of encryption:</span></span>  
  
 <span data-ttu-id="2b23f-151">**ON**: Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="2b23f-151">**ON**: Default setting.</span></span> <span data-ttu-id="2b23f-152">Vollständige Dialogsicherheit wird konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2b23f-152">Full dialog security is configured.</span></span> <span data-ttu-id="2b23f-153">Auf beiden Seiten des Dialogs wurden Zertifikate bereitgestellt, eine Remotedienstbindung ist vorhanden, und in der GRANT SEND-Anweisung für den Zieldienst wurde der Initiatorbenutzer angegeben.</span><span class="sxs-lookup"><span data-stu-id="2b23f-153">Certificates have been deployed on both sides of the dialog, a remote service binding is present, and the GRANT SEND statement for the target service specified the initiator user.</span></span>  
  
 <span data-ttu-id="2b23f-154">**OFF**: Es wird keine Dialogsicherheit konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2b23f-154">**OFF**: No dialog security is configured.</span></span> <span data-ttu-id="2b23f-155">Es wurden keine Zertifikate bereitgestellt, keine Remotedienstbindung erstellt, und in der GRANT SEND-Anweisung für den Initiatordienst wurde die **public** -Rolle angegeben.</span><span class="sxs-lookup"><span data-stu-id="2b23f-155">No certificates have been deployed, no remote service binding was created, and the GRANT SEND for the initiator service specified the **public** role.</span></span>  
  
 <span data-ttu-id="2b23f-156">**ANONYMOUS**: Anonyme Dialogsicherheit wird konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="2b23f-156">**ANONYMOUS**: Anonymous dialog security is configured.</span></span> <span data-ttu-id="2b23f-157">Ein Zertifikat wurde bereitgestellt, die Remotedienstbindung wurde in der ANONYMOUS-Klausel angegeben, und in der GRANT SEND-Anweisung für den Zieldienst wurde die **public** -Rolle angegeben.</span><span class="sxs-lookup"><span data-stu-id="2b23f-157">One certificate has been deployed, the remote service binding specified the anonymous clause, and the GRANT SEND for the target service specified the **public** role.</span></span>  
  
 <span data-ttu-id="2b23f-158">**RUNTIME**</span><span class="sxs-lookup"><span data-stu-id="2b23f-158">**RUNTIME**</span></span>  
 <span data-ttu-id="2b23f-159">Fordert einen Bericht über Probleme an, die Laufzeitfehler in einer [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Konversation verursachen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-159">Requests a report of issues that cause runtime errors for a [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversation.</span></span> <span data-ttu-id="2b23f-160">Wenn weder **-NEW** noch **-ID** angegeben ist, überwacht **ssbdiagnose** alle Konversationen in allen in den Verbindungsoptionen angegebenen Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="2b23f-160">If neither **-NEW** or **-ID** are specified, **ssbdiagnose** monitors all conversations in all databases specified in the connection options.</span></span> <span data-ttu-id="2b23f-161">Wenn **-NEW** oder **-ID** angegeben ist, erstellt **ssbdiagnose** eine Liste der in den Parametern angegebenen IDs.</span><span class="sxs-lookup"><span data-stu-id="2b23f-161">If **-NEW** or **-ID** are specified, **ssbdiagnose** builds a list of the IDs specified in the parameters.</span></span>  
  
 <span data-ttu-id="2b23f-162">Solange **ssbdiagnose** ausgeführt wird, werden alle [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] -Ereignisse aufgezeichnet, die Laufzeitfehler angeben.</span><span class="sxs-lookup"><span data-stu-id="2b23f-162">While **ssbdiagnose** is running, it records all [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events that indicate runtime errors.</span></span> <span data-ttu-id="2b23f-163">Es werden die Ereignisse, die für die angegebenen IDs auftreten, sowie Ereignisse auf Systemebene aufgezeichnet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-163">It records the events that occur for the specified IDs, plus system-level events.</span></span> <span data-ttu-id="2b23f-164">Wenn Laufzeitfehler auftreten, führt **ssbdiagnose** einen Konfigurationsbericht über die zugeordnete Konfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="2b23f-164">If runtime errors are encountered, **ssbdiagnose** runs a configuration report on the associated configuration.</span></span>  
  
 <span data-ttu-id="2b23f-165">Standardmäßig werden keine Laufzeitfehler, sondern nur die Ergebnisse der Konfigurationsanalyse in den Ausgabebericht aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-165">By default, runtime errors are not included in the output report, only the results of the configuration analysis.</span></span> <span data-ttu-id="2b23f-166">Verwenden Sie **-SHOWEVENTS** , um die Laufzeitfehler in den Bericht aufzunehmen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-166">Use **-SHOWEVENTS** to have the runtime errors included in the report.</span></span>  
  
 <span data-ttu-id="2b23f-167">**-SHOWEVENTS**</span><span class="sxs-lookup"><span data-stu-id="2b23f-167">**-SHOWEVENTS**</span></span>  
 <span data-ttu-id="2b23f-168">Gibt an, dass **ssbdiagnose** in einem RUNTIME-Bericht [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] -Ereignisse melden soll.</span><span class="sxs-lookup"><span data-stu-id="2b23f-168">Specifies that **ssbdiagnose** report [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events during a RUNTIME report.</span></span> <span data-ttu-id="2b23f-169">Nur Ereignisse, die als Fehlerbedingungen erachtet werden, werden gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-169">Only events that are considered error conditions are reported.</span></span> <span data-ttu-id="2b23f-170">Standardmäßig überwacht **ssbdiagnose** Fehlerereignisse nur, meldet sie jedoch in der Ausgabe nicht.</span><span class="sxs-lookup"><span data-stu-id="2b23f-170">By default, **ssbdiagnose** only monitors error events; it does not report them in the output.</span></span>  
  
 <span data-ttu-id="2b23f-171">**-NEW**</span><span class="sxs-lookup"><span data-stu-id="2b23f-171">**-NEW**</span></span>  
 <span data-ttu-id="2b23f-172">Fordert die Laufzeitüberwachung der ersten Konversation an, die beginnt, nachdem **ssbdiagnose** gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="2b23f-172">Requests runtime monitoring of the first conversation that begins after **ssbdiagnose** starts running.</span></span>  
  
 <span data-ttu-id="2b23f-173">**-ID**</span><span class="sxs-lookup"><span data-stu-id="2b23f-173">**-ID**</span></span>  
 <span data-ttu-id="2b23f-174">Fordert die Laufzeitüberwachung der angegebenen Konversationselemente an.</span><span class="sxs-lookup"><span data-stu-id="2b23f-174">Requests runtime monitoring of the specified conversation elements.</span></span> <span data-ttu-id="2b23f-175">Sie können **-ID** mehrmals angeben.</span><span class="sxs-lookup"><span data-stu-id="2b23f-175">You can specify **-ID** multiple times.</span></span>  
  
 <span data-ttu-id="2b23f-176">Wenn Sie ein Konversationshandle angeben, werden nur Ereignisse für den zugeordneten Konversationsendpunkt gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-176">If you specify a conversation handle, only events associated with the associated conversation endpoint are reported.</span></span> <span data-ttu-id="2b23f-177">Wenn Sie eine Konversations-ID angeben, werden alle Ereignisse für diese Konversation sowie für deren Endpunkte für den Initiator und das Ziel gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-177">If you specify a conversation ID, all events for that conversation and its initiator and target endpoints are reported.</span></span> <span data-ttu-id="2b23f-178">Wenn Sie eine Konversationsgruppen-ID angeben, werden alle Ereignisse für alle Konversationen und Endpunkte in der Konversationsgruppe gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-178">If a conversation group ID is specified, all events for all conversations and endpoints in the conversation group are reported.</span></span>  
  
 <span data-ttu-id="2b23f-179">*conversation_handle*</span><span class="sxs-lookup"><span data-stu-id="2b23f-179">*conversation_handle*</span></span>  
 <span data-ttu-id="2b23f-180">Ein eindeutiger Bezeichner, der einen Konversationsendpunkt in einer Anwendung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="2b23f-180">A unique identifier that identifies a conversation endpoint in an application.</span></span> <span data-ttu-id="2b23f-181">Konversationshandles sind für einen Endpunkt einer Konversation eindeutig, d. h., die Endpunkte für den Initiator und das Ziel weisen unterschiedliche Konversationshandles auf.</span><span class="sxs-lookup"><span data-stu-id="2b23f-181">Conversation handles are unique to one endpoint of a conversation, the initiator and target endpoints have separate conversation handles.</span></span>  
  
 <span data-ttu-id="2b23f-182">Konversations Handles werden durch den *@dialog_handle* -Parameter der **Begin Dialog** -Anweisung und die- `conversation_handle` Spalte im Resultset einer **Receive** -Anweisung an Anwendungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2b23f-182">Conversation handles are returned to applications by the *@dialog_handle* parameter of the **BEGIN DIALOG** statement, and the `conversation_handle` column in the result set of a **RECEIVE** statement.</span></span>  
  
 <span data-ttu-id="2b23f-183">Konversations Handles werden in der `conversation_handle` -Spalte der Katalog Sichten **sys. transmission_queue** und **sys. conversation_endpoints** gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-183">Conversation handles are reported in the `conversation_handle` column of the **sys.transmission_queue** and **sys.conversation_endpoints** catalog views.</span></span>  
  
 <span data-ttu-id="2b23f-184">*conversation_group_id*</span><span class="sxs-lookup"><span data-stu-id="2b23f-184">*conversation_group_id*</span></span>  
 <span data-ttu-id="2b23f-185">Der eindeutige Bezeichner, der eine Konversationsgruppe identifiziert.</span><span class="sxs-lookup"><span data-stu-id="2b23f-185">The unique identifier that identifies a conversation group.</span></span>  
  
 <span data-ttu-id="2b23f-186">Konversations Gruppen-IDs werden durch den *@conversation_group_id* -Parameter der **Get Conversation Group** -Anweisung und die- `conversation_group_id` Spalte im Resultset einer **Receive** -Anweisung an Anwendungen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="2b23f-186">Conversation group IDs are returned to applications by the *@conversation_group_id* parameter of the **GET CONVERSATION GROUP** statement and the `conversation_group_id` column in the result set of a **RECEIVE** statement.</span></span>  
  
 <span data-ttu-id="2b23f-187">Konversations Gruppen-IDs werden in den `conversation_group_id` Spalten der Katalog Sichten **sys. conversation_groups** und **sys. conversation_endpoints** gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-187">Conversation group IDs are reported in the `conversation_group_id` columns of the **sys.conversation_groups** and **sys.conversation_endpoints** catalog views.</span></span>  
  
 <span data-ttu-id="2b23f-188">*conversation_id*</span><span class="sxs-lookup"><span data-stu-id="2b23f-188">*conversation_id*</span></span>  
 <span data-ttu-id="2b23f-189">Der eindeutige Bezeichner, der eine Konversation identifiziert.</span><span class="sxs-lookup"><span data-stu-id="2b23f-189">The unique identifier that identifies a conversation.</span></span> <span data-ttu-id="2b23f-190">Konversations-IDs sind für die Endpunkte für den Initiator und das Ziel einer Konversation identisch.</span><span class="sxs-lookup"><span data-stu-id="2b23f-190">Conversation IDs are the same for both the initiator and target endpoints of a conversation.</span></span>  
  
 <span data-ttu-id="2b23f-191">Konversations-IDs werden in der- `conversation_id` Spalte der **sys. conversation_endpoints** -Katalog Sicht gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-191">Conversation IDs are reported in the `conversation_id` column of the **sys.conversation_endpoints** catalog view.</span></span>  
  
 <span data-ttu-id="2b23f-192">**-TIMEOUT** *timeout_interval*</span><span class="sxs-lookup"><span data-stu-id="2b23f-192">**-TIMEOUT** *timeout_interval*</span></span>  
 <span data-ttu-id="2b23f-193">Gibt die Anzahl der Sekunden für die Ausführung eines **RUNTIME** -Berichts an.</span><span class="sxs-lookup"><span data-stu-id="2b23f-193">Specifies the number of seconds for a **RUNTIME** report to run.</span></span> <span data-ttu-id="2b23f-194">Wenn **-TIMEOUT** nicht angegeben ist, wird der Laufzeitbericht ohne zeitliche Begrenzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2b23f-194">If **-TIMEOUT** is not specified the runtime report runs indefinitely.</span></span> <span data-ttu-id="2b23f-195">**-TIMEOUT** wird nur für **RUNTIME** -Berichte und nicht für **CONFIGURATION** -Berichte verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-195">**-TIMEOUT** is used only on **RUNTIME** reports, not **CONFIGURATION** reports.</span></span> <span data-ttu-id="2b23f-196">Mit STRG+C können Sie **ssbdiagnose** beenden, wenn **-TIMEOUT** nicht angegeben wurde, oder Sie können einen Laufzeitbericht vor Ablauf des Timeoutintervalls beenden. **-**</span><span class="sxs-lookup"><span data-stu-id="2b23f-196">Use ctrl + C to quit **ssbdiagnose** if **-TIMEOUT** was not specified or to end a runtime report before the time**-** out interval expires.</span></span> <span data-ttu-id="2b23f-197">Das*Timeoutintervall* muss eine Zahl zwischen 1 und 2.147.483.647 sein.</span><span class="sxs-lookup"><span data-stu-id="2b23f-197">*timeout_interval* must be a number between 1 and 2,147,483,647.</span></span>  
  
 **\<runtimeconnectionoptions>**  
 <span data-ttu-id="2b23f-198">Gibt die Verbindungsinformationen für die Datenbanken an, in denen die den überwachten Konversationselementen zugeordneten Dienste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2b23f-198">Specifies the connection information for the databases that contain the services associated with conversation elements being monitored.</span></span> <span data-ttu-id="2b23f-199">Wenn alle Dienste in der gleichen Datenbank enthalten sind, müssen Sie nur eine **CONNECT TO** -Klausel angeben.</span><span class="sxs-lookup"><span data-stu-id="2b23f-199">If all the services are in the same database, you only have to specify one **CONNECT TO** clause.</span></span> <span data-ttu-id="2b23f-200">Wenn sich die Dienste in unterschiedlichen Datenbanken befinden, müssen Sie für jede dieser Datenbanken eine **CONNECT TO** -Klausel angeben.</span><span class="sxs-lookup"><span data-stu-id="2b23f-200">If the services are in separate databases you must supply a **CONNECT TO** clause for each database.</span></span> <span data-ttu-id="2b23f-201">Wenn **runtimeconnectionoptions** nicht angegeben ist, verwendet **ssbdiagnose** die Verbindungsinformationen aus **baseconnectionoptions**.</span><span class="sxs-lookup"><span data-stu-id="2b23f-201">If **runtimeconnectionoptions** is not specified, **ssbdiagnose** uses the connection information from **baseconnectionoptions**.</span></span>  
  
 <span data-ttu-id="2b23f-202">**-E**</span><span class="sxs-lookup"><span data-stu-id="2b23f-202">**-E**</span></span>  
 <span data-ttu-id="2b23f-203">Öffnen Sie mithilfe der Windows-Authentifizierung eine Verbindung mit einer Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] . Verwenden Sie dazu das aktuelle Windows-Konto als Anmelde-ID.</span><span class="sxs-lookup"><span data-stu-id="2b23f-203">Open a Windows Authentication connection to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] by using your current Windows account as the login ID.</span></span> <span data-ttu-id="2b23f-204">Die Anmeldung muss Mitglied der festen Serverrolle **sysadmin** sein.</span><span class="sxs-lookup"><span data-stu-id="2b23f-204">The login must be a member of the **sysadmin** fixed-server role.</span></span>  
  
 <span data-ttu-id="2b23f-205">Die Option "-E" ignoriert die Benutzer- und Kennworteinstellungen der Umgebungsvariablen SQLCMDUSER und SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="2b23f-205">The -E option ignores the user and password settings of the SQLCMDUSER and SQLCMDPASSWORD environment variables.</span></span>  
  
 <span data-ttu-id="2b23f-206">Wenn weder **-E** noch **-U** angegeben ist, verwendet **ssbdiagnose** den Wert aus der Umgebungsvariablen SQLCMDUSER.</span><span class="sxs-lookup"><span data-stu-id="2b23f-206">If neither **-E** nor **-U** is specified, **ssbdiagnose** uses the value from the SQLCMDUSER environment variable.</span></span> <span data-ttu-id="2b23f-207">Wenn SQLCMDUSER auch nicht festgelegt ist, verwendet **ssbdiagnose** die Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2b23f-207">If SQLCMDUSER is not set either, **ssbdiagnose** uses Windows Authentication.</span></span>  
  
 <span data-ttu-id="2b23f-208">Wird die Option **-E** zusammen mit der Option **-U** oder der Option **-P** verwendet, wird eine Fehlermeldung generiert.</span><span class="sxs-lookup"><span data-stu-id="2b23f-208">If the **-E** option is used together with the **-U** option or the **-P** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="2b23f-209">**-U** *login_id*</span><span class="sxs-lookup"><span data-stu-id="2b23f-209">**-U** *login_id*</span></span>  
 <span data-ttu-id="2b23f-210">Öffnen Sie mit der angegebenen Anmelde-ID eine Verbindung mit der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2b23f-210">Open a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication connection by using the specified login ID.</span></span> <span data-ttu-id="2b23f-211">Die Anmeldung muss Mitglied der festen Serverrolle **sysadmin** sein.</span><span class="sxs-lookup"><span data-stu-id="2b23f-211">The login must be a member of the **sysadmin** fixed-server role.</span></span>  
  
 <span data-ttu-id="2b23f-212">Wenn weder **-E** noch **-U** angegeben ist, verwendet **ssbdiagnose** den Wert aus der Umgebungsvariablen SQLCMDUSER.</span><span class="sxs-lookup"><span data-stu-id="2b23f-212">If neither **-E** nor **-U** is specified, **ssbdiagnose** uses the value from the SQLCMDUSER environment variable.</span></span> <span data-ttu-id="2b23f-213">Wenn SQLCMDUSER auch nicht festgelegt ist, versucht **ssbdiagnose** , eine Verbindung unter Verwendung des Windows-Authentifizierungsmodus herzustellen. Dabei wird das Windows-Konto des Benutzers verwendet, der **ssbdiagnose**ausführt.</span><span class="sxs-lookup"><span data-stu-id="2b23f-213">If SQLCMDUSER is not set either, **ssbdiagnose** tries to connect by using Windows Authentication mode based on the Windows account of the user who is running **ssbdiagnose**.</span></span>  
  
 <span data-ttu-id="2b23f-214">Wird die Option **-U** zusammen mit der Option **-E** verwendet, wird eine Fehlermeldung generiert.</span><span class="sxs-lookup"><span data-stu-id="2b23f-214">If the **-U** option is used together with the **-E** option, an error message is generated.</span></span> <span data-ttu-id="2b23f-215">Werden nach der Option **-U** mehrere Argumente angegeben, wird eine Fehlermeldung generiert und das Programm beendet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-215">If the **-U** option is followed by more than one argument, an error message is generated and the program exits.</span></span>  
  
 <span data-ttu-id="2b23f-216">**-P** *password*</span><span class="sxs-lookup"><span data-stu-id="2b23f-216">**-P** *password*</span></span>  
 <span data-ttu-id="2b23f-217">Gibt das Kennwort für die Anmelde-ID **-U** an.</span><span class="sxs-lookup"><span data-stu-id="2b23f-217">Specifies the password for the **-U** login ID.</span></span> <span data-ttu-id="2b23f-218">Bei Kennwörtern wird nach Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-218">Passwords are case sensitive.</span></span> <span data-ttu-id="2b23f-219">Wenn die Option **-U** verwendet wird, nicht aber die Option **-P** , verwendet **ssbdiagnose** den Wert aus der Umgebungsvariablen SQLCMDPASSWORD.</span><span class="sxs-lookup"><span data-stu-id="2b23f-219">If the **-U** option is used and the **-P** option is not used, **ssbdiagnose** uses the value from the SQLCMDPASSWORD environment variable.</span></span> <span data-ttu-id="2b23f-220">Wenn SQLCMDPASSWORD auch nicht festgelegt ist, fordert **ssbdiagnose** den Benutzer zur Eingabe eines Kennworts auf.</span><span class="sxs-lookup"><span data-stu-id="2b23f-220">If SQLCMDPASSWORD is not set either, **ssbdiagnose** prompts the user for a password.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="2b23f-221">Wenn Sie einen SET SQLCMDPASSWORD-Befehl eingeben, kann das Kennwort von jeder Person gelesen werden, die auf den Bildschirm schauen kann.</span><span class="sxs-lookup"><span data-stu-id="2b23f-221">When you type a SET SQLCMDPASSWORD command, your password will be visible to anyone who can see your monitor.</span></span>  
  
 <span data-ttu-id="2b23f-222">Wenn die Option **-P** ohne Kennwort angegeben ist, verwendet **ssbdiagnose** das Standardkennwort (NULL).</span><span class="sxs-lookup"><span data-stu-id="2b23f-222">If the **-P** option is specified without a password **ssbdiagnose** uses the default password (NULL).</span></span>  
  
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteStrongPass](../../includes/ssnotestrongpass-md.md)] <span data-ttu-id="2b23f-223">Weitere Informationen finden Sie unter [Sichere Kennwörter](../../relational-databases/security/strong-passwords.md).</span><span class="sxs-lookup"><span data-stu-id="2b23f-223">For more information, see [Strong Passwords](../../relational-databases/security/strong-passwords.md).</span></span>  
  
 <span data-ttu-id="2b23f-224">Die Aufforderung zur Eingabe des Kennworts wird folgendermaßen an der Konsole ausgegeben: `Password:`</span><span class="sxs-lookup"><span data-stu-id="2b23f-224">The password prompt is displayed by printing the password prompt to the console, as follows: `Password:`</span></span>  
  
 <span data-ttu-id="2b23f-225">Die Benutzereingabe bleibt verborgen,</span><span class="sxs-lookup"><span data-stu-id="2b23f-225">User input is hidden.</span></span> <span data-ttu-id="2b23f-226">d. h. es erfolgt keine Anzeige, und der Cursor bleibt an der Anfangsposition.</span><span class="sxs-lookup"><span data-stu-id="2b23f-226">This means that nothing is displayed and the cursor stays in position.</span></span>  
  
 <span data-ttu-id="2b23f-227">Wird die Option **-P** zusammen mit der Option **-E** verwendet, wird eine Fehlermeldung generiert.</span><span class="sxs-lookup"><span data-stu-id="2b23f-227">If the **-P** option is used with the **-E** option, an error message is generated.</span></span>  
  
 <span data-ttu-id="2b23f-228">Wird nach der Option **-P** mehr als ein Argument angegeben, wird eine Fehlermeldung generiert.</span><span class="sxs-lookup"><span data-stu-id="2b23f-228">If the **-P** option is followed by more than one argument, an error message is generated.</span></span>  
  
 <span data-ttu-id="2b23f-229">**-S** *server_name*[\\*instance_name*]</span><span class="sxs-lookup"><span data-stu-id="2b23f-229">**-S** *server_name*[\\*instance_name*]</span></span>  
 <span data-ttu-id="2b23f-230">Gibt die Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] an, die die zu analysierenden [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Dienste enthält.</span><span class="sxs-lookup"><span data-stu-id="2b23f-230">Specifies the instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] that holds the [!INCLUDE[ssSB](../../includes/sssb-md.md)] services to be analyzed.</span></span>  
  
 <span data-ttu-id="2b23f-231">Geben Sie *Servername* an, um eine Verbindung mit der Standardinstanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] auf diesem Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-231">Specify *server_name* to connect to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="2b23f-232">Geben Sie *server_name ***\\*** instance_name* an, um eine Verbindung mit einer benannten Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] auf diesem Server herzustellen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-232">Specify *server_name***\\***instance_name* to connect to a named instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on that server.</span></span> <span data-ttu-id="2b23f-233">Wenn **-S** nicht angegeben ist, verwendet **ssbdiagnose** den Wert der Umgebungsvariablen SQLCMDSERVER.</span><span class="sxs-lookup"><span data-stu-id="2b23f-233">If **-S** is not specified, **ssbdiagnose** uses the value of the SQLCMDSERVER environment variable.</span></span> <span data-ttu-id="2b23f-234">Wenn SQLCMDSERVER auch nicht festgelegt ist, stellt **ssbdiagnose** eine Verbindung mit der Standardinstanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)] auf dem lokalen Computer her.</span><span class="sxs-lookup"><span data-stu-id="2b23f-234">If SQLCMDSERVER is not set either, **ssbdiagnose** connects to the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] on the local computer.</span></span>  
  
 <span data-ttu-id="2b23f-235">**-d** *database_name*</span><span class="sxs-lookup"><span data-stu-id="2b23f-235">**-d** *database_name*</span></span>  
 <span data-ttu-id="2b23f-236">Gibt die Datenbank an, die die zu analysierenden [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Dienste enthält.</span><span class="sxs-lookup"><span data-stu-id="2b23f-236">Specifies the database that holds the [!INCLUDE[ssSB](../../includes/sssb-md.md)] services to be analyzed.</span></span> <span data-ttu-id="2b23f-237">Wenn die Datenbank nicht vorhanden ist, wird eine Fehlermeldung generiert.</span><span class="sxs-lookup"><span data-stu-id="2b23f-237">If the database does not exist, an error message is generated.</span></span> <span data-ttu-id="2b23f-238">Wenn **-d** nicht angegeben ist, wird standardmäßig die Datenbank verwendet, die in der Standarddatenbank-Eigenschaft Ihrer Anmeldung angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="2b23f-238">If **-d** is not specified, the default is the database specified in the default-database property for your login.</span></span>  
  
 <span data-ttu-id="2b23f-239">**-l** *login_timeout*</span><span class="sxs-lookup"><span data-stu-id="2b23f-239">**-l** *login_timeout*</span></span>  
 <span data-ttu-id="2b23f-240">Gibt die Anzahl von Sekunden an, die verstreichen, ehe für den Versuch einer Verbindung mit einem Server ein Timeout eintritt. Wenn **-l** nicht angegeben ist, verwendet **ssbdiagnose** den für die Umgebungsvariable SQLCMDLOGINTIMEOUT festgelegten Wert.</span><span class="sxs-lookup"><span data-stu-id="2b23f-240">Specifies the number of seconds before an attempt to connect to a server times out. If **-l** is not specified, **ssbdiagnose** uses the value set for the SQLCMDLOGINTIMEOUT environment variable.</span></span> <span data-ttu-id="2b23f-241">Wenn SQLCMDLOGINTIMEOUT auch nicht festgelegt ist, beträgt der Standardwert für das Timeout dreißig Sekunden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-241">If SQLCMDLOGINTIMEOUT is not set either, the default time-out is thirty seconds.</span></span> <span data-ttu-id="2b23f-242">Der Timeoutwert für den Anmeldungszeitraum muss eine Zahl zwischen 0 und 65534 sein.</span><span class="sxs-lookup"><span data-stu-id="2b23f-242">The login time-out must be a number between 0 and 65534.</span></span> <span data-ttu-id="2b23f-243">Wenn der angegebene Wert kein numerischer Wert ist oder außerhalb dieses Bereichs liegt, generiert **ssbdiagnose** eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="2b23f-243">If the value that is supplied is not numeric or does not fall into that range, **ssbdiagnose** generates an error message.</span></span> <span data-ttu-id="2b23f-244">Mit dem Wert 0 wird eine unbegrenzte Wartezeit festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2b23f-244">A value of 0 specifies time-out to be infinite.</span></span>  
  
 <span data-ttu-id="2b23f-245">**-?**</span><span class="sxs-lookup"><span data-stu-id="2b23f-245">**-?**</span></span>  
 <span data-ttu-id="2b23f-246">Zeigt die Hilfe zur Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="2b23f-246">Displays command line help.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2b23f-247">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2b23f-247">Remarks</span></span>  
 <span data-ttu-id="2b23f-248">Verwenden Sie **ssbdiagnose** , um folgende Aufgaben auszuführen:</span><span class="sxs-lookup"><span data-stu-id="2b23f-248">Use **ssbdiagnose** to do the following:</span></span>  
  
-   <span data-ttu-id="2b23f-249">Bestätigen, dass in einer neu konfigurierten [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Anwendung keine Konfigurationsfehler vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2b23f-249">Confirm that there are no configuration errors in a newly configured [!INCLUDE[ssSB](../../includes/sssb-md.md)] application.</span></span>  
  
-   <span data-ttu-id="2b23f-250">Bestätigen, dass keine Konfigurationsfehler vorhanden sind, nachdem Sie die Konfiguration einer vorhandenen [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Anwendung geändert haben.</span><span class="sxs-lookup"><span data-stu-id="2b23f-250">Confirm that there are no configuration errors after changing the configuration of an existing [!INCLUDE[ssSB](../../includes/sssb-md.md)] application.</span></span>  
  
-   <span data-ttu-id="2b23f-251">Bestätigen, dass keine Konfigurationsfehler vorhanden sind, nachdem eine [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Datenbank getrennt und dann an eine neue Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="2b23f-251">Confirm that there are no configuration errors after a [!INCLUDE[ssSB](../../includes/sssb-md.md)] database is detached and then reattached to a new instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="2b23f-252">Überprüfen, ob Konfigurationsfehler vorhanden sind, wenn Nachrichten nicht erfolgreich zwischen Diensten übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-252">Research whether there are configuration errors when messages are not successfully transmitted between services.</span></span>  
  
-   <span data-ttu-id="2b23f-253">Abrufen eines Berichts über Fehler, die in einer Gruppe von [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Konversationselementen auftreten.</span><span class="sxs-lookup"><span data-stu-id="2b23f-253">Get a report of any errors that occur in a set of [!INCLUDE[ssSB](../../includes/sssb-md.md)] conversation elements.</span></span>  
  
## <a name="configuration-reporting"></a><span data-ttu-id="2b23f-254">Konfigurationsberichte</span><span class="sxs-lookup"><span data-stu-id="2b23f-254">Configuration Reporting</span></span>  
 <span data-ttu-id="2b23f-255">Führen Sie einen **ssbdiagnose** -Konfigurationsbericht aus, für den die gleichen Optionen wie für die Konversation verwendet werden, um die von einer Konversation verwendete Konfiguration ordnungsgemäß zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="2b23f-255">To correctly analyze the configuration used by a conversation, run a **ssbdiagnose** configuration report that uses the same options that are used by the conversation.</span></span> <span data-ttu-id="2b23f-256">Wenn Sie für **ssbdiagnose** weniger Optionen angeben, als für die Konversation verwendet werden, meldet **ssbdiagnose** möglicherweise keine Bedingungen, die für die Konversation erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2b23f-256">If you specify a lower level of options for **ssbdiagnose** than are used by the conversation, **ssbdiagnose** might not report conditions that are required by the conversation.</span></span> <span data-ttu-id="2b23f-257">Wenn Sie für **ssbdiagnose**mehr Optionen angeben, werden möglicherweise Elemente gemeldet, die für die Konversation nicht erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="2b23f-257">If you specify a higher level of options for **ssbdiagnose**, it might report items that are not required by the conversation.</span></span> <span data-ttu-id="2b23f-258">So kann z. B. eine Konversation zwischen zwei Diensten in der gleichen Datenbank mit ENCPRYPTION OFF ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-258">For example, a conversation between two services in the same database can be run with ENCPRYPTION OFF.</span></span> <span data-ttu-id="2b23f-259">Wenn Sie **ssbdiagnose** ausführen, um die Konfiguration zwischen den beiden Diensten zu überprüfen, dabei jedoch die Standardeinstellung ENCRYPTION ON verwenden, meldet **ssbdiagnose** , dass in der Datenbank ein Hauptschlüssel fehlt.</span><span class="sxs-lookup"><span data-stu-id="2b23f-259">If you run **ssbdiagnose** to validate the configuration between the two services, but use the default ENCRYPTION ON setting, **ssbdiagnose** reports that the database is missing a master key.</span></span> <span data-ttu-id="2b23f-260">Ein Hauptschlüssel ist für die Konversation nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2b23f-260">A master key is not required for the conversation.</span></span>  
  
 <span data-ttu-id="2b23f-261">Der **ssbdiagnose** -Konfigurationsbericht analysiert bei jeder Ausführung nur einen einzelnen [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Dienst oder ein einzelnes Paar von Diensten.</span><span class="sxs-lookup"><span data-stu-id="2b23f-261">The **ssbdiagnose** configuration report analyzes only one [!INCLUDE[ssSB](../../includes/sssb-md.md)] service or a single pair of services every time it is run.</span></span> <span data-ttu-id="2b23f-262">Wenn mehrere Paare von [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Diensten im Bericht berücksichtigt werden sollen, erstellen Sie eine CMD-Befehlsdatei, die **ssbdiagnose** mehrmals aufruft.</span><span class="sxs-lookup"><span data-stu-id="2b23f-262">To report on multiple pairs of [!INCLUDE[ssSB](../../includes/sssb-md.md)] services, build a .cmd command file that calls **ssbdiagnose** multiple times.</span></span>  
  
## <a name="runtime-reporting"></a><span data-ttu-id="2b23f-263">Laufzeitberichte</span><span class="sxs-lookup"><span data-stu-id="2b23f-263">Runtime Reporting</span></span>  
 <span data-ttu-id="2b23f-264">Wenn -RUNTIME angegeben ist, durchsucht **ssbdiagnose** alle in **runtimeconnectionoptions** und **baseconnectionoptions** angegebenen Datenbanken, um eine Liste der [!INCLUDE[ssSB](../../includes/sssb-md.md)] -IDs zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-264">When -RUNTIME is specified, **ssbdiagnose** searches all databases specified in **runtimeconnectionoptions** and **baseconnectionoptions** to build a list of [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs.</span></span> <span data-ttu-id="2b23f-265">Wie die vollständige Liste von IDs aussieht, hängt davon ab, was für - NEW und - ID angegeben wird:</span><span class="sxs-lookup"><span data-stu-id="2b23f-265">The full list of IDs built depends on what is specified for -NEW and -ID:</span></span>  
  
-   <span data-ttu-id="2b23f-266">Wenn weder **-NEW** noch **-ID** angegeben ist, enthält die Liste alle Konversationen für alle in den Verbindungsoptionen angegebenen Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="2b23f-266">If neither **-NEW** or **-ID** are specified, the list includes all conversations for all databases specified in the connection options.</span></span>  
  
-   <span data-ttu-id="2b23f-267">Wenn **-NEW** angegeben ist, schließt **ssbdiagnose** die Elemente für die erste Konversation ein, die gestartet wird, nachdem **ssbdiagnose** gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="2b23f-267">If **-NEW** is specified, **ssbdiagnose** includes the elements for the first conversation that starts after **ssbdiagnose** is run.</span></span> <span data-ttu-id="2b23f-268">Hierzu zählen die Konversations-ID und die Konversationshandles für die Konversationsendpunkte für den Initiator und das Ziel.</span><span class="sxs-lookup"><span data-stu-id="2b23f-268">This includes the conversation ID and the conversation handles for both the target and initiator conversation endpoints.</span></span>  
  
-   <span data-ttu-id="2b23f-269">Wenn **-ID** mit einem Konversationshandle angegeben ist, wird nur dieses Handle in die Liste aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-269">If **-ID** is specified with a conversation handle, only that handle is included in the list.</span></span>  
  
-   <span data-ttu-id="2b23f-270">Wenn **-ID** mit einer Konversations-ID angegeben ist, werden die Konversations-ID und die Handles für beide Konversationsendpunkte der Liste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2b23f-270">If **-ID** is specified with a conversation ID, the conversation ID and the handles for both of its conversation endpoints are added to the list.</span></span>  
  
-   <span data-ttu-id="2b23f-271">Wenn **-ID** mit einer Konversationsgruppen-ID angegeben ist, werden alle in der Gruppe enthaltenen Konversations-IDs und Konversationshandles der Liste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2b23f-271">If **-ID** is specified with a conversation group ID, all the conversation IDs and conversation handles in that group are added to the list.</span></span>  
  
 <span data-ttu-id="2b23f-272">Die Liste enthält keine Elemente aus Datenbanken, die in den Verbindungsoptionen nicht angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-272">The list does not include elements from databases that are not covered by the connection options.</span></span> <span data-ttu-id="2b23f-273">Beispiel: Angenommen, Sie verwenden **-ID** , um eine Konversations-ID anzugeben, geben jedoch nur für die Initiatordatenbank eine **runtimeconnectionoptions** -Klausel an, nicht für die Zieldatenbank.</span><span class="sxs-lookup"><span data-stu-id="2b23f-273">For example, assume that you use **-ID** to specify a conversation ID, but only provide a **runtimeconnectionoptions** clause for the initiator database and not the target database.</span></span> <span data-ttu-id="2b23f-274">**ssbdiagnose** schließt das Zielkonversationshandle in diesem Fall nicht in die Liste der IDs ein, sondern nur die Konversations-ID und das Initiatorkonversationshandle.</span><span class="sxs-lookup"><span data-stu-id="2b23f-274">**ssbdiagnose** will not include the target conversation handle in its list of IDs, only the conversation ID and the initiator conversation handle.</span></span>  
  
 <span data-ttu-id="2b23f-275">**ssbdiagnose** überwacht die [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] -Ereignisse in den von **runtimeconnectionoptions** und **baseconnectionoptions**abgedeckten Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="2b23f-275">**ssbdiagnose** monitors the [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] events from the databases covered by **runtimeconnectionoptions** and **baseconnectionoptions**.</span></span> <span data-ttu-id="2b23f-276">Das Hilfsprogramm sucht [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Ereignisse, die angeben, dass von einer oder mehreren der [!INCLUDE[ssSB](../../includes/sssb-md.md)] -IDs in der Laufzeitliste ein Fehler gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="2b23f-276">It searches for [!INCLUDE[ssSB](../../includes/sssb-md.md)] events that indicate an error was encountered by one or more of the [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs in the runtime list.</span></span> <span data-ttu-id="2b23f-277">**ssbdiagnose** sucht auch nach [!INCLUDE[ssSB](../../includes/sssb-md.md)] -Fehlerereignissen auf Systemebene, die nicht explizit mit einer bestimmten Konversationsgruppe verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="2b23f-277">**ssbdiagnose** also searches for system-level [!INCLUDE[ssSB](../../includes/sssb-md.md)] error events not specifically associated with any conversation group.</span></span>  
  
 <span data-ttu-id="2b23f-278">Wenn **ssbdiagnose** Konversationsfehler feststellt, versucht das Hilfsprogramm, die Ursache der Ereignisse zurückzugeben, indem zusätzlich ein Konfigurationsbericht ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2b23f-278">If **ssbdiagnose** finds conversation errors, the utility will attempt to report on the root cause of the events by also running a configuration report.</span></span> <span data-ttu-id="2b23f-279">**ssbdiagnose** ermittelt anhand der Metadaten in den Datenbanken die von der Konversation verwendeten Instanzen, [!INCLUDE[ssSB](../../includes/sssb-md.md)] -IDs, Datenbanken, Dienste und Verträge.</span><span class="sxs-lookup"><span data-stu-id="2b23f-279">**ssbdiagnose** uses the metadata in the databases to try to determine the instances, [!INCLUDE[ssSB](../../includes/sssb-md.md)] IDs, databases, services, and contracts used by the conversation.</span></span> <span data-ttu-id="2b23f-280">Anschließend wird ein Konfigurationsbericht mit allen verfügbaren Informationen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2b23f-280">It then runs a configuration report using all available information.</span></span>  
  
 <span data-ttu-id="2b23f-281">Standardmäßig meldet **ssbdiagnose** keine Fehlerereignisse.</span><span class="sxs-lookup"><span data-stu-id="2b23f-281">By default, **ssbdiagnose** does not report error events.</span></span> <span data-ttu-id="2b23f-282">Es werden nur die während der Konfigurationsüberprüfung gefundenen eigentlichen Probleme gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-282">It only reports the underlying issues found during the configuration check.</span></span> <span data-ttu-id="2b23f-283">Dadurch wird die Menge gemeldeter Informationen minimiert, und Sie können sich besser auf die eigentlichen Konfigurationsprobleme konzentrieren.</span><span class="sxs-lookup"><span data-stu-id="2b23f-283">This minimizes the amount of information reported and helps you focus on the underlying configuration issues.</span></span> <span data-ttu-id="2b23f-284">Sie können **-SHOWEVENTS** angeben, um die von **ssbdiagnose**gefundenen Fehlerereignisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-284">You can specify **-SHOWEVENTS** to see the error events encountered by **ssbdiagnose**.</span></span>  
  
## <a name="issues-reported-by-ssbdiagnose"></a><span data-ttu-id="2b23f-285">Von "ssbdiagnose" gemeldete Probleme</span><span class="sxs-lookup"><span data-stu-id="2b23f-285">Issues Reported by ssbdiagnose</span></span>  
 <span data-ttu-id="2b23f-286">**ssbdiagnose** meldet drei Klassen von Problemen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-286">**ssbdiagnose** reports three classes of issues.</span></span> <span data-ttu-id="2b23f-287">In der XML-Ausgabedatei wird jede Klasse von Problemen als gesonderter Typ des Issue-Elements gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-287">In the XML output file, each class of issue is reported as a separate type of the Issue element.</span></span> <span data-ttu-id="2b23f-288">Folgende drei Typen von Problemen werden von **ssbdiagnose** gemeldet:</span><span class="sxs-lookup"><span data-stu-id="2b23f-288">The three types of issues reported by **ssbdiagnose** are as follows:</span></span>  
  
 <span data-ttu-id="2b23f-289">**Diagnosis**</span><span class="sxs-lookup"><span data-stu-id="2b23f-289">**Diagnosis**</span></span>  
 <span data-ttu-id="2b23f-290">Meldet ein Konfigurationsproblem.</span><span class="sxs-lookup"><span data-stu-id="2b23f-290">Reports a configuration issue.</span></span> <span data-ttu-id="2b23f-291">Hierunter fallen Probleme, die entweder bei der Ausführung eines **CONFIGURATION** -Berichts oder in der Konfigurationsphase eines **RUNTIME** -Berichts gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-291">This includes issues found either a **CONFIGURATION** report is running, or during the configuration phase of a **RUNTIME** report.</span></span> <span data-ttu-id="2b23f-292">**ssbdiagnose** meldet jedes Konfigurationsproblem nur einmal.</span><span class="sxs-lookup"><span data-stu-id="2b23f-292">**ssbdiagnose** reports each configuration issue one time.</span></span>  
  
 <span data-ttu-id="2b23f-293">**Event**</span><span class="sxs-lookup"><span data-stu-id="2b23f-293">**Event**</span></span>  
 <span data-ttu-id="2b23f-294">Meldet ein [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] -Ereignis, das auf ein Problem bei einer überwachten Konversation während eines **RUNTIME** -Berichts hindeutet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-294">Reports a [!INCLUDE[ssSqlProfiler](../../includes/sssqlprofiler-md.md)] event that indicates a problem was encountered by a conversation being monitored during a **RUNTIME** report.</span></span> <span data-ttu-id="2b23f-295">**ssbdiagnose** meldet jedes generierte Ereignis.</span><span class="sxs-lookup"><span data-stu-id="2b23f-295">**ssbdiagnose** reports events every time they are generated.</span></span> <span data-ttu-id="2b23f-296">Ereignisse können mehrmals gemeldet werden, wenn das Problem in mehreren Konversationen auftritt.</span><span class="sxs-lookup"><span data-stu-id="2b23f-296">Events can be reported multiple times if several conversations encounter the problem.</span></span>  
  
 <span data-ttu-id="2b23f-297">**Problem**</span><span class="sxs-lookup"><span data-stu-id="2b23f-297">**Problem**</span></span>  
 <span data-ttu-id="2b23f-298">Meldet ein Problem, das **ssbdiagnose** daran hindert, eine Konfigurationsanalyse abzuschließen oder Konversationen zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-298">Reports an issue that is preventing **ssbdiagnose** from completing a configuration analysis or from monitoring conversations.</span></span>  
  
## <a name="sqlcmd-environment-variables"></a><span data-ttu-id="2b23f-299">Umgebungsvariablen von "sqlcmd"</span><span class="sxs-lookup"><span data-stu-id="2b23f-299">sqlcmd Environment Variables</span></span>  
 <span data-ttu-id="2b23f-300">Das Hilfsprogramm **ssbdiagnose** unterstützt die Umgebungsvariablen SQLCMDSERVER, SQLCMDUSER, SQLCMDPASSWORD und SQLCMDLOGINTIMOUT, die auch von dem Hilfsprogramm **sqlcmd** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-300">The **ssbdiagnose** utility supports the SQLCMDSERVER, SQLCMDUSER, SQLCMDPASSWORD, and SQLCMDLOGINTIMOUT environment variables that are also used by the **sqlcmd** utility.</span></span> <span data-ttu-id="2b23f-301">Sie können zum Festlegen der Umgebungsvariablen entweder den SET-Befehl an der Eingabeaufforderung oder den **setvar** -Befehl in [!INCLUDE[tsql](../../includes/tsql-md.md)] -Skripts verwenden, die Sie mit **sqlcmd**ausführen.</span><span class="sxs-lookup"><span data-stu-id="2b23f-301">You can set the environment variables either by using the command prompt SET command, or by using the **setvar** command in [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts that you run by using **sqlcmd**.</span></span> <span data-ttu-id="2b23f-302">Weitere Informationen zum Verwenden von **setvar** in **sqlcmd**finden Sie unter [Verwenden von sqlcmd mit Skriptvariablen](../../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span><span class="sxs-lookup"><span data-stu-id="2b23f-302">For more information about how to use **setvar** in **sqlcmd**, see [Use sqlcmd with Scripting Variables](../../relational-databases/scripting/sqlcmd-use-with-scripting-variables.md).</span></span>  
  
## <a name="permissions"></a><span data-ttu-id="2b23f-303">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="2b23f-303">Permissions</span></span>  
 <span data-ttu-id="2b23f-304">In jeder **connectionoptions** -Klausel muss der mit **-E** oder **-U** angegebene Anmeldename Mitglied der festen Serverrolle **sysadmin** in der in **-S**angegebenen Instanz sein.</span><span class="sxs-lookup"><span data-stu-id="2b23f-304">In each **connectionoptions** clause, the login specified with either **-E** or **-U** must be a member of the **sysadmin** fixed-server role in the instance specified in **-S**.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2b23f-305">Beispiele</span><span class="sxs-lookup"><span data-stu-id="2b23f-305">Examples</span></span>  
 <span data-ttu-id="2b23f-306">Dieser Abschnitt enthält Beispiele für die Verwendung von **ssbdiagnose** an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="2b23f-306">This section contains examples of using **ssbdiagnose** at a command prompt.</span></span>  
  
### <a name="a-checking-the-configuration-of-two-services-in-the-same-database"></a><span data-ttu-id="2b23f-307">A.</span><span class="sxs-lookup"><span data-stu-id="2b23f-307">A.</span></span> <span data-ttu-id="2b23f-308">Überprüfen der Konfiguration von zwei Diensten in der gleichen Datenbank</span><span class="sxs-lookup"><span data-stu-id="2b23f-308">Checking the Configuration of Two Services in the Same Database</span></span>  
 <span data-ttu-id="2b23f-309">Im folgenden Beispiel wird gezeigt, wie ein Konfigurationsbericht angefordert wird, wenn folgende Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="2b23f-309">The following example shows how to request a configuration report when the following are true;</span></span>  
  
-   <span data-ttu-id="2b23f-310">Der Initiator- und der Zieldienst befinden sich in der gleichen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2b23f-310">The initiator and target service are in the same database.</span></span>  
  
-   <span data-ttu-id="2b23f-311">Die Datenbank befindet sich in der Standardinstanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b23f-311">The database is in the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="2b23f-312">Die Instanz befindet sich auf dem Computer, auf dem **ssbdiagnose** ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2b23f-312">The instances is on the same computer on which **ssbdiagnose** is run.</span></span>  
  
 <span data-ttu-id="2b23f-313">Das Hilfsprogramm **ssbdiagnose** meldet die Konfiguration, die den DEFAULT-Vertrag verwendet, weil ON CONTRACT nicht angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="2b23f-313">The **ssbdiagnose** utility reports the configuration that uses the DEFAULT contract because ON CONTRACT is not specified.</span></span>  
  
```  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE /test/initiator TO SERVICE /test/target  
```  
  
### <a name="b-checking-the-configuration-of-two-services-on-separate-computers-that-use-one-login"></a><span data-ttu-id="2b23f-314">B.</span><span class="sxs-lookup"><span data-stu-id="2b23f-314">B.</span></span> <span data-ttu-id="2b23f-315">Überprüfen der Konfiguration von zwei Diensten auf unterschiedlichen Computern, die einen Anmeldenamen verwenden</span><span class="sxs-lookup"><span data-stu-id="2b23f-315">Checking the Configuration of Two Services on Separate Computers That Use One Login</span></span>  
 <span data-ttu-id="2b23f-316">Das folgende Beispiel zeigt, wie ein Konfigurationsbericht angefordert wird, wenn sich der Initiator- und der Zieldienst auf unterschiedlichen Computern befinden, der Zugriff auf diese jedoch mit dem gleichen Anmeldenamen für die Windows-Authentifizierung erfolgt.</span><span class="sxs-lookup"><span data-stu-id="2b23f-316">The following example shows how to request a configuration report when the initiator and target service are on separate computers, but can be accessed by using the same Windows Authentication login.</span></span>  
  
```  
ssbdiagnose -E CONFIGURATION FROM SERVICE /text/initiator -S InitiatorComputer -d InitiatorDatabase TO SERVICE /test/target -S TargetComputer -d TargetDatabase ON CONTRACT TestContract  
```  
  
### <a name="c-checking-the-configuration-of-two-services-on-separate-computers-that-use-separate-logins"></a><span data-ttu-id="2b23f-317">C.</span><span class="sxs-lookup"><span data-stu-id="2b23f-317">C.</span></span> <span data-ttu-id="2b23f-318">Überprüfen der Konfiguration von zwei Diensten auf unterschiedlichen Computern, die unterschiedliche Anmeldenamen verwenden</span><span class="sxs-lookup"><span data-stu-id="2b23f-318">Checking the Configuration of Two Services on Separate Computers That Use Separate Logins</span></span>  
 <span data-ttu-id="2b23f-319">Das folgende Beispiel zeigt, wie ein Konfigurationsbericht angefordert wird, wenn sich der Initiator- und der Zieldienst auf unterschiedlichen Computern befinden und für jede Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ein separater Anmeldename für die [!INCLUDE[ssDE](../../includes/ssde-md.md)]-Authentifizierung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="2b23f-319">The following example shows how to request a configuration report when the initiator and target service are on separate computers, and separate [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication logins are required for each instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
```  
ssbdiagnose CONFIGURATION FROM SERVICE /text/initiator   
-S InitiatorComputer -U InitiatorLogin -p !wEx23Dvb   
-d InitiatorDatabase TO SERVICE /test/target -S TargetComputer   
-U TargetLogin -p ER!49jiy -d TargetDatabase ON CONTRACT TestContract  
```  
  
### <a name="d-checking-mirrored-service-configurations-on-separate-computers-with-anonymous-encryption"></a><span data-ttu-id="2b23f-320">D:</span><span class="sxs-lookup"><span data-stu-id="2b23f-320">D.</span></span> <span data-ttu-id="2b23f-321">Überprüfen der Konfigurationen gespiegelter Dienste auf separaten Computern mit anonymer Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="2b23f-321">Checking Mirrored Service Configurations on Separate Computers With Anonymous Encryption</span></span>  
 <span data-ttu-id="2b23f-322">Das folgende Beispiel zeigt, wie ein Konfigurationsbericht angefordert wird, wenn sich der Initiator- und der Zieldienst auf unterschiedlichen Computern befinden und der Initiator auf eine benannte Instanz gespiegelt ist.</span><span class="sxs-lookup"><span data-stu-id="2b23f-322">The following example shows how to request a configuration report when the initiator and target service are on separate computers and the initiator is mirrored to a named instance.</span></span> <span data-ttu-id="2b23f-323">Mit dem Bericht wird auch überprüft, ob die Dienste für die anonyme Verschlüsselung konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="2b23f-323">The report also verifies that the services are configured to use anonymous encryption.</span></span>  
  
```  
ssbdiagnose -E CONFIGURATION FROM SERVICE /text/initiator   
-S InitiatorComputer -d InitiatorDatabase MIRROR   
-S MirrorComputer/MirrorInstance TO SERVICE /test/target   
-S TargetComputer -d TargetDatabase ON CONTRACT TestContract ENCRYPTION ANONYMOUS  
```  
  
### <a name="e-checking-the-configuration-of-two-contracts"></a><span data-ttu-id="2b23f-324">E.</span><span class="sxs-lookup"><span data-stu-id="2b23f-324">E.</span></span> <span data-ttu-id="2b23f-325">Überprüfen der Konfiguration von zwei Verträgen</span><span class="sxs-lookup"><span data-stu-id="2b23f-325">Checking the Configuration of Two Contracts</span></span>  
 <span data-ttu-id="2b23f-326">Im folgenden Beispiel wird gezeigt, wie eine Befehlsdatei erstellt wird, mit der Konfigurationsberichte angefordert werden, wenn folgende Bedingungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="2b23f-326">The following example shows how to build a command file that requests configuration reports when the following are true:</span></span>  
  
-   <span data-ttu-id="2b23f-327">Der Initiator- und der Zieldienst befinden sich in der gleichen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="2b23f-327">The initiator and target service are in the same database.</span></span>  
  
-   <span data-ttu-id="2b23f-328">Die Datenbank befindet sich in der Standardinstanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2b23f-328">The database is in the default instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span>  
  
-   <span data-ttu-id="2b23f-329">Die Instanz befindet sich auf dem Computer, auf dem **ssbdiagnose** ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2b23f-329">The instance is on the same computer on which **ssbdiagnose** is run.</span></span>  
  
 <span data-ttu-id="2b23f-330">Bei jeder Ausführung von **ssbdiagnose** wird die Konfiguration für einen anderen Vertrag zwischen den gleichen Diensten gemeldet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-330">Each time **ssbdiagnose** is run it reports the configuration for a different contract between the same services.</span></span>  
  
```  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target ON CONTRACT PayRaiseContract  
ssbdiagnose -E -d MyDatabase CONFIGURATION FROM SERVICE /test/initiator   
TO SERVICE /test/target ON CONTRACT PromotionContract  
```  
  
### <a name="f-monitor-the-status-of-a-specific-conversation-on-the-local-computer-with-a-time-out"></a><span data-ttu-id="2b23f-331">F.</span><span class="sxs-lookup"><span data-stu-id="2b23f-331">F.</span></span> <span data-ttu-id="2b23f-332">Überwachen des Status einer bestimmten Konversation auf dem lokalen Computer mit einem Timeout</span><span class="sxs-lookup"><span data-stu-id="2b23f-332">Monitor the status of a specific conversation on the local computer with a time out</span></span>  
 <span data-ttu-id="2b23f-333">Das folgende Beispiel zeigt, wie eine bestimmte Konversation überwacht wird, wenn sich der Initiator- und der Zieldienst in der gleichen Datenbank in der Standardinstanz auf dem gleichen Computer befinden, auf dem auch **ssbdiagnose**ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="2b23f-333">The following example shows how to monitor a specific conversation where the initiator and target services are in the same database in the default instance of the same computer that is running **ssbdiagnose**.</span></span> <span data-ttu-id="2b23f-334">Das Timeoutintervall ist auf 20 Sekunden festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2b23f-334">The time-out interval is set to 20 seconds.</span></span>  
  
```  
ssbdiagnose -E -d TestDatabase RUNTIME -ID D68D77A9-B1CF-41BF-A5CE-279ABCAB140D -TIMEOUT 20  
```  
  
### <a name="g-monitor-the-status-of-a-conversation-that-spans-two-computers"></a><span data-ttu-id="2b23f-335">G.</span><span class="sxs-lookup"><span data-stu-id="2b23f-335">G.</span></span> <span data-ttu-id="2b23f-336">Überwachen des Status einer Konversation, die zwei Computer umfasst</span><span class="sxs-lookup"><span data-stu-id="2b23f-336">Monitor the status of a conversation that spans two computers</span></span>  
 <span data-ttu-id="2b23f-337">Das folgende Beispiel zeigt, wie eine bestimmte Konversation überwacht wird, wenn sich der Initiator- und der Zieldienst auf unterschiedlichen Computern befinden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-337">The following example shows how to monitor a specific conversation where the initiator and target services are on separate computers.</span></span>  
  
```  
ssbdiagnose RUNTIME -ID D68D77A9-B1CF-41BF-A5CE-279ABCAB140D   
-TIMEOUT 10 CONNECT TO -E -S InitiatorComputer/InitiatorInstance   
-d InitiatorDatabase CONNECT TO -E -S TargetComputer/TargetInstance   
-d TargetDatabase  
```  
  
### <a name="h-monitor-the-status-of-a-conversation-in-two-databases-in-the-same-instance"></a><span data-ttu-id="2b23f-338">H.</span><span class="sxs-lookup"><span data-stu-id="2b23f-338">H.</span></span> <span data-ttu-id="2b23f-339">Überwachen des Status einer Konversation in zwei Datenbanken in der gleichen Instanz</span><span class="sxs-lookup"><span data-stu-id="2b23f-339">Monitor the status of a conversation in two databases in the same instance</span></span>  
 <span data-ttu-id="2b23f-340">Das folgende Beispiel zeigt, wie eine bestimmte Konversation überwacht wird, wenn sich der Initiator- und der Zieldienst in unterschiedlichen Datenbanken in der gleichen Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]befinden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-340">The following example shows how to monitor a specific conversation where the initiator and target services are in separate databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="2b23f-341">In diesem Beispiel wird **baseconnectionoptions** verwendet, um die Instanz und die Anmeldeinformationen anzugeben, und es werden zwei CONNECT TO-Klauseln zum Angeben der Datenbanken verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-341">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span> <span data-ttu-id="2b23f-342">-SHOWEVENTS wird angegeben, damit alle Laufzeitereignisse in der Berichtsausgabe enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="2b23f-342">-SHOWEVENTS is specified so that all runtime events are included in the report output.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME -SHOWEVENTS   
-ID 5094d4a7-e38c-4c37-da37-1d58b1cb8455 -TIMEOUT 10 CONNECT TO   
-d InitiatorDatabase CONNECT TO -d TargetDatabase  
```  
  
### <a name="i-monitor-the-status-of-two-conversations-between-two-databases"></a><span data-ttu-id="2b23f-343">I.</span><span class="sxs-lookup"><span data-stu-id="2b23f-343">I.</span></span> <span data-ttu-id="2b23f-344">Überwachen des Status von zwei Konversationen zwischen zwei Datenbanken</span><span class="sxs-lookup"><span data-stu-id="2b23f-344">Monitor the status of two conversations between two databases</span></span>  
 <span data-ttu-id="2b23f-345">Das folgende Beispiel zeigt, wie zwei Konversationen überwacht wenn, bei denen sich der Initiator- und der Zieldienst in unterschiedlichen Datenbanken in der gleichen Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]befinden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-345">The following example shows how to monitor two conversations where the initiator and target services are in separate databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="2b23f-346">In diesem Beispiel wird **baseconnectionoptions** verwendet, um die Instanz und die Anmeldeinformationen anzugeben, und es werden zwei CONNECT TO-Klauseln zum Angeben der Datenbanken verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-346">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME   
-ID 5094d4a7-e38c-4c37-da37-1d58b1cb8455   
-ID 9b293be9-226b-4e22-e169-1d2c2c15be86 -TIMEOUT 10 CONNECT TO   
-d InitiatorDatabase CONNECT TO -d TargetDatabase  
```  
  
### <a name="j-monitor-the-status-of-all-conversations-between-two-databases"></a><span data-ttu-id="2b23f-347">J.</span><span class="sxs-lookup"><span data-stu-id="2b23f-347">J.</span></span> <span data-ttu-id="2b23f-348">Überwachen des Status aller Konversationen zwischen zwei Datenbanken</span><span class="sxs-lookup"><span data-stu-id="2b23f-348">Monitor the status of all conversations between two databases</span></span>  
 <span data-ttu-id="2b23f-349">Das folgende Beispiel zeigt, wie alle Konversationen zwischen zwei Datenbanken in der gleichen Instanz von [!INCLUDE[ssDE](../../includes/ssde-md.md)]überwacht werden</span><span class="sxs-lookup"><span data-stu-id="2b23f-349">The following example shows how to monitor all the conversation between two databases in the same instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="2b23f-350">In diesem Beispiel wird **baseconnectionoptions** verwendet, um die Instanz und die Anmeldeinformationen anzugeben, und es werden zwei CONNECT TO-Klauseln zum Angeben der Datenbanken verwendet.</span><span class="sxs-lookup"><span data-stu-id="2b23f-350">The example uses the **baseconnectionoptions** to specify the instance and login information, and two CONNECT TO clauses to specify the databases.</span></span>  
  
```  
ssbdiagnose -E -S TestComputer/DevTestInstance RUNTIME   
-TIMEOUT 10 CONNECT TO -d InitiatorDatabase CONNECT TO   
-d TargetDatabase  
```  
  
### <a name="k-ignore-specific-errors"></a><span data-ttu-id="2b23f-351">K.</span><span class="sxs-lookup"><span data-stu-id="2b23f-351">K.</span></span> <span data-ttu-id="2b23f-352">Ignorieren bestimmter Fehler</span><span class="sxs-lookup"><span data-stu-id="2b23f-352">Ignore Specific Errors</span></span>  
 <span data-ttu-id="2b23f-353">Das folgende Beispiel zeigt, wie bekannte Fehler (303 und 304) in der aktuellen Konfiguration der Aktivierung in einem Testsystem ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-353">The following example shows how to ignore known errors (303 and 304) in how activation is currently configured in a test system.</span></span>  
  
```  
ssbdiagnose -IGNORE 303 -IGNORE 304 -E -d TestDatabase   
CONFIGURATION FROM SERVICE /test/initiator TO SERVICE /test/target   
ON CONTRACT TextContract  
```  
  
### <a name="l-redirecting-ssbdiagnose-xml-output"></a><span data-ttu-id="2b23f-354">L.</span><span class="sxs-lookup"><span data-stu-id="2b23f-354">L.</span></span> <span data-ttu-id="2b23f-355">Umleiten der XML-Ausgabe von ssbdiagnose</span><span class="sxs-lookup"><span data-stu-id="2b23f-355">Redirecting ssbdiagnose XML Output</span></span>  
 <span data-ttu-id="2b23f-356">Das folgende Beispiel zeigt, wie die Anforderung erstellt wird, dass die Ausgabe von **ssbdiagnose** als XML-Datei generiert werden soll, die in eine Datei umgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="2b23f-356">The following example shows how to request that **ssbdiagnose** generate its output as an XML file that is redirected to a file.</span></span> <span data-ttu-id="2b23f-357">Die Datei „TestDiag.xml“ kann dann von einer Anwendung geöffnet werden, um **ssbdiagnose** -XML-Dateien zu analysieren oder zu melden.</span><span class="sxs-lookup"><span data-stu-id="2b23f-357">The TestDiag.xml file can then be opened by an application to analyze or report **ssbdiagnose** XML files.</span></span> <span data-ttu-id="2b23f-358">Die Anzeige ist auch in einem allgemeinen XML-Editor wie XML Editor möglich.</span><span class="sxs-lookup"><span data-stu-id="2b23f-358">Or, you can view it from a general XML editor such as XML Notepad.</span></span>  
  
```  
ssbdiagnose -XML -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target > c:\MyDiagnostics\TestDiag.xml  
```  
  
### <a name="m-using-an-environment-variable"></a><span data-ttu-id="2b23f-359">M.</span><span class="sxs-lookup"><span data-stu-id="2b23f-359">M.</span></span> <span data-ttu-id="2b23f-360">Verwenden einer Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="2b23f-360">Using an Environment Variable</span></span>  
 <span data-ttu-id="2b23f-361">Im folgenden Beispiel wird zunächst die SQLCMDSERVER-Umgebungsvariable für den Servernamen festgelegt, und anschließend wird **ssbdiagnose** ohne Angabe von **-S**ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="2b23f-361">The following example first sets the SQLCMDSERVER environment variable to hold the server name, and then runs **ssbdiagnose** without specifying **-S**.</span></span>  
  
```  
SET SQLCMDSERVER=MyComputer  
ssbdiagnose -XML -E -d MyDatabase CONFIGURATION FROM SERVICE   
/test/initiator TO SERVICE /test/target  
```  
  
## <a name="see-also"></a><span data-ttu-id="2b23f-362">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2b23f-362">See Also</span></span>  
 <span data-ttu-id="2b23f-363">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span><span class="sxs-lookup"><span data-stu-id="2b23f-363">[SQL Server Service Broker](../../database-engine/configure-windows/sql-server-service-broker.md) </span></span>  
 <span data-ttu-id="2b23f-364">[BEGIN DIALOG CONVERSATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/begin-dialog-conversation-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b23f-364">[BEGIN DIALOG CONVERSATION &#40;Transact-SQL&#41;](/sql/t-sql/statements/begin-dialog-conversation-transact-sql) </span></span>  
 <span data-ttu-id="2b23f-365">[CREATE BROKER PRIORITY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-broker-priority-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b23f-365">[CREATE BROKER PRIORITY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-broker-priority-transact-sql) </span></span>  
 <span data-ttu-id="2b23f-366">[CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b23f-366">[CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql) </span></span>  
 <span data-ttu-id="2b23f-367">[CREATE CONTRACT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-contract-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b23f-367">[CREATE CONTRACT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-contract-transact-sql) </span></span>  
 <span data-ttu-id="2b23f-368">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b23f-368">[CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="2b23f-369">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b23f-369">[CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) </span></span>  
 <span data-ttu-id="2b23f-370">[CREATE MESSAGE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-message-type-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b23f-370">[CREATE MESSAGE TYPE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-message-type-transact-sql) </span></span>  
 <span data-ttu-id="2b23f-371">[CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b23f-371">[CREATE QUEUE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-queue-transact-sql) </span></span>  
 <span data-ttu-id="2b23f-372">[CREATE REMOTE SERVICE BINDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-remote-service-binding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b23f-372">[CREATE REMOTE SERVICE BINDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-remote-service-binding-transact-sql) </span></span>  
 <span data-ttu-id="2b23f-373">[CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b23f-373">[CREATE ROUTE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-route-transact-sql) </span></span>  
 <span data-ttu-id="2b23f-374">[CREATE SERVICE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-service-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b23f-374">[CREATE SERVICE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-service-transact-sql) </span></span>  
 <span data-ttu-id="2b23f-375">[RECEIVE &#40;Transact-SQL&#41;](/sql/t-sql/statements/receive-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b23f-375">[RECEIVE &#40;Transact-SQL&#41;](/sql/t-sql/statements/receive-transact-sql) </span></span>  
 <span data-ttu-id="2b23f-376">[sys.transmission_queue &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-transmission-queue-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b23f-376">[sys.transmission_queue &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-transmission-queue-transact-sql) </span></span>  
 <span data-ttu-id="2b23f-377">[sys.conversation_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-conversation-endpoints-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="2b23f-377">[sys.conversation_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-conversation-endpoints-transact-sql) </span></span>  
 [<span data-ttu-id="2b23f-378">sys.conversation_groups &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="2b23f-378">sys.conversation_groups &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-catalog-views/sys-conversation-groups-transact-sql)  
  
  
