---
title: Hinzufügen einer erweiterten gespeicherten Prozedur zu SQL Server | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- extended stored procedures [SQL Server], adding
- adding extended stored procedures
- collations [SQL Server], extended stored procedures
ms.assetid: 10f1bb74-3b43-4efd-b7ab-7a85a8600a50
author: rothja
ms.author: jroth
ms.openlocfilehash: 03ac8c2a0fa9ce77db59d50b3a7b9da42415e013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620397"
---
# <a name="adding-an-extended-stored-procedure-to-sql-server"></a><span data-ttu-id="142a1-102">Hinzufügen einer erweiterten gespeicherten Prozedur zu SQL Server</span><span class="sxs-lookup"><span data-stu-id="142a1-102">Adding an Extended Stored Procedure to SQL Server</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="142a1-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="142a1-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="142a1-104">Eine DLL, die erweiterte gespeicherte Prozedurfunktionen enthält, stellt eine Erweiterung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dar.</span><span class="sxs-lookup"><span data-stu-id="142a1-104">A DLL that contains extended stored procedure functions acts as an extension to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="142a1-105">Um die dll zu installieren, kopieren Sie die Datei in ein Verzeichnis, z. b. das Verzeichnis, das die dll-Standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Dateien enthält (c:\Programme\Microsoft SQL server\mssql12.0.\* x\*\MSSQL\Binn standardmäßig).</span><span class="sxs-lookup"><span data-stu-id="142a1-105">To install the DLL, copy the file to a directory, such as the one that contains the standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] DLL files (C:\Program Files\Microsoft SQL Server\MSSQL12.0.*x*\MSSQL\Binn by default).</span></span>  
  
 <span data-ttu-id="142a1-106">Nachdem die DLL mit der erweiterten gespeicherten Prozedur auf den Server kopiert wurde, muss ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Systemadministrator jede Funktion der in der DLL enthaltenen erweiterten gespeicherten Prozedur in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registrieren.</span><span class="sxs-lookup"><span data-stu-id="142a1-106">After the extended stored procedure DLL has been copied to the server, a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] system administrator must register to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] each extended stored procedure function in the DLL.</span></span> <span data-ttu-id="142a1-107">Hierzu wird die gespeicherte Systemprozedur sp_addextendedproc verwendet.</span><span class="sxs-lookup"><span data-stu-id="142a1-107">This is done using the sp_addextendedproc system stored procedure.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="142a1-108">Der Systemadministrator muss die erweiterte gespeicherte Prozedur sorgfältig überprüfen, um sicherzustellen, dass sie keinen schädlichen oder bösartigen Code enthält, bevor er sie dem Server hinzufügt und anderen Benutzern Berechtigungen zum Ausführen der Prozedur gewährt.</span><span class="sxs-lookup"><span data-stu-id="142a1-108">The system administrator should thoroughly review an extended stored procedure to ensure that it does not contain harmful or malicious code before adding it to the server and granting execute permissions to other users.</span></span>  <span data-ttu-id="142a1-109">Überprüfen Sie alle Benutzereingaben.</span><span class="sxs-lookup"><span data-stu-id="142a1-109">Validate all user input.</span></span> <span data-ttu-id="142a1-110">Verketten Sie Benutzereingaben nicht, bevor Sie Sie überprüfen.</span><span class="sxs-lookup"><span data-stu-id="142a1-110">Do not concatenate user input before validating it.</span></span> <span data-ttu-id="142a1-111">Führen Sie niemals Befehle aus, die sich aus nicht überprüften Benutzereingaben zusammensetzen.</span><span class="sxs-lookup"><span data-stu-id="142a1-111">Never execute a command constructed from unvalidated user input.</span></span>  
  
 <span data-ttu-id="142a1-112">Der erste Parameter namens sp_addextendedproc gibt den Namen der Funktion an, und der zweite Parameter gibt den Namen der DLL an, in der sich die Funktion befindet.</span><span class="sxs-lookup"><span data-stu-id="142a1-112">The first parameter of sp_addextendedproc specifies the name of the function, and the second parameter specifies the name of the DLL in which that function resides.</span></span> <span data-ttu-id="142a1-113">Es ist empfehlenswert, den vollständigen Pfad der DLL anzugeben.</span><span class="sxs-lookup"><span data-stu-id="142a1-113">It is recommended that you specify the complete path of the DLL.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="142a1-114">Vorhandene DLLs, die nicht mit einem vollständigen Pfad registriert wurden, sind nach dem Upgrade auf SQL Server 2005 oder höher nicht mehr funktionsfähig.</span><span class="sxs-lookup"><span data-stu-id="142a1-114">Existing DLLs that were not registered with a complete path will not work after upgrading to SQL Server 2005 or later.</span></span> <span data-ttu-id="142a1-115">Verwenden Sie zum Beheben des Problems sp_dropextendedproc, um die Registrierung der DLL aufzuheben. Registrieren Sie sie dann mit sp_addextendedproc unter Angabe des vollständigen Pfades erneut.</span><span class="sxs-lookup"><span data-stu-id="142a1-115">To correct the problem, use sp_dropextendedproc to unregister the DLL, and then reregister it with sp_addextendedproc, specifying the complete path.</span></span>  
  
 <span data-ttu-id="142a1-116">Der Name der im `sp_addextendedproc`-Parameter angegebenen Funktion muss genau (einschließlich Groß-/Kleinschreibung) dem Funktionsnamen in der DLL entsprechen.</span><span class="sxs-lookup"><span data-stu-id="142a1-116">The name of the function specified in `sp_addextendedproc` must be exactly the same, including the case, as the function's name in the DLL.</span></span> <span data-ttu-id="142a1-117">Zum Beispiel wird mit dem folgenden Befehl die Funktion `xp_hello,`, die sich in der DLL mit dem Namen `xp_hello.dll` befindet, als erweiterte gespeicherte [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Prozedur registriert:</span><span class="sxs-lookup"><span data-stu-id="142a1-117">For example, this command registers a function `xp_hello,` located in a dll named `xp_hello.dll`, as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extended stored procedure:</span></span>  
  
