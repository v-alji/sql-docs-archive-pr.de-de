---
title: Identitätswechsel Informationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 42319d60-ccd0-46b8-af0b-f0968c390d8a
author: minewiskan
ms.author: owend
ms.openlocfilehash: f9226fdbe8656aecf0f9173976c67ee386040d6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696285"
---
# <a name="impersonation-information"></a><span data-ttu-id="c9f19-102">Identitätswechselinformationen</span><span class="sxs-lookup"><span data-stu-id="c9f19-102">Impersonation Information</span></span>
  <span data-ttu-id="c9f19-103">Verwenden Sie die Seite **Identitätswechselinformationen** , um die Anmeldeinformationen anzugeben, mit denen Analysis Services eine Verbindung mit der Datenquelle herstellt.</span><span class="sxs-lookup"><span data-stu-id="c9f19-103">Use the **Impersonation Information** page to specify the credentials that Analysis Services will use to connect to the data source.</span></span>  
  
## <a name="options"></a><span data-ttu-id="c9f19-104">Tastatur</span><span class="sxs-lookup"><span data-stu-id="c9f19-104">Options</span></span>  
 <span data-ttu-id="c9f19-105">**Bestimmten Windows-Benutzernamen und bestimmtes Kennwort verwenden**</span><span class="sxs-lookup"><span data-stu-id="c9f19-105">**Use a specific Windows user name and password**</span></span>  
 <span data-ttu-id="c9f19-106">Wählen Sie diese Option aus, damit das [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekt die Sicherheitsanmeldeinformationen eines angegebenen Windows-Benutzerkontos verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9f19-106">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials of a specified Windows user account.</span></span> <span data-ttu-id="c9f19-107">Die angegebenen Anmeldeinformationen werden für Verarbeitungsvorgänge, ROLAP-Abfragen, Out-of-Line-Bindungen, lokale Cubes, Miningmodelle, Remotepartitionen, verknüpfte Objekte und Synchronisierungen vom Ziel zur Quelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9f19-107">The specified credentials will be used for processing, ROLAP queries, out-of-line bindings, local cubes, mining models, remote partitions, linked objects, and synchronization from target to source.</span></span> <span data-ttu-id="c9f19-108">Bei OPENQUERY-Anweisungen von Data Mining-Erweiterungen (DMX) wird diese Option jedoch ignoriert, und es werden die Anmeldeinformationen des aktuellen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9f19-108">However, for Data Mining Extensions (DMX) OPENQUERY statements, this option is ignored and the credentials of the current user will be used.</span></span>  
  
 <span data-ttu-id="c9f19-109">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="c9f19-109">**User name**</span></span>  
 <span data-ttu-id="c9f19-110">Geben Sie die Domäne und den Namen des Benutzerkontos ein, die von dem ausgewählten [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekt verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="c9f19-110">Type the domain and name of the user account to be used by the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="c9f19-111">Verwenden Sie das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="c9f19-111">Use the following format:</span></span>  
  
 <span data-ttu-id="c9f19-112">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="c9f19-112">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="c9f19-113">Die Option ist nur verfügbar, wenn die Option **Bestimmten Benutzernamen und bestimmtes Kennwort verwenden** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c9f19-113">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="c9f19-114">**Kennwort**</span><span class="sxs-lookup"><span data-stu-id="c9f19-114">**Password**</span></span>  
 <span data-ttu-id="c9f19-115">Geben Sie das Kennwort des Benutzerkontos ein, das von dem ausgewählten [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekt verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c9f19-115">Type the password of the user account to be used by the selected [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="c9f19-116">Die Option ist nur verfügbar, wenn die Option **Bestimmten Benutzernamen und bestimmtes Kennwort verwenden** ausgewählt ist.</span><span class="sxs-lookup"><span data-stu-id="c9f19-116">This option is enabled only if **Use a specific name and password** is selected.</span></span>  
  
 <span data-ttu-id="c9f19-117">**Dienstkonto verwenden**</span><span class="sxs-lookup"><span data-stu-id="c9f19-117">**Use the service account**</span></span>  
 <span data-ttu-id="c9f19-118">Wählen Sie diese Option aus, damit das [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekt die Anmeldeinformationen mit dem [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Dienst verwendet, der das Objekt verwaltet.</span><span class="sxs-lookup"><span data-stu-id="c9f19-118">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials associated with the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] service that manages the object.</span></span> <span data-ttu-id="c9f19-119">Die Dienstkonto-Anmeldeinformationen werden für Verarbeitungsvorgänge, ROLAP-Abfragen, Remotepartitionen, verknüpfte Objekte und Synchronisierungen vom Ziel zur Quelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9f19-119">The service account credentials will be used for processing, ROLAP queries, remote partitions, linked objects, and synchronization from target to source.</span></span> <span data-ttu-id="c9f19-120">Bei OPENQUERY-Anweisungen von Data Mining-Erweiterungen (DMX), lokalen Cubes und Miningmodellen werden die Anmeldeinformationen des aktuellen Benutzers verwendet.</span><span class="sxs-lookup"><span data-stu-id="c9f19-120">However, for Data Mining Extensions (DMX) OPENQUERY statements, local cubes, and mining models, the credentials of the current user will be used.</span></span> <span data-ttu-id="c9f19-121">Diese Option wird für Out-of-Line-Bindungen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c9f19-121">This option is not supported for out-of-line bindings.</span></span>  
  
 <span data-ttu-id="c9f19-122">**Anmeldeinformationen des aktuellen Benutzers verwenden**</span><span class="sxs-lookup"><span data-stu-id="c9f19-122">**Use the credentials of the current user**</span></span>  
 <span data-ttu-id="c9f19-123">Wählen Sie diese Option aus, damit vom [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekt für Out-of-Line-Bindungen, DMX OPENQUERY-Anweisungen, lokale Cubes und Miningmodelle die Sicherheitsanmeldeinformationen des aktuellen Benutzers verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c9f19-123">Select this option to have the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object use the security credentials of the current user for out-of-line bindings, DMX OPENQUERY, local cubes, and mining models.</span></span> <span data-ttu-id="c9f19-124">Diese Option wird für Verarbeitungsvorgänge, ROLAP-Abfragen, Remotepartitionen, verknüpfte Objekte und Synchronisierungen vom Ziel zur Quelle nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="c9f19-124">This option is not supported for processing, ROLAP queries, remote partitions, linked objects, and synchronization from target to source.</span></span>  
  
 <span data-ttu-id="c9f19-125">**Ver**</span><span class="sxs-lookup"><span data-stu-id="c9f19-125">**Inherit**</span></span>  
 <span data-ttu-id="c9f19-126">Aktivieren Sie diese Option, um das auf Datenbankebene definierte Identitätswechselverhalten zu verwenden. Dies wurde mithilfe der Datenbankeigenschaft `DataSourceImpersonation` vom Serveradministrator festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c9f19-126">Select this option to use the impersonation behavior, defined at the database level, which has been set by the server administrator using the `DataSourceImpersonation` database property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9f19-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c9f19-127">See Also</span></span>  
 <span data-ttu-id="c9f19-128">[Datenquellen in mehrdimensionalen Modellen](multidimensional-models/data-sources-in-multidimensional-models.md) </span><span class="sxs-lookup"><span data-stu-id="c9f19-128">[Data Sources in Multidimensional Models](multidimensional-models/data-sources-in-multidimensional-models.md) </span></span>  
 [<span data-ttu-id="c9f19-129">Unterstützte Datenquellen &#40;mehrdimensionalen SSAS-&#41;</span><span class="sxs-lookup"><span data-stu-id="c9f19-129">Data Sources Supported &#40;SSAS Multidimensional&#41;</span></span>](multidimensional-models/supported-data-sources-ssas-multidimensional.md)  
  
  
