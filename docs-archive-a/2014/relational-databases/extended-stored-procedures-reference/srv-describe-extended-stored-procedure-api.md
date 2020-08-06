---
title: srv_describe (API für die erweiterte gespeicherte Prozedur) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_describe
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_describe
ms.assetid: 2115600e-5ce7-4be0-9cd3-a1dd1fab0729
author: rothja
ms.author: jroth
ms.openlocfilehash: 52a397b79f4fcecaa2ccacde7500cb852ae793fd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622110"
---
# <a name="srv_describe-extended-stored-procedure-api"></a><span data-ttu-id="89d76-102">srv_describe (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="89d76-102">srv_describe (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="89d76-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="89d76-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="89d76-104">Definiert den Spaltennamen und die Quellen- und Zieldatentypen für eine bestimmte Spalte in einer Zeile.</span><span class="sxs-lookup"><span data-stu-id="89d76-104">Defines the column name and source and destination data types for a specific column in a row.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89d76-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="89d76-105">Syntax</span></span>  
  
```  
  
int srv_describe (  
SRV_PROC *  
srvproc  
,  
int  
colnumber  
,  
DBCHAR *  
column_name  
,  
int  
namelen  
,  
DBINT  
desttype  
,  
DBINT  
destlen  
,  
DBINT  
srctype  
,  
DBINT  
srclen  
,  
void *  
srcdata  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="89d76-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="89d76-106">Arguments</span></span>  
 <span data-ttu-id="89d76-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="89d76-107">*srvproc*</span></span>  
 <span data-ttu-id="89d76-108">Ist ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist (in diesem Fall der die Zeile sendende Client).</span><span class="sxs-lookup"><span data-stu-id="89d76-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection (in this case, the client sending the row).</span></span> <span data-ttu-id="89d76-109">Die Struktur enthält alle Kontrollinformationen, mit der die API-Bibliothek für erweiterte gespeicherte Prozeduren Kommunikationen und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="89d76-109">The structure contains all the information that the Extended Stored Procedure API library uses to manage communications and data between the application and the client.</span></span>  
  
 <span data-ttu-id="89d76-110">*colnumber*</span><span class="sxs-lookup"><span data-stu-id="89d76-110">*colnumber*</span></span>  
 <span data-ttu-id="89d76-111">Wird derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="89d76-111">Is currently not supported.</span></span> <span data-ttu-id="89d76-112">Spalten müssen der Reihe nach beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="89d76-112">Columns must be described in order.</span></span> <span data-ttu-id="89d76-113">Alle Spalten müssen vor dem Aufrufen von **srv_sendrow** beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="89d76-113">All columns must be described before **srv_sendrow** is called.</span></span>  
  
 <span data-ttu-id="89d76-114">*column_name*</span><span class="sxs-lookup"><span data-stu-id="89d76-114">*column_name*</span></span>  
 <span data-ttu-id="89d76-115">Gibt den Namen der Spalte an, zu der die Daten gehören.</span><span class="sxs-lookup"><span data-stu-id="89d76-115">Specifies the name of the column to which the data belongs.</span></span> <span data-ttu-id="89d76-116">Dieser Parameter kann NULL sein, da eine Spalte nicht zwingend einen Namen haben muss.</span><span class="sxs-lookup"><span data-stu-id="89d76-116">This parameter can be NULL because a column is not required to have a name.</span></span>  
  
 <span data-ttu-id="89d76-117">*namelen*</span><span class="sxs-lookup"><span data-stu-id="89d76-117">*namelen*</span></span>  
 <span data-ttu-id="89d76-118">Gibt die Länge von *column_name* in Byte an.</span><span class="sxs-lookup"><span data-stu-id="89d76-118">Specifies the length, in bytes, of *column_name*.</span></span> <span data-ttu-id="89d76-119">Wenn *namelen* den Wert SRV_NULLTERM hat, muss *column_name* NULL-terminiert sein.</span><span class="sxs-lookup"><span data-stu-id="89d76-119">If *namelen* is SRV_NULLTERM, then *column_name* must be null-terminated.</span></span>  
  
 <span data-ttu-id="89d76-120">*desttype*</span><span class="sxs-lookup"><span data-stu-id="89d76-120">*desttype*</span></span>  
 <span data-ttu-id="89d76-121">Gibt den Datentyp der Spalte mit der Zielzeile an.</span><span class="sxs-lookup"><span data-stu-id="89d76-121">Specifies the data type of the destination row column.</span></span> <span data-ttu-id="89d76-122">Dies ist der Datentyp, der an den Client gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="89d76-122">This is the data type sent to the client.</span></span> <span data-ttu-id="89d76-123">Der Datentyp muss angegeben werden, auch wenn die Daten NULL sind. Weitere Informationen finden Sie unter [Data Types (Extended Stored Procedure API) (Datentypen (API für erweiterte gespeicherte Prozeduren))](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="89d76-123">The data type must be specified even if the data is NULL, for more information, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="89d76-124">*destlen*</span><span class="sxs-lookup"><span data-stu-id="89d76-124">*destlen*</span></span>  
 <span data-ttu-id="89d76-125">Gibt die Länge der Daten in Byte an, die an den Client gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="89d76-125">Specifies the length, in bytes, of the data to be sent to the client.</span></span> <span data-ttu-id="89d76-126">Für Datentypen mit fester Länge, die keine NULL-Werte zulassen, wird *destlen* ignoriert.</span><span class="sxs-lookup"><span data-stu-id="89d76-126">For fixed-length data types that do not allow null values, *destlen* is ignored.</span></span> <span data-ttu-id="89d76-127">Für Datentypen variabler Länge und Datentypen fester Länge, die NULL-Werte zulassen, gibt *destlen* die maximal zulässige Länge der Zieldaten an.</span><span class="sxs-lookup"><span data-stu-id="89d76-127">For variable-length data types and fixed-length data types that allow null values, *destlen* specifies the maximum length the destination data can be.</span></span>  
  
 <span data-ttu-id="89d76-128">*srctype*</span><span class="sxs-lookup"><span data-stu-id="89d76-128">*srctype*</span></span>  
 <span data-ttu-id="89d76-129">Gibt den Datentyp der Quelldaten an.</span><span class="sxs-lookup"><span data-stu-id="89d76-129">Specifies the data type of the source data.</span></span>  
  
 <span data-ttu-id="89d76-130">*srclen*</span><span class="sxs-lookup"><span data-stu-id="89d76-130">*srclen*</span></span>  
 <span data-ttu-id="89d76-131">Gibt die Länge der Quelldaten in Byte an.</span><span class="sxs-lookup"><span data-stu-id="89d76-131">Specifies the length, in bytes, of the source data.</span></span> <span data-ttu-id="89d76-132">Dieser Wert wird für Datentypen fester Länge ignoriert.</span><span class="sxs-lookup"><span data-stu-id="89d76-132">This value is ignored for fixed-length data types.</span></span>  
  
 <span data-ttu-id="89d76-133">*srcdata*</span><span class="sxs-lookup"><span data-stu-id="89d76-133">*srcdata*</span></span>  
 <span data-ttu-id="89d76-134">Stellt die Quelldatenadresse für eine bestimmte Spalte zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="89d76-134">Provides the source data address for a particular column.</span></span> <span data-ttu-id="89d76-135">Wenn **srv_sendrow** aufgerufen wird, werden die Daten für *colnumber* in *srcdata* gesucht.</span><span class="sxs-lookup"><span data-stu-id="89d76-135">When **srv_sendrow** is called, it looks for the data for *colnumber* at *srcdata*.</span></span> <span data-ttu-id="89d76-136">Daher sollte keine Freigabe vor einem Aufruf von **srv_sendrow** erfolgen.</span><span class="sxs-lookup"><span data-stu-id="89d76-136">Therefore it should not be freed before a call to **srv_sendrow**.</span></span> <span data-ttu-id="89d76-137">Die Quelldatenadresse kann zwischen Aufrufen von **srv_sendrow** mit **srv_setcoldata** geändert werden.</span><span class="sxs-lookup"><span data-stu-id="89d76-137">The source data address can be changed between calls to **srv_sendrow** by using **srv_setcoldata**.</span></span> <span data-ttu-id="89d76-138">Der *srcdata* zugewiesene Speicher sollte erst freigegeben werden, bis die Spaltendaten durch einen anderen Aufruf von **srv_setcoldata** ersetzt wurden oder bis **srv_senddone** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="89d76-138">Memory allocated for *srcdata* should not be freed until the column data is replaced by another call to **srv_setcoldata**, or until **srv_senddone** is called.</span></span>  
  
 <span data-ttu-id="89d76-139">Wenn *desttype* den Wert SRVDECIMAL oder SRVNUMERIC aufweist, muss der *srcdata*-Parameter ein Zeiger auf eine DBNUMERIC- oder DBDECIMAL-Struktur sein, und die Felder für Genauigkeit und Dezimalstellen müssen bereits auf die gewünschten Werte festgelegt worden sein.</span><span class="sxs-lookup"><span data-stu-id="89d76-139">If *desttype* is SRVDECIMAL or SRVNUMERIC, the *srcdata* parameter must be a pointer to a DBNUMERIC or DBDECIMAL structure with the precision and scale fields of the structure already set to the values you want.</span></span> <span data-ttu-id="89d76-140">Mit DEFAULTPRECISION können Sie eine Standardgenauigkeit angeben und mit DEFAULTSCALE einen Standardwert für die Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="89d76-140">You can use DEFAULTPRECISION to specify a default precision, and DEFAULTSCALE to specify a default scale.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="89d76-141">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="89d76-141">Returns</span></span>  
 <span data-ttu-id="89d76-142">Die Nummer der beschriebenen Spalte.</span><span class="sxs-lookup"><span data-stu-id="89d76-142">The number of the column described.</span></span> <span data-ttu-id="89d76-143">Die erste Spalte ist die Spalte 1.</span><span class="sxs-lookup"><span data-stu-id="89d76-143">The first column is column 1.</span></span> <span data-ttu-id="89d76-144">Tritt ein Fehler auf, wird 0 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="89d76-144">If an error occurs, returns 0.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="89d76-145">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="89d76-145">Remarks</span></span>  
 <span data-ttu-id="89d76-146">Die **srv_describe**-Funktion muss einmal für jede Spalte in der Zeile aufgerufen werden, bevor der erste Aufruf von **srv_sendrow** erfolgt.</span><span class="sxs-lookup"><span data-stu-id="89d76-146">The **srv_describe** function must be called once for each column in the row before the first call to **srv_sendrow**.</span></span> <span data-ttu-id="89d76-147">Die Spalten einer Zeile können in jeder Reihenfolge beschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="89d76-147">The columns of a row can be described in any order.</span></span>  
  
 <span data-ttu-id="89d76-148">Verwenden Sie **srv_setcoldata** bzw. **srv_setcollen**, um den Speicherort und die Länge der Quelldaten in Spaltenzeilen zu ändern, bevor das gesamte Resultset gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="89d76-148">To change the location and length of the source data in column rows before the complete result set has been sent, use **srv_setcoldata** and **srv_setcollen**, respectively.</span></span>  
  
 <span data-ttu-id="89d76-149">Eine Beschreibung von Datentypen und Datentypkonvertierungen der API für erweiterte gespeicherte Prozeduren finden Sie unter [Data Types (Extended Stored Procedure API) (Datentypen (API für erweiterte gespeicherte Prozeduren))](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="89d76-149">For a description of data types and Extended Store Procedure API data type conversions, see[Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="89d76-150">Wenn der Spaltenname in der Anwendung in Unicode angegeben ist, muss er in die Multibytecodepage des Servers konvertiert werden, bevor **srv_describe** aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="89d76-150">If the column name in your application is in Unicode, you need to convert it to the multibyte code page of the server before calling **srv_describe**.</span></span> <span data-ttu-id="89d76-151">Weitere Informationen finden Sie unter [Unicode-Daten und Server-Codepages](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span><span class="sxs-lookup"><span data-stu-id="89d76-151">For more information, see [Unicode Data and Server Code Pages](../extended-stored-procedures-programming/unicode-data-and-server-code-pages.md).</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="89d76-152">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="89d76-152">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="89d76-153">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="89d76-153">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d76-154">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89d76-154">See Also</span></span>  
 <span data-ttu-id="89d76-155">[srv_sendrow &#40;API für erweiterte gespeicherte Prozeduren&#41;](srv-sendrow-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="89d76-155">[srv_sendrow &#40;Extended Stored Procedure API&#41;](srv-sendrow-extended-stored-procedure-api.md) </span></span>  
 <span data-ttu-id="89d76-156">[srv_setutype &#40;API für erweiterte gespeicherte Prozeduren&#41;](srv-setutype-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="89d76-156">[srv_setutype &#40;Extended Stored Procedure API&#41;](srv-setutype-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="89d76-157">srv_setcoldata (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="89d76-157">srv_setcoldata &#40;Extended Stored Procedure API&#41;</span></span>](srv-setcoldata-extended-stored-procedure-api.md)  
  
  
