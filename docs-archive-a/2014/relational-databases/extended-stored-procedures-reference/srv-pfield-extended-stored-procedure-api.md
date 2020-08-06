---
title: srv_pfield (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_pfield
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_pfield
ms.assetid: a61e4c1f-e65b-48ea-a7d1-3e1544af389d
author: rothja
ms.author: jroth
ms.openlocfilehash: 90680d59dbf36ad3f713fd7a09d07553890a8668
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725801"
---
# <a name="srv_pfield-extended-stored-procedure-api"></a><span data-ttu-id="029fc-102">srv_pfield (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="029fc-102">srv_pfield (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="029fc-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="029fc-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="029fc-104">Gibt Informationen zur Datenbankverbindung zurück.</span><span class="sxs-lookup"><span data-stu-id="029fc-104">Returns information about a database connection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="029fc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="029fc-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_pfield (  
SRV_PROC *  
srvproc  
,  
int   
field  
,  
int *  
len  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="029fc-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="029fc-106">Arguments</span></span>  
 <span data-ttu-id="029fc-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="029fc-107">*srvproc*</span></span>  
 <span data-ttu-id="029fc-108">Zeiger, der eine Datenbankverbindung identifiziert</span><span class="sxs-lookup"><span data-stu-id="029fc-108">Pointer identifying a database connection.</span></span>  
  
 <span data-ttu-id="029fc-109">*Flächen*</span><span class="sxs-lookup"><span data-stu-id="029fc-109">*field*</span></span>  
 <span data-ttu-id="029fc-110">Gibt Daten über die Verbindung zur Rückgabe an.</span><span class="sxs-lookup"><span data-stu-id="029fc-110">Specifies data on the connection to return.</span></span>  
  
|<span data-ttu-id="029fc-111">Wert</span><span class="sxs-lookup"><span data-stu-id="029fc-111">Value</span></span>|<span data-ttu-id="029fc-112">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="029fc-112">Returns</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="029fc-113">SRV_APPLNAME</span><span class="sxs-lookup"><span data-stu-id="029fc-113">SRV_APPLNAME</span></span>|<span data-ttu-id="029fc-114">Der vom Client beim Herstellen der Verbindung bereitgestellte Anwendungsname.</span><span class="sxs-lookup"><span data-stu-id="029fc-114">The application name provided by the client when it established the connection.</span></span>|  
|<span data-ttu-id="029fc-115">SRV_BCPFLAG</span><span class="sxs-lookup"><span data-stu-id="029fc-115">SRV_BCPFLAG</span></span>|<span data-ttu-id="029fc-116">Ein Flag, das TRUE ist, wenn sich der Client auf einen Massenkopiervorgang vorbereitet; andernfalls FALSE.</span><span class="sxs-lookup"><span data-stu-id="029fc-116">A flag that is TRUE if the client is preparing for a bulk copy operation; otherwise, FALSE.</span></span>|  
|<span data-ttu-id="029fc-117">SRV_CLIB</span><span class="sxs-lookup"><span data-stu-id="029fc-117">SRV_CLIB</span></span>|<span data-ttu-id="029fc-118">Der Name der Bibliothek, die dem Client ermöglicht, mit einem Server zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="029fc-118">The name of the library that enables the client to talk to a server.</span></span>|  
|<span data-ttu-id="029fc-119">SRV_CPID</span><span class="sxs-lookup"><span data-stu-id="029fc-119">SRV_CPID</span></span>|<span data-ttu-id="029fc-120">Die Client-Prozess-ID auf dem Client-Quellcomputer.</span><span class="sxs-lookup"><span data-stu-id="029fc-120">The client process ID on the client source computer.</span></span>|  
|<span data-ttu-id="029fc-121">SRV_HOST</span><span class="sxs-lookup"><span data-stu-id="029fc-121">SRV_HOST</span></span>|<span data-ttu-id="029fc-122">Der vom Client beim Herstellen der Verbindung bereitgestellte Name des Clientcomputers.</span><span class="sxs-lookup"><span data-stu-id="029fc-122">The name of the client's machine provided by the client when it established the connection.</span></span>|  
|<span data-ttu-id="029fc-123">SRV_LIBVERS</span><span class="sxs-lookup"><span data-stu-id="029fc-123">SRV_LIBVERS</span></span>|<span data-ttu-id="029fc-124">Die Version der Clientbibliothek.</span><span class="sxs-lookup"><span data-stu-id="029fc-124">The version of the client library.</span></span>|  
|<span data-ttu-id="029fc-125">SRV_LSECURE</span><span class="sxs-lookup"><span data-stu-id="029fc-125">SRV_LSECURE</span></span>|<span data-ttu-id="029fc-126">Ein Flag.</span><span class="sxs-lookup"><span data-stu-id="029fc-126">A flag.</span></span> <span data-ttu-id="029fc-127">TRUE, wenn die Verbindung integrierte Sicherheit zur Anmeldung verwendet hat.</span><span class="sxs-lookup"><span data-stu-id="029fc-127">TRUE if the connection used integrated security to login.</span></span>|  
|<span data-ttu-id="029fc-128">SRV_NETWORK_MODULE</span><span class="sxs-lookup"><span data-stu-id="029fc-128">SRV_NETWORK_MODULE</span></span>|<span data-ttu-id="029fc-129">Der Name der von der Verbindung verwendeten Netzwerkbibliotheks-DLL.</span><span class="sxs-lookup"><span data-stu-id="029fc-129">The name of the Net-Library DLL used by the connection.</span></span>|  
|<span data-ttu-id="029fc-130">SRV_NETWORK_VERSION</span><span class="sxs-lookup"><span data-stu-id="029fc-130">SRV_NETWORK_VERSION</span></span>|<span data-ttu-id="029fc-131">Die Version der von der Verbindung verwendeten Netzwerkbibliotheks-DLL.</span><span class="sxs-lookup"><span data-stu-id="029fc-131">The version of the Net-Library DLL used by the connection.</span></span>|  
|<span data-ttu-id="029fc-132">SRV_NETWORK_CONNECTION</span><span class="sxs-lookup"><span data-stu-id="029fc-132">SRV_NETWORK_CONNECTION</span></span>|<span data-ttu-id="029fc-133">Die Verbindungszeichenfolge, die an die Net-Library-DLL für die aktuelle *srvproc*-Verbindung übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="029fc-133">The connection string passed to the Net-Library DLL used for the current *srvproc* connection.</span></span>|  
|<span data-ttu-id="029fc-134">SRV_PIPEHANDLE</span><span class="sxs-lookup"><span data-stu-id="029fc-134">SRV_PIPEHANDLE</span></span>|<span data-ttu-id="029fc-135">Zeichenfolge, die das Pipehandle eines verbundenen Client enthält, oder NULL, falls der Client mit einem Netzwerk verbunden ist, das keine Named Pipes verwendet.</span><span class="sxs-lookup"><span data-stu-id="029fc-135">A string containing the pipe handle of a connected client, or NULL if the client is connected on a network that does not use named pipes.</span></span> <span data-ttu-id="029fc-136">Um dieses Handle als gültiges Pipehandle mit [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows zu verwenden, wandeln Sie die Zeichenfolge in eine Ganzzahl um.</span><span class="sxs-lookup"><span data-stu-id="029fc-136">To use this handle as a valid pipe handle with [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows, convert this string to an integer.</span></span>|  
|<span data-ttu-id="029fc-137">SRV_RMTSERVER</span><span class="sxs-lookup"><span data-stu-id="029fc-137">SRV_RMTSERVER</span></span>|<span data-ttu-id="029fc-138">Der Server, von dem der Clientprozess angemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="029fc-138">The server from which the client process is logged in.</span></span> <span data-ttu-id="029fc-139">Wenn die Anmeldung von einem Client stammt, ist dieser Wert eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="029fc-139">If the login is from a client, this value is an empty string.</span></span>|  
|<span data-ttu-id="029fc-140">SRV_ROWSENT</span><span class="sxs-lookup"><span data-stu-id="029fc-140">SRV_ROWSENT</span></span>|<span data-ttu-id="029fc-141">Die Anzahl von Zeilen, die bereits von *srvproc* für die aktuellen Ergebnisse gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="029fc-141">The number of rows already sent by *srvproc* for the current set of results.</span></span>|  
|<span data-ttu-id="029fc-142">SRV_SPID</span><span class="sxs-lookup"><span data-stu-id="029fc-142">SRV_SPID</span></span>|<span data-ttu-id="029fc-143">Serverthread-ID von *srvproc*.</span><span class="sxs-lookup"><span data-stu-id="029fc-143">The server thread ID of the *srvproc*.</span></span> <span data-ttu-id="029fc-144">Für erweiterte gespeicherte Prozeduren ist dieser Wert identisch mit der **kpid**-Spalte von **sys.sysprocesses** und kann sich im Laufe der Zeit ändern.</span><span class="sxs-lookup"><span data-stu-id="029fc-144">For extended stored procedures, this value is the same as the **kpid** column of **sys.sysprocesses**, and it can change over time.</span></span>|  
|<span data-ttu-id="029fc-145">SRV_SPROC_CODEPAGE</span><span class="sxs-lookup"><span data-stu-id="029fc-145">SRV_SPROC_CODEPAGE</span></span>|<span data-ttu-id="029fc-146">Codepage, die der Server verwendet, um Multibytedaten zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="029fc-146">Codepage that the server uses to interpret multbyte data.</span></span>|  
|<span data-ttu-id="029fc-147">SRV_STATUS</span><span class="sxs-lookup"><span data-stu-id="029fc-147">SRV_STATUS</span></span>|<span data-ttu-id="029fc-148">Aktueller Status von *srvproc*: wird ausgeführt oder wurde beendet</span><span class="sxs-lookup"><span data-stu-id="029fc-148">The current status of *srvproc*: running or closed</span></span>|  
|<span data-ttu-id="029fc-149">SRV_TYPE</span><span class="sxs-lookup"><span data-stu-id="029fc-149">SRV_TYPE</span></span>|<span data-ttu-id="029fc-150">Verbindungstyp von *srvproc*.</span><span class="sxs-lookup"><span data-stu-id="029fc-150">The connection type of *srvproc*.</span></span> <span data-ttu-id="029fc-151">Wenn ein Server zurückgegeben wird, ist *srvproc* von einer Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="029fc-151">If server is returned, *srvproc* is from an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="029fc-152">Wenn ein Client zurückgegeben wird, stammt *srvproc* von einer DB-Bibliothek oder einem ODBC-Client.</span><span class="sxs-lookup"><span data-stu-id="029fc-152">If client is returned, *srvproc* is from a DB-Library or ODBC client.</span></span>|  
|<span data-ttu-id="029fc-153">SRV_USER</span><span class="sxs-lookup"><span data-stu-id="029fc-153">SRV_USER</span></span>|<span data-ttu-id="029fc-154">Der Benutzername der Verbindung.</span><span class="sxs-lookup"><span data-stu-id="029fc-154">The user name of the connection.</span></span>|  
|||  
  
 <span data-ttu-id="029fc-155">*Nest*</span><span class="sxs-lookup"><span data-stu-id="029fc-155">*len*</span></span>  
 <span data-ttu-id="029fc-156">Zeiger auf eine **int**-Variable, die die Länge des zurückgegebenen *field*-Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="029fc-156">Is a pointer to an **int** variable that contains the length of the returned *field* value.</span></span> <span data-ttu-id="029fc-157">Wenn *len* NULL ist, wird die Länge der Zeichenfolge nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="029fc-157">If *len* is NULL, the length of the string is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="029fc-158">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="029fc-158">Returns</span></span>  
 <span data-ttu-id="029fc-159">Zeiger auf eine auf NULL endende Zeichenfolge, die den aktuellen Wert für das in der SRV_PROC-Struktur angegebene Feld enthält.</span><span class="sxs-lookup"><span data-stu-id="029fc-159">A pointer to a null-terminated string containing the current value for the specified field in the SRV_PROC structure.</span></span> <span data-ttu-id="029fc-160">Wenn das Feld leer ist, wird ein gültiger Zeiger auf eine leere Zeichenfolge zurückgegeben, und *len* enthält den Wert 0.</span><span class="sxs-lookup"><span data-stu-id="029fc-160">If the field is empty, a valid pointer to an empty string is returned and *len* contains 0.</span></span> <span data-ttu-id="029fc-161">Wenn das Feld unbekannt ist, wird NULL zurückgegeben, und *len* enthält den Wert –1.</span><span class="sxs-lookup"><span data-stu-id="029fc-161">If the field is unknown, NULL is returned and *len* contains the value -1.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="029fc-162">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="029fc-162">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="029fc-163">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie im [Security Developer Center](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="029fc-163">For information about security review and testing, see the [Security Developer Center](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
