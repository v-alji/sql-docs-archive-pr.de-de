---
title: Erstellen eines Finance-Kontos der Dimension "Parent-Child Type" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- dimensions [Analysis Services], account
- account dimensions [Analysis Services]
- adding account intelligence
- account intelligence [Analysis Services]
ms.assetid: 2ba74e81-5b4b-407e-acdf-deb2f6accf0a
author: minewiskan
ms.author: owend
ms.openlocfilehash: ba10e642425628426d9183be2b8d2c4ff751c3ef
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698690"
---
# <a name="create-a-finance-account-of-parent-child-type-dimension"></a><span data-ttu-id="c45de-102">Erstellen eines Finanzkontos des über- und untergeordneten Typs Dimension</span><span class="sxs-lookup"><span data-stu-id="c45de-102">Create a Finance Account of parent-child type Dimension</span></span>
  <span data-ttu-id="c45de-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] handelt es sich bei einer Kontotyp Dimension um eine Dimension, deren Attribute ein Diagramm der Konten für Finanz Berichterstattungs Zwecke darstellen.</span><span class="sxs-lookup"><span data-stu-id="c45de-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)], an account type dimension is a dimension whose attributes represent a chart of accounts for financial reporting purposes.</span></span>  
  
 <span data-ttu-id="c45de-104">Mit einer Kontodimension können Sie selektiv das Aggregationsverhalten für Konten im Lauf der Zeit verwalten.</span><span class="sxs-lookup"><span data-stu-id="c45de-104">An account dimension lets you selectively manage aggregation behavior across accounts over time.</span></span> <span data-ttu-id="c45de-105">Eine Kontodimension ermöglicht auch das Verwenden eines Standardmechanismus, mit dem die meisten der vom Standard abweichenden Aggregationsprobleme behoben werden können, die in Business Intelligence-Projektmappen für den Umgang mit Finanzdaten typischerweise auftreten.</span><span class="sxs-lookup"><span data-stu-id="c45de-105">An account dimension also lets use a standard mechanism to resolve most of the nonstandard aggregation issues typically encountered in business intelligence solutions that handle financial data.</span></span> <span data-ttu-id="c45de-106">Wenn Sie bisher nicht über einen solchen Standardmechanismus verfügt haben, waren zum Beheben dieser vom Standard abweichenden Aggregationsprobleme benutzerdefinierte Rollupformeln, berechnete Elemente oder MDX-Skripts (Multidimensional Expressions) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c45de-106">If you did not have such a standard mechanism, resolving these nonstandard aggregation issues would require custom rollup formulas, calculated members, or Multidimensional Expressions (MDX) scripts.</span></span>  
  
 <span data-ttu-id="c45de-107">Um eine Dimension als eine Kontodimension zu identifizieren, legen Sie die `Type`-Eigenschaft der Dimension auf `Accounts` fest.</span><span class="sxs-lookup"><span data-stu-id="c45de-107">To identify a dimension as an account dimension, set the `Type` property of the dimension to `Accounts`.</span></span>  
  
## <a name="dimension-structure"></a><span data-ttu-id="c45de-108">Dimensionsstruktur</span><span class="sxs-lookup"><span data-stu-id="c45de-108">Dimension Structure</span></span>  
 <span data-ttu-id="c45de-109">Eine Kontodimension enthält mindestens zwei Attribute:</span><span class="sxs-lookup"><span data-stu-id="c45de-109">An account dimension contains, at least, two attributes:</span></span>  
  
-   <span data-ttu-id="c45de-110">Ein Schlüssel Attribut: ein Attribut, das einzelne Konten in der Dimensions Tabelle für die Konto Dimension identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c45de-110">A key attribute-an attribute that identifies individual accounts in the dimension table for the account dimension.</span></span>  
  
-   <span data-ttu-id="c45de-111">Ein Konto Attribut: ein übergeordnetes Attribut, das beschreibt, wie Konten hierarchisch in der Konto Dimension angeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="c45de-111">An account attribute-a parent attribute that describes how accounts are hierarchically arranged in the account dimension.</span></span>  
  
     <span data-ttu-id="c45de-112">Um ein Attribut als Kontoattribut zu identifizieren, legen Sie die `Type`-Eigenschaft des Attributs auf `Account` und die `Usage`-Eigenschaft auf `Parent` fest.</span><span class="sxs-lookup"><span data-stu-id="c45de-112">To identify an attribute as an account attribute, set the `Type` property of the attribute to `Account` and the `Usage` property to `Parent`.</span></span>  
  
 <span data-ttu-id="c45de-113">Kontodimensionen können optional die folgenden Attribute enthalten:</span><span class="sxs-lookup"><span data-stu-id="c45de-113">Account dimensions can optionally contain the following attributes:</span></span>  
  
