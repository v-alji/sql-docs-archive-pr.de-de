---
title: Verwenden von SQL Server erweiterten Ereignissen (xevents) zum Überwachen von Analysis Services | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b57cc2fe-52dc-4fa9-8554-5a866e25c6d7
author: minewiskan
ms.author: owend
ms.openlocfilehash: 9d12d9bc8d6a56702e1b44f8404b25681a1033f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620036"
---
# <a name="use-sql-server-extended-events-xevents-to-monitor-analysis-services"></a><span data-ttu-id="64fcf-102">Verwenden von erweiterten Ereignissen von SQL Server (XEvents) zum Überwachen von Analysis Services</span><span class="sxs-lookup"><span data-stu-id="64fcf-102">Use SQL Server Extended Events (XEvents) to Monitor Analysis Services</span></span>
  <span data-ttu-id="64fcf-103">Analysis Services bietet Ablauf Verfolgungs Funktionen durch die Verwendung von [erweiterten Ereignissen](../../relational-databases/extended-events/extended-events.md).</span><span class="sxs-lookup"><span data-stu-id="64fcf-103">Analysis Services provides tracing capabilities through the usage of [Extended Events](../../relational-databases/extended-events/extended-events.md).</span></span>  
  
 <span data-ttu-id="64fcf-104">Erweiterte Ereignisse ist eine Ereignisinfrastruktur, die für Serversysteme stark skalierbar und konfigurierbar ist.</span><span class="sxs-lookup"><span data-stu-id="64fcf-104">Extended Events is an event infrastructure that is highly scalable and configurable for server systems.</span></span> <span data-ttu-id="64fcf-105">Erweiterte Ereignisse ist ein Lightweight-Leistungsüberwachungssystem, das sehr wenige Leistungsressourcen verwendet.</span><span class="sxs-lookup"><span data-stu-id="64fcf-105">Extended Events is a light weight performance monitoring system that uses very few performance resources.</span></span>  
  
 <span data-ttu-id="64fcf-106">Alle Analysis Services Ereignisse können aufgezeichnet und für bestimmte Consumer, die in [erweiterten Ereignissen](../../relational-databases/extended-events/extended-events.md)definiert sind, mithilfe von xevents als Ziel festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="64fcf-106">All Analysis Services events can be captured and target to specific consumers, as defined in [Extended Events](../../relational-databases/extended-events/extended-events.md), through XEvents.</span></span>  
  
## <a name="initiating-extended-events-in-analysis-services"></a><span data-ttu-id="64fcf-107">Initiieren von Erweiterte Ereignisse in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="64fcf-107">Initiating Extended Events in Analysis Services</span></span>  
 <span data-ttu-id="64fcf-108">Die Erweiterte Ereignis-Ablaufverfolgung wird mit einem ähnlichen XMLA-Skriptbefehl zum Erstellen eines Objekts wie unten dargestellt aktiviert:</span><span class="sxs-lookup"><span data-stu-id="64fcf-108">Extended Event tracing is enabled using a similar XMLA create object script command as shown below:</span></span>  
  
