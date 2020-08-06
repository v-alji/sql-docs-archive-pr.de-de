---
title: srv_alloc (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_alloc
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_alloc
ms.assetid: 91505c59-a273-452f-b71d-5e8205c21863
author: rothja
ms.author: jroth
ms.openlocfilehash: 7b372c1b43987e5bebd1fb82e995dc6d262455ae
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615396"
---
# <a name="srv_alloc-extended-stored-procedure-api"></a><span data-ttu-id="c4c62-102">srv_alloc (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="c4c62-102">srv_alloc (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="c4c62-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="c4c62-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="c4c62-104">Weist dynamisch Arbeitsspeicher zu.</span><span class="sxs-lookup"><span data-stu-id="c4c62-104">Allocates memory dynamically.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4c62-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4c62-105">Syntax</span></span>  
  
```  
  
void * srv_alloc ( DBINT  
size  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="c4c62-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="c4c62-106">Arguments</span></span>  
 <span data-ttu-id="c4c62-107">*size*</span><span class="sxs-lookup"><span data-stu-id="c4c62-107">*size*</span></span>  
 <span data-ttu-id="c4c62-108">Legt die Anzahl der zuzuweisenden Bytes fest.</span><span class="sxs-lookup"><span data-stu-id="c4c62-108">Specifies the number of bytes to allocate.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="c4c62-109">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="c4c62-109">Returns</span></span>  
 <span data-ttu-id="c4c62-110">Ein Zeiger auf den neu zugeordneten Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="c4c62-110">A pointer to the newly allocated space.</span></span> <span data-ttu-id="c4c62-111">Wenn *size*-Bytes nicht zugeordnet werden können, wird ein NULL-Zeiger zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c4c62-111">If *size* bytes cannot be allocated, a null pointer is returned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4c62-112">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="c4c62-112">Remarks</span></span>  
 <span data-ttu-id="c4c62-113">Die **srv_alloc**-Funktion entspricht der **GlobalAlloc**-Funktion der [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows-API.</span><span class="sxs-lookup"><span data-stu-id="c4c62-113">The **srv_alloc** function is equivalent to the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows API  **GlobalAlloc** function.</span></span> <span data-ttu-id="c4c62-114">Normale C-Laufzeitspeicher-Verwaltungsfunktionen der Windows API können in einer Anwendung mit der API für erweiterte gespeicherte Prozeduren verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c4c62-114">Normal Windows API C run-time memory management functions can be used in an Extended Stored Procedure API application.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c4c62-115">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="c4c62-115">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="c4c62-116">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="c4c62-116">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
  
