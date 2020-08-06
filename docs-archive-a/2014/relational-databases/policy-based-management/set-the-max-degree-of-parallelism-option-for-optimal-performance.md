---
title: Festlegen der 'Max. Grad an Parallelität'-Option auf optimale Leistung | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: ec908006-67ae-4674-9a61-25ea741d6197
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 3043a656cbe1ac1ec40f0d0a67b6eac057005af4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724529"
---
# <a name="set-the-max-degree-of-parallelism-option-for-optimal-performance"></a><span data-ttu-id="0bca2-102">Festlegen der 'Max. Grad an Parallelität'-Option auf optimale Leistung</span><span class="sxs-lookup"><span data-stu-id="0bca2-102">Set the Max Degree of Parallelism Option for Optimal Performance</span></span>
  <span data-ttu-id="0bca2-103">Diese Regel bestimmt, ob die Max. Grad an Parallelität-Option (MAXDOP) einen Wert größer als 8 hat.</span><span class="sxs-lookup"><span data-stu-id="0bca2-103">This rule determines whether the max degree of parallelism (MAXDOP) option for a value greater than 8.</span></span> <span data-ttu-id="0bca2-104">Wird diese Option auf einen größeren Wert festgelegt, führt dies häufig zu unerwünschtem Ressourcenverbrauch und zu Leistungseinbußen.</span><span class="sxs-lookup"><span data-stu-id="0bca2-104">Setting this option to a larger value often causes unwanted resource consumption and performance degradation.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="0bca2-105">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="0bca2-105">Best Practices Recommendations</span></span>  
 <span data-ttu-id="0bca2-106">Legen Sie die Max. Grad an Parallelität-Option mit sp_configure auf einen Wert von 8 oder weniger fest.</span><span class="sxs-lookup"><span data-stu-id="0bca2-106">Set the max degree of parallelism option to 8 or less by using sp_configure.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="0bca2-107">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0bca2-107">For More Information</span></span>  
 [<span data-ttu-id="0bca2-108">Microsoft Knowledge Base-Artikel 329204</span><span class="sxs-lookup"><span data-stu-id="0bca2-108">Microsoft Knowledge Base article 329204</span></span>](https://go.microsoft.com/fwlink/?linkid=117786)  
  
 [<span data-ttu-id="0bca2-109">Konfigurieren der Serverkonfigurationsoption Max. Grad an Parallelität</span><span class="sxs-lookup"><span data-stu-id="0bca2-109">Configure the max degree of parallelism Server Configuration Option</span></span>](../../database-engine/configure-windows/configure-the-max-degree-of-parallelism-server-configuration-option.md)  
  
 [<span data-ttu-id="0bca2-110">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="0bca2-110">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
  
