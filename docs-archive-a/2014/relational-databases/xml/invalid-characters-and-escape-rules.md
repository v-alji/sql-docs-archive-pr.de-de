---
title: Ungültige Zeichen und Escaperegeln | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, invalid characters
- FOR XML clause, escape rules
ms.assetid: f2e9b997-f400-4963-b225-59d46c6b93e8
author: rothja
ms.author: jroth
ms.openlocfilehash: 8624a31dea4e97e05da6d86c3c0c518b9c4d0aba
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725341"
---
# <a name="invalid-characters-and-escape-rules"></a><span data-ttu-id="b1313-102">Ungültige Zeichen und Escaperegeln</span><span class="sxs-lookup"><span data-stu-id="b1313-102">Invalid Characters and Escape Rules</span></span>
  <span data-ttu-id="b1313-103">In diesem Thema wird beschrieben, wie ungültige XML-Zeichen von der FOR XML-Klausel behandelt werden, und die Escaperegeln für Zeichen aufgelistet, die in XML-Namen ungültig sind.</span><span class="sxs-lookup"><span data-stu-id="b1313-103">This topic describes how invalid XML characters are handled by the FOR XML clause, and lists the escape rules for characters that are invalid in XML names.</span></span>  
  
## <a name="for-xml-and-invalid-characters"></a><span data-ttu-id="b1313-104">FOR XML und ungültige Zeichen</span><span class="sxs-lookup"><span data-stu-id="b1313-104">For XML and Invalid Characters</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b1313-105">ändert ungültige XML-Zeichen in Entitäten, wenn sie innerhalb von FOR XML-Abfragen zurückgegeben werden, die nicht die TYPE-Direktive verwenden.</span><span class="sxs-lookup"><span data-stu-id="b1313-105">entitizes invalid XML characters when they are returned within FOR XML queries that do not use the TYPE directive.</span></span>  
  
 <span data-ttu-id="b1313-106">Zwar lösen XML 1.0-konforme Parser Analysefehler unabhängig davon aus, ob diese Zeichen in Entitäten geändert wurden, die Entitätsform ist jedoch kompatibler mit XML 1.1.</span><span class="sxs-lookup"><span data-stu-id="b1313-106">Although XML 1.0 conformant parsers raise parse errors regardless of whether these characters are entitized or not, the entitized form is better aligned with XML 1.1.</span></span> <span data-ttu-id="b1313-107">Die Entitätsform ist außerdem möglicherweise kompatibler mit zukünftigen Versionen des XML-Standards.</span><span class="sxs-lookup"><span data-stu-id="b1313-107">The entitized form is also potentially better aligned with future versions of the XML standard.</span></span> <span data-ttu-id="b1313-108">Darüber hinaus vereinfacht sie das Debuggen, weil das Codeelement des ungültigen Zeichens sichtbar wird.</span><span class="sxs-lookup"><span data-stu-id="b1313-108">Additionally, it makes debugging simpler, because the code point of the invalid character becomes visible.</span></span>  
  
 <span data-ttu-id="b1313-109">Für Benutzer von XML-Tools ist keine Problemumgehung erforderlich, weil der XML-Parser unter allen Umständen an dem Punkt fehlschlägt, an dem das ungültige Zeichen im Datenstrom auftritt.</span><span class="sxs-lookup"><span data-stu-id="b1313-109">For users of XML tools, no workaround is required, because the XML parser will fail either way at the point where the invalid characters occur in the data stream.</span></span> <span data-ttu-id="b1313-110">Wenn Sie Nicht-XML-Tools verwenden, kann diese Änderung das Aktualisieren der Programmierlogik erforderlich machen, damit diese nach diesen Zeichen als in Entitäten geänderte Werte sucht.</span><span class="sxs-lookup"><span data-stu-id="b1313-110">If you use non-XML tools, this change can require you to update your programming logic to search for these characters as entitized values.</span></span>  
  
 <span data-ttu-id="b1313-111">Die folgenden Leerzeichen werden in FOR XML-Abfragen auf andere Weise in Entitäten geändert, damit sie bei Roundtrips beibehalten werden:</span><span class="sxs-lookup"><span data-stu-id="b1313-111">The following white space characters are entitized differently in FOR XML queries to preserve their presence through round-tripping:</span></span>  
  
-   <span data-ttu-id="b1313-112">In Elementinhalten und -attributen: **hex(0D)** (Wagenrücklauf)</span><span class="sxs-lookup"><span data-stu-id="b1313-112">In element content and attributes: **hex(0D)** (carriage return)</span></span>  
  
-   <span data-ttu-id="b1313-113">In Attributinhalten: **hex(09)** (Tabulator), **hex(0A)** (Zeilenvorschub)</span><span class="sxs-lookup"><span data-stu-id="b1313-113">In attribute content: **hex(09)** (tab), **hex(0A)** (line feed)</span></span>  
  
 <span data-ttu-id="b1313-114">Diese Zeichen werden in der Ausgabe beibehalten und nicht von Parsern normalisiert.</span><span class="sxs-lookup"><span data-stu-id="b1313-114">These characters are preserved in output, and a parser will not normalize them.</span></span>  
  
