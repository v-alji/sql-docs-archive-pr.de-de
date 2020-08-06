---
title: Codierung und Decodierung von SQL Server-Bezeichnern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: scripting
ms.topic: conceptual
ms.assetid: bb9fe0d3-e432-42d3-b324-64dc908b544a
author: stevestein
ms.author: sstein
ms.openlocfilehash: 88e7ebbc81d9c3cb91b1bf678075c5b5d0884890
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696909"
---
# <a name="encode-and-decode-sql-server-identifiers"></a><span data-ttu-id="8c7c2-102">Codierung und Decodierung von SQL Server-Bezeichnern</span><span class="sxs-lookup"><span data-stu-id="8c7c2-102">Encode and Decode SQL Server Identifiers</span></span>
  <span data-ttu-id="8c7c2-103">Begrenzungsbezeichner von SQL Server können Zeichen enthalten, die in Windows PowerShell-Pfaden nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8c7c2-103">SQL Server delimited identifiers sometimes contain characters not supported in Windows PowerShell paths.</span></span> <span data-ttu-id="8c7c2-104">Diese Zeichen können angegeben werden, indem ihre Hexadezimalwerte codiert werden.</span><span class="sxs-lookup"><span data-stu-id="8c7c2-104">These characters can be specified by encoding their hexadecimal values.</span></span>  
  
