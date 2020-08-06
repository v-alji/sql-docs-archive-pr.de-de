---
title: srv_convert (API für die erweiterte gespeicherte Prozedur) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: stored-procedures
ms.topic: reference
api_name:
- srv_convert
api_location:
- opends60.dll
topic_type:
- apiref
dev_langs:
- C++
helpviewer_keywords:
- srv_convert
ms.assetid: 216b4a31-786e-4361-8a33-e5f6e9790f90
author: rothja
ms.author: jroth
ms.openlocfilehash: 30a0ea356f017ed3d1b3ecc85cf483b4553e120a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622111"
---
# <a name="srv_convert-extended-stored-procedure-api"></a><span data-ttu-id="482e2-102">srv_convert (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="482e2-102">srv_convert (Extended Stored Procedure API)</span></span>
    
> [!IMPORTANT]  
>  [!INCLUDE[ssNoteDepFutureDontUse](../../includes/ssnotedepfuturedontuse-md.md)] <span data-ttu-id="482e2-103">Verwenden Sie stattdessen die CLR-Integration.</span><span class="sxs-lookup"><span data-stu-id="482e2-103">Use CLR integration instead.</span></span>  
  
 <span data-ttu-id="482e2-104">Ändert Daten von einem Datentyp in einen anderen.</span><span class="sxs-lookup"><span data-stu-id="482e2-104">Changes data from one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="482e2-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="482e2-105">Syntax</span></span>  
  
```  
  
int srv_convert (  
SRV_PROC *  
srvproc  
,  
int  
srctype  
,  
void *  
src  
,  
DBINT  
srclen  
,  
int  
desttype  
,  
void *  
dest  
,  
DBINT  
destlen  
);  
  
```  
  
