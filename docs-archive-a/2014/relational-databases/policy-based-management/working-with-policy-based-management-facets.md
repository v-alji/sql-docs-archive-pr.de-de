---
title: Arbeiten mit Facets der richtlinienbasierten Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- viewing Policy-Based Management facets
- facets [Policy-Based Management], copying
- facets [Policy-Based Management], viewing
- copying Policy-Based Management facets
ms.assetid: 88d025c4-07c2-4e4d-8634-204249a8c82c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 5a356550796cc682b2292defffd6565b7fea0783
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87615974"
---
# <a name="working-with-policy-based-management-facets"></a><span data-ttu-id="0c79b-102">Arbeiten mit Facets der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="0c79b-102">Working with Policy-Based Management Facets</span></span>
  <span data-ttu-id="0c79b-103">Ein Facet der richtlinienbasierten Verwaltung ist ein Satz von logischen Eigenschaften, die sich auf einen verwaltungsrelevanten Bereich beziehen.</span><span class="sxs-lookup"><span data-stu-id="0c79b-103">A Policy-Based Management facet is a set of logical properties that are related to an area of management interest.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="0c79b-104">umfasst mehrere vordefinierte Facets.</span><span class="sxs-lookup"><span data-stu-id="0c79b-104">includes several predefined facets.</span></span> <span data-ttu-id="0c79b-105">Dazu gehört beispielsweise das Facet für die Oberflächenkonfiguration, das die standardmäßig deaktivierten Funktionen als Eigenschaften definiert.</span><span class="sxs-lookup"><span data-stu-id="0c79b-105">For example, the Surface Area Configuration facet defines, as properties, the features that are off by default.</span></span>  
  
 <span data-ttu-id="0c79b-106">Wenn Sie viele ähnliche [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Umgebungen verwalten, können Sie ein Facet für eine Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]konfigurieren, den Status des Facets in eine Datei kopieren und diese Datei anschließend als Richtlinie in eine andere Instanz von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] importieren.</span><span class="sxs-lookup"><span data-stu-id="0c79b-106">When you manage many similar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] environments, you can configure a facet in one instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], copy the state of the facet to a file, and then import that file into another instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as a policy.</span></span> <span data-ttu-id="0c79b-107">Sobald der Status in eine Richtlinie umgewandelt wurde, kann die Richtlinie auf andere Instanzen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Instanzobjekte, Datenbanken oder Datenbankobjekte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="0c79b-107">When the state has been converted to a policy, the policy can be applied to other instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], instance objects, databases, or database objects.</span></span>  
  
 <span data-ttu-id="0c79b-108">In diesem Thema wird beschrieben, wie der Status eines Facets in eine XML-Datei kopiert wird.</span><span class="sxs-lookup"><span data-stu-id="0c79b-108">This topic describes how to copy the state of a facet to an XML file.</span></span>  
  
##  <a name="permissions"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="0c79b-109">Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="0c79b-109">Permissions</span></span>  
 <span data-ttu-id="0c79b-110">Die Verfahren in diesem Thema erfordern die Mitgliedschaft in der PolicyAdministratorRole-Rolle in der msdb-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="0c79b-110">The procedures in this topic require membership in the PolicyAdministratorRole role in the msdb database.</span></span>  
  
## <a name="viewing-and-copying-facet-states"></a><span data-ttu-id="0c79b-111">Anzeigen und Kopieren von Facet-Status</span><span class="sxs-lookup"><span data-stu-id="0c79b-111">Viewing and Copying Facet States</span></span>  
 [<span data-ttu-id="0c79b-112">Anzeigen der Facets der richtlinienbasierten Verwaltung für ein SQL Server-Objekt</span><span class="sxs-lookup"><span data-stu-id="0c79b-112">View the Policy-Based Management Facets on a SQL Server Object</span></span>](view-the-policy-based-management-facets-on-a-sql-server-object.md)  
  
 [<span data-ttu-id="0c79b-113">Kopieren eines Facet-Status der richtlinienbasierten Verwaltung in eine XML-Datei</span><span class="sxs-lookup"><span data-stu-id="0c79b-113">Copy a Policy-Based Management Facet State to an XML File</span></span>](copy-a-policy-based-management-facet-state-to-an-xml-file.md)  
  
## <a name="see-also"></a><span data-ttu-id="0c79b-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0c79b-114">See Also</span></span>  
 [<span data-ttu-id="0c79b-115">Verwalten von Servern mit der richtlinienbasierten Verwaltung</span><span class="sxs-lookup"><span data-stu-id="0c79b-115">Administer Servers by Using Policy-Based Management</span></span>](administer-servers-by-using-policy-based-management.md)  
  
  
