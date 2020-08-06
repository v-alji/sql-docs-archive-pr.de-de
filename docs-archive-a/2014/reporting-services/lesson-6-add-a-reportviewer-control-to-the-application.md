---
title: 'Lektion 6: Hinzufügen eines ReportViewer-Steuerelements zur Anwendung | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: f9492a97-5609-4059-ae76-0fba111d4968
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: bb04008fa47801f0500de711592a3cec45ca3dd6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621877"
---
# <a name="lesson-6-add-a-reportviewer-control-to-the-application"></a><span data-ttu-id="885c0-102">Lektion 6: Hinzufügen eines ReportViewer-Steuerelements zur Anwendung</span><span class="sxs-lookup"><span data-stu-id="885c0-102">Lesson 6: Add a ReportViewer Control to the Application</span></span>
  <span data-ttu-id="885c0-103">Nachdem Sie den untergeordneten Bericht mit dem Berichts-Assistenten entworfen haben, fügen Sie der Websiteanwendung im nächsten Schritt ein ReportViewer-Steuerelement hinzu.</span><span class="sxs-lookup"><span data-stu-id="885c0-103">After you design the child report by using the Report Wizard, your next step is to add a ReportViewer control to the website application.</span></span>  
  
### <a name="to-add-a-reportviewer-control-to-the-application"></a><span data-ttu-id="885c0-104">So fügen Sie der Anwendung das ReportViewer-Steuerelement hinzu</span><span class="sxs-lookup"><span data-stu-id="885c0-104">To add a ReportViewer control to the application</span></span>  
  
1.  <span data-ttu-id="885c0-105">Klicken Sie im **Projektmappen-Explorer**mit der rechten Maustaste auf **Default.aspx**, und klicken Sie auf **Sicht-Designer**.</span><span class="sxs-lookup"><span data-stu-id="885c0-105">In **Solution Explorer**, right-click **Default.aspx**, and then click **View Designer**.</span></span>  
  
2.  <span data-ttu-id="885c0-106">Ziehen Sie ein **ScriptManager** -Steuerelement aus der Gruppe **AJAX-Erweiterungen** im Fenster **Toolbox** auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="885c0-106">From the **AJAX Extensions** group in the **Toolbox** window, drag a **ScriptManager** control to the design surface.</span></span>  
  
3.  <span data-ttu-id="885c0-107">Ziehen Sie ein **ReportViewer** -Steuerelement aus der Gruppe **Berichterstellung** unterhalb des **ScriptManager** -Steuerelements auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="885c0-107">From the **Reporting** group, drag a **ReportViewer** control to the design surface below the **ScriptManager** control.</span></span>  
  
4.  <span data-ttu-id="885c0-108">Öffnen Sie das Fenster **ReportViewer-Aufgaben** , indem Sie auf den Pfeil in der oberen rechten Ecke des **ReportViewer** -Steuerelements klicken.</span><span class="sxs-lookup"><span data-stu-id="885c0-108">Open the **ReportViewer Tasks** window by clicking the arrow in the top right-hand corner of the **ReportViewer** control.</span></span>  
  
5.  <span data-ttu-id="885c0-109">Wählen Sie im Feld **Bericht auswählen** den erstellten übergeordneten Bericht aus.</span><span class="sxs-lookup"><span data-stu-id="885c0-109">In the **Choose Report** box, select Parent report you created.</span></span>  
  
     <span data-ttu-id="885c0-110">Nachdem Sie einen Bericht ausgewählt haben, werden automatisch Instanzen der im Bericht verwendeten Datenquellen erstellt.</span><span class="sxs-lookup"><span data-stu-id="885c0-110">When you select a report, instances of data sources used in the report are created automatically.</span></span> <span data-ttu-id="885c0-111">Der Code wird generiert, um jede DataTable (und den zugehörigen [DataSet](https://msdn.microsoft.com/library/system.data.dataset\(v=vs.100\).aspx) -Container) zu instanziieren.</span><span class="sxs-lookup"><span data-stu-id="885c0-111">Code is generated to instantiate each DataTable (and its [DataSet](https://msdn.microsoft.com/library/system.data.dataset\(v=vs.100\).aspx) container).</span></span> <span data-ttu-id="885c0-112">Gemäß den einzelnen, im Bericht verwendeten Datenquellen wird der Entwurfsoberfläche ein [ObjectDataSource](https://msdn.microsoft.com/library/system.web.ui.webcontrols.objectdatasource\(v=vs.100\).aspx) -Steuerelement hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="885c0-112">An [ObjectDataSource](https://msdn.microsoft.com/library/system.web.ui.webcontrols.objectdatasource\(v=vs.100\).aspx) control is added to the design surface, corresponding to each data source used in the report.</span></span> <span data-ttu-id="885c0-113">Dieses Datenquellen-Steuerelement wird automatisch konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="885c0-113">This data source control is configured automatically.</span></span>  
  
     <span data-ttu-id="885c0-114">Wenn Sie Microsoft Visual Studio 2012 verwenden, stellen Sie sicher, dass das ObjectDataSource-Steuerelement an dataSet1 gebunden ist, das mit dem Project-Namespace voll qualifiziert ist, wenn der voll qualifizierte Name im Dropdown-Listenfeld **Wählen Sie Ihr Geschäftsobjekt** (z. b. projectnamespace. DataSet1TableAdapters. ProductTableAdapter) aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="885c0-114">If you're using Microsoft Visual Studio 2012, make sure that the ObjectDataSource control is bound with DataSet1 that is fully qualified with the project namespace, if the fully qualified name is listed in the **Choose your business object** drop-down list box (for example, Projectnamespace.DataSet1TableAdapters.ProductTableAdapter).</span></span> <span data-ttu-id="885c0-115">Um auf das Listenfeld zuzugreifen, klicken Sie mit der rechten Maustaste auf ObjectDataSource, und klicken Sie dann auf **Datenquelle konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="885c0-115">You access the list box by right-clicking ObjectDataSource, and then clicking **Configure Data Source**.</span></span>  
  
6.  <span data-ttu-id="885c0-116">Klicken Sie im Menü Erstellen auf Website erstellen.</span><span class="sxs-lookup"><span data-stu-id="885c0-116">On the Build menu, click Build website.</span></span>  
  
     <span data-ttu-id="885c0-117">Der Bericht wird kompiliert und alle Fehler, z. B. Syntaxfehler in einem Berichtsausdruck, werden im Bereich **Fehlerliste** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="885c0-117">The report is compiled and any errors such as a syntax error in a report expression appear in the **Error List** area.</span></span> <span data-ttu-id="885c0-118">Klicken Sie unten im Visual Studio-Fenster auf **Fehlerliste** , um den Bereich **Fehlerliste** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="885c0-118">Click **Error List** at the bottom of the Visual Studio window to display the **Error List** area.</span></span>  
  
## <a name="next-task"></a><span data-ttu-id="885c0-119">Nächste Aufgabe</span><span class="sxs-lookup"><span data-stu-id="885c0-119">Next Task</span></span>  
 <span data-ttu-id="885c0-120">Sie haben der Websiteanwendung erfolgreich ein ReportViewer-Steuerelement hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="885c0-120">You have successfully added a ReportViewer control to the website application.</span></span> <span data-ttu-id="885c0-121">Als Nächstes fügen Sie dem übergeordneten Bericht eine Drillthroughaktion hinzu.</span><span class="sxs-lookup"><span data-stu-id="885c0-121">Next, you will add a drillthrough action on the parent report.</span></span>  
  
  
