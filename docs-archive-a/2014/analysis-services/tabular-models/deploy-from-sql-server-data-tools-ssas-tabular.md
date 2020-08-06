---
title: Bereitstellung aus SQL Server Data Tools (SSAS-Tabelle) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.deploystatus.f1
ms.assetid: 67dde3fe-ba43-41f3-b56c-c656029ee93f
author: minewiskan
ms.author: owend
ms.openlocfilehash: 8bc8008e7c79e1652b54b21e6afb116301d1700b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618919"
---
# <a name="deploy-from-sql-server-data-tools-ssas-tabular"></a><span data-ttu-id="10bb8-102">Bereitstellen in SQL Server-Datentools (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="10bb8-102">Deploy From SQL Server Data Tools (SSAS Tabular)</span></span>
  <span data-ttu-id="10bb8-103">Verwenden Sie die Aufgaben in diesem Thema, um mit dem Befehl "Bereitstellen" in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]eine Projektmappe für tabellarische Modelle bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="10bb8-103">Use the tasks in this topic to deploy a tabular model solution by using the Deploy command in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
 <span data-ttu-id="10bb8-104">Abschnitte in diesem Thema:</span><span class="sxs-lookup"><span data-stu-id="10bb8-104">Sections in this topic:</span></span>  
  
-   [<span data-ttu-id="10bb8-105">Konfigurieren von Bereitstellungs Optionen und Bereitstellungs Server Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="10bb8-105">Configure Deployment Options and Deployment Server Properties</span></span>](#bkmk_deploy)  
  
-   [<span data-ttu-id="10bb8-106">Bereitstellen einer Projektmappe für tabellarische Modelle</span><span class="sxs-lookup"><span data-stu-id="10bb8-106">Deploy a Tabular Model Solution</span></span>](#bkmk_deploy_proc)  
  
-   [<span data-ttu-id="10bb8-107">Bereitstellungsstatus</span><span class="sxs-lookup"><span data-stu-id="10bb8-107">Deploy Status</span></span>](#bkmk_deploy_status)  
  
##  <a name="configure-deployment-options-and-deployment-server-properties"></a><a name="bkmk_deploy"></a><span data-ttu-id="10bb8-108">Konfigurieren von Bereitstellungs Optionen und Bereitstellungs Server Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="10bb8-108">Configure Deployment Options and Deployment Server Properties</span></span>  
 <span data-ttu-id="10bb8-109">Bevor Sie die Projektmappe für tabellarische Modelle bereitstellen, müssen Sie die Eigenschaft Bereitstellungsoptionen und die Eigenschaft Bereitstellungsserver angeben.</span><span class="sxs-lookup"><span data-stu-id="10bb8-109">Before you deploy your tabular model solution, you must first specify the Deployment Options and Deployment Server properties.</span></span> <span data-ttu-id="10bb8-110">Weitere Informationen zu Bereitstellungseigenschaften und -einstellungen finden Sie unter [Bereitstellung von Tabellenmodelllösungen &#40;SSAS – tabellarisch&#41;](tabular-model-solution-deployment-ssas-tabular.md)eine Projektmappe für tabellarische Modelle bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="10bb8-110">For more information about deployment properties and settings, see [Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-model-solution-deployment-ssas-tabular.md).</span></span>  
  
#### <a name="to-configure-deployment-options-and-deployment-server-properties"></a><span data-ttu-id="10bb8-111">So konfigurieren Sie die Eigenschaften "Bereitstellungsoptionen" und "Bereitstellungsserver"</span><span class="sxs-lookup"><span data-stu-id="10bb8-111">To configure Deployment Options and Deployment Server properties</span></span>  
  
1.  <span data-ttu-id="10bb8-112">Klicken Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]im **Projektmappen-Explorer**mit der rechten Maustaste auf den Projektnamen, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="10bb8-112">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], in **Solution Explorer**, right-click the project name, and then click **Properties**.</span></span>  
  
2.  <span data-ttu-id="10bb8-113">Geben Sie im Dialogfeld \*\* \<project name> Eigenschaften\*\* unter **Bereitstellungs Optionen**die Eigenschaften Einstellungen an, falls diese von den Standardeinstellungen abweichen.</span><span class="sxs-lookup"><span data-stu-id="10bb8-113">In the **\<project name> Properties** dialog, in **Deployment Options**, specify property settings if different from the default settings.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="10bb8-114">Für Modelle, die sich im zwischengespeicherten Modus befinden, ist der **Abfragemodus** immer auf **InMemory**festgelegt.</span><span class="sxs-lookup"><span data-stu-id="10bb8-114">For models in cached mode, **Query Mode** is always **In-Memory**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="10bb8-115">Für Modelle im DirectQuery-Modus können keine **Identitätswechseleinstellungen** angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="10bb8-115">You cannot specify **Impersonation Settings** for models in DirectQuery mode.</span></span>  
  
3.  <span data-ttu-id="10bb8-116">Legen Sie unter **Bereitstellungsserver**die Einstellungen der Eigenschaften **Server** (Name), **Edition**, **Datenbank** (Name) und **Cubename** fest, falls diese von den Standardeinstellungen abweichen, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="10bb8-116">In **Deployment Server**, specify the **Server** (name), **Edition**, **Database** (name), and **Cube Name** property settings, if different from the default settings, and then click **OK**.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="10bb8-117">Sie können auch die Einstellung der Eigenschaft Standardbereitstellungsserver angeben, damit alle neu erstellten Projekte automatisch auf dem angegebenen Server bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="10bb8-117">You can also specify the Default Deployment Server property setting so any new projects you create will automatically be deployed to the specified server.</span></span> <span data-ttu-id="10bb8-118">Weitere Informationen finden Sie unter [Konfigurieren von Standarddatenmodellierung und Bereitstellungseigenschaften &#40;SSAS – tabellarisch&#41;](properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="10bb8-118">For more information, see [Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;](properties-ssas-tabular.md).</span></span>  
  
##  <a name="deploy-a-tabular-model-solution"></a><a name="bkmk_deploy_proc"></a><span data-ttu-id="10bb8-119">Bereitstellen einer Lösung für tabellarische Modelle</span><span class="sxs-lookup"><span data-stu-id="10bb8-119">Deploy a Tabular Model Solution</span></span>  
  
#### <a name="to-deploy-a-tabular-model-solution"></a><span data-ttu-id="10bb8-120">So stellen Sie eine Projektmappe für tabellarische Modelle bereit</span><span class="sxs-lookup"><span data-stu-id="10bb8-120">To deploy a tabular model solution</span></span>  
  
-   <span data-ttu-id="10bb8-121">[!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]Klicken Sie in im Menü **Erstellen** auf bereitstellen. \*\* \<project name> \*\*</span><span class="sxs-lookup"><span data-stu-id="10bb8-121">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], on the **Build** menu, click **Deploy \<project name>**.</span></span>  
  
     <span data-ttu-id="10bb8-122">Im Dialogfeld **Bereitstellen** wird der Status der Metadatenbereitstellung und der Verarbeitung jeder im Modell enthaltenen Tabelle angezeigt (es sei denn, die Eigenschaft „Verarbeitungsoption“ wurde auf „Nicht verarbeiten“ festgelegt).</span><span class="sxs-lookup"><span data-stu-id="10bb8-122">The **Deploy** dialog box will appear and indicate the status of the metadata deployment and the processing (unless Processing Option property is set to Do Not Process) of each table included in the model.</span></span> <span data-ttu-id="10bb8-123">Stellen Sie nach Abschluss des Bereitstellungsprozesses mit [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] eine Verbindung mit der Analysis Services-Instanz her, und überprüfen Sie, ob das neue Modelldatenbankobjekt erstellt wurde, oder verwenden Sie die Clientberichterstellungsanwendung, um eine Verbindung mit dem bereitgestellten Modell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="10bb8-123">After the deployment process is complete, use [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to connect to the Analysis Services instance and verify the new model database object has been created or use a client reporting application to connect to the deployed model.</span></span>  
  
##  <a name="deploy-status"></a><a name="bkmk_deploy_status"></a><span data-ttu-id="10bb8-124">Bereitstellungs Status</span><span class="sxs-lookup"><span data-stu-id="10bb8-124">Deploy Status</span></span>  
 <span data-ttu-id="10bb8-125">Im Dialogfeld **Bereitstellen** können Sie den Status eines Bereitstellungsvorgangs überwachen.</span><span class="sxs-lookup"><span data-stu-id="10bb8-125">The **Deploy** dialog box enables you to monitor the progress of a Deploy operation.</span></span> <span data-ttu-id="10bb8-126">Außerdem kann ein Bereitstellungsvorgang beendet werden.</span><span class="sxs-lookup"><span data-stu-id="10bb8-126">A deploy operation can also be stopped.</span></span>  
  
 <span data-ttu-id="10bb8-127">**Status**</span><span class="sxs-lookup"><span data-stu-id="10bb8-127">**Status**</span></span>  
 <span data-ttu-id="10bb8-128">Gibt an, ob der Bereitstellungsvorgang erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="10bb8-128">Indicates whether the Deploy operation was successful or not.</span></span>  
  
 <span data-ttu-id="10bb8-129">**Details**</span><span class="sxs-lookup"><span data-stu-id="10bb8-129">**Details**</span></span>  
 <span data-ttu-id="10bb8-130">Listet die bereitgestellten Metadatenelemente sowie den Status für jedes Metadatenelement auf und stellt eine Meldung über etwaige Probleme bereit.</span><span class="sxs-lookup"><span data-stu-id="10bb8-130">Lists the metadata items that were deployed, the status for each metadata item, and provides a message of any issues.</span></span>  
  
 <span data-ttu-id="10bb8-131">**Bereitstellung beenden**</span><span class="sxs-lookup"><span data-stu-id="10bb8-131">**Stop Deploy**</span></span>  
 <span data-ttu-id="10bb8-132">Klicken Sie auf diese Option, um den Bereitstellungsvorgang anzuhalten.</span><span class="sxs-lookup"><span data-stu-id="10bb8-132">Click to halt the Deploy operation.</span></span> <span data-ttu-id="10bb8-133">Diese Option ist nützlich, wenn der Bereitstellungsvorgang zu lange dauert oder wenn es zu viele Fehler gibt.</span><span class="sxs-lookup"><span data-stu-id="10bb8-133">This option is useful if the Deploy operation is taking too long, or if there are too many errors.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="10bb8-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="10bb8-134">See Also</span></span>  
 <span data-ttu-id="10bb8-135">[Bereitstellung von Tabellen Modelllösungen &#40;tabellarischen SSAS-&#41;](tabular-model-solution-deployment-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="10bb8-135">[Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-model-solution-deployment-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="10bb8-136">Konfigurieren von Standarddatenmodellierung und Bereitstellungseigenschaften &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="10bb8-136">Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;</span></span>](properties-ssas-tabular.md)  
  
  
