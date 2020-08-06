---
title: Implementieren von Übermittlungserweiterungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- delivery [Reporting Services]
- custom delivery extensions [Reporting Services]
- extensions [Reporting Services], delivery
- delivery extensions [Reporting Services]
ms.assetid: 600cd229-efcd-480e-8c95-3c3c39ff4e7a
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: af1e804e029dae77fb7836577aa8d4a45ad20109
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630548"
---
# <a name="implementing-a-delivery-extension"></a><span data-ttu-id="cb36e-102">Implementieren von Übermittlungserweiterungen</span><span class="sxs-lookup"><span data-stu-id="cb36e-102">Implementing a Delivery Extension</span></span>
  <span data-ttu-id="cb36e-103">Mithilfe von [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] können Benutzer Berichte erstellen und veröffentlichen, die anschließend an diverse Orte übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="cb36e-103">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] enables users to create and publish reports that, once created and published, can be delivered to various locations.</span></span> <span data-ttu-id="cb36e-104">Außerdem enthält [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] verschiedene Übermittlungserweiterungen und eine Übermittlungs-API, mit der Entwickler zusätzliche Übermittlungserweiterungen erstellen können, um die Übermittlungsfunktionen in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] noch zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="cb36e-104">In addition, [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] includes several delivery extensions and a delivery API that enable developers to create additional delivery extensions to further extend the functionality of delivery in [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="cb36e-105">Eine Beispielimplementierung einer Übermittlungserweiterung finden Sie unter [SQL Server Reporting Services-Produktbeispiele](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="cb36e-105">For a sample implementation of a delivery extension, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="cb36e-106">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="cb36e-106">In This Section</span></span>  
 <span data-ttu-id="cb36e-107">[Übersicht über Übermittlungs Erweiterungen] Delivery-Extensions-Overview.MD)</span><span class="sxs-lookup"><span data-stu-id="cb36e-107">[Delivery Extensions Overview]delivery-extensions-overview.md)</span></span>  
 <span data-ttu-id="cb36e-108">Erläutert, wie eine benutzerdefinierte Übermittlungserweiterung für [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] geschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="cb36e-108">Introduces how to write a custom delivery extension for [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)].</span></span>  
  
 [<span data-ttu-id="cb36e-109">Preparing to Implement a Delivery Extension (Vorbereiten der Implementierung von Übermittlungserweiterungen)</span><span class="sxs-lookup"><span data-stu-id="cb36e-109">Preparing to Implement a Delivery Extension</span></span>](preparing-to-implement-a-delivery-extension.md)  
 <span data-ttu-id="cb36e-110">Beschreibt die verfügbaren Schnittstellen und Klassen beim Implementieren einer [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Übermittlungserweiterung sowie die Themen, die vor der Implementierung berücksichtigt werden sollten.</span><span class="sxs-lookup"><span data-stu-id="cb36e-110">Describes the interfaces and classes available when implementing an [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension, as well as issues to consider before implementation.</span></span>  
  
 [<span data-ttu-id="cb36e-111">Creating a Delivery Extension Library (Erstellen einer Bibliothek für Übermittlungserweiterungen)</span><span class="sxs-lookup"><span data-stu-id="cb36e-111">Creating a Delivery Extension Library</span></span>](creating-a-delivery-extension-library.md)  
 <span data-ttu-id="cb36e-112">Beschreibt die Zuordnung eines Namespace für die [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)]-Übermittlungserweiterung und die Kompilierung der Übermittlungserweiterung in eine DLL-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="cb36e-112">Describes assigning a namespace for your [!INCLUDE[ssRSnoversion](../../../includes/ssrsnoversion-md.md)] delivery extension and compiling your delivery extension into a library DLL.</span></span>  
  
 [<span data-ttu-id="cb36e-113">Implementing the IDeliveryExtension Interface for a Delivery Extension (Implementieren der IDeliveryExtension-Schnittstelle für Übermittlungserweiterungen)</span><span class="sxs-lookup"><span data-stu-id="cb36e-113">Implementing the IDeliveryExtension Interface for a Delivery Extension</span></span>](implementing-the-ideliveryextension-interface-for-a-delivery-extension.md)  
 <span data-ttu-id="cb36e-114">Beschreibt die Attribute einer Übermittlungserweiterung und die Art der Implementierung einer eigenen Klasse für die Übermittlungserweiterung.</span><span class="sxs-lookup"><span data-stu-id="cb36e-114">Describes the attributes of a delivery extension, and how to implement your own delivery extension class.</span></span>  
  
 [<span data-ttu-id="cb36e-115">Using a Notification Class for a Delivery Extension (Verwenden einer Notification-Klasse für eine Übermittlungserweiterung)</span><span class="sxs-lookup"><span data-stu-id="cb36e-115">Using a Notification Class for a Delivery Extension</span></span>](using-a-notification-class-for-a-delivery-extension.md)  
 <span data-ttu-id="cb36e-116">Beschreibt die Attribute der **Notification**-Klasse und die Verwendungsweise in Ihrer Implementierung der Übermittlungserweiterung</span><span class="sxs-lookup"><span data-stu-id="cb36e-116">Describes the attributes of a **Notification** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="cb36e-117">Using the Setting Class for a Delivery Extension (Verwenden der Setting-Klasse für eine Übermittlungserweiterung)</span><span class="sxs-lookup"><span data-stu-id="cb36e-117">Using the Setting Class for a Delivery Extension</span></span>](using-the-setting-class-for-a-delivery-extension.md)  
 <span data-ttu-id="cb36e-118">Beschreibt die Attribute der **Setting**-Klasse und die Verwendungsweise in Ihrer Implementierung der Übermittlungserweiterung</span><span class="sxs-lookup"><span data-stu-id="cb36e-118">Describes the attributes of a **Setting** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="cb36e-119">Verwenden der IDeliveryReportServerInformation-Schnittstelle für Übermittlungserweiterungen</span><span class="sxs-lookup"><span data-stu-id="cb36e-119">Using the IDeliveryReportServerInformation Interface for a Delivery Extension</span></span>](using-the-ideliveryreportserverinformation-interface-for-a-delivery-extension.md)  
 <span data-ttu-id="cb36e-120">Beschreibt die Attribute der **IDeliveryReportServerInformation**-Klasse und die Verwendungsweise in Ihrer Implementierung der Übermittlungserweiterung</span><span class="sxs-lookup"><span data-stu-id="cb36e-120">Describes the attributes of a **IDeliveryReportServerInformation** interface and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="cb36e-121">Verwenden der Report-Klasse für eine Übermittlungserweiterung</span><span class="sxs-lookup"><span data-stu-id="cb36e-121">Using the Report Class for a Delivery Extension</span></span>](using-the-report-class-for-a-delivery-extension.md)  
 <span data-ttu-id="cb36e-122">Beschreibt die Attribute der **Report**-Klasse und die Verwendungsweise in Ihrer Implementierung der Übermittlungserweiterung</span><span class="sxs-lookup"><span data-stu-id="cb36e-122">Describes the attributes of a **Report** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="cb36e-123">Verwenden der RenderedOutputFile-Klasse für eine Übermittlungserweiterung</span><span class="sxs-lookup"><span data-stu-id="cb36e-123">Using the RenderedOutputFile Class for a Delivery Extension</span></span>](using-the-renderedoutputfile-class-for-a-delivery-extension.md)  
 <span data-ttu-id="cb36e-124">Beschreibt die Attribute der **RenderedOutputFile**-Klasse und die Verwendungsweise in Ihrer Implementierung der Übermittlungserweiterung</span><span class="sxs-lookup"><span data-stu-id="cb36e-124">Describes the attributes of a **RenderedOutputFile** class and how to use it in your delivery extension implementation.</span></span>  
  
 [<span data-ttu-id="cb36e-125">Implementieren der ISubscriptionBaseUIUserControl-Schnittstelle für eine Übermittlungserweiterung</span><span class="sxs-lookup"><span data-stu-id="cb36e-125">Implementing the ISubscriptionBaseUIUserControl Interface for a Delivery Extension</span></span>](implementing-the-isubscriptionbaseuiusercontrol-interface.md)  
 <span data-ttu-id="cb36e-126">Beschreibt die Attribute eines Steuerelements für die Übermittlungserweiterung und die Art der Implementierung einer eigenen Schnittstelle für das Abonnement.</span><span class="sxs-lookup"><span data-stu-id="cb36e-126">Describes the attributes of a delivery extension user control and how to implement your own user interface for a subscription.</span></span>  
  
 [<span data-ttu-id="cb36e-127">Bereitstellen von Übermittlungserweiterungen</span><span class="sxs-lookup"><span data-stu-id="cb36e-127">Deploying a Delivery Extension</span></span>](deploying-a-delivery-extension.md)  
 <span data-ttu-id="cb36e-128">Beschreibt, wie Sie eine Übermittlungserweiterung anwenden</span><span class="sxs-lookup"><span data-stu-id="cb36e-128">Describes how to deploy your delivery extension.</span></span>  
  
 [<span data-ttu-id="cb36e-129">Debuggen von Übermittlungserweiterungscode</span><span class="sxs-lookup"><span data-stu-id="cb36e-129">Debugging Delivery Extension Code</span></span>](debugging-delivery-extension-code.md)  
 <span data-ttu-id="cb36e-130">Beschreibt, wie Sie Code in der Übermittlungserweiterung debuggen</span><span class="sxs-lookup"><span data-stu-id="cb36e-130">Describes how to debug code in your delivery extension.</span></span>  
  
 [<span data-ttu-id="cb36e-131">Entfernen einer Übermittlungserweiterung</span><span class="sxs-lookup"><span data-stu-id="cb36e-131">Removing a Delivery Extension</span></span>](removing-a-delivery-extension.md)  
 <span data-ttu-id="cb36e-132">Beschreibt, wie Sie eine Übermittlungserweiterung von einem Berichtsserver entfernen</span><span class="sxs-lookup"><span data-stu-id="cb36e-132">Describes how to remove a delivery extension from a report server.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb36e-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb36e-133">See Also</span></span>  
 <span data-ttu-id="cb36e-134">[Reporting Services Erweiterungen](../reporting-services-extensions.md) </span><span class="sxs-lookup"><span data-stu-id="cb36e-134">[Reporting Services Extensions](../reporting-services-extensions.md) </span></span>  
 [<span data-ttu-id="cb36e-135">Reporting Services-Erweiterungsbibliothek</span><span class="sxs-lookup"><span data-stu-id="cb36e-135">Reporting Services Extension Library</span></span>](../reporting-services-extension-library.md)  
  
  
