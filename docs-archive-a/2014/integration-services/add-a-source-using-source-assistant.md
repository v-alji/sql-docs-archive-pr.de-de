---
title: Hinzufügen einer Quelle mit dem Quellen-Assistenten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5e850b7c-4b89-42ad-b0a6-d63ac7cc9568
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 1b58b10508765580e0cffe9bd62099f3e2d69863
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617261"
---
# <a name="add-a-source-using-source-assistant"></a><span data-ttu-id="9c819-102">Hinzufügen einer Quelle mit dem Quellen-Assistenten</span><span class="sxs-lookup"><span data-stu-id="9c819-102">Add a Source using Source Assistant</span></span>
  <span data-ttu-id="9c819-103">Dieses Thema gibt Schritte an, um eine neue Quelle mithilfe des Quellen-Assistenten hinzuzufügen, und führt die im Dialogfeld **Neue Quelle hinzufügen** verfügbaren Optionen auf, die angezeigt werden, wenn Sie den Quellen-Assistent per Drag &amp; Drop in den SSIS-Designer ziehen.</span><span class="sxs-lookup"><span data-stu-id="9c819-103">This topic provides steps to add a new source using the Source Assistant and also lists the options that are available on the **Add New Source** dialog, which you will see when you drag-drop the Source Assistant to the SSIS Designer.</span></span>  
  
### <a name="to-use-source-assistant-to-add-a-source"></a><span data-ttu-id="9c819-104">So verwenden Sie den Quellen-Assistenten, um eine Quelle hinzuzufügen</span><span class="sxs-lookup"><span data-stu-id="9c819-104">To use Source Assistant to add a source</span></span>  
  
1.  <span data-ttu-id="9c819-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]das [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Paket, dem eine neue Quellkomponente hinzugefügt werden soll.</span><span class="sxs-lookup"><span data-stu-id="9c819-105">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package that you want to add a source component to.</span></span>  
  
2.  <span data-ttu-id="9c819-106">Ziehen Sie die **Quellen-Assistenten** -Komponente von der SSIS-Toolbox auf die Registerkarte **Datenfluss** . Sie sollten das Dialogfeld **Neue Quelle hinzufügen** sehen.</span><span class="sxs-lookup"><span data-stu-id="9c819-106">Drag the **Source Assistant** component from the SSIS Toolbox to the **Data Flow** tab. You should see the **Add New Source** dialog box.</span></span> <span data-ttu-id="9c819-107">Der nächste Abschnitt enthält Details zu den im Dialogfeld verfügbaren Optionen.</span><span class="sxs-lookup"><span data-stu-id="9c819-107">The next section provides you details about the options available in the dialog box.</span></span>  
  
3.  <span data-ttu-id="9c819-108">Wählen Sie den Zieltyp in der Liste **Typ** aus.</span><span class="sxs-lookup"><span data-stu-id="9c819-108">Select the type of the destination in the **Types** list.</span></span>  
  
4.  <span data-ttu-id="9c819-109">Wählen Sie in der Liste **Verbindungs-Manager** einen vorhandenen Verbindungs-Manager aus. Wählen Sie alternativ **\<New>** aus, um einen neuen Verbindungs-Manager zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9c819-109">Select an existing connection manager in the **Connection Managers** list or select **\<New>** to create a new connection manager.</span></span>  
  
5.  <span data-ttu-id="9c819-110">Wenn Sie einen vorhandenen Verbindungs-Manager auswählen, klicken Sie auf **OK** , um das Dialogfeld **Neues Ziel hinzufügen** zu schließen.</span><span class="sxs-lookup"><span data-stu-id="9c819-110">If you select an existing connection manager, click **OK** to close the **Add New Destination** dialog box.</span></span> <span data-ttu-id="9c819-111">Sie sollten nun das Ziel und die Verbindungs-Manager sehen, die dem Datenfluss hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="9c819-111">You should see the destination and connection managers added to the data flow.</span></span>  
  
6.  <span data-ttu-id="9c819-112">Wenn Sie auf **\<New>** klicken, um einen neuen Verbindungs-Manager zu erstellen, sollten Sie ein **Verbindungs-Manager**-Dialogfeld sehen, in dem Sie Parameter für die Verbindung angeben können.</span><span class="sxs-lookup"><span data-stu-id="9c819-112">If you click **\<New>** to create a new connection manager, you should see a **Connection Manager** dialog box, which lets you specify parameters for the connection.</span></span> <span data-ttu-id="9c819-113">Nachdem Sie einen neuen Verbindungs-Managers erstellt haben, werden das Ziel und der Verbindungs-Manager in SSIS-Designer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="9c819-113">After you are done with creating the new connection manager, you will see the destination and the connection manager in SSIS Designer.</span></span>  
  
  
