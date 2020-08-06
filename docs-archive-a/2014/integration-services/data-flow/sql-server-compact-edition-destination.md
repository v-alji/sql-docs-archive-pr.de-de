---
title: SQL Server Compact Edition-Ziel | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.sqlservercompactdest.f1
helpviewer_keywords:
- destinations [Integration Services], SQL Server Compact
- SQL Server Compact, destination
- inserting data
ms.assetid: 697742ba-cc14-414d-8187-1845ad0dd99b
author: chugugrace
ms.author: chugu
ms.openlocfilehash: bfeb0bfce54c9ebefb5c526656be6b736dc0d82b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621111"
---
# <a name="sql-server-compact-edition-destination"></a><span data-ttu-id="c86ce-102">SQL Server Compact Edition-Ziel</span><span class="sxs-lookup"><span data-stu-id="c86ce-102">SQL Server Compact Edition Destination</span></span>
  <span data-ttu-id="c86ce-103">Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Ziel schreibt Daten in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Datenbanken.</span><span class="sxs-lookup"><span data-stu-id="c86ce-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination writes data to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact databases.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c86ce-104">Auf einem 64-Bit-Computer müssen Sie Pakete, die mit den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Datenquellen verbunden sind, im 32-Bit-Modus ausführen.</span><span class="sxs-lookup"><span data-stu-id="c86ce-104">On a 64-bit computer, you must run packages that connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources in 32-bit mode.</span></span> <span data-ttu-id="c86ce-105">Der Anbieter von [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact, der von [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] zum Herstellen einer Verbindung mit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Datenquellen verwendet wird, ist lediglich in einer 32-Bit-Version verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c86ce-105">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact provider that [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] uses to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact data sources is available only in a 32-bit version.</span></span>  
  
 <span data-ttu-id="c86ce-106">Sie konfigurieren das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Ziel, indem Sie den Namen der Tabelle angeben, in die die Daten vom [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Ziel eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c86ce-106">You configure the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination by specifying the name of the table into which the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination inserts the data.</span></span> <span data-ttu-id="c86ce-107">Die benutzerdefinierte Eigenschaft TableName des [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Ziels enthält den Tabellennamen.</span><span class="sxs-lookup"><span data-stu-id="c86ce-107">The custom property TableName of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination contains the table name.</span></span>  
  
 <span data-ttu-id="c86ce-108">Von diesem Ziel wird ein [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Verbindungs-Manager zum Herstellen einer Verbindung mit einer Datenquelle verwendet, und der Verbindungs-Manager gibt den zu verwendenden OLE DB-Anbieter an.</span><span class="sxs-lookup"><span data-stu-id="c86ce-108">This destination uses an [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact connection manager to connect to a data source, and the connection manager specifies the OLE DB provider to use.</span></span> <span data-ttu-id="c86ce-109">Weitere Informationen finden Sie unter [SQL Server Compact Edition-Verbindungs-Managerl](../connection-manager/sql-server-compact-edition-connection-manager.md).</span><span class="sxs-lookup"><span data-stu-id="c86ce-109">For more information, see [SQL Server Compact Edition Connection Manager](../connection-manager/sql-server-compact-edition-connection-manager.md).</span></span>  
  
 <span data-ttu-id="c86ce-110">Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Ziel schließt die benutzerdefinierte Eigenschaft TableName ein, die beim Laden des Pakets durch einen Eigenschaftsausdruck aktualisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="c86ce-110">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination includes the TableName custom property, which can be updated by a property expression when the package is loaded.</span></span> <span data-ttu-id="c86ce-111">Weitere Informationen finden Sie unter [Integration Services-Ausdrücke &#40;SSIS&#41;](../expressions/integration-services-ssis-expressions.md), [Verwenden von Eigenschaftsausdrücken in Paketen](../expressions/use-property-expressions-in-packages.md) und [Benutzerdefinierte Eigenschaften des Ziels für SQL Server Compact Edition](sql-server-compact-edition-destination-custom-properties.md).</span><span class="sxs-lookup"><span data-stu-id="c86ce-111">For more information, see [Integration Services &#40;SSIS&#41; Expressions](../expressions/integration-services-ssis-expressions.md), [Use Property Expressions in Packages](../expressions/use-property-expressions-in-packages.md), and [SQL Server Compact Edition Destination Custom Properties](sql-server-compact-edition-destination-custom-properties.md).</span></span>  
  
 <span data-ttu-id="c86ce-112">Das [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact-Ziel hat eine Eingabe und unterstützt keine Fehlerausgabe.</span><span class="sxs-lookup"><span data-stu-id="c86ce-112">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Compact destination has one input and does not support an error output.</span></span>  
  
## <a name="configuration-of-the-sql-server-compact-edition-destination"></a><span data-ttu-id="c86ce-113">Konfiguration des SQL Server Compact Edition-Ziels</span><span class="sxs-lookup"><span data-stu-id="c86ce-113">Configuration of the SQL Server Compact Edition Destination</span></span>  
 <span data-ttu-id="c86ce-114">Sie können Eigenschaften mit dem [!INCLUDE[ssIS](../../includes/ssis-md.md)] -Designer oder programmgesteuert festlegen.</span><span class="sxs-lookup"><span data-stu-id="c86ce-114">You can set properties through [!INCLUDE[ssIS](../../includes/ssis-md.md)] Designer or programmatically.</span></span>  
  
 <span data-ttu-id="c86ce-115">Das Dialogfeld **Erweiterter Editor** enthält die Eigenschaften, die programmgesteuert festgelegt werden können.</span><span class="sxs-lookup"><span data-stu-id="c86ce-115">The **Advanced Editor** dialog box reflects the properties that can be set programmatically.</span></span> <span data-ttu-id="c86ce-116">Klicken Sie auf eines der folgenden Themen, um weitere Informationen zu den Eigenschaften zu erhalten, die Sie im Dialogfeld **Erweiterter Editor** oder programmgesteuert festlegen können:</span><span class="sxs-lookup"><span data-stu-id="c86ce-116">For more information about the properties that you can set in the **Advanced Editor** dialog box or programmatically, click one of the following topics:</span></span>  
  
-   [<span data-ttu-id="c86ce-117">Common Properties</span><span class="sxs-lookup"><span data-stu-id="c86ce-117">Common Properties</span></span>](../common-properties.md)  
  
-   [<span data-ttu-id="c86ce-118">Benutzerdefinierte Eigenschaften des SQL Server-Ziels</span><span class="sxs-lookup"><span data-stu-id="c86ce-118">SQL Server Destination Custom Properties</span></span>](sql-server-destination-custom-properties.md)  
  
## <a name="related-tasks"></a><span data-ttu-id="c86ce-119">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="c86ce-119">Related Tasks</span></span>  
 <span data-ttu-id="c86ce-120">Weitere Informationen zum Festlegen von Eigenschaften finden Sie unter [Festlegen der Eigenschaften einer Datenflusskomponente](set-the-properties-of-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="c86ce-120">For more information about how to set properties of this component, see [Set the Properties of a Data Flow Component](set-the-properties-of-a-data-flow-component.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c86ce-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c86ce-121">See Also</span></span>  
 [<span data-ttu-id="c86ce-122">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="c86ce-122">Data Flow</span></span>](data-flow.md)  
  
  
