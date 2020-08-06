---
title: Benutzerdefinierte Eigenschaften des DataReader-Ziels | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: f151c3e8-3811-457d-a3d3-6158ca65a646
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 62b6f628614d533e1bebcce071ce4761e73e08f7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618819"
---
# <a name="datareader-destination-custom-properties"></a><span data-ttu-id="750e6-102">Benutzerdefinierte Eigenschaften des DataReader-Ziels</span><span class="sxs-lookup"><span data-stu-id="750e6-102">DataReader Destination Custom Properties</span></span>
  <span data-ttu-id="750e6-103">Das DataReader-Ziel verfügt sowohl über benutzerdefinierte Eigenschaften als auch über die Eigenschaften, die allen Datenflusskomponenten gemeinsam sind.</span><span class="sxs-lookup"><span data-stu-id="750e6-103">The DataReader destination has both custom properties and the properties common to all data flow components.</span></span>  
  
 <span data-ttu-id="750e6-104">Die folgende Tabelle beschreibt die benutzerdefinierten Eigenschaften des DataReader-Ziels.</span><span class="sxs-lookup"><span data-stu-id="750e6-104">The following table describes the custom properties of the DataReader destination.</span></span> <span data-ttu-id="750e6-105">Alle Eigenschaften außer `DataReader` weisen Lese-/Schreibzugriff auf.</span><span class="sxs-lookup"><span data-stu-id="750e6-105">All properties except for `DataReader` are read/write.</span></span>  
  
|<span data-ttu-id="750e6-106">Eigenschaftenname</span><span class="sxs-lookup"><span data-stu-id="750e6-106">Property name</span></span>|<span data-ttu-id="750e6-107">Datentyp</span><span class="sxs-lookup"><span data-stu-id="750e6-107">Data Type</span></span>|<span data-ttu-id="750e6-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="750e6-108">Description</span></span>|  
|-------------------|---------------|-----------------|  
|<span data-ttu-id="750e6-109">DataReader</span><span class="sxs-lookup"><span data-stu-id="750e6-109">DataReader</span></span>|<span data-ttu-id="750e6-110">String</span><span class="sxs-lookup"><span data-stu-id="750e6-110">String</span></span>|<span data-ttu-id="750e6-111">Der Klassenname des DataReader-Ziels.</span><span class="sxs-lookup"><span data-stu-id="750e6-111">The class name of the DataReader destination.</span></span>|  
|<span data-ttu-id="750e6-112">FailOnTimeout</span><span class="sxs-lookup"><span data-stu-id="750e6-112">FailOnTimeout</span></span>|<span data-ttu-id="750e6-113">Boolean</span><span class="sxs-lookup"><span data-stu-id="750e6-113">Boolean</span></span>|<span data-ttu-id="750e6-114">Gibt an, ob ein Fehler ausgegeben wird, wenn ein `ReadTimeout` auftritt.</span><span class="sxs-lookup"><span data-stu-id="750e6-114">Indicates whether to fail when a `ReadTimeout` occurs.</span></span> <span data-ttu-id="750e6-115">Der Standardwert dieser Eigenschaft ist **False**.</span><span class="sxs-lookup"><span data-stu-id="750e6-115">The default value of this property is **False**.</span></span>|  
|<span data-ttu-id="750e6-116">ReadTimeout</span><span class="sxs-lookup"><span data-stu-id="750e6-116">ReadTimeout</span></span>|<span data-ttu-id="750e6-117">Integer</span><span class="sxs-lookup"><span data-stu-id="750e6-117">Integer</span></span>|<span data-ttu-id="750e6-118">Die Anzahl von Millisekunden, bevor ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="750e6-118">The number of milliseconds before a time-out occurs.</span></span> <span data-ttu-id="750e6-119">Der Standardwert dieser Eigenschaft beträgt 30000 (30 Sekunden).</span><span class="sxs-lookup"><span data-stu-id="750e6-119">The default value of this property is 30000 (30 seconds).</span></span>|  
  
 <span data-ttu-id="750e6-120">Die Eingabe und die Eingabespalten des DataReader-Ziels verfügen nicht über benutzerdefinierte Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="750e6-120">The input and the input columns of the DataReader destination have no custom properties.</span></span>  
  
 <span data-ttu-id="750e6-121">Weitere Informationen finden Sie unter [DataReader Destination](datareader-destination.md).</span><span class="sxs-lookup"><span data-stu-id="750e6-121">For more information, see [DataReader Destination](datareader-destination.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="750e6-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="750e6-122">See Also</span></span>  
 [<span data-ttu-id="750e6-123">Common Properties</span><span class="sxs-lookup"><span data-stu-id="750e6-123">Common Properties</span></span>](../common-properties.md)  
  
  
