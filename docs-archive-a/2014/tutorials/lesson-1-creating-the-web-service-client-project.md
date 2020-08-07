---
title: 'Lektion 1: Erstellen des Webdienst-Client Projekts | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 0070daa6-56b0-4663-83b2-44c96acafad8
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: eda9413867c4ca6d44a5cf98b82be9bddc04d0f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87719102"
---
# <a name="lesson-1-creating-the-web-service-client-project"></a><span data-ttu-id="403b4-102">Lektion 1: Erstellen des Webdienst-Clientprojekts</span><span class="sxs-lookup"><span data-stu-id="403b4-102">Lesson 1: Creating the Web Service Client Project</span></span>
  <span data-ttu-id="403b4-103">Mithilfe dieser Anleitung werden Sie eine einfache Konsolenanwendung erstellen, die auf den Berichtsserver-Webdienst zugreift.</span><span class="sxs-lookup"><span data-stu-id="403b4-103">For this walkthrough, you will create a simple console application that accesses the Report Server Web service.</span></span> <span data-ttu-id="403b4-104">Im Zusammenhang mit dieser Anleitung wird davon ausgegangen, dass Sie in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] entwickeln.</span><span class="sxs-lookup"><span data-stu-id="403b4-104">This walkthrough assumes you are developing in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
### <a name="to-create-a-console-application"></a><span data-ttu-id="403b4-105">So erstellen Sie eine Konsolenanwendung</span><span class="sxs-lookup"><span data-stu-id="403b4-105">To create a console application</span></span>  
  
1.  <span data-ttu-id="403b4-106">Zeigen Sie im Menü **Datei** auf **neu**, und klicken Sie dann auf **Projekt** , um das Dialogfeld **Neues Projekt** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="403b4-106">On the **File** menu, point to **New**, and then click **Project** to open the **New Project** dialog box.</span></span>  
  
2.  <span data-ttu-id="403b4-107">Klicken Sie im linken Bereich unter **installierte Vorlagen**entweder auf **Visual Basic** oder den **Visual c#** -Knoten, und wählen Sie eine Kategorie von Projekttypen aus der erweiterten Liste aus.</span><span class="sxs-lookup"><span data-stu-id="403b4-107">In the left pane, under **Installed Templates**, click either **Visual Basic** or the **Visual C#** node, and select a category of project types from the expanded list.</span></span>  
  
3.  <span data-ttu-id="403b4-108">Wählen Sie den Projekttyp **Konsolenanwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="403b4-108">Choose the **Console Application** project type.</span></span>  
  
4.  <span data-ttu-id="403b4-109">Geben Sie im Feld **Name** einen Namen für das Projekt ein.</span><span class="sxs-lookup"><span data-stu-id="403b4-109">In the **Name** box, enter a name for your project.</span></span> <span data-ttu-id="403b4-110">Geben Sie den Namen ein `GetPropertiesSample` .</span><span class="sxs-lookup"><span data-stu-id="403b4-110">Type the name `GetPropertiesSample`.</span></span>  
  
5.  <span data-ttu-id="403b4-111">Geben Sie im Feld **Speicherort** den Pfad ein, in dem Sie das Projekt speichern möchten, oder klicken Sie auf **Durchsuchen** , um zum Ordner zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="403b4-111">In the **Location** box, enter the path where you want to save your project, or click **Browse** to navigate to the folder.</span></span>  
  
6.  [!INCLUDE[clickOK](../includes/clickok-md.md)]<span data-ttu-id="403b4-112">Eine reduzierte Ansicht des Projekts wird in Projektmappen-Explorer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="403b4-112">A collapsed view of your project appears in Solution Explorer.</span></span>  
  
     <span data-ttu-id="403b4-113">Erweitern Sie den Projektknoten im Projektmappen-Explorer.</span><span class="sxs-lookup"><span data-stu-id="403b4-113">In Solution Explorer, expand the project node.</span></span> <span data-ttu-id="403b4-114">Dem Projekt wurde eine Datei mit dem Standardnamen Program.cs (Module1. vb für [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="403b4-114">A file with the default name of Program.cs (Module1.vb for [!INCLUDE[msCoName](../includes/msconame-md.md)] [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) has been added to your project.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="403b4-115">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="403b4-115">See Also</span></span>  
 <span data-ttu-id="403b4-116">[Lektion 2: Hinzufügen eines Webverweises](../../2014/tutorials/lesson-2-adding-a-web-reference.md) </span><span class="sxs-lookup"><span data-stu-id="403b4-116">[Lesson 2: Adding a Web Reference](../../2014/tutorials/lesson-2-adding-a-web-reference.md) </span></span>  
 [<span data-ttu-id="403b4-117">Zugreifen auf den Report Server-Webdienst mithilfe von Visual Basic oder Visual C&#35; &#40;SSRS-Tutorial&#41;</span><span class="sxs-lookup"><span data-stu-id="403b4-117">Accessing the Report Server Web Service Using Visual Basic or Visual C&#35; &#40;SSRS Tutorial&#41;</span></span>](../../2014/tutorials/access-report-server-web-service-vb-vcsharp-ssrs-tutorial.md)  
  
  
