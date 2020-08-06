---
title: Neuer verknüpfter Bericht (Seite) (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: fefb46e8-6901-4d50-a3f8-7c49ad72e7b1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 61138e51cfd9bb6e1ee124dd4aa3bc224d8aebcf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620238"
---
# <a name="new-linked-report-page-report-manager"></a><span data-ttu-id="0c4c7-102">Neuer verknüpfter Bericht (Seite) (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="0c4c7-102">New Linked Report Page (Report Manager)</span></span>
  <span data-ttu-id="0c4c7-103">Auf der Seite Neuer verknüpfter Bericht können Sie einen verknüpften Bericht erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-103">Use the New Linked Report page to create a linked report.</span></span> <span data-ttu-id="0c4c7-104">Als verknüpfter Bericht wird ein Bericht mit eigenen Einstellungen und Eigenschaften bezeichnet, der jedoch mit der Berichtsdefinition eines anderen Berichts verknüpft ist.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-104">A linked report is a report with settings and properties of its own, but links to the report definition of another report.</span></span> <span data-ttu-id="0c4c7-105">Verwenden Sie verknüpfte Berichte, wenn Sie über einen Basisbericht verfügen, der für spezifische Gruppen oder Benutzer unterschiedlich angezeigt werden soll. Dies kann z. B. ein regionaler Bericht sein, der auf der Grundlage einer Regionalkennzahl, die Sie als Parameter angeben, unterschiedliche Daten zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-105">Linked reports are useful when you have a base report that you want to vary for specific groups or users; for example, a regional report that returns different data based on a regional code that you specify as a parameter.</span></span> <span data-ttu-id="0c4c7-106">Ein verknüpfter Bericht wird in der Regel aus einem parametrisierten Bericht erstellt, den Sie variieren und für den Sie anschließend unterschiedliche Parameterwerte für jede einzelne Berichtsinstanz speichern.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-106">A linked report is typically created from a parameterized report when you want to vary and then save different parameter values with each report instance.</span></span> <span data-ttu-id="0c4c7-107">Sie können aus jedem beliebigen Bericht, auf den Sie zugreifen können, einen verknüpften Bericht erstellen.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-107">However, you can create a linked report from any report to which you have access.</span></span>  
  
 <span data-ttu-id="0c4c7-108">Ein verknüpfter Bericht kann über einen eigenen Namen und Speicherort, eine eigene Beschreibung sowie eigene Parametereigenschaften, Berichtsausführungseigenschaften, Berichtsverlaufseigenschaften, Berechtigungen und Abonnements verfügen.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-108">A linked report can have its own name, description, location, parameter properties, report execution properties, report history properties, permissions, and subscriptions.</span></span> <span data-ttu-id="0c4c7-109">Ein verknüpfter Bericht muss jedoch die Datenquelleneigenschaften und das Layout des Basisberichts verwenden, der die Berichtsdefinition bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-109">However, a linked report must use the data source properties and layout of the base report that provides the report definition.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="0c4c7-110">Navigation</span><span class="sxs-lookup"><span data-stu-id="0c4c7-110">Navigation</span></span>  
 <span data-ttu-id="0c4c7-111">Verwenden Sie folgende Verfahren, um zu dieser Position in der Benutzeroberfläche zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-111">Use the following procedures to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-linked-report-page-from-the-contents-page"></a><span data-ttu-id="0c4c7-112">So öffnen Sie die Seite "Neuer verknüpfter Bericht" über die Seite "Inhalt"</span><span class="sxs-lookup"><span data-stu-id="0c4c7-112">To open the New Linked Report page from the Contents page</span></span>  
  
1.  <span data-ttu-id="0c4c7-113">Öffnen Sie den Berichts-Manager, und suchen Sie einen Bericht, für den Sie einen verknüpften Bericht erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-113">Open Report Manager, and locate a report for which you want to create a linked report.</span></span>  
  
2.  <span data-ttu-id="0c4c7-114">Zeigen Sie auf den Bericht, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-114">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="0c4c7-115">Klicken Sie im Dropdownmenü auf **Verknüpften Bericht erstellen**.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-115">In the drop-down menu, click **Create Linked Report**.</span></span>  
  
###### <a name="to-open-the-new-linked-report-page-from-the-general-properties-page-of-a-report"></a><span data-ttu-id="0c4c7-116">So öffnen Sie die Seite 'Neuer verknüpfter Bericht' von der Seite 'Allgemeine Eigenschaften' eines Berichts</span><span class="sxs-lookup"><span data-stu-id="0c4c7-116">To open the New Linked Report page from the General properties page of a report</span></span>  
  
1.  <span data-ttu-id="0c4c7-117">Öffnen Sie den Berichts-Manager, und suchen Sie einen Bericht, für den Sie einen verknüpften Bericht erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-117">Open Report Manager, and locate a report for which you want to create a linked report.</span></span>  
  
2.  <span data-ttu-id="0c4c7-118">Zeigen Sie auf den Bericht, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-118">Hover over the report, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="0c4c7-119">Klicken Sie im Dropdownmenü auf **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-119">In the drop-down menu, click **Manage**.</span></span> <span data-ttu-id="0c4c7-120">Dadurch wird die Seite Allgemeine Eigenschaften für den Bericht geöffnet.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-120">This opens the General properties page for the report.</span></span>  
  
4.  <span data-ttu-id="0c4c7-121">Klicken Sie auf der Elementsymbolleiste auf **Verknüpften Bericht erstellen**.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-121">In the item toolbar, click **Create Linked Report**.</span></span>  
  
## <a name="options"></a><span data-ttu-id="0c4c7-122">Tastatur</span><span class="sxs-lookup"><span data-stu-id="0c4c7-122">Options</span></span>  
 <span data-ttu-id="0c4c7-123">**Name**</span><span class="sxs-lookup"><span data-stu-id="0c4c7-123">**Name**</span></span>  
 <span data-ttu-id="0c4c7-124">Geben Sie den Namen des verknüpften Berichts an.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-124">Specify the name of the linked report.</span></span> <span data-ttu-id="0c4c7-125">Der Name muss mindestens ein alphanumerisches Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-125">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="0c4c7-126">Er kann auch Leerzeichen und bestimmte Sonderzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-126">It can also include spaces and certain symbols.</span></span> <span data-ttu-id="0c4c7-127">Folgende Zeichen können nicht beim Angeben eines Namens verwendet werden: ; ?</span><span class="sxs-lookup"><span data-stu-id="0c4c7-127">However, you must not use the characters ; ?</span></span> <span data-ttu-id="0c4c7-128">: \@ & = +, $/\* \< > | "oder/, wenn ein Name angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-128">: \@ & = + , $ / \* \< > | " or / when specifying a name.</span></span>  
  
 <span data-ttu-id="0c4c7-129">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0c4c7-129">**Description**</span></span>  
 <span data-ttu-id="0c4c7-130">Geben Sie eine Beschreibung des Berichtsinhalts ein.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-130">Type a description of the report contents.</span></span> <span data-ttu-id="0c4c7-131">Diese Beschreibung wird für Benutzer, die über die Berechtigung zum Zugreifen auf den Bericht verfügen, auf der Seite Inhalt angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-131">This description appears in the Contents page to users who have permission to access the report.</span></span>  
  
 <span data-ttu-id="0c4c7-132">**Location**</span><span class="sxs-lookup"><span data-stu-id="0c4c7-132">**Location**</span></span>  
 <span data-ttu-id="0c4c7-133">Geben Sie den Ordnerpfad des Berichts an.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-133">Specify the folder path that contains the report.</span></span> <span data-ttu-id="0c4c7-134">Standardmäßig werden verknüpfte Berichte als gleichgeordnete Elemente des Basisberichts erstellt.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-134">By default, linked reports are created as siblings to the base report.</span></span> <span data-ttu-id="0c4c7-135">Klicken Sie auf **Speicherort ändern** , um den verknüpften Bericht in einem anderen Ordner zu speichern.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-135">Click **Change Location** to put the linked report in a different folder.</span></span>  
  
 <span data-ttu-id="0c4c7-136">**OK**</span><span class="sxs-lookup"><span data-stu-id="0c4c7-136">**OK**</span></span>  
 <span data-ttu-id="0c4c7-137">Klicken Sie auf **OK** , um die Änderungen zu speichern und zur Eigenschaftenseite Allgemein des Basisberichts zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="0c4c7-137">Click **OK** to save your changes and return to the General properties page of the base report.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c4c7-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0c4c7-138">See Also</span></span>  
 <span data-ttu-id="0c4c7-139">[Erstellen eines verknüpften Berichts](reports/create-a-linked-report.md) </span><span class="sxs-lookup"><span data-stu-id="0c4c7-139">[Create a Linked Report](reports/create-a-linked-report.md) </span></span>  
 <span data-ttu-id="0c4c7-140">[Allgemeine Eigenschaften (Seite), Berichte &#40;Berichts-Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span><span class="sxs-lookup"><span data-stu-id="0c4c7-140">[General Properties Page, Reports &#40;Report Manager&#41;](../../2014/reporting-services/general-properties-page-reports-report-manager.md) </span></span>  
 [<span data-ttu-id="0c4c7-141">Berichts-Manager (F1-Hilfe)</span><span class="sxs-lookup"><span data-stu-id="0c4c7-141">Report Manager F1 Help</span></span>](../../2014/reporting-services/report-manager-f1-help.md)  
  
  
