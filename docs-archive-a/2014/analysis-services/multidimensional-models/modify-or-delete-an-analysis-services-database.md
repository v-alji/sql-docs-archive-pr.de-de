---
title: Ändern oder Löschen einer Analysis Services Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- databases [Analysis Services], modifying
- removing databases
- deleting databases
- dropping databases
- databases [Analysis Services], deleting
- modifying databases
ms.assetid: e48e3988-c091-4379-aabc-4da62f709a7e
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6182e91bd95754fe639e8a48548b5cab1835bdc7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724265"
---
# <a name="modify-or-delete-an-analysis-services-database"></a><span data-ttu-id="d0f65-102">Ändern oder Löschen einer Analysis Services-Datenbank</span><span class="sxs-lookup"><span data-stu-id="d0f65-102">Modify or Delete an Analysis Services Database</span></span>
  <span data-ttu-id="d0f65-103">Sie können den Namen und die Beschreibung einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank vor der Bereitstellung in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] und nach der Bereitstellung in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]ändern.</span><span class="sxs-lookup"><span data-stu-id="d0f65-103">You can change the name and description of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database before deployment in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] and after deployment in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span> <span data-ttu-id="d0f65-104">Sie können darüber hinaus, abhängig von der Umgebung, weitere Einstellungen der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank ändern.</span><span class="sxs-lookup"><span data-stu-id="d0f65-104">You can also adjust additional settings on an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, depending on the environment.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d0f65-105">Im Onlinemodus ist das Ändern der Datenbankeigenschaften mit [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="d0f65-105">You cannot change database properties using [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in online mode.</span></span>  
  
## <a name="modifying-databases-using-sql-server-management-studio"></a><span data-ttu-id="d0f65-106">Ändern von Datenbanken mit SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="d0f65-106">Modifying Databases Using SQL Server Management Studio</span></span>  
 <span data-ttu-id="d0f65-107">Nach dem Bereitstellen einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank können Sie mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] den Identitätswechselmodus ändern, der von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] beim Verbindungsaufbau zu Datenquellen verwendet wird, die in der Datenbank vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="d0f65-107">Once an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database is deployed, you can use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to change the impersonation mode used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] when connecting to data sources contained by the database.</span></span> <span data-ttu-id="d0f65-108">Mit dem Identitätswechselmodus können Sie den Sicherheitskontext angeben, der von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] beim Verbindungsaufbau mit einer Datenquelle verwendet wird, um Daten zu verarbeiten, zu durchsuchen oder um einen Drillthrough durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="d0f65-108">The impersonation mode allows you to specify the security context used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] when attempting to connect to a data source for processing, browsing, or drillthrough purposes.</span></span>  
  
## <a name="modifying-databases-using-sql-server-data-tools"></a><span data-ttu-id="d0f65-109">Ändern von Datenbanken mithilfe von SQL Server-Datentools</span><span class="sxs-lookup"><span data-stu-id="d0f65-109">Modifying Databases Using SQL Server Data Tools</span></span>  
 <span data-ttu-id="d0f65-110">Sie können [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] im Projektmodus verwenden, um die Übersetzungen für die Beschriftung und die Beschreibung eines [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekts zum Definieren einer Datenbank zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d0f65-110">You can use [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] in project mode to modify the translations for the caption and description of an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project used to define a database.</span></span> <span data-ttu-id="d0f65-111">Weitere Informationen zum Verwenden von Übersetzungen in einer- [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank finden Sie unter [Globalisierungs Szenarios für Analysis Services multidimensionalen](../globalization-scenarios-for-analysis-services-multiidimensional.md).</span><span class="sxs-lookup"><span data-stu-id="d0f65-111">For more information about using translations in an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, see [Globalization scenarios for Analysis Services Multiidimensional](../globalization-scenarios-for-analysis-services-multiidimensional.md).</span></span>  
  
 <span data-ttu-id="d0f65-112">Sie können außerdem Aliasse und Aggregationsfunktionen festlegen, die Kontotypen zugeordnet sind, die von den Kontoattributen in Dimensionen in der Datenbank verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d0f65-112">You can also set the aliases and aggregation functions associated with account types used by account attributes in dimensions contained by the database.</span></span> <span data-ttu-id="d0f65-113">Mit Aliassen können Sie die geschäftsspezifische Terminologie auswählen, die von Ihrer Organisation für Kontotypen in einem Kontodiagramm verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d0f65-113">Aliases allow you to select the business-specific terminology used by your organization for the account types in a chart of accounts.</span></span> <span data-ttu-id="d0f65-114">Die Kontotypen werden von Elementen eines Kontoattributs verwendet, um anzugeben, wie Measures über jedem Element mithilfe der für jeden Kontotyp in der Datenbank angegebenen Aggregatfunktionen zusammengefasst werden.</span><span class="sxs-lookup"><span data-stu-id="d0f65-114">The account types are used by members of an account attribute to indicate how to aggregate measures over each member by using the aggregation functions specified for each account type contained in the database.</span></span> <span data-ttu-id="d0f65-115">Weitere Informationen zu Kontoattributen finden Sie unter [Attribute und Attributhierarchien](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md).</span><span class="sxs-lookup"><span data-stu-id="d0f65-115">For more information about account attributes, see [Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md).</span></span>  
  
## <a name="deleting-databases"></a><span data-ttu-id="d0f65-116">Löschen von Datenbanken</span><span class="sxs-lookup"><span data-stu-id="d0f65-116">Deleting Databases</span></span>  
 <span data-ttu-id="d0f65-117">Beim Löschen einer vorhandenen [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank werden die Datenbank und alle Cubes, Dimensionen und Miningmodelle in der Datenbank gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d0f65-117">Deleting an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database deletes the database and all cubes, dimensions, and mining models in the database.</span></span> <span data-ttu-id="d0f65-118">Sie können eine vorhandene [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank nur in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]löschen.</span><span class="sxs-lookup"><span data-stu-id="d0f65-118">You can only delete an existing [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)].</span></span>  
  
#### <a name="to-delete-an-analysis-services-database"></a><span data-ttu-id="d0f65-119">So löschen Sie eine Analysis Services-Datenbank</span><span class="sxs-lookup"><span data-stu-id="d0f65-119">To delete an Analysis Services database</span></span>  
  
1.  <span data-ttu-id="d0f65-120">Stellen Sie eine Verbindung zu einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz her.</span><span class="sxs-lookup"><span data-stu-id="d0f65-120">Connect to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
2.  <span data-ttu-id="d0f65-121">Erweitern Sie im **Objekt-Explorer**den Knoten für die verbundene [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz, und stellen Sie sicher, dass das zu löschende Objekt sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="d0f65-121">In **Object Explorer**, expand the node for the connected [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and ensure that the object to be deleted is visible.</span></span>  
  
3.  <span data-ttu-id="d0f65-122">Klicken Sie mit der rechten Maustaste auf das Objekt, und wählen Sie **Löschen**aus.</span><span class="sxs-lookup"><span data-stu-id="d0f65-122">Right-click the object to be deleted and select **Delete**.</span></span>  
  
4.  <span data-ttu-id="d0f65-123">Klicken Sie im Dialogfeld **Objekt löschen** auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="d0f65-123">In the **Delete Object** dialog box, click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0f65-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d0f65-124">See Also</span></span>  
 [<span data-ttu-id="d0f65-125">Dokumentieren und Skripterstellung einer Analysis Services-Datenbank</span><span class="sxs-lookup"><span data-stu-id="d0f65-125">Document and Script an Analysis Services Database</span></span>](document-and-script-an-analysis-services-database.md)  
  
  
