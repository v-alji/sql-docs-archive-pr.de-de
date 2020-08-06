---
title: Erstellen eines verknüpften Berichts | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- linked reports [Reporting Services], creating
ms.assetid: 12be8341-cb57-45e8-a421-2bf66b50234d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed5e70c9ff8179ae05186685e21303693fc9aed7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619568"
---
# <a name="create-a-linked-report"></a><span data-ttu-id="fc5b0-102">Erstellen eines verknüpften Berichts</span><span class="sxs-lookup"><span data-stu-id="fc5b0-102">Create a Linked Report</span></span>
  <span data-ttu-id="fc5b0-103">Ein verknüpfter Bericht ist ein Berichtsserverelement, das einen Zugriffspunkt auf einen vorhandenen Bericht bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-103">A linked report is a report server item that provides an access point to an existing report.</span></span> <span data-ttu-id="fc5b0-104">Grundsätzlich ist er mit einer Programmverknüpfung vergleichbar, die Sie verwenden, um ein Programm auszuführen oder eine Datei zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-104">Conceptually, it is similar to a program shortcut that you use to run a program or open a file.</span></span>

 <span data-ttu-id="fc5b0-105">Ein verknüpfter Bericht wird von einem vorhandenen Bericht abgeleitet und behält die Berichtsdefinition des Originals bei.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-105">A linked report is derived from an existing report and retains the original's report definition.</span></span> <span data-ttu-id="fc5b0-106">Ein verknüpfter Bericht erbt immer das Berichtslayout und die Datenquelleneigenschaften des ursprünglichen Berichts.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-106">A linked report always inherits report layout and data source properties of the original report.</span></span> <span data-ttu-id="fc5b0-107">Alle anderen Eigenschaften und Einstellungen können sich von denen des ursprünglichen Berichts unterscheiden, einschließlich Sicherheit, Parameter, Speicherort, Abonnements und Zeitpläne.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-107">All other properties and settings can be different from those of the original report, including security, parameters, location, subscriptions, and schedules.</span></span>

 <span data-ttu-id="fc5b0-108">Sie können einen verknüpften Bericht erstellen, wenn Sie zusätzliche Versionen eines vorhandenen Berichts erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-108">You can create a linked report when you want to create additional versions of an existing report.</span></span> <span data-ttu-id="fc5b0-109">Beispielsweise könnten Sie einen einzelnen regionalen Vertriebsbericht verwenden, um regionsspezifische Berichte für alle Vertriebsgebiete zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-109">For example, you could use a single regional sales report to create region-specific reports for all of your sales territories.</span></span>

 <span data-ttu-id="fc5b0-110">Obwohl verknüpfte Berichte in der Regel auf parametrisierten Berichten basieren, ist kein parametrisierter Bericht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-110">Although linked reports are typically based on parameterized reports, a parameterized report is not required.</span></span> <span data-ttu-id="fc5b0-111">Sie können immer dann verknüpfte Berichte erstellen, wenn Sie einen vorhandenen Bericht mit anderen Einstellungen bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-111">You can create linked reports whenever you want to deploy an existing report with different settings.</span></span>

### <a name="to-create-a-linked-report"></a><span data-ttu-id="fc5b0-112">So erstellen Sie einen verknüpften Bericht</span><span class="sxs-lookup"><span data-stu-id="fc5b0-112">To create a linked report</span></span>

1.  <span data-ttu-id="fc5b0-113">Navigieren Sie im Berichts-Manager zum Ordner, der den Bericht enthält, zu dem Sie einen Link erstellen möchten, und öffnen Sie dann das Menü Optionen und klicken Sie auf **Verknüpften Bericht erstellen**.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-113">In Report Manager, navigate to the folder containing the report that you want to link to, and then open the options menu can click **Create Linked Report**.</span></span>

2.  <span data-ttu-id="fc5b0-114">Geben Sie einen Namen für den neuen verknüpften Bericht ein.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-114">Type a name for the new linked report.</span></span> <span data-ttu-id="fc5b0-115">Geben Sie optional eine Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-115">Optionally type a description.</span></span>

3.  <span data-ttu-id="fc5b0-116">Um einen anderen Ordner für den Bericht auszuwählen, klicken Sie auf **Speicherort ändern**.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-116">To select a different folder for the report, click **Change Location**.</span></span> <span data-ttu-id="fc5b0-117">Klicken Sie auf den Ordner, den Sie verwenden möchten, oder geben Sie den Ordnernamen im Feld **Speicherort** ein.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-117">Click the folder you want to use, or type the folder name in the **Location** box.</span></span> [!INCLUDE[clickOK](../../../includes/clickok-md.md)] <span data-ttu-id="fc5b0-118">Wenn Sie keinen anderen Ordner auswählen, wird der verknüpfte Bericht im aktuellen Ordner (in dem der Bericht, auf dem er basiert, gespeichert ist) erstellt.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-118">If you do not select a different folder, the linked report is created in the current folder (where the report it is based on is stored).</span></span>

4.  [!INCLUDE[clickOK](../../../includes/clickok-md.md)] <span data-ttu-id="fc5b0-119">Der verknüpfte Bericht wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-119">The linked report opens.</span></span>

     <span data-ttu-id="fc5b0-120">Das Symbol für einen verknüpften Bericht unterscheidet sich von anderen Elementen, die von einem Berichtsserver verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="fc5b0-120">A linked report's icon differs from other items managed by a report server.</span></span> <span data-ttu-id="fc5b0-121">Das folgende Symbol steht für einen verknüpften Bericht:</span><span class="sxs-lookup"><span data-stu-id="fc5b0-121">The following icon indicates a linked report:</span></span>

     <span data-ttu-id="fc5b0-122">![Symbol für einen verknüpften Bericht](../media/hlp-16linked.gif "Symbol für einen verknüpften Bericht")</span><span class="sxs-lookup"><span data-stu-id="fc5b0-122">![Linked report icon](../media/hlp-16linked.gif "Linked report icon")</span></span>

## <a name="see-also"></a><span data-ttu-id="fc5b0-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fc5b0-123">See Also</span></span>
 <span data-ttu-id="fc5b0-124">[Öffnen und schließen Sie einen Bericht &#40;Berichts-Manager&#41;](../reports/open-and-close-a-report-report-manager.md) [neuen verknüpften Berichtsseite &#40;Berichts-Manager](../new-linked-report-page-report-manager.md) [&#41;Seite Speicherort für Elemente auswählen &#40;Berichts-Manager&#41;Seite](../choose-item-location-page-report-manager.md) [Allgemeine Eigenschaften die Berichte &#40;](../general-properties-page-reports-report-manager.md) Berichts-Manager&#41;Reporting Services &#40;&#41;[SSRS](../reporting-services-concepts-ssrs.md) Berichts-Manager &#40;&#41;[SSRS im einheitlichen Modus](../report-manager-ssrs-native-mode.md)</span><span class="sxs-lookup"><span data-stu-id="fc5b0-124">[Open and Close a Report &#40;Report Manager&#41;](../reports/open-and-close-a-report-report-manager.md) [New Linked Report Page &#40;Report Manager&#41;](../new-linked-report-page-report-manager.md) [Choose Item Location Page &#40;Report Manager&#41;](../choose-item-location-page-report-manager.md) [General Properties Page, Reports &#40;Report Manager&#41;](../general-properties-page-reports-report-manager.md) [Reporting Services Concepts &#40;SSRS&#41;](../reporting-services-concepts-ssrs.md) [Report Manager  &#40;SSRS Native Mode&#41;](../report-manager-ssrs-native-mode.md)</span></span>


