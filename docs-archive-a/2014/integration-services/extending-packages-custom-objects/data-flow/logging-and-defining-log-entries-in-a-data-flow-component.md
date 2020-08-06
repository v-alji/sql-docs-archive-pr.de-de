---
title: Protokollieren und Definieren von Protokolleinträgen in einer Datenflusskomponente | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
helpviewer_keywords:
- logs [Integration Services], custom
- custom log entries [Integration Services]
- custom data flow components [Integration Services], logging
- data flow components [Integration Services], logging
ms.assetid: 2190dba9-59b5-480b-b8e9-21d5a54c5917
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 14dfec71679bbe455ae8be5face98b776a80b9e1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697001"
---
# <a name="logging-and-defining-log-entries-in-a-data-flow-component"></a><span data-ttu-id="a8f62-102">Protokollieren und Definieren von Protokolleinträgen in einer Datenflusskomponente</span><span class="sxs-lookup"><span data-stu-id="a8f62-102">Logging and Defining Log Entries in a Data Flow Component</span></span>
  <span data-ttu-id="a8f62-103">Benutzerdefinierte Datenflusskomponenten können mithilfe der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.PostLogMessage%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>-Schnittstelle Nachrichten an einen vorhandenen Protokolleintrag senden.</span><span class="sxs-lookup"><span data-stu-id="a8f62-103">Custom data flow components can post messages to an existing log entry by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.PostLogMessage%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="a8f62-104">Darüber hinaus können sie auch mithilfe der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A>-Methode oder ähnlichen Methoden der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100>-Schnittstelle Informationen für den Benutzer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a8f62-104">They can also present information to the user by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.FireInformation%2A> method or similar methods of the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100> interface.</span></span> <span data-ttu-id="a8f62-105">Bei dieser Vorgehensweise entsteht jedoch durch das Auslösen und Behandeln zusätzlicher Ereignisse Arbeitsaufwand, und die Benutzer sind dazu gezwungen, ausführliche Informationsmeldungen zu durchsuchen, um schließlich zu den für sie relevanten Nachrichten zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="a8f62-105">However, this approach incurs the overhead of raising and handling additional events, and forces the user to sift through verbose informational messages for the messages that may be of interest to them.</span></span> <span data-ttu-id="a8f62-106">Um für die Benutzer Ihrer Komponente benutzerdefinierte Protokollinformationen mit einer eindeutigen Bezeichnung bereitzustellen, können Sie, wie nachstehend beschrieben, einen benutzerdefinierten Protokolleintrag verwenden.</span><span class="sxs-lookup"><span data-stu-id="a8f62-106">You can use a custom log entry as described below to provide distinctly labeled custom log information to users of your component.</span></span>  
  
## <a name="registering-and-using-a-custom-log-entry"></a><span data-ttu-id="a8f62-107">Registrieren und Verwenden eines benutzerdefinierten Protokolleintrags</span><span class="sxs-lookup"><span data-stu-id="a8f62-107">Registering and Using a Custom Log Entry</span></span>  
  
### <a name="registering-a-custom-log-entry"></a><span data-ttu-id="a8f62-108">Registrieren eines benutzerdefinierten Protokolleintrags</span><span class="sxs-lookup"><span data-stu-id="a8f62-108">Registering a Custom Log Entry</span></span>  
 <span data-ttu-id="a8f62-109">Um einen benutzerdefinierten Protokolleintrag für die Verwendung durch Ihre Komponente zu registrieren, überschreiben Sie die <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterLogEntries%2A>-Methode der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent>-Basisklasse.</span><span class="sxs-lookup"><span data-stu-id="a8f62-109">To register a custom log entry for use by your component, override the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.RegisterLogEntries%2A> method of the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent> base class.</span></span> <span data-ttu-id="a8f62-110">Im folgenden Beispiel wird ein benutzerdefinierter Protokolleintrag registriert und ein Name sowie eine Beschreibung bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="a8f62-110">The following example registers a custom log entry and provides a name and description.</span></span>  
  
```csharp  
using Microsoft.SqlServer.Dts.Runtime;  
...  
private const string MyLogEntryName = "My Custom Component Log Entry";  
private const string MyLogEntryDescription = "Log entry from My Custom Component ";  
...  
    public override void RegisterLogEntries()  
    {  
      this.LogEntryInfos.Add(MyLogEntryName,  
        MyLogEntryDescription,  
        Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT);  
    }  
```  
  
```vb  
Imports Microsoft.SqlServer.Dts.Runtime  
...  
Private Const MyLogEntryName As String = "My Custom Component Log Entry"   
Private Const MyLogEntryDescription As String = "Log entry from My Custom Component "  
...  
Public  Overrides Sub RegisterLogEntries()   
  Me.LogEntryInfos.Add(MyLogEntryName, _  
    MyLogEntryDescription, _  
    Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT)   
End Sub  
```  
  
 <span data-ttu-id="a8f62-111">Die <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency>-Enumeration stellt einen Hinweis für die Laufzeit bereit, wie häufig das Ereignis protokolliert wird:</span><span class="sxs-lookup"><span data-stu-id="a8f62-111">The <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency> enumeration provides a hint to the runtime about how frequently the event will be logged:</span></span>  
  
-   <span data-ttu-id="a8f62-112"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_OCCASIONAL>: Ereignis wird nur manchmal protokolliert, nicht während jeder Ausführung.</span><span class="sxs-lookup"><span data-stu-id="a8f62-112"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_OCCASIONAL>: Event is logged only sometimes, not during every execution.</span></span>  
  
