---
title: srv_message_handler (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_message_handler
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_message_handler
ms.assetid: 41bcd057-436f-4fa8-8293-fc8057a30877
author: rothja
ms.author: jroth
ms.openlocfilehash: 7e7b6472ed4fabb6dc2d545eb51a1e026635ce19
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615395"
---
# <a name="srv_message_handler-extended-stored-procedure-api"></a><span data-ttu-id="52f7e-102">srv_message_handler (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="52f7e-102">srv_message_handler (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="52f7e-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="52f7e-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="52f7e-104">Ruft den installierten Meldungshandler für die API für erweiterte gespeicherte Prozeduren auf.</span><span class="sxs-lookup"><span data-stu-id="52f7e-104">Calls the installed Extended Stored Procedure API message handler.</span></span> <span data-ttu-id="52f7e-105">Diese Funktion wird normalerweise verwendet, um [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] aus einer erweiterten gespeicherten Prozedur aufzurufen, um einen von der erweiterten gespeicherten Prozedur definierten Fehler in der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Fehlerprotokoll Datei oder im [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-Anwendungsprotokoll zu protokollieren.</span><span class="sxs-lookup"><span data-stu-id="52f7e-105">This function is usually used to call [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] from an extended stored procedure to log an error (defined by the extended stored procedure) in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] error log file or the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows application log.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52f7e-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="52f7e-106">Syntax</span></span>  
  
```  
  
int srv_message_handler (  
SRV_PROC *  
srvproc  
,  
int  
errornum  
,  
BYTE   
severity  
,  
BYTE  
state  
,  
int  
oserrnum  
,  
char *  
errtext  
,  
int  
errtextlen  
,  
char *  
oserrtext  
,  
int  
oserrtextlen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="52f7e-107">Argumente</span><span class="sxs-lookup"><span data-stu-id="52f7e-107">Arguments</span></span>  
 <span data-ttu-id="52f7e-108">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="52f7e-108">*srvproc*</span></span>  
 <span data-ttu-id="52f7e-109">Ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist.</span><span class="sxs-lookup"><span data-stu-id="52f7e-109">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="52f7e-110">Der *srvproc*-Parameter enthält Informationen, mit denen die Daten und die Kommunikation zwischen der Anwendung und dem Client verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="52f7e-110">The *srvproc* parameter contains information that is used to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="52f7e-111">*errornum*</span><span class="sxs-lookup"><span data-stu-id="52f7e-111">*errornum*</span></span>  
 <span data-ttu-id="52f7e-112">Eine von der erweiterten gespeicherten Prozedur definierte Fehlernummer.</span><span class="sxs-lookup"><span data-stu-id="52f7e-112">Is an error number defined by the extended stored procedure.</span></span> <span data-ttu-id="52f7e-113">Diese Zahl muss zwischen 50.001 und 2.147.483.647 liegen.</span><span class="sxs-lookup"><span data-stu-id="52f7e-113">This number must be from 50,001 through 2,147,483,647.</span></span>  
  
 <span data-ttu-id="52f7e-114">*severity*</span><span class="sxs-lookup"><span data-stu-id="52f7e-114">*severity*</span></span>  
 <span data-ttu-id="52f7e-115">Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Standardwert für den Schweregrad des Fehlers.</span><span class="sxs-lookup"><span data-stu-id="52f7e-115">Is a standard [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] severity value for the error.</span></span> <span data-ttu-id="52f7e-116">Diese Zahl ist ein Wert zwischen 0 und 24.</span><span class="sxs-lookup"><span data-stu-id="52f7e-116">This number must be from 0 through 24.</span></span>  
  
 <span data-ttu-id="52f7e-117">*state*</span><span class="sxs-lookup"><span data-stu-id="52f7e-117">*state*</span></span>  
 <span data-ttu-id="52f7e-118">Ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Statuswert für den Fehler.</span><span class="sxs-lookup"><span data-stu-id="52f7e-118">Is a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] state value for the error.</span></span>  
  
 <span data-ttu-id="52f7e-119">*oserrnum*</span><span class="sxs-lookup"><span data-stu-id="52f7e-119">*oserrnum*</span></span>  
 <span data-ttu-id="52f7e-120">Die Nummer des Betriebssystemfehlers.</span><span class="sxs-lookup"><span data-stu-id="52f7e-120">Is the operating-system error number.</span></span> <span data-ttu-id="52f7e-121">Dieses Argument wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="52f7e-121">This argument is ignored.</span></span>  
  
 <span data-ttu-id="52f7e-122">*errtext*</span><span class="sxs-lookup"><span data-stu-id="52f7e-122">*errtext*</span></span>  
 <span data-ttu-id="52f7e-123">Die Beschreibung des Fehlers der erweiterten gespeicherten Prozedur *errornum*.</span><span class="sxs-lookup"><span data-stu-id="52f7e-123">Is the description of the extended stored procedure error *errornum*.</span></span>  
  
 <span data-ttu-id="52f7e-124">*errtextlen*</span><span class="sxs-lookup"><span data-stu-id="52f7e-124">*errtextlen*</span></span>  
 <span data-ttu-id="52f7e-125">Die Länge der Fehlerzeichenfolge der erweiterten gespeicherten Prozedur *errtext*.</span><span class="sxs-lookup"><span data-stu-id="52f7e-125">Is the length of the extended stored procedure error string *errtext*.</span></span>  
  
 <span data-ttu-id="52f7e-126">*oserrtext*</span><span class="sxs-lookup"><span data-stu-id="52f7e-126">*oserrtext*</span></span>  
 <span data-ttu-id="52f7e-127">Die Beschreibung des Betriebssystemfehlers *oserrnum*.</span><span class="sxs-lookup"><span data-stu-id="52f7e-127">Is the description of the operating-system error *oserrnum*.</span></span> <span data-ttu-id="52f7e-128">Dieses Argument wird ignoriert.</span><span class="sxs-lookup"><span data-stu-id="52f7e-128">This argument is ignored.</span></span>  
  
 <span data-ttu-id="52f7e-129">*oserrtextlen*</span><span class="sxs-lookup"><span data-stu-id="52f7e-129">*oserrtextlen*</span></span>  
 <span data-ttu-id="52f7e-130">Die Länge der Zeichenfolge des Betriebssystemfehlers *oserrtext*.</span><span class="sxs-lookup"><span data-stu-id="52f7e-130">Is the length of the operating-system error string *oserrtext*.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="52f7e-131">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="52f7e-131">Returns</span></span>  
 <span data-ttu-id="52f7e-132">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="52f7e-132">SUCCEED or FAIL.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52f7e-133">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="52f7e-133">Remarks</span></span>  
 <span data-ttu-id="52f7e-134">Über die **srv_message_handler**-Funktion kann eine erweiterte gespeicherte Prozedur mit der zentralisierten Fehlerprotokollierung und den Berichterstellungsfunktionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] integriert werden.</span><span class="sxs-lookup"><span data-stu-id="52f7e-134">The **srv_message_handler** function enables an extended stored procedure to integrate with the centralized error logging and reporting features of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="52f7e-135">Für Ereignisse in erweiterten gespeicherten Prozeduren können [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Warnungen festgelegt werden, die dann vom SQL Server-Agent überwacht werden.</span><span class="sxs-lookup"><span data-stu-id="52f7e-135">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alerts can be established for events from extended stored procedures, and SQL Server Agent will monitor for these alert conditions.</span></span>  
  
 <span data-ttu-id="52f7e-136">Wenn die Fehlermeldung zu lang ist, wird sie bei 412 Byte abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="52f7e-136">If the error message is longer, it is truncated to 412 bytes.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="52f7e-137">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="52f7e-137">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="52f7e-138">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="52f7e-138">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
