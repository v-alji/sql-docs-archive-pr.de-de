---
title: srv_rpcname (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcname
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcname
ms.assetid: 0a1424e4-3319-4836-b8d8-5e0344cc683f
author: rothja
ms.author: jroth
ms.openlocfilehash: 21530b3e7b8aaa8c5a3f8770762cde7e258e3a43
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725797"
---
# <a name="srv_rpcname-extended-stored-procedure-api"></a><span data-ttu-id="8d2a7-102">srv_rpcname (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="8d2a7-102">srv_rpcname (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="8d2a7-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="8d2a7-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="8d2a7-104">Gibt die Prozedurnamenskomponente für die derzeit remote gespeicherte Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="8d2a7-104">Returns the procedure name component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d2a7-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8d2a7-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcname (  
SRV_PROC *  
srvproc  
,  
int *  
len   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="8d2a7-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="8d2a7-106">Arguments</span></span>  
 <span data-ttu-id="8d2a7-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="8d2a7-107">*srvproc*</span></span>  
 <span data-ttu-id="8d2a7-108">Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall das Handle, das die remote gespeicherte Prozedur erhalten hat).</span><span class="sxs-lookup"><span data-stu-id="8d2a7-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the handle that received the remote stored procedure).</span></span> <span data-ttu-id="8d2a7-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="8d2a7-109">The structure contains information that the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="8d2a7-110">*Nest*</span><span class="sxs-lookup"><span data-stu-id="8d2a7-110">*len*</span></span>  
 <span data-ttu-id="8d2a7-111">Ist ein Zeiger auf eine ganzzahlige Variable, die die Länge des Datenbanknamens empfängt.</span><span class="sxs-lookup"><span data-stu-id="8d2a7-111">Is a pointer to an integer variable that receives the length of the database name.</span></span> <span data-ttu-id="8d2a7-112">Wenn *len* NULL ist, wird die Länge des Namens der remote gespeicherten Prozedur nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8d2a7-112">If *len* is NULL, the length of the remote stored procedure name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="8d2a7-113">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="8d2a7-113">Returns</span></span>  
 <span data-ttu-id="8d2a7-114">Ein DBCHAR-Zeiger auf die NULL-terminierte Zeichenfolge für die Prozedurnamenskomponente der aktuellen remote gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="8d2a7-114">A DBCHAR pointer to the null-terminated string for the remote stored procedure name component of the current remote stored procedure.</span></span> <span data-ttu-id="8d2a7-115">Wenn keine aktuelle remote gespeicherte Prozedur vorhanden ist, wird NULL zurückgegeben, und *len* wird auf -1 festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8d2a7-115">If there is not a current remote stored procedure, NULL is returned and *len* is set to -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8d2a7-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8d2a7-116">Remarks</span></span>  
 <span data-ttu-id="8d2a7-117">Diese Funktion gibt nur den Namen der remote gespeicherten Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="8d2a7-117">This function returns only the name of the remote stored procedure.</span></span> <span data-ttu-id="8d2a7-118">Sie schließt die optionalen Spezifizierer für Besitzer, Datenbanknamen und Name der remote gespeicherten Prozedur nicht ein.</span><span class="sxs-lookup"><span data-stu-id="8d2a7-118">It does not include the optional specifiers for owner, database name, and remote stored procedure number.</span></span>  
  
 <span data-ttu-id="8d2a7-119">Weil ein Aufruf von **srv_rpcname** auch zulässig ist, wenn keine remote gespeicherte Prozedur vorhanden ist (es tritt kein Informationsfehler auf), stellt diese Funktion eine Methode zur Verfügung, mit der ermittelt werden kann, ob eine remote gespeicherte Prozedur vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8d2a7-119">Because it is valid to call **srv_rpcname** when there is not a remote stored procedure (no informational error occurs), this function provides a method for determining whether a remote stored procedure exists.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8d2a7-120">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="8d2a7-120">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="8d2a7-121">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="8d2a7-121">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