1.  <span data-ttu-id="8c7c2-105">**Vorbereitungen:**  [Einschränkungen](#LimitationsRestrictions)</span><span class="sxs-lookup"><span data-stu-id="8c7c2-105">**Before you begin:**  [Limitations and Restrictions](#LimitationsRestrictions)</span></span>  
  
2.  <span data-ttu-id="8c7c2-106">**Zum Verarbeiten von Sonderzeichen:**  [Codieren eines Bezeichners](#EncodeIdent), [Decodieren eines Bezeichners](#DecodeIdent)</span><span class="sxs-lookup"><span data-stu-id="8c7c2-106">**To process special characters:**  [Encoding an Identifier](#EncodeIdent), [Decoding an Identifier](#DecodeIdent)</span></span>  
  
## <a name="before-you-begin"></a><span data-ttu-id="8c7c2-107">Vorbereitungen</span><span class="sxs-lookup"><span data-stu-id="8c7c2-107">Before You Begin</span></span>  
 <span data-ttu-id="8c7c2-108">Zeichen, die nicht in Windows PowerShell-Pfadnamen unterstützt werden, können als "%"-Zeichen gefolgt vom Hexadezimalwert des Bitmusters, das das Zeichen darstellt, dargestellt oder codiert werden, wie in " **%** xx".</span><span class="sxs-lookup"><span data-stu-id="8c7c2-108">Characters that are not supported in Windows PowerShell path names can be represented, or encoded, as the "%" character followed by the hexadecimal value for the bit pattern that represents the character, as in "**%** xx".</span></span> <span data-ttu-id="8c7c2-109">Codierung kann immer zur Verarbeitung von Zeichen verwendet werden, die in Windows PowerShell-Pfaden nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8c7c2-109">Encoding can always be used to handle characters that are not supported in Windows PowerShell paths.</span></span>  
  
 <span data-ttu-id="8c7c2-110">Das Cmdlet **Encode-SqlName** verwendet als Eingabe einen [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="8c7c2-110">The **Encode-SqlName** cmdlet takes as input a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifier.</span></span> <span data-ttu-id="8c7c2-111">Es gibt eine Zeichenfolge mit allen nicht von der Windows PowerShell-Sprache unterstützten Zeichen, die mit "%xx" codiert sind, aus.</span><span class="sxs-lookup"><span data-stu-id="8c7c2-111">It outputs a string with all the characters that are not supported by the Windows PowerShell language encoded with "%xx".</span></span> <span data-ttu-id="8c7c2-112">Das Cmdlet **Decode-SqlName** verwendet einen codierten [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Bezeichner als Eingabe und gibt den ursprünglichen Bezeichner zurück.</span><span class="sxs-lookup"><span data-stu-id="8c7c2-112">The **Decode-SqlName** cmdlet takes as input an encoded [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] identifier and returns the original identifier.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="LimitationsRestrictions"></a> <span data-ttu-id="8c7c2-113">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8c7c2-113">Limitations and Restrictions</span></span>  
 <span data-ttu-id="8c7c2-114">Das `Encode-Sqlname`-Cmdlet und das `Decode-Sqlname`-Cmdlet codieren oder decodieren nur die Zeichen, die in SQL Server-Begrenzungsbezeichnern zulässig sind, jedoch nicht in PowerShell-Pfaden unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="8c7c2-114">The `Encode-Sqlname` and `Decode-Sqlname` cmdlets only encode or decode the characters that are allowed in SQL Server delimited identifiers, but are not supported in PowerShell paths.</span></span> <span data-ttu-id="8c7c2-115">Dies sind die Zeichen, die von **Encode-SqlName** codiert und von **Decode-SqlName**decodiert werden:</span><span class="sxs-lookup"><span data-stu-id="8c7c2-115">These are the characters encoded by **Encode-SqlName** and decoded by **Decode-SqlName**:</span></span>  
  
|||||||||||||  
|-|-|-|-|-|-|-|-|-|-|-|-|  
|<span data-ttu-id="8c7c2-116">**Zeichen**</span><span class="sxs-lookup"><span data-stu-id="8c7c2-116">**Character**</span></span>|\ |/|<span data-ttu-id="8c7c2-117">:</span><span class="sxs-lookup"><span data-stu-id="8c7c2-117">:</span></span>|%|\<|>|*|<span data-ttu-id="8c7c2-118">?</span><span class="sxs-lookup"><span data-stu-id="8c7c2-118">?</span></span>|<span data-ttu-id="8c7c2-119">[</span><span class="sxs-lookup"><span data-stu-id="8c7c2-119">[</span></span>|<span data-ttu-id="8c7c2-120">]</span><span class="sxs-lookup"><span data-stu-id="8c7c2-120">]</span></span>|<span data-ttu-id="8c7c2-121">&#124;</span><span class="sxs-lookup"><span data-stu-id="8c7c2-121">&#124;</span></span>|  
|<span data-ttu-id="8c7c2-122">**Hexadezimale Codierung**</span><span class="sxs-lookup"><span data-stu-id="8c7c2-122">**Hexadecimal Encoding**</span></span>|<span data-ttu-id="8c7c2-123">%5C</span><span class="sxs-lookup"><span data-stu-id="8c7c2-123">%5C</span></span>|<span data-ttu-id="8c7c2-124">%2F</span><span class="sxs-lookup"><span data-stu-id="8c7c2-124">%2F</span></span>|<span data-ttu-id="8c7c2-125">%3A</span><span class="sxs-lookup"><span data-stu-id="8c7c2-125">%3A</span></span>|<span data-ttu-id="8c7c2-126">%25</span><span class="sxs-lookup"><span data-stu-id="8c7c2-126">%25</span></span>|<span data-ttu-id="8c7c2-127">%3C</span><span class="sxs-lookup"><span data-stu-id="8c7c2-127">%3C</span></span>|<span data-ttu-id="8c7c2-128">%3E</span><span class="sxs-lookup"><span data-stu-id="8c7c2-128">%3E</span></span>|<span data-ttu-id="8c7c2-129">%2A</span><span class="sxs-lookup"><span data-stu-id="8c7c2-129">%2A</span></span>|<span data-ttu-id="8c7c2-130">%3F</span><span class="sxs-lookup"><span data-stu-id="8c7c2-130">%3F</span></span>|<span data-ttu-id="8c7c2-131">%5B</span><span class="sxs-lookup"><span data-stu-id="8c7c2-131">%5B</span></span>|<span data-ttu-id="8c7c2-132">%5D</span><span class="sxs-lookup"><span data-stu-id="8c7c2-132">%5D</span></span>|<span data-ttu-id="8c7c2-133">%7C</span><span class="sxs-lookup"><span data-stu-id="8c7c2-133">%7C</span></span>|  
  
##  <a name="encoding-an-identifier"></a><a name="EncodeIdent"></a> <span data-ttu-id="8c7c2-134">Codieren eines Bezeichners</span><span class="sxs-lookup"><span data-stu-id="8c7c2-134">Encoding an Identifier</span></span>  
 <span data-ttu-id="8c7c2-135">**So codieren Sie einen SQL Server-Bezeichner in einem PowerShell-Pfad**</span><span class="sxs-lookup"><span data-stu-id="8c7c2-135">**To encode a SQL Server identifier in a PowerShell path**</span></span>  
  
-   <span data-ttu-id="8c7c2-136">Codieren Sie mithilfe einer der folgenden beiden Methoden einen SQL Server-Bezeichner:</span><span class="sxs-lookup"><span data-stu-id="8c7c2-136">Use one of two methods to encode a SQL Server identifier:</span></span>  
  
    -   <span data-ttu-id="8c7c2-137">Geben Sie den Hexadezimalcode für das nicht unterstützte Zeichen an, indem Sie die Syntax % XX verwenden, wobei XX der Hexadezimalcode ist.</span><span class="sxs-lookup"><span data-stu-id="8c7c2-137">Specify the hexadecimal code for the unsupported character using the syntax %XX, where XX is the hexadecimal code.</span></span>  
  
    -   <span data-ttu-id="8c7c2-138">Übergeben Sie den Bezeichners als Zeichenfolge in Anführungszeichen an das `Encode-Sqlname`-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8c7c2-138">Pass the identifier as a quoted string to the `Encode-Sqlname` cmdlet</span></span>  
  
### <a name="examples-encoding"></a><span data-ttu-id="8c7c2-139">Beispiele (Codierung)</span><span class="sxs-lookup"><span data-stu-id="8c7c2-139">Examples (Encoding)</span></span>  
 <span data-ttu-id="8c7c2-140">In diesem Beispiel wird die codierte Version des Zeichens ":" (%3A) dargestellt:</span><span class="sxs-lookup"><span data-stu-id="8c7c2-140">This example specifies the encoded version of the ":" character (%3A):</span></span>  
  
```  
Set-Location Table%3ATest  
```  
  
 <span data-ttu-id="8c7c2-141">Alternativ können Sie **Encode-SqlName** verwenden, um einen von Windows PowerShell unterstützten Namen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="8c7c2-141">Alternatively, you can use **Encode-SqlName** to build a name supported by Windows PowerShell:</span></span>  
  
```powershell
Set-Location (Encode-SqlName "Table:Test")  
```  
  
##  <a name="decoding-an-identifier"></a><a name="DecodeIdent"></a> <span data-ttu-id="8c7c2-142">Decodieren eines Bezeichners</span><span class="sxs-lookup"><span data-stu-id="8c7c2-142">Decoding an Identifier</span></span>  
 <span data-ttu-id="8c7c2-143">**So decodieren Sie einen SQL Server-Bezeichner aus einem PowerShell-Pfad**</span><span class="sxs-lookup"><span data-stu-id="8c7c2-143">**To decode a SQL Server identifier from a PowerShell path**</span></span>  
  
 <span data-ttu-id="8c7c2-144">Verwenden Sie das `Decode-Sqlname`-Cmdlet, um die Hexadezimalcodierungen durch die von der Codierung dargestellten Zeichen zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="8c7c2-144">Use the `Decode-Sqlname` cmdlet to replace the hexadecimal encodings with the characters represented by the encoding.</span></span>  
  
### <a name="examples-decoding"></a><span data-ttu-id="8c7c2-145">Beispiele (Decodierung)</span><span class="sxs-lookup"><span data-stu-id="8c7c2-145">Examples (Decoding)</span></span>  
 <span data-ttu-id="8c7c2-146">Dieses Beispiel gibt „Table:Test“ zurück:</span><span class="sxs-lookup"><span data-stu-id="8c7c2-146">This example returns "Table:Test":</span></span>  
  
```powershell
Decode-SqlName "Table%3ATest"  
```  
  
## <a name="see-also"></a><span data-ttu-id="8c7c2-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8c7c2-147">See Also</span></span>  
 <span data-ttu-id="8c7c2-148">[SQL Server Bezeichner in PowerShell](sql-server-identifiers-in-powershell.md) </span><span class="sxs-lookup"><span data-stu-id="8c7c2-148">[SQL Server Identifiers in PowerShell](sql-server-identifiers-in-powershell.md) </span></span>  
 <span data-ttu-id="8c7c2-149">[SQL Server PowerShell Anbieter](sql-server-powershell-provider.md) </span><span class="sxs-lookup"><span data-stu-id="8c7c2-149">[SQL Server PowerShell Provider](sql-server-powershell-provider.md) </span></span>  
 [<span data-ttu-id="8c7c2-150">SQL Server-PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c7c2-150">SQL Server PowerShell</span></span>](sql-server-powershell.md)  
