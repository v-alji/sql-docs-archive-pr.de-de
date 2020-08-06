---
title: Zugreifen auf Diagnoseinformationen im Protokoll der erweiterten Ereignisse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: aaa180c2-5e1a-4534-a125-507c647186ab
author: rothja
ms.author: jroth
ms.openlocfilehash: 5148683d464f06e8a4f52cc924baaacac9102b12
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698108"
---
# <a name="accessing-diagnostic-information-in-the-extended-events-log"></a><span data-ttu-id="befb2-102">Zugreifen auf Diagnoseinformationen im Protokoll der erweiterten Ereignisse</span><span class="sxs-lookup"><span data-stu-id="befb2-102">Accessing Diagnostic Information in the Extended Events Log</span></span>
  <span data-ttu-id="befb2-103">Ab [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]wurden der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client und die Datenzugriffs-Ablaufverfolgung ([Datenzugriffs-Ablaufverfolgung](https://go.microsoft.com/fwlink/?LinkId=125805)) aktualisiert, um das Abrufen von Diagnoseinformationen über Verbindungsfehler vom Verbindungsringpuffer sowie von Informationen zur Anwendungsleistung aus dem Protokoll für erweiterte Ereignisse zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="befb2-103">Beginning in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and data access tracing ([Data Access Tracing](https://go.microsoft.com/fwlink/?LinkId=125805)) have been updated to make it easier to get diagnostic information about connection failures from the connectivity ring buffer and application performance information from the extended events log.</span></span>  
  
 <span data-ttu-id="befb2-104">Informationen dazu, wie Sie das Protokoll für erweiterte Ereignisse lesen, finden Sie unter [View Event Session Data](../../../database-engine/view-event-session-data.md).</span><span class="sxs-lookup"><span data-stu-id="befb2-104">For information about reading the extended events log, see [View Event Session Data](../../../database-engine/view-event-session-data.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="befb2-105">Diese Funktion ist nur für Problembehandlung und Diagnosezwecke vorgesehen und ist möglicherweise nicht geeignet zu Überwachungs oder Sicherheitszwecken.</span><span class="sxs-lookup"><span data-stu-id="befb2-105">This feature is intended only for troubleshooting and diagnostic purposes and may not be suitable for auditing or security purposes.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="befb2-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="befb2-106">Remarks</span></span>  
 <span data-ttu-id="befb2-107">Für Verbindungsvorgänge sendet der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client eine Clientverbindungs-ID.</span><span class="sxs-lookup"><span data-stu-id="befb2-107">For connection operations, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client will send a client connection ID.</span></span> <span data-ttu-id="befb2-108">Wenn die Verbindung nicht hergestellt werden kann, können Sie auf den konnektivitätsringpuffer zugreifen ([Problembehandlung bei der Konnektivität in SQL Server 2008 mit dem konnektivitätsringpuffer](https://go.microsoft.com/fwlink/?LinkId=207752)), das `ClientConnectionID` Feld Suchen und Diagnoseinformationen zum Verbindungsfehler abrufen.</span><span class="sxs-lookup"><span data-stu-id="befb2-108">If the connection fails, you can access the connectivity ring buffer ([Connectivity troubleshooting in SQL Server 2008 with the Connectivity Ring Buffer](https://go.microsoft.com/fwlink/?LinkId=207752)) and find the `ClientConnectionID` field and get diagnostic information about the connection failure.</span></span> <span data-ttu-id="befb2-109">Clientverbindungs-IDs werden nur im Ringpuffer protokolliert, wenn ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="befb2-109">Client connection IDs are logged in the ring buffer only if an error occurs.</span></span> <span data-ttu-id="befb2-110">(Wenn vor dem Senden des prelogin-Pakets keine Verbindung hergestellt werden kann, wird keine Clientverbindungs-ID generiert.) Die Clientverbindungs-ID ist eine 16-Byte-GUID.</span><span class="sxs-lookup"><span data-stu-id="befb2-110">(If a connection fails before sending the prelogin packet, a client connection ID will not be generated.) The client connection ID is a 16-byte GUID.</span></span> <span data-ttu-id="befb2-111">Sie können auch die Clientverbindungs-ID im erweiterten Ereignisse-Ausgabeziel suchen, wenn Ereignissen in einer Sitzung für erweiterte Ereignisse die `client_connection_id`-Aktion hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="befb2-111">You can also find the client connection ID in the extended events output target, if the `client_connection_id` action is added to events in an extended events session.</span></span> <span data-ttu-id="befb2-112">Sie können die Datenzugriffs-Ablaufverfolgung aktivieren, den Verbindungsbefehl erneut ausführen und das `ClientConnectionID`-Feld in der Datenzugriffs-Ablaufverfolgung für einen fehlgeschlagenen Vorgang beobachten, wenn Sie weitere Hilfe bei der Diagnose benötigen.</span><span class="sxs-lookup"><span data-stu-id="befb2-112">You can enable data access tracing and rerun the connection command and observe the `ClientConnectionID` field in the data access trace for a failed operation, if you need further diagnostic assistance.</span></span>  
  
 <span data-ttu-id="befb2-113">Wenn Sie ODBC in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client verwenden und eine Verbindung erfolgreich ist, können Sie die Clientverbindungs-ID mithilfe des- `SQL_COPT_SS_CLIENT_CONNECTION_ID` Attributs mit [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md)erhalten.</span><span class="sxs-lookup"><span data-stu-id="befb2-113">If you are using ODBC in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client and a connection succeeds, you can get the client connection ID by using the `SQL_COPT_SS_CLIENT_CONNECTION_ID` attribute with [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md).</span></span>  
  
 [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="befb2-114">Native Client sendet auch eine Thread-spezifische Aktivitäts-ID.</span><span class="sxs-lookup"><span data-stu-id="befb2-114">Native Client also sends a thread-specific activity ID.</span></span> <span data-ttu-id="befb2-115">Die Aktivitäts-ID wird in den Sitzungen für erweiterte Ereignisse aufgezeichnet, wenn die Sitzungen bei aktivierter TRACK_CAUSAILITY-Option gestartet werden.</span><span class="sxs-lookup"><span data-stu-id="befb2-115">The activity ID is captured in the extended events sessions if the sessions are started with the TRACK_CAUSAILITY option enabled.</span></span> <span data-ttu-id="befb2-116">Bei Leistungsproblemen mit einer aktiven Verbindung können Sie die Aktivitäts-ID aus der Datenzugriffs-Ablaufverfolgung des Clients abrufen (`ActivityID`-Feld) und dann die Aktivitäts-ID in der Ausgabe für die erweiterten Ereignisse suchen.</span><span class="sxs-lookup"><span data-stu-id="befb2-116">For performance issues with an active connection, you can get the activity ID from the client's data access trace (`ActivityID` field) and then locate the activity ID in the extended events output.</span></span> <span data-ttu-id="befb2-117">Die Aktivitäts-ID in den erweiterten Ereignissen ist eine 16-Byte-GUID (nicht dieselbe wie die GUID für die Clientverbindungs-ID), der eine Vier-Byte-Sequenznummer angefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="befb2-117">The activity ID in the extended events is a 16-byte GUID (not the same as the GUID for the client connection ID) appended with a four-byte sequence number.</span></span> <span data-ttu-id="befb2-118">Die Sequenznummer steht für die Reihenfolge einer Anforderung innerhalb eines Threads und gibt die relative Reihenfolge des Batches und der RPC-Anweisungen für den Thread an.</span><span class="sxs-lookup"><span data-stu-id="befb2-118">The sequence number represents the order of a request within a thread and indicates the relative ordering of batch and RPC statements for the thread.</span></span> <span data-ttu-id="befb2-119">Der `ActivityID` wird optional für SQL-Batchanweisungen und RPC-Anforderungen gesendet, wenn die Datenzugriffsablaufverfolgung aktiviert und das 18. Bit im Datenzugriffs-Ablaufverfolgungs-Konfigurationswort auf ON gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="befb2-119">The `ActivityID` is optionally sent for SQL batch statements and RPC requests when data access tracing is enabled on and the 18th bit in the data access tracing configuration word is turned ON.</span></span>  
  
 <span data-ttu-id="befb2-120">Im folgenden Beispiel wird [!INCLUDE[tsql](../../../includes/tsql-md.md)] zum Starten einer Sitzung für erweiterte Ereignisse verwendet, die in einem Ringpuffer gespeichert werden und die von einem Client in RPC- und Batch-Vorgängen gesendete Aktivitäts-ID aufzeichnen.</span><span class="sxs-lookup"><span data-stu-id="befb2-120">The following is a sample that uses [!INCLUDE[tsql](../../../includes/tsql-md.md)] to start an extended events session that will be stored in a ring buffer and will record the activity ID sent from a client on RPC and batch operations.</span></span>  
  
```  
create event session MySession on server   
add event connectivity_ring_buffer_recorded,   
add event sql_statement_starting (action (client_connection_id)),   
add event sql_statement_completed (action (client_connection_id)),   
add event rpc_starting (action (client_connection_id)),   
add event rpc_completed (action (client_connection_id))  
add target ring_buffer with (track_causality=on)  
  
```  
  
## <a name="control-file"></a><span data-ttu-id="befb2-121">Steuerelementdatei</span><span class="sxs-lookup"><span data-stu-id="befb2-121">Control File</span></span>  
 <span data-ttu-id="befb2-122">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]ist der Inhalt der SQL Server Native Client-Steuerelementdatei (ctrl.guid.snac11):</span><span class="sxs-lookup"><span data-stu-id="befb2-122">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the contents of the SQL Server Native  Client control file (ctrl.guid.snac11) is:</span></span>  
  
```  
{8B98D3F2-3CC6-0B9C-6651-9649CCE5C752}  0x00000000  0   MSDADIAG.ETW  
{2DA81B52-908E-7DB6-EF81-76856BB47C4F}  0xFFFFFFFF  0   SQLNCLI11.1  
```  
  
## <a name="mof-file"></a><span data-ttu-id="befb2-123">MOF-Datei</span><span class="sxs-lookup"><span data-stu-id="befb2-123">MOF File</span></span>  
 <span data-ttu-id="befb2-124">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]ist der Inhalt der SQL Server Native Client-MOF-Datei:</span><span class="sxs-lookup"><span data-stu-id="befb2-124">In [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], the contents of the SQL Server Native  Client mof file is:</span></span>  
  
```  
#pragma classflags("forceupdate")  
#pragma namespace ("\\\\.\\Root\\WMI")  
  
/////////////////////////////////////////////////////////////////////////////  
//  
//  MSDADIAG.ETW  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW"),  
 Guid("{8B98D3F2-3CC6-0B9C-6651-9649CCE5C752}"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW : EventTrace  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW"),  
 Guid("{8B98D3F3-3CC6-0B9C-6651-9649CCE5C752}"),  
 DisplayName("msdadiag"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace : Bid2Etw_MSDADIAG_ETW  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW formatted output (A)"),  
 EventType(17),  
 EventTypeName("TextA"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace_TextA : Bid2Etw_MSDADIAG_ETW_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringA"),  
     extension("RString"),  
     read  
    ]  
    object msgStr;  
};  
  
[  
 dynamic: ToInstance,  
 Description("MSDADIAG.ETW formatted output (W)"),  
 EventType(18),  
 EventTypeName("TextW"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_MSDADIAG_ETW_Trace_TextW : Bid2Etw_MSDADIAG_ETW_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringW"),  
     extension("RWString"),  
     read  
    ]  
    object msgStr;  
};  
  
/////////////////////////////////////////////////////////////////////////////  
//  
//  SQLNCLI11.1  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1"),  
 Guid("{2DA81B52-908E-7DB6-EF81-76856BB47C4F}"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1 : EventTrace  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1"),  
 Guid("{2DA81B53-908E-7DB6-EF81-76856BB47C4F}"),  
 DisplayName("SQLNCLI11.1"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace : Bid2Etw_SQLNCLI11_1  
{  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1 formatted output (A)"),  
 EventType(17),  
 EventTypeName("TextA"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace_TextA : Bid2Etw_SQLNCLI11_1_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringA"),  
     extension("RString"),  
     read  
    ]  
    object msgStr;  
};  
  
[  
 dynamic: ToInstance,  
 Description("SQLNCLI11.1 formatted output (W)"),  
 EventType(18),  
 EventTypeName("TextW"),  
 locale("MS\\0x409")  
]  
class Bid2Etw_SQLNCLI11_1_Trace_TextW : Bid2Etw_SQLNCLI11_1_Trace  
{  
    [  
     WmiDataId(1),  
     Description("Module ID"),  
     read  
    ]  
    uint32 ModID;  
  
    [  
     WmiDataId(2),  
     Description("Text StringW"),  
     extension("RWString"),  
     read  
    ]  
    object msgStr;  
};  
```  
  
## <a name="see-also"></a><span data-ttu-id="befb2-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="befb2-125">See Also</span></span>  
 [<span data-ttu-id="befb2-126">Behandlung von Fehlern und Meldungen</span><span class="sxs-lookup"><span data-stu-id="befb2-126">Handling Errors and Messages</span></span>](../../native-client-odbc-error-messages/handling-errors-and-messages.md)  
  
  
