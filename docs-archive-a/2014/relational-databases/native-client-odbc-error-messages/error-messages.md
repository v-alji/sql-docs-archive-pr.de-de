---
title: Fehlermeldungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, errors
- messages [ODBC], types
- ODBC error handling, message types
- errors [ODBC], types
ms.assetid: 46c0c22e-d105-4d5b-bb9d-5694472e8651
author: rothja
ms.author: jroth
ms.openlocfilehash: d004ba320b50896b6f57c5de335d7f7b3d33e87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87722777"
---
# <a name="error-messages"></a><span data-ttu-id="095e0-102">Fehlermeldungen</span><span class="sxs-lookup"><span data-stu-id="095e0-102">Error Messages</span></span>
  <span data-ttu-id="095e0-103">Der Text der Nachrichten, die vom Native Client-ODBC-Treiber zurückgegeben werden, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] wird im *MessageText* -Parameter von **SQLGetDiagRec**abgelegt.</span><span class="sxs-lookup"><span data-stu-id="095e0-103">The text of messages returned by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver is placed in the *MessageText* parameter of **SQLGetDiagRec**.</span></span> <span data-ttu-id="095e0-104">Die Quelle eines Fehlers wird im Header der Meldung angegeben:</span><span class="sxs-lookup"><span data-stu-id="095e0-104">The source of an error is indicated by the header of the message:</span></span>  
  
 <span data-ttu-id="095e0-105">[Microsoft][ODBC-Treiber-Manager]</span><span class="sxs-lookup"><span data-stu-id="095e0-105">[Microsoft][ODBC Driver Manager]</span></span>  
 <span data-ttu-id="095e0-106">Diese Fehler werden vom ODBC-Treiber-Manager ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="095e0-106">These errors are raised by the ODBC Driver Manager.</span></span>  
  
 <span data-ttu-id="095e0-107">[Microsoft][ODBC-Cursorbibliothek]</span><span class="sxs-lookup"><span data-stu-id="095e0-107">[Microsoft][ODBC Cursor Library]</span></span>  
 <span data-ttu-id="095e0-108">Diese Fehler werden von der ODBC-Cursorbibliothek ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="095e0-108">These errors are raised by the ODBC cursor library.</span></span>  
  
 <span data-ttu-id="095e0-109">[Microsoft][SQL Server Native Client]</span><span class="sxs-lookup"><span data-stu-id="095e0-109">[Microsoft][SQL Server Native Client]</span></span>  
 <span data-ttu-id="095e0-110">Diese Fehler werden vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client-ODBC-Treiber ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="095e0-110">These errors are raised by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span> <span data-ttu-id="095e0-111">Wenn keine anderen Knoten entweder mit den Namen einer Netzwerkbibliothek oder [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] vorhanden sind, trat der Fehler im Treiber auf.</span><span class="sxs-lookup"><span data-stu-id="095e0-111">If there are no other nodes with either the name of a Net-Library or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], then the error was encountered in the driver.</span></span>  
  
 <span data-ttu-id="095e0-112">Microsoft [SQL Server Native Client] [*Net-TransportName*]</span><span class="sxs-lookup"><span data-stu-id="095e0-112">[Microsoft][SQL Server Native Client][*Net-Transportname*]</span></span>  
 <span data-ttu-id="095e0-113">Diese Fehler werden von der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Netzwerk Bibliothek ausgelöst, wobei *net-TransportName* der Anzeige Name eines [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Client Netzwerk Transports (z. b. Named Pipes, Shared Memory, TCP/IP Sockets oder via) ist.</span><span class="sxs-lookup"><span data-stu-id="095e0-113">These errors are raised by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Net-Library, where *Net-Transportname* is the display name of a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client network transport (for example, Named Pipes, Shared Memory, TCP/IP Sockets, or VIA).</span></span> <span data-ttu-id="095e0-114">Die restliche Fehlermeldung enthält die aufgerufene Netzwerkbibliotheksfunktion und die von der TDS-Funktion in der zugrunde liegenden Netzwerk-API aufgerufene Funktion.</span><span class="sxs-lookup"><span data-stu-id="095e0-114">The remainder of the error message contains the Net-Library function called and the function called in the underlying network API by the TDS function.</span></span> <span data-ttu-id="095e0-115">Der mit diesen Fehlern zurückgegebene *pfNative* -Fehlercode ist der Fehlercode aus dem zugrunde liegenden Netzwerkprotokoll Stapel.</span><span class="sxs-lookup"><span data-stu-id="095e0-115">The *pfNative* error code returned with these errors is the error code from the underlying network protocol stack.</span></span>  
  
 <span data-ttu-id="095e0-116">[Microsoft][SQL Server Native Client][[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]</span><span class="sxs-lookup"><span data-stu-id="095e0-116">[Microsoft][SQL Server Native Client][[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]]</span></span>  
 <span data-ttu-id="095e0-117">Diese Fehler werden von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="095e0-117">These errors are raised by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="095e0-118">Die übrige Fehlermeldung entspricht dem Text der Fehlermeldung aus [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="095e0-118">The remainder of the error message is the text of the error message from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="095e0-119">Der mit diesen Fehlern zurückgegebene *pfNative* Code ist die Fehlernummer von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="095e0-119">The *pfNative* code returned with these errors is the error number from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="095e0-120">Weitere Informationen zu einer Liste von Fehlermeldungen (und deren Zahlen), die von zurückgegeben werden können, finden Sie in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] den Spalten "Description" und "Error" der **sysmmeages** -Systemtabelle in der **Master** -Datenbank in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="095e0-120">For more information about a list of error messages (and their numbers) that can be returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see the description and error columns of the **sysmessages** system table in the **master** database in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="095e0-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="095e0-121">See Also</span></span>  
 [<span data-ttu-id="095e0-122">Behandlung von Fehlern und Meldungen</span><span class="sxs-lookup"><span data-stu-id="095e0-122">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
