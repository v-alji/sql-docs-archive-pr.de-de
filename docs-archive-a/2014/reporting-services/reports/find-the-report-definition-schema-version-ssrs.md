---
title: Suchen der Berichtsdefinitions-Schemaversion (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- XML schemas [Reporting Services]
- Report Definition Language, XML schema
- schemas [Reporting Services]
ms.assetid: 67954419-1b61-4481-a3b9-23b4ba7a5624
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 413a270a3722ddda1f418c748fa5b7fba50dfeea
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700784"
---
# <a name="find-the-report-definition-schema-version-ssrs"></a><span data-ttu-id="7bee6-102">Suchen der Berichtsdefinitions-Schemaversion (SSRS)</span><span class="sxs-lookup"><span data-stu-id="7bee6-102">Find the Report Definition Schema Version (SSRS)</span></span>
  <span data-ttu-id="7bee6-103">In einer Berichtsdefinitionsdatei ist der RDL-Namespace für die Version des Berichtsdefinitionsschemas angegeben, das zur Überprüfung der RDL-Datei verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7bee6-103">A report definition file specifies the RDL namespace for the version of the report definition schema that is used to validate the rdl file.</span></span> <span data-ttu-id="7bee6-104">Wenn Sie eine RDL-Datei in einer Berichterstellungsumgebung wie dem Berichts-Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] oder dem Berichts-Generator öffnen und der Bericht für einen vorherigen Namespace erstellt wurde, wird automatisch eine Sicherungsdatei erstellt und der Bericht auf den aktuellen Namespace aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="7bee6-104">When you open an .rdl file in a report authoring environment such as Report Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] or Report Builder, if the report was created for a previous namespace, a backup file is automatically created, and the report is upgraded to the current namespace.</span></span> <span data-ttu-id="7bee6-105">Wenn Sie die aktualisierte Berichtsdefinition speichern, haben Sie die konvertierte RDL-Datei gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7bee6-105">If you save the upgraded report definition, you have saved the converted .rdl file.</span></span> <span data-ttu-id="7bee6-106">Dies ist die einzige Möglichkeit, eine Berichtsdefinition zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="7bee6-106">This is the only way to upgrade a report definition.</span></span> <span data-ttu-id="7bee6-107">Die Berichtsdefinition selbst wird auf einem Berichtsserver nicht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="7bee6-107">The report definition itself is not upgraded on a report server.</span></span> <span data-ttu-id="7bee6-108">Der kompilierte Bericht wird auf einem Berichtsserver aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="7bee6-108">The compiled report is upgraded on a report server.</span></span> <span data-ttu-id="7bee6-109">Weitere Informationen finden Sie unter [Upgrade Reports](../install-windows/upgrade-reports.md).</span><span class="sxs-lookup"><span data-stu-id="7bee6-109">For more information, see [Upgrade Reports](../install-windows/upgrade-reports.md).</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-of-a-report"></a><span data-ttu-id="7bee6-110">Vorgehensweise: Identifizieren der RDL-Schemaversion eines Berichts</span><span class="sxs-lookup"><span data-stu-id="7bee6-110">How to: Identify the RDL Schema Version of a Report</span></span>  
  
1.  <span data-ttu-id="7bee6-111">Öffnen Sie die RDL-Berichtsdatei in einer Anwendung wie dem Editor oder XML Notepad 2007, in der Sie XML anzeigen können.</span><span class="sxs-lookup"><span data-stu-id="7bee6-111">Open the report .rdl file in an application such as Notepad or XML Notepad 2007 in which you can view the xml.</span></span>  
  
     <span data-ttu-id="7bee6-112">Das XML-Berichtselement gibt den Schemanamespace an.</span><span class="sxs-lookup"><span data-stu-id="7bee6-112">The XML Report element specifies the schema namespace.</span></span> <span data-ttu-id="7bee6-113">Zum Beispiel gibt das folgende Berichtselement den Namespace für den Berichts-Designer und den Namespace für die Berichtsdefinition an.</span><span class="sxs-lookup"><span data-stu-id="7bee6-113">For example, the following Report element specifies the namespace for Report Designer and the namespace for the report definition.</span></span>  
  
    ```  
    <Report xmlns:rd=https://schemas.microsoft.com/SQLServer/reporting/reportdesigner   
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition">  
    ```  
  
     <span data-ttu-id="7bee6-114">Der Berichtsdefinitionsnamespace wird von der folgenden URL angegeben: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`.</span><span class="sxs-lookup"><span data-stu-id="7bee6-114">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`.</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-of-report-designer"></a><span data-ttu-id="7bee6-115">Vorgehensweise: Identifizieren der RDL-Schemaversion des Berichts-Designers</span><span class="sxs-lookup"><span data-stu-id="7bee6-115">How to: Identify the RDL Schema Version of Report Designer</span></span>  
  
1.  <span data-ttu-id="7bee6-116">Öffnen Sie ein neues Projekt.</span><span class="sxs-lookup"><span data-stu-id="7bee6-116">Open a new project.</span></span> <span data-ttu-id="7bee6-117">Die Version des ausgewählten Projekts bestimmt die Version des RDL-Schemas.</span><span class="sxs-lookup"><span data-stu-id="7bee6-117">The version of the project that you choose determines the version of the RDL schema.</span></span> <span data-ttu-id="7bee6-118">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)]werden mehrere Schemaversionen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7bee6-118">In [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)], more than one schema version is supported.</span></span> <span data-ttu-id="7bee6-119">Weitere Informationen finden Sie unter [Bereitstellung und Versionsunterstützung in SQL Server Data Tools &#40;SSRS&#41;](../tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md)enthalten.</span><span class="sxs-lookup"><span data-stu-id="7bee6-119">For more information, see [Deployment and Version Support in SQL Server Data Tools &#40;SSRS&#41;](../tools/deployment-and-version-support-in-sql-server-data-tools-ssrs.md).</span></span>  
  
