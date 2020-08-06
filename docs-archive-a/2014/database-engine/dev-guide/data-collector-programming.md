---
title: Programmierung von Datensammlern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: reference
helpviewer_keywords:
- data collector [SQL Server], programming
ms.assetid: 53b4752b-055d-4716-b2bc-75b4cce84101
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 9f4da839f25da8f8aab3e21fa98547eff72d2140
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726221"
---
# <a name="data-collector-programming"></a><span data-ttu-id="69fb3-102">Programmieren mit dem Datensammler</span><span class="sxs-lookup"><span data-stu-id="69fb3-102">Data Collector Programming</span></span>
  <span data-ttu-id="69fb3-103">Die Datensammler-API in <xref:Microsoft.SqlServer.Management.Collector> lässt eine programmgesteuerte Steuerung aller Konfigurationsvorgänge durch das Objektmodell zu.</span><span class="sxs-lookup"><span data-stu-id="69fb3-103">The data collector API, in <xref:Microsoft.SqlServer.Management.Collector>, allows programmatic control of all configuration operations through the object model.</span></span> <span data-ttu-id="69fb3-104">Außerdem sind zahlreiche der Datensammlungsvorgänge, die die API verwenden, als auf dem Server gespeicherte Prozeduren implementiert.</span><span class="sxs-lookup"><span data-stu-id="69fb3-104">In addition, many of the data collection operations that use the API are implemented as stored procedures that are installed on the server.</span></span>

 <span data-ttu-id="69fb3-105">Die folgende Abbildung zeigt Schlüsselelemente des Datensammler-Objektmodells.</span><span class="sxs-lookup"><span data-stu-id="69fb3-105">The following illustration shows key elements of the data collector object model.</span></span>

 <span data-ttu-id="69fb3-106">![Objektmodell für den Datensammler](../../../2014/database-engine/dev-guide/media/dc-objectmodel.gif "Objektmodell für den Datensammler")</span><span class="sxs-lookup"><span data-stu-id="69fb3-106">![The Data Collector Object Model](../../../2014/database-engine/dev-guide/media/dc-objectmodel.gif "The Data Collector Object Model")</span></span>


