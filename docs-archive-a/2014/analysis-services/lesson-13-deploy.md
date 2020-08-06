---
title: 'Lektion 14: Bereitstellen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: 24863a8a-9017-415a-a97b-fbac76ed0675
author: minewiskan
ms.author: owend
ms.openlocfilehash: c1a55960a0c33a386d978f3c15e489ed7bd861ce
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608036"
---
# <a name="lesson-14-deploy"></a><span data-ttu-id="b55ff-102">Lektion 14: Bereitstellen</span><span class="sxs-lookup"><span data-stu-id="b55ff-102">Lesson 14: Deploy</span></span>
  <span data-ttu-id="b55ff-103">In dieser Lektion konfigurieren Sie Bereitstellungseigenschaften, wobei Sie eine Bereitstellungsserverinstanz von Analysis Services im Tabellenmodus sowie einen Namen für das bereitgestellte Modell angeben.</span><span class="sxs-lookup"><span data-stu-id="b55ff-103">In this lesson, you will configure deployment properties; specifying a deployment server instance of Analysis Services running in Tabular mode, and a name for the model you deploy.</span></span> <span data-ttu-id="b55ff-104">Sie stellen dann das Modell auf dieser Instanz bereit.</span><span class="sxs-lookup"><span data-stu-id="b55ff-104">You will then deploy the model to that instance.</span></span> <span data-ttu-id="b55ff-105">Nach der Bereitstellung können Benutzer unter Verwendung einer Clientanwendung zur Berichtserstellung eine Verbindung zum Modell herstellen.</span><span class="sxs-lookup"><span data-stu-id="b55ff-105">After it is deployed, users can connect to the model by using a reporting client application.</span></span> <span data-ttu-id="b55ff-106">Weitere Informationen finden Sie unter [Bereitstellung von Tabellenmodelllösungen &#40;SSAS – tabellarisch&#41;](tabular-models/tabular-model-solution-deployment-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="b55ff-106">To learn more, see [Tabular Model Solution Deployment &#40;SSAS Tabular&#41;](tabular-models/tabular-model-solution-deployment-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="b55ff-107">Geschätzte Zeit zum Bearbeiten dieser Lektion: **5 Minuten**</span><span class="sxs-lookup"><span data-stu-id="b55ff-107">Estimated time to complete this lesson: **5 minutes**</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b55ff-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b55ff-108">Prerequisites</span></span>  
 <span data-ttu-id="b55ff-109">Dieses Thema ist Teil eines Tutorials zur Tabellenmodellierung, das in der richtigen Reihenfolge absolviert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="b55ff-109">This topic is part of a tabular modeling tutorial, which should be completed in order.</span></span> <span data-ttu-id="b55ff-110">Sie sollten vor dem Ausführen der Aufgaben in dieser Lektion die vorherige Lektion abgeschlossen haben: [Lektion 13: Analysieren in Excel](lesson-12-analyze-in-excel.md).</span><span class="sxs-lookup"><span data-stu-id="b55ff-110">Before performing the tasks in this lesson, you should have completed the previous lesson: [Lesson 13: Analyze in Excel](lesson-12-analyze-in-excel.md).</span></span>  
  
## <a name="deploy-the-model"></a><span data-ttu-id="b55ff-111">Bereitstellen des Modells</span><span class="sxs-lookup"><span data-stu-id="b55ff-111">Deploy the Model</span></span>  
  
#### <a name="to-configure-deployment-properties"></a><span data-ttu-id="b55ff-112">So Konfigurieren Sie die Bereitstellungseigenschaften</span><span class="sxs-lookup"><span data-stu-id="b55ff-112">To configure deployment properties</span></span>  
  
1.  <span data-ttu-id="b55ff-113">Klicken Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]im **Projektmappen-Explorer**mit der rechten Maustaste auf das Projekt für das **Tabellenmodell für die Adventure Works-Internetverkäufe** . Klicken Sie anschließend im Kontextmenü auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="b55ff-113">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], in **Solution Explorer**, right-click on the **Adventure Works Internet Sales Tabular Model** project, and then in the context menu, click **Properties**.</span></span>  
  
2.  <span data-ttu-id="b55ff-114">Klicken Sie im Dialogfeld für die **Eigenschaftenseiten des Tabellenmodells für AW-Internetverkäufe** unter **Bereitstellungsserver**in der Eigenschaft **Server** den Namen einer Analysis Services-Instanz ein, die im Tabellenmodus ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b55ff-114">In the **AW Internet Sales Tabular Model Property Pages** dialog box, under **Deployment Server**, in the **Server** property, type the name of an Analysis Services instance running in Tabular mode.</span></span> <span data-ttu-id="b55ff-115">Dies ist die Instanz, auf der das Modell bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="b55ff-115">This will be the instance your model will be deployed to.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="b55ff-116">Sie benötigen für die Bereitstellung auf einer Analysis Services-Remoteinstanz entsprechende Administratorberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="b55ff-116">You must have Administrator permissions on a remote Analysis Services instance in-order to deploy to it.</span></span>  
  
3.  <span data-ttu-id="b55ff-117">Vergewissern Sie sich, dass die Eigenschaft **Abfrage Modus** auf **in-Memory**festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="b55ff-117">Verify the **Query Mode** property is set to **In-Memory**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="b55ff-118">Das in diesem Lernprogramm erstellte Modell wird im DirectQuery-Modus nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b55ff-118">The model created by using this tutorial is not supported in DirectQuery mode.</span></span>  
  