2.  <span data-ttu-id="7bee6-120">Klicken Sie im Menü **Projekt** auf **Neues Element hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7bee6-120">On the **Project** menu, click **Add New Item**.</span></span> <span data-ttu-id="7bee6-121">Das Dialogfeld **Neues Element hinzufügen** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7bee6-121">The **Add New Item** dialog box opens.</span></span>  
  
3.  <span data-ttu-id="7bee6-122">Klicken Sie im Bereich **Vorlagen** auf **Bericht**.</span><span class="sxs-lookup"><span data-stu-id="7bee6-122">In the **Templates** pane, click **Report**.</span></span>  
  
4.  <span data-ttu-id="7bee6-123">Geben Sie im Feld **Name**einen Berichtsnamen ein, oder übernehmen Sie den Standardnamen.</span><span class="sxs-lookup"><span data-stu-id="7bee6-123">In **Name**, type a report name or accept the default.</span></span>  
  
5.  <span data-ttu-id="7bee6-124">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="7bee6-124">Click **Add**.</span></span> <span data-ttu-id="7bee6-125">Der Berichts-Designer öffnet in der Entwurfsansicht einen neuen leeren Bericht.</span><span class="sxs-lookup"><span data-stu-id="7bee6-125">Report Designer opens a new blank report in Design view.</span></span>  
  
