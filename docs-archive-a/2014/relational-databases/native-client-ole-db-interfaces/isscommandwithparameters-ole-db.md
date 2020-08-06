---
title: ISSCommandWithParameters (OLE DB) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
api_name:
- ISSCommandWithParameters (OLE DB)
topic_type:
- apiref
helpviewer_keywords:
- ISSCommandWithParameters interface
ms.assetid: 3419b7f3-36a3-4863-816e-e641e4e90496
author: rothja
ms.author: jroth
ms.openlocfilehash: 295026497a97b4ce13d1a1a68de48079809390ad
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616038"
---
# <a name="isscommandwithparameters-ole-db"></a><span data-ttu-id="1c380-102">ISSCommandWithParameters (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="1c380-102">ISSCommandWithParameters (OLE DB)</span></span>
  <span data-ttu-id="1c380-103">**ISSCommandWithParameters** stellt Unterstützung für [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -XML- und benutzerdefinierte Typen (UDT) zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1c380-103">**ISSCommandWithParameters** exposes support for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] XML and user-defined types (UDT).</span></span> <span data-ttu-id="1c380-104">Hierbei handelt es sich um eine optionale Schnittstelle, die von der OLE DB-Kernschnittstelle **ICommandWithParameters**erbt.</span><span class="sxs-lookup"><span data-stu-id="1c380-104">This is an optional interface that inherits from the core OLE DB interface **ICommandWithParameters**.</span></span> <span data-ttu-id="1c380-105">Zusätzlich zu den drei von **ICommandWithParameters**geerbten Methoden **GetParameterInfo**, **MapParameterNames**und **SetParameterInfo**stellt **ISSCommandWithParameters** zur Verarbeitung serverspezifischer Datentypen zwei neue Methoden bereit.</span><span class="sxs-lookup"><span data-stu-id="1c380-105">In addition to the three methods inherited from **ICommandWithParameters**; **GetParameterInfo**, **MapParameterNames**, and **SetParameterInfo**; **ISSCommandWithParameters** provides two new methods that are used to handle server specific data types.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1c380-106"> Die **ISSCommandWithParameters** -Schnittstelle kann bei Einsatz von Dienstkomponenten verwendet werden. Die Dienstkomponenten selbst verwenden diese Schnittstelle jedoch nicht.</span><span class="sxs-lookup"><span data-stu-id="1c380-106">The **ISSCommandWithParameters** interface can be used when Service Components are used, but the Service Components themselves will not use this interface.</span></span>  
  
|<span data-ttu-id="1c380-107">Methode</span><span class="sxs-lookup"><span data-stu-id="1c380-107">Method</span></span>|<span data-ttu-id="1c380-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1c380-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="1c380-109">ISSCommandWithParameters::GetParameterProperties &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1c380-109">ISSCommandWithParameters::GetParameterProperties &#40;OLE DB&#41;</span></span>](isscommandwithparameters-getparameterproperties-ole-db.md)|<span data-ttu-id="1c380-110">Gibt eine **SSPARAMPROPS** -Eigenschaftssatzstruktur im Array für jeden UDT- oder XML-Parameter zurück, der dem Befehl übergeben wurde. Für andere Parametertypen wird hingegen keine Struktur zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="1c380-110">Returns one **SSPARAMPROPS** property set structure in the array for each UDT or XML parameter passed to the command, but none is returned for other types of parameters.</span></span>|  
|[<span data-ttu-id="1c380-111">ISSCommandWithParameters::SetParameterProperties &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="1c380-111">ISSCommandWithParameters::SetParameterProperties &#40;OLE DB&#41;</span></span>](isscommandwithparameters-setparameterproperties-ole-db.md)|<span data-ttu-id="1c380-112">Legt die Parameter Eigenschaften für einen Parameter auf Grundlage der Ordnungszahl fest oder legt Massen Parameter Eigenschaften durch Angabe eines Arrays von **ssparamproperties** -Strukturen fest.</span><span class="sxs-lookup"><span data-stu-id="1c380-112">Sets the parameter properties on a per parameter basis by ordinal, or sets bulk parameter properties by specifying an array of **SSPARAMPROPS** structures.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1c380-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1c380-113">See Also</span></span>  
 <span data-ttu-id="1c380-114">[Schnittstellen &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="1c380-114">[Interfaces &#40;OLE DB&#41;](../../database-engine/dev-guide/interfaces-ole-db.md) </span></span>  
 <span data-ttu-id="1c380-115">[Verwenden von XML-Datentypen](../native-client/features/using-xml-data-types.md) </span><span class="sxs-lookup"><span data-stu-id="1c380-115">[Using XML Data Types](../native-client/features/using-xml-data-types.md) </span></span>  
 [<span data-ttu-id="1c380-116">Verwenden von benutzerdefinierten Typen</span><span class="sxs-lookup"><span data-stu-id="1c380-116">Using User-Defined Types</span></span>](../native-client/features/using-user-defined-types.md)  
  
  
