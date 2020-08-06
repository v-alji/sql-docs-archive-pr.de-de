---
title: Festlegen oder Ändern der bevorzugten Verbindungsmethode für directquery | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
ms.assetid: f10d5678-d678-4251-8cce-4e30cfe15751
author: minewiskan
ms.author: owend
ms.openlocfilehash: 239c80ace0daa3498c8dafd8fea358ce540931d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721833"
---
# <a name="set-or-change-the-preferred-connection-method-for-directquery"></a><span data-ttu-id="248f6-102">Festlegen oder Ändern der bevorzugten Verbindungsmethode für DirectQuery</span><span class="sxs-lookup"><span data-stu-id="248f6-102">Set or Change the Preferred Connection Method for DirectQuery</span></span>
  <span data-ttu-id="248f6-103">Wenn Sie ein Modell für die Verwendung im DirectQuery-Modus erstellen, müssen Sie zuerst die Entwurfsumgebung konfigurieren, um die Verwendung von DirectQuery zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="248f6-103">When you create a model for use in DirectQuery mode, you must first configure the design environment to support use of DirectQuery.</span></span> <span data-ttu-id="248f6-104">Informationen hierzu finden Sie unter [enable directquery Design Mode &#40;SSAS tabellarischer&#41;](tabular-models/enable-directquery-mode-in-ssdt.md).</span><span class="sxs-lookup"><span data-stu-id="248f6-104">To do this, see [Enable DirectQuery Design Mode &#40;SSAS Tabular&#41;](tabular-models/enable-directquery-mode-in-ssdt.md).</span></span>  
  
 <span data-ttu-id="248f6-105">Wenn Sie zur Bereitstellung des Modells bereit sind, müssen Sie einige zusätzliche Eigenschaften festlegen, um Benutzern den Zugriff auf das Modell mit einem der DirectQuery-Modi zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="248f6-105">When you are ready to deploy the model, you must set some additional properties to enable users to access your model using one of the DirectQuery modes:</span></span>  
  
-   <span data-ttu-id="248f6-106">Sie müssen angeben, ob in Abfragen für das Modell zwischengespeicherte Daten oder die relationale Datenquelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="248f6-106">You must indicate whether queries against the model should use cached data or the relational data source.</span></span> <span data-ttu-id="248f6-107">Sie können nur einen Hybridmodus oder DirectQuery verwenden.</span><span class="sxs-lookup"><span data-stu-id="248f6-107">You can use a hybrid mode or DirectQuery only.</span></span>  
  
-   <span data-ttu-id="248f6-108">Wenn Sie Partitionen verwenden, müssen Sie angeben, welche Partition als DirectQuery-Datenquelle verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="248f6-108">If you are using partitions, you must indicate which partition to use as the DirectQuery data source.</span></span>  
  
-   <span data-ttu-id="248f6-109">Sie müssen Identitätswechseloptionen für Benutzer festlegen, die auf die SQL Server-Datenquelle zugreifen.</span><span class="sxs-lookup"><span data-stu-id="248f6-109">You must set impersonation options for users who will be accessing the SQL Server data source.</span></span>  
  
 <span data-ttu-id="248f6-110">In dieser Prozedur wird beschrieben, wie die bevorzugte Verbindungsmethode für ein DirectQuery-Modell im Designer festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="248f6-110">This procedure describes how to set the preferred connection method for a DirectQuery model in the designer.</span></span> <span data-ttu-id="248f6-111">Zudem wird geschildert, wie die Eigenschaft in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] nach der Bereitstellung des Modells geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="248f6-111">It also describes how you can change this property in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] after the model has been deployed.</span></span>  
  
### <a name="to-set-the-preferred-connection-method-for-a-directquery-model"></a><span data-ttu-id="248f6-112">So legen Sie die bevorzugte Verbindungsmethode für ein DirectQuery-Modell fest</span><span class="sxs-lookup"><span data-stu-id="248f6-112">To set the preferred connection method for a DirectQuery model</span></span>  
  
1.  <span data-ttu-id="248f6-113">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)]die Lösungsdatei für das DirectQuery-Modell.</span><span class="sxs-lookup"><span data-stu-id="248f6-113">In [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)], open the solution file for the DirectQuery model.</span></span>  
  
2.  <span data-ttu-id="248f6-114">Wählen Sie in Visual Studio im Menü **Projekt** die Option **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="248f6-114">In Visual Studio, from the **Project** menu, select **Properties**.</span></span>  
  
