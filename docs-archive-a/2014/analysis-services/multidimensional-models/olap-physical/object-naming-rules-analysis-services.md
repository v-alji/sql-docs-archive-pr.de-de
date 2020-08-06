---
title: Benennungs Regeln für Objekte (Analysis Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- objects [Analysis Services], naming
ms.assetid: b338a60d-4802-4b68-862a-6dc6a3f75e48
author: minewiskan
ms.author: owend
ms.openlocfilehash: 6adfd4b23b6fe9129641271fc3c2381e161119ea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620590"
---
# <a name="object-naming-rules-analysis-services"></a><span data-ttu-id="4e416-102">Objektbenennungsregeln (Analysis Services)</span><span class="sxs-lookup"><span data-stu-id="4e416-102">Object Naming Rules (Analysis Services)</span></span>
  <span data-ttu-id="4e416-103">In diesem Thema werden Benennungskonventionen für Objekte sowie reservierte Wörter und Zeichen beschrieben, die in Objektnamen, in Code oder Skripts in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)] nicht verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4e416-103">This topic describes object naming conventions, as well as the reserved words and characters that cannot be used in any object name, in code or script in [!INCLUDE[ssASnoversion](../../../includes/ssasnoversion-md.md)].</span></span>  
  
##  <a name="naming-conventions"></a><a name="bkmk_Names"></a><span data-ttu-id="4e416-104">Benennungs Konventionen</span><span class="sxs-lookup"><span data-stu-id="4e416-104">Naming Conventions</span></span>  
 <span data-ttu-id="4e416-105">Jedes Objekt verfügt über eine `Name`-Eigenschaft und eine `ID`-Eigenschaft, die innerhalb des Bereichs der übergeordneten Auflistung eindeutig sein müssen.</span><span class="sxs-lookup"><span data-stu-id="4e416-105">Every object has a `Name` and `ID` property that must be unique within the scope of the parent collection.</span></span> <span data-ttu-id="4e416-106">Beispielsweise können zwei Dimensionen denselben Namen haben, solange sich beide in unterschiedlichen Datenbanken befinden.</span><span class="sxs-lookup"><span data-stu-id="4e416-106">For example, two dimensions can have same name as long as each one resides in a different database.</span></span>  
  
 <span data-ttu-id="4e416-107">Sie können die `ID` manuell eingeben. In der Regel wird diese jedoch automatisch beim Erstellen des Objekts generiert.</span><span class="sxs-lookup"><span data-stu-id="4e416-107">Although you can specify it manually, the `ID` is typically auto-generated when the object is created.</span></span> <span data-ttu-id="4e416-108">Die `ID` sollte nicht mehr geändert werden, nachdem Sie mit dem Erstellen eines Modells begonnen haben.</span><span class="sxs-lookup"><span data-stu-id="4e416-108">You should never change the `ID` once you have begun building a model.</span></span> <span data-ttu-id="4e416-109">Alle Objektverweise im gesamten Modell basieren auf der `ID`.</span><span class="sxs-lookup"><span data-stu-id="4e416-109">All object references throughout a model are based on the `ID`.</span></span> <span data-ttu-id="4e416-110">Daher kann das Ändern der `ID` sehr schnell zu Fehlern im Modell führen.</span><span class="sxs-lookup"><span data-stu-id="4e416-110">Thus, changing an `ID` can easily result in model corruption.</span></span>  
  
 <span data-ttu-id="4e416-111">Bei den Benennungskonventionen für `DataSource`-Objekte und `DataSourceView`-Objekte gelten keine nennenswerten Ausnahmen.</span><span class="sxs-lookup"><span data-stu-id="4e416-111">`DataSource` and `DataSourceView` objects have notable exceptions to naming conventions.</span></span> <span data-ttu-id="4e416-112">Die `DataSource`-ID kann auf einen einzelnen Punkt (.) festgelegt werden, der als Verweis auf die aktuelle Datenbank dient, aber nicht eindeutig ist.</span><span class="sxs-lookup"><span data-stu-id="4e416-112">`DataSource` ID can be set to a single dot (.), which is not unique, as a reference to the current database.</span></span> <span data-ttu-id="4e416-113">Eine zweite Ausnahme bildet das `DataSourceView`-Objekt, das der für `DataSet`-Objekte in .NET Framework definierten Benennungskonvention folgt, bei der `Name` als Bezeichner verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4e416-113">A second exception is `DataSourceView`, which adheres to the naming conventions defined for `DataSet` objects in the .NET Framework, where the `Name` is used as the identifier.</span></span>  
  
 <span data-ttu-id="4e416-114">Die folgenden Regeln gelten für `Name`-Eigenschaften und `ID`-Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="4e416-114">The following rules apply to `Name` and `ID` properties.</span></span>  
  
