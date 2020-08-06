---
title: Erstellen von erweiterten gespeicherten Prozeduren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
helpviewer_keywords:
- warnings [SQL Server]
- extended stored procedures [SQL Server], debugging
- extended stored procedures [SQL Server], creating
- messages [SQL Server], extended stored procedures
ms.assetid: 9f7c0cdb-6d88-44c0-b049-29953ae75717
author: rothja
ms.author: jroth
ms.openlocfilehash: d243b27b8542ec5fe10d795de1729d6c1fe484c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620395"
---
# <a name="creating-extended-stored-procedures"></a><span data-ttu-id="6297a-102">Erstellen erweiterter gespeicherter Prozeduren</span><span class="sxs-lookup"><span data-stu-id="6297a-102">Creating Extended Stored Procedures</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="6297a-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="6297a-103">Use CLR Integration instead.</span></span>  
  
 <span data-ttu-id="6297a-104">Eine erweiterte gespeicherte Prozedur ist eine Funktion mit einem Prototyp:</span><span class="sxs-lookup"><span data-stu-id="6297a-104">An extended stored procedure is a function with a prototype:</span></span>  
  
 <span data-ttu-id="6297a-105">Srvretcode *xp_extendedProcName* **(** srvproc \*\* \* );\*\*</span><span class="sxs-lookup"><span data-stu-id="6297a-105">SRVRETCODE *xp_extendedProcName* **(** SRVPROC **\*);**</span></span>  
  
 <span data-ttu-id="6297a-106">Die Verwendung des Präfix xp_ ist optional.</span><span class="sxs-lookup"><span data-stu-id="6297a-106">Using the prefix xp_ is optional.</span></span> <span data-ttu-id="6297a-107">Bei den Namen erweiterter gespeicherter Prozeduren wird die Groß-/Kleinschreibung beachtet, wenn in [!INCLUDE[tsql](../../includes/tsql-md.md)]-Anweisungen auf sie verwiesen wird, und zwar unabhängig von der auf dem Server installierten Codepage/Sortierreihenfolge.</span><span class="sxs-lookup"><span data-stu-id="6297a-107">Extended stored procedure names are case sensitive when referenced in [!INCLUDE[tsql](../../includes/tsql-md.md)] statements, regardless of code page/sort order installed on the server.</span></span> <span data-ttu-id="6297a-108">Wenn Sie eine DLL erstellen:</span><span class="sxs-lookup"><span data-stu-id="6297a-108">When you build a DLL:</span></span>  
  
-   <span data-ttu-id="6297a-109">Wenn ein Einstiegspunkt erforderlich ist, schreiben Sie eine DllMain-Funktion.</span><span class="sxs-lookup"><span data-stu-id="6297a-109">If an entry point is necessary, write a DllMain function.</span></span>  
  
     <span data-ttu-id="6297a-110">Diese Funktion ist optional; wenn Sie sie nicht im Quellcode angeben, erstellt der Compiler einen Link zu seiner eigenen Version, die keine Aktionen ausführt, außer TRUE zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="6297a-110">This function is optional; if you do not provide it in source code, the compiler links its own version, which does nothing but return TRUE.</span></span> <span data-ttu-id="6297a-111">Wenn Sie eine DllMain-Funktion bereitstellen, ruft das Betriebssystem diese Funktion auf, wenn ein Thread oder ein Prozess mit der DLL verbunden oder von ihr getrennt wird.</span><span class="sxs-lookup"><span data-stu-id="6297a-111">If you provide a DllMain function, the operating system calls this function when a thread or process attaches to or detaches from the DLL.</span></span>  
  