```  
sp_addextendedproc 'xp_hello', 'c:\Program Files\Microsoft SQL Server\MSSQL12.0.MSSQLSERVER\MSSQL\Binn\xp_hello.dll';  
```  
  
 <span data-ttu-id="142a1-118">Entspricht der in `sp_addextendedproc` angegebene Funktionsname nicht genau dem Funktionsnamen in der DLL, dann wird der neue Name in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] registriert, kann jedoch nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="142a1-118">If the name of the function specified in `sp_addextendedproc` does not exactly match the function name in the DLL, the new name will be registered in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], but the name will not be usable.</span></span> <span data-ttu-id="142a1-119">Obwohl beispielsweise `xp_Hello` als [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Erweiterte gespeicherte Prozedur in registriert ist `xp_hello.dll` , [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] kann die Funktion in der dll nicht finden, wenn Sie verwenden, `xp_Hello` um die Funktion zu einem späteren Zeitpunkt aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="142a1-119">For example, although `xp_Hello` is registered as a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] extended stored procedure located in `xp_hello.dll`, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not be able to find the function in the DLL if you use `xp_Hello` to call the function later.</span></span>  
  
```  
--Register the function (xp_hello) with an initial upper case  
sp_addextendedproc 'xp_Hello', 'c:\xp_hello.dll';  
  
--Use the newly registered name to call the function  
DECLARE @txt varchar(33);  
EXEC xp_Hello @txt OUTPUT;  
  
--This is the error message  
Server: Msg 17750, Level 16, State 1, Procedure xp_Hello, Line 1  
Could not load the DLL xp_hello.dll, or one of the DLLs it references. Reason: 127(The specified procedure could not be found.).  
```  
  
 <span data-ttu-id="142a1-120">Wenn der in `sp_addextendedproc` angegebene Funktionsname genau dem Funktionsnamen in der DLL entspricht, und die in der Sortierung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] nicht zwischen Groß- und Kleinschreibung unterschieden wird, dann kann der Benutzer die erweiterte gespeicherte Prozedur unter Angabe des Namens aufrufen, wobei dieser beliebige Kombinationen von Klein- und Großbuchstaben enthalten kann.</span><span class="sxs-lookup"><span data-stu-id="142a1-120">If the name of the function specified in `sp_addextendedproc` matches exactly the function name in the DLL, and the collation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is case-insensitive, the user can call the extended stored procedure using any combination of lower- and upper-case letters of the name.</span></span>  
  
```  
--Register the function (xp_hello)  
sp_addextendedproc 'xp_hello', 'c:\xp_hello.dll';  
  
--The following will succeed in calling xp_hello  
DECLARE @txt varchar(33);  
EXEC xp_Hello @txt OUTPUT;  
  
DECLARE @txt varchar(33);  
EXEC xp_HelLO @txt OUTPUT;  
  
DECLARE @txt varchar(33);  
EXEC xp_HELLO @txt OUTPUT;  
```  
  
 <span data-ttu-id="142a1-121">Wenn die Sortierung von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zwischen Groß- und Kleinschreibung unterscheidet, dann kann [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] die erweiterte gespeicherte Prozedur nicht aufrufen, wenn sich die Groß-/Kleinschreibung des Namens im Aufruf vom registrierten Namen unterscheidet. Dies gilt auch dann, wenn die Prozedur mit dem gleichen Namen und der gleichen Sortierung wie die Funktion in der DLL registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="142a1-121">When the collation of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance is case-sensitive, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] will not be able to call the extended stored procedure -- even if it was registered with exactly the same name and collation as the function in the DLL -- if the procedure is called with a different case.</span></span>  
  
```  
--Register the function (xp_hello)  
sp_addextendedproc 'xp_hello', 'c:\xp_hello.dll';  
  
--The following will result in an error  
DECLARE @txt varchar(33);  
EXEC xp_HELLO @txt OUTPUT;  
  
--This is the error  
Server: Msg 2812, Level 16, State 62, Line 1  
```  
  
 <span data-ttu-id="142a1-122">Es ist nicht notwendig, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] zu beenden und neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="142a1-122">It is not necessary to stop and restart [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="142a1-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="142a1-123">See Also</span></span>  
 <span data-ttu-id="142a1-124">[sp_addextendedproc &#40;Transact-SQL-&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="142a1-124">[sp_addextendedproc &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-addextendedproc-transact-sql) </span></span>  
 [<span data-ttu-id="142a1-125">sp_dropextendedproc &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="142a1-125">sp_dropextendedproc &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-dropextendedproc-transact-sql)  
  
  