-   <span data-ttu-id="c45de-114">Ein Kontotyp Attribut: ein Attribut, das den Kontotyp für jedes Konto in der Dimension definiert.</span><span class="sxs-lookup"><span data-stu-id="c45de-114">An account type attribute-an attribute that defines the account type for each account in the dimension.</span></span> <span data-ttu-id="c45de-115">Die Elementnamen des Kontotypattributs sind in den Kontotypen zugeordnet, die für die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank oder das Projekt definiert sind, und geben die Aggregatfunktion an, die von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] für diese Konten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c45de-115">The member names of the account type attribute map to the account types defined for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database or project, and indicate the aggregation function used by [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] for those accounts.</span></span> <span data-ttu-id="c45de-116">Sie können auch unäre Operatoren oder benutzerdefinierte Rollupformeln verwenden, um das Aggregationsverhalten für Kontoattribute zu bestimmen, aber mit Kontotypen können Sie problemlos ein einheitliches Verhalten für ein Kontodiagramm durchsetzen, ohne dass dazu Änderungen an der zugrunde liegenden relationalen Datenbank erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="c45de-116">You can also use unary operators or custom rollup formulas to determine aggregation behavior for account attributes, but account types let you to easily apply consistent behavior to a chart of accounts without requiring changes to the underlying relational database.</span></span>  
  
     <span data-ttu-id="c45de-117">Um ein Kontotypattribut zu identifizieren, legen Sie die `Type`-Eigenschaft des Attributs auf `AccountType` fest.</span><span class="sxs-lookup"><span data-stu-id="c45de-117">To identify an account type attribute, set the `Type` property of the attribute to `AccountType`.</span></span>  
  
-   <span data-ttu-id="c45de-118">Ein Konto Namensattribut-ein Attribut, das zu Berichtszwecken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c45de-118">An account name attribute-an attribute that is used for reporting purposes.</span></span> <span data-ttu-id="c45de-119">Um ein Kontonamenattribut zu identifizieren, legen Sie die `Type`-Eigenschaft des Attributs auf `AccountName` fest.</span><span class="sxs-lookup"><span data-stu-id="c45de-119">You identify an account name attribute by setting the `Type` property of the attribute to `AccountName`.</span></span>  
  
-   <span data-ttu-id="c45de-120">Ein Kontonummern Attribut: ein Attribut, das zu Berichtszwecken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c45de-120">An account number attribute-an attribute that is used for reporting purposes.</span></span> <span data-ttu-id="c45de-121">Um ein Kontonummernattribut zu identifizieren, legen Sie die `Type`-Eigenschaft des Attributs auf `AccountNumber` fest.</span><span class="sxs-lookup"><span data-stu-id="c45de-121">You identify an account number attribute by setting the `Type` property of the attribute to `AccountNumber`.</span></span>  
  
 <span data-ttu-id="c45de-122">Weitere Informationen zu Attributtypen finden Sie unter [Konfigurieren von Attributtypen](attribute-properties-configure-attribute-types.md).</span><span class="sxs-lookup"><span data-stu-id="c45de-122">For more information about attribute types, see [Configure Attribute Types](attribute-properties-configure-attribute-types.md).</span></span>  
  
## <a name="adding-account-intelligence-with-the-business-intelligence-wizard"></a><span data-ttu-id="c45de-123">Hinzufügen von Kontointelligenz mit dem Business Intelligence-Assistenten</span><span class="sxs-lookup"><span data-stu-id="c45de-123">Adding Account Intelligence with the Business Intelligence Wizard</span></span>  
 <span data-ttu-id="c45de-124">Nachdem Sie eine Kontodimension definiert und diese Dimension zu einem Cube hinzugefügt haben, können Sie den Business Intelligence-Assistenten verwenden, um der Dimension Kontointelligenzfunktionalität hinzuzufügen, z. B. zum Identifizieren und Zuordnen von Kontotypen.</span><span class="sxs-lookup"><span data-stu-id="c45de-124">After you have defined an account dimension and added that dimension to a cube, you can use the Business Intelligence Wizard to adding account intelligence functionality, such as identifying and mapping account types, to the dimension.</span></span> <span data-ttu-id="c45de-125">Weitere Informationen finden Sie unter [Hinzufügen von Kontointelligenz zu einer Dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span><span class="sxs-lookup"><span data-stu-id="c45de-125">For more information, see [Add Account Intelligence to a Dimension](bi-wizard-add-account-intelligence-to-a-dimension.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c45de-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c45de-126">See Also</span></span>  
 <span data-ttu-id="c45de-127">[Attribute und Attribut Hierarchien](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span><span class="sxs-lookup"><span data-stu-id="c45de-127">[Attributes and Attribute Hierarchies](../multidimensional-models-olap-logical-dimension-objects/attributes-and-attribute-hierarchies.md) </span></span>  
 <span data-ttu-id="c45de-128">[Business Intelligence Wizard (F1-Hilfe)](../business-intelligence-wizard-f1-help.md) </span><span class="sxs-lookup"><span data-stu-id="c45de-128">[Business Intelligence Wizard F1 Help](../business-intelligence-wizard-f1-help.md) </span></span>  
 [<span data-ttu-id="c45de-129">Dimensionstypen</span><span class="sxs-lookup"><span data-stu-id="c45de-129">Dimension Types</span></span>](../multidimensional-models-olap-logical-dimension-objects/database-dimension-properties-types.md)  
  
  