## <a name="escape-rules"></a><span data-ttu-id="b1313-115">Escaperegeln</span><span class="sxs-lookup"><span data-stu-id="b1313-115">Escape Rules</span></span>  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="b1313-116">-Namen, die Zeichen enthalten, die in XML-Namen ungültig sind (wie etwa Leerzeichen), werden so in XML-Namen übersetzt, dass die ungültigen Zeichen in geschützte numerische Entitätscodierung übersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="b1313-116">names that contain characters that are invalid in XML names, such as spaces, are translated into XML names in a way in which the invalid characters are translated into escaped numeric entity encoding.</span></span>  
  
 <span data-ttu-id="b1313-117">Nur zwei nicht alphabetische Zeichen können in einem XML-Namen auftreten: der Doppelpunkt (:) und der Unterstrich (_).</span><span class="sxs-lookup"><span data-stu-id="b1313-117">There are only two non-alphabetic characters that can occur within an XML name: the colon (:) and the underscore (_).</span></span> <span data-ttu-id="b1313-118">Da der Doppelpunkt bereits für Namespaces vorbehalten ist, wurde der Unterstrich als Escapezeichen gewählt.</span><span class="sxs-lookup"><span data-stu-id="b1313-118">Because the colon is already reserved for namespaces, the underscore is chosen as the escape character.</span></span> <span data-ttu-id="b1313-119">Die folgenden Escaperegeln werden für die Codierung verwendet:</span><span class="sxs-lookup"><span data-stu-id="b1313-119">Following are the escape rules that are used for encoding:</span></span>  
  
-   <span data-ttu-id="b1313-120">Alle UCS-2-Zeichen, die keine gültigen Zeichen für XML-Namen gemäß der XML 1.0-Spezifikation sind, werden in _xHHHH\_umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="b1313-120">Any UCS-2 character that is not a valid XML name character, according to the XML 1.0 specification, is escaped as _xHHHH\_.</span></span> <span data-ttu-id="b1313-121">HHHH steht für den vierstelligen hexadezimalen UCS-2-Code für das Zeichen in einer nach Signifikanz geordneten Bitfolge.</span><span class="sxs-lookup"><span data-stu-id="b1313-121">The HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span> <span data-ttu-id="b1313-122">So wird z.B. der Tabellenname **Order Details** als Order_x0020_Details codiert.</span><span class="sxs-lookup"><span data-stu-id="b1313-122">For example, the table name **Order Details** is encoded as Order_x0020_Details.</span></span>  
  
-   <span data-ttu-id="b1313-123">Zeichen außerhalb des UCS-2-Bereichs (die UCS-4-Erweiterungen des Bereichs U+00010000 bis U+0010FFFF) werden als _xHHHHHHHH\_codiert.</span><span class="sxs-lookup"><span data-stu-id="b1313-123">Characters that do not fit into the UCS-2 realm (the UCS-4 additions of the range U+00010000 to U+0010FFFF) are encoded as _xHHHHHHHH\_.</span></span> <span data-ttu-id="b1313-124">Dabei steht HHHHHHHH für die achtstellige hexadezimale UCS-4-Codierung des Zeichens, wenn der Abwärtskompatibilitätsmodus von SQL Server 2000 verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b1313-124">The HHHHHHHH stands for the eight-digit hexadecimal UCS-4 encoding of the character, if under SQL Server 2000 backward compatibility mode.</span></span> <span data-ttu-id="b1313-125">Anderenfalls werden die Zeichen als _xHHHHHH\_codiert, um dem ISO-Standard zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="b1313-125">Otherwise, the characters are encoded as_xHHHHHH\_, in order to align with the ISO standard.</span></span>  
  
-   <span data-ttu-id="b1313-126">Der Unterstrich muss nur mit Escapezeichen versehen werden, wenn darauf das Zeichen x folgt.</span><span class="sxs-lookup"><span data-stu-id="b1313-126">The underscore character does not have to be escaped unless it is followed by the character x.</span></span> <span data-ttu-id="b1313-127">Der Tabellenname **Order_Details** wird z.B. nicht codiert.</span><span class="sxs-lookup"><span data-stu-id="b1313-127">For example, the table name **Order_Details** is not encoded.</span></span>  
  
-   <span data-ttu-id="b1313-128">Der Doppelpunkt in Bezeichnern wird nicht in eine Escapezeichenfolge umgewandelt. Als Ergebnis können Element- und Attributnamen für Namespaces von der FOR XML-Abfrage generiert werden.</span><span class="sxs-lookup"><span data-stu-id="b1313-128">The colon in identifiers is not escaped As a result, the namespace element and attribute names can be generated by the FOR XML query.</span></span> <span data-ttu-id="b1313-129">So generiert z. B. die folgende Abfrage ein Namespaceattribut mit einem Doppelpunkt im Namen:</span><span class="sxs-lookup"><span data-stu-id="b1313-129">For example, the following query generates a namespace attribute that has a colon in the name:</span></span>  
  
    ```  
    SELECT 'namespace-urn' as 'xmlns:namespace',   
     1 as 'namespace:a'   
    FOR XML RAW  
    ```  
  
     <span data-ttu-id="b1313-130">Die Abfrage liefert folgendes Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="b1313-130">The query produces this result:</span></span>  
  
    ```  
    <row xmlns:namespace="namespace-urn" namespace:a="1"/>  
    ```  
  
     <span data-ttu-id="b1313-131">Beachten Sie, dass WITH XMLNAMESPACES das empfohlene Verfahren zum Hinzufügen von XML-Namespaces ist.</span><span class="sxs-lookup"><span data-stu-id="b1313-131">Note that WITH XMLNAMESPACES is the recommended way to add XML namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b1313-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b1313-132">See Also</span></span>  
 [<span data-ttu-id="b1313-133">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="b1313-133">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
