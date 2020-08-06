---
title: Erstellen von SQL Server-Indizes | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- CreateIndex function
- constraints [OLE DB]
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
- adding indexes
ms.assetid: 6239d440-2818-4b98-bb79-732dced41952
author: rothja
ms.author: jroth
ms.openlocfilehash: 3693355eec7a290c03658c10db500161aa52062d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723753"
---
# <a name="creating-sql-server-indexes"></a><span data-ttu-id="e3ce8-102">Erstellen von SQL Server-Indizes</span><span class="sxs-lookup"><span data-stu-id="e3ce8-102">Creating SQL Server Indexes</span></span>
  <span data-ttu-id="e3ce8-103">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter macht die **IIndexDefinition:: | ateindex** -Funktion verfügbar und ermöglicht es Consumern, neue Indizes für Tabellen zu definieren [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="e3ce8-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition::CreateIndex** function, allowing consumers to define new indexes on [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables.</span></span>  
  
 <span data-ttu-id="e3ce8-104">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter erstellt Tabellenindizes entweder als Indizes oder als Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-104">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider creates table indexes as either indexes or constraints.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e3ce8-105">gewährt dem Tabellenbesitzer, Datenbankbesitzer und Mitgliedern bestimmter Administratorrollen die Berechtigung zum Erstellen von Einschränkungen.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-105">gives constraint-creation privilege to the table owner, database owner, and members of certain administrative roles.</span></span> <span data-ttu-id="e3ce8-106">Standardmäßig kann nur der Tabellenbesitzer einen Index für eine Tabelle erstellen.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-106">By default, only the table owner can create an index on a table.</span></span> <span data-ttu-id="e3ce8-107">Aus diesem Grund hängt es nicht nur von den Zugriffsrechten des Anwendungsbenutzers, sondern auch von der Art des erstellten Indexes ab, ob **CreateIndex** erfolgreich verläuft oder fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-107">Therefore, the success or failure of **CreateIndex** depends not only on the application user's access rights but also on the type of index created.</span></span>  
  
 <span data-ttu-id="e3ce8-108">Consumer geben den Tabellennamen als Unicode-Zeichenfolge in das *pwszName*-Element der *uName*-Vereinigung des *pTableID*-Parameters ein.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-108">Consumers specify the table name as a Unicode character string in the *pwszName* member of the *uName* union in the *pTableID* parameter.</span></span> <span data-ttu-id="e3ce8-109">Das *eKind*-Element von *pTableID* muss DBKIND_NAME sein.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-109">The *eKind* member of *pTableID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="e3ce8-110">Der *pIndexID* -Parameter kann NULL sein, und wenn dies der Fall ist, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] erstellt der Native Client OLE DB-Anbieter einen eindeutigen Namen für den Index.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-110">The *pIndexID* parameter can be NULL, and if it is, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider creates a unique name for the index.</span></span> <span data-ttu-id="e3ce8-111">Der Consumer kann den Namen des Indexes aufzeichnen, indem er einen gültigen Zeiger auf eine DBID im Parameter *ppIndexID* angibt.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-111">The consumer can capture the name of the index by specifying a valid pointer to a DBID in the *ppIndexID* parameter.</span></span>  
  
 <span data-ttu-id="e3ce8-112">Der Consumer kann den Indexnamen als Unicode-Zeichenfolge in das Element *pwszName* der Vereinigung *uName* des Parameters *pIndexID* eingeben.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-112">The consumer can specify the index name as a Unicode character string in the *pwszName* member of the *uName* union of the *pIndexID* parameter.</span></span> <span data-ttu-id="e3ce8-113">Das *eKind*-Element von *pIndexID* muss DBKIND_NAME sein.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-113">The *eKind* member of *pIndexID* must be DBKIND_NAME.</span></span>  
  
 <span data-ttu-id="e3ce8-114">Der Consumer gibt die Spalte oder die Spalten an, die namentlich in den Index einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-114">The consumer specifies the column or columns participating in the index by name.</span></span> <span data-ttu-id="e3ce8-115">Für jede DBINDEXCOLUMNDESC-Struktur, die in **CreateIndex** verwendet wird, muss das Element *eKind* der *pColumnID* DBKIND_NAME sein.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-115">For each DBINDEXCOLUMNDESC structure used in **CreateIndex**, the *eKind* member of the *pColumnID* must be DBKIND_NAME.</span></span> <span data-ttu-id="e3ce8-116">Der Name der Spalte wird als Unicode-Zeichenfolge in das Element *pwszName* der Vereinigung *uName* des Parameters *pColumnID* eingegeben.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-116">The name of the column is specified as a Unicode character string in the *pwszName* member of the *uName* union in the *pColumnID*.</span></span>  
  
 <span data-ttu-id="e3ce8-117">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter und [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] unterstützen aufsteigende Reihenfolge bei Werten im Index.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-117">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support ascending order on values in the index.</span></span> <span data-ttu-id="e3ce8-118">Der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter gibt E_INVALIDARG zurück, wenn der Consumer DBINDEX_COL_ORDER_DESC in einer beliebigen DBINDEXCOLUMNDESC-Struktur angibt.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-118">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider returns E_INVALIDARG if the consumer specifies DBINDEX_COL_ORDER_DESC in any DBINDEXCOLUMNDESC structure.</span></span>  
  
 <span data-ttu-id="e3ce8-119">**CreateIndex** interpretiert Indexeigenschaften wie folgt.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-119">**CreateIndex** interprets index properties as follows.</span></span>  
  
