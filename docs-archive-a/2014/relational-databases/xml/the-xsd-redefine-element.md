---
title: Das &lt;xsd:redefine&gt;-Element | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xsd:redefine element
ms.assetid: 5f3e9b65-f10e-4db2-a62c-b270ac11d04e
author: rothja
ms.author: jroth
ms.openlocfilehash: ce439e81cf87e97b4afe6e25a201e1ab0cb2a458
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719732"
---
# <a name="the-ltxsdredefinegt-element"></a><span data-ttu-id="3169b-102">Das &lt;xsd:redefine&gt;-Element</span><span class="sxs-lookup"><span data-stu-id="3169b-102">The &lt;xsd:redefine&gt; Element</span></span>
  <span data-ttu-id="3169b-103">Das W3C XSD **redefine** -Element stellt Unterstützung zum Neudefinieren von Schemakomponenten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="3169b-103">The W3C XSD **redefine** element provides support for redefining schema components.</span></span> <span data-ttu-id="3169b-104">Die Unterstützung dieser Direktive kann jedoch die Leistung beeinträchtigen und erfordert außerdem, dass [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] alle Instanzen des Datentyps erneut überprüft werden, die `xml` mit dem neu definierten Schema verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="3169b-104">However, support for this directive is potentially costly to performance and also requires that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] revalidate all instances of the `xml` data type associated with the redefined schema.</span></span> <span data-ttu-id="3169b-105">Deshalb unterstützt [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dieses Element nicht.</span><span class="sxs-lookup"><span data-stu-id="3169b-105">Therefore, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not support this element.</span></span> <span data-ttu-id="3169b-106">XML-Schemas, die das **\<xsd:redefine>** -Element einschließen, werden vom Server abgelehnt.</span><span class="sxs-lookup"><span data-stu-id="3169b-106">XML schemas that include the **\<xsd:redefine>** element are rejected by the server.</span></span>  
  
 <span data-ttu-id="3169b-107">Gehen Sie zum Aktualisieren des Schemas oder seiner Komponenten stattdessen folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="3169b-107">To update a schema or its components, you can do the following instead:</span></span>  
  
1.  <span data-ttu-id="3169b-108">Erstellen Sie eine neue XML-Schemaauflistung mit den geänderten Schemakomponenten.</span><span class="sxs-lookup"><span data-stu-id="3169b-108">Create a new XML Schema collection with the modified schema components.</span></span>  
  
2.  <span data-ttu-id="3169b-109">Geben Sie alle `xml` Datentypen (XML DT) erneut ein, die die XML-Schema Auflistung verwenden, um die neue XML-Schema Auflistung zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3169b-109">Retype all `xml` data types (XML DT) that use the XML Schema collection to be redefined to use the new XML Schema collection instead.</span></span> <span data-ttu-id="3169b-110">Hierzu verwenden Sie die ALTER COLUMN-Option des ALTER TABLE-Befehls, um den Spaltentyp zu ändern, oder Sie ändern die für Variablen oder Parameter geltenden Einschränkungen der XML-Schemaauflistung.</span><span class="sxs-lookup"><span data-stu-id="3169b-110">To do this, use the ALTER COLUMN option of the ALTER TABLE command for retyping columns, or change the XML Schema collection constraints on variables or parameters.</span></span>  
  
3.  <span data-ttu-id="3169b-111">Löschen Sie die alte Version der XML-Schemaauflistung.</span><span class="sxs-lookup"><span data-stu-id="3169b-111">Drop the old version of the XML Schema collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3169b-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3169b-112">See Also</span></span>  
 [<span data-ttu-id="3169b-113">Anforderungen und Einschränkungen für XML-Schemaauflistungen auf dem Server</span><span class="sxs-lookup"><span data-stu-id="3169b-113">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