-   <span data-ttu-id="4e416-115">Bei den Namen wird die Groß-/Kleinschreibung nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="4e416-115">Names are case insensitive.</span></span> <span data-ttu-id="4e416-116">Ein Cube mit dem Namen "Sales" und ein anderer mit dem Namen "Sales" können nicht in derselben Datenbank vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="4e416-116">You cannot have a cube named "sales" and another named "Sales" in the same database.</span></span>  
  
-   <span data-ttu-id="4e416-117">Führende oder nachfolgende Leerzeichen sind in Objektnamen nicht zulässig. Innerhalb des Namens können Leerzeichen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4e416-117">No leading or trailing spaces allowed in an object name, although you can embed spaces within a name.</span></span> <span data-ttu-id="4e416-118">Führende und nachstehende Leerzeichen werden implizit abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="4e416-118">Leading and trailing spaces are implicitly trimmed.</span></span> <span data-ttu-id="4e416-119">Dies gilt für die `Name`-Eigenschaft und die `ID`-Eigenschaft eines Objekts.</span><span class="sxs-lookup"><span data-stu-id="4e416-119">This applies to both the `Name` and `ID` of an object.</span></span>  
  
-   <span data-ttu-id="4e416-120">Es können maximal 100 Zeichen eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4e416-120">The maximum number of characters is 100.</span></span>  
  
-   <span data-ttu-id="4e416-121">Es gibt keine besondere Anforderung für das erste Zeichen eines Bezeichners.</span><span class="sxs-lookup"><span data-stu-id="4e416-121">There is no special requirement for the first character of an identifier.</span></span> <span data-ttu-id="4e416-122">Das erste Zeichen kann ein beliebiges gültiges Zeichen sein.</span><span class="sxs-lookup"><span data-stu-id="4e416-122">The first character may be any valid character.</span></span>  
  
##  <a name="reserved-words-and-characters"></a><a name="bkmk_reserved"></a><span data-ttu-id="4e416-123">Reservierte Wörter und Zeichen</span><span class="sxs-lookup"><span data-stu-id="4e416-123">Reserved Words and Characters</span></span>  
 <span data-ttu-id="4e416-124">Reservierte Wörter sind auf Englisch und gelten für Objektnamen, nicht für Beschriftungen.</span><span class="sxs-lookup"><span data-stu-id="4e416-124">Reserved words are in English, and apply to object names, not Captions.</span></span> <span data-ttu-id="4e416-125">Falls Sie ein reserviertes Wort versehentlich in einem Objektnamen verwenden, tritt ein Überprüfungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="4e416-125">If you inadvertently use a reserved word in an object name, a validation error will occur.</span></span> <span data-ttu-id="4e416-126">Die unten aufgeführten reservierten Wörter dürfen in keinem Fall in Objektnamen für mehrdimensionale Modelle und Data Mining-Modelle verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4e416-126">For multidimensional and data mining models, the reserved words described below cannot be used in any object name, at any time.</span></span>  
  
 <span data-ttu-id="4e416-127">Bei tabellarischen Modellen mit dem Datenbank-Kompatibilitätsgrad 1103 wurden die Überprüfungsregeln für bestimmte Objekte gelockert, um zu gewährleisten, dass sie mit den Anforderungen an erweiterte Zeichen und Benennungskonventionen bestimmter Clientanwendungen kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="4e416-127">For tabular models, where the database compatibility is set to 1103, validation rules have been relaxed for certain objects, out of compliance for the extended character requirements and naming conventions of certain client applications.</span></span> <span data-ttu-id="4e416-128">Datenbanken, die diese Kriterien erfüllen, unterliegen weniger strengen Überprüfungsregeln.</span><span class="sxs-lookup"><span data-stu-id="4e416-128">Databases that meet these criteria are subject to less stringent validation rules.</span></span> <span data-ttu-id="4e416-129">In diesem Fall kann ein Objekt die Überprüfung bestehen, obwohl es ein eingeschränktes Zeichen enthält.</span><span class="sxs-lookup"><span data-stu-id="4e416-129">In this case, it's possible for an object name to include a restricted character and still pass validation.</span></span>  
  
 <span data-ttu-id="4e416-130">**Reservierte Wörter**</span><span class="sxs-lookup"><span data-stu-id="4e416-130">**Reserved Words**</span></span>  
  
