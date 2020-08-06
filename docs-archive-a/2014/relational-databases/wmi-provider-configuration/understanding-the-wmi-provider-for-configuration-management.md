---
title: Grundlegendes zum WMI-Anbieter für die Konfigurations Verwaltung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
helpviewer_keywords:
- WMI Provider for Configuration Management, operations supported
ms.assetid: 92323972-7943-4208-bbf4-050774fb6027
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 0f4f38265093fdb0c27d6bd49ff64ba4b572111e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87607562"
---
# <a name="understanding-the-wmi-provider-for-configuration-management"></a><span data-ttu-id="d17a5-102">Grundlegendes zum WMI-Anbieter für die Konfigurationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="d17a5-102">Understanding the WMI Provider for Configuration Management</span></span>
  [!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="d17a5-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]stellt den WMI-Anbieter für die Konfigurations Verwaltung bereit.</span><span class="sxs-lookup"><span data-stu-id="d17a5-103">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the WMI Provider for Configuration Management.</span></span> <span data-ttu-id="d17a5-104">So können Sie die Windows-Verwaltungsinstrumentation (WMI) verwenden, um [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Dienste, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Client- und Servernetzwerkeinstellungen sowie Serveraliase zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="d17a5-104">This lets you use Windows Management Instrumentation (WMI) to manage [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] services, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] client and server network settings, and server aliases.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="d17a5-105">Dienste, Netzwerkeinstellungen und Aliase werden durch WMI-Objekte im Namespace root\Microsoft\SqlServer\ComputerManagement*NN* des Computers dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d17a5-105">services, network settings, and aliases are represented by WMI objects in the root\Microsoft\SqlServer\ComputerManagement*nn* namespace of the computer.</span></span> <span data-ttu-id="d17a5-106">Nachdem eine Verbindung mit dem WMI-Anbieter auf dem angegebenen Computer hergestellt wurde, können mithilfe von WQL oder einer Skriptsprache Abfragen auf die Dienste, Netzwerkeinstellungen und Aliasnamen ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d17a5-106">After a connection is established with the WMI provider on the specified computer, the services, network settings, and aliases can be queried using WQL or a scripting language.</span></span>  
  
 <span data-ttu-id="d17a5-107">Der WMI-Anbieter ist ein Instanzanbieter.</span><span class="sxs-lookup"><span data-stu-id="d17a5-107">The WMI Provider is an instance provider.</span></span> <span data-ttu-id="d17a5-108">Sie stellt Instanzen der [WMI-Klassen](../wmi-provider-configuration-classes/wmi-provider-for-configuration-management-classes.md) bereit und unterstützt die folgenden asynchronen Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="d17a5-108">It supplies instances of the [WMI Classes](../wmi-provider-configuration-classes/wmi-provider-for-configuration-management-classes.md) and supports the following asynchronous operations.</span></span>  
  
 <span data-ttu-id="d17a5-109">Instanzabruf</span><span class="sxs-lookup"><span data-stu-id="d17a5-109">Instance retrieval</span></span>  
 <span data-ttu-id="d17a5-110">Abrufen einer bestimmten Klassentypinstanz.</span><span class="sxs-lookup"><span data-stu-id="d17a5-110">Retrieval of a particular class type instance.</span></span>  
  
 <span data-ttu-id="d17a5-111">Enumeration</span><span class="sxs-lookup"><span data-stu-id="d17a5-111">Enumeration</span></span>  
 <span data-ttu-id="d17a5-112">Enumeration aller Instanzen eines Klassentyps.</span><span class="sxs-lookup"><span data-stu-id="d17a5-112">Enumeration of all instances of a class type.</span></span>  
  
 <span data-ttu-id="d17a5-113">Modifikation (Modification)</span><span class="sxs-lookup"><span data-stu-id="d17a5-113">Modification</span></span>  
 <span data-ttu-id="d17a5-114">Änderung einer bestimmten Instanz eines Klassentyps.</span><span class="sxs-lookup"><span data-stu-id="d17a5-114">Modification of a particular instance of a class type.</span></span>  
  
 <span data-ttu-id="d17a5-115">Klassen verfügen über Methoden, die die Änderung ihrer Eigenschaften ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d17a5-115">Classes have methods that allow the modification of their properties.</span></span>  
  
 <span data-ttu-id="d17a5-116">Löschen</span><span class="sxs-lookup"><span data-stu-id="d17a5-116">Deletion</span></span>  
 <span data-ttu-id="d17a5-117">Entfernen einer bestimmten Instanz eines Klassentyps.</span><span class="sxs-lookup"><span data-stu-id="d17a5-117">Removing a particular instance of a class type.</span></span>  
  
 <span data-ttu-id="d17a5-118">Abfrageverarbeitung</span><span class="sxs-lookup"><span data-stu-id="d17a5-118">Query processing</span></span>  
 <span data-ttu-id="d17a5-119">Enumeration der Instanzen eines Klassentyps auf Grundlage eines Filters.</span><span class="sxs-lookup"><span data-stu-id="d17a5-119">Enumeration of instances of a class type based on a filter.</span></span>  
  
 <span data-ttu-id="d17a5-120">Beispiele für Verwaltungs Anwendungen, die den WMI-Anbieter für die Konfigurations Verwaltung verwenden, finden [Sie unter Verwenden von WQL und Skriptsprachen mit dem WMI-Anbieter für die Konfigurations Verwaltung](using-wql-and-scripting-languages-with-the-wmi-provider.md).</span><span class="sxs-lookup"><span data-stu-id="d17a5-120">For examples of management application using the WMI Provider for Configuration Management, see [Using WQL and Scripting Languages with the WMI Provider for Configuration Management](using-wql-and-scripting-languages-with-the-wmi-provider.md).</span></span>  
  
 <span data-ttu-id="d17a5-121">Weitere Informationen zu Programmier Verwaltungs Anwendungen, die den WMI-Anbieter verwenden, finden Sie in der WMI-Dokumentation im [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework SDK.</span><span class="sxs-lookup"><span data-stu-id="d17a5-121">For more information about programming management applications using the WMI Provider, see the WMI documentation in the [!INCLUDE[msCoName](../../includes/msconame-md.md)] .NET Framework SDK.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d17a5-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d17a5-122">See Also</span></span>  
 <span data-ttu-id="d17a5-123">[Arbeiten mit dem WMI-Anbieter für die Konfigurations Verwaltung](working-with-the-wmi-provider-for-configuration-management.md) </span><span class="sxs-lookup"><span data-stu-id="d17a5-123">[Working with the WMI Provider for Configuration Management](working-with-the-wmi-provider-for-configuration-management.md) </span></span>  
 [<span data-ttu-id="d17a5-124">Verwenden von WQL und Skriptsprachen mit dem WMI-Anbieter für die Konfigurationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="d17a5-124">Using WQL and Scripting Languages with the WMI Provider for Configuration Management</span></span>](using-wql-and-scripting-languages-with-the-wmi-provider.md)  
  
  
