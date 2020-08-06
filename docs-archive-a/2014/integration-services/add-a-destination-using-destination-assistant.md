---
title: Hinzufügen eines Ziels mit dem Ziel-Assistenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 747a0de0-3c2f-4d31-a692-7111fc0911d8
author: chugugrace
ms.author: chugu
ms.openlocfilehash: cd36828a7bab7fb33b86765f9f064b6406a17a9a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610021"
---
# <a name="add-a-destination-using-destination-assistant"></a><span data-ttu-id="ff095-102">Hinzufügen eines Ziels mit dem Ziel-Assistenten</span><span class="sxs-lookup"><span data-stu-id="ff095-102">Add a Destination using Destination Assistant</span></span>
  <span data-ttu-id="ff095-103">In diesem Thema werden die Schritte beschrieben, um ein neues Ziel mithilfe des Ziel-Assistenten hinzuzufügen. Darüber hinaus werden die im Dialogfeld **Neues Ziel hinzufügen** verfügbaren Optionen aufgelistet, die angezeigt werden, wenn Sie den Ziel-Assistent per Drag &amp; Drop in den SSIS-Designer ziehen.</span><span class="sxs-lookup"><span data-stu-id="ff095-103">This topic provides steps to add a new destination using the Destination Assistant and also lists the options that are available on the **Add New Destination** dialog, which you will see when you drag-drop the Destination Assistant to the SSIS Designer.</span></span>  
  
### <a name="to-use-destination-assistant-to-add-a-destination"></a><span data-ttu-id="ff095-104">So verwenden Sie den Ziel-Assistenten, um ein Ziel hinzuzufügen</span><span class="sxs-lookup"><span data-stu-id="ff095-104">To use Destination Assistant to add a destination</span></span>  
  
1.  <span data-ttu-id="ff095-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket, dem eine neue Zielkomponente hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ff095-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you want to add a destination component to.</span></span>  
  
2.  <span data-ttu-id="ff095-106">Ziehen Sie die **Ziel-Assistenten** -Komponente von der SSIS-Toolbox auf die Registerkarte **Datenfluss** . Sie sollten das Dialogfeld **Neues Ziel hinzufügen** sehen.</span><span class="sxs-lookup"><span data-stu-id="ff095-106">Drag the **Destination Assistant** component from the SSIS Toolbox to the **Data Flow** tab. You should see the **Add New Destination** dialog box.</span></span> <span data-ttu-id="ff095-107">Der nächste Abschnitt enthält Details zu den im Dialogfeld verfügbaren Optionen.</span><span class="sxs-lookup"><span data-stu-id="ff095-107">The next section provides you details about the options available in the dialog box.</span></span>  
  
3.  <span data-ttu-id="ff095-108">Wählen Sie den Zieltyp in der Liste **Typ** aus.</span><span class="sxs-lookup"><span data-stu-id="ff095-108">Select the type of the destination in the **Types** list.</span></span>  
  
4.  <span data-ttu-id="ff095-109">Wählen Sie in der Liste **Verbindungs-Manager** einen vorhandenen Verbindungs-Manager aus. Wählen Sie alternativ **\<New>** aus, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ff095-109">Select an existing connection manager in the **Connection Managers** list or select **\<New>** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="ff095-110">Wenn Sie einen vorhandenen Verbindungs-Manager auswählen, klicken Sie auf **OK** , um das Dialogfeld **Neues Ziel hinzufügen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="ff095-110">If you select an existing connection manager, click **OK** to close the **Add New Destination** dialog box.</span></span> <span data-ttu-id="ff095-111">Sie sollten nun das Ziel und die Verbindungs-Manager sehen, die dem Datenfluss hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="ff095-111">You should see the destination and connection managers added to the data flow.</span></span>  
  
6.  <span data-ttu-id="ff095-112">Wenn Sie auf **\<New>** klicken, um einen neuen Verbindungs-Manager zu erstellen, sollten Sie ein **Verbindungs-Manager**-Dialogfeld sehen, in dem Sie Parameter für die Verbindung angeben können.</span><span class="sxs-lookup"><span data-stu-id="ff095-112">If you click **\<New>** to create a new connection manager, you should see a **Connection Manager** dialog box, which lets you specify parameters for the connection.</span></span> <span data-ttu-id="ff095-113">Nachdem Sie einen neuen Verbindungs-Managers erstellt haben, werden das Ziel und der Verbindungs-Manager in SSIS-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ff095-113">After you are done with creating the new connection manager, you will see the destination and the connection manager in SSIS Designer.</span></span>  
  
  
