---
title: Anwenden von Datenqualitätsregeln auf eine Datenquelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: a965e8f2-004d-4ccc-8523-a185b35b26e2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: d59e6fb5ffb752b3346d40740e0b841bf574344e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695877"
---
# <a name="apply-data-quality-rules-to-data-source"></a><span data-ttu-id="eae4c-102">Anwenden von Datenqualitätsregeln auf eine Datenquelle</span><span class="sxs-lookup"><span data-stu-id="eae4c-102">Apply Data Quality Rules to Data Source</span></span>
  <span data-ttu-id="eae4c-103">Sie können mit Data Quality Services (DQS) Daten im Paketdatenfluss korrigieren, indem Sie eine Verbindung zwischen der DQS-Bereinigungstransformation und der Datenquelle herstellen.</span><span class="sxs-lookup"><span data-stu-id="eae4c-103">You can use Data Quality Services (DQS) to correct data in the package data flow by connecting the DQS Cleansing transformation to the data source.</span></span> <span data-ttu-id="eae4c-104">Weitere Informationen zu DQS finden Sie unter [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="eae4c-104">For more information about DQS, see [Data Quality Services Concepts](../../../data-quality-services/data-quality-services-concepts.md).</span></span> <span data-ttu-id="eae4c-105">Weitere Informationen zu der Transformation finden Sie unter [DQS Cleansing Transformation](dqs-cleansing-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="eae4c-105">For more information about the transformation, see [DQS Cleansing Transformation](dqs-cleansing-transformation.md).</span></span>  
  
 <span data-ttu-id="eae4c-106">Wenn Sie Daten mit der DQS-Bereinigungstransformation verarbeiten, wird ein Data Quality-Projekt auf dem Data Quality-Server erstellt.</span><span class="sxs-lookup"><span data-stu-id="eae4c-106">When you process data with the DQS Cleansing transformation, a data quality project is created on the Data Quality Server.</span></span> <span data-ttu-id="eae4c-107">Das Projekt wird mit dem Data Quality Client verwaltet.</span><span class="sxs-lookup"><span data-stu-id="eae4c-107">You use the Data Quality Client to manage the project.</span></span> <span data-ttu-id="eae4c-108">Weitere Informationen finden Sie unter [Verwalten von Data Quality-Projekten &#40;Öffnen, Entsperren, Umbenennen, Löschen&#41;](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md).</span><span class="sxs-lookup"><span data-stu-id="eae4c-108">For more information, see [Manage &#40;Open, Unlock, Rename, and Delete&#41; a Data Quality Project](../../../data-quality-services/manage-open-unlock-rename-and-delete-a-data-quality-project.md).</span></span>  
  
### <a name="to-correct-data-in-the-data-flow"></a><span data-ttu-id="eae4c-109">So korrigieren Sie Daten im Datenfluss</span><span class="sxs-lookup"><span data-stu-id="eae4c-109">To correct data in the data flow</span></span>  
  
1.  <span data-ttu-id="eae4c-110">Erstellen eines Pakets.</span><span class="sxs-lookup"><span data-stu-id="eae4c-110">Create a package.</span></span>  
  
2.  <span data-ttu-id="eae4c-111">Fügen Sie die DQS-Bereinigungstransformation hinzu, und konfigurieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="eae4c-111">Add and configure the DQS Cleansing transformation.</span></span> <span data-ttu-id="eae4c-112">Weitere Informationen finden Sie unter [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span><span class="sxs-lookup"><span data-stu-id="eae4c-112">For more information, see [DQS Cleansing Transformation Editor Dialog Box](../../dqs-cleansing-transformation-editor-dialog-box.md).</span></span>  
  
3.  <span data-ttu-id="eae4c-113">Verbinden Sie die DQS-Bereinigungstransformation mit einer Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="eae4c-113">Connect the DQS Cleansing transformation to a data source.</span></span>  
  
  