## <a name="arguments"></a><span data-ttu-id="482e2-106">Argumente</span><span class="sxs-lookup"><span data-stu-id="482e2-106">Arguments</span></span>  
 <span data-ttu-id="482e2-107">*srvproc*</span><span class="sxs-lookup"><span data-stu-id="482e2-107">*srvproc*</span></span>  
 <span data-ttu-id="482e2-108">Ein Zeiger auf die SRV_PROC-Struktur, die das Handle für eine bestimmte Clientverbindung ist.</span><span class="sxs-lookup"><span data-stu-id="482e2-108">Is a pointer to the SRV_PROC structure that is the handle for a particular client connection.</span></span> <span data-ttu-id="482e2-109">Die Struktur enthält alle Kontrollinformationen, mit der die API für erweiterte gespeicherte Prozeduren Kommunikationen und Daten zwischen der Anwendung und dem Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="482e2-109">The structure contains all the control information that the Extended Stored Procedure API uses to manage communications and data between the application and the client.</span></span> <span data-ttu-id="482e2-110">Wenn das *srvproc*-Handle zur Verfügung gestellt wird, wird es an die Fehlerhandlerfunktion der API für erweiterte gespeicherte Prozeduren übergeben, sobald ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="482e2-110">If the *srvproc* handle is supplied, it is passed to the Extended Stored Procedure API error handler function when an error occurs.</span></span>  
  
 <span data-ttu-id="482e2-111">*srctype*</span><span class="sxs-lookup"><span data-stu-id="482e2-111">*srctype*</span></span>  
 <span data-ttu-id="482e2-112">Gibt den Datentyp der zu konvertierenden Daten an.</span><span class="sxs-lookup"><span data-stu-id="482e2-112">Specifies the data type of the data to be converted.</span></span> <span data-ttu-id="482e2-113">Dieser Parameter kann ein beliebiger Datentyp der API für erweiterte gespeicherte Prozeduren sein.</span><span class="sxs-lookup"><span data-stu-id="482e2-113">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="482e2-114">*src*</span><span class="sxs-lookup"><span data-stu-id="482e2-114">*src*</span></span>  
 <span data-ttu-id="482e2-115">Ist ein Zeiger auf die zu konvertierenden Daten.</span><span class="sxs-lookup"><span data-stu-id="482e2-115">Is a pointer to the data to be converted.</span></span> <span data-ttu-id="482e2-116">Dieser Parameter kann ein beliebiger Datentyp der API für erweiterte gespeicherte Prozeduren sein.</span><span class="sxs-lookup"><span data-stu-id="482e2-116">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="482e2-117">*srclen*</span><span class="sxs-lookup"><span data-stu-id="482e2-117">*srclen*</span></span>  
 <span data-ttu-id="482e2-118">Gibt die Länge der zu konvertierenden Daten in Byte an.</span><span class="sxs-lookup"><span data-stu-id="482e2-118">Specifies the length, in bytes, of the data to be converted.</span></span> <span data-ttu-id="482e2-119">Wenn *srclen* 0 ist, fügt **srv_convert** einen NULL-Wert in die Zielvariable ein.</span><span class="sxs-lookup"><span data-stu-id="482e2-119">If *srclen* is 0, **srv_convert** places a null value in the destination variable.</span></span> <span data-ttu-id="482e2-120">Wenn nicht 0, wird dieser Parameter für Datentypen fester Länge ignoriert. In diesem Fall wird für die Quelldaten der Wert NULL angenommen.</span><span class="sxs-lookup"><span data-stu-id="482e2-120">Unless it is 0, this parameter is ignored for fixed-length data types, in which case the source data is assumed to be NULL.</span></span> <span data-ttu-id="482e2-121">Für Daten des SRVCHAR-Datentyps gibt eine Länge von -1 an, dass die Zeichenfolge NULL-terminiert ist.</span><span class="sxs-lookup"><span data-stu-id="482e2-121">For data of the SRVCHAR data type, a length of -1 indicates the string is null-terminated.</span></span>  
  
 <span data-ttu-id="482e2-122">*desttype*</span><span class="sxs-lookup"><span data-stu-id="482e2-122">*desttype*</span></span>  
 <span data-ttu-id="482e2-123">Gibt den Datentyp an, in den die Quelle konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="482e2-123">Specifies the data type to convert the source to.</span></span> <span data-ttu-id="482e2-124">Dieser Parameter kann ein beliebiger Datentyp der API für erweiterte gespeicherte Prozeduren sein.</span><span class="sxs-lookup"><span data-stu-id="482e2-124">This parameter can be any of the Extended Store Procedure API data types.</span></span>  
  
 <span data-ttu-id="482e2-125">*dest*</span><span class="sxs-lookup"><span data-stu-id="482e2-125">*dest*</span></span>  
 <span data-ttu-id="482e2-126">Ist ein Zeiger auf die Zielvariable, die die konvertierten Daten empfängt.</span><span class="sxs-lookup"><span data-stu-id="482e2-126">Is a pointer to the destination variable that receives converted data.</span></span> <span data-ttu-id="482e2-127">Wenn dieser Zeiger NULL ist, ruft **srv_convert** den ggf. vom Benutzer bereitgestellten Fehlerhandler auf und gibt –1 zurück.</span><span class="sxs-lookup"><span data-stu-id="482e2-127">If this pointer is NULL, **srv_convert** calls the user-supplied error handler ,if any, and returns -1.</span></span>  
  
 <span data-ttu-id="482e2-128">Wenn *desttype* den Wert SRVDECIMAL oder SRVNUMERIC aufweist, muss der *dest*-Parameter ein Zeiger auf eine DBNUMERIC- oder DBDECIMAL-Struktur sein, und die Felder für Genauigkeit und Dezimalstellen müssen bereits auf die gewünschten Werte festgelegt worden sein.</span><span class="sxs-lookup"><span data-stu-id="482e2-128">If *desttype* is SRVDECIMAL or SRVNUMERIC, the *dest* parameter must be a pointer to a DBNUMERIC or DBDECIMAL structure with the precision and scale fields of the structure already set to the desired values.</span></span> <span data-ttu-id="482e2-129">Mit DEFAULTPRECISION können Sie eine Standardgenauigkeit angeben und mit DEFAULTSCALE einen Standardwert für die Dezimalstellen.</span><span class="sxs-lookup"><span data-stu-id="482e2-129">You can use DEFAULTPRECISION to specify a default precision, and DEFAULTSCALE to specify a default scale.</span></span>  
  
 <span data-ttu-id="482e2-130">*destlen*</span><span class="sxs-lookup"><span data-stu-id="482e2-130">*destlen*</span></span>  
 <span data-ttu-id="482e2-131">Gibt die Länge der Zielvariable in Byte an.</span><span class="sxs-lookup"><span data-stu-id="482e2-131">Specifies the length, in bytes, of the destination variable.</span></span> <span data-ttu-id="482e2-132">Dieser Parameter wird für Datentypen fester Länge ignoriert.</span><span class="sxs-lookup"><span data-stu-id="482e2-132">This parameter is ignored for fixed-length data types.</span></span> <span data-ttu-id="482e2-133">Für eine Zielvariable des Typs SRVCHAR muss der Wert von *destlen* der Gesamtlänge des Zielpufferspeichers entsprechen.</span><span class="sxs-lookup"><span data-stu-id="482e2-133">For a destination variable of type SRVCHAR, the value of *destlen* must be the total length of the destination buffer space.</span></span> <span data-ttu-id="482e2-134">Eine Länge von -1 für eine Zielvariable des Typs SRVCHAR oder SRVBINARY gibt an, dass genügend Speicher verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="482e2-134">A length of -1 for a destination variable of type SRVCHAR or SRVBINARY indicates there is sufficient space available.</span></span> <span data-ttu-id="482e2-135">Für eine Zielvariable des Typs *srvchar* führt eine Länge von –1 zur NULL-Terminierung der Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="482e2-135">For a destination variable of type *srvchar*, a length of -1 causes the character string to be null-terminated.</span></span>  
  
