---
title: Informationen zu OLE DB-Eigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, properties
- SQL Server Native Client OLE DB provider, properties
- properties [OLE DB]
- property values [SQL Server Native Client]
ms.assetid: 0b36a61e-b542-400d-a3d2-e6f643caf2c6
author: rothja
ms.author: jroth
ms.openlocfilehash: d4eb80ab9c0ab90da11d8580e9a2983455b676bb
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87698132"
---
# <a name="about-ole-db-properties"></a><span data-ttu-id="e7765-102">Informationen zu OLE DB-Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="e7765-102">About OLE DB Properties</span></span>
  <span data-ttu-id="e7765-103">Consumer legen Eigenschaftswerte fest, um ein bestimmtes Objektverhalten anzufordern.</span><span class="sxs-lookup"><span data-stu-id="e7765-103">Consumers set property values to request specific object behavior.</span></span> <span data-ttu-id="e7765-104">Zum Beispiel verwenden Consumer Eigenschaften, um die Schnittstellen anzugeben, die von einem Rowset verfügbar gemacht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e7765-104">For example, consumers use properties to specify the interfaces to be exposed by a rowset.</span></span> <span data-ttu-id="e7765-105">Consumer rufen die Eigenschaftswerte ab, um die Fähigkeiten eines Objekts zu ermitteln, beispielsweise eines Rowsets, einer Sitzung oder eines Datenquellenobjekts.</span><span class="sxs-lookup"><span data-stu-id="e7765-105">Consumers get the property values to determine the capabilities of an object, such as a rowset, a session, or a data source object.</span></span>  
  
 <span data-ttu-id="e7765-106">Jede Eigenschaft verfügt über einen Wert, einen Typ, eine Beschreibung, ein Lese-/Schreibattribut. Rowset-Eigenschaften besitzen überdies einen Indikator, der angibt, ob die Eigenschaft auf einzelne Spalten des Rowsets angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="e7765-106">Each property has a value, type, description, and read/write attribute, and for rowset properties, an indicator of whether it can be applied on a column-by-column basis.</span></span>  
  
 <span data-ttu-id="e7765-107">Eine Eigenschaft wird durch eine GUID und eine ganze Zahl, welche die Eigenschaften-ID darstellt, identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e7765-107">A property is identified by a GUID and an integer representing the property ID.</span></span> <span data-ttu-id="e7765-108">Ein Eigenschaftensatz ist ein Satz aller Eigenschaften, die über die gleiche GUID verfügen.</span><span class="sxs-lookup"><span data-stu-id="e7765-108">A property set is a set of all properties that share the same GUID.</span></span> <span data-ttu-id="e7765-109">Zusätzlich zu den vordefinierten OLE DB-Eigenschafts Sätzen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] implementiert der Native Client OLE DB-Anbieter anbieterspezifische Eigenschaften Sätze und Eigenschaften darin.</span><span class="sxs-lookup"><span data-stu-id="e7765-109">In addition to the predefined OLE DB property sets, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider implements provider-specific property sets and properties in them.</span></span> <span data-ttu-id="e7765-110">Jede Eigenschaft gehört zu einer oder mehreren Eigenschaftengruppen.</span><span class="sxs-lookup"><span data-stu-id="e7765-110">Each property belongs to one or more property groups.</span></span> <span data-ttu-id="e7765-111">Eine Eigenschaftengruppe ist die Gruppe aller Eigenschaften, die für ein bestimmtes Objekt gelten.</span><span class="sxs-lookup"><span data-stu-id="e7765-111">A property group is the group of all properties that apply to a particular object.</span></span> <span data-ttu-id="e7765-112">Beispiele für Eigenschaftengruppen sind die Initialisierungseigenschaftengruppe, die Datenquellen-Eigenschaftengruppe, die Sitzungseigenschaftengruppe, die Rowseteigenschaftengruppe, die Tabelleneigenschaftengruppe und die Spalteneigenschaftengruppe.</span><span class="sxs-lookup"><span data-stu-id="e7765-112">Some property groups include the initialization property group, data source property group, session property group, rowset property group, table property group, and column property group.</span></span> <span data-ttu-id="e7765-113">Jede dieser Eigenschaftengruppen enthält Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e7765-113">There are properties in each of these property groups.</span></span>  
  
 <span data-ttu-id="e7765-114">Das Festlegen von Eigenschaftswerten beinhaltet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e7765-114">Setting property values involves:</span></span>  
  
