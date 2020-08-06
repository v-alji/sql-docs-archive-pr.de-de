---
title: Neues Modell (Seite) (Berichts-Manager) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 27d5bf66-b0e7-489e-a830-ffe2ec8e5350
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: ed591108585b494ebb4498c1a0ab3e782693a45b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620237"
---
# <a name="new-model-page-report-manager"></a><span data-ttu-id="24eb0-102">Neues Modell (Seite) (Berichts-Manager)</span><span class="sxs-lookup"><span data-stu-id="24eb0-102">New Model Page (Report Manager)</span></span>
  <span data-ttu-id="24eb0-103">Verwenden Sie diese Seite, um ein Standardberichtsmodell aus einer freigegebenen Datenquelle zu generieren.</span><span class="sxs-lookup"><span data-stu-id="24eb0-103">Use this page to generate a default report model from a shared data source.</span></span> <span data-ttu-id="24eb0-104">Sie können Berichtsmodelle nur aus mehrdimensionalen [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] -Datenquellen, relationalen [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenquellen und relationalen Oracle-Datenquellen generieren.</span><span class="sxs-lookup"><span data-stu-id="24eb0-104">You can only generate report models from [!INCLUDE[ssASnoversion](../includes/ssasnoversion-md.md)] multidimensional data sources, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] relational data sources, and Oracle relational data sources.</span></span>  
  
 <span data-ttu-id="24eb0-105">Modelle, die Sie im Berichts-Manager generieren, basieren auf dem Schema der freigegebenen Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="24eb0-105">Models that you generate in Report Manager are based on the schema of the shared data source.</span></span> <span data-ttu-id="24eb0-106">Für alle Tabellen und Spalten in der Datenquelle werden Entitäten, Ordner und Felder erstellt.</span><span class="sxs-lookup"><span data-stu-id="24eb0-106">Entities, folders, and fields are created for all tables and columns in the data source.</span></span> <span data-ttu-id="24eb0-107">Sie können weder Elemente ausschließen, noch können Sie Optionen festlegen, die bestimmen, wie das Modell generiert wird.</span><span class="sxs-lookup"><span data-stu-id="24eb0-107">You cannot exclude items, nor can you set options that determine how the model is generated.</span></span> <span data-ttu-id="24eb0-108">Wenn Sie ein Modell anpassen oder verfeinern möchten, müssen Sie stattdessen den Modell-Designer verwenden.</span><span class="sxs-lookup"><span data-stu-id="24eb0-108">If you want to customize or refine a model, you must use Model Designer instead.</span></span>  
  
## <a name="navigation"></a><span data-ttu-id="24eb0-109">Navigation</span><span class="sxs-lookup"><span data-stu-id="24eb0-109">Navigation</span></span>  
 <span data-ttu-id="24eb0-110">Verwenden Sie folgendes Verfahren, um zu dieser Position in der Benutzeroberfläche zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="24eb0-110">Use the following procedure to navigate to this location in the user interface (UI).</span></span>  
  
###### <a name="to-open-the-new-model-page"></a><span data-ttu-id="24eb0-111">So öffnen Sie die Seite "Neues Modell"</span><span class="sxs-lookup"><span data-stu-id="24eb0-111">To open the New Model page</span></span>  
  
1.  <span data-ttu-id="24eb0-112">Öffnen Sie den Berichts-Manager, und suchen Sie die freigegebene Datenquelle, von der Sie ein Modell generieren möchten.</span><span class="sxs-lookup"><span data-stu-id="24eb0-112">Open Report Manager, and locate the shared data source from which you want to generate a model.</span></span>  
  
2.  <span data-ttu-id="24eb0-113">Zeigen Sie auf die Datenquelle, und klicken Sie auf den Dropdownpfeil.</span><span class="sxs-lookup"><span data-stu-id="24eb0-113">Hover over the data source, and click the drop-down arrow.</span></span>  
  
3.  <span data-ttu-id="24eb0-114">Führen Sie im Dropdownmenü einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="24eb0-114">In the drop-down menu, perform one of the following steps:</span></span>  
  
    -   <span data-ttu-id="24eb0-115">Klicken Sie auf **Berichtsmodell generieren** , um die Seite Neues Modell zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="24eb0-115">Click **Generate Report Model** to open the New Model page.</span></span>  
  
    -   <span data-ttu-id="24eb0-116">Klicken Sie auf **Verwalten** , um die Seite Allgemeine Eigenschaften für den Bericht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="24eb0-116">Click **Manage** to open the General properties page for the report.</span></span> <span data-ttu-id="24eb0-117">Klicken Sie dann auf **Modell generieren** , um die Seite Neues Modell zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="24eb0-117">Then click **Generate Model** to open the New Model page.</span></span>  
  
## <a name="options"></a><span data-ttu-id="24eb0-118">Tastatur</span><span class="sxs-lookup"><span data-stu-id="24eb0-118">Options</span></span>  
 <span data-ttu-id="24eb0-119">**Name**</span><span class="sxs-lookup"><span data-stu-id="24eb0-119">**Name**</span></span>  
 <span data-ttu-id="24eb0-120">Gibt den Namen des Modells an.</span><span class="sxs-lookup"><span data-stu-id="24eb0-120">Specifies the name of the model.</span></span> <span data-ttu-id="24eb0-121">Der Name muss mindestens ein alphanumerisches Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="24eb0-121">A name must contain at least one alphanumeric character.</span></span> <span data-ttu-id="24eb0-122">Er kann auch Leerzeichen und Sonderzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="24eb0-122">It can also include spaces and some symbols.</span></span> <span data-ttu-id="24eb0-123">Folgende Zeichen können beim Angeben eines Namens nicht verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="24eb0-123">Do not use the following characters when specifying a name:</span></span>  
  
 <span data-ttu-id="24eb0-124">; ?</span><span class="sxs-lookup"><span data-stu-id="24eb0-124">; ?</span></span> <span data-ttu-id="24eb0-125">: \@ & = +, $/\* \< > | " /</span><span class="sxs-lookup"><span data-stu-id="24eb0-125">: \@ & = + , $ / \* \< > | " /</span></span>  
  
 <span data-ttu-id="24eb0-126">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="24eb0-126">**Description**</span></span>  
 <span data-ttu-id="24eb0-127">Zeigt eine Beschreibung des Modells an.</span><span class="sxs-lookup"><span data-stu-id="24eb0-127">Shows a description of the model.</span></span> <span data-ttu-id="24eb0-128">Benutzer, die dieses Element über den Berichts-Manager anzeigen, können diese Beschreibung sehen, wenn sie die Ordnerhierarchie durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="24eb0-128">Users who view this item through Report Manager see this description when browsing the folder hierarchy.</span></span>  
  
 <span data-ttu-id="24eb0-129">**Speicherort ändern**</span><span class="sxs-lookup"><span data-stu-id="24eb0-129">**Change Location**</span></span>  
 <span data-ttu-id="24eb0-130">Zeigt den Speicherort des Ordners des neuen Modells an.</span><span class="sxs-lookup"><span data-stu-id="24eb0-130">Shows the folder location for the new model.</span></span> <span data-ttu-id="24eb0-131">Sie können auf die Schaltfläche **Speicherort ändern** klicken, um einen anderen Speicherort auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="24eb0-131">You can click the **Change Location** button to select a different location.</span></span>  
  
  
