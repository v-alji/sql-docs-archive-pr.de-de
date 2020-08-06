---
title: Erstellen eines Cubes mit dem Cube-Assistenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- cubes [Analysis Services], creating
ms.assetid: d46d659c-3a4e-4364-94ac-f5eb6ba0ec25
author: minewiskan
ms.author: owend
ms.openlocfilehash: 441c296c0fd71b2a9c2b8332743da6224839a471
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721961"
---
# <a name="create-a-cube-using-the-cube-wizard"></a><span data-ttu-id="7e2ff-102">Erstellen eines Cubes mit dem Cube-Assistenten</span><span class="sxs-lookup"><span data-stu-id="7e2ff-102">Create a Cube Using the Cube Wizard</span></span>
  <span data-ttu-id="7e2ff-103">Sie können einen neuen Cube erstellen, indem Sie den Cube-Assistenten von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-103">You can create a new cube by using the Cube Wizard in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-create-a-new-cube"></a><span data-ttu-id="7e2ff-104">So erstellen Sie einen neuen Cube</span><span class="sxs-lookup"><span data-stu-id="7e2ff-104">To create a new cube</span></span>  
  
1.  <span data-ttu-id="7e2ff-105">Klicken Sie in **Projektmappen-Explorer**mit der rechten Maustaste auf **Cubes**, und klicken Sie dann auf **Neuer Cube**.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-105">In **Solution Explorer**, right-click **Cubes**, and then click **New Cube**.</span></span>  
  
2.  <span data-ttu-id="7e2ff-106">Wählen Sie auf der Seite **Erstellungsmethode auswählen** des Cube-Assistenten die Option **Vorhandene Tabellen verwenden**aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-106">On the **Select Creation Method** page of the Cube Wizard, select **Use existing tables**, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7e2ff-107">Möglicherweise müssen Sie gelegentlich einen Cube ohne vorhandene Tabellen erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-107">You might occasionally have to create a cube without using existing tables.</span></span> <span data-ttu-id="7e2ff-108">Um einen leeren Cube zu erstellen, wählen Sie **Leeren Cube erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-108">To create an empty cube, select **Create an empty cube**.</span></span> <span data-ttu-id="7e2ff-109">Um Tabellen zu generieren, wählen Sie **Tabellen in der Datenquelle generieren**aus.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-109">To generate tables, select **Generate tables in the data source**.</span></span>  
  
3.  <span data-ttu-id="7e2ff-110">Führen Sie auf der Seite **Measuregruppentabellen auswählen** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="7e2ff-110">On the **Select Measure Group Tables** page, do the following procedures:</span></span>  
  
    1.  <span data-ttu-id="7e2ff-111">Wählen Sie in der Liste **Datenquellensicht** eine Datenquellensicht aus.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-111">In the **Data source view** list, select a data source view.</span></span>  
  
    2.  <span data-ttu-id="7e2ff-112">Wählen Sie in der Liste **Measuregruppentabellen** die Tabellen aus, die verwendet werden, um Measuregruppen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-112">In the **Measure group tables** list, select the tables that will be used to create measure groups.</span></span>  
  
    3.  <span data-ttu-id="7e2ff-113">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-113">Click **Next**.</span></span>  
  
4.  <span data-ttu-id="7e2ff-114">Wählen Sie auf der Seite **Measures auswählen** die Measures aus, die Sie in den Cube einschließen möchten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-114">On the **Select Measures** page, select the measures that you want to include in the cube, and then click **Next**.</span></span>  
  
     <span data-ttu-id="7e2ff-115">Optional können Sie die Namen der Measures und der Measuregruppen ändern.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-115">Optionally, you can change the names of the measures and measure groups.</span></span>  
  
5.  <span data-ttu-id="7e2ff-116">Wählen Sie auf der Seite **Vorhandene Dimensionen auswählen** die vorhandenen Dimensionen aus, die in den Cube eingeschlossen werden sollen, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-116">On the **Select Existing Dimensions** page, select the existing dimensions to include in the cube, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7e2ff-117"> Die Seite **Vorhandene Dimensionen auswählen** wird angezeigt, wenn für eine der ausgewählten Measuregruppe bereits Dimensionen in der Datenbank vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-117">The **Select Existing Dimensions** page appears if dimensions already exist in the database for any of the selected measure groups.</span></span>  
  
6.  <span data-ttu-id="7e2ff-118">Wählen Sie auf der Seite **Neue Dimensionen auswählen** die neuen zu erstellenden Dimensionen aus, und klicken Sie dann **auf Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-118">On the **Select New Dimensions** page, select the new dimensions to create, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7e2ff-119"> Die Seite **Neue Dimensionen auswählen** wird angezeigt, wenn Tabellen geeignete Kandidaten für Dimensionstabellen wären und sie noch nicht von vorhandenen Dimensionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-119">The **Select New Dimensions** page appears if any tables would be good candidates for dimension tables, and the tables have not already been used by existing dimensions.</span></span>  
  
7.  <span data-ttu-id="7e2ff-120">Wählen Sie auf der Seite **Fehlende Dimensionsschlüssel auswählen** einen Schlüssel für die Dimension aus, und klicken Sie dann **auf Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-120">On the **Select Missing Dimension Keys** page, select a key for the dimension, and then click **Next**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7e2ff-121"> Die Seite **Fehlende Dimensionsschlüssel auswählen** wird angezeigt, wenn für die von Ihnen angegebenen Dimensionstabellen kein Schlüssel definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-121">The **Select Missing Dimension Keys** page appears if any of the dimension tables that you specified do not have a key defined.</span></span>  
  
8.  <span data-ttu-id="7e2ff-122">Geben Sie auf der Seite **Assistenten abschließen** einen Namen für den neuen Cube ein, und überprüfen Sie die Cubestruktur.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-122">On the **Completing the Wizard** page, enter a name for the new cube and review the cube structure.</span></span> <span data-ttu-id="7e2ff-123">Wenn Sie Änderungen vornehmen möchten, klicken Sie auf **Zurück**, andernfalls auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-123">If you want to make changes, click **Back**; otherwise, click **Finish**.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7e2ff-124">Sie können den Cube-Designer verwenden, nachdem Sie den Cube-Assistenten vervollständigt haben, um den Cube zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-124">You can use Cube Designer after you complete the Cube Wizard to configure the cube.</span></span> <span data-ttu-id="7e2ff-125">Sie können außerdem den Dimensions-Designer zum Hinzufügen, Entfernen und Konfigurieren von Attributen und Hierarchien in den von Ihnen erstellten Dimensionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="7e2ff-125">You can also use Dimension Designer to add, remove, and configure attributes and hierarchies in the dimensions that you created.</span></span>  
  
  
