---
title: Transformations-Editor für Fuzzygruppierung (Registerkarte Verbindungs-Manager) Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.designer.fuzzygroupingtransformation.connection.f1
helpviewer_keywords:
- Fuzzy Grouping Transformation Editor
ms.assetid: 47b1446d-5331-473c-9cb5-a98b1f55bf5f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b2a8b0af9f36fdd386f7da375184fd4e4ec5c4be
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621062"
---
# <a name="fuzzy-grouping-transformation-editor-connection-manager-tab"></a><span data-ttu-id="fee83-102">Transformations-Editor für Fuzzygruppierung (Registerkarte Verbindungs-Manager)</span><span class="sxs-lookup"><span data-stu-id="fee83-102">Fuzzy Grouping Transformation Editor (Connection Manager Tab)</span></span>
  <span data-ttu-id="fee83-103">Mithilfe der Registerkarte **Verbindungs-Manager** des Dialogfelds **Transformations-Editor für Fuzzygruppierung** können Sie eine vorhandene Verbindung auswählen oder eine neue erstellen.</span><span class="sxs-lookup"><span data-stu-id="fee83-103">Use the **Connection Manager** tab of the **Fuzzy Grouping Transformation Editor** dialog box to select an existing connection or create a new one.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="fee83-104">Auf dem von der Verbindung angegebenen Server muss [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fee83-104">The server specified by the connection must be running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="fee83-105">Die Transformation für Fuzzygruppierung erstellt temporäre Datenobjekte in tempdb, die so groß sein können wie die gesamte Eingabe der Transformation.</span><span class="sxs-lookup"><span data-stu-id="fee83-105">The Fuzzy Grouping transformation creates temporary data objects in tempdb that may be as large as the full input to the transformation.</span></span> <span data-ttu-id="fee83-106">Während die Transformation ausgeführt wird, werden Abfragen für diese temporären Objekte ausgegeben.</span><span class="sxs-lookup"><span data-stu-id="fee83-106">While the transformation executes, it issues server queries against these temporary objects.</span></span> <span data-ttu-id="fee83-107">Dadurch kann die Gesamtleistung des Servers beeinträchtigt werden.</span><span class="sxs-lookup"><span data-stu-id="fee83-107">This can affect overall server performance.</span></span>  
  
 <span data-ttu-id="fee83-108">Weitere Informationen zur Transformation für Fuzzygruppierung finden Sie unter [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span><span class="sxs-lookup"><span data-stu-id="fee83-108">To learn more about the Fuzzy Grouping transformation, see [Fuzzy Grouping Transformation](data-flow/transformations/fuzzy-grouping-transformation.md).</span></span>  
  
## <a name="options"></a><span data-ttu-id="fee83-109">Tastatur</span><span class="sxs-lookup"><span data-stu-id="fee83-109">Options</span></span>  
 <span data-ttu-id="fee83-110">**Teilcache**</span><span class="sxs-lookup"><span data-stu-id="fee83-110">**OLE DB connection manager**</span></span>  
 <span data-ttu-id="fee83-111">Wählen Sie einen vorhandenen OLE DB-Verbindungs-Manager aus dem Listenfeld aus, oder erstellen Sie mithilfe der Schaltfläche **Neu** eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="fee83-111">Select an existing OLE DB connection manager by using the list box, or create a new connection by using the **New** button.</span></span>  
  
 <span data-ttu-id="fee83-112">**Neu**</span><span class="sxs-lookup"><span data-stu-id="fee83-112">**New**</span></span>  
 <span data-ttu-id="fee83-113">Erstellen Sie mithilfe des Dialogfelds **OLE DB-Verbindungs-Manager konfigurieren** eine neue Verbindung.</span><span class="sxs-lookup"><span data-stu-id="fee83-113">Create a new connection by using the **Configure OLE DB Connection Manager** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fee83-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="fee83-114">See Also</span></span>  
 <span data-ttu-id="fee83-115">[Fehler- und Meldungsreferenz von Integration Services](../../2014/integration-services/integration-services-error-and-message-reference.md) </span><span class="sxs-lookup"><span data-stu-id="fee83-115">[Integration Services Error and Message Reference](../../2014/integration-services/integration-services-error-and-message-reference.md) </span></span>  
 [<span data-ttu-id="fee83-116">Identifizieren ähnlicher Datenzeilen mithilfe der Transformation für Fuzzygruppierung</span><span class="sxs-lookup"><span data-stu-id="fee83-116">Identify Similar Data Rows by Using the Fuzzy Grouping Transformation</span></span>](data-flow/transformations/identify-similar-data-rows-by-using-the-fuzzy-grouping-transformation.md)  
  
  
