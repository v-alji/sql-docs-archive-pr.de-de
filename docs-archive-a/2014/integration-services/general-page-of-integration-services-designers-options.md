---
title: Seite "Allgemein" | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- VS.ToolsOptionsPages.Business_Intelligence_Designers.Data_Transformation_Designers.General
ms.assetid: d695690a-923b-4036-945e-7621e8651deb
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 59073ac29f95f1e64bd0a9382366e9539ce1408a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87609336"
---
# <a name="general-page"></a><span data-ttu-id="3b956-102">Seite Allgemein</span><span class="sxs-lookup"><span data-stu-id="3b956-102">General Page</span></span>
  <span data-ttu-id="3b956-103">Verwenden Sie die Seite **Allgemein** der Seite **Integration Services-Designer** im Dialogfeld **Optionen** , um die Optionen für das Laden, Anzeigen und Aktualisieren von Paketen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="3b956-103">Use the **General** page of the **Integration Services Designers** page in the **Options** dialog box to specify the options for loading, displaying, and upgrading packages.</span></span>  
  
 <span data-ttu-id="3b956-104">Um die Seite **Allgemein** in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]zu öffnen, klicken Sie im Menü **Extras** auf **Optionen**, erweitern **Business Intelligence-Designer**und wählen **Integration Services-Designer**aus.</span><span class="sxs-lookup"><span data-stu-id="3b956-104">To open the **General** page, in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], on the **Tools** menu, click **Options**, expand **Business Intelligence Designers**, and select **Integration Services Designers**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="3b956-105">Tastatur</span><span class="sxs-lookup"><span data-stu-id="3b956-105">Options</span></span>  
 <span data-ttu-id="3b956-106">**Digitale Signatur beim Laden eines Pakets überprüfen**</span><span class="sxs-lookup"><span data-stu-id="3b956-106">**Check digital signature when loading a package**</span></span>  
 <span data-ttu-id="3b956-107">Wählen Sie diese Option aus, damit [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] die digitale Signatur beim Laden eines Pakets überprüft.</span><span class="sxs-lookup"><span data-stu-id="3b956-107">Select to have [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] check the digital signature when loading a package.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="3b956-108">überprüft nur, ob die digitale Signatur vorhanden und gültig ist und von einer vertrauenswürdigen Quelle stammt.</span><span class="sxs-lookup"><span data-stu-id="3b956-108">will only check whether the digital signature is present, is valid, and is from a trusted source.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="3b956-109">überprüft nicht, ob das Paket seit der Signierung geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="3b956-109">will not check whether the package has been changed since the package was signed.</span></span>  
  
 <span data-ttu-id="3b956-110">Wenn Sie den **BlockedSignatureStates** -Registrierungswert festlegen, überschreibt dieser Registrierungswert die Option **Digitale Signatur beim Laden eines Pakets überprüfen** .</span><span class="sxs-lookup"><span data-stu-id="3b956-110">If you set the **BlockedSignatureStates** registry value, this registry value overrides the **Check digital signature when loading a package** option.</span></span> <span data-ttu-id="3b956-111">Weitere Informationen finden Sie unter [Implementieren einer Signaturrichtlinie durch Festlegen eines Registrierungswerts](implement-a-signing-policy-by-setting-a-registry-value.md).</span><span class="sxs-lookup"><span data-stu-id="3b956-111">For more information, see [Implement a Signing Policy by Setting a Registry Value](implement-a-signing-policy-by-setting-a-registry-value.md).</span></span>  
  
 <span data-ttu-id="3b956-112">Weitere Informationen zu digitalen Zertifikaten und Paketen finden Sie unter [Identifizieren der Quelle von Paketen mit digitalen Signaturen](security/identify-the-source-of-packages-with-digital-signatures.md).</span><span class="sxs-lookup"><span data-stu-id="3b956-112">For more information about digital certificates and packages, see [Identify the Source of Packages with Digital Signatures](security/identify-the-source-of-packages-with-digital-signatures.md).</span></span>  
  
 <span data-ttu-id="3b956-113">**Warnung anzeigen, wenn ein Paket nicht signiert ist**</span><span class="sxs-lookup"><span data-stu-id="3b956-113">**Show warning if package is unsigned**</span></span>  
 <span data-ttu-id="3b956-114">Wählen Sie diese Option aus, wenn beim Laden eines unsignierten Pakets eine Warnung angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3b956-114">Select to display a warning when loading a package that is not signed.</span></span>  
  
 <span data-ttu-id="3b956-115">**Bezeichnungen für Rangfolgeneinschränkungen anzeigen**</span><span class="sxs-lookup"><span data-stu-id="3b956-115">**Show precedence constraint labels**</span></span>  
 <span data-ttu-id="3b956-116">Wählen Sie aus, welche Bezeichnung – Success, Failure oder Completion (Erfolg, Fehler oder Beendet) – bei Rangfolgeneinschränkungen angezeigt werden soll, wenn Sie Pakete in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)] anzeigen.</span><span class="sxs-lookup"><span data-stu-id="3b956-116">Select which label-Success, Failure, or Completion-to display on precedence constraints when viewing packages in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="3b956-117">**"Skriptsprache"**</span><span class="sxs-lookup"><span data-stu-id="3b956-117">**Scripting language**</span></span>  
 <span data-ttu-id="3b956-118">Wählen Sie die Standardskriptsprache für neue Skripttasks und Skriptkomponenten aus.</span><span class="sxs-lookup"><span data-stu-id="3b956-118">Select the default scripting language for new Script tasks and Script components.</span></span>  
  
 <span data-ttu-id="3b956-119">**Verbindungszeichenfolgen zum Verwenden neuer Anbieternamen aktualisieren**</span><span class="sxs-lookup"><span data-stu-id="3b956-119">**Update connection strings to use new provider names**</span></span>  
 <span data-ttu-id="3b956-120">Wenn Sie [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] -Pakete öffnen oder aktualisieren, werden die Verbindungszeichenfolgen für die aktuelle Version von [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]dahingehend aktualisiert, dass sie die Namen für die folgenden Anbieter verwenden:</span><span class="sxs-lookup"><span data-stu-id="3b956-120">When opening or upgrading [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] packages, update connection strings to use the names for the following providers, for the current release of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)][!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)]:</span></span>  
  