|<span data-ttu-id="e3ce8-120">Eigenschafts-ID</span><span class="sxs-lookup"><span data-stu-id="e3ce8-120">Property ID</span></span>|<span data-ttu-id="e3ce8-121">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e3ce8-121">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="e3ce8-122">DBPROP_INDEX_AUTOUPDATE</span><span class="sxs-lookup"><span data-stu-id="e3ce8-122">DBPROP_INDEX_AUTOUPDATE</span></span>|<span data-ttu-id="e3ce8-123">R/W: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="e3ce8-123">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="e3ce8-124">Standardwert: Keiner</span><span class="sxs-lookup"><span data-stu-id="e3ce8-124">Default: None</span></span><br /><br /> <span data-ttu-id="e3ce8-125">Beschreibung: der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt diese Eigenschaft nicht.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-125">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="e3ce8-126">Versuche, diese Eigenschaft in **CreateIndex** festzulegen, verursachen einen DB_S_ERRORSOCCURRED-Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-126">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="e3ce8-127">Das Element *dwStatus* der Eigenschaftsstruktur gibt DBPROPSTATUS_BADVALUE an.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-127">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="e3ce8-128">DBPROP_INDEX_CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="e3ce8-128">DBPROP_INDEX_CLUSTERED</span></span>|<span data-ttu-id="e3ce8-129">R/W: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="e3ce8-129">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="e3ce8-130">Standardwert: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="e3ce8-130">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="e3ce8-131">Beschreibung: Steuert die Indexgruppierung.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-131">Description: Controls index clustering.</span></span><br /><br /> <span data-ttu-id="e3ce8-132">VARIANT_TRUE: der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter versucht, einen gruppierten Index für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Tabelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-132">VARIANT_TRUE: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider attempts to create a clustered index on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span> [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="e3ce8-133">unterstützt maximal einen gruppierten Index pro Tabelle.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-133">supports at most one clustered index on any table.</span></span><br /><br /> <span data-ttu-id="e3ce8-134">VARIANT_FALSE: der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter versucht, einen nicht gruppierten Index für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Tabelle zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-134">VARIANT_FALSE: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider attempts to create a nonclustered index on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] table.</span></span>|  
|<span data-ttu-id="e3ce8-135">DBPROP_INDEX_FILLFACTOR</span><span class="sxs-lookup"><span data-stu-id="e3ce8-135">DBPROP_INDEX_FILLFACTOR</span></span>|<span data-ttu-id="e3ce8-136">R/W: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="e3ce8-136">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="e3ce8-137">Standard: 0</span><span class="sxs-lookup"><span data-stu-id="e3ce8-137">Default: 0</span></span><br /><br /> <span data-ttu-id="e3ce8-138">Beschreibung: Gibt den Prozentsatz einer für Speicher verwendeten Indexseite an.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-138">Description: Specifies the percentage of an index page used for storage.</span></span> <span data-ttu-id="e3ce8-139">Weitere Informationen finden Sie unter [Create Index](/sql/t-sql/statements/create-index-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="e3ce8-139">For more information, see [CREATE INDEX](/sql/t-sql/statements/create-index-transact-sql).</span></span><br /><br /> <span data-ttu-id="e3ce8-140">Der Typ der Variante ist VT_I4.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-140">The type of the variant is VT_I4.</span></span> <span data-ttu-id="e3ce8-141">Der Wert muss größer als oder gleich 1 und kleiner als oder gleich 100 sein.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-141">The value must be greater than or equal to 1 and less than or equal to 100.</span></span>|  
|<span data-ttu-id="e3ce8-142">DBPROP_INDEX_INITIALIZE</span><span class="sxs-lookup"><span data-stu-id="e3ce8-142">DBPROP_INDEX_INITIALIZE</span></span>|<span data-ttu-id="e3ce8-143">R/W: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="e3ce8-143">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="e3ce8-144">Standardwert: Keiner</span><span class="sxs-lookup"><span data-stu-id="e3ce8-144">Default: None</span></span><br /><br /> <span data-ttu-id="e3ce8-145">Beschreibung: der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt diese Eigenschaft nicht.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-145">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="e3ce8-146">Versuche, diese Eigenschaft in **CreateIndex** festzulegen, verursachen einen DB_S_ERRORSOCCURRED-Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-146">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="e3ce8-147">Das Element *dwStatus* der Eigenschaftsstruktur gibt DBPROPSTATUS_BADVALUE an.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-147">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="e3ce8-148">DBPROP_INDEX_NULLCOLLATION</span><span class="sxs-lookup"><span data-stu-id="e3ce8-148">DBPROP_INDEX_NULLCOLLATION</span></span>|<span data-ttu-id="e3ce8-149">R/W: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="e3ce8-149">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="e3ce8-150">Standardwert: Keiner</span><span class="sxs-lookup"><span data-stu-id="e3ce8-150">Default: None</span></span><br /><br /> <span data-ttu-id="e3ce8-151">Beschreibung: der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt diese Eigenschaft nicht.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-151">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="e3ce8-152">Versuche, diese Eigenschaft in **CreateIndex** festzulegen, verursachen einen DB_S_ERRORSOCCURRED-Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-152">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="e3ce8-153">Das Element *dwStatus* der Eigenschaftsstruktur gibt DBPROPSTATUS_BADVALUE an.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-153">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="e3ce8-154">DBPROP_INDEX_NULLS</span><span class="sxs-lookup"><span data-stu-id="e3ce8-154">DBPROP_INDEX_NULLS</span></span>|<span data-ttu-id="e3ce8-155">R/W: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="e3ce8-155">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="e3ce8-156">Standardwert: Keiner</span><span class="sxs-lookup"><span data-stu-id="e3ce8-156">Default: None</span></span><br /><br /> <span data-ttu-id="e3ce8-157">Beschreibung: der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt diese Eigenschaft nicht.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-157">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="e3ce8-158">Versuche, diese Eigenschaft in **CreateIndex** festzulegen, verursachen einen DB_S_ERRORSOCCURRED-Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-158">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="e3ce8-159">Das Element *dwStatus* der Eigenschaftsstruktur gibt DBPROPSTATUS_BADVALUE an.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-159">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="e3ce8-160">DBPROP_INDEX_PRIMARYKEY</span><span class="sxs-lookup"><span data-stu-id="e3ce8-160">DBPROP_INDEX_PRIMARYKEY</span></span>|<span data-ttu-id="e3ce8-161">R/W: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="e3ce8-161">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="e3ce8-162">Standard: VARIANT_FALSE Beschreibung: Erstellt den Index als PRIMARY KEY-Einschränkung mit referenzieller Integrität.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-162">Default: VARIANT_FALSE Description: Creates the index as a referential integrity, PRIMARY KEY constraint.</span></span><br /><br /> <span data-ttu-id="e3ce8-163">VARIANT_TRUE: Der Index wird erstellt, um die PRIMARY KEY-Einschränkung der Tabelle zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-163">VARIANT_TRUE: The index is created to support the PRIMARY KEY constraint of the table.</span></span> <span data-ttu-id="e3ce8-164">Die Spalten dürfen keine NULL-Werte zulassen.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-164">The columns must be nonnullable.</span></span><br /><br /> <span data-ttu-id="e3ce8-165">VARIANT_FALSE: Der Index wird nicht als PRIMARY KEY-Einschränkung für Zeilenwerte in der Tabelle verwendet.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-165">VARIANT_FALSE: The index is not used as a PRIMARY KEY constraint for row values in the table.</span></span>|  
|<span data-ttu-id="e3ce8-166">DBPROP_INDEX_SORTBOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="e3ce8-166">DBPROP_INDEX_SORTBOOKMARKS</span></span>|<span data-ttu-id="e3ce8-167">R/W: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="e3ce8-167">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="e3ce8-168">Standardwert: Keiner</span><span class="sxs-lookup"><span data-stu-id="e3ce8-168">Default: None</span></span><br /><br /> <span data-ttu-id="e3ce8-169">Beschreibung: der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt diese Eigenschaft nicht.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-169">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="e3ce8-170">Versuche, diese Eigenschaft in **CreateIndex** festzulegen, verursachen einen DB_S_ERRORSOCCURRED-Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-170">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="e3ce8-171">Das Element *dwStatus* der Eigenschaftsstruktur gibt DBPROPSTATUS_BADVALUE an.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-171">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="e3ce8-172">DBPROP_INDEX_TEMPINDEX</span><span class="sxs-lookup"><span data-stu-id="e3ce8-172">DBPROP_INDEX_TEMPINDEX</span></span>|<span data-ttu-id="e3ce8-173">R/W: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="e3ce8-173">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="e3ce8-174">Standardwert: Keiner</span><span class="sxs-lookup"><span data-stu-id="e3ce8-174">Default: None</span></span><br /><br /> <span data-ttu-id="e3ce8-175">Beschreibung: der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt diese Eigenschaft nicht.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-175">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="e3ce8-176">Versuche, diese Eigenschaft in **CreateIndex** festzulegen, verursachen einen DB_S_ERRORSOCCURRED-Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-176">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="e3ce8-177">Das Element *dwStatus* der Eigenschaftsstruktur gibt DBPROPSTATUS_BADVALUE an.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-177">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="e3ce8-178">DBPROP_INDEX_TYPE</span><span class="sxs-lookup"><span data-stu-id="e3ce8-178">DBPROP_INDEX_TYPE</span></span>|<span data-ttu-id="e3ce8-179">R/W: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="e3ce8-179">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="e3ce8-180">Standardwert: Keiner</span><span class="sxs-lookup"><span data-stu-id="e3ce8-180">Default: None</span></span><br /><br /> <span data-ttu-id="e3ce8-181">Beschreibung: der [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB-Anbieter unterstützt diese Eigenschaft nicht.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-181">Description: The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider does not support this property.</span></span> <span data-ttu-id="e3ce8-182">Versuche, diese Eigenschaft in **CreateIndex** festzulegen, verursachen einen DB_S_ERRORSOCCURRED-Rückgabewert.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-182">Attempts to set the property in **CreateIndex** cause a DB_S_ERRORSOCCURRED return value.</span></span> <span data-ttu-id="e3ce8-183">Das Element *dwStatus* der Eigenschaftsstruktur gibt DBPROPSTATUS_BADVALUE an.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-183">The *dwStatus* member of the property structure indicates DBPROPSTATUS_BADVALUE.</span></span>|  
|<span data-ttu-id="e3ce8-184">DBPROP_INDEX_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="e3ce8-184">DBPROP_INDEX_UNIQUE</span></span>|<span data-ttu-id="e3ce8-185">R/W: Lesen/Schreiben</span><span class="sxs-lookup"><span data-stu-id="e3ce8-185">R/W: Read/write</span></span><br /><br /> <span data-ttu-id="e3ce8-186">Standardwert: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="e3ce8-186">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="e3ce8-187">Beschreibung: Erstellt den Index als UNIQUE-Einschränkung für die einbezogene(n) Spalte oder Spalten.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-187">Description: Creates the index as a UNIQUE constraint on the participating column or columns.</span></span><br /><br /> <span data-ttu-id="e3ce8-188">VARIANT_TRUE: Der Index wird verwendet, um Zeilenwerte in der Tabelle eindeutig einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-188">VARIANT_TRUE: The index is used to uniquely constrain row values in the table.</span></span><br /><br /> <span data-ttu-id="e3ce8-189">VARIANT_FALSE: Der Index schränkt Zeilenwerte nicht eindeutig ein.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-189">VARIANT_FALSE: The index does not uniquely constrain row values.</span></span>|  
  
 <span data-ttu-id="e3ce8-190">Im anbieterspezifischen Eigenschaften Satz DBPROPSET_SQLSERVERINDEX [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] definiert der Native Client OLE DB-Anbieter die folgende Eigenschaft für Datenquellen Informationen.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-190">In the provider-specific property set DBPROPSET_SQLSERVERINDEX, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the following data source information property.</span></span>  
  
|<span data-ttu-id="e3ce8-191">Eigenschafts-ID</span><span class="sxs-lookup"><span data-stu-id="e3ce8-191">Property ID</span></span>|<span data-ttu-id="e3ce8-192">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="e3ce8-192">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="e3ce8-193">SSPROP_INDEX_XML</span><span class="sxs-lookup"><span data-stu-id="e3ce8-193">SSPROP_INDEX_XML</span></span>|<span data-ttu-id="e3ce8-194">Typ: VT_BOOL (R/W)</span><span class="sxs-lookup"><span data-stu-id="e3ce8-194">Type: VT_BOOL (R/W)</span></span><br /><br /> <span data-ttu-id="e3ce8-195">Standardwert: VARIANT_FALSE</span><span class="sxs-lookup"><span data-stu-id="e3ce8-195">Default: VARIANT_FALSE</span></span><br /><br /> <span data-ttu-id="e3ce8-196">Beschreibung: Wenn diese Eigenschaft mit dem Wert VARIANT_TRUE mit IIndexDefinition::CreateIndex angegeben wird, wird ein primärer XML-Index erstellt, der der zu indizierenden Spalte entspricht.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-196">Description: When this property is specified with a value of VARIANT_TRUE with IIndexDefinition::CreateIndex, it results in a primary xml index being created corresponding to the column being indexed.</span></span> <span data-ttu-id="e3ce8-197">Wenn diese Eigenschaft VARIANT_TRUE ist, sollte cIndexColumnDescs 1 sein; andernfalls tritt ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="e3ce8-197">If this property is VARIANT_TRUE, cIndexColumnDescs should be 1, otherwise it is an error.</span></span>|  
  
 <span data-ttu-id="e3ce8-198">In diesem Beispiel wird ein Primärschlüsselindex erstellt:</span><span class="sxs-lookup"><span data-stu-id="e3ce8-198">This example creates a primary key index:</span></span>  
  
```  
// This CREATE TABLE statement shows the referential integrity and   
// PRIMARY KEY constraint on the OrderDetails table that will be created   
// by the following example code.  
//  
// CREATE TABLE OrderDetails  
// (  
//    OrderID      int      NOT NULL  
//    ProductID   int      NOT NULL  
//        CONSTRAINT PK_OrderDetails  
//        PRIMARY KEY CLUSTERED (OrderID, ProductID),  
//    UnitPrice   money      NOT NULL,  
//    Quantity   int      NOT NULL,  
//    Discount   decimal(2,2)   NOT NULL  
//        DEFAULT 0  
// )  
//  
HRESULT CreatePrimaryKey  
    (  
    IIndexDefinition* pIIndexDefinition  
    )  
    {  
    HRESULT             hr = S_OK;  
  
    DBID                dbidTable;  
    DBID                dbidIndex;  
    const ULONG         nCols = 2;  
    ULONG               nCol;  
    const ULONG         nProps = 2;  
    ULONG               nProp;  
  
    DBINDEXCOLUMNDESC   dbidxcoldesc[nCols];  
    DBPROP              dbpropIndex[nProps];  
    DBPROPSET           dbpropset;  
  
    DBID*               pdbidIndexOut = NULL;  
  
    // Set up identifiers for the table and index.  
    dbidTable.eKind = DBKIND_NAME;  
    dbidTable.uName.pwszName = L"OrderDetails";  
  
    dbidIndex.eKind = DBKIND_NAME;  
    dbidIndex.uName.pwszName = L"PK_OrderDetails";  
  
    // Set up column identifiers.  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        dbidxcoldesc[nCol].pColumnID = new DBID;  
        dbidxcoldesc[nCol].pColumnID->eKind = DBKIND_NAME;  
  
        dbidxcoldesc[nCol].eIndexColOrder = DBINDEX_COL_ORDER_ASC;  
        }  
    dbidxcoldesc[0].pColumnID->uName.pwszName = L"OrderID";  
    dbidxcoldesc[1].pColumnID->uName.pwszName = L"ProductID";  
  
    // Set properties for the index. The index is clustered,  
    // PRIMARY KEY.  
    for (nProp = 0; nProp < nProps; nProp++)  
        {  
        dbpropIndex[nProp].dwOptions = DBPROPOPTIONS_REQUIRED;  
        dbpropIndex[nProp].colid = DB_NULLID;  
  
        VariantInit(&(dbpropIndex[nProp].vValue));  
  
        dbpropIndex[nProp].vValue.vt = VT_BOOL;  
        }  
    dbpropIndex[0].dwPropertyID = DBPROP_INDEX_CLUSTERED;  
    dbpropIndex[0].vValue.boolVal = VARIANT_TRUE;  
  
    dbpropIndex[1].dwPropertyID = DBPROP_INDEX_PRIMARYKEY;  
    dbpropIndex[1].vValue.boolVal = VARIANT_TRUE;  
  
    dbpropset.rgProperties = dbpropIndex;  
    dbpropset.cProperties = nProps;  
    dbpropset.guidPropertySet = DBPROPSET_INDEX;  
  
    hr = pIIndexDefinition->CreateIndex(&dbidTable, &dbidIndex, nCols,  
        dbidxcoldesc, 1, &dbpropset, &pdbidIndexOut);  
  
    // Clean up dynamically allocated DBIDs.  
    for (nCol = 0; nCol < nCols; nCol++)  
        {  
        delete dbidxcoldesc[nCol].pColumnID;  
        }  
  
    return (hr);  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="e3ce8-199">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e3ce8-199">See Also</span></span>  
 [<span data-ttu-id="e3ce8-200">Tabellen und Indizes</span><span class="sxs-lookup"><span data-stu-id="e3ce8-200">Tables and Indexes</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/tables-and-indexes.md)  
  
  
