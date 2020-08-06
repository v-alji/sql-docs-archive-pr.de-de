---
title: Festlegen der PAGE_VERIFY-Datenbankoption auf CHECKSUM | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- Best Practices [Database Engine]
ms.assetid: 686b9a4a-ea61-4263-9ab8-f444a3077679
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 13296a976722390668b8ca6d901cf0dd080e5cc3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724517"
---
# <a name="set-the-page_verify-database-option-to-checksum"></a><span data-ttu-id="ed6d5-102">Festlegen der PAGE_VERIFY-Datenbankoption auf CHECKSUM</span><span class="sxs-lookup"><span data-stu-id="ed6d5-102">Set the PAGE_VERIFY Database Option to CHECKSUM</span></span>
  <span data-ttu-id="ed6d5-103">Diese Regel überprüft, ob die PAGE_VERIFY-Datenbankoption auf CHECKSUM festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="ed6d5-103">This rule checks whether PAGE_VERIFY database option is set to CHECKSUM.</span></span> <span data-ttu-id="ed6d5-104">Wenn CHECKSUM für die PAGE_VERIFY-Datenbankoption angegeben wird, berechnet [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] beim Schreiben der Seite auf den Datenträger eine Prüfsumme des Inhalts der gesamten Seite und speichert den Wert im Seitenkopf.</span><span class="sxs-lookup"><span data-stu-id="ed6d5-104">When CHECKSUM is enabled for the PAGE_VERIFY database option, the [!INCLUDE[ssDEnoversion](../../includes/ssdenoversion-md.md)] calculates a checksum over the contents of the whole page, and stores the value in the page header when a page is written to disk.</span></span> <span data-ttu-id="ed6d5-105">Wenn die Seite vom Datenträger gelesen wird, wird die Prüfsumme erneut berechnet und mit dem im Seitenkopf gespeicherten Prüfsummenwert verglichen.</span><span class="sxs-lookup"><span data-stu-id="ed6d5-105">When the page is read from disk, the checksum is recomputed and compared to the checksum value that is stored in the page header.</span></span> <span data-ttu-id="ed6d5-106">Dadurch wird ein hohes Maß an Integrität der Datendateien bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ed6d5-106">This helps provide a high level of data-file integrity.</span></span>  
  
## <a name="best-practices-recommendations"></a><span data-ttu-id="ed6d5-107">Empfehlungen zu Best Practices</span><span class="sxs-lookup"><span data-stu-id="ed6d5-107">Best Practices Recommendations</span></span>  
 <span data-ttu-id="ed6d5-108">Legen Sie die PAGE_VERIFY-Datenbankoption auf CHECKSUM fest.</span><span class="sxs-lookup"><span data-stu-id="ed6d5-108">Set the PAGE_VERIFY database option to CHECKSUM.</span></span>  
  
## <a name="for-more-information"></a><span data-ttu-id="ed6d5-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ed6d5-109">For More Information</span></span>  
 [<span data-ttu-id="ed6d5-110">ALTER DATABASE SET-Optionen &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="ed6d5-110">ALTER DATABASE SET Options &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql-set-options)  
  
  
