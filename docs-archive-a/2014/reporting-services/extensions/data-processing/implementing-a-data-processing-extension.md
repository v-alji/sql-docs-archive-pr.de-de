---
title: Implementieren von Datenverarbeitungserweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom data processing extensions [Reporting Services]
- data sources [Reporting Services], data processing extensions
- data processing extensions [Reporting Services]
- extensions [Reporting Services], data processing
ms.assetid: 8dc2b44e-5ad9-411d-a29f-7213e29321a9
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 5a1b7668f2319e742dcf3f1969fc3c5cc85cd7eb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87725270"
---
# <a name="implementing-a-data-processing-extension"></a><span data-ttu-id="9770c-102">Implementieren von Datenverarbeitungserweiterungen</span><span class="sxs-lookup"><span data-stu-id="9770c-102">Implementing a Data Processing Extension</span></span>
  <span data-ttu-id="9770c-103">Mithilfe von Datenverarbeitungserweiterungen in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] können Sie eine Verbindung zu einer Datenquelle herstellen und Daten abrufen.</span><span class="sxs-lookup"><span data-stu-id="9770c-103">Data processing extensions in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] enable you to connect to a data source and retrieve data.</span></span> <span data-ttu-id="9770c-104">Sie dienen außerdem als Verbindung zwischen einer Datenquelle und einem Dataset.</span><span class="sxs-lookup"><span data-stu-id="9770c-104">They also serve as a bridge between a data source and a dataset.</span></span> <span data-ttu-id="9770c-105">Datenverarbeitungserweiterungen für [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] sind einer Teilmenge der Datenanbieterschnittstellen für [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] nachgebildet.</span><span class="sxs-lookup"><span data-stu-id="9770c-105">[!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extensions are modeled after a subset of the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] data provider interfaces.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9770c-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="9770c-106">In This Section</span></span>  
 [<span data-ttu-id="9770c-107">Data Processing Extensions Overview (Übersicht über Datenverarbeitungserweiterungen)</span><span class="sxs-lookup"><span data-stu-id="9770c-107">Data Processing Extensions Overview</span></span>](data-processing-extensions-overview.md)  
 <span data-ttu-id="9770c-108">Erläutert, wie eine benutzerdefinierte Datenverarbeitungserweiterung für [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="9770c-108">Introduces how to write a custom data processing extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="9770c-109">Preparing to Implement a Data Processing Extension (Vorbereiten der Implementierung von Datenverarbeitungserweiterungen)</span><span class="sxs-lookup"><span data-stu-id="9770c-109">Preparing to Implement a Data Processing Extension</span></span>](preparing-to-implement-a-data-processing-extension.md)  
 <span data-ttu-id="9770c-110">Beschreibt die verfügbaren Schnittstellen beim Implementieren einer [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Datenverarbeitungserweiterung sowie den Fall, in dem Sie eine bestimmte Schnittstelle implementieren müssen.</span><span class="sxs-lookup"><span data-stu-id="9770c-110">Describes the interfaces available when implementing an [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension, as well as when you are required to implement a particular interface.</span></span>  
  
 [<span data-ttu-id="9770c-111">Creating a Data Processing Extension Library (Erstellen einer Bibliothek für Datenverarbeitungserweiterungen)</span><span class="sxs-lookup"><span data-stu-id="9770c-111">Creating a Data Processing Extension Library</span></span>](creating-a-data-processing-extension-library.md)  
 <span data-ttu-id="9770c-112">Beschreibt die Zuordnung eines Namespace für Ihre [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Datenverarbeitungserweiterung und die Kompilierung Ihrer Datenverarbeitungserweiterung in eine DLL-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="9770c-112">Describes assigning a namespace for your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] data processing extension and compiling your data processing extension into a library DLL.</span></span>  
  
 [<span data-ttu-id="9770c-113">Implementing a Connection Class for a Data Processing Extension (Implementieren einer Connection-Klasse für Datenverarbeitungserweiterungen)</span><span class="sxs-lookup"><span data-stu-id="9770c-113">Implementing a Connection Class for a Data Processing Extension</span></span>](implementing-a-connection-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="9770c-114">Beschreibt die Attribute einer Verbindung und die Implementierungsweise einer eigenen **Connection**-Klasse für Ihre Datenverarbeitungserweiterung</span><span class="sxs-lookup"><span data-stu-id="9770c-114">Describes the attributes of a connection and how to implement your own **Connection** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="9770c-115">Implementing a Command Class for a Data Processing Extension (Implementieren einer Command-Klasse für Datenverarbeitungserweiterungen)</span><span class="sxs-lookup"><span data-stu-id="9770c-115">Implementing a Command Class for a Data Processing Extension</span></span>](implementing-a-command-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="9770c-116">Beschreibt die Attribute eines Befehls und die Implementierungsweise einer eigenen **Command**-Klasse für Ihre Datenverarbeitungserweiterung</span><span class="sxs-lookup"><span data-stu-id="9770c-116">Describes the attributes of a command, and how to implement your own **Command** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="9770c-117">Implementing a DataReader Class for a Data Processing Extension (Implementieren einer DataReader-Klasse für Datenverarbeitungserweiterungen)</span><span class="sxs-lookup"><span data-stu-id="9770c-117">Implementing a DataReader Class for a Data Processing Extension</span></span>](implementing-a-datareader-class-for-a-data-processing-extension.md)  
 <span data-ttu-id="9770c-118">Beschreibt die Attribute eines Datenlesers und die Implementierungsweise einer eigenen **DataReader**-Klasse für Ihre Datenverarbeitungserweiterung</span><span class="sxs-lookup"><span data-stu-id="9770c-118">Describes the attributes of a data reader and how to implement your own **DataReader** class for your data processing extension.</span></span>  
  
 [<span data-ttu-id="9770c-119">Using an External Dataset with Reporting Services (Verwenden eines externen Datasets mit Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="9770c-119">Using an External Dataset with Reporting Services</span></span>](using-an-external-dataset-with-reporting-services.md)  
 <span data-ttu-id="9770c-120">Beschreibt, wie die benutzerdefinierten **Dataset**-Objekte für die Verwendung durch den Berichtsserver zur Verfügung gestellt werden</span><span class="sxs-lookup"><span data-stu-id="9770c-120">Describes how to expose your custom **DataSet** objects to the report server for consumption.</span></span>  
  
 [<span data-ttu-id="9770c-121">Bereitstellen von Datenverarbeitungserweiterungen</span><span class="sxs-lookup"><span data-stu-id="9770c-121">Deploying a Data Processing Extension</span></span>](deploying-a-data-processing-extension.md)  
 <span data-ttu-id="9770c-122">Beschreibt, wie Sie eine Datenverarbeitungserweiterung bereitstellen</span><span class="sxs-lookup"><span data-stu-id="9770c-122">Describes how to deploy your data processing extension.</span></span>  
  
 [<span data-ttu-id="9770c-123">Debugging Data Processing Extension Code (Debuggen von Code für Datenverarbeitungserweiterungen)</span><span class="sxs-lookup"><span data-stu-id="9770c-123">Debugging Data Processing Extension Code</span></span>](debugging-data-processing-extension-code.md)  
 <span data-ttu-id="9770c-124">Beschreibt, wie Sie Code in Ihren Datenverarbeitungserweiterungen debuggen</span><span class="sxs-lookup"><span data-stu-id="9770c-124">Describes how to debug code in your data processing extensions.</span></span>  
  
 [<span data-ttu-id="9770c-125">Entfernen einer Datenverarbeitungserweiterung</span><span class="sxs-lookup"><span data-stu-id="9770c-125">Removing a Data Processing Extension</span></span>](removing-a-data-processing-extension.md)  
 <span data-ttu-id="9770c-126">Beschreibt, wie Sie eine Datenverarbeitungserweiterung von einem Berichtsserver oder Berichts-Designer entfernen</span><span class="sxs-lookup"><span data-stu-id="9770c-126">Describes how to remove a data processing extension from a report server or Report Designer.</span></span>  
  
 <span data-ttu-id="9770c-127">Ein Beispiel für eine vollständig implementierte Datenverarbeitungserweiterung finden Sie unter [SQL Server Reporting Services-Produktbeispiele](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="9770c-127">For a sample of a fully implemented data processing extension, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9770c-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9770c-128">See Also</span></span>  
 <span data-ttu-id="9770c-129">[Reporting Services Erweiterungen](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="9770c-129">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="9770c-130">Reporting Services-Erweiterungsbibliothek</span><span class="sxs-lookup"><span data-stu-id="9770c-130">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
