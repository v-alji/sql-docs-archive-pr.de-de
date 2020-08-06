---
title: Sicherheitskontext (Dialog Feld) (Analysis Services-Mehrdimensionale Daten) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.cubeeditor.browsecube.securitycontext.f1
ms.assetid: 238a4a4b-84bd-4b3d-9f02-f3adf57fa3af
author: minewiskan
ms.author: owend
ms.openlocfilehash: 58d5f71172ac16087ecc342342e70ade234226a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610107"
---
# <a name="security-context-dialog-box-analysis-services---multidimensional-data"></a><span data-ttu-id="3fa6c-102">Dialogfeld 'Sicherheitskontext' (Analysis Services – Mehrdimensionale Daten)</span><span class="sxs-lookup"><span data-stu-id="3fa6c-102">Security Context Dialog Box (Analysis Services - Multidimensional Data)</span></span>
  <span data-ttu-id="3fa6c-103">Mithilfe des Dialogfelds **Sicherheitskontext** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] können Sie den Benutzer und die Rolle ändern, die zur Untersuchung von Daten oder Metadaten für ein [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3fa6c-103">Use the **Security Context** dialog box in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] to change the user and role used to examine data or metadata for a [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="3fa6c-104">Sie können das Dialogfeld **Sicherheitskontext** anzeigen, indem Sie im Cube-Designer auf der Registerkarte **Berechnungen** oder **Browser** im Bereich **Symbolleiste** auf **Sicherheitskontext** klicken.</span><span class="sxs-lookup"><span data-stu-id="3fa6c-104">You can display the **Security Context** dialog box by clicking **Security Context** in the **Toolbar** pane on either the **Calculations** tab or the **Browser** tab in Cube Designer.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3fa6c-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="3fa6c-105">Options</span></span>  
 <span data-ttu-id="3fa6c-106">**Aktueller Benutzer**</span><span class="sxs-lookup"><span data-stu-id="3fa6c-106">**Current user**</span></span>  
 <span data-ttu-id="3fa6c-107">Wählen Sie diese Option aus, um zum Anzeigen der Daten und Metadaten des [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekts die Domäne und den Benutzernamen des aktuellen Benutzers zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3fa6c-107">Select to use the domain and user name of the current user while viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="3fa6c-108">**Anderer Benutzer**</span><span class="sxs-lookup"><span data-stu-id="3fa6c-108">**Other user**</span></span>  
 <span data-ttu-id="3fa6c-109">Geben Sie zum Anzeigen der Daten und Metadaten des [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekts die Domäne und den Benutzernamen eines anderen Benutzers oder einer Gruppe ein.</span><span class="sxs-lookup"><span data-stu-id="3fa6c-109">Type the domain and user name of another user or group to use while viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span>  
  
 <span data-ttu-id="3fa6c-110">Die Domäne und der Name des Benutzers oder der Gruppe folgen dem folgenden Format:</span><span class="sxs-lookup"><span data-stu-id="3fa6c-110">The domain and name of the user or group uses the following format:</span></span>  
  
 <span data-ttu-id="3fa6c-111">*\<Domain name>* **\\** *\<User account name>*</span><span class="sxs-lookup"><span data-stu-id="3fa6c-111">*\<Domain name>* **\\** *\<User account name>*</span></span>  
  
 <span data-ttu-id="3fa6c-112">**Rollen**</span><span class="sxs-lookup"><span data-stu-id="3fa6c-112">**Roles**</span></span>  
 <span data-ttu-id="3fa6c-113">Wählen Sie diese Option aus, um beim Anzeigen der Daten und Metadaten des [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Objekts eine oder mehrere angegebene Rollen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="3fa6c-113">Select to use one or more specified roles when viewing the data and metadata of the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] object.</span></span> <span data-ttu-id="3fa6c-114">Wenn mehrere Rollen in der [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenbank definiert sind, können Sie die zu verwendenden Rollen auswählen.</span><span class="sxs-lookup"><span data-stu-id="3fa6c-114">You can select the roles to use if multiple roles are defined in the [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3fa6c-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3fa6c-115">See Also</span></span>  
 <span data-ttu-id="3fa6c-116">[KPIs &#40;Cube-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3fa6c-116">[KPIs &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](kpis-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 <span data-ttu-id="3fa6c-117">[Browser &#40;Cube-Designer&#41; &#40;Analysis Services Mehrdimensionale Daten&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span><span class="sxs-lookup"><span data-stu-id="3fa6c-117">[Browser &#40;Cube Designer&#41; &#40;Analysis Services - Multidimensional Data&#41;](browser-cube-designer-analysis-services-multidimensional-data.md) </span></span>  
 [<span data-ttu-id="3fa6c-118">Analysis Services Designer und Dialog Felder &#40;Mehrdimensionale Daten&#41;</span><span class="sxs-lookup"><span data-stu-id="3fa6c-118">Analysis Services Designers and Dialog Boxes &#40;Multidimensional Data&#41;</span></span>](analysis-services-designers-and-dialog-boxes-multidimensional-data.md)  
  
  