3.  <span data-ttu-id="248f6-115">Ändern Sie im Bereich **Eigenschaften** die Eigenschaft **DirectQueryMode**in einen der Werte, die DirectQuery-Verwendung unterstützen:</span><span class="sxs-lookup"><span data-stu-id="248f6-115">In the **Properties** pane, change the property, **DirectQueryMode**, to one of the values that support DirectQuery usage:</span></span>  
  
    -   <span data-ttu-id="248f6-116">**InMemory mit DirectQuery**: Wenn Sie diese Option verwenden, wird das Modell bereitgestellt, doch Sie müssen den Cache verarbeiten, bevor Sie Abfragen des Modell ausführen können.</span><span class="sxs-lookup"><span data-stu-id="248f6-116">**InMemory with DirectQuery**: If you use this option, the model is deployed but you must process the cache before you can run queries against the model.</span></span>  
  
    -   <span data-ttu-id="248f6-117">**DirectQuery mit InMemory**: Wenn Sie diese Option verwenden, ist der Cache zur Verwendung durch Clients verfügbar, wenn er bereits verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="248f6-117">**DirectQuery with InMemory**: If you use this option, the cache will be available for use by clients if it has already been processed.</span></span> <span data-ttu-id="248f6-118">Wenn Sie das Modell mit dieser Einstellung bereitstellen und den Cache nicht verarbeiten, müssen einige Clients eine Fehlermeldung erhalten, wenn sie versuchen, eine Verbindung mit dem Modell herzustellen.</span><span class="sxs-lookup"><span data-stu-id="248f6-118">If you deploy the model with this setting and do not process the cache, some clients must get an error on trying to connect to the model.</span></span>  
  
    -   <span data-ttu-id="248f6-119">**Nur DirectQuery**: Wenn Sie diese Option verwenden, werden die Metadaten bereitgestellt, doch das Modell enthält keine Daten.</span><span class="sxs-lookup"><span data-stu-id="248f6-119">**DirectQuery only**: If you use this option, the metadata is deployed but the model has no data in it.</span></span> <span data-ttu-id="248f6-120">Clients, die versuchen, mit dem Modus "Im Arbeitsspeicher" eine Verbindung herzustellen, erhalten eine Fehlermeldung wegen eines nicht vorhandenen Modells oder der fehlenden Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="248f6-120">Clients that attempt to connect using In-Memory mode will get an error, indicating that the model does not exist or has not been processed.</span></span>  
  
4.  <span data-ttu-id="248f6-121">Wenn Fehler vorhanden sind, öffnen Sie in Visual Studio die **Fehlerliste** , und beheben Sie alle Probleme, durch die verhindert werden würde, dass das Modell im DirectQuery-Modus bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="248f6-121">If there are errors, in Visual Studio, open the **Error List** and resolve any problems that would prevent the model from being deployed in DirectQuery mode.</span></span>  
  
### <a name="to-verify-or-change-the-preferred-connection-method-for-a-directquery-model"></a><span data-ttu-id="248f6-122">So überprüfen oder ändern Sie die bevorzugte Verbindungsmethode für ein DirectQuery-Modell</span><span class="sxs-lookup"><span data-stu-id="248f6-122">To verify or change the preferred connection method for a DirectQuery model</span></span>  
  
1.  <span data-ttu-id="248f6-123">Stellen Sie in [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]eine Verbindung mit der Instanz her, wo Sie das DirectQuery-Modell bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="248f6-123">In [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], connect to the instance where you deployed the DirectQuery model.</span></span>  
  
2.  <span data-ttu-id="248f6-124">Klicken Sie mit der rechten Maustaste auf die Modelldatenbank, und wählen Sie **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="248f6-124">Right-click the model database, and select **Properties**.</span></span>  
  
3.  <span data-ttu-id="248f6-125">Ändern Sie im Bereich **Eigenschaften** die Eigenschaft **DirectQueryMode**in einen der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="248f6-125">In the **Properties** pane, change the property, **DirectQueryMode**, to one of these values:</span></span>  
  
    -   <span data-ttu-id="248f6-126">**Nur directquery**</span><span class="sxs-lookup"><span data-stu-id="248f6-126">**DirectQuery Only**</span></span>  
  
    -   <span data-ttu-id="248f6-127">**InMemory mit DirectQuery**</span><span class="sxs-lookup"><span data-stu-id="248f6-127">**InMemory with DirectQuery**</span></span>  
  
    -   <span data-ttu-id="248f6-128">**Directquery mit inMemory**</span><span class="sxs-lookup"><span data-stu-id="248f6-128">**DirectQuery with InMemory**</span></span>  
  
 <span data-ttu-id="248f6-129">Diese Eigenschaften sind mit den Eigenschaften identisch, die für das Projekt vor der Bereitstellung in Visual Studio festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="248f6-129">Note that these properties are the same as the properties that you set on the project before deployment in Visual Studio.</span></span> <span data-ttu-id="248f6-130">Sie können den bevorzugten Verbindungsmodus für den DirectQuery-Modus jederzeit ändern, vorausgesetzt, dass Sie das Modell für die Unterstützung von DirectQuery-Verwendung konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="248f6-130">You can change the preferred connection mode for DirectQuery mode at any time, provided that you have configured the model to support DirectQuery usage.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="248f6-131">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="248f6-131">See Also</span></span>  
 <span data-ttu-id="248f6-132">[Directquery-Modus &#40;tabellarischen SSAS-&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="248f6-132">[DirectQuery Mode &#40;SSAS Tabular&#41;](tabular-models/directquery-mode-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="248f6-133">Aktivieren des directquery-Entwurfs Modus &#40;tabellarischen SSAS-&#41;</span><span class="sxs-lookup"><span data-stu-id="248f6-133">Enable DirectQuery Design Mode &#40;SSAS Tabular&#41;</span></span>](tabular-models/enable-directquery-mode-in-ssdt.md)  
  
  
