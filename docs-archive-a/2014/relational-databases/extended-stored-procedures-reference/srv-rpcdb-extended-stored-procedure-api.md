---
title: srv_rpcdb (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_rpcdb
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_rpcdb
ms.assetid: d52bfd22-7a7c-4ab0-af65-df96ff359e6f
author: rothja
ms.author: jroth
ms.openlocfilehash: c951a4a821bbd49748182d9ddf5df017344a174d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723889"
---
# <a name="srv_rpcdb-extended-stored-procedure-api"></a><span data-ttu-id="8f8b4-102">srv_rpcdb (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="8f8b4-102">srv_rpcdb (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="8f8b4-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="8f8b4-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="8f8b4-104">Gibt die Datenbanknamenskomponente für die derzeit remote gespeicherte Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="8f8b4-104">Returns the database name component for the current remote stored procedure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f8b4-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8f8b4-105">Syntax</span></span>  
  
```  
  
DBCHAR * srv_rpcdb (  
SRV_PROC * srvproc,int *len );  
```  
  
## <a name="arguments"></a><span data-ttu-id="8f8b4-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="8f8b4-106">Arguments</span></span>  
 <span data-ttu-id="8f8b4-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="8f8b4-107">*srvproc*</span></span>  
 <span data-ttu-id="8f8b4-108">Ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist.</span><span class="sxs-lookup"><span data-stu-id="8f8b4-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="8f8b4-109">Die Struktur enthält Informationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren die Kommunikation und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="8f8b4-109">The structure contains information the Extended Stored Procedure API library uses to manage communication and data between the application and the client.</span></span>  
  
 <span data-ttu-id="8f8b4-110">*Nest*</span><span class="sxs-lookup"><span data-stu-id="8f8b4-110">*len*</span></span>  
 <span data-ttu-id="8f8b4-111">Ist ein Zeiger auf eine `int`-Variable, die die Länge des Datenbanknamens empfängt.</span><span class="sxs-lookup"><span data-stu-id="8f8b4-111">Is a pointer to an `int` variable that receives the length of the database name.</span></span> <span data-ttu-id="8f8b4-112">Wenn *len* NULL ist, wird die Länge des Datenbanknamens nicht zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="8f8b4-112">If *len* is NULL, the length of the database name is not returned.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="8f8b4-113">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="8f8b4-113">Returns</span></span>  
 <span data-ttu-id="8f8b4-114">Ein DBCHAR-Zeiger auf die NULL-terminierte Zeichenfolge für den Datenbanknamensteil der aktuellen remote gespeicherten Prozedur.</span><span class="sxs-lookup"><span data-stu-id="8f8b4-114">A DBCHAR pointer to the null-terminated string for the database name part of the current remote stored procedure.</span></span> <span data-ttu-id="8f8b4-115">Wenn keine aktuelle remote gespeicherte Prozedur vorhanden ist, wird NULL zurückgegeben, und der *len*-Parameter wird auf –1 gesetzt.</span><span class="sxs-lookup"><span data-stu-id="8f8b4-115">If there is no current remote stored procedure, NULL is returned and the *len* parameter is set to - 1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f8b4-116">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8f8b4-116">Remarks</span></span>  
 <span data-ttu-id="8f8b4-117">Diese Funktion gibt nur die Datenbankkomponente des Objektnamens der remote gespeicherten Prozedur zurück.</span><span class="sxs-lookup"><span data-stu-id="8f8b4-117">This function returns only the database component of the remote stored procedure object name.</span></span> <span data-ttu-id="8f8b4-118">Sie schließt die optionalen Spezifizierer für Besitzer, den remote gespeicherten Prozedurnamen und die Nummer der remote gespeicherten Prozedur nicht ein.</span><span class="sxs-lookup"><span data-stu-id="8f8b4-118">It does not include the optional specifiers for owner, remote stored procedure name, and remote stored procedure number.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="8f8b4-119">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="8f8b4-119">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="8f8b4-120">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="8f8b4-120">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
