---
title: Anzeigen der CDC-Instanzeigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 4bce9b82-7bbd-41df-b3f4-4b40b8bad474
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 86fa298b0e02a16ddbaea220ef7f3d9f6172bf85
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87701510"
---
# <a name="how-to-view-the-cdc-instance-properties"></a><span data-ttu-id="fdfd9-102">Anzeigen der CDC-Instanzeigenschaften</span><span class="sxs-lookup"><span data-stu-id="fdfd9-102">How to View the CDC Instance Properties</span></span>
  <span data-ttu-id="fdfd9-103">In diesem Verfahren wird beschrieben, wie Sie die CDC Designer Console zum Anzeigen von Informationen zu den Instanzen verwenden, die Sie im Rahmen der Verwaltung des Betriebs der Instanzen erstellen.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-103">This procedure describes how to use the CDC Designer Console to view information about the instances that you create to help manage the operation of the instances.</span></span>  
  
### <a name="to-view-information-about-a-specific-instance"></a><span data-ttu-id="fdfd9-104">So zeigen Sie Informationen zu einer bestimmten Instanz an</span><span class="sxs-lookup"><span data-stu-id="fdfd9-104">To view information about a specific instance</span></span>  
  
1.  <span data-ttu-id="fdfd9-105">Wählen Sie im Menü **Start** die Option **CDC Designer Console**aus.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="fdfd9-106">Erweitern Sie im linken Bereich die Option **Change Data Capture** , und erweitern Sie dann den Dienst, der die anzuzeigende Instanz enthält.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance you want to view.</span></span>  
  
3.  <span data-ttu-id="fdfd9-107">Wählen Sie den Namen einer Instanz aus, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-107">Select the name of an instance you want to work with.</span></span>  
  
     <span data-ttu-id="fdfd9-108">Die Informationen zur Instanz werden im mittleren Teil der CDC Designer Console angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-108">The information about the instance is displayed in the center part of the CDC Designer Console.</span></span> <span data-ttu-id="fdfd9-109">Er ist in vier Registerkarten unterteilt.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-109">It is divided into four tabs.</span></span> <span data-ttu-id="fdfd9-110">Alle Registerkarten sind schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-110">All of the tabs are read only.</span></span>  
  
     <span data-ttu-id="fdfd9-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="fdfd9-111">**Status**</span></span>  
     <span data-ttu-id="fdfd9-112">Auf dieser Registerkarte werden die Informationen zum aktuellen Change Data Capture-Status für die Instanz angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-112">This tab displays the information about the current status of the change data capture for the instance.</span></span> <span data-ttu-id="fdfd9-113">Informationen zur Anzeige auf dieser Registerkarte finden Sie im Abschnitt **Viewer-Registerkarten** unter [Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="fdfd9-113">For information about what is displayed in this tab, see the **Viewer Tabs** section in [Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
     <span data-ttu-id="fdfd9-114">**Oracle**</span><span class="sxs-lookup"><span data-stu-id="fdfd9-114">**Oracle**</span></span>  
     <span data-ttu-id="fdfd9-115">Auf dieser Registerkarte werden allgemeine Informationen zur CDC-Instanz und zur Oracle-Quelldatenbank angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-115">This tab displays general information about the CDC instance and the Oracle source database.</span></span> <span data-ttu-id="fdfd9-116">Informationen zur Anzeige auf dieser Registerkarte finden Sie unter [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fdfd9-116">For information about what is displayed in this tab, see [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span></span>  
  
     <span data-ttu-id="fdfd9-117">**Tabellen**</span><span class="sxs-lookup"><span data-stu-id="fdfd9-117">**Tables**</span></span>  
     <span data-ttu-id="fdfd9-118">Auf dieser Registerkarte werden Informationen zu den Tabellen angezeigt, die Teil des Change Data Capture-Vorgangs sind.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-118">This tab displays information about the tables included in the change data capture.</span></span> <span data-ttu-id="fdfd9-119">Außerdem werden die Spalten aufgeführt, die aufgezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-119">It also lists the columns that are captured.</span></span> <span data-ttu-id="fdfd9-120">Informationen zur Anzeige auf dieser Registerkarte finden Sie unter [Edit Tables](edit-tables.md).</span><span class="sxs-lookup"><span data-stu-id="fdfd9-120">For information about what is displayed in this tab, see [Edit Tables](edit-tables.md).</span></span>  
  
     <span data-ttu-id="fdfd9-121">**Erweitert**</span><span class="sxs-lookup"><span data-stu-id="fdfd9-121">**Advanced**</span></span>  
     <span data-ttu-id="fdfd9-122">Auf dieser Registerkarte wird eine Liste mit den erweiterten Eigenschaften angezeigt, die Sie im Eigenschaften-Editor definieren.</span><span class="sxs-lookup"><span data-stu-id="fdfd9-122">This tab displays a list of advanced properties that you define in the properties editor.</span></span> <span data-ttu-id="fdfd9-123">Informationen zur Anzeige auf dieser Registerkarte finden Sie unter [Edit the Advanced Properties](edit-the-advanced-properties.md).</span><span class="sxs-lookup"><span data-stu-id="fdfd9-123">For information about what is displayed in this tab, see [Edit the Advanced Properties](edit-the-advanced-properties.md).</span></span>  
  
  
