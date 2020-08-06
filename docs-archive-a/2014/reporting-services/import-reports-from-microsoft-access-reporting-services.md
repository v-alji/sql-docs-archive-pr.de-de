---
title: Importieren von Berichten aus Microsoft Access (Reporting Services) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- Access reports [Reporting Services]
- importing reports
ms.assetid: 4f29d5b8-b77d-4714-a84a-05523df55646
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 862d8b90f3c91dffda35971677db7fdc231c1b63
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620752"
---
# <a name="import-reports-from-microsoft-access-reporting-services"></a><span data-ttu-id="14a44-102">Importieren von Berichten aus Microsoft Access (Reporting Services)</span><span class="sxs-lookup"><span data-stu-id="14a44-102">Import Reports from Microsoft Access (Reporting Services)</span></span>
  <span data-ttu-id="14a44-103">In Berichts-Designer können Sie Berichte aus einer Access- [!INCLUDE[msCoName](../includes/msconame-md.md)] Datenbank oder einem-Projekt importieren.</span><span class="sxs-lookup"><span data-stu-id="14a44-103">In Report Designer, you can import reports from a [!INCLUDE[msCoName](../includes/msconame-md.md)] Access database or project.</span></span> <span data-ttu-id="14a44-104">Hierfür muss Access 2002 oder höher auf dem Computer, auf dem der Berichts-Designer installiert ist, installiert sein.</span><span class="sxs-lookup"><span data-stu-id="14a44-104">Access 2002 or a later version must be installed on the same computer on which Report Designer is installed.</span></span>  
  
 <span data-ttu-id="14a44-105">Bei Verwendung der Importfunktion werden alle Berichte in der Datenbank- oder Projektdatei importiert.</span><span class="sxs-lookup"><span data-stu-id="14a44-105">When you use the import feature, all reports in the database or project file are imported.</span></span> <span data-ttu-id="14a44-106">Enthält die Access-Datei zahlreiche Berichte, ist es möglicherweise sinnvoll, ein separates Berichtsprojekt zum Importieren der Berichte zu erstellen und dann die einzelnen RDL-Dateien im Hauptberichtsprojekt zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="14a44-106">If your Access file contains many reports, you may want to create a separate report project into which to import the reports, and then open the individual RDL files in your main report project.</span></span> <span data-ttu-id="14a44-107">Sie können die Berichte nach dem Import in den Berichts-Designer bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="14a44-107">You can edit the reports after they are imported into Report Designer.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRSnoversion](../includes/ssrsnoversion-md.md)] <span data-ttu-id="14a44-108">unterstützt nicht alle Access-Berichtsobjekte.</span><span class="sxs-lookup"><span data-stu-id="14a44-108">does not support all Access report objects.</span></span> <span data-ttu-id="14a44-109">Elemente, die nicht konvertiert werden, werden im Fenster **Aufgabenliste** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="14a44-109">Items that are not converted are displayed in the **Task List** window.</span></span> <span data-ttu-id="14a44-110">Weitere Informationen finden Sie [unter Supported Access Report Features &#40;SSRS&#41;](../../2014/reporting-services/supported-access-report-features-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="14a44-110">For more information, see [Supported Access Report Features &#40;SSRS&#41;](../../2014/reporting-services/supported-access-report-features-ssrs.md).</span></span>  
  
### <a name="to-import-reports-from-microsoft-access"></a><span data-ttu-id="14a44-111">So importieren Sie Berichte aus Microsoft Access</span><span class="sxs-lookup"><span data-stu-id="14a44-111">To import reports from Microsoft Access</span></span>  
  
1.  <span data-ttu-id="14a44-112">Öffnen oder erstellen Sie ein Projekt, in das Sie die Berichte importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="14a44-112">Open or create a project into which to import the reports.</span></span>  
  
2.  <span data-ttu-id="14a44-113">Zeigen Sie im Menü **Projekt** auf **Berichte importieren**, und klicken Sie dann auf **Microsoft Access**.</span><span class="sxs-lookup"><span data-stu-id="14a44-113">On the **Project** menu, point to **Import Reports**, and then click **Microsoft Access**.</span></span> <span data-ttu-id="14a44-114">Alternativ klicken Sie in Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, zeigen Sie auf **Berichte importieren**, und klicken Sie dann auf **Microsoft Access**.</span><span class="sxs-lookup"><span data-stu-id="14a44-114">Alternatively, right-click the project in Solution Explorer, point to **Import Reports**, and then click **Microsoft Access**.</span></span>  
  
3.  <span data-ttu-id="14a44-115">Wählen Sie im Dialogfeld **Öffnen** die Access-Datenbank (. mdb,. accdb) oder das Projekt (. ADP) aus, die die Berichte enthält, und klicken Sie dann auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="14a44-115">In the **Open** dialog box, select the Access database (.mdb, .accdb) or project (.adp) that contains the reports, and then click **Open**.</span></span> <span data-ttu-id="14a44-116">Es werden alle Berichte aus der Datenbank- oder Projektdatei importiert und im Berichtsordner im Projektmappen-Explorer aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="14a44-116">All the reports in the database or project file are imported and listed in the Reports folder in Solution Explorer.</span></span>  
  
4.  <span data-ttu-id="14a44-117">Überprüfen Sie das **Aufgabenliste** Fenster auf Buildfehler.</span><span class="sxs-lookup"><span data-stu-id="14a44-117">Check the **Task List** window for build errors.</span></span> <span data-ttu-id="14a44-118">Um das Fenster **Aufgabenliste** anzuzeigen, öffnen Sie das Menü **Ansicht** , zeigen Sie auf **Weitere Fenster**, und klicken Sie dann auf **Aufgabenliste**.</span><span class="sxs-lookup"><span data-stu-id="14a44-118">To view the **Task List** window, open the **View** menu, point to **Other Windows**, and then click **Task List**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14a44-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="14a44-119">See Also</span></span>  
 [<span data-ttu-id="14a44-120">Entwerfen von Berichten mithilfe des Berichts-Designers (SSRS)</span><span class="sxs-lookup"><span data-stu-id="14a44-120">Design Reports with Report Designer &#40;SSRS&#41;</span></span>](tools/design-reporting-services-paginated-reports-with-report-designer-ssrs.md)  
  
  
