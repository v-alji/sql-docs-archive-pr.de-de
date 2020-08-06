---
title: Ausführungs Merkmale erweiterter gespeicherter Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], executing
- executing extended stored procedures [SQL Server]
ms.assetid: 6fe1f7e8-cc02-49df-8a2a-d47a96ec3567
author: rothja
ms.author: jroth
ms.openlocfilehash: edbd73797699d65f694e91bc3035e0dc9366c9d4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609225"
---
# <a name="execution-characteristics-of-extended-stored-procedures"></a><span data-ttu-id="7e41b-102">Ausführungsmerkmale erweiterter gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="7e41b-102">Execution Characteristics of Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="7e41b-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="7e41b-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="7e41b-104">Die Ausführung einer erweiterten gespeicherten Prozedur weist folgende Merkmale auf:</span><span class="sxs-lookup"><span data-stu-id="7e41b-104">The execution of an extended stored procedure has these characteristics:</span></span>  
  
-   <span data-ttu-id="7e41b-105">Die Funktion der erweiterten gespeicherten Prozedur wird im Sicherheitskontext von ausgeführt [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="7e41b-105">The extended stored procedure function is executed under the security context of [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="7e41b-106">Die Funktion der erweiterten gespeicherten Prozedur wird im Prozessraum von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7e41b-106">The extended stored procedure function runs in the process space of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="7e41b-107">Der mit der Ausführung der erweiterten gespeicherten Prozedur verknüpfte Thread ist derselbe wie derjenige, der für die Clientverbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7e41b-107">The thread associated with the execution of the extended stored procedure is the same one used for the client connection.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="7e41b-108">Bevor der Systemadministrator die erweiterte gespeicherte Prozedur dem Server hinzufügt und Benutzern Berechtigungen zum Ausführen der Prozedur gewährt, sollte er die Prozedur gründlich überprüfen, um sicherzustellen, dass sie keinen schädlichen oder bösartigen Code enthält.</span><span class="sxs-lookup"><span data-stu-id="7e41b-108">Before adding extended stored procedures to the server and granting execute permissions to other users, the system administrator should thoroughly review each extended stored procedure to make sure that it does not contain harmful or malicious code.</span></span>  
  
-  
  
 <span data-ttu-id="7e41b-109">Nachdem die dll der erweiterten gespeicherten Prozedur geladen wurde, bleibt die dll in den Adressraum des Servers geladen, bis [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] beendet wird, oder der Administrator entlädt die dll explizit mithilfe von DBCC *DLL_Name* (Free).</span><span class="sxs-lookup"><span data-stu-id="7e41b-109">After the extended stored procedure DLL is loaded, the DLL remains loaded in the address space of the server until [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is stopped or the administrator explicitly unloads the DLL by using DBCC *DLL_name* (FREE).</span></span>  
  
 <span data-ttu-id="7e41b-110">Die erweiterte gespeicherte Prozedur kann in [!INCLUDE[tsql](../../includes/tsql-md.md)] mithilfe der EXECUTE-Anweisung als gespeicherte Prozedur ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="7e41b-110">The extended stored procedure can be executed from [!INCLUDE[tsql](../../includes/tsql-md.md)] as a stored procedure by using the EXECUTE statement:</span></span>  
  
```  
EXECUTE @retval = xp_extendedProcName @param1, @param2 OUTPUT  
```  
  
## <a name="parameters"></a><span data-ttu-id="7e41b-111">Parameter</span><span class="sxs-lookup"><span data-stu-id="7e41b-111">Parameters</span></span>  
 <span data-ttu-id="7e41b-112">\@ *retval*</span><span class="sxs-lookup"><span data-stu-id="7e41b-112">\@ *retval*</span></span>  
 <span data-ttu-id="7e41b-113">Ein Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="7e41b-113">Is a return value.</span></span>  
  
 <span data-ttu-id="7e41b-114">\@*param1*</span><span class="sxs-lookup"><span data-stu-id="7e41b-114">\@ *param1*</span></span>  
 <span data-ttu-id="7e41b-115">Ein Eingabeparameter.</span><span class="sxs-lookup"><span data-stu-id="7e41b-115">Is an input parameter.</span></span>  
  
 <span data-ttu-id="7e41b-116">\@*Param2*</span><span class="sxs-lookup"><span data-stu-id="7e41b-116">\@ *param2*</span></span>  
 <span data-ttu-id="7e41b-117">Ein Eingabe-/Ausgabeparameter.</span><span class="sxs-lookup"><span data-stu-id="7e41b-117">Is an input/output parameter.</span></span>  
  
> [!CAUTION]  
>  <span data-ttu-id="7e41b-118">Erweiterte gespeicherte Prozeduren bieten Leistungssteigerungen und erweitern die Funktionalität von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e41b-118">Extended stored procedures offer performance enhancements and extend [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functionality.</span></span> <span data-ttu-id="7e41b-119">Da die DLLs der erweiterten gespeicherten Prozeduren und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] jedoch denselben Adressraum nutzen, kann sich eine problematische Prozedur negativ auf die Funktionsweise von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] auswirken.</span><span class="sxs-lookup"><span data-stu-id="7e41b-119">However, because the extended stored procedure DLL and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] share the same address space, a problem procedure can adversely affect [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] functioning.</span></span> <span data-ttu-id="7e41b-120">Von DLLs erweiterter gespeicherter Prozeduren ausgelöste Ausnahmen werden zwar von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] behandelt; es ist jedoch trotzdem möglich, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Datenbereiche beschädigt werden.</span><span class="sxs-lookup"><span data-stu-id="7e41b-120">Although exceptions thrown by the extended stored procedure DLL are handled by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], it is possible to damage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data areas.</span></span> <span data-ttu-id="7e41b-121">Als Sicherheitsvorkehrung können nur [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Systemadministratoren erweiterte gespeicherte Prozeduren zu [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7e41b-121">As a security precaution, only [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrators can add extended stored procedures to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="7e41b-122">Diese Prozeduren sollten vor der Installation gründlich getestet werden.</span><span class="sxs-lookup"><span data-stu-id="7e41b-122">These procedures should be thoroughly tested before they are installed.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7e41b-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7e41b-123">See Also</span></span>  
 <span data-ttu-id="7e41b-124">[Programmierung von erweiterten gespeicherten Prozeduren](database-engine-extended-stored-procedures-programming.md) </span><span class="sxs-lookup"><span data-stu-id="7e41b-124">[Programming Extended Stored Procedures](database-engine-extended-stored-procedures-programming.md) </span></span>  
 [<span data-ttu-id="7e41b-125">Abfragen von in SQL Server installierten erweiterten gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="7e41b-125">Querying Extended Stored Procedures Installed in SQL Server</span></span>](querying-extended-stored-procedures-installed-in-sql-server.md)  
  
  
