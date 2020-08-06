---
title: srv_willconvert (API für erweiterte gespeicherte Prozeduren) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_willconvert
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_willconvert
ms.assetid: 6f4db5fd-215a-461c-95e4-17697852733e
author: rothja
ms.author: jroth
ms.openlocfilehash: 0b9adfbd2a73b30cbfc0229b7942f79d3ddc1a82
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725793"
---
# <a name="srv_willconvert-extended-stored-procedure-api"></a><span data-ttu-id="1b1ff-102">srv_willconvert (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="1b1ff-102">srv_willconvert (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="1b1ff-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="1b1ff-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="1b1ff-104">Bestimmt, ob eine bestimmte Datentypkonvertierung innerhalb der ODS-Bibliothek verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="1b1ff-104">Determines whether a specific data type conversion is available within the ODS Library.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b1ff-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b1ff-105">Syntax</span></span>  
  
```  
  
BOOL srv_willconvert (  
int  
srctype  
,  
int  
desttype   
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="1b1ff-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="1b1ff-106">Arguments</span></span>  
 <span data-ttu-id="1b1ff-107">*srctype*</span><span class="sxs-lookup"><span data-stu-id="1b1ff-107">*srctype*</span></span>  
 <span data-ttu-id="1b1ff-108">Gibt den Datentyp der zu konvertierenden Daten an.</span><span class="sxs-lookup"><span data-stu-id="1b1ff-108">Indicates the data type of the data to be converted.</span></span> <span data-ttu-id="1b1ff-109">Dieser Parameter kann ein beliebiger in der API für erweiterte gespeicherte Prozeduren verfügbarer Datentyp sein.</span><span class="sxs-lookup"><span data-stu-id="1b1ff-109">This parameter can be any of the Extended Stored Procedure API data types.</span></span>  
  
 <span data-ttu-id="1b1ff-110">*desttype*</span><span class="sxs-lookup"><span data-stu-id="1b1ff-110">*desttype*</span></span>  
 <span data-ttu-id="1b1ff-111">Gibt den Datentyp an, in den die Quelldaten konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="1b1ff-111">Indicates the data type to which the source data is converted.</span></span> <span data-ttu-id="1b1ff-112">Dieser Parameter kann ein beliebiger in der API für erweiterte gespeicherte Prozeduren verfügbarer Datentyp sein.</span><span class="sxs-lookup"><span data-stu-id="1b1ff-112">This parameter can be any of the Extended Stored Procedure API data types.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="1b1ff-113">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="1b1ff-113">Returns</span></span>  
 <span data-ttu-id="1b1ff-114">TRUE, wenn die Datentypkonvertierung unterstützt wird; FALSE, wenn die Datentypkonvertierung nicht unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="1b1ff-114">TRUE if the data type conversion is supported; FALSE if the data type conversion is not supported.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1b1ff-115">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="1b1ff-115">Remarks</span></span>  
 <span data-ttu-id="1b1ff-116">Eine Beschreibung der einzelnen Datentypen finden Sie in [Data Types (Extended Stored Procedure API) (Datentypen (API für erweiterte gespeicherte Prozeduren))](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="1b1ff-116">For a description of each data type, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="1b1ff-117">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="1b1ff-117">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="1b1ff-118">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="1b1ff-118">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b1ff-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1b1ff-119">See Also</span></span>  
 [<span data-ttu-id="1b1ff-120">srv_convert (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="1b1ff-120">srv_convert &#40;Extended Stored Procedure API&#41;</span></span>](srv-convert-extended-stored-procedure-api.md)  
  
  