-   <span data-ttu-id="4e416-131">AUX</span><span class="sxs-lookup"><span data-stu-id="4e416-131">AUX</span></span>  
  
-   <span data-ttu-id="4e416-132">CLOCK$</span><span class="sxs-lookup"><span data-stu-id="4e416-132">CLOCK$</span></span>  
  
-   <span data-ttu-id="4e416-133">COM1 bis COM9 (COM1, COM2, COM3 usw.)</span><span class="sxs-lookup"><span data-stu-id="4e416-133">COM1 through COM9 (COM1, COM2, COM3, and so on)</span></span>  
  
-   <span data-ttu-id="4e416-134">CON</span><span class="sxs-lookup"><span data-stu-id="4e416-134">CON</span></span>  
  
-   <span data-ttu-id="4e416-135">LPT1 bis LPT9 (LPT1, LPT2, LPT3 usw.)</span><span class="sxs-lookup"><span data-stu-id="4e416-135">LPT1 through LPT9 (LPT1, LPT2, LPT3, and so on)</span></span>  
  
-   <span data-ttu-id="4e416-136">NUL</span><span class="sxs-lookup"><span data-stu-id="4e416-136">NUL</span></span>  
  
-   <span data-ttu-id="4e416-137">PRN</span><span class="sxs-lookup"><span data-stu-id="4e416-137">PRN</span></span>  
  
-   <span data-ttu-id="4e416-138">NULL ist in XML in keiner Zeichenfolge als Zeichen zulässig.</span><span class="sxs-lookup"><span data-stu-id="4e416-138">NULL is not allowed as a character in any string within the XML</span></span>  
  
 <span data-ttu-id="4e416-139">**Reservierte Zeichen**</span><span class="sxs-lookup"><span data-stu-id="4e416-139">**Reserved Characters**</span></span>  
  
 <span data-ttu-id="4e416-140">In der folgenden Tabelle werden die ungültigen Zeichen für bestimmte Objekte aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="4e416-140">The following table lists invalid characters for specific objects.</span></span>  
  
|<span data-ttu-id="4e416-141">Object</span><span class="sxs-lookup"><span data-stu-id="4e416-141">Object</span></span>|<span data-ttu-id="4e416-142">Ungültige Zeichen</span><span class="sxs-lookup"><span data-stu-id="4e416-142">Invalid characters</span></span>|  
|------------|------------------------|  
|`Server`|<span data-ttu-id="4e416-143">Befolgen Sie beim Benennen von Serverobjekten die Benennungskonventionen für Windows-Server.</span><span class="sxs-lookup"><span data-stu-id="4e416-143">Follow Windows server naming conventions when naming a server object.</span></span> <span data-ttu-id="4e416-144">Weitere Informationen finden Sie unter [Benennungs Konventionen (Windows)](/windows/desktop/DNS/naming-conventions) .</span><span class="sxs-lookup"><span data-stu-id="4e416-144">See [Naming Conventions (Windows)](/windows/desktop/DNS/naming-conventions) for details.</span></span>|  
|`DataSource`| `: / \ * \| ? " () [] {} <>` |  
|<span data-ttu-id="4e416-145">`Level` oder `Attribute`</span><span class="sxs-lookup"><span data-stu-id="4e416-145">`Level` or `Attribute`</span></span>|````. , ; ' ` : / \ * & \| ? " & % $ ! + = [] {} < >````|  
|<span data-ttu-id="4e416-146">`Dimension` oder `Hierarchy`</span><span class="sxs-lookup"><span data-stu-id="4e416-146">`Dimension` or `Hierarchy`</span></span>|````. , ; ' ` : / \ * \| ? " & % $ ! + = () [] {} <,>````|  
|<span data-ttu-id="4e416-147">Alle anderen Objekte</span><span class="sxs-lookup"><span data-stu-id="4e416-147">All other objects</span></span>|````. , ; ' ` : / \ * \| ? " & % $ ! + = () [] {} < >````|  
  
 <span data-ttu-id="4e416-148">**Ausnahmen: Wenn reservierte Zeichen zulässig sind**</span><span class="sxs-lookup"><span data-stu-id="4e416-148">**Exceptions: When Reserved Characters are Allowed**</span></span>  
  
 <span data-ttu-id="4e416-149">Wie bereits erwähnt, können Datenbanken mit einem bestimmten Modalitäts- und Kompatibilitätsgrad Objektnamen enthalten, die reservierte Zeichen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4e416-149">As noted, databases of a specific modality and compatibility level can have object names that include reserved characters.</span></span> <span data-ttu-id="4e416-150">Dimensionsattribut-, Hierarchie-, Ebenen-, Measure- und KPI-Objektnamen für tabellarische Datenbanken (1103 oder höher) können reservierte Zeichen enthalten, wenn diese Datenbanken die Verwendung erweiterter Zeichen zulassen:</span><span class="sxs-lookup"><span data-stu-id="4e416-150">Dimension attribute, hierarchy, level, measure and KPI object names can include reserved characters, for tabular databases (1103 or higher) that allow the use of extended characters:</span></span>  
  
