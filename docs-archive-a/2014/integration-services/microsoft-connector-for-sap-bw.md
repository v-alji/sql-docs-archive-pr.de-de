---
title: Microsoft-Connector 1,1 für SAP BW | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5281f080-53d5-4679-aa26-f4cd4ac7a2df
author: chugugrace
ms.author: chugu
ms.openlocfilehash: ec5cfe83b201976be0512c54b77bc79f8aa824b3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721590"
---
# <a name="microsoft-connector-11-for-sap-bw"></a><span data-ttu-id="14c13-102">Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="14c13-102">Microsoft Connector 1.1 for SAP BW</span></span>
  <span data-ttu-id="14c13-103">Der [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1,1 für SAP BW besteht aus einem Satz von drei Komponenten, mit denen Sie Daten aus einem SAP NetWeaver BW-System, Version 7, extrahieren oder in ein solches System laden können.</span><span class="sxs-lookup"><span data-stu-id="14c13-103">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW consists of a set of three components that let you extract data from, or load data into, an SAP Netweaver BW version 7 system.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="14c13-104">Die Dokumentation für Microsoft Connector 1.1 for SAP BW setzt Kenntnisse der SAP NetWeaver BW-Umgebung voraus.</span><span class="sxs-lookup"><span data-stu-id="14c13-104">The documentation for the Microsoft Connector 1.1 for SAP BW assumes familiarity with the SAP Netweaver BW environment.</span></span> <span data-ttu-id="14c13-105">Weitere Informationen zu SAP NetWeaver BW oder Informationen zur Konfiguration von SAP NetWeaver BW-Objekten und -Prozessen finden Sie in der SAP-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="14c13-105">For more information about SAP Netweaver BW, or for information about how to configure SAP Netweaver BW objects and processes, see your SAP documentation.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="14c13-106">Das Extrahieren von Daten aus SAP NetWeaver BW erfordert zusätzliche SAP-Lizenzen.</span><span class="sxs-lookup"><span data-stu-id="14c13-106">Extracting data from SAP Netweaver BW requires additional SAP licensing.</span></span> <span data-ttu-id="14c13-107">Stimmen Sie diese Anforderungen mit SAP ab.</span><span class="sxs-lookup"><span data-stu-id="14c13-107">Check with SAP to verify these requirements.</span></span>  
  
## <a name="components"></a><span data-ttu-id="14c13-108">Komponenten</span><span class="sxs-lookup"><span data-stu-id="14c13-108">Components</span></span>  
 <span data-ttu-id="14c13-109">Der [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1,1 für SAP BW verfügt über die folgenden Komponenten:</span><span class="sxs-lookup"><span data-stu-id="14c13-109">The [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW has the following components:</span></span>  
  
-   <span data-ttu-id="14c13-110">**SAP BW Quelle**: die SAP BW Quelle ist eine Datenfluss Quell Komponente, mit der Sie Daten aus einem SAP NetWeaver BW-System, Version 7, extrahieren können.</span><span class="sxs-lookup"><span data-stu-id="14c13-110">**SAP BW Source**-The SAP BW source is a data flow source component that lets you extract data from an SAP Netweaver BW version 7 system.</span></span>  
  
-   <span data-ttu-id="14c13-111">**SAP BW Ziel**: das SAP BW Ziel ist eine Datenfluss Zielkomponente, mit der Sie Daten in ein SAP NetWeaver BW-System (Version 7) laden können.</span><span class="sxs-lookup"><span data-stu-id="14c13-111">**SAP BW Destination**-The SAP BW destination is a data flow destination component that lets you load data into an SAP Netweaver BW version 7 system.</span></span>  
  
-   <span data-ttu-id="14c13-112">**SAP BW Verbindungs-Manager**: der SAP BW-Verbindungs-Manager verbindet entweder eine SAP BW Quelle oder SAP BW Ziel mit einem SAP NetWeaver BW-System, Version 7.</span><span class="sxs-lookup"><span data-stu-id="14c13-112">**SAP BW Connection Manager**-The SAP BW connection manager connects either an SAP BW source or SAP BW destination to an SAP Netweaver BW version 7 system.</span></span>  
  
 <span data-ttu-id="14c13-113">Eine exemplarische Vorgehensweise, die zeigt, wie der SAP BW-Verbindungs-Manager sowie die zugehörige Quelle und das zugehörige Ziel konfiguriert und verwendet werden, finden Sie im Whitepaper [Using SQL Server Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkId=301897)(Verwenden von SQL Server Integration Services und SAP BI 7.0).</span><span class="sxs-lookup"><span data-stu-id="14c13-113">For a walkthrough that demonstrates how to configure and use the SAP BW connection manager, source, and destination, see the white paper, [Using SQL Server Integration Services with SAP BI 7.0](https://go.microsoft.com/fwlink/?LinkId=301897).</span></span> <span data-ttu-id="14c13-114">In diesem Whitepaper wird auch erläutert, wie die erforderlichen Objekte in SAP BW konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="14c13-114">This white paper also shows how to configure the required objects in SAP BW.</span></span>  
  
## <a name="documentation"></a><span data-ttu-id="14c13-115">Dokumentation</span><span class="sxs-lookup"><span data-stu-id="14c13-115">Documentation</span></span>  
 <span data-ttu-id="14c13-116">Diese Hilfedatei für den [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1,1 für SAP BW enthält die folgenden Themen und Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="14c13-116">This Help file for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW contains the following topics and sections:</span></span>  
  
 [<span data-ttu-id="14c13-117">Installieren von Microsoft Connector 1.1 für SAP BW</span><span class="sxs-lookup"><span data-stu-id="14c13-117">Installing the Microsoft Connector for 1.1 SAP BW</span></span>](installing-the-microsoft-connector-for-sap-bw.md)  
 <span data-ttu-id="14c13-118">Beschreibt die Installationsanforderungen für den [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1,1 für SAP BW.</span><span class="sxs-lookup"><span data-stu-id="14c13-118">Describes the installation requirements for the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 [<span data-ttu-id="14c13-119">Komponenten von Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="14c13-119">Microsoft Connector 1.1 for SAP BW Components</span></span>](microsoft-connector-for-sap-bw-components.md)  
 <span data-ttu-id="14c13-120">Beschreibt die einzelnen Komponenten von [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1,1 für SAP BW.</span><span class="sxs-lookup"><span data-stu-id="14c13-120">Describes each component of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
 [<span data-ttu-id="14c13-121">F1-Hilfe zu Microsoft Connector 1.1 for SAP BW</span><span class="sxs-lookup"><span data-stu-id="14c13-121">Microsoft Connector 1.1 for SAP BW F1 Help</span></span>](microsoft-connector-for-sap-bw-f1-help.md)  
 <span data-ttu-id="14c13-122">Beschreibt die Benutzeroberfläche der einzelnen Komponenten von [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1,1 für SAP BW.</span><span class="sxs-lookup"><span data-stu-id="14c13-122">Describes the user interface of each component of the [!INCLUDE[msCoName](../includes/msconame-md.md)] Connector 1.1 for SAP BW.</span></span>  
  
  
