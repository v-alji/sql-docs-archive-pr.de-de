---
title: Dimensionstabelle und Schlüssel auswählen (Assistent für langsam veränderliche Dimensionen) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.loaddimwizard.selecttableandkeys.f1
ms.assetid: 01e0495f-de35-4607-ba19-0539e801e8fd
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 671c66a8a5d5f1f4f5201fd8c9ecc144540d8b68
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87727081"
---
# <a name="select-a-dimension-table-and-keys-slowly-changing-dimension-wizard"></a><span data-ttu-id="4c185-102">Dimensionstabelle und Schlüssel auswählen (Assistent für langsam veränderliche Dimensionen)</span><span class="sxs-lookup"><span data-stu-id="4c185-102">Select a Dimension Table and Keys (Slowly Changing Dimension Wizard)</span></span>
  <span data-ttu-id="4c185-103">Mithilfe der Seite **Dimensionstabelle und Schlüssel auswählen** können Sie eine zu ladende Dimensionstabelle auswählen.</span><span class="sxs-lookup"><span data-stu-id="4c185-103">Use the **Select a Dimension Table and Keys** page to select a dimension table to load.</span></span> <span data-ttu-id="4c185-104">Spalten aus dem Datenfluss werden den zu ladenden Spalten zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="4c185-104">Map columns from the data flow to the columns that will be loaded.</span></span>  
  
 <span data-ttu-id="4c185-105">Weitere Informationen zu diesem Assistenten finden Sie unter [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="4c185-105">To learn more about this wizard, see [Slowly Changing Dimension Transformation](slowly-changing-dimension-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="4c185-106">Tastatur</span><span class="sxs-lookup"><span data-stu-id="4c185-106">Options</span></span>  
 <span data-ttu-id="4c185-107">**Connection manager**</span><span class="sxs-lookup"><span data-stu-id="4c185-107">**Connection manager**</span></span>  
 <span data-ttu-id="4c185-108">Wählen Sie in der Liste einen vorhandenen OLE DB-Verbindungs-Manager aus, oder erstellen Sie einen neuen OLE DB-Verbindungs-Manager, indem Sie auf **Neu** klicken.</span><span class="sxs-lookup"><span data-stu-id="4c185-108">Select an existing OLE DB connection manager from the list, or click **New** to create an OLE DB connection manager.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="4c185-109">Der Assistent für langsam veränderliche Dimensionen unterstützt nur OLE DB-Verbindungs-Manager und Verbindungen mit [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="4c185-109">The Slowly Changing Dimension Wizard only supports OLE DB connection managers, and only supports connections to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="4c185-110">**Neu**</span><span class="sxs-lookup"><span data-stu-id="4c185-110">**New**</span></span>  
 <span data-ttu-id="4c185-111">Verwenden Sie das Dialogfeld **OLE DB-Verbindungs-Manager konfigurieren** , um einen vorhandenen Verbindungs-Manager auszuwählen, oder klicken Sie auf **Neu** , um eine neue OLE DB-Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="4c185-111">Use the **Configure OLE DB Connection Manager** dialog box to select an existing connection manager, or click **New** to create a new OLE DB connection.</span></span>  
  
 <span data-ttu-id="4c185-112">**Tabelle oder Sicht**</span><span class="sxs-lookup"><span data-stu-id="4c185-112">**Table or View**</span></span>  
 <span data-ttu-id="4c185-113">Wählen Sie eine Tabelle oder eine Sicht aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="4c185-113">Select a table or view from the list.</span></span>  
  
 <span data-ttu-id="4c185-114">**Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="4c185-114">**Input Columns**</span></span>  
 <span data-ttu-id="4c185-115">Wählen Sie aus der Liste der Eingabespalten aus, für die Sie Zuordnungen angeben können.</span><span class="sxs-lookup"><span data-stu-id="4c185-115">Select from the list of input columns for which you may specify mapping.</span></span>  
  
 <span data-ttu-id="4c185-116">**Dimensionsspalten**</span><span class="sxs-lookup"><span data-stu-id="4c185-116">**Dimension Columns**</span></span>  
 <span data-ttu-id="4c185-117">Zeigen Sie alle verfügbaren Dimensionsspalten an.</span><span class="sxs-lookup"><span data-stu-id="4c185-117">View all available dimension columns.</span></span>  
  
 <span data-ttu-id="4c185-118">**Schlüsseltyp**</span><span class="sxs-lookup"><span data-stu-id="4c185-118">**Key Type**</span></span>  
 <span data-ttu-id="4c185-119">Wählen Sie eine der Dimensionsspalten aus, die als Geschäftsschlüssel verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="4c185-119">Select one of the dimension columns to be the business key.</span></span> <span data-ttu-id="4c185-120">Sie müssen über einen Geschäftsschlüssel verfügen.</span><span class="sxs-lookup"><span data-stu-id="4c185-120">You must have one business key.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c185-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4c185-121">See Also</span></span>  
 [<span data-ttu-id="4c185-122">Konfiguration von Ausgaben mithilfe des Assistenten für langsam veränderliche Dimensionen</span><span class="sxs-lookup"><span data-stu-id="4c185-122">Configure Outputs Using the Slowly Changing Dimension Wizard</span></span>](configure-outputs-using-the-slowly-changing-dimension-wizard.md)  
  
  