|<span data-ttu-id="4e416-151">Servermodus und Datenbank-Kompatibilitätsgrad</span><span class="sxs-lookup"><span data-stu-id="4e416-151">Server mode and database compatibility level</span></span>|<span data-ttu-id="4e416-152">Reservierte Zeichen zulässig?</span><span class="sxs-lookup"><span data-stu-id="4e416-152">Reserved characters allowed?</span></span>|  
|--------------------------------------------------|----------------------------------|  
|<span data-ttu-id="4e416-153">MOLAP (alle Versionen)</span><span class="sxs-lookup"><span data-stu-id="4e416-153">MOLAP (all versions)</span></span>|<span data-ttu-id="4e416-154">Nein</span><span class="sxs-lookup"><span data-stu-id="4e416-154">No</span></span>|  
|<span data-ttu-id="4e416-155">Tabellarischer Modus - 1050</span><span class="sxs-lookup"><span data-stu-id="4e416-155">Tabular - 1050</span></span>|<span data-ttu-id="4e416-156">Nein</span><span class="sxs-lookup"><span data-stu-id="4e416-156">No</span></span>|  
|<span data-ttu-id="4e416-157">Tabellarischer Modus - 1100</span><span class="sxs-lookup"><span data-stu-id="4e416-157">Tabular - 1100</span></span>|<span data-ttu-id="4e416-158">Nein</span><span class="sxs-lookup"><span data-stu-id="4e416-158">No</span></span>|  
|<span data-ttu-id="4e416-159">Tabellarisch-1130 und höher</span><span class="sxs-lookup"><span data-stu-id="4e416-159">Tabular - 1130 and higher</span></span>|<span data-ttu-id="4e416-160">Ja</span><span class="sxs-lookup"><span data-stu-id="4e416-160">Yes</span></span>|  
  
 <span data-ttu-id="4e416-161">ModelType kann für Datenbanken auf default festgelegt sein.</span><span class="sxs-lookup"><span data-stu-id="4e416-161">Databases can have a ModelType of default.</span></span> <span data-ttu-id="4e416-162">Da default mit multidimensional identisch ist, werden reservierte Zeichen in Spaltennamen folglich nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4e416-162">Default is equivalent to multidimensional, and thus does not support the use of reserved characters in column names.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e416-163">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4e416-163">See Also</span></span>  
 <span data-ttu-id="4e416-164">[Reservierte MDX-Wörter](/sql/mdx/mdx-reserved-words) </span><span class="sxs-lookup"><span data-stu-id="4e416-164">[MDX Reserved Words](/sql/mdx/mdx-reserved-words) </span></span>  
 <span data-ttu-id="4e416-165">[Übersetzungen &#40;Analysis Services&#41;](/analysis-services/translation-support-in-analysis-services) </span><span class="sxs-lookup"><span data-stu-id="4e416-165">[Translations &#40;Analysis Services&#41;](/analysis-services/translation-support-in-analysis-services) </span></span>  
 [<span data-ttu-id="4e416-166">XML for Analysis Konformität &#40;XMLA&#41;</span><span class="sxs-lookup"><span data-stu-id="4e416-166">XML for Analysis Compliance &#40;XMLA&#41;</span></span>](https://docs.microsoft.com/bi-reference/xmla/xml-for-analysis-compliance-xmla)  
  
  
