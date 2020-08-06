---
title: Benennungs Konventionen angeben (Schemagenerierungs-Assistent) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.schemagenwizard.namingconventions.f1
ms.assetid: 02d830ea-5b1f-4485-9f94-d64b8bea592b
author: minewiskan
ms.author: owend
ms.openlocfilehash: 2e9588b49331934041cad888142d29d189fc1a7a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620556"
---
# <a name="specify-naming-conventions-schema-generation-wizard-analysis-services---multidimensional-data"></a><span data-ttu-id="4d171-102">Benennungskonventionen angeben (Schemagenerierungs-Assistent) (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="4d171-102">Specify Naming Conventions (Schema Generation Wizard) (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="4d171-103">Auf der Seite **Benennungskonventionen angeben** definieren Sie die Benennungskonventionen, die bei der Erstellung von Schemaobjekten vom Schemagenerierungs-Assistenten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4d171-103">Use the **Specify Naming Conventions** page to define the naming conventions that the Schema Generation Wizard uses when creating schema objects.</span></span>  
  
## <a name="options"></a><span data-ttu-id="4d171-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4d171-104">Options</span></span>  
 <span data-ttu-id="4d171-105">**Option**</span><span class="sxs-lookup"><span data-stu-id="4d171-105">**Option**</span></span>  
 <span data-ttu-id="4d171-106">Geben Sie die Benennungskonventionen für den zu verwendenden Assistenten an.</span><span class="sxs-lookup"><span data-stu-id="4d171-106">Specify the naming conventions for the wizard to use.</span></span> <span data-ttu-id="4d171-107">In der folgenden Tabelle werden die Optionen beschrieben, die Sie angeben können.</span><span class="sxs-lookup"><span data-stu-id="4d171-107">The following table describes the options you can specify.</span></span>  
  
