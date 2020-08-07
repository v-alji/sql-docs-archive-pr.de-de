---
title: Aktivieren und Deaktivieren von RDL-Sandkasten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: d5619e9f-ec5b-4376-9b34-1f74de6fade7
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 7af1477751093862c99d00978278315e600511e7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719618"
---
# <a name="enable-and-disable-rdl-sandboxing"></a><span data-ttu-id="3fdfc-102">Aktivieren und Deaktivieren von RDL-Sandkasten</span><span class="sxs-lookup"><span data-stu-id="3fdfc-102">Enable and Disable RDL Sandboxing</span></span>
  <span data-ttu-id="3fdfc-103">Mithilfe der Sandkastenfunktion der RDL (Report Definition Language, Berichtsdefinitionssprache) können Sie die Verwendung bestimmter Ressourcentypen durch einzelne Mandanten in einer Umgebung erkennen und einschränken, in der mehrere Mandanten eine einzelne Webfarm von Berichtsservern verwenden.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-103">The RDL (Report Definition Language) Sandboxing feature lets you detect and restrict the usage of specific types of resources, by individual tenants, in an environment of multiple tenants that use a single web farm of report servers.</span></span> <span data-ttu-id="3fdfc-104">Ein Beispiel hierfür ist ein Szenario mit einem Hostingdienst, in dem eine einzelne Webfarm mit Berichtsservern verwaltet wird, die von mehreren Mandanten und möglicherweise auch unterschiedlichen Firmen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-104">An example of this is a hosting services scenario where you might maintain a single web farm of report servers that are used by multiple tenants, and perhaps different companies.</span></span> <span data-ttu-id="3fdfc-105">Als Berichtsserveradministrator können Sie diese Funktion aktivieren, um die folgenden Zielsetzungen zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="3fdfc-105">As a report server administrator, you can enable this feature to help achieve the following objectives:</span></span>  
  
-   <span data-ttu-id="3fdfc-106">Beschränken der Größen externer Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-106">Restrict external resource sizes.</span></span> <span data-ttu-id="3fdfc-107">Externe Ressourcen sind Bilder, XSLT-Dateien und Kartendaten.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-107">External resources include images, .xslt files, and map data.</span></span>  
  
-   <span data-ttu-id="3fdfc-108">Beschränken der Typen und Elemente, die in Ausdruckstext verwendet werden, zum Veröffentlichungszeitpunkt des Berichts.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-108">At report publish time, limit types and members that are used in expression text.</span></span>  
  
-   <span data-ttu-id="3fdfc-109">Beschränken der Länge des Texts und der Größe des Rückgabewerts für Ausdrücke zur Berichtsverarbeitungszeit.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-109">At report processing time, limit the length of the text and the size of the return value for expressions.</span></span>  
  
 <span data-ttu-id="3fdfc-110">Bei Aktivierung des RDL-Sandboxing werden die folgenden Funktionen deaktiviert:</span><span class="sxs-lookup"><span data-stu-id="3fdfc-110">When RDL Sandboxing is enabled, the following features are disabled:</span></span>  
  
-   <span data-ttu-id="3fdfc-111">Benutzerdefinierter Code im- **\<Code>** Element einer Berichtsdefinition.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-111">Custom code in the **\<Code>** element of a report definition.</span></span>  
  