```  
<Execute ...>  
   <Command>  
      <Batch ...>  
         <Create ...>  
            <ObjectDefinition>  
               <Trace>  
                  <ID>trace_id</ID>  
                  <Name>trace_name</Name>  
                  <ddl300_300:XEvent>  
                     <event_session ...>  
                        <event package="AS" name="AS_event">  
                           <action package="PACKAGE0" .../>  
                        </event>  
                        <target package="PACKAGE0" name="asynchronous_file_target">  
                           <parameter name="filename" value="data_filename.xel"/>  
                           <parameter name="metadatafile" value="metadata_filename.xem"/>  
                        </target>  
                     </event_session>  
                  </ddl300_300:XEvent>  
               </Trace>  
            </ObjectDefinition>  
         </Create>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 <span data-ttu-id="64fcf-109">Dabei sind die folgenden Elemente abhängig von den Ablaufverfolgungsanforderungen vom Benutzer zu definieren:</span><span class="sxs-lookup"><span data-stu-id="64fcf-109">Where the following elements are to be defined by the user, depending on the tracing needs:</span></span>  
  
 <span data-ttu-id="64fcf-110">*trace_id*</span><span class="sxs-lookup"><span data-stu-id="64fcf-110">*trace_id*</span></span>  
 <span data-ttu-id="64fcf-111">Definiert den eindeutigen Bezeichner für diese Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="64fcf-111">Defines the unique identifier for this trace.</span></span>  
  
 <span data-ttu-id="64fcf-112">*trace_name*</span><span class="sxs-lookup"><span data-stu-id="64fcf-112">*trace_name*</span></span>  
 <span data-ttu-id="64fcf-113">Der Name dieser Ablaufverfolgung, normalerweise eine lesbare Beschreibung der Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="64fcf-113">The name given to this trace; usually a human readable definition of the trace.</span></span> <span data-ttu-id="64fcf-114">Üblicherweise wird der *trace_id* -Wert als Name verwendet.</span><span class="sxs-lookup"><span data-stu-id="64fcf-114">It is a common practice to use the *trace_id* value as the name.</span></span>  
  
 <span data-ttu-id="64fcf-115">*AS_event*</span><span class="sxs-lookup"><span data-stu-id="64fcf-115">*AS_event*</span></span>  
 <span data-ttu-id="64fcf-116">Das Analysis Services-Ereignis, das verfügbar gemacht werden soll.</span><span class="sxs-lookup"><span data-stu-id="64fcf-116">The Analysis Services event to be exposed.</span></span> <span data-ttu-id="64fcf-117">Die Namen der Ereignisse finden Sie unter [Analysis Services-Ablaufverfolgungsereignisse](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events) .</span><span class="sxs-lookup"><span data-stu-id="64fcf-117">See [Analysis Services Trace Events](https://docs.microsoft.com/bi-reference/trace-events/analysis-services-trace-events) for names of the events.</span></span>  
  
 <span data-ttu-id="64fcf-118">*data_filename*</span><span class="sxs-lookup"><span data-stu-id="64fcf-118">*data_filename*</span></span>  
 <span data-ttu-id="64fcf-119">Der Name der Datei, die die Ereignisdaten enthält.</span><span class="sxs-lookup"><span data-stu-id="64fcf-119">The name of the file that contains the events data.</span></span> <span data-ttu-id="64fcf-120">Für diesen Namen wird ein Zeitstempel als Suffix verwendet, um das Überschreiben von Daten zu vermeiden, wenn die Ablaufverfolgung fortlaufend gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="64fcf-120">This name is suffixed with a time stamp to avoid data overwriting if the trace is sent over and over.</span></span>  
  
 <span data-ttu-id="64fcf-121">*metadata_filename*</span><span class="sxs-lookup"><span data-stu-id="64fcf-121">*metadata_filename*</span></span>  
 <span data-ttu-id="64fcf-122">Der Name der Datei, die die Ereignismetadaten enthält.</span><span class="sxs-lookup"><span data-stu-id="64fcf-122">The name of the file that contains the events metadata.</span></span> <span data-ttu-id="64fcf-123">Für diesen Namen wird ein Zeitstempel als Suffix verwendet, um das Überschreiben von Daten zu vermeiden, wenn die Ablaufverfolgung fortlaufend gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="64fcf-123">This name is suffixed with a time stamp to avoid data overwriting if the trace is sent over and over.</span></span>  
  
## <a name="stopping-extended-events-in-analysis-services"></a><span data-ttu-id="64fcf-124">Beenden von Erweiterte Ereignisse in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="64fcf-124">Stopping Extended Events in Analysis Services</span></span>  
 <span data-ttu-id="64fcf-125">Um das Erweiterte Ereignisse-Ablaufverfolgungsobjekt zu beenden, müssen Sie dieses Objekt mit einem ähnlichen XMLA-Skriptbefehl zum Löschen eines Objekts wie unten dargestellt löschen:</span><span class="sxs-lookup"><span data-stu-id="64fcf-125">To stop the Extended Events tracing object you need to delete that object using a similar XMLA delete object script command as shown below:</span></span>  
  
```  
<Execute xmlns="urn:schemas-microsoft-com:xml-analysis">  
   <Command>  
      <Batch ...>  
         <Delete ...>  
            <Object>  
               <TraceID>trace_id</TraceID>  
            </Object>  
         </Delete>  
      </Batch>  
   </Command>  
   <Properties></Properties>  
</Execute>  
  
```  
  
 <span data-ttu-id="64fcf-126">Dabei sind die folgenden Elemente abhängig von den Ablaufverfolgungsanforderungen vom Benutzer zu definieren:</span><span class="sxs-lookup"><span data-stu-id="64fcf-126">Where the following elements are to be defined by the user, depending on the tracing needs:</span></span>  
  
 <span data-ttu-id="64fcf-127">*trace_id*</span><span class="sxs-lookup"><span data-stu-id="64fcf-127">*trace_id*</span></span>  
 <span data-ttu-id="64fcf-128">Definiert den eindeutigen Bezeichner für die zu löschende Ablaufverfolgung.</span><span class="sxs-lookup"><span data-stu-id="64fcf-128">Defines the unique identifier for the trace to be deleted.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64fcf-129">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="64fcf-129">See Also</span></span>  
 [<span data-ttu-id="64fcf-130">Erweiterte Ereignisse</span><span class="sxs-lookup"><span data-stu-id="64fcf-130">Extended Events</span></span>](../../relational-databases/extended-events/extended-events.md)  
  
  
