---
title: 'Aufgabe 2: Zuordnung von Excel-Spalten zu DQS-Domänen | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: f347cc92-950f-4021-b7af-393640dfe821
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: 293b035ff52845959e2c8b70c63df643ae6e3e55
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621287"
---
# <a name="task-2-mapping-excel-columns-to-dqs-domains"></a><span data-ttu-id="37e3a-102">Aufgabe 2: Zuordnen von Excel-Spalten zu DQS-Domänen</span><span class="sxs-lookup"><span data-stu-id="37e3a-102">Task 2: Mapping Excel Columns to DQS Domains</span></span>
    
1.  <span data-ttu-id="37e3a-103">Wählen Sie auf der Seite **Zuordnen** für **Datenquelle** die Option **Excel-Datei**aus.</span><span class="sxs-lookup"><span data-stu-id="37e3a-103">In the **Map** page, select **Excel File** for **Data Source**.</span></span>  
  
2.  <span data-ttu-id="37e3a-104">Klicken Sie auf **Durchsuchen**, und wählen **Sie** **Suppliers.xlsx**aus.</span><span class="sxs-lookup"><span data-stu-id="37e3a-104">Click **Browse**, select **Suppliers.xlsx**, and click **Open**.</span></span>  
  
3.  <span data-ttu-id="37e3a-105">Wählen Sie **incomingsuppliers $** für das **Arbeitsblatt**aus.</span><span class="sxs-lookup"><span data-stu-id="37e3a-105">Select **IncomingSuppliers$** for the **Worksheet**.</span></span>  
  
4.  <span data-ttu-id="37e3a-106">Ordnen Sie die Spalten an, wie in der folgenden Tabelle und im Screenshot dargestellt.</span><span class="sxs-lookup"><span data-stu-id="37e3a-106">Map columns as shown in the following table and screenshot.</span></span> <span data-ttu-id="37e3a-107">Wenn Sie Zuordnungen für die **Zustands** Domäne erstellen, klicken Sie auf die Schaltfläche **Spalten Zuordnung hinzufügen** auf der Symbolleiste, die sich direkt über der Liste befindet.</span><span class="sxs-lookup"><span data-stu-id="37e3a-107">When creating mappings for the **State** domain, click **Add a column mapping** button on the toolbar located just above the list.</span></span>  
  
    > [!TIP]  
    >  <span data-ttu-id="37e3a-108">Sie verwenden die Spalte/Domäne der **Lieferanten-ID** nicht für die Bereinigung.</span><span class="sxs-lookup"><span data-stu-id="37e3a-108">You are not using **Supplier ID** column/domain for cleansing.</span></span> <span data-ttu-id="37e3a-109">Sie verwenden die **Lieferanten-ID** -Domäne später in der abgleichsaktivität.</span><span class="sxs-lookup"><span data-stu-id="37e3a-109">You will use the **Supplier ID** domain later in the matching activity.</span></span>  
  
    |<span data-ttu-id="37e3a-110">Excel-Spalte</span><span class="sxs-lookup"><span data-stu-id="37e3a-110">Excel column</span></span>|<span data-ttu-id="37e3a-111">DQS-Domäne</span><span class="sxs-lookup"><span data-stu-id="37e3a-111">DQS Domain</span></span>|  
    |------------------|----------------|  
    |<span data-ttu-id="37e3a-112">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="37e3a-112">Supplier Name</span></span>|<span data-ttu-id="37e3a-113">Supplier Name</span><span class="sxs-lookup"><span data-stu-id="37e3a-113">Supplier Name</span></span>|  
    |<span data-ttu-id="37e3a-114">ContactEmailAddress</span><span class="sxs-lookup"><span data-stu-id="37e3a-114">ContactEmailAddress</span></span>|<span data-ttu-id="37e3a-115">Kontakt-E-Mail</span><span class="sxs-lookup"><span data-stu-id="37e3a-115">Contact Email</span></span>|  
    |<span data-ttu-id="37e3a-116">Adresszeile</span><span class="sxs-lookup"><span data-stu-id="37e3a-116">Address Line</span></span>|<span data-ttu-id="37e3a-117">Adresszeile</span><span class="sxs-lookup"><span data-stu-id="37e3a-117">Address Line</span></span>|  
    |<span data-ttu-id="37e3a-118">City</span><span class="sxs-lookup"><span data-stu-id="37e3a-118">City</span></span>|<span data-ttu-id="37e3a-119">City</span><span class="sxs-lookup"><span data-stu-id="37e3a-119">City</span></span>|  
    |<span data-ttu-id="37e3a-120">State</span><span class="sxs-lookup"><span data-stu-id="37e3a-120">State</span></span>|<span data-ttu-id="37e3a-121">State</span><span class="sxs-lookup"><span data-stu-id="37e3a-121">State</span></span>|  
    |<span data-ttu-id="37e3a-122">Country (Klicken Sie auf **+ (Spalten Zuordnung hinzufügen)** Symbolleiste, um eine Zeile hinzuzufügen)</span><span class="sxs-lookup"><span data-stu-id="37e3a-122">Country (Click **+(Add a column mapping)** toolbar to add a row)</span></span>|<span data-ttu-id="37e3a-123">Land</span><span class="sxs-lookup"><span data-stu-id="37e3a-123">Country</span></span>|  
    |<span data-ttu-id="37e3a-124">Zip Code</span><span class="sxs-lookup"><span data-stu-id="37e3a-124">Zip Code</span></span>|<span data-ttu-id="37e3a-125">Zip</span><span class="sxs-lookup"><span data-stu-id="37e3a-125">Zip</span></span>|  
  
     <span data-ttu-id="37e3a-126">![Zuordnen von Excel-Spalten zu Domänen](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "Zuordnen von Excel-Spalten zu Domänen")</span><span class="sxs-lookup"><span data-stu-id="37e3a-126">![Mappings of Excel Columns to Domains](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-01.jpg "Mappings of Excel Columns to Domains")</span></span>  
  