-   <span data-ttu-id="3fdfc-112">RDL-Abwärtskompatibilitätsmodus für benutzerdefinierte Berichtselemente von [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3fdfc-112">RDL backward compatibility mode for [!INCLUDE[ssRSversion2005](../includes/ssrsversion2005-md.md)] custom report items.</span></span>  
  
-   <span data-ttu-id="3fdfc-113">Benannte Parameter in Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-113">Named parameters in expressions.</span></span>  
  
 <span data-ttu-id="3fdfc-114">In diesem Thema werden die einzelnen Elemente im <`RDLSandboxing`>-Element in der RSReportServer.Config-Datei beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-114">This topic describes each element in the <`RDLSandboxing`> element in the RSReportServer.Config file.</span></span> <span data-ttu-id="3fdfc-115">Weitere Informationen zum Ändern dieser Datei finden Sie unter [Ändern einer Reporting Services-Konfigurationsdatei &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span><span class="sxs-lookup"><span data-stu-id="3fdfc-115">For more information about how to modify this file, see [Modify a Reporting Services Configuration File &#40;RSreportserver.config&#41;](report-server/modify-a-reporting-services-configuration-file-rsreportserver-config.md).</span></span> <span data-ttu-id="3fdfc-116">In einem Server-Ablaufverfolgungsprotokoll werden Aktivitäten aufgezeichnet, die sich auf die RDL-Sandboxingfunktion beziehen.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-116">A server trace log records activity related to the RDL Sandboxing feature.</span></span> <span data-ttu-id="3fdfc-117">Weitere Informationen zu Ablaufverfolgungsprotokollen finden Sie unter [Berichtsserverdienst-Ablaufverfolgungsprotokoll](report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="3fdfc-117">For more information about trace logs, see [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span></span>  
  
## <a name="example-configuration"></a><span data-ttu-id="3fdfc-118">Beispielkonfiguration</span><span class="sxs-lookup"><span data-stu-id="3fdfc-118">Example Configuration</span></span>  
 <span data-ttu-id="3fdfc-119">Im folgenden Beispiel werden die Einstellungen und Beispiel Werte für das <`RDLSandboxing`>-Element in der RSReportServer.Config-Datei gezeigt.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-119">The following example shows the settings and example values for the <`RDLSandboxing`> element in the RSReportServer.Config file.</span></span>  
  
```  
<RDLSandboxing>  
   <MaxExpressionLength>5000</MaxExpressionLength>  
   <MaxResourceSize>5000</MaxResourceSize>  
   <MaxStringResultLength>3000</MaxStringResultLength>  
   <MaxArrayResultLength>250</MaxArrayResultLength>  
   <Types>  
      <Allow Namespace="System.Drawing" AllowNew="True">Bitmap</Allow>  
      <Allow Namespace="TypeConverters.Custom" AllowNew="True">*</Allow>  
   </Types>  
   <Members>  
      <Deny>Format</Deny>  
      <Deny>StrDup</Deny>  
   </Members>  
</RDLSandboxing>  
```  
  
## <a name="configuration-settings"></a><span data-ttu-id="3fdfc-120">Konfigurationseinstellungen</span><span class="sxs-lookup"><span data-stu-id="3fdfc-120">Configuration Settings</span></span>  
 <span data-ttu-id="3fdfc-121">Die folgende Tabelle enthält Informationen zu Konfigurationseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-121">The following table provides information about configuration settings.</span></span> <span data-ttu-id="3fdfc-122">Diese Einstellungen werden in der Reihenfolge aufgeführt, in der sie in der Konfigurationsdatei angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-122">Settings are presented in the order in which they appear in the configuration file.</span></span>  
  
|<span data-ttu-id="3fdfc-123">Einstellung</span><span class="sxs-lookup"><span data-stu-id="3fdfc-123">Setting</span></span>|<span data-ttu-id="3fdfc-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="3fdfc-124">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3fdfc-125">**MaxExpressionLength**</span><span class="sxs-lookup"><span data-stu-id="3fdfc-125">**MaxExpressionLength**</span></span>|<span data-ttu-id="3fdfc-126">Maximale Anzahl von Zeichen, die in RDL-Ausdrücken zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-126">Maximum number of characters allowed in RDL expressions.</span></span><br /><br /> <span data-ttu-id="3fdfc-127">Standard: 1000</span><span class="sxs-lookup"><span data-stu-id="3fdfc-127">Default: 1000</span></span>|  
|<span data-ttu-id="3fdfc-128">**MaxResourceSize**</span><span class="sxs-lookup"><span data-stu-id="3fdfc-128">**MaxResourceSize**</span></span>|<span data-ttu-id="3fdfc-129">Maximale Anzahl von KB, die für eine externe Ressource zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-129">Maximum number of KB allowed for an external resource.</span></span><br /><br /> <span data-ttu-id="3fdfc-130">Standard: 100</span><span class="sxs-lookup"><span data-stu-id="3fdfc-130">Default: 100</span></span>|  
|<span data-ttu-id="3fdfc-131">**MaxStringResultLength**</span><span class="sxs-lookup"><span data-stu-id="3fdfc-131">**MaxStringResultLength**</span></span>|<span data-ttu-id="3fdfc-132">Maximale Anzahl von Zeichen, die für einen Rückgabewert für einen RDL-Ausdruck zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-132">Maximum number of characters allowed in a return value for an RDL expression.</span></span><br /><br /> <span data-ttu-id="3fdfc-133">Standard: 1000</span><span class="sxs-lookup"><span data-stu-id="3fdfc-133">Default: 1000</span></span>|  
|<span data-ttu-id="3fdfc-134">**MaxArrayResultLength**</span><span class="sxs-lookup"><span data-stu-id="3fdfc-134">**MaxArrayResultLength**</span></span>|<span data-ttu-id="3fdfc-135">Maximale Anzahl von Elementen, die für einen Rückgabewert vom Typ "Array" für einen RDL-Ausdruck zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-135">Maximum number of items allowed in an array return value for an RDL expression.</span></span><br /><br /> <span data-ttu-id="3fdfc-136">Standard: 100</span><span class="sxs-lookup"><span data-stu-id="3fdfc-136">Default: 100</span></span>|  
|<span data-ttu-id="3fdfc-137">**Typen**</span><span class="sxs-lookup"><span data-stu-id="3fdfc-137">**Types**</span></span>|<span data-ttu-id="3fdfc-138">Die Liste der Elemente, die innerhalb von RDL-Ausdrücken zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-138">The list of members to allow within RDL expressions.</span></span>|  
|<span data-ttu-id="3fdfc-139">**Zulassen**</span><span class="sxs-lookup"><span data-stu-id="3fdfc-139">**Allow**</span></span>|<span data-ttu-id="3fdfc-140">Ein Typ oder ein Satz von Typen, die in RDL-Ausdrücken zugelassen sind.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-140">A type or set of types to allow in RDL expressions.</span></span>|  
|<span data-ttu-id="3fdfc-141">**Namespace**</span><span class="sxs-lookup"><span data-stu-id="3fdfc-141">**Namespace**</span></span>|<span data-ttu-id="3fdfc-142">Attribut für **Erlauben** , das den Namespace darstellt, der mindestens einen gültigen Typ für Value enthält.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-142">Attribute for **Allow** that is the namespace that contains one or more types that apply to Value.</span></span> <span data-ttu-id="3fdfc-143">Bei dieser Eigenschaft wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-143">This property is case-insensitive.</span></span>|  
|`AllowNew`|<span data-ttu-id="3fdfc-144">Ein boolesches Attribut für **Allow** , mit dem gesteuert wird, ob neue Instanzen des Typs in RDL-Ausdrücken oder in einem RDL-Element erstellt werden dürfen **\<Class>** .</span><span class="sxs-lookup"><span data-stu-id="3fdfc-144">Boolean attribute for **Allow** that controls whether new instances of the type are allowed to be created in RDL expressions or in an RDL **\<Class>** element.</span></span><br /><br /> <span data-ttu-id="3fdfc-145">Hinweis: Wenn `RDLSandboxing` aktiviert ist, können in RDL-Ausdrücken keine neuen Arrays erstellt werden, unabhängig von der Einstellung von `AllowNew` .</span><span class="sxs-lookup"><span data-stu-id="3fdfc-145">Note: When `RDLSandboxing` is enabled, new arrays cannot be created in RDL expressions, regardless of the setting of `AllowNew`.</span></span>|  
|<span data-ttu-id="3fdfc-146">**Wert**</span><span class="sxs-lookup"><span data-stu-id="3fdfc-146">**Value**</span></span>|<span data-ttu-id="3fdfc-147">Wert für **Allow** , der den Namen des in RDL-Ausdrücken zuzulassenden Typs angibt.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-147">Value for **Allow** that is the name of the type to allow in RDL expressions.</span></span> <span data-ttu-id="3fdfc-148">Der Wert **\*** gibt an, dass alle Typen im-Namespace zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-148">The value **\*** indicates that all types in the namespace are allowed.</span></span> <span data-ttu-id="3fdfc-149">Bei dieser Eigenschaft wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-149">This property is case-insensitive.</span></span>|  
|<span data-ttu-id="3fdfc-150">**Mitglieder**</span><span class="sxs-lookup"><span data-stu-id="3fdfc-150">**Members**</span></span>|<span data-ttu-id="3fdfc-151">Die Liste der Typen, die im-Element enthalten sind **\<Types>** , ist die Liste der Elementnamen, die in RDL-Ausdrücken nicht zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-151">For the list of types that are include in the **\<Types>** element, the list of member names that are not allowed in RDL expressions.</span></span>|  
|<span data-ttu-id="3fdfc-152">**Deny**</span><span class="sxs-lookup"><span data-stu-id="3fdfc-152">**Deny**</span></span>|<span data-ttu-id="3fdfc-153">Der Name eines Elements, das nicht in RDL-Ausdrücken zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-153">The name of a member that is not allowed in RDL expressions.</span></span> <span data-ttu-id="3fdfc-154">Bei dieser Eigenschaft wird die Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-154">This property is case-insensitive.</span></span><br /><br /> <span data-ttu-id="3fdfc-155">Hinweis: Wenn **Deny** für ein Element angegeben wird, werden alle Elemente mit diesem Namen für alle Typen nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-155">Note: When **Deny** is specified for a member, all members with this name for all types are not allowed.</span></span>|  
  
## <a name="working-with-expressions-when-rdl-sandboxing-is-enabled"></a><span data-ttu-id="3fdfc-156">Arbeiten mit Ausdrücken bei aktiviertem RDL-Sandboxing</span><span class="sxs-lookup"><span data-stu-id="3fdfc-156">Working with Expressions when RDL Sandboxing is Enabled</span></span>  
 <span data-ttu-id="3fdfc-157">Sie können die RDL-Sandboxingfunktion auf die folgenden Weisen ändern, um die von einem Ausdruck verwendeten Ressourcen zu verwalten:</span><span class="sxs-lookup"><span data-stu-id="3fdfc-157">You can modify the RDL Sandboxing feature to help manage the resources that are used by an expression in the following ways:</span></span>  
  
-   <span data-ttu-id="3fdfc-158">Schränken Sie die Anzahl von Zeichen ein, die für einen Ausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-158">Restrict the number of characters that are used for an expression.</span></span>  
  
-   <span data-ttu-id="3fdfc-159">Schränken Sie die Größe des Ergebnisses ein, das von einem Ausdruck zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-159">Restrict the size of the result returned by an expression.</span></span>  
  
-   <span data-ttu-id="3fdfc-160">Lassen Sie eine bestimmte Liste von Typen zu, die in einem Ausdruck verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-160">Allow a specific list of types that can be used in an expression.</span></span>  
  
-   <span data-ttu-id="3fdfc-161">Schränken Sie die Liste der Elemente anhand ihrer Namen für die Liste von zulässigen Typen ein, die in einem Ausdruck verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-161">Restrict the list of members by name for the list of allowed types that can be used in an expression.</span></span>  
  
-   <span data-ttu-id="3fdfc-162">Mithilfe der RDL-Sandboxingfunktion können Sie eine Liste genehmigter Typen und eine Liste verweigerter Elemente erstellen.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-162">The RDL Sandboxing feature enables you to create a list of approved types and a list of denied members.</span></span> <span data-ttu-id="3fdfc-163">Die Liste der genehmigten Typen wird als Zulassungsliste bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-163">The list of approved types is called an allow list.</span></span> <span data-ttu-id="3fdfc-164">Die Liste der verweigerten Elemente wird als Sperrliste bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-164">The list of denied members is called a block list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="3fdfc-165">In der Berichtsdefinition ist der Typ der einzelnen Instanzen eines Ausdrucksverweises nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-165">In the report definition, a computer cannot know the type of each instances of an expression reference.</span></span> <span data-ttu-id="3fdfc-166">Wenn Sie der Sperrliste ein Element hinzufügen, verweigern Sie alle Elemente dieses Namens für alle Typen in der Zulassungsliste.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-166">When you add a member to the block list, you are denying all members of that name across all types in the allow list.</span></span>  
  
 <span data-ttu-id="3fdfc-167">Ergebnisse von RDL-Ausdrücken werden zur Laufzeit überprüft.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-167">RDL expression results are verified at run time.</span></span> <span data-ttu-id="3fdfc-168">RDL-Ausdrücke werden in die Berichtsdefinition überprüft, wenn der Bericht veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-168">RDL expressions are verified in the report definition when the report is published.</span></span> <span data-ttu-id="3fdfc-169">Überwachen Sie das Ablaufverfolgungsprotokoll des Berichtsservers auf Verstöße.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-169">Monitor the report server trace log for violations.</span></span> <span data-ttu-id="3fdfc-170">Weitere Informationen finden Sie unter [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span><span class="sxs-lookup"><span data-stu-id="3fdfc-170">For more information, see [Report Server Service Trace Log](report-server/report-server-service-trace-log.md).</span></span>  
  
### <a name="working-with-types"></a><span data-ttu-id="3fdfc-171">Arbeiten mit Typen</span><span class="sxs-lookup"><span data-stu-id="3fdfc-171">Working with Types</span></span>  
 <span data-ttu-id="3fdfc-172">Wenn Sie der Zulassungsliste einen Typ hinzufügen, steuern Sie die folgenden Einstiegspunkte, um auf RDL-Ausdrücke zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="3fdfc-172">When you add a type to the allow list, you are controlling the following entry points to access RDL expressions:</span></span>  
  
-   <span data-ttu-id="3fdfc-173">Statische Elemente eines Typs.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-173">Static members of a type.</span></span>  
  
-   <span data-ttu-id="3fdfc-174">Die- [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] `New` Methode.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-174">The [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] `New` method.</span></span>  
  
-   <span data-ttu-id="3fdfc-175">Das **\<Classes>** Element in der Berichtsdefinition.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-175">The **\<Classes>** element in the report definition.</span></span>  
  
-   <span data-ttu-id="3fdfc-176">Elemente, die Sie der Sperrliste für einen Typ in der Zulassungsliste hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-176">Members that you have added to the block list for a type in the allow list.</span></span>  
  
 <span data-ttu-id="3fdfc-177">Die Zulassungsliste steuert die folgenden Einstiegspunkte nicht:</span><span class="sxs-lookup"><span data-stu-id="3fdfc-177">The allow list does not control the following entry points:</span></span>  
  
-   <span data-ttu-id="3fdfc-178">Berichtsdatasets.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-178">Report datasets.</span></span> <span data-ttu-id="3fdfc-179">Felder in Berichtsdatasets, die von Abfragen zurückgegeben werden, können jeden gültigen RDL-Typ enthalten.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-179">Fields in report datasets that are returned from queries might contain any valid RDL type.</span></span>  
  
-   <span data-ttu-id="3fdfc-180">Berichtsparameter.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-180">Report parameters.</span></span> <span data-ttu-id="3fdfc-181">Vom Benutzer bereitgestellte Parameterwerte könnten jeden gültigen RDL-Typ enthalten.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-181">User-supplied parameter values might contain any valid RDL type.</span></span>  
  
-   <span data-ttu-id="3fdfc-182">Elemente eines aktivierten Typs, die nicht in der Sperrliste enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-182">Members of an enabled type that are not in the block list.</span></span> <span data-ttu-id="3fdfc-183">Standardmäßig werden alle Elemente aller Typen in der Zulassungsliste aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-183">By default, all members of all types in the allow list are enabled.</span></span> <span data-ttu-id="3fdfc-184">Wenn Sie der Sperrliste einen Elementnamen hinzufügen, verweigern Sie alle Elemente dieses Namens für alle Typen in der Zulassungsliste.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-184">When you add a member name to the block list, you are denying all members with that name across all types that are in the allow list.</span></span>  
  
 <span data-ttu-id="3fdfc-185">Um ein Element eines Typs zu aktivieren, aber ein Element mit dem gleichen Namen für einen anderen Typ zu verweigern, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="3fdfc-185">To enable a member of one type but deny a member with the same name for a different type, you must do the following:</span></span>  
  
-   <span data-ttu-id="3fdfc-186">Fügen Sie ein- **\<Deny>** Element für den Elementnamen hinzu.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-186">Add a **\<Deny>** element for the member name.</span></span>  
  
-   <span data-ttu-id="3fdfc-187">Erstellen Sie ein Proxyelement mit einem anderen Namen für eine Klasse in einer benutzerdefinierten Assembly für das Element, das Sie aktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-187">Create a proxy member with a different name on a class in a custom assembly for the member that you want to enable.</span></span>  
  
-   <span data-ttu-id="3fdfc-188">Fügen Sie der Zulassungsliste diese neue Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-188">Add that new class to the allow list.</span></span>  
  
 <span data-ttu-id="3fdfc-189">Um der Zulassungsliste [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] -Funktionen für .NET Framework hinzuzufügen, fügen Sie die entsprechenden Typen aus dem Namespace „Microsoft.VisualBasic“ zur Zulassungsliste hinzu.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-189">To add [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework functions to the allow list, add the corresponding types from the Microsoft.VisualBasic namespace to the allow list.</span></span>  
  
 <span data-ttu-id="3fdfc-190">Um der Zulassungsliste [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] -Typschlüsselwörter für .NET Framework hinzuzufügen, fügen Sie der Zulassungsliste den entsprechenden CLR-Typ hinzu.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-190">To add [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework type keywords to the allow list, add the corresponding CLR type to the allow list.</span></span> <span data-ttu-id="3fdfc-191">Um z. b. das [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework-Schlüsselwort zu verwenden `Integer` , fügen Sie dem-Element das folgende XML-Fragment hinzu **\<RDLSandboxing>** :</span><span class="sxs-lookup"><span data-stu-id="3fdfc-191">For example, to use the [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework keyword `Integer`, add the following XML fragment to the **\<RDLSandboxing>** element:</span></span>  
  
```  
<Allow Namespace="System">Int32</Allow>  
```  
  
 <span data-ttu-id="3fdfc-192">Um der Zulassungsliste einen generischen Typ oder einen [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] -Typ für .NET Framework hinzuzufügen, der NULL-Werte zulässt, führen Sie folgende Aktionen aus.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-192">To add a generic or a [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework nullable type to the allow list, you must do the following:</span></span>  
  
-   <span data-ttu-id="3fdfc-193">Erstellen Sie einen Proxytyp für den generischen Typ oder den [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] -Typ für .NET Framework, der NULL-Werte zulässt.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-193">Create a proxy type for the generic or [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework nullable type.</span></span>  
  
-   <span data-ttu-id="3fdfc-194">Fügen Sie der Zulassungsliste den Proxytyp hinzu.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-194">Add the proxy type to the allow list.</span></span>  
  
 <span data-ttu-id="3fdfc-195">Indem Sie einen Typ aus einer benutzerdefinierten Assembly der Zulassungsliste hinzufügen, gewähren Sie nicht implizit die Ausführungsberechtigung für die Assembly.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-195">Adding a type from a custom assembly to the allow list does not implicitly grant execute permission on the assembly.</span></span> <span data-ttu-id="3fdfc-196">Sie müssen die Codezugriffs-Sicherheitsdatei spezifisch ändern und die  Ausführungsberechtigung für die Assembly bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-196">You must specifically modify the code access security file and provide execute permission to your assembly.</span></span> <span data-ttu-id="3fdfc-197">Weitere Informationen finden Sie unter [Code Access Security in Reporting Services](extensions/secure-development/code-access-security-in-reporting-services.md).</span><span class="sxs-lookup"><span data-stu-id="3fdfc-197">For more information, see [Code Access Security in Reporting Services](extensions/secure-development/code-access-security-in-reporting-services.md).</span></span>  
  
#### <a name="maintaining-the-deny-list-of-members"></a><span data-ttu-id="3fdfc-198">Beibehalten der \<Deny> Liste der Mitglieder</span><span class="sxs-lookup"><span data-stu-id="3fdfc-198">Maintaining the \<Deny> List of Members</span></span>  
 <span data-ttu-id="3fdfc-199">Wenn Sie der Zulassungsliste einen neuen Typ hinzufügen, verwenden Sie die folgende Liste, um zu bestimmen, wann Sie die Sperrliste von Elementen möglicherweise aktualisieren müssen:</span><span class="sxs-lookup"><span data-stu-id="3fdfc-199">When you add a new type to the allow list, use the following list to determine when you might have to update the block list of members:</span></span>  
  
-   <span data-ttu-id="3fdfc-200">Wenn Sie eine benutzerdefinierte Assembly mit einer Version aktualisieren, in der neue Typen eingeführt werden.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-200">When you update a custom assembly with a version that introduces new types.</span></span>  
  
-   <span data-ttu-id="3fdfc-201">Wenn Sie den Typen in der Zulassungsliste Elemente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-201">When you add members to the types in the allow list.</span></span>  
  
-   <span data-ttu-id="3fdfc-202">Wenn Sie den [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] auf dem Berichtsserver aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-202">When you update the [!INCLUDE[dnprdnshort](../includes/dnprdnshort-md.md)] on the report server.</span></span>  
  
-   <span data-ttu-id="3fdfc-203">Wenn Sie den Berichtsserver auf eine höhere Version von [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)]aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-203">When you upgrade the report server to a later version of [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="3fdfc-204">Wenn Sie einen Berichtsserver aktualisieren, um ein späteres RDL-Schema verarbeiten zu können, da RDL-Typen möglicherweise neue Elemente hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-204">When you update a report server to handle a later RDL schema, because new members might have been added to RDL types.</span></span>  
  
### <a name="working-with-operators-and-new"></a><span data-ttu-id="3fdfc-205">Arbeiten mit Operatoren und "New"</span><span class="sxs-lookup"><span data-stu-id="3fdfc-205">Working with Operators and New</span></span>  
 <span data-ttu-id="3fdfc-206">Standardmäßig werden [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]-Sprachoperatoren für .NET Framework außer `New` immer zugelassen.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-206">By default, [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework language operators, except for `New`, are always allowed.</span></span> <span data-ttu-id="3fdfc-207">Der `New` Operator wird durch das- `AllowNew` Attribut des- **\<Allow>** Elements gesteuert.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-207">The `New` operator is controlled by the `AllowNew` attribute on the **\<Allow>** element.</span></span> <span data-ttu-id="3fdfc-208">Andere sprach Operatoren, wie z. b. der Standard-Auflistungs Accessor `!` -Operator und .NET Framework Umwandlungs [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] Makros wie `CInt` , sind immer zulässig.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-208">Other language operators, such as the default collection accessor operator `!` and [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] .NET Framework cast macros such as `CInt`, are always allowed.</span></span>  
  
 <span data-ttu-id="3fdfc-209">Das Hinzufügen von Operatoren, einschließlich benutzerdefinierter Operatoren, zu einer Sperrliste wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-209">Adding operators to a block list, including custom operators, is not supported.</span></span> <span data-ttu-id="3fdfc-210">Um Operatoren für einen Typ auszuschließen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="3fdfc-210">To exclude operators for a type, you must do the following:</span></span>  
  
-   <span data-ttu-id="3fdfc-211">Erstellen Sie einen Proxytyp, der die auszuschließenden Operatoren nicht implementiert.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-211">Create a proxy type that does not implement the operators that you want to exclude.</span></span>  
  
-   <span data-ttu-id="3fdfc-212">Fügen Sie der Zulassungsliste den Proxytyp hinzu.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-212">Add the proxy type to the allow list.</span></span>  
  
 <span data-ttu-id="3fdfc-213">Um in einem RDL-Ausdruck ein neues Array zu erstellen, erstellen Sie das Array in einer Methode für eine Klasse, die Sie definieren, und fügen Sie der Zulassungsliste diese Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-213">To create a new array in an RDL expression, create the array in a method on a class that you define, and add that class to the allow list.</span></span>  
  
 <span data-ttu-id="3fdfc-214">Um in einem RDL-Ausdruck ein neues Array zu erstellen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="3fdfc-214">To create a new array in an RDL expression, you must do the following:</span></span>  
  
-   <span data-ttu-id="3fdfc-215">Definieren Sie eine neue Klasse, und erstellen Sie das Array in einer Methode für diese Klasse.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-215">Define a new class and create the array in a method on that class.</span></span>  
  
-   <span data-ttu-id="3fdfc-216">Fügen Sie der Zulassungsliste die Klasse hinzu.</span><span class="sxs-lookup"><span data-stu-id="3fdfc-216">Add the class to the allow list.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fdfc-217">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fdfc-217">See Also</span></span>  
 <span data-ttu-id="3fdfc-218">[RSReportServer-Konfigurationsdatei](report-server/rsreportserver-config-configuration-file.md) </span><span class="sxs-lookup"><span data-stu-id="3fdfc-218">[RSReportServer Configuration File](report-server/rsreportserver-config-configuration-file.md) </span></span>  
 [<span data-ttu-id="3fdfc-219">Berichtsserverdienst-Ablaufverfolgungsprotokoll</span><span class="sxs-lookup"><span data-stu-id="3fdfc-219">Report Server Service Trace Log</span></span>](report-server/report-server-service-trace-log.md)  
  
  
