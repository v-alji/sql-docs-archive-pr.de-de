---
title: Länge von voll Text Katalog-Namen, die auf 120 Zeichen beschränkt sind | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
helpviewer_keywords:
- full-text catalogs names
ms.assetid: 50633373-83f6-4ed9-99b9-71f92479a14f
author: mashamsft
ms.author: mathoma
ms.openlocfilehash: fa9b06fa6fe4acd79782c19a8814357721e59c24
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87630490"
---
# <a name="length-of-full-text-catalog-names-restricted-to-120-characters"></a><span data-ttu-id="0858f-102">Länge von Volltextkatalognamen auf 120 Zeichen beschränkt</span><span class="sxs-lookup"><span data-stu-id="0858f-102">Length of full-text catalog names restricted to 120 characters</span></span>
  <span data-ttu-id="0858f-103">Die Länge der Volltextkatalognamen ist auf 120 Zeichen beschränkt. In früheren Versionen von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] lag die Beschränkung bei 128 Zeichen.</span><span class="sxs-lookup"><span data-stu-id="0858f-103">The length of full-text catalog names is restricted to 120 characters, reduced from the 128 character restriction in previous releases of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
## <a name="description"></a><span data-ttu-id="0858f-104">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="0858f-104">Description</span></span>  
 <span data-ttu-id="0858f-105">Diese Änderung betrifft bestehende Katalognamen nicht. Skripts, die Volltextkatalognamen erstellen, die länger als 120 Zeichen sind, führen zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="0858f-105">This change does not affect existing catalog names; however, scripts that create full-text catalogs with names longer than 120 characters result in an error.</span></span> <span data-ttu-id="0858f-106">Die Katalognamen werden dazu verwendet, logische Dateinamen zu generieren, die Katalogen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0858f-106">The catalog names are used to generate logical file names that correspond to catalogs.</span></span>  
  
## <a name="corrective-action"></a><span data-ttu-id="0858f-107">Korrekturmaßnahme</span><span class="sxs-lookup"><span data-stu-id="0858f-107">Corrective Action</span></span>  
 <span data-ttu-id="0858f-108">Ändern Sie alle Skripts, die Volltextkataloge erstellen, um sicherzustellen, dass die Katalognamen maximal 120 Zeichen umfassen.</span><span class="sxs-lookup"><span data-stu-id="0858f-108">Modify all scripts that create full-text catalogs to ensure that they restrict catalog names to 120 characters.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0858f-109">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0858f-109">See Also</span></span>  
 [<span data-ttu-id="0858f-110">Arbeiten mit dem Upgrade Advisor</span><span class="sxs-lookup"><span data-stu-id="0858f-110">Working with Upgrade Advisor</span></span>](../../../2014/sql-server/install/working-with-upgrade-advisor.md)  
  
  
