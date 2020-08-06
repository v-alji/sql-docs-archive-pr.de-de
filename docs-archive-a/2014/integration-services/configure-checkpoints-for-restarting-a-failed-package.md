---
title: Konfigurieren von Prüfpunkten zum erneuten Starten eines fehlerhaften Pakets | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- checkpoints [Integration Services]
- restarting packages
- starting packages
ms.assetid: 9afffa5a-d803-4653-8afc-386453fc163f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a85354377453e0b24692ab8c2b567cc8998b6b05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721670"
---
# <a name="configure-checkpoints-for-restarting-a-failed-package"></a><span data-ttu-id="2bc57-102">Konfigurieren von Prüfpunkten zum erneuten Starten eines fehlerhaften Pakets</span><span class="sxs-lookup"><span data-stu-id="2bc57-102">Configure Checkpoints for Restarting a Failed Package</span></span>
  <span data-ttu-id="2bc57-103">Sie können ein [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket so konfigurieren, dass nicht das gesamte Paket erneut ausgeführt wird, sondern ab dem Punkt, an dem ein Fehler auftrat. Hierzu legen Sie die Eigenschaften fest, die für Prüfpunkte gelten.</span><span class="sxs-lookup"><span data-stu-id="2bc57-103">You configure [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages to restart from a point of failure, instead of rerunning the entire package, by setting the properties that apply to checkpoints.</span></span>  
  
### <a name="to-configure-a-package-to-restart"></a><span data-ttu-id="2bc57-104">So konfigurieren Sie den Neustart eines Pakets</span><span class="sxs-lookup"><span data-stu-id="2bc57-104">To configure a package to restart</span></span>  
  
1.  <span data-ttu-id="2bc57-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekt mit dem Paket, das Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2bc57-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project that contains the package you want to configure.</span></span>  
  
2.  <span data-ttu-id="2bc57-106">Doppelklicken Sie im **Projektmappen-Explorer**auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2bc57-106">In **Solution Explorer**, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="2bc57-107">Klicken Sie auf die Registerkarte **Ablaufsteuerung** .</span><span class="sxs-lookup"><span data-stu-id="2bc57-107">Click the **Control Flow** tab.</span></span>  
  
4.  <span data-ttu-id="2bc57-108">Klicken Sie mit der rechten Maustaste an einer beliebigen Stelle im Hintergrund der Entwurfsoberfläche der Ablaufsteuerung, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2bc57-108">Right-click anywhere in the background of the control flow design surface, and then click **Properties**.</span></span>  
  
5.  <span data-ttu-id="2bc57-109">Legen Sie die SaveCheckpoints-Eigenschaft auf fest `True` .</span><span class="sxs-lookup"><span data-stu-id="2bc57-109">Set the SaveCheckpoints property to `True`.</span></span>  
  
6.  <span data-ttu-id="2bc57-110">Geben Sie den Namen der Prüfpunktdatei in die CheckpointFileName-Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="2bc57-110">Type the name of the checkpoint file in the CheckpointFileName property.</span></span>  
  
7.  <span data-ttu-id="2bc57-111">Legen Sie die CheckpointUsage-Eigenschaft auf einen der beiden Werte fest:</span><span class="sxs-lookup"><span data-stu-id="2bc57-111">Set the CheckpointUsage property to one of two values:</span></span>  
  
    -   <span data-ttu-id="2bc57-112">Wählen Sie `Always` aus, damit das Paket immer am Prüfpunkt neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="2bc57-112">Select `Always` to always restart the package from the checkpoint.</span></span>  
  
        > [!IMPORTANT]  
        >  <span data-ttu-id="2bc57-113">Falls die Prüfpunktdatei nicht verfügbar ist, tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="2bc57-113">An error occurs if the checkpoint file is not available.</span></span>  
  
    -   <span data-ttu-id="2bc57-114">Wählen Sie `IfExists` aus, damit das Paket nur neu gestartet wird, wenn die Prüfpunktdatei verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="2bc57-114">Select `IfExists` to restart the package only if the checkpoint file is available.</span></span>  
  
8.  <span data-ttu-id="2bc57-115">Konfigurieren Sie die Tasks und Container, von denen das Paket neu gestartet werden kann.</span><span class="sxs-lookup"><span data-stu-id="2bc57-115">Configure the tasks and containers from which the package can restart.</span></span>  
  
    -   <span data-ttu-id="2bc57-116">Klicken Sie mit der rechten Maustaste auf einen Task oder Container, und klicken Sie anschließend auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="2bc57-116">Right-click a task or container and click **Properties**.</span></span>  
  
    -   <span data-ttu-id="2bc57-117">Legen Sie die FailPackageOnFailure `True` -Eigenschaft für jeden ausgewählten Task und Container auf fest.</span><span class="sxs-lookup"><span data-stu-id="2bc57-117">Set the FailPackageOnFailure property to `True` for each selected task and container.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2bc57-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2bc57-118">See Also</span></span>  
 [<span data-ttu-id="2bc57-119">Neustarten von Paketen mit Prüfpunkten</span><span class="sxs-lookup"><span data-stu-id="2bc57-119">Restart Packages by Using Checkpoints</span></span>](packages/restart-packages-by-using-checkpoints.md)  
  
  
