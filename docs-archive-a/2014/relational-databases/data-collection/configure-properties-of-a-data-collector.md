---
title: Konfigurieren der Eigenschaften eines Datensammlers | Microsoft Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: supportability
ms.topic: conceptual
f1_keywords:
- sql12.swb.dc.datacollectionprop.advanced.f1
- sql12.swb.dc.datacollectionprop.general.f1
ms.assetid: cf98f57d-5a6d-4bc3-bf10-783e460fc63d
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 05172c2c831ec649269512a625be069cdc67047a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87718250"
---
# <a name="configure-properties-of-a-data-collector"></a><span data-ttu-id="12b09-102">Konfigurieren der Eigenschaften eines Datensammlers</span><span class="sxs-lookup"><span data-stu-id="12b09-102">Configure Properties of a Data Collector</span></span>
  <span data-ttu-id="12b09-103">In diesem Thema wird erläutert, wie Sie die Eigenschaften eines Datensammlers konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="12b09-103">This topic discusses how you can configure the properties of a data collector.</span></span>  
  
## <a name="data-collection-properties-general-tab"></a><span data-ttu-id="12b09-104">Datensammlungseigenschaften (Registerkarte 'Allgemein')</span><span class="sxs-lookup"><span data-stu-id="12b09-104">Data Collection Properties (General Tab)</span></span>  
 <span data-ttu-id="12b09-105">Verwenden Sie diese Seite, um Einstellungen für das Verwaltungs-Data Warehouse zu konfigurieren und den Speicherort für aufgelistete Daten anzugeben, bevor diese in das Data Warehouse hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="12b09-105">Use this page to configure settings for the management data warehouse and specify where collected data should be stored before it is uploaded to the data warehouse.</span></span>  
  
 <span data-ttu-id="12b09-106">**Datensammlung aktivieren**</span><span class="sxs-lookup"><span data-stu-id="12b09-106">**Enable Data Collection**</span></span>  
 <span data-ttu-id="12b09-107">Aktivieren Sie dieses Kontrollkästchen, um die Datensammlung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="12b09-107">Select to enable data collection.</span></span> <span data-ttu-id="12b09-108">Dies hat die gleichen Auswirkungen wie das Ausführen der gespeicherten Prozedur sp_syscollector_enable_collector stored procedure.</span><span class="sxs-lookup"><span data-stu-id="12b09-108">This has the same effect as running the sp_syscollector_enable_collector stored procedure.</span></span> <span data-ttu-id="12b09-109">Wenn Sie dieses Kontrollkästchen deaktivieren, ist die Datensammlung deaktiviert. Dies hat die gleichen Auswirkungen wie das Ausführen der gespeicherten Prozedur sp_syscollector_disable_collector.</span><span class="sxs-lookup"><span data-stu-id="12b09-109">Clearing this check box disables data collection and has the same effect as running the sp_syscollector_disable_collector stored procedure.</span></span>  
  
 <span data-ttu-id="12b09-110">**Server**</span><span class="sxs-lookup"><span data-stu-id="12b09-110">**Server**</span></span>  
 <span data-ttu-id="12b09-111">Zeigt den Namen des Servers an, der als Host für das Verwaltungs-Data Warehouse fungiert.</span><span class="sxs-lookup"><span data-stu-id="12b09-111">Displays the name of the server that will host the management data warehouse</span></span>  
  
 <span data-ttu-id="12b09-112">**Datenbankname**</span><span class="sxs-lookup"><span data-stu-id="12b09-112">**Database name**</span></span>  
 <span data-ttu-id="12b09-113">Zeigt den Namen der relationalen Datenbank an, die für das Verwaltungs-Data Warehouse verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="12b09-113">Displays the name of the relational database that is used for the management data warehouse.</span></span>  
  
 <span data-ttu-id="12b09-114">**Verbindung testen**</span><span class="sxs-lookup"><span data-stu-id="12b09-114">**Test Connection**</span></span>  
 <span data-ttu-id="12b09-115">Testen Sie die Verbindung mit dem angegebenen **Server** mithilfe der Informationen, die beim Konfigurieren der Datensammlung angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="12b09-115">Test the connection to the specified **Server** using information provided when data collection is configured.</span></span>  
  
 <span data-ttu-id="12b09-116">**Cacheverzeichnis**</span><span class="sxs-lookup"><span data-stu-id="12b09-116">**Cache directory**</span></span>  
 <span data-ttu-id="12b09-117">Gibt das Verzeichnis an, in dem die aufgelisteten Daten auf dem die Daten auflistenden System gespeichert werden, bevor sie in das Verwaltungs-Data Warehouse hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="12b09-117">Specifies the directory where collected data is stored on the system collecting the data before it is uploaded to the management data warehouse.</span></span> <span data-ttu-id="12b09-118">Wenn kein **Cacheverzeichnis** angegeben ist, sucht der Datensammler nach den Umgebungsvariablen %TEMP% und %TMP% und verwendet einen dieser Speicherorte als Standardspeicherort für die temporäre Speicherung.</span><span class="sxs-lookup"><span data-stu-id="12b09-118">If **Cache directory** is not specified, the data collector attempts to locate the %TEMP% and %TMP% environment variables and use one these locations as the default location for temporary storage.</span></span> <span data-ttu-id="12b09-119">Wenn diese Umgebungsvariablen nicht konfiguriert sind, tritt ein Fehler auf, und Sie werden aufgefordert, ein Cacheverzeichnis zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="12b09-119">If these environment variables are not configured, an error occurs and you are prompted to create a cache directory.</span></span>  
  
## <a name="data-collection-properties-advanced-tab"></a><span data-ttu-id="12b09-120">Datensammlungseigenschaften (Registerkarte 'Erweitert')</span><span class="sxs-lookup"><span data-stu-id="12b09-120">Data Collection Properties (Advanced Tab)</span></span>  
 <span data-ttu-id="12b09-121">Verwenden Sie diese Seite, um die Einstellungen für Wiederholungsversuche für die Verbindung mit dem Verwaltungs-Data Warehouse zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="12b09-121">Use this page to configure the retry settings for the connection to the management data warehouse.</span></span>  
  
 <span data-ttu-id="12b09-122">**Anzahl der Wiederholungsversuche im Falle eines Fehlers beim Hochladen**</span><span class="sxs-lookup"><span data-stu-id="12b09-122">**Number of times to retry if upload fails**</span></span>  
 <span data-ttu-id="12b09-123">Gibt an, wie häufig im Fall eines Fehlers erneut versucht wird, Daten in das Verwaltungs-Data Warehouse hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="12b09-123">Specifies the number of times to retry an upload to the management data warehouse if an upload fails.</span></span> <span data-ttu-id="12b09-124">Der Standardwert ist 1.</span><span class="sxs-lookup"><span data-stu-id="12b09-124">The default is 1.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12b09-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="12b09-125">See Also</span></span>  
 <span data-ttu-id="12b09-126">[Verwalten von Datensammlungen](data-collection.md) </span><span class="sxs-lookup"><span data-stu-id="12b09-126">[Manage Data Collection](data-collection.md) </span></span>  
 [<span data-ttu-id="12b09-127">Konfigurieren des Verwaltungs-Data Warehouses &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="12b09-127">Configure the Management Data Warehouse &#40;SQL Server Management Studio&#41;</span></span>](configure-the-management-data-warehouse-sql-server-management-studio.md)  
  
  
