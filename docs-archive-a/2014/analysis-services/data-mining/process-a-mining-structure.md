---
title: Verarbeiten einer Mining Struktur | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- mining structures [Analysis Services], processing
ms.assetid: 4162f33e-c23f-4293-8905-271781e45fa4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76d25a927ae61ee5ffadf4ca21073a1c04cdb542
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718958"
---
# <a name="process-a-mining-structure"></a><span data-ttu-id="9481e-102">Verarbeiten einer Miningstruktur</span><span class="sxs-lookup"><span data-stu-id="9481e-102">Process a Mining Structure</span></span>
  <span data-ttu-id="9481e-103">Bevor Sie die einer Miningstruktur zugeordneten Miningmodelle durchsuchen und verwenden können, müssen Sie das [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt bereitstellen und die Miningstruktur und die Miningmodelle verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="9481e-103">Before you can browse or work with the mining models that are associated with a mining structure, you have to deploy the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project and process the mining structure and mining models.</span></span> <span data-ttu-id="9481e-104">Wenn Sie eine Änderung an der Miningstruktur oder den Miningmodellen vornehmen, werden Sie zur erneuten Bereitstellung und Verarbeitung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="9481e-104">Also, if you make a change to the mining structure or mining models, you will be prompted to redeploy and process them.</span></span> <span data-ttu-id="9481e-105">Beim Verarbeiten der Struktur auf der Registerkarte **Miningstruktur** des Data Mining-Designers von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] werden auch alle zugeordneten Modelle verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="9481e-105">Processing the structure in the **Mining Structure** tab of Data Mining Designer in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] processes all the associated models.</span></span>  
  
 <span data-ttu-id="9481e-106">Sie können eine Miningstruktur mit den folgenden Tools verarbeiten:</span><span class="sxs-lookup"><span data-stu-id="9481e-106">You can process a mining structure by using these tools:</span></span>  
  
-   [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]  
  
-   [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)]  
  
-   <span data-ttu-id="9481e-107">XMLA: Process-Befehl</span><span class="sxs-lookup"><span data-stu-id="9481e-107">XMLA: Process command</span></span>  
  
 <span data-ttu-id="9481e-108">Informationen zum Verarbeiten einzelner Modelle finden Sie unter [Verarbeiten eines Miningmodells](process-a-mining-model.md).</span><span class="sxs-lookup"><span data-stu-id="9481e-108">For information about how to process individual models, see [Process a Mining Model](process-a-mining-model.md).</span></span>  
  
### <a name="to-process-a-mining-structure-and-all-associated-mining-models-using-sql-server-data-tools"></a><span data-ttu-id="9481e-109">So verarbeiten Sie eine Miningstruktur und alle zugeordneten Miningmodelle mit SQL Server-Datentools</span><span class="sxs-lookup"><span data-stu-id="9481e-109">To process a mining structure and all associated mining models using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="9481e-110">Wählen Sie in **im Menüelement** Miningmodell **die Option** Miningstruktur und alle Modelle verarbeiten [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]aus.</span><span class="sxs-lookup"><span data-stu-id="9481e-110">Select **Process Mining Structure and All Models** from the **Mining Model** menu item in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span>  
  
     <span data-ttu-id="9481e-111">Wenn Sie Änderungen an der Struktur vorgenommen haben, werden Sie aufgefordert, die Struktur erneut bereitzustellen, bevor die Modelle verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="9481e-111">If you made changes to the structure, you will be prompted to redeploy the structure before processing the models.</span></span> <span data-ttu-id="9481e-112">Klicken Sie auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="9481e-112">Click **Yes**.</span></span>  
  
2.  <span data-ttu-id="9481e-113">Klicken Sie im Dialogfeld **Mining Struktur verarbeiten \<structure> -** auf **Ausführen** .</span><span class="sxs-lookup"><span data-stu-id="9481e-113">Click **Run** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
     <span data-ttu-id="9481e-114">Das Dialogfeld **Verarbeitungsstatus** wird geöffnet und zeigt detaillierte Informationen zur Verarbeitung des Modells an.</span><span class="sxs-lookup"><span data-stu-id="9481e-114">The **Process Progress** dialog box opens to display the details of model processing.</span></span>  
  
3.  <span data-ttu-id="9481e-115">Klicken Sie nach Abschluss der Modellverarbeitung im Dialogfeld **Verarbeitungsstatus** auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="9481e-115">Click **Close** in the **Process Progress** dialog box after the models have completed processing.</span></span>  
  
4.  <span data-ttu-id="9481e-116">Klicken Sie im Dialogfeld **Mining Struktur verarbeiten \<structure> -** auf **Schließen** .</span><span class="sxs-lookup"><span data-stu-id="9481e-116">Click **Close** in the **Processing Mining Structure - \<structure>** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9481e-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9481e-117">See Also</span></span>  
 [<span data-ttu-id="9481e-118">Tasks und Anweisungen für Miningstrukturen</span><span class="sxs-lookup"><span data-stu-id="9481e-118">Mining Structure Tasks and How-tos</span></span>](mining-structure-tasks-and-how-tos.md)  
  
  
