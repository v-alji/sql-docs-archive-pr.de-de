---
title: Einschränkung für eindeutige Partikelzuordnung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
f1_keywords:
- unique particle attribution
helpviewer_keywords:
- schema collections [SQL Server], unique particle attribution
- XML schema collections [SQL Server], unique particle attribution
- UPA constraint rule
- unique particle attribution constraint rule
ms.assetid: 6bb879e9-a5ee-402e-94e4-fe8cec5966b0
author: rothja
ms.author: jroth
ms.openlocfilehash: 7416aa4ea14539f3bf633207768783aa439ec818
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695458"
---
# <a name="unique-particle-attribution-constraint"></a><span data-ttu-id="dc07d-102">Einschränkung für eindeutige Partikelzuordnung</span><span class="sxs-lookup"><span data-stu-id="dc07d-102">Unique Particle Attribution Constraint</span></span>
  <span data-ttu-id="dc07d-103">In XSD werden komplexe Inhaltsmodelle durch die UPA-Einschränkungsregel (Unique Particle Attribution, eindeutige Partikelzuordnung) eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="dc07d-103">In XSD, complex content models are constrained by the unique particle attribution (UPA) constraint rule.</span></span> <span data-ttu-id="dc07d-104">Diese Regel verlangt, dass jedes Element in einem Instanzdokument eindeutig genau einem `<xsd:element>` - oder `<xsd:any>` -Partikel im übergeordneten Inhaltsmodell entspricht.</span><span class="sxs-lookup"><span data-stu-id="dc07d-104">This rule requires that each element in an instance document correspond unambiguously to exactly one `<xsd:element>` or `<xsd:any>` particle in its parent's content model.</span></span> <span data-ttu-id="dc07d-105">Jedes Schema, das einen Typ mit einem potenziell mehrdeutigen Inhaltsmodell enthält, wird zurückgewiesen.</span><span class="sxs-lookup"><span data-stu-id="dc07d-105">Any schema that contains a type with a potentially ambiguous content model is rejected.</span></span>  
  
 <span data-ttu-id="dc07d-106">Die häufigste Ursache für Mehrdeutigkeit sind `<xsd:any>`-Platzhalterzeichen und -partikel, die variable Vorkommensbereiche aufweisen, z. B. minOccurs < maxOccurs.</span><span class="sxs-lookup"><span data-stu-id="dc07d-106">The most common causes of ambiguity are `<xsd:any>` wildcard characters and particles that have variable occurrence ranges, such as minOccurs < maxOccurs.</span></span> <span data-ttu-id="dc07d-107">Das folgende Inhaltsmodell ist z. B. mehrdeutig, da ein <`e1`>-Element dem `<xsd:element>`- oder dem `<xsd:any>`-Element entsprechen kann.</span><span class="sxs-lookup"><span data-stu-id="dc07d-107">For example, the following content model is ambiguous, because an <`e1`> element could match either the `<xsd:element>` or the `<xsd:any>` element.</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:choice>  
            <xsd:element name="e1"/>  
            <xsd:any namespace="##any"/>  
        </xsd:choice>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="dc07d-108">Das folgende Inhaltsmodell ist ebenfalls mehrdeutig:</span><span class="sxs-lookup"><span data-stu-id="dc07d-108">The following content model is also ambiguous:</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:sequence>  
            <xsd:element name="e1" maxOccurs="2"/>  
            <xsd:element name="e2" minOccurs="0"/>  
            <xsd:element name="e1"/>  
        </xsd:sequence>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="dc07d-109">Ein Dokument wie z. B. `<root><e1/><e2/><e1/></root>` kann zwar eindeutig überprüft werden, ein Dokument wie z. B. `<root><e1/><e1/></root>` hingegen nicht, weil nicht eindeutig ist, welchem `<xsd:element>` die zweite Angabe `<e1/>` entspricht.</span><span class="sxs-lookup"><span data-stu-id="dc07d-109">Although a document such as `<root><e1/><e2/><e1/></root>` can be validated unambiguously, a document such as `<root><e1/><e1/></root>` cannot, because it is not clear to which `<xsd:element>` the second `<e1/>` corresponds.</span></span> <span data-ttu-id="dc07d-110">Auch wenn einige Dokumente eindeutig überprüft werden können, wird das Schema aufgrund potenzieller Mehrdeutigkeit zurückgewiesen.</span><span class="sxs-lookup"><span data-stu-id="dc07d-110">Even though some documents can be validated unambiguously, the schema will be rejected, because of the potential for ambiguity.</span></span>  
  
 <span data-ttu-id="dc07d-111">Beachten Sie, dass ein Inhaltsmodell in der Lage sein muss, jede Instanz ohne Lookahead eindeutig zu überprüfen, damit es gültig ist.</span><span class="sxs-lookup"><span data-stu-id="dc07d-111">Note that for a content model to be valid, it must be possible to validate any instance unambiguously without looking ahead.</span></span> <span data-ttu-id="dc07d-112">Betrachten Sie z. B. das folgende Inhaltsmodell:</span><span class="sxs-lookup"><span data-stu-id="dc07d-112">For example, consider the following content model:</span></span>  
  