-   [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] <span data-ttu-id="3b956-121">OLE DB-Anbieter</span><span class="sxs-lookup"><span data-stu-id="3b956-121">OLE DB provider</span></span>  
  
-   [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="3b956-122">Native Client</span><span class="sxs-lookup"><span data-stu-id="3b956-122">Native Client</span></span>  
  
 <span data-ttu-id="3b956-123">Der [!INCLUDE[ssIS](../includes/ssis-md.md)] -Paketupgrade-Assistent aktualisiert nur Verbindungszeichenfolgen, die in Verbindungs-Managern gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="3b956-123">The [!INCLUDE[ssIS](../includes/ssis-md.md)] Package Upgrade Wizard updates only connection strings that are stored in connection managers.</span></span> <span data-ttu-id="3b956-124">Der Assistent aktualisiert keine Verbindungszeichenfolgen, die dynamisch mithilfe der [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Ausdruckssprache oder mithilfe von Code in einem Skripttask erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="3b956-124">The wizard does not update connection strings that are constructed dynamically by using the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] expression language, or by using code in a Script task.</span></span>  
  
 <span data-ttu-id="3b956-125">**Neue Paket-ID erstellen**</span><span class="sxs-lookup"><span data-stu-id="3b956-125">**Create new package ID**</span></span>  
 <span data-ttu-id="3b956-126">Erstellen Sie beim Upgrade von [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] -Paketen neue Paket-IDs für die aktualisierten Versionen der Pakete.</span><span class="sxs-lookup"><span data-stu-id="3b956-126">When upgrading [!INCLUDE[ssISversion2005](../includes/ssisversion2005-md.md)] packages, create new package IDs for the upgraded versions of the packages.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b956-127">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3b956-127">See Also</span></span>  
 <span data-ttu-id="3b956-128">[Sicherheitsübersicht &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span><span class="sxs-lookup"><span data-stu-id="3b956-128">[Security Overview &#40;Integration Services&#41;](security/security-overview-integration-services.md) </span></span>  
 [<span data-ttu-id="3b956-129">Erweitern von Paketen mit Skripts</span><span class="sxs-lookup"><span data-stu-id="3b956-129">Extending Packages with Scripting</span></span>](extending-packages-scripting/extending-packages-with-scripting.md)  
  
  
