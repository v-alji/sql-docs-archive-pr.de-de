---
title: Herstellen einer Verbindung mit einer Datenquelle (SSAS) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.conndatasource.f1
ms.assetid: 1e2b17e9-092b-4af1-8a58-c52b8fe10ff1
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4fe7f7d5b31118369b8ce2a855b955e44f661dbc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610230"
---
# <a name="connect-to-a-data-source-ssas"></a><span data-ttu-id="7b91a-102">Mit einer Datenquelle verbinden (SSAS)</span><span class="sxs-lookup"><span data-stu-id="7b91a-102">Connect to a Data Source (SSAS)</span></span>
  <span data-ttu-id="7b91a-103">Auf dieser Seite des **Tabellenimport-Assistenten** können Sie eine neue Datenquellenverbindung mit einer Vielzahl von Datenquellen erstellen, z. B. relationalen Datenbanken, Datenfeeds und Dateien.</span><span class="sxs-lookup"><span data-stu-id="7b91a-103">This page of the **Table Import Wizard** enables you to create a new data source connection to a variety of data sources, such as relational databases, data feeds, and files.</span></span> <span data-ttu-id="7b91a-104">Um im [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)]auf den Assistenten zuzugreifen, klicken Sie im Menü **Modell** auf **Aus Datenquelle importieren**.</span><span class="sxs-lookup"><span data-stu-id="7b91a-104">To access the wizard from the [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)], on the **Model** menu, click **Import from Data Source**.</span></span>  
  
 <span data-ttu-id="7b91a-105">Der entsprechende Anbieter muss auf dem Computer installiert sein, um eine Verbindung mit einer Datenquelle herzustellen.</span><span class="sxs-lookup"><span data-stu-id="7b91a-105">To connect to a data source, you must have the appropriate provider installed on your machine.</span></span> <span data-ttu-id="7b91a-106">Außerdem muss der entsprechende Anbieter auf dem Arbeitsbereichsdatenbankserver installiert sein.</span><span class="sxs-lookup"><span data-stu-id="7b91a-106">You must also have the appropriate provider installed on the workspace database server.</span></span> <span data-ttu-id="7b91a-107">Für 32-Bit (x86)-Server müssen 32-Bit-Anbieter installiert sein.</span><span class="sxs-lookup"><span data-stu-id="7b91a-107">For 32-bit (x86) servers, 32-bit providers must be installed.</span></span> <span data-ttu-id="7b91a-108">Für 64-Bit (x64)-Server müssen 64-Bit-Anbieter installiert sein.</span><span class="sxs-lookup"><span data-stu-id="7b91a-108">For 64-bit (x64) servers, 64-bit providers must be installed.</span></span>  
  
 [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] <span data-ttu-id="7b91a-109">wird unabhängig von der Architektur immer in einem 32-Bit-Prozess ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7b91a-109">always runs in a 32-bit process, regardless of architecture.</span></span> <span data-ttu-id="7b91a-110">Wenn [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] auf einem 64-Bit-Computer ausgeführt wird, sollten Sie beim Installieren von Datenanbietern Folgendes beachten:</span><span class="sxs-lookup"><span data-stu-id="7b91a-110">When running [!INCLUDE[ssBIDevStudio](../includes/ssbidevstudio-md.md)] on a 64-bit machine, you should be aware of the following when installing data providers:</span></span>  
  
-   <span data-ttu-id="7b91a-111">Für Anbieter, die die parallele Installation von 32-Bit- und 64-Bit-Anbietern unterstützen, sollten Sie beide Anbieter installieren.</span><span class="sxs-lookup"><span data-stu-id="7b91a-111">For providers that support side-by-side installation of 32-bit and 64-bit providers, you should install both providers.</span></span>  
  
-   <span data-ttu-id="7b91a-112">Für den ACE-Anbieter müssen Sie die 64-Bit-Version des Anbieters installieren.</span><span class="sxs-lookup"><span data-stu-id="7b91a-112">For the ACE provider, you must install the 64-bit version of the provider.</span></span> <span data-ttu-id="7b91a-113">Da Office den ACE-Anbieter automatisch installiert, sollten Sie keine 32-Bit-Version von Microsoft Office auf einem 64-Bit-Computer ausführen, der den Arbeitsbereichsdatenbankserver hostet.</span><span class="sxs-lookup"><span data-stu-id="7b91a-113">Because Office automatically installs the ACE provider, you should not run a 32-bit version of Microsoft Office on a 64-bit machine hosting the workspace database server.</span></span>  
  
     <span data-ttu-id="7b91a-114">Der ACE-Anbieter wird zum Importieren aus Text-, Excel- und Access-Dateien verwendet.</span><span class="sxs-lookup"><span data-stu-id="7b91a-114">The ACE provider is used to import from Text, Excel, and Access files.</span></span> <span data-ttu-id="7b91a-115">Wenn die Unterstützung für diese Datenquellen nicht erforderlich ist, können Sie eine 32-Bit-Version von Microsoft Office auf einem Computer mit einem 64-Bit-Arbeitsbereichsdatenbankserver ausführen.</span><span class="sxs-lookup"><span data-stu-id="7b91a-115">If support for these data sources is not needed, you can then run a 32-bit version of Microsoft Office on a machine running a 64-bit workspace database server.</span></span>  
  
-   <span data-ttu-id="7b91a-116">Für andere Anbieter, die keine parallele Installation von 32-Bit- und 64-Bit-Anbietern unterstützen, müssen Sie den 32-Bit-Anbieter installieren.</span><span class="sxs-lookup"><span data-stu-id="7b91a-116">For other providers that do not support side-by-side installation of 32-bit and 64-bit providers, you must install the 32-bit provider.</span></span> <span data-ttu-id="7b91a-117">Wenn nur 64-Bit-Computer verfügbar sind, müssen Sie einen Remotecomputer mit einem als Arbeitsbereichsdatenbankserver installierten 64-Bit-Anbieter verwenden.</span><span class="sxs-lookup"><span data-stu-id="7b91a-117">If only 64-bit machines are available, you must use a remote machine with a 64-bit provider installed as the workspace database server.</span></span>  
  
  