```  
<xsd:element name="root">  
    <xsd:complexType>  
        <xsd:choice>  
           <xsd:sequence>  
               <xsd:element name="e1"/>  
               <xsd:element name="e2"/>  
           </xsd:sequence>  
           <xsd:sequence>  
               <xsd:element name="e1"/>  
               <xsd:element name="e3"/>  
           </xsd:sequence>  
       </xsd:choice>  
    </xsd:complexType>  
</xsd:element>  
```  
  
 <span data-ttu-id="dc07d-113">Für ein Dokument wie z. B. `<root><e1/><e3/></root>`entspricht die Sequenz `<e1/><e3/>` eindeutig der zweiten Sequenz `<xsd:sequence>`.</span><span class="sxs-lookup"><span data-stu-id="dc07d-113">For a document such as `<root><e1/><e3/></root>`, the sequence `<e1/><e3/>` unambiguously matches the second `<xsd:sequence>`.</span></span> <span data-ttu-id="dc07d-114">Da das `<xsd:element>` , dem `<e1/>` entspricht, jedoch nicht ohne Lookahead auf `<e3/>`ermittelt werden kann, verletzt das Inhaltsmodell die UPA-Einschränkungsregel.</span><span class="sxs-lookup"><span data-stu-id="dc07d-114">However, because the `<xsd:element>` to which `<e1/>` corresponds cannot be determined without looking ahead to `<e3/>`, the content model violates the UPA constraint rule.</span></span>  
  
## <a name="finding-more-information"></a><span data-ttu-id="dc07d-115">Weitere Informationsquellen</span><span class="sxs-lookup"><span data-stu-id="dc07d-115">Finding More Information</span></span>  
 <span data-ttu-id="dc07d-116">Das folgende Dokument wird vom W3C (World Wide Web Consortium) veröffentlicht; es enthält die technische Beschreibung der UPA-Einschränkung:</span><span class="sxs-lookup"><span data-stu-id="dc07d-116">The following document is published by the World Wide Web Consortium (W3C) and contains the technical description of the unique particle attribution constraint:</span></span>  
  
 <span data-ttu-id="dc07d-117">"XML Schema Part 1: Structures Second Edition, W3C Proposed Edited Recommendation" (XML Schema Part 1: Strukturen 2. Ausgabe, vom W3C empfohlene Ausgabe):</span><span class="sxs-lookup"><span data-stu-id="dc07d-117">"XML Schema Part 1: Structures Second Edition, W3C Proposed Edited Recommendation":</span></span>  
  
-   <span data-ttu-id="dc07d-118">Abschnitt 3.8.6: Constraints on Model Group Schema Components (Einschränkungen für Komponenten des Modellgruppenschemas)</span><span class="sxs-lookup"><span data-stu-id="dc07d-118">Section 3.8.6: Constraints on Model Group Schema Components</span></span>  
  
-   <span data-ttu-id="dc07d-119">Anhang H: Analysis of the Unique Particle Attribution Constraint (non-normative) (Analyse der Einschränkung für die eindeutige Partikelzuordnung (nicht-normativ))</span><span class="sxs-lookup"><span data-stu-id="dc07d-119">Appendix H: Analysis of the Unique Particle Attribution Constraint (non-normative)</span></span>  
  
 <span data-ttu-id="dc07d-120">Besuchen Sie [http://www.w3.org/TR/xmlschema-1](https://go.microsoft.com/fwlink/?linkid=48881), um das Dokument anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="dc07d-120">To see the document, visit [http://www.w3.org/TR/xmlschema-1](https://go.microsoft.com/fwlink/?linkid=48881).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc07d-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="dc07d-121">See Also</span></span>  
 [<span data-ttu-id="dc07d-122">XML-Schemaauflistungen &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="dc07d-122">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
