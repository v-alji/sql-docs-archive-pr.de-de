---
title: Berichts-Generator (SSRS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 32be8fcc-e87d-4c45-a644-dff45776a981
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: dae43dd86cd6b02c81f0fc90a05292458eb87200
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700688"
---
# <a name="report-builder-ssrs"></a><span data-ttu-id="2f11b-102">Berichts-Generator (SSRS)</span><span class="sxs-lookup"><span data-stu-id="2f11b-102">Report Builder (SSRS)</span></span>
  <span data-ttu-id="2f11b-103">Berichts-Generator ist eine Berichterstellungsumgebung für Geschäftsbenutzer, die lieber in der vertrauten [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office-Umgebung arbeiten.</span><span class="sxs-lookup"><span data-stu-id="2f11b-103">Report Builder is a report authoring environment for business users who prefer to work in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] Office environment.</span></span> <span data-ttu-id="2f11b-104">Beim Entwurf eines Berichts geben Sie an, wo die Daten abgerufen werden sollen, welche Daten abgerufen werden sollen und wie die Daten angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="2f11b-104">When you design a report, you specify where to get the data, which data to get, and how to display the data.</span></span> <span data-ttu-id="2f11b-105">Bei der Ausführung des Berichts übernimmt der Berichtsprozessor alle angegebenen Informationen, ruft die Daten ab und kombiniert sie mit dem Berichtslayout, um den Bericht zu generieren.</span><span class="sxs-lookup"><span data-stu-id="2f11b-105">When you run the report, the report processor takes all the information you have specified, retrieves the data, and combines it with the report layout to generate the report.</span></span>  
  
## <a name="benefits-of-report-builder"></a><span data-ttu-id="2f11b-106">Vorteile des Berichts-Generators</span><span class="sxs-lookup"><span data-stu-id="2f11b-106">Benefits of Report Builder</span></span>  
 <span data-ttu-id="2f11b-107">Der Berichts-Generator bietet Ihnen folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="2f11b-107">Report Builder enables you to:</span></span>  
  
-   <span data-ttu-id="2f11b-108">Über das Menüband des Berichts-Generators können Sie Berichten Elemente hinzufügen, den Tabellen-, Diagramm- und Karten-Assistenten starten und die Berichtsdaten formatieren.</span><span class="sxs-lookup"><span data-stu-id="2f11b-108">Use the Report Builder ribbon to quickly add items your reports, launch table, chart, and map wizards, and format report data.</span></span>  
  
-   <span data-ttu-id="2f11b-109">Fügen Sie Daten aus integrierten Datenanbietern mithilfe der Abfrage-Designer hinzu. Diese helfen Ihnen, die in den Bericht einzuschließenden Daten anzugeben.</span><span class="sxs-lookup"><span data-stu-id="2f11b-109">Add data from built-in data providers by using query designers that help you specify which data to include in your report.</span></span>  
  
-   <span data-ttu-id="2f11b-110">Erstellen und verwenden Sie Berichtsparameter und andere interaktive Funktionen, mit denen Berichtsleser die Daten anpassen und die Berichtspräsentation ändern können.</span><span class="sxs-lookup"><span data-stu-id="2f11b-110">Create and use report parameters and other interactive features that enable your report readers to customize data and vary report presentation.</span></span>  
  
-   <span data-ttu-id="2f11b-111">Erstellen Sie Ausdrücke aus integrierten Feldern, Auflistungen, Operatoren und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="2f11b-111">Create expressions from built-in fields, collections, operators, and functions.</span></span>  
  
-   <span data-ttu-id="2f11b-112">Öffnen Sie Berichte direkt auf einem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="2f11b-112">Open reports directly from a report server.</span></span>  
  
-   <span data-ttu-id="2f11b-113">Zeigen Sie eine lokale Vorschau der Berichte oder veröffentlichten freigegebene Datenquellen und freigegebene Datasets an.</span><span class="sxs-lookup"><span data-stu-id="2f11b-113">Preview reports that use local or published shared data sources and shared datasets.</span></span>  
  
-   <span data-ttu-id="2f11b-114">Zeigen Sie eine Vorschau der Berichte im HTML- oder Druckformat an.</span><span class="sxs-lookup"><span data-stu-id="2f11b-114">Preview reports in HTML or print format.</span></span>  
  
-   <span data-ttu-id="2f11b-115">Exportieren Sie die Berichte in andere Dateiformate z. B. [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)].</span><span class="sxs-lookup"><span data-stu-id="2f11b-115">Export reports to other file formats such as [!INCLUDE[ofprexcel](../../includes/ofprexcel-md.md)].</span></span>  
  
-   <span data-ttu-id="2f11b-116">Speichern Sie Berichte und verwandte Elemente in einer SharePoint-Bibliothek, auf einem Berichtsserver oder auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="2f11b-116">Save your report and related items s to a SharePoint library, a report server, or your local computer.</span></span>  
  
 <span data-ttu-id="2f11b-117">Der Berichts-Generator und der Berichts-Designer haben viele gemeinsame Funktionen.</span><span class="sxs-lookup"><span data-stu-id="2f11b-117">Report Builder and Report Designer share many features.</span></span> <span data-ttu-id="2f11b-118">Weitere Informationen zum Berichts-Generator finden Sie in der [Dokumentation zum Berichts-Generator](https://go.microsoft.com/fwlink/?LinkId=154494) unter msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="2f11b-118">For more information about Report Builder, see [Report Builder documentation](https://go.microsoft.com/fwlink/?LinkId=154494) on msdn.microsoft.com.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f11b-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f11b-119">See Also</span></span>  
 <span data-ttu-id="2f11b-120">[Konfigurieren des Berichts-Generator Zugriffs](../report-server/configure-report-builder-access.md) </span><span class="sxs-lookup"><span data-stu-id="2f11b-120">[Configure Report Builder Access](../report-server/configure-report-builder-access.md) </span></span>  
 <span data-ttu-id="2f11b-121">[Reporting Services Tools](reporting-services-tools.md) </span><span class="sxs-lookup"><span data-stu-id="2f11b-121">[Reporting Services Tools](reporting-services-tools.md) </span></span>  
 [<span data-ttu-id="2f11b-122">Entwerfen von Berichten mithilfe des Berichts-Designers (SSRS)</span><span class="sxs-lookup"><span data-stu-id="2f11b-122">Design Reports with Report Designer &#40;SSRS&#41;</span></span>](design-reporting-services-paginated-reports-with-report-designer-ssrs.md)  
  
  
