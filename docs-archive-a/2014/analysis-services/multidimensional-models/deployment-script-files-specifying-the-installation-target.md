---
title: Angeben des Installations Ziels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- input files [Analysis Services]
- installation targets [Analysis Services]
- Analysis Services deployments, installation targets
- Analysis Services Deployment Wizard, installation targets
- deploying [Analysis Services], installation targets
- modifying installation targets
ms.assetid: cb706817-6f63-4771-92c3-b70030bbce3d
author: minewiskan
ms.author: owend
ms.openlocfilehash: e830fc353898e3ec835b338e84765a0cad0de43f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618937"
---
# <a name="specifying-the-installation-target"></a><span data-ttu-id="f221b-102">Angeben des Installationszieles</span><span class="sxs-lookup"><span data-stu-id="f221b-102">Specifying the Installation Target</span></span>
  <span data-ttu-id="f221b-103">Der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Bereitstellungs-Assistent liest die Informationen zum Installationsziel aus der \<*project name*> Datei ". deploymenttargets".</span><span class="sxs-lookup"><span data-stu-id="f221b-103">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard reads the installation target information from the \<*project name*>.deploymenttargets file.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="f221b-104">erstellt diese Datei, wenn Sie das [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Projekt erstellen.</span><span class="sxs-lookup"><span data-stu-id="f221b-104">creates this file when you build the [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project.</span></span> [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]<span data-ttu-id="f221b-105">verwendet die Datenbank und den Server, die auf der Seite **Bereitstellung** des Dialog Felds *\<project name>* **Eigenschaften Seiten** angegeben sind, um die targets-Datei zu erstellen \<*project name*> .</span><span class="sxs-lookup"><span data-stu-id="f221b-105">uses the database and server specified on the **Deployment** page of the *\<project name>* **Properties Pages** dialog box to create the \<*project name*>.targets file.</span></span>  
  
## <a name="modifying-the-installation-target-for-deployment"></a><span data-ttu-id="f221b-106">Ändern des Installationszieles für die Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="f221b-106">Modifying the Installation Target for Deployment</span></span>  
 <span data-ttu-id="f221b-107">In einigen Situationen müssen Sie möglicherweise ein [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt für eine andere Datenbank oder eine andere Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] bereitstellen, als auf der Seite **Bereitstellung** angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="f221b-107">In some situations, you may need to deploy an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to a database or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance that is different than the one specified on the **Deployment** page.</span></span> <span data-ttu-id="f221b-108">Vielleicht möchten Sie das Projekt, bevor Sie es bereitstellen, erst auf einem Server zum Testen bereitstellen und es nach Abschluss der Testes auf einem Produktionsserver bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f221b-108">For example, you may want to deploy the project to a server for testing before deployment, and then deploy it to a production server after testing is finished.</span></span> <span data-ttu-id="f221b-109">Sie können aber auch ein abgeschlossenes und getestetes Projekt auf mehreren Produktionsservern in einem Netzwerklastenausgleich-Cluster oder auf einem Stagingserver und einem Produktionsserver bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="f221b-109">You may also want to deploy a completed and tested project to multiple production servers in a Network Load Balancing cluster, or to a staging server and a production server.</span></span>  
  
 <span data-ttu-id="f221b-110">Sie können mit einer der im Folgenden beschriebenen Methoden das Installationsziel in der Eingabedatei ändern, um ein [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt auf einer anderen Datenbank oder einer anderen Instanz von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="f221b-110">To deploy an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project to a different database or [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance, you can change the installation target in the input file by using one of the methods described in the following procedure.</span></span>  
  
#### <a name="to-change-the-installation-target-after-the-input-files-have-been-generated"></a><span data-ttu-id="f221b-111">So ändern Sie das Installationsziel, nachdem die Eingabedateien erstellt wurden</span><span class="sxs-lookup"><span data-stu-id="f221b-111">To change the installation target after the input files have been generated</span></span>  
  
-   <span data-ttu-id="f221b-112">Führen Sie den Bereitstellungs-Assistenten für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] interaktiv aus.</span><span class="sxs-lookup"><span data-stu-id="f221b-112">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard interactively.</span></span> <span data-ttu-id="f221b-113">Geben Sie auf der Seite **Installationsziel** ein neues Ziel für die Instanz und die Datenbank von [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] an.</span><span class="sxs-lookup"><span data-stu-id="f221b-113">On the **Installation Target** page, specify a new destination for the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance and database.</span></span>  
  
     <span data-ttu-id="f221b-114">Oder</span><span class="sxs-lookup"><span data-stu-id="f221b-114">-or-</span></span>  
  
-   <span data-ttu-id="f221b-115">Führen Sie den Bereitstellungs-Assistenten für [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] an der Eingabeaufforderung aus, und legen Sie fest, dass der Assistent im Antwortdateimodus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f221b-115">Run the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Deployment Wizard at the command prompt and set the wizard to run in answer file mode.</span></span> <span data-ttu-id="f221b-116">Weitere Informationen zum Antwortdateimodus finden Sie unter [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="f221b-116">For more information about answer file mode, see [Running the Analysis Services Deployment Wizard](running-the-analysis-services-deployment-wizard.md).</span></span>  
  
     <span data-ttu-id="f221b-117">Oder</span><span class="sxs-lookup"><span data-stu-id="f221b-117">-or-</span></span>  
  
-   <span data-ttu-id="f221b-118">Ändern \<*project name*> Sie die Datei deploymenttargets mit einem beliebigen Text-Editor.</span><span class="sxs-lookup"><span data-stu-id="f221b-118">Modify the \<*project name*>.deploymenttargets file by using any text editor.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f221b-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f221b-119">See Also</span></span>  
 <span data-ttu-id="f221b-120">[Angeben von Bereitstellungs Optionen für Partitionen und Rollen](deployment-script-files-partition-and-role-deployment-options.md) </span><span class="sxs-lookup"><span data-stu-id="f221b-120">[Specifying Partition and Role Deployment Options](deployment-script-files-partition-and-role-deployment-options.md) </span></span>  
 <span data-ttu-id="f221b-121">[Angeben von Konfigurationseinstellungen für die Lösungs Bereitstellung](deployment-script-files-solution-deployment-config-settings.md) </span><span class="sxs-lookup"><span data-stu-id="f221b-121">[Specifying Configuration Settings for Solution Deployment](deployment-script-files-solution-deployment-config-settings.md) </span></span>  
 [<span data-ttu-id="f221b-122">Angeben von Verarbeitungsoptionen</span><span class="sxs-lookup"><span data-stu-id="f221b-122">Specifying Processing Options</span></span>](deployment-script-files-specifying-processing-options.md)  
  
  