5.  <span data-ttu-id="37e3a-127">Wenn Sie alle einzelnen Domänen innerhalb der Verbund Domäne der **Adressvalidierung** zugeordnet haben, wird die Verbund Domäne automatisch an dem Bereinigungs Prozess beteiligt.</span><span class="sxs-lookup"><span data-stu-id="37e3a-127">As you have mapped all the individual domains within the **Address Validation** composite domain, the composite domain automatically participates in the cleansing process.</span></span> <span data-ttu-id="37e3a-128">Klicken Sie auf die Schaltfläche **Verbund Domänen anzeigen/auswählen** , um anzuzeigen, dass die Verbund Domäne für die **Adressvalidierung** automatisch ausgewählt ist, **und klicken Sie dann auf**</span><span class="sxs-lookup"><span data-stu-id="37e3a-128">Click **View/Select Composite Domains** button to see that the **Address Validation** composite domain is automatically selected, and then click **OK**.</span></span>  
  
     <span data-ttu-id="37e3a-129">![Verbunddomänen anzeigen/auswählen (Dialogfeld)](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "Verbunddomänen anzeigen/auswählen (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="37e3a-129">![View/Select Composite Domains Dialog Box](../../2014/tutorials/media/et-mappingexcelcolumnstodqsdomains-02.jpg "View/Select Composite Domains Dialog Box")</span></span>  
  
6.  <span data-ttu-id="37e3a-130">Klicken Sie auf **weiter** , um **zur Seite** bereinigen zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="37e3a-130">Click **Next** to switch to the **Cleanse** page.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="37e3a-131">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="37e3a-131">Next Step</span></span>  
 [<span data-ttu-id="37e3a-132">Aufgabe 3: Bereinigung von Daten anhand der Wissensdatenbank „Suppliers“</span><span class="sxs-lookup"><span data-stu-id="37e3a-132">Task 3: Cleansing Data against the Suppliers Knowledge Base</span></span>](../../2014/tutorials/task-3-cleansing-data-against-the-suppliers-knowledge-base.md)  
  
  