-   <span data-ttu-id="6297a-112">Alle von außerhalb der DLL aufgerufenen Funktionen (alle e-Funktionen einer erweiterten gespeicherten Prozedur) müssen exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="6297a-112">All functions called from outside the DLL (all extended stored procedure Efunctions) must be exported.</span></span>  
  
     <span data-ttu-id="6297a-113">Sie können eine Funktion exportieren, indem Sie Ihren Namen im Abschnitt Exports einer DEF-Datei auflisten, oder Sie können den Funktionsnamen im Quellcode mit __declspec (dllexport), einer Microsoft-Compilererweiterung, als Präfix versehen (Beachten Sie, dass \_ _declspec () mit zwei unterstrichen beginnt).</span><span class="sxs-lookup"><span data-stu-id="6297a-113">You can export a function by listing its name in the EXPORTS section of a .def file, or you can prefix the function name in the source code with __declspec(dllexport), a Microsoft compiler extension (Note that \__declspec() begins with two underscores).</span></span>  
  
 <span data-ttu-id="6297a-114">Diese Dateien sind zum Erstellen einer DLL einer erweiterten gespeicherten Prozedur erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6297a-114">These files are required for creating an extended stored procedure DLL.</span></span>  
  
|<span data-ttu-id="6297a-115">Datei</span><span class="sxs-lookup"><span data-stu-id="6297a-115">File</span></span>|<span data-ttu-id="6297a-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6297a-116">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="6297a-117">Srv.h</span><span class="sxs-lookup"><span data-stu-id="6297a-117">Srv.h</span></span>|<span data-ttu-id="6297a-118">API-Headerdatei für erweiterte gespeicherte Prozeduren</span><span class="sxs-lookup"><span data-stu-id="6297a-118">Extended Stored Procedure API header file</span></span>|  
|<span data-ttu-id="6297a-119">Opends60.lib</span><span class="sxs-lookup"><span data-stu-id="6297a-119">Opends60.lib</span></span>|<span data-ttu-id="6297a-120">Importbibliothek für Opends60.dll</span><span class="sxs-lookup"><span data-stu-id="6297a-120">Import library for Opends60.dll</span></span>|  
  
 <span data-ttu-id="6297a-121">Um eine DLL für eine erweiterte gespeicherte Prozedur zu erstellen, erstellen Sie ein Projekt des Typs Dynamic Link Library.</span><span class="sxs-lookup"><span data-stu-id="6297a-121">To create an extended stored procedure DLL, create a project of type Dynamic Link Library.</span></span> <span data-ttu-id="6297a-122">Weitere Informationen über das Erstellen einer DLL finden Sie in der Dokumentation zur Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="6297a-122">For more information about creating a DLL, see the development environment documentation.</span></span>  
  
 <span data-ttu-id="6297a-123">Es wird empfohlen, dass alle DLLs für erweiterte gespeicherte Prozeduren die folgende Funktion implementieren und exportieren:</span><span class="sxs-lookup"><span data-stu-id="6297a-123">It is highly recommended that all extended stored procedure DLLs implement and export the following function:</span></span>  
  
```  
__declspec(dllexport) ULONG __GetXpVersion()  
{  
   return ODS_VERSION;  
}  
```  
  
