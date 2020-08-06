---
title: Verbinden einer Power Pivot-Dienst Anwendung mit einer SharePoint-Webanwendung in der zentral Administration | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: a5da8e29-7ffd-44e7-bf61-344fa5bea8ce
author: minewiskan
ms.author: owend
ms.openlocfilehash: 5fc6dcde4cc2d18c3650adbab0ec71ef5c6265cb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620586"
---
# <a name="connect-a-powerpivot-service-application-to-a-sharepoint-web-application-in-central-administration"></a><span data-ttu-id="943c7-102">Verbinden einer Power Pivot-Dienst Anwendung mit einer SharePoint-Webanwendung in der zentral Administration</span><span class="sxs-lookup"><span data-stu-id="943c7-102">Connect a PowerPivot Service Application to a SharePoint Web Application in Central Administration</span></span>
  <span data-ttu-id="943c7-103">Eine PowerPivot-Dienstanwendung kann von einer beliebigen Anzahl von SharePoint-Webanwendungen in der Farm verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="943c7-103">A PowerPivot service application can be used by any number of SharePoint Web applications in the farm.</span></span> <span data-ttu-id="943c7-104">Um eine PowerPivot-Dienstanwendung zur Verfügung zu stellen, fügen Sie sie einer Dienstzuordnungsliste hinzu.</span><span class="sxs-lookup"><span data-stu-id="943c7-104">To make a PowerPivot service application available, you add it to a service association list.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="943c7-105">Damit das PowerPivot-Management-Dashboard ordnungsgemäß funktioniert, muss eine PowerPivot-Dienstanwendung in der Standardverbindungsgruppe enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="943c7-105">You must have one PowerPivot service application in the default group to ensure that PowerPivot Management Dashboard works properly.</span></span> <span data-ttu-id="943c7-106">Fügen Sie nicht mehr als eine PowerPivot-Dienstanwendung zu der Standardgruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="943c7-106">Do not add more than one PowerPivot service application to the default group.</span></span> <span data-ttu-id="943c7-107">Das Hinzufügen mehrerer Einträge des gleichen Dienstanwendungstyps ist keine unterstützte Konfiguration und könnte Fehler verursachen.</span><span class="sxs-lookup"><span data-stu-id="943c7-107">Adding multiple entries of the same service application type is not a supported configuration and might cause errors.</span></span> <span data-ttu-id="943c7-108">Wenn Sie zusätzliche Dienstanwendungen erstellen, fügen Sie sie benutzerdefinierten Listen hinzu.</span><span class="sxs-lookup"><span data-stu-id="943c7-108">If you are creating additional service applications, add them to custom lists.</span></span>  
  
 <span data-ttu-id="943c7-109">Dieses Thema enthält folgende Abschnitte:</span><span class="sxs-lookup"><span data-stu-id="943c7-109">This topic contains the following sections:</span></span>  
  
 [<span data-ttu-id="943c7-110">Hinzufügen einer PowerPivot-Dienstanwendung zur Standardgruppe</span><span class="sxs-lookup"><span data-stu-id="943c7-110">Add PowerPivot Services Application to the Default Group</span></span>](#default)  
  
 [<span data-ttu-id="943c7-111">Hinzufügen einer PowerPivot-Dienstanwendung zu einer benutzerdefinierten Dienstzuordnungsliste</span><span class="sxs-lookup"><span data-stu-id="943c7-111">Add PowerPivot Services Application a Custom Service Association List</span></span>](#custom)  
  
##  <a name="add-powerpivot-services-application-to-the-default-group"></a><a name="default"></a><span data-ttu-id="943c7-112">Power Pivot-Dienst Anwendung zur Standardgruppe hinzufügen</span><span class="sxs-lookup"><span data-stu-id="943c7-112">Add PowerPivot Services Application to the Default Group</span></span>  
 <span data-ttu-id="943c7-113">Eine Dienstanwendungsliste ist eine Liste freigegebener Dienste, die Ressourcen für andere SharePoint-Webanwendungen in der Farm bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="943c7-113">A service association list is a list of shared services that provide resources to other SharePoint Web applications in the farm.</span></span> <span data-ttu-id="943c7-114">Es gibt eine Standardgruppe von Dienstzuordnungen für die Farm.</span><span class="sxs-lookup"><span data-stu-id="943c7-114">There is one default group of service associations for the farm.</span></span>  
  
 <span data-ttu-id="943c7-115">Eine PowerPivot-Dienstanwendung kann der Liste entweder hinzugefügt werden, wenn Sie die Anwendung erstellen oder im Anschluss daran mithilfe folgender Schritte.</span><span class="sxs-lookup"><span data-stu-id="943c7-115">To be on the list, a PowerPivot service application can either be added when you create the application or afterwards by using the following steps.</span></span>  
  
1.  <span data-ttu-id="943c7-116">Klicken Sie in der Zentraladministration unter **Anwendungsverwaltung**auf **Dienstanwendungszuordnungen konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="943c7-116">In Central Administration, in **Application Management**, click **Configure service application associations**.</span></span>  
  
2.  <span data-ttu-id="943c7-117">Klicken Sie unter Anwendungsproxygruppe auf **Standard**.</span><span class="sxs-lookup"><span data-stu-id="943c7-117">In Application Proxy Group, click **default**.</span></span>  
  
3.  <span data-ttu-id="943c7-118">Aktivieren Sie das Kontrollkästchen neben der PowerPivot-Dienstanwendung (durch den Typnamen `PowerPivot Service Application Proxy` gekennzeichnet).</span><span class="sxs-lookup"><span data-stu-id="943c7-118">Select the checkbox next to the PowerPivot service application (indicated by type name `PowerPivot Service Application Proxy`).</span></span> <span data-ttu-id="943c7-119">Bei mehreren PowerPivot-Dienstanwendung wählen Sie nur eine Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="943c7-119">If you have more than one PowerPivot service application, choose just one.</span></span>  
  
4.  <span data-ttu-id="943c7-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="943c7-120">Click **OK**.</span></span>  
  
##  <a name="add-powerpivot-services-application-a-custom-service-association-list"></a><a name="custom"></a><span data-ttu-id="943c7-121">Power Pivot-Dienst Anwendung zu einer benutzerdefinierten Dienst Zuordnungs Liste hinzufügen</span><span class="sxs-lookup"><span data-stu-id="943c7-121">Add PowerPivot Services Application a Custom Service Association List</span></span>  
 <span data-ttu-id="943c7-122">Die Standardgruppe kann durch eine benutzerdefinierte Liste ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="943c7-122">The default group can be replaced by a custom list.</span></span> <span data-ttu-id="943c7-123">Eine benutzerdefinierte Liste wird speziell für eine einzelne SharePoint-Webanwendung erstellt.</span><span class="sxs-lookup"><span data-stu-id="943c7-123">A custom list is created specifically for a single SharePoint Web application.</span></span> <span data-ttu-id="943c7-124">Dabei wird die Standardgruppe überschrieben und durch vom Farm- oder Dienstadministrator angegebene Dienstzuordnungen ersetzt.</span><span class="sxs-lookup"><span data-stu-id="943c7-124">It overrides the default group and replaces it with only those service associations that a farm or service administrator specifies.</span></span> <span data-ttu-id="943c7-125">Wenn Sie mehrere PowerPivot-Dienstanwendungen erstellt haben, müssen Sie die zu verwendende Anwendung mithilfe einer benutzerdefinierten Liste angeben.</span><span class="sxs-lookup"><span data-stu-id="943c7-125">If you created multiple PowerPivot service applications, you must use a custom list to specify which one to use.</span></span> <span data-ttu-id="943c7-126">Eine benutzerdefinierte Liste kann nicht von anderen Webanwendungen wiederverwendet werden.</span><span class="sxs-lookup"><span data-stu-id="943c7-126">A custom list cannot be reused by other Web applications.</span></span> <span data-ttu-id="943c7-127">Sie gilt nur für die Webanwendung, für die sie erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="943c7-127">It applies only to the Web application for which it was created.</span></span>  
  
1.  <span data-ttu-id="943c7-128">Klicken Sie in der Zentraladministration unter **Anwendungsverwaltung**auf **Webanwendungen verwalten**.</span><span class="sxs-lookup"><span data-stu-id="943c7-128">In Central Administration, in **Application Management**, click **Manage web applications**.</span></span>  
  
2.  <span data-ttu-id="943c7-129">Wählen Sie die Anwendung (z. B. SharePoint -80) aus.</span><span class="sxs-lookup"><span data-stu-id="943c7-129">Select the application (for example, SharePoint -80).</span></span>  
  
3.  <span data-ttu-id="943c7-130">Klicken Sie in Webanwendungen unter „Verwalten“ auf **Dienstverbindungen**.</span><span class="sxs-lookup"><span data-stu-id="943c7-130">In Web Applications, in Manage, click **Service Connections**.</span></span>  
  
4.  <span data-ttu-id="943c7-131">Wählen Sie unter **Folgende Zuordnungsgruppe bearbeiten**die Option **[Benutzerdefiniert]** aus.</span><span class="sxs-lookup"><span data-stu-id="943c7-131">In **Edit the following group of connections**, select **[custom]**.</span></span>  
  
5.  <span data-ttu-id="943c7-132">Aktivieren Sie das Kontrollkästchen neben jeder Dienstanwendungsverbindung, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="943c7-132">Select the checkbox next to each service application connection you want to use.</span></span> <span data-ttu-id="943c7-133">Falls Sie über mehrere PowerPivot-Dienstanwendungen verfügen (am Typ `PowerPivot Service Application Proxy` erkennbar), achten Sie darauf, nur eine auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="943c7-133">If you have multiple PowerPivot service applications (indicated by Type set to `PowerPivot Service Application Proxy`), be sure to choose only one.</span></span>  
  
6.  <span data-ttu-id="943c7-134">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="943c7-134">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="943c7-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="943c7-135">See Also</span></span>  
 <span data-ttu-id="943c7-136">[Erstellen und Konfigurieren einer Power Pivot-Dienst Anwendung in der zentral Administration](create-and-configure-power-pivot-service-application-in-ca.md) </span><span class="sxs-lookup"><span data-stu-id="943c7-136">[Create and Configure a PowerPivot Service Application in Central Administration](create-and-configure-power-pivot-service-application-in-ca.md) </span></span>  
 [<span data-ttu-id="943c7-137">Anfängliche Konfiguration &#40;PowerPivot für SharePoint&#41;</span><span class="sxs-lookup"><span data-stu-id="943c7-137">Initial Configuration &#40;PowerPivot for SharePoint&#41;</span></span>](../../sql-server/install/initial-configuration-powerpivot-for-sharepoint.md)  
  
  