1.  <span data-ttu-id="e7765-115">Bestimmen der Eigenschaften, deren Werte festgelegt werden sollen</span><span class="sxs-lookup"><span data-stu-id="e7765-115">Determining the properties for which to set values.</span></span>  
  
2.  <span data-ttu-id="e7765-116">Bestimmen der Eigenschaftensätze, die die identifizierten Eigenschaften enthalten</span><span class="sxs-lookup"><span data-stu-id="e7765-116">Determining the property sets that contain the identified properties.</span></span>  
  
3.  <span data-ttu-id="e7765-117">Zuordnen eines Arrays von DBPROPSET-Strukturen, wobei für jeden identifizierten Eigenschaftensatz eine Struktur angegeben werden muss</span><span class="sxs-lookup"><span data-stu-id="e7765-117">Allocating an array of DBPROPSET structures, one for each identified property set.</span></span>  
  
4.  <span data-ttu-id="e7765-118">Zuordnen eines Arrays von DBPROP-Strukturen, wobei für jeden Eigenschaftensatz eine Struktur angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="e7765-118">Allocating an array of DBPROP structures for each property set.</span></span> <span data-ttu-id="e7765-119">Die Anzahl der Elemente in jedem Array entspricht der Anzahl der Eigenschaften (die in Schritt 1 identifiziert wurden), die zu diesem Eigenschaftensatz gehören.</span><span class="sxs-lookup"><span data-stu-id="e7765-119">The number of elements in each array is the number of properties (identified in Step 1) that belong to that property set.</span></span>  
  
5.  <span data-ttu-id="e7765-120">Füllen der DBPROP-Struktur für jede Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="e7765-120">Filling in the DBPROP structure for each property.</span></span>  
  
6.  <span data-ttu-id="e7765-121">Eintragen der Daten (Eigenschaftensatz-GUID, Zähler für die Anzahl der Elemente und ein Zeiger auf das zugehörige DBPROP-Array) in die DBPROPSET-Struktur für jeden Eigenschaftensatz</span><span class="sxs-lookup"><span data-stu-id="e7765-121">Filling in information (property set GUID, count of number of elements, and a pointer to the corresponding DBPROP array) in the DBPROPSET structure for each property set.</span></span>  
  
7.  <span data-ttu-id="e7765-122">Aufrufen einer Methode, um Eigenschaften festzulegen und die Anzahl und das Array von DBPROPSET-Strukturen zu übergeben</span><span class="sxs-lookup"><span data-stu-id="e7765-122">Calling a method to set properties and passing the count and the array of DBPROPSET structures.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7765-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7765-123">See Also</span></span>  
 <span data-ttu-id="e7765-124">[Erstellen einer SQL Server Native Client OLE DB-Anbieter Anwendung](creating-a-sql-server-native-client-ole-db-provider-application.md) </span><span class="sxs-lookup"><span data-stu-id="e7765-124">[Creating a SQL Server Native Client OLE DB Provider Application](creating-a-sql-server-native-client-ole-db-provider-application.md) </span></span>  
 [<span data-ttu-id="e7765-125">Eigenschaften (OLE DB)</span><span class="sxs-lookup"><span data-stu-id="e7765-125">Properties (OLE DB)</span></span>](https://go.microsoft.com/fwlink/?LinkId=112207)  
  
  
