---
title: Transformations-Editor für das Kopieren von Spalten Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.copymaptransformation.f1
helpviewer_keywords:
- Copy Column Transformation Editor
ms.assetid: d8e70541-d563-4ce4-bf66-bc888a0d3026
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7647d25891b37e5f09356d427072e84b45882e4c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87618836"
---
# <a name="copy-column-transformation-editor"></a><span data-ttu-id="0a843-102">Transformations-Editor für das Kopieren von Spalten</span><span class="sxs-lookup"><span data-stu-id="0a843-102">Copy Column Transformation Editor</span></span>
  <span data-ttu-id="0a843-103">Über das Dialogfeld **Transformations-Editor für das Kopieren von Spalten** können Sie zu kopierende Spalten auswählen und den neuen Ausgabespalten Namen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="0a843-103">Use the **Copy Column Transformation Editor** dialog box to select columns to copy and to assign names for the new output columns.</span></span>  
  
 <span data-ttu-id="0a843-104">Weitere Informationen zur Transformation für das Kopieren von Spalten finden Sie unter [Copy Column Transformation](data-flow/transformations/copy-column-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="0a843-104">To learn more about the Copy Column transformation, see [Copy Column Transformation](data-flow/transformations/copy-column-transformation.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0a843-105">Wenn Sie einfach alle Quelldaten in ein Ziel kopieren, ist die Verwendung der Transformation für das Kopieren von Spalten möglicherweise nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="0a843-105">When you are simply copying all of your source data to a destination, it may not be necessary to use the Copy Column transformation.</span></span> <span data-ttu-id="0a843-106">In einigen Szenarien können Sie eine Quelle direkt mit einem Ziel verbinden, wenn keine Datentransformation erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0a843-106">In some scenarios, you can connect a source directly to a destination, when no data transformation is required.</span></span> <span data-ttu-id="0a843-107">In solchen Fällen ist zum Erstellen des Pakets häufig die Verwendung des SQL Server-Import/Export-Assistenten zu bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="0a843-107">In these circumstances it is often preferable to use the SQL Server Import and Export Wizard to create your package for you.</span></span> <span data-ttu-id="0a843-108">Sie können das Paket je nach Bedarf zu einem späteren Zeitpunkt erweitern und neu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0a843-108">Later you can enhance and reconfigure the package as needed.</span></span> <span data-ttu-id="0a843-109">Weitere Informationen finden Sie unter [SQL Server Import and Export Wizard](import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span><span class="sxs-lookup"><span data-stu-id="0a843-109">For more information, see [SQL Server Import and Export Wizard](import-export-data/import-and-export-data-with-the-sql-server-import-and-export-wizard.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="0a843-110">Tastatur</span><span class="sxs-lookup"><span data-stu-id="0a843-110">Options</span></span>  
 <span data-ttu-id="0a843-111">**Verfügbare Eingabespalten**</span><span class="sxs-lookup"><span data-stu-id="0a843-111">**Available Input Columns**</span></span>  
 <span data-ttu-id="0a843-112">Wählen Sie mithilfe der Kontrollkästchen die zu kopierenden Spalten aus.</span><span class="sxs-lookup"><span data-stu-id="0a843-112">Select columns to copy by using the check boxes.</span></span> <span data-ttu-id="0a843-113">Durch Ihre Auswahl werden der nachfolgenden Tabelle Eingabespalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0a843-113">Your selections add input columns to the table below.</span></span>  
  
 <span data-ttu-id="0a843-114">**Eingabespalte**</span><span class="sxs-lookup"><span data-stu-id="0a843-114">**Input Column**</span></span>  
 <span data-ttu-id="0a843-115">Wählen Sie zu kopierende Spalten aus der Liste der verfügbaren Eingabespalten aus.</span><span class="sxs-lookup"><span data-stu-id="0a843-115">Select columns to copy from the list of available input columns.</span></span> <span data-ttu-id="0a843-116">Ihre Auswahl wird entsprechend in der Auswahl der Kontrollkästchen in der **Verfügbare Eingabespalten** -Tabelle deutlich.</span><span class="sxs-lookup"><span data-stu-id="0a843-116">Your selections are reflected in the check box selections in the **Available Input Columns** table.</span></span>  
  
 <span data-ttu-id="0a843-117">**Ausgabealias**</span><span class="sxs-lookup"><span data-stu-id="0a843-117">**Output Alias**</span></span>  
 <span data-ttu-id="0a843-118">Geben Sie einen Alias für jede neue Ausgabespalte ein.</span><span class="sxs-lookup"><span data-stu-id="0a843-118">Type an alias for each new output column.</span></span> <span data-ttu-id="0a843-119">Der Standard lautet **Kopie von**, gefolgt von dem Namen der Eingabespalte. Sie können jedoch auch einen eindeutigen, beschreibenden Namen auswählen.</span><span class="sxs-lookup"><span data-stu-id="0a843-119">The default is **Copy of**, followed by the name of the input column; however, you can choose any unique, descriptive name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a843-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0a843-120">See Also</span></span>  
 [<span data-ttu-id="0a843-121">Fehler- und Meldungsreferenz von Integration Services</span><span class="sxs-lookup"><span data-stu-id="0a843-121">Integration Services Error and Message Reference</span></span>](../../2014/integration-services/integration-services-error-and-message-reference.md)  
  
  