-   <span data-ttu-id="a8f62-113"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT>: Ereignis wird während jeder Ausführung mit konstanter Häufigkeit protokolliert.</span><span class="sxs-lookup"><span data-stu-id="a8f62-113"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT>: Event is logged a constant number of times during every execution.</span></span>  
  
-   <span data-ttu-id="a8f62-114"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_PROPORTIONAL>: Ereignis wird mit einer zur fertiggestellten Menge der Arbeit proportionalen Häufigkeit protokolliert.</span><span class="sxs-lookup"><span data-stu-id="a8f62-114"><xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_PROPORTIONAL>: Event is logged a number of times proportional to the amount of work completed.</span></span>  
  
 <span data-ttu-id="a8f62-115">Das oben stehende Beispiel verwendet <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT>, da die Komponente erwartet, jeweils einen Eintrag pro Ausführung zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="a8f62-115">The example above uses <xref:Microsoft.SqlServer.Dts.Runtime.Wrapper.DTSLogEntryFrequency.DTSLEF_CONSISTENT> because the component expects to log an entry once per execution.</span></span>  
  
 <span data-ttu-id="a8f62-116">Nach der Registrierung des benutzerdefinierten Protokolleintrags und dem Hinzufügen einer Instanz Ihrer benutzerdefinierten Komponente zur Oberfläche des Datenfluss-Designers zeigt das Dialogfeld **Protokollierung** im Designer einen neuen Protokolleintrag mit dem Namen „My Custom Component Log Entry“ (Protokolleintrag meiner benutzerdefinierten Komponente) in der Liste der verfügbaren Protokolleinträge an.</span><span class="sxs-lookup"><span data-stu-id="a8f62-116">After registering the custom log entry and adding an instance of your custom component to the data flow designer surface, the **Logging** dialog box in the designer displays a new log entry with the name "My Custom Component Log Entry" in the list of available log entries.</span></span>  
  
### <a name="logging-to-a-custom-log-entry"></a><span data-ttu-id="a8f62-117">Protokollieren eines benutzerdefinierten Protokolleintrags</span><span class="sxs-lookup"><span data-stu-id="a8f62-117">Logging to a Custom Log Entry</span></span>  
 <span data-ttu-id="a8f62-118">Nach der Registrierung des benutzerdefinierten Protokolleintrags kann die Komponente jetzt benutzerdefinierte Meldungen protokollieren.</span><span class="sxs-lookup"><span data-stu-id="a8f62-118">After registering the custom log entry, the component can now log custom messages.</span></span> <span data-ttu-id="a8f62-119">Das folgende Beispiel schreibt während der <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A>-Methode, die den Text einer von der Komponente verwendeten SQL-Anweisung enthält, einen benutzerdefinierten Protokolleintrag.</span><span class="sxs-lookup"><span data-stu-id="a8f62-119">The example below writes a custom log entry during the <xref:Microsoft.SqlServer.Dts.Pipeline.PipelineComponent.PreExecute%2A> method that contains the text of a SQL statement used by the component.</span></span>  
  
```csharp  
public override void PreExecute()  
{  
  DateTime now = DateTime.Now;  
  byte[] additionalData = null;  
  this.ComponentMetaData.PostLogMessage(MyLogEntryName,  
    this.ComponentMetaData.Name,  
    "Command Sent was: " + myCommand.CommandText,  
    now, now, 0, ref additionalData);  
}  
```  
  
```vb  
Public  Overrides Sub PreExecute()   
  Dim now As DateTime = DateTime.Now   
  Dim additionalData As Byte() = Nothing   
  Me.ComponentMetaData.PostLogMessage(MyLogEntryName, _  
    Me.ComponentMetaData.Name, _  
    "Command Sent was: " + myCommand.CommandText, _  
    now, now, 0, additionalData)   
End Sub  
```  
  
 <span data-ttu-id="a8f62-120">Wenn der Benutzer jetzt das Paket nach Auswählen von „My Custom Component Log Entry“ (Protokolleintrag meiner benutzerdefinierten Komponente) im Dialogfeld **Protokollierung** ausführt, dann enthält das Protokoll einen Eintrag, der eindeutig mit „User::My Custom Component Log Entry“ (Benutzer::Protokolleintrag meiner benutzerdefinierten Komponente) gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="a8f62-120">Now when the user executes the package, after selecting the "My Custom Component Log Entry" in the **Logging** dialog box, the log will contain an entry clearly labeled as "User::My Custom Component Log Entry."</span></span> <span data-ttu-id="a8f62-121">Dieses neue Protokoll enthält den Text der SQL-Anweisung, den Zeitstempel und alle zusätzlichen Daten, die vom Entwickler protokolliert wurden.</span><span class="sxs-lookup"><span data-stu-id="a8f62-121">This new log entry contains the text of the SQL statement, the timestamp, and any additional data logged by the developer.</span></span>  
  
<span data-ttu-id="a8f62-122">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="a8f62-122">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="a8f62-123">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="a8f62-123">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="a8f62-124">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="a8f62-124">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="a8f62-125">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a8f62-125">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f62-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a8f62-126">See Also</span></span>  
 [<span data-ttu-id="a8f62-127">Integration Services-Protokollierung &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="a8f62-127">Integration Services &#40;SSIS&#41; Logging</span></span>](../../performance/integration-services-ssis-logging.md)  
  
  