4.  <span data-ttu-id="b55ff-119">Geben Sie in der Eigenschaft **Datenbank** den Namen ein `Adventure Works Internet Sales Model` .</span><span class="sxs-lookup"><span data-stu-id="b55ff-119">In the **Database** property, type `Adventure Works Internet Sales Model`.</span></span>  
  
5.  <span data-ttu-id="b55ff-120">Geben Sie in der Eigenschaft **Cube** Name den Namen ein `Adventure Works Internet Sales Model` .</span><span class="sxs-lookup"><span data-stu-id="b55ff-120">In the **Cube** Name property, type `Adventure Works Internet Sales Model`.</span></span>  
  
6.  <span data-ttu-id="b55ff-121">Überprüfen Sie die Auswahl, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b55ff-121">Verify your selections and then click **OK**.</span></span>  
  
#### <a name="to-deploy-the-adventure-works-internet-sales-tabular-model"></a><span data-ttu-id="b55ff-122">So stellen Sie das Tabellenmodell für Adventure Works-Internetverkäufe bereit</span><span class="sxs-lookup"><span data-stu-id="b55ff-122">To deploy the Adventure Works Internet Sales tabular model</span></span>  
  
1.  <span data-ttu-id="b55ff-123">Klicken Sie in [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf das Menü **Erstellen** und anschließend auf die **Option zum Bereitstellen des Tabellenmodells für AW-Internetverkäufe**.</span><span class="sxs-lookup"><span data-stu-id="b55ff-123">In [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], click the **Build** menu, and then click **Deploy AW Internet Sales Tabular Model**.</span></span>  
  
     <span data-ttu-id="b55ff-124">Das Dialogfeld für die Bereitstellung öffnet sich und zeigt den Bereitstellungsstatus der Metadaten sowie jede im Modell enthaltene Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="b55ff-124">The Deploy dialog box appears and displays the deployment status of the metadata as well as each table included in the model.</span></span>  
  
## <a name="conclusion"></a><span data-ttu-id="b55ff-125">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="b55ff-125">Conclusion</span></span>  
 <span data-ttu-id="b55ff-126">Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="b55ff-126">Congratulations!</span></span> <span data-ttu-id="b55ff-127">Sie haben die Erstellung und Bereitstellung des ersten Analysis Services-Tabellenmodells abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="b55ff-127">You are finished authoring and deploying your first Analysis Services tabular model.</span></span> <span data-ttu-id="b55ff-128">Mit diesem Lernprogramm wurden Sie durch die häufigsten Aufgaben zur Erstellung eines Tabellenmodells geführt.</span><span class="sxs-lookup"><span data-stu-id="b55ff-128">This tutorial has helped guide you through completing the most common tasks in creating a tabular model.</span></span> <span data-ttu-id="b55ff-129">Nach der Bereitstellung des Adventure Works-Internetverkaufsmodells können Sie nun mit SQL Server Management Studio das Modell verwalten und Prozessskripts sowie einen Sicherungsplan erstellen.</span><span class="sxs-lookup"><span data-stu-id="b55ff-129">Now that your Adventure Works Internet Sales Model is deployed, you can use SQL Server Management Studio to manage the model; create process scripts and a backup plan.</span></span> <span data-ttu-id="b55ff-130">Benutzer können mithilfe einer Clientanwendung zur Berichtserstellung wie Microsoft Excel oder [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)]eine Verbindung zum Modell herstellen.</span><span class="sxs-lookup"><span data-stu-id="b55ff-130">Users can connect to the model using a reporting client application such as Microsoft Excel or [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)].</span></span>  
  
## <a name="additional-resources"></a><span data-ttu-id="b55ff-131">Weitere Ressourcen</span><span class="sxs-lookup"><span data-stu-id="b55ff-131">Additional Resources</span></span>  
 <span data-ttu-id="b55ff-132">Weitere Informationen zu Tabellenmodelleigenschaften, die [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)]-Berichte unterstützen, finden Sie unter [Power View-Berichterstellungseigenschaften &#40;SSAS – tabellarisch&#41;](tabular-models/properties-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="b55ff-132">To learn more about tabular model properties that support [!INCLUDE[ssCrescent](../includes/sscrescent-md.md)] reports, see [Power View Reporting Properties &#40;SSAS Tabular&#41;](tabular-models/properties-ssas-tabular.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b55ff-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b55ff-133">See Also</span></span>  
 <span data-ttu-id="b55ff-134">[Directquery-Modus &#40;tabellarischen SSAS-&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="b55ff-134">[DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span></span>  
 <span data-ttu-id="b55ff-135">[Konfigurieren von Standarddaten Modellierung und Bereitstellungs Eigenschaften &#40;tabellarischen SSAS-&#41;](tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="b55ff-135">[Configure Default Data Modeling and Deployment Properties &#40;SSAS Tabular&#41;](tabular-models/configure-default-data-modeling-and-deployment-properties-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="b55ff-136">Tabellarische Modelldatenbanken &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="b55ff-136">Tabular Model Databases &#40;SSAS Tabular&#41;</span></span>](tabular-models/tabular-model-databases-ssas-tabular.md)  
  
  
