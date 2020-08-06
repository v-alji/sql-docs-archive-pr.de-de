---
title: Klassen und Eigenschaften für den WMI-Anbieter für Server Ereignisse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- event classes [WMI]
- WMI Provider for Server Events, events listed
- classes [WMI]
ms.assetid: e2916cd7-a3ed-41e6-97b4-2ee060754cbe
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 471e77cb7afa4e6aed441dcbbc8b3b70064f6737
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723638"
---
# <a name="wmi-provider-for-server-events-classes-and-properties"></a><span data-ttu-id="45991-102">Klassen und Eigenschaften für den WMI-Anbieter für Serverereignisse</span><span class="sxs-lookup"><span data-stu-id="45991-102">WMI Provider for Server Events Classes and Properties</span></span>
  <span data-ttu-id="45991-103">Die folgenden Serverereignisse bilden das Programmiermodell für den WMI-Anbieter für Serverereignisse.</span><span class="sxs-lookup"><span data-stu-id="45991-103">The following server events make up the programming model for the WMI Provider for Server Events.</span></span> <span data-ttu-id="45991-104">Es gibt zwei Hauptkategorien von Ereignissen, die durch Absetzen von WQL-Abfragen an den Anbieter abgefragt werden können:</span><span class="sxs-lookup"><span data-stu-id="45991-104">There are two main categories of events that can be queried by issuing WQL queries against the provider.</span></span> <span data-ttu-id="45991-105">DDL-Ereignisse (Data Definition Language) und Ablaufverfolgungsereignisse.</span><span class="sxs-lookup"><span data-stu-id="45991-105">These are data definition language (DDL) events and trace events.</span></span> <span data-ttu-id="45991-106">Auch die Service Broker-Ereignisse QUEUE_ACTIVATION und BROKER_QUEUE_DISABLED können abgefragt werden.</span><span class="sxs-lookup"><span data-stu-id="45991-106">The QUEUE_ACTIVATION and BROKER_QUEUE_DISABLED service broker events can also be queried.</span></span> <span data-ttu-id="45991-107">Beachten Sie den inklusiven Charakter der folgenden Strukturdiagramme.</span><span class="sxs-lookup"><span data-stu-id="45991-107">Note the inclusive nature of the following tree diagrams.</span></span> <span data-ttu-id="45991-108">Das DDL_ASSEMBLY_EVENTS-Ereignis schließt z. B. beliebige Ereignisse vom Typ ALTER_ASSEMBLY, CREATE_ASSEMBLY und DROP_ASSEMBLY ein.</span><span class="sxs-lookup"><span data-stu-id="45991-108">The DDL_ASSEMBLY_EVENTS event, for example, includes any ALTER_ASSEMBLY, CREATE_ASSEMBLY, and DROP_ASSEMBLY event.</span></span> <span data-ttu-id="45991-109">Analog dazu schließt das TRC_FULL_TEXT-Ereignis beliebige Ereignisse vom Typ FT_CRAWL_ABORTED, FT_CRAWL_STARTED und FT_CRAWL_STOPPED ein.</span><span class="sxs-lookup"><span data-stu-id="45991-109">Similarly, the TRC_FULL_TEXT event includes any FT_CRAWL_ABORTED, FT_CRAWL_STARTED, and FT_CRAWL_STOPPED event.</span></span> <span data-ttu-id="45991-110">ALL_EVENTS deckt alle DDL-Ereignisse, Ablaufverfolgungsereignisse, QUEUE_ACTIVATION und BROKER_QUEUE_DISABLED ab.</span><span class="sxs-lookup"><span data-stu-id="45991-110">ALL_EVENTS covers all DDL events, trace events, QUEUE_ACTIVATION, and BROKER_QUEUE_DISABLED.</span></span>  
  
 <span data-ttu-id="45991-111">Um zu ermitteln, welche Eigenschaften aus einem Ereignis oder einer Ereignisgruppe abgefragt werden können, konsultieren Sie das Ereignisschema.</span><span class="sxs-lookup"><span data-stu-id="45991-111">To learn which properties can be queried from an event or event group, refer to the event schema.</span></span> <span data-ttu-id="45991-112">Standardmäßig wird das Ereignisschema im folgenden Verzeichnis installiert: [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)] Tools\Binn\schemas\sqlserver\2006\11\events\events .xsd.</span><span class="sxs-lookup"><span data-stu-id="45991-112">By default, the event schema is installed in the following directory: [!INCLUDE[ssInstallPath](../../includes/ssinstallpath-md.md)]Tools\Binn\schemas\sqlserver\2006\11\events\events.xsd.</span></span>  
  
 <span data-ttu-id="45991-113">Alternativ dazu können Sie auch auf das Ereignis Schema verweisen, das unter veröffentlicht wurde [https://schemas.microsoft.com/sqlserver](https://go.microsoft.com/fwlink/?linkid=43100) .</span><span class="sxs-lookup"><span data-stu-id="45991-113">Alternatively, you can refer to the event schema published at [https://schemas.microsoft.com/sqlserver](https://go.microsoft.com/fwlink/?linkid=43100).</span></span>  
  
 <span data-ttu-id="45991-114">Zum ALTER_DATABASE-Ereignis erfahren Sie beispielsweise, dass DDL_SERVER_LEVEL_EVENTS das übergeordnete Ereignis ist und seine Eigenschaften `TSQLCommand` und `DatabaseName` sind.</span><span class="sxs-lookup"><span data-stu-id="45991-114">For example, by referring to the ALTER_DATABASE event, you will learn that its parent event is DDL_SERVER_LEVEL_EVENTS and its properties are `TSQLCommand` and `DatabaseName`.</span></span> <span data-ttu-id="45991-115">Das Ereignis erbt auch die Eigenschaften `SQLInstance`, `PostTime`, `ComputerName`, `SPID` und `LoginName`.</span><span class="sxs-lookup"><span data-stu-id="45991-115">The event also inherits the properties `SQLInstance`, `PostTime`, `ComputerName`, `SPID`, and `LoginName`.</span></span> <span data-ttu-id="45991-116">Das Ereignis verfügt über keinen untergeordneten Ereignisse.</span><span class="sxs-lookup"><span data-stu-id="45991-116">The event has no children events.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="45991-117">Gespeicherte Systemprozeduren, die DDL-ähnliche Vorgänge ausführen, können auch Ereignisbenachrichtigungen auslösen.</span><span class="sxs-lookup"><span data-stu-id="45991-117">System stored procedures that perform DDL-like operations can also fire event notifications.</span></span> <span data-ttu-id="45991-118">Testen Sie die Ereignisbenachrichtigungen, um ihre Reaktion auf gespeicherte Systemprozeduren, die ausgeführt werden, zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="45991-118">Test your event notifications to determine their responses to system stored procedures that are run.</span></span> <span data-ttu-id="45991-119">Beispielsweise lösen die CREATE TYPE-Anweisung und die gespeicherte Prozedur **sp_addtype** eine Ereignis Benachrichtigung aus, die für ein CREATE_TYPE-Ereignis erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="45991-119">For example, the CREATE TYPE statement and **sp_addtype** stored procedure will both fire an event notification that is created on a CREATE_TYPE event.</span></span> <span data-ttu-id="45991-120">Weitere Informationen finden Sie unter[DDL-Ereignisse](../../relational-databases/triggers/ddl-events.md).</span><span class="sxs-lookup"><span data-stu-id="45991-120">For more information, see[DDL Events](../../relational-databases/triggers/ddl-events.md).</span></span>  
  
 <span data-ttu-id="45991-121">**Ereignisse und Ereignisgruppen der Datendefinitionssprache (DDL)**</span><span class="sxs-lookup"><span data-stu-id="45991-121">**Data Definition Language Events and Event Groups**</span></span>  
  
 <span data-ttu-id="45991-122">![WMI-Anbieter für Serverereignisse-Ereignisstruktur](../../../2014/database-engine/dev-guide/media/sql-wmi-ddl-events-ktm.gif "WMI-Anbieter für Serverereignisse-Ereignisstruktur")</span><span class="sxs-lookup"><span data-stu-id="45991-122">![WMI Provider for Server Events Event Tree](../../../2014/database-engine/dev-guide/media/sql-wmi-ddl-events-ktm.gif "WMI Provider for Server Events Event Tree")</span></span>  
  
 <span data-ttu-id="45991-123">**Ablaufverfolgungsereignisse und Ereignisgruppen**</span><span class="sxs-lookup"><span data-stu-id="45991-123">**Trace Events and Event Groups**</span></span>  
  
 <span data-ttu-id="45991-124">![Ablauf Verfolgungs Ereignisse und Ereignis Gruppen](../../../2014/database-engine/dev-guide/media/sql-wmi-trc-all-events.gif "Ablaufverfolgungsereignisse und -Ereignisgruppen")</span><span class="sxs-lookup"><span data-stu-id="45991-124">![Trace events and event groups](../../../2014/database-engine/dev-guide/media/sql-wmi-trc-all-events.gif "Trace events and event groups")</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45991-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="45991-125">See Also</span></span>  
 <span data-ttu-id="45991-126">[Konzepte des WMI-Anbieters für Server Ereignisse](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md) </span><span class="sxs-lookup"><span data-stu-id="45991-126">[WMI Provider for Server Events Concepts](../../relational-databases/wmi-provider-server-events/wmi-provider-for-server-events-concepts.md) </span></span>  
 [<span data-ttu-id="45991-127">Verwenden von WQL mit dem WMI-Anbieter für Serverereignisse</span><span class="sxs-lookup"><span data-stu-id="45991-127">Using WQL with the WMI Provider for Server Events</span></span>](../../relational-databases/wmi-provider-server-events/using-wql-with-the-wmi-provider-for-server-events.md)  
  
  