## <a name="returns"></a><span data-ttu-id="482e2-136">Gibt zurück</span><span class="sxs-lookup"><span data-stu-id="482e2-136">Returns</span></span>  
 <span data-ttu-id="482e2-137">Die Länge der konvertierten Daten (in Byte) bei erfolgreicher Konvertierung des Datentyps.</span><span class="sxs-lookup"><span data-stu-id="482e2-137">The length of the converted data, in bytes, if the data type conversion succeeds.</span></span> <span data-ttu-id="482e2-138">Wenn **srv_convert** eine Konvertierungsanforderung erhält, die nicht unterstützt wird, wird – sofern vorhanden – der vom Entwickler bereitgestellte Fehlerhandler aufgerufen, eine globale Fehlernummer festgelegt und der Wert –1 zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="482e2-138">When **srv_convert** encounters a request for a conversion it does not support, it calls the developer-supplied error handler, if any, sets a global error number, and returns -1.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="482e2-139">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="482e2-139">Remarks</span></span>  
 <span data-ttu-id="482e2-140">Die **srv_willconvert**-Funktion bestimmt, ob eine bestimmte Konvertierung zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="482e2-140">The **srv_willconvert** function determines whether a particular conversion is allowed.</span></span>  
  
 <span data-ttu-id="482e2-141">Das Konvertieren von SRVFLT4 oder SRVFLT8 in die ungefähren numerischen Datentypen kann zu einem Genauigkeitsverlust führen.</span><span class="sxs-lookup"><span data-stu-id="482e2-141">Converting to the approximate numeric data types SRVFLT4 or SRVFLT8 can result in some loss of precision.</span></span> <span data-ttu-id="482e2-142">Ein Genauigkeitsverlust kann auch durch Konvertieren der ungefähren numerischen Datentypen SRVFLT4 oder SRVFLT8 in SRVCHAR oder SRVTEXT auftreten.</span><span class="sxs-lookup"><span data-stu-id="482e2-142">Converting from the approximate numeric data types SRVFLT4 or SRVFLT8 to SRVCHAR or SRVTEXT can also result in some loss of precision.</span></span>  
  
 <span data-ttu-id="482e2-143">Das Konvertieren in SRVFLT*x*, SRVINT*x*, SRVMONEY, SRVMONEY4, SRVDECIMAL oder SRVNUMERIC kann zu einem Überlauf führen, wenn die Zahl größer ist als der Maximalwert des Ziels, oder zu einem Unterlauf, wenn die Zahl kleiner ist als der Mindestwert des Ziels.</span><span class="sxs-lookup"><span data-stu-id="482e2-143">Converting to SRVFLT*x*, SRVINT*x*, SRVMONEY, SRVMONEY4, SRVDECIMAL, or SRVNUMERIC can result in overflow if the number is larger than the maximum value of the destination, or in underflow if the number is smaller than the minimum value of the destination.</span></span> <span data-ttu-id="482e2-144">Wenn beim Konvertieren von SRVCHAR oder SRVTEXT ein Überlauf auftritt, enthält das erste Zeichen des resultierenden Werts einen Stern (\*) als Hinweis auf den Fehler.</span><span class="sxs-lookup"><span data-stu-id="482e2-144">If overflow occurs when converting to SRVCHAR or SRVTEXT, the first character of the resulting value contains an asterisk (\*) to indicate the error.</span></span>  
  
 <span data-ttu-id="482e2-145">Wenn Sie SRVCHAR in SRVBINARY konvertieren, interpretiert **srv_convert** SRVCHAR als eine Hexadezimalzeichenfolge, unabhängig davon, ob die Zeichenfolge eine führende 0 enthält.</span><span class="sxs-lookup"><span data-stu-id="482e2-145">When converting SRVCHAR to SRVBINARY, **srv_convert** interprets SRVCHAR as hexadecimal, whether or not the string contains a leading 0.</span></span> <span data-ttu-id="482e2-146">Beim Konvertieren von SRVBINARY in SRVCHAR erstellt **srv_convert** eine Hexadezimalzeichenfolge ohne eine führende 0.</span><span class="sxs-lookup"><span data-stu-id="482e2-146">When converting SRVBINARY to SRVCHAR, **srv_convert** creates a hexadecimal string without a leading 0.</span></span> <span data-ttu-id="482e2-147">In allen anderen Fällen ist eine Konvertierung in oder aus dem SRVBINARY-Datentyp eine exakte Bitkopie.</span><span class="sxs-lookup"><span data-stu-id="482e2-147">In all other cases, a conversion to or from the SRVBINARY data type is a straight bit-copy.</span></span>  
  
 <span data-ttu-id="482e2-148">In bestimmten Fällen kann es nützlich sein, einen Datentyp in sich selbst zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="482e2-148">In certain cases, it can be useful to convert a data type to itself.</span></span> <span data-ttu-id="482e2-149">Durch Konvertieren von SRVCHAR in SRVCHAR mit einem Wert für *destlen* von –1 wird einer Zeichenfolge beispielsweise ein NULL-Terminator hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="482e2-149">For example, converting SRVCHAR to SRVCHAR with a *destlen* of -1 adds a null terminator to a string.</span></span>  
  
 <span data-ttu-id="482e2-150">Eine Beschreibung von Datentypen und Datentypkonvertierungen der API für erweiterte gespeicherte Prozeduren finden Sie unter [Data Types (Extended Stored Procedure API) (Datentypen (API für erweiterte gespeicherte Prozeduren))](data-types-extended-stored-procedure-api.md).</span><span class="sxs-lookup"><span data-stu-id="482e2-150">For a description of data types and Extended Store Procedure API data type conversions, see [Data Types &#40;Extended Stored Procedure API&#41;](data-types-extended-stored-procedure-api.md).</span></span>  
  
 <span data-ttu-id="482e2-151">Die **srv_convert**-Funktion kann aus verschiedenen Gründen fehlschlagen:</span><span class="sxs-lookup"><span data-stu-id="482e2-151">The **srv_convert** function can fail for several reasons:</span></span>  
  
-   <span data-ttu-id="482e2-152">Die angeforderte Konvertierung ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="482e2-152">The requested conversion is not available.</span></span>  
  
-   <span data-ttu-id="482e2-153">Die Konvertierung hat zu Abschneidung, Überlauf oder Genauigkeitsverlust in der Zielvariablen geführt.</span><span class="sxs-lookup"><span data-stu-id="482e2-153">The conversion resulted in truncation, overflow, or loss of precision in the destination variable.</span></span>  
  
-   <span data-ttu-id="482e2-154">Beim Konvertieren einer Zeichenfolge in einen numerischen Datentyp ist ein Syntaxfehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="482e2-154">A syntax error occurred while converting a character string to a numeric data type.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="482e2-155">Sie sollten den Quellcode der erweiterten gespeicherten Prozeduren sorgfältig prüfen, und Sie sollten die kompilierten DLL-Dateien testen, bevor Sie sie auf einem Produktionsserver installieren.</span><span class="sxs-lookup"><span data-stu-id="482e2-155">You should thoroughly review the source code of extended stored procedures, and you should test the compiled DLLs before you install them on a production server.</span></span> <span data-ttu-id="482e2-156">Weitere Informationen zum Überprüfen und Testen der Sicherheit finden Sie auf dieser [Microsoft-Website](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span><span class="sxs-lookup"><span data-stu-id="482e2-156">For information about security review and testing, see this [Microsoft Web site](https://go.microsoft.com/fwlink/?LinkID=54761&amp;clcid=0x409https://msdn.microsoft.com/security/).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="482e2-157">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="482e2-157">See Also</span></span>  
 <span data-ttu-id="482e2-158">[srv_setutype &#40;API für erweiterte gespeicherte Prozeduren&#41;](srv-setutype-extended-stored-procedure-api.md) </span><span class="sxs-lookup"><span data-stu-id="482e2-158">[srv_setutype &#40;Extended Stored Procedure API&#41;](srv-setutype-extended-stored-procedure-api.md) </span></span>  
 [<span data-ttu-id="482e2-159">srv_willconvert (API für erweiterte gespeicherte Prozeduren)</span><span class="sxs-lookup"><span data-stu-id="482e2-159">srv_willconvert &#40;Extended Stored Procedure API&#41;</span></span>](srv-willconvert-extended-stored-procedure-api.md)  
  
  
