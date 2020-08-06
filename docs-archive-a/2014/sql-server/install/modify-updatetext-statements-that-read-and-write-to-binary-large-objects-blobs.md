---
title: Ändern von UPDATETEXT-Anweisungen, die in binäre große Objekte (BLOB) lesen und schreiben | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- UPDATETEXT statement
- text [SQL Server], UPDATETEXT statements
ms.assetid: b85da6a7-42f6-4707-a25e-3ded8958b94f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: 061e7bad0bae5a74d103406265ad79195f79f7db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617470"
---
# <a name="modify-updatetext-statements-that-read-and-write-to-binary-large-objects-blobs"></a><span data-ttu-id="53c90-102">Ändern der UPDATETEXT-Anweisungen, die BLOBs (Binary Large Objects) lesen bzw. in BLOBs schreiben</span><span class="sxs-lookup"><span data-stu-id="53c90-102">Modify UPDATETEXT statements that read and write to binary large objects (BLOBs)</span></span>
  <span data-ttu-id="53c90-103">Der Upgrade Advisor hat UPDATETEXT-Anweisungen erkannt, die mithilfe des gleichen Textzeigers die gleichen BLOB-Daten (Binary Large Object) lesen bzw. in die gleichen BLOB-Daten schreiben.</span><span class="sxs-lookup"><span data-stu-id="53c90-103">Upgrade Advisor detected UPDATETEXT statements that read and write to the same binary large objects (BLOB) by using the same text pointer.</span></span> <span data-ttu-id="53c90-104">Von [!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] wird die Verwendung von Textzeigern auf diese Weise nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="53c90-104">[!INCLUDE[ssCurrent](../../includes/sscurrent-md.md)] does not support the use of text pointers in this manner.</span></span>  
  
## <a name="component"></a><span data-ttu-id="53c90-105">Komponente</span><span class="sxs-lookup"><span data-stu-id="53c90-105">Component</span></span>  
 [!INCLUDE[ssDE](../../includes/ssde-md.md)]  
  
## <a name="corrective-action"></a><span data-ttu-id="53c90-106">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="53c90-106">Corrective Action</span></span>  
 <span data-ttu-id="53c90-107">Kopieren Sie das BLOB in eine temporäre Tabelle oder eine Tabellenvariable, und weisen Sie den Wert dann erneut der ursprünglichen Spalte zu.</span><span class="sxs-lookup"><span data-stu-id="53c90-107">Copy the BLOB to a temporary table or to a table variable, and then assign the value back to the original column.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53c90-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53c90-108">See Also</span></span>  
 <span data-ttu-id="53c90-109">[Datenbank-Engine Upgradeprobleme](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span><span class="sxs-lookup"><span data-stu-id="53c90-109">[Database Engine Upgrade Issues](../../../2014/sql-server/install/database-engine-upgrade-issues.md) </span></span>  
 [<span data-ttu-id="53c90-110">SQL Server 2014 Upgrade Advisor &#91;neuen&#93;</span><span class="sxs-lookup"><span data-stu-id="53c90-110">SQL Server 2014 Upgrade Advisor &#91;new&#93;</span></span>](sql-server-2014-upgrade-advisor.md)  
  
  
