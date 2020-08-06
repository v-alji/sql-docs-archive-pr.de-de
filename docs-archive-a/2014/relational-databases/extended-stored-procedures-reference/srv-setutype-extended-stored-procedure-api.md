---
title: srv_setutype (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_setutype
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_setutype
ms.assetid: 6160f15d-1b68-411e-ab6d-491ec288f264
author: rothja
ms.author: jroth
ms.openlocfilehash: e9e02605995e44f5869633d5e8778a955236005f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723885"
---
# <a name="srv_setutype-extended-stored-procedure-api"></a><span data-ttu-id="fc53f-102">srv_setutype (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="fc53f-102">srv_setutype (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="fc53f-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="fc53f-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="fc53f-104">Legt den benutzerdefinierten Datentyp für eine Spalte in einer Zeile fest.</span><span class="sxs-lookup"><span data-stu-id="fc53f-104">Sets the user-defined data type for a column in a row.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fc53f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fc53f-105">Syntax</span></span>  
  
```  
  
int srv_setutype (  
SRV_PROC *  
srvproc  
,  
int   
column  
,   
DBINT  
user_type   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="fc53f-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="fc53f-106">Arguments</span></span>  
 <span data-ttu-id="fc53f-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="fc53f-107">*srvproc*</span></span>  
 <span data-ttu-id="fc53f-108">Ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist.</span><span class="sxs-lookup"><span data-stu-id="fc53f-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="fc53f-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="fc53f-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="fc53f-110">*column*</span><span class="sxs-lookup"><span data-stu-id="fc53f-110">*column*</span></span>  
 <span data-ttu-id="fc53f-111">Gibt an, welche Spalte festgelegt werden soll.</span><span class="sxs-lookup"><span data-stu-id="fc53f-111">Indicates which column to set.</span></span> <span data-ttu-id="fc53f-112">Die Spalten sind fortlaufend nummeriert, beginnend mit 1.</span><span class="sxs-lookup"><span data-stu-id="fc53f-112">Columns are numbered beginning with 1.</span></span>  
  
 <span data-ttu-id="fc53f-113">*user_type*</span><span class="sxs-lookup"><span data-stu-id="fc53f-113">*user_type*</span></span>  
 <span data-ttu-id="fc53f-114">Gibt den benutzerdefinierten Datentypcode an.</span><span class="sxs-lookup"><span data-stu-id="fc53f-114">Specifies the user-defined data type code.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="fc53f-115">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="fc53f-115">Returns</span></span>  
 <span data-ttu-id="fc53f-116">SUCCEED oder FAIL.</span><span class="sxs-lookup"><span data-stu-id="fc53f-116">SUCCEED or FAIL.</span></span> <span data-ttu-id="fc53f-117">Wenn die Spalte nicht vorhanden ist, wird FAIL zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="fc53f-117">Returns FAIL if the column does not exist.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fc53f-118">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="fc53f-118">Remarks</span></span>  
 <span data-ttu-id="fc53f-119">Eine Spalte verfügt über zwei Datentypen: ihren tatsächlichen Datentyp und ihren benutzerdefinierten Datentyp.</span><span class="sxs-lookup"><span data-stu-id="fc53f-119">A column has two data types: its actual data type and its user-defined data type.</span></span> <span data-ttu-id="fc53f-120">Der benutzerdefinierte Datentyp wird von verwendet, [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] um den tatsächlichen benutzerdefinierten Datentyp der Spalte, sofern vorhanden, und Spalten Beschreibungs Informationen (z. b. NULL-Zulässigkeit und Aktualisierbarkeit) für die Spalte zu speichern.</span><span class="sxs-lookup"><span data-stu-id="fc53f-120">The user-defined data type is used by [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] to store the actual user-defined data type of the column, if any, and column description information, such as nullability and updatability, for the column.</span></span>  
  
 <span data-ttu-id="fc53f-121">Die **srv_setutype** -Funktion kann jedes Mal aufgerufen werden, wenn *column* mit **srv_describe** definiert ist, und bevor die letzte Zeile gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="fc53f-121">The **srv_setutype** function can be called any time that *column* has been defined with **srv_describe** and before the last row has been sent.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="fc53f-122">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="fc53f-122">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="fc53f-123">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="fc53f-123">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fc53f-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc53f-124">See Also</span></span>  
 [<span data-ttu-id="fc53f-125">srv_describe (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="fc53f-125">srv_describe &#40;Extended Stored Procedure API&#41;</span></span>](srv-describe-extended-stored-procedure-api.md)  
  
  
