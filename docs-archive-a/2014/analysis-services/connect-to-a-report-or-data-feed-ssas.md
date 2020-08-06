---
title: Mit einem Bericht oder Datenfeed verbinden (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.connreportdatafeed.f1
ms.assetid: e0ccfb0b-e646-4de8-b7da-f88c986c96e4
author: minewiskan
ms.author: owend
ms.openlocfilehash: 76dd51c32d13e64b0368267ba7ac66aa6d76a784
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610214"
---
# <a name="connect-to-a-report-or-data-feed-ssas"></a><span data-ttu-id="bd6ad-102">Mit einem Bericht oder Datenfeed verbinden (SSAS)</span><span class="sxs-lookup"><span data-stu-id="bd6ad-102">Connect to a Report or Data Feed (SSAS)</span></span>
  <span data-ttu-id="bd6ad-103">Auf dieser Seite des **Tabellenimport-Assistenten** können Sie eine Verbindung mit einem Datenfeed herstellen.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-103">This page of the **Table Import Wizard** enables you to connect to a data feed.</span></span> <span data-ttu-id="bd6ad-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
## <a name="from-a-report"></a><span data-ttu-id="bd6ad-105">Aus einem Bericht</span><span class="sxs-lookup"><span data-stu-id="bd6ad-105">From a Report</span></span>  
 <span data-ttu-id="bd6ad-106">**Anzeige Name der Verbindung**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-106">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="bd6ad-107">Geben Sie einen Anzeigenamen für die Verbindung mit dem Datenfeed ein.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-107">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="bd6ad-108">**Berichtspfad**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-108">**Report Path**</span></span>  
 <span data-ttu-id="bd6ad-109">Führt die URL für einen SQL Server Reporting Services-Bericht auf, der Datenfeeds generiert.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-109">Lists the URL for a SQL Server Reporting Services report that generates data feeds.</span></span> <span data-ttu-id="bd6ad-110">Klicken Sie auf **Durchsuchen** , um die URL für den Bericht anzugeben.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-110">Click **Browse** to specify the URL for the report.</span></span>  
  
 <span data-ttu-id="bd6ad-111">Klicken Sie auf **Bericht anzeigen**, um den Bericht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-111">Click **View Report** to display the report.</span></span>  
  
 <span data-ttu-id="bd6ad-112">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-112">**Browse**</span></span>  
 <span data-ttu-id="bd6ad-113">Navigieren Sie zu einem Speicherort, an dem ein Bericht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-113">Navigate to a location where a report is available.</span></span>  
  
 <span data-ttu-id="bd6ad-114">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-114">**Advanced**</span></span>  
 <span data-ttu-id="bd6ad-115">Legen Sie zusätzliche Verbindungs Eigenschaften im Dialogfeld **Erweiterte Eigenschaften festlegen** fest.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-115">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="bd6ad-116">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-116">**Test Connection**</span></span>  
 <span data-ttu-id="bd6ad-117">Stellen Sie unter Verwendung der aktuellen Einstellungen eine Verbindung mit der Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-117">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="bd6ad-118">Eine Meldung gibt Aufschluss darüber, ob die Verbindungsherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-118">A message is displayed indicating whether the connection is successful.</span></span>  
  
## <a name="from-an-azure-datamarket-dataset"></a><span data-ttu-id="bd6ad-119">Aus einem Azure DataMarket-Dataset</span><span class="sxs-lookup"><span data-stu-id="bd6ad-119">From an Azure DataMarket Dataset</span></span>  
 <span data-ttu-id="bd6ad-120">**Anzeige Name der Verbindung**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-120">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="bd6ad-121">Geben Sie einen Anzeigenamen für die Verbindung mit dem Datenfeed ein.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-121">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="bd6ad-122">**Datenfeed-URL**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-122">**Data Feed URL**</span></span>  
 <span data-ttu-id="bd6ad-123">Geben Sie den vollständigen Pfad zu einem Atom-Dienstdokument (.atomsvc, .atom) oder die URL für einen einzelnen Datenfeed ein, oder klicken Sie auf **Durchsuchen** , um ein Atom-Dienstdokument auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-123">Type the full path to an Atom service document (.atomsvc, .atom) or the URL for a single data feed, or click **Browse** to select an Atom service document.</span></span>  
  
 <span data-ttu-id="bd6ad-124">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-124">**Browse**</span></span>  
 <span data-ttu-id="bd6ad-125">Navigieren Sie zu einem Speicherort, an dem ein Bericht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-125">Navigate to a location where a report is available.</span></span>  
  
 <span data-ttu-id="bd6ad-126">Klicken Sie auf **Verfügbare Azure DataMarket-Datasets anzeigen** , um verfügbare Datasets anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-126">Click **View available Azure DataMarket datasets** to display available datasets.</span></span>  
  
 <span data-ttu-id="bd6ad-127">**Kontoschlüssel**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-127">**Account key**</span></span>  
 <span data-ttu-id="bd6ad-128">Geben Sie den Kontoschlüssel an, mit dem auf Ihre Azure Marketplace DataSet-Abonnements zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-128">Specify the account key used to access your Azure Marketplace dataset subscriptions.</span></span>  
  
 <span data-ttu-id="bd6ad-129">**Sich**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-129">**Find**</span></span>  
 <span data-ttu-id="bd6ad-130">Suchen Sie einen einem Windows Live-Konto zugeordneten Kontoschlüssel.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-130">Locate an account key associated with a Windows Live account.</span></span>  
  
 <span data-ttu-id="bd6ad-131">**Meinen Kontoschlüssel speichern**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-131">**Save my account key**</span></span>  
 <span data-ttu-id="bd6ad-132">Speichert den Kontoschlüssel (verschlüsselt) mit der Datenverbindung.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-132">Saves the account key (encrypted) with the data connection.</span></span>  
  
 <span data-ttu-id="bd6ad-133">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-133">**Advanced**</span></span>  
 <span data-ttu-id="bd6ad-134">Legen Sie zusätzliche Verbindungs Eigenschaften im Dialogfeld **Erweiterte Eigenschaften festlegen** fest.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-134">Set additional connection properties by using the **Set Advanced Properties** dialog box..</span></span>  
  
 <span data-ttu-id="bd6ad-135">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-135">**Test Connection**</span></span>  
 <span data-ttu-id="bd6ad-136">Stellen Sie unter Verwendung der aktuellen Einstellungen eine Verbindung mit der Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-136">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="bd6ad-137">Eine Meldung gibt Aufschluss darüber, ob die Verbindungsherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-137">A message is displayed indicating whether the connection is successful.</span></span>  
  
## <a name="from-other-feeds"></a><span data-ttu-id="bd6ad-138">Aus anderen Feeds</span><span class="sxs-lookup"><span data-stu-id="bd6ad-138">From Other Feeds</span></span>  
 <span data-ttu-id="bd6ad-139">**Anzeige Name der Verbindung**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-139">**Friendly Connection Name**</span></span>  
 <span data-ttu-id="bd6ad-140">Geben Sie einen Anzeigenamen für die Verbindung mit dem Datenfeed ein.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-140">Type a friendly name for the data feed connection.</span></span>  
  
 <span data-ttu-id="bd6ad-141">**Datenfeed-URL**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-141">**Data Feed URL**</span></span>  
 <span data-ttu-id="bd6ad-142">Geben Sie den vollständigen Pfad zu einem Atom-Dienstdokument (.atomsvc, .atom) oder die URL für einen einzelnen Datenfeed ein, oder klicken Sie auf **Durchsuchen** , um ein Atom-Dienstdokument auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-142">Type the full path to an Atom service document (.atomsvc, .atom) or the URL for a single data feed, or click **Browse** to select an Atom service document.</span></span>  
  
 <span data-ttu-id="bd6ad-143">Klicken Sie auf **Alle Feedspalten einschließen** , um anzugeben, dass alle Datenfeedspalten importiert werden.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-143">Click **Include all feed columns** to specify whether all the data feed columns are imported.</span></span>  
  
 <span data-ttu-id="bd6ad-144">**Durchsuchen**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-144">**Browse**</span></span>  
 <span data-ttu-id="bd6ad-145">Navigieren Sie zu einem Speicherort, an dem ein Datenfeed verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-145">Navigate to a location where a data feed is available.</span></span>  
  
 <span data-ttu-id="bd6ad-146">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-146">**Advanced**</span></span>  
 <span data-ttu-id="bd6ad-147">Legen Sie zusätzliche Verbindungseigenschaften im Dialogfeld **Erweiterte Eigenschaften festlegen** fest.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-147">Set additional connection properties by using the **Set Advanced Properties** dialog box.</span></span>  
  
 <span data-ttu-id="bd6ad-148">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="bd6ad-148">**Test Connection**</span></span>  
 <span data-ttu-id="bd6ad-149">Stellen Sie unter Verwendung der aktuellen Einstellungen eine Verbindung mit der Datenquelle her.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-149">Attempt to establish a connection to the data source using the current settings.</span></span> <span data-ttu-id="bd6ad-150">Eine Meldung gibt Aufschluss darüber, ob die Verbindungsherstellung erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="bd6ad-150">A message is displayed indicating whether the connection is successful.</span></span>  
  
  
