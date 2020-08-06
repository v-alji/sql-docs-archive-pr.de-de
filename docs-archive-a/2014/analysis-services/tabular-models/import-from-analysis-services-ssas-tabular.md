---
title: Aus Analysis Services importieren (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: b9a21b23-3a06-4ef8-bc06-9c79cdc54870
author: minewiskan
ms.author: owend
ms.openlocfilehash: 7d6c3d226e46cdb4101bc8db52830046d27b0706
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87696186"
---
# <a name="import-from-analysis-services-ssas-tabular"></a><span data-ttu-id="2f009-102">Importieren aus Analysis Services (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="2f009-102">Import from Analysis Services (SSAS Tabular)</span></span>
  <span data-ttu-id="2f009-103">In diesem Thema wird beschrieben, wie Sie ein neues Projekt für tabellarische Modelle erstellen, indem Sie die Metadaten mithilfe der Projektvorlage Von Server importieren in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]aus einem vorhandenen tabellarischen Modell importieren.</span><span class="sxs-lookup"><span data-stu-id="2f009-103">This topic describes how to create a new tabular model project by importing the metadata from an existing tabular model by using the Import from Server project template in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
## <a name="create-a-new-model-by-importing-metadata-from-an-existing-model-in-analysis-services"></a><span data-ttu-id="2f009-104">Erstellen eines neuen Modells durch Importieren von Metadaten aus einem vorhandenen Modell in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="2f009-104">Create a new model by importing metadata from an existing model in Analysis Services</span></span>  
 <span data-ttu-id="2f009-105">Erstellen Sie mithilfe der Projektvorlage Von Server importieren ein neues tabellarisches Modellprojekt, indem Sie die Metadaten aus einem vorhandenen tabellarischen Modell auf einem Analysis Services-Server kopieren.</span><span class="sxs-lookup"><span data-stu-id="2f009-105">You can use the Import from Server project template to create a new tabular model project by copying the metadata from an existing tabular model on an Analysis Services server.</span></span> <span data-ttu-id="2f009-106">Das neue Projekt wird mit den gleichen Datenquellenverbindungen, Tabellen, Beziehungen, Measures, KPIs, Rollen, Hierarchien, Perspektiven und Partitionen wie das Modell erstellt, aus dem es importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2f009-106">The new project will be created with the same data source connections, tables, relationships, measures, KPIs, roles, hierarchies, perspectives, and partitions as the model it was imported from.</span></span> <span data-ttu-id="2f009-107">Die Daten werden jedoch nicht aus dem vorhandenen Modell in den Arbeitsbereich des neuen Modells kopiert.</span><span class="sxs-lookup"><span data-stu-id="2f009-107">The data, however, is not copied from the existing model to the new model workspace.</span></span> <span data-ttu-id="2f009-108">Sobald der Importvorgang abgeschlossen und das neue Modellprojekt erstellt wurde, müssen Sie Alles verarbeiten (Alles aktualisieren) ausführen, um die Daten aus den Datenquellen in die Arbeitsbereichsdatenbank des neuen Modellprojekts zu laden.</span><span class="sxs-lookup"><span data-stu-id="2f009-108">Once the import process has completed, and the new model project created, you must run a Process All to load the data from the data sources into the new model project workspace database.</span></span>  
  
#### <a name="to-create-a-new-model-by-importing-metadata-from-an-existing-model"></a><span data-ttu-id="2f009-109">So erstellen Sie ein neues Modell durch Importieren von Metadaten aus einem vorhandenen Modell</span><span class="sxs-lookup"><span data-stu-id="2f009-109">To create a new model by importing metadata from an existing model</span></span>  
  
1.  <span data-ttu-id="2f009-110">Klicken Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]auf das Menü **Datei** , auf **Neu**und dann auf **Projekt**.</span><span class="sxs-lookup"><span data-stu-id="2f009-110">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], on the **File** menu, click **New**, and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="2f009-111">Klicken Sie im Dialogfeld **Neues Projekt** unter **Installierte Vorlagen**auf **Business Intelligence**und dann auf **Von Server importieren**.</span><span class="sxs-lookup"><span data-stu-id="2f009-111">In the **New Project** dialog box, under **Installed Templates**, click **Business Intelligence**, and then click **Import from Server**.</span></span>  
  
3.  <span data-ttu-id="2f009-112">Geben Sie unter **Name**einen Namen für das Projekt ein, geben Sie dann einen Speicherort und einen Projektmappennamen an, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f009-112">In **Name**, type a name for the project, then specify a location and solution name, and then click **OK**.</span></span>  
  
4.  <span data-ttu-id="2f009-113">Geben Sie im Dialogfeld **Aus Analysis Services importieren** im Feld **Servername**den Namen des Analysis Services-Servers ein, auf dem sich die zu importierenden Modellmetadaten befinden.</span><span class="sxs-lookup"><span data-stu-id="2f009-113">In the **Import from Analysis Services** dialog box, in **Server Name**, specify the name of the Analysis Services server that contains the model metadata you want to import.</span></span>  
  
5.  <span data-ttu-id="2f009-114">Wählen Sie im Feld **Datenbankname**die Datenbank für das tabellarische Modell aus, die die Modellmetadaten enthält, die Sie importieren möchten, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2f009-114">In **Database Name**, select the tabular model database that contains the model metadata you want to import, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f009-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2f009-115">See Also</span></span>  
 [<span data-ttu-id="2f009-116">Projekteigenschaften &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="2f009-116">Project Properties &#40;SSAS Tabular&#41;</span></span>](properties-ssas-tabular.md)  
  
  
