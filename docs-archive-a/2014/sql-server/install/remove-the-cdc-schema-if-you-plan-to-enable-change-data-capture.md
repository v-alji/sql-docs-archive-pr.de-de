---
title: Entfernen Sie das CDC-Schema, wenn Sie planen, Change Data Capture zu aktivieren | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- cdc schema
- change data capture
ms.assetid: 6a84aa25-0f31-4be3-b2dd-4f249b8254ae
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: abdb33fa3d1ff022a65ed569f19d48bcf4468501
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620145"
---
# <a name="remove-the-cdc-schema-if-you-plan-to-enable-change-data-capture"></a><span data-ttu-id="eda9b-102">Entfernen Sie das CDC-Schema, wenn Sie planen, Change Data Capture zu aktivieren</span><span class="sxs-lookup"><span data-stu-id="eda9b-102">Remove the cdc schema if you plan to enable change data capture</span></span>
  <span data-ttu-id="eda9b-103">Eine Datenbank enthält bereits ein CDC-Schema.</span><span class="sxs-lookup"><span data-stu-id="eda9b-103">A database already contains a cdc schema.</span></span> <span data-ttu-id="eda9b-104">Wenn Sie nach dem Upgrade Change Data Capture aktivieren möchten, müssen Sie zuerst dieses CDC-Schema löschen.</span><span class="sxs-lookup"><span data-stu-id="eda9b-104">If you plan to enable change data capture after upgrade, you must first drop this cdc schema.</span></span> <span data-ttu-id="eda9b-105">Wenn Sie eine Datenbank für Change Data Capture aktivieren, erstellt [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] ein neues Schema mit dem Namen CDC.</span><span class="sxs-lookup"><span data-stu-id="eda9b-105">When you enable a database for change data capture, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] will create a new schema named cdc.</span></span>  
  
  