6.  <span data-ttu-id="7bee6-126">Klicken Sie im Menü **Ansicht** auf **Code**.</span><span class="sxs-lookup"><span data-stu-id="7bee6-126">On the **View** menu, click **Code**.</span></span> <span data-ttu-id="7bee6-127">Die Berichtsdefinition wird als XML-Datei angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7bee6-127">The report definition is displayed as an XML file.</span></span>  
  
     <span data-ttu-id="7bee6-128">Das XML-Berichtselement gibt den Schemanamespace an.</span><span class="sxs-lookup"><span data-stu-id="7bee6-128">The XML Report element specifies the schema namespace.</span></span> <span data-ttu-id="7bee6-129">Zum Beispiel gibt das folgende Berichtselement den Namespace für den Berichts-Designer und den Namespace für die Berichtsdefinition an.</span><span class="sxs-lookup"><span data-stu-id="7bee6-129">For example, the following Report element specifies the namespace for Report Designer and the namespace for the report definition.</span></span>  
  
    ```  
    <Report xmlns:rd=https://schemas.microsoft.com/SQLServer/reporting/reportdesigner  
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition">  
    ```  
  
     <span data-ttu-id="7bee6-130">Der Berichtsdefinitionsnamespace wird von der folgenden URL angegeben: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span><span class="sxs-lookup"><span data-stu-id="7bee6-130">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span></span>  
  
### <a name="how-to-identify-the-rdl-schema-version-on-the-report-server"></a><span data-ttu-id="7bee6-131">Vorgehensweise: Identifizieren der RDL-Schemaversion auf dem Berichtsserver</span><span class="sxs-lookup"><span data-stu-id="7bee6-131">How to: Identify the RDL Schema Version on the Report Server</span></span>  
  
-   <span data-ttu-id="7bee6-132">Geben Sie im Berichts-Manager die URL für den Berichtsserver ein.</span><span class="sxs-lookup"><span data-stu-id="7bee6-132">In Report Manager, type the URL for the report server.</span></span> <span data-ttu-id="7bee6-133">Die folgende URL gibt z. B. einen Berichtsserver auf dem lokalen Computer an:</span><span class="sxs-lookup"><span data-stu-id="7bee6-133">For example, the following URL specifies a report server on the local computer:</span></span>  
  
     `http://localhost/reportserver/reportdefinition.xsd`  
  
     <span data-ttu-id="7bee6-134">Die XSD-Datei wird im Browser geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7bee6-134">The .xsd file opens in the browser.</span></span>  
  
     <span data-ttu-id="7bee6-135">Das XML-Schemaelement gibt den Schemanamespace an.</span><span class="sxs-lookup"><span data-stu-id="7bee6-135">The XML schema element specifies the schema namespace.</span></span> <span data-ttu-id="7bee6-136">Das folgende Schemaelement gibt beispielsweise drei Namespaces an: den targetNamespace-Verweis, der intern von [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]verwendet wird, den XSD-Verweis für das Schema selbst (XSD) und die Berichtsdefinitionsreferenz.</span><span class="sxs-lookup"><span data-stu-id="7bee6-136">For example, the following schema element specifies three namespaces: the targetNamespace reference that is used internally by [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)], the xsd reference for the schema itself (xsd), and the report definition reference.</span></span>  
  
    ```  
    <xsd:schema   
    targetNamespace="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"   
    xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
    xmlns="https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition"   
    elementFormDefault="qualified">  
    ```  
  
     <span data-ttu-id="7bee6-137">Der Berichtsdefinitionsnamespace wird von der folgenden URL angegeben: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span><span class="sxs-lookup"><span data-stu-id="7bee6-137">The report definition namespace is specified by the following URL: `https://schemas.microsoft.com/sqlserver/reporting/2009/01/reportdefinition`</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7bee6-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7bee6-138">See Also</span></span>  
 <span data-ttu-id="7bee6-139">[Aktualisieren von Berichten](../install-windows/upgrade-reports.md) </span><span class="sxs-lookup"><span data-stu-id="7bee6-139">[Upgrade Reports](../install-windows/upgrade-reports.md) </span></span>  
 [<span data-ttu-id="7bee6-140">Berichtsdefinitionssprache (SSRS)</span><span class="sxs-lookup"><span data-stu-id="7bee6-140">Report Definition Language &#40;SSRS&#41;</span></span>](report-definition-language-ssrs.md)  
  
  