> [!NOTE]  
>  <span data-ttu-id="6297a-124">__declspec (dllexport) ist eine Microsoft-spezifische Compilererweiterung.</span><span class="sxs-lookup"><span data-stu-id="6297a-124">__declspec(dllexport) is a Microsoft-specific compiler extension.</span></span> <span data-ttu-id="6297a-125">Wenn Ihr Compiler diese Direktive nicht unterstützt, sollten Sie diese Funktion in Ihre DEF-Datei im Abschnitt EXPORTS exportieren.</span><span class="sxs-lookup"><span data-stu-id="6297a-125">If your compiler does not support this directive, you should export this function in your DEF file under the EXPORTS section.</span></span>  
  
 <span data-ttu-id="6297a-126">Wenn [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] mit dem Ablaufverfolgungsflag gestartet wird T260 gestartet oder wenn ein Benutzer mit Systemadministrator Berechtigungen DBCC TRACEON (260) ausführt und die dll der erweiterten gespeicherten Prozedur __GetXpVersion () nicht unterstützt, wird eine Warnmeldung (Fehler 8131: die dll "%" der erweiterten gespeicherten Prozedur \_ wird nicht _GetXpVersion ().) in das-Fehlerprotokoll ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="6297a-126">When [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is started with the trace flag -T260 or if a user with system administrator privileges runs DBCC TRACEON (260), and if the extended stored procedure DLL does not support __GetXpVersion(), a warning message (Error 8131: Extended stored procedure DLL '%' does not export \__GetXpVersion().) is printed to the error log.</span></span> <span data-ttu-id="6297a-127">(Beachten Sie, dass \_ _GetXpVersion () mit zwei unterstrichen beginnt.)</span><span class="sxs-lookup"><span data-stu-id="6297a-127">(Note that \__GetXpVersion() begins with two underscores.)</span></span>  
  
 <span data-ttu-id="6297a-128">Wenn die DLL für die erweiterte gespeicherte Prozedur __GetXpVersion() exportiert, die von der Funktion zurückgegebene Version jedoch niedriger ist als die vom Server benötigte Version, wird eine Warnmeldung ausgegeben. Diese gibt die von der Funktion zurückgegebene Version und die vom Server benötigte Version im Fehlerprotokoll an.</span><span class="sxs-lookup"><span data-stu-id="6297a-128">If the extended stored procedure DLL exports __GetXpVersion(), but the version returned by the function is less than that required by the server, a warning message stating the version returned by the function and the version expected by the server is printed to the error log.</span></span> <span data-ttu-id="6297a-129">Wenn Sie diese Meldung erhalten, geben Sie einen falschen Wert aus \_ _GetXpVersion () zurück, oder Sie Kompilieren mit einer älteren Version von SRV. h.</span><span class="sxs-lookup"><span data-stu-id="6297a-129">If you get this message, you are returning an incorrect value from \__GetXpVersion(), or you are compiling with an older version of srv.h.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6297a-130">SetErrorMode, eine [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32 Funktion, sollte in erweiterten gespeicherten Prozeduren nicht aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6297a-130">SetErrorMode, a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Win32 function, should not be called in extended stored procedures.</span></span>  
  
 <span data-ttu-id="6297a-131">Es wird empfohlen, dass eine erweiterte gespeicherte Prozedur mit langer Ausführungszeit in regelmäßigen Abständen srv_got_attention aufruft, damit die Prozedur sich selbst beenden kann, falls die Verbindung unterbrochen oder der Batch abgebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="6297a-131">It is recommended that a long-running extended stored procedure should call srv_got_attention periodically so that the procedure can terminate itself if the connection is killed or the batch is aborted.</span></span>  
  
 <span data-ttu-id="6297a-132">Wenn Sie eine DLL für eine erweiterte gespeicherte Prozedur debuggen möchten, kopieren Sie sie in das Verzeichnis [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\Binn.</span><span class="sxs-lookup"><span data-stu-id="6297a-132">To debug an extended stored procedure DLL, copy it to the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]\Binn directory.</span></span> <span data-ttu-id="6297a-133">Wenn Sie die ausführbare Datei für die Debugsitzung angeben möchten, geben Sie den Pfad und den Dateinamen der [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ausführbaren Datei ein (z. b. c:\Programme\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Sqlservr.exe).</span><span class="sxs-lookup"><span data-stu-id="6297a-133">To specify the executable for the debugging session, enter the path and file name of the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] executable file (for example, C:\Program Files\Microsoft SQL Server\MSSQL12.MSSQLSERVER\MSSQL\Binn\Sqlservr.exe).</span></span> <span data-ttu-id="6297a-134">Weitere Informationen zu sqlservr-Argumenten finden Sie unter [sqlservr-Anwendung](../../tools/sqlservr-application.md).</span><span class="sxs-lookup"><span data-stu-id="6297a-134">For information about sqlservr arguments, see [sqlservr Application](../../tools/sqlservr-application.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6297a-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6297a-135">See Also</span></span>  
 [<span data-ttu-id="6297a-136">srv_got_attention &#40;API für erweiterte gespeicherte Prozeduren&#41;</span><span class="sxs-lookup"><span data-stu-id="6297a-136">srv_got_attention &#40;Extended Stored Procedure API&#41;</span></span>](../extended-stored-procedures-reference/srv-got-attention-extended-stored-procedure-api.md)  
  
  
