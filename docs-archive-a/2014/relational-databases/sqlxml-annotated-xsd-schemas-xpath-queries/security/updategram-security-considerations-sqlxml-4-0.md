---
title: Sicherheitsüberlegungen zu Update grams (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- SQLXML, updategrams
- security [SQLXML], updategrams
- updategrams [SQLXML], security
ms.assetid: 00dc6cf4-a2e8-4cca-bdd6-d5122102a82d
author: rothja
ms.author: jroth
ms.openlocfilehash: eb0319285e6e8cf6e8b3e70f3eb6b9923de06f55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620773"
---
# <a name="updategram-security-considerations-sqlxml-40"></a><span data-ttu-id="397ea-102">Sicherheitsüberlegungen zu Updategrams (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="397ea-102">Updategram Security Considerations (SQLXML 4.0)</span></span>
  <span data-ttu-id="397ea-103">Im Folgenden finden Sie Sicherheitsrichtlinien zur Verwendung von Updategrams:</span><span class="sxs-lookup"><span data-stu-id="397ea-103">The following are security guidelines for using updategrams:</span></span>  
  
-   <span data-ttu-id="397ea-104">Vermeiden Sie die Verwendung von Standardzuordnungen, wenn Sie Daten mithilfe von Updategrams aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="397ea-104">Avoid using default mapping when you use updategrams to update data.</span></span> <span data-ttu-id="397ea-105">Bei Verwendung einer Standardzuordnung wird einem Elementnamen in einem Updategram ein Tabellenname und einem Attributnamen wird eine Spalte zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="397ea-105">When you use default mapping, an element name in an updategram maps to a table name, and an attribute name maps to a column.</span></span> <span data-ttu-id="397ea-106">Dadurch werden die Datentabelle und die Spaltendaten der Datenbank verfügbar gemacht, und dies kann potenziell ein Sicherheitsrisiko darstellen.</span><span class="sxs-lookup"><span data-stu-id="397ea-106">This exposes the database table and column information in the database, which can be a potential security risk.</span></span> <span data-ttu-id="397ea-107">Wenn Sie stattdessen ein eigenes Zuordnungsschema angeben, um die Elemente und Attribute eines Updategrams den Datenbanktabellen und –spalten zuzuordnen, dann können Sie für das Updategram beliebige Element- und Attributnamen wählen und dem Schema die Zuordnung dieser Namen zu Datenbanktabellen und –spalten überlassen.</span><span class="sxs-lookup"><span data-stu-id="397ea-107">Instead, if you specify a separate mapping schema that maps the elements and attributes in an updategram to the database tables and columns, your updategram element and attribute names can be arbitrary, and the schema does necessary mapping of these names to the database tables and columns.</span></span> <span data-ttu-id="397ea-108">So werden die Datenbankinformationen nicht in einem Updategram verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="397ea-108">Thus, the database information is not exposed in an updategram.</span></span>  
  
-   <span data-ttu-id="397ea-109">Lassen Sie nicht zu, dass Benutzer eigene Updategrams erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="397ea-109">Do not allow users to create and execute their updategrams.</span></span> <span data-ttu-id="397ea-110">Updategrams sollten sich in Form von Vorlagen auf dem Server befinden und nicht mithilfe von Anwendungen im ASP-Stil dynamisch erstellt werden, da sonst die Daten der Datenbank gefährdet werden könnten.</span><span class="sxs-lookup"><span data-stu-id="397ea-110">It is recommended having updategrams reside as templates on a server rather than creating them dynamically in ASP-type applications, which could put the data in the database at risk.</span></span> <span data-ttu-id="397ea-111">Dieses Risiko lässt sich ausschließen, indem Benutzer lediglich erlaubt wird, über die als Vorlagen bereitgestellten Updategrams auf die Daten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="397ea-111">Allowing users to access the data only through the updategrams provided as templates, can eliminate this risk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="397ea-112">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="397ea-112">See Also</span></span>  
 [<span data-ttu-id="397ea-113">Verwenden von Updategrams zum Ändern von Daten in SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="397ea-113">Using Updategrams to Modify Data in SQLXML 4.0</span></span>](../updategrams/using-updategrams-to-modify-data-in-sqlxml-4-0.md)  
  
  