|<span data-ttu-id="4d171-108">Option</span><span class="sxs-lookup"><span data-stu-id="4d171-108">Option</span></span>|<span data-ttu-id="4d171-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="4d171-109">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4d171-110">**Trennzeichen**</span><span class="sxs-lookup"><span data-stu-id="4d171-110">**Separator**</span></span>|<span data-ttu-id="4d171-111">Gibt das Zeichen an, das zwischen den Wörtern in einem Objektnamen steht.</span><span class="sxs-lookup"><span data-stu-id="4d171-111">Specifies the character that separates words in an object name.</span></span> <span data-ttu-id="4d171-112">Wählen Sie in der **Value** -Spalte **Unterstrich**, **Leerzeichen**oder **Kein**aus.</span><span class="sxs-lookup"><span data-stu-id="4d171-112">In the **Value** column, select **Underscore**, **Space**, or **None**.</span></span> <span data-ttu-id="4d171-113">Der Standardwert ist **Unterstrich**.</span><span class="sxs-lookup"><span data-stu-id="4d171-113">The default is **Underscore**.</span></span>|  
|<span data-ttu-id="4d171-114">**Präfix der Primärschlüsselspalte**</span><span class="sxs-lookup"><span data-stu-id="4d171-114">**Primary key column prefix**</span></span>|<span data-ttu-id="4d171-115">Gibt die Zeichenfolge an, die dem Namen einer Primärschlüsselspalte als Präfix vorangestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4d171-115">Specifies the string to prefix the name of each primary key column.</span></span> <span data-ttu-id="4d171-116">Der Standardwert lautet **PS**.</span><span class="sxs-lookup"><span data-stu-id="4d171-116">The default is **PK**.</span></span>|  
|<span data-ttu-id="4d171-117">**Präfix der Fremdschlüsselspalte**</span><span class="sxs-lookup"><span data-stu-id="4d171-117">**Foreign key column prefix**</span></span>|<span data-ttu-id="4d171-118">Gibt die Zeichenfolge an, die dem Namen einer Fremdschlüsselspalte als Präfix vorangestellt wird.</span><span class="sxs-lookup"><span data-stu-id="4d171-118">Specifies the string to prefix the name of each foreign key column.</span></span> <span data-ttu-id="4d171-119">Der Standardwert lautet **FS**.</span><span class="sxs-lookup"><span data-stu-id="4d171-119">The default is **FK**.</span></span>|  
|<span data-ttu-id="4d171-120">**Attributnamenssuffix**</span><span class="sxs-lookup"><span data-stu-id="4d171-120">**Attribute name suffix**</span></span>|<span data-ttu-id="4d171-121">Gibt die Zeichenfolge an, die an den Namen der einzelnen Attributspalten angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4d171-121">Specifies the string to be appended to the name of each attribute column.</span></span> <span data-ttu-id="4d171-122">Der Standardwert ist " **Name**".</span><span class="sxs-lookup"><span data-stu-id="4d171-122">The default is **Name**.</span></span>|  
|<span data-ttu-id="4d171-123">**Suffix für benutzerdefinierten Rollup**</span><span class="sxs-lookup"><span data-stu-id="4d171-123">**Custom rollup suffix**</span></span>|<span data-ttu-id="4d171-124">Gibt die Zeichenfolge an, die an den Namen der einzelnen Rollupspalten angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4d171-124">Specifies the string to be appended to the name of each rollup column.</span></span> <span data-ttu-id="4d171-125">Der Standardwert lautet **CustomRollup**.</span><span class="sxs-lookup"><span data-stu-id="4d171-125">The default is **CustomRollup**.</span></span>|  
|<span data-ttu-id="4d171-126">**Suffix für benutzerdefinierte Rollupeigenschaften**</span><span class="sxs-lookup"><span data-stu-id="4d171-126">**Custom rollup Properties suffix**</span></span>|<span data-ttu-id="4d171-127">Gibt die Zeichenfolge an, die an den Namen der einzelnen Rollupeigenschaftenspalten angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4d171-127">Specifies the string to be appended to the name of each rollup property column.</span></span> <span data-ttu-id="4d171-128">Der Standardwert lautet **CustomRollupProperties**.</span><span class="sxs-lookup"><span data-stu-id="4d171-128">The default is **CustomRollupProperties**.</span></span>|  
|<span data-ttu-id="4d171-129">**Suffix für unären Operator**</span><span class="sxs-lookup"><span data-stu-id="4d171-129">**Unary operator suffix**</span></span>|<span data-ttu-id="4d171-130">Gibt die Zeichenfolge an, die an den Namen der einzelnen Spalten für unäre Operatoren angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="4d171-130">Specifies the string to be appended to the name of each unary operator column.</span></span> <span data-ttu-id="4d171-131">Die Standardeinstellung lautet **UnaryOperator**.</span><span class="sxs-lookup"><span data-stu-id="4d171-131">The default is **UnaryOperator**.</span></span>|  
  
 <span data-ttu-id="4d171-132">**Wert**</span><span class="sxs-lookup"><span data-stu-id="4d171-132">**Value**</span></span>  
 <span data-ttu-id="4d171-133">Geben Sie einen Wert für die in **Option** angegebene Option an, der bei der Schemagenerierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4d171-133">Specify a value for the option specified in **Option** that you want to use when the schema is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d171-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4d171-134">See Also</span></span>  
 <span data-ttu-id="4d171-135">[Schemagenerierungs-Assistent F1-Hilfe &#40;Analysis Services-mehrdimensionalen Daten&#41;](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="4d171-135">[Schema Generation Wizard F1 Help &#40;Analysis Services - Multidimensional Data&#41;](schema-generation-wizard-f1-help-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="4d171-136">Analysis Services Assistenten &#40;Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="4d171-136">Analysis Services Wizards &#40;Multidimensional Data&#41;</span></span>](analysis-services-wizards-multidimensional-data.md)  
  
  
