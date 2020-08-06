---
title: Extrahieren von Daten mithilfe der XML-Quelle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- extracting data [Integration Services]
- sources [Integration Services], XML
- XML source [Integration Services]
ms.assetid: 5d5be54c-2b7e-4957-9193-c5ea5c5d6d15
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 57758353c476badfba4cb12a1ef6b5101f16735d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726109"
---
# <a name="extract-data-by-using-the-xml-source"></a><span data-ttu-id="68166-102">Extrahieren von Daten mithilfe der XML-Quelle</span><span class="sxs-lookup"><span data-stu-id="68166-102">Extract Data by Using the XML Source</span></span>
  <span data-ttu-id="68166-103">Um eine XML-Quelle hinzuzufügen und zu konfigurieren, muss das Paket bereits mindestens einen Datenflusstask enthalten.</span><span class="sxs-lookup"><span data-stu-id="68166-103">To add and configure an XML source, the package must already include at least one Data Flow task.</span></span>  
  
### <a name="to-extract-data-using-an-xml-source"></a><span data-ttu-id="68166-104">So extrahieren Sie Daten mithilfe einer XML-Quelle</span><span class="sxs-lookup"><span data-stu-id="68166-104">To extract data using an XML source</span></span>  
  
1.  <span data-ttu-id="68166-105">Öffnen Sie in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] das [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt mit dem gewünschten Paket.</span><span class="sxs-lookup"><span data-stu-id="68166-105">In [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)], open the [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] project that contains the package you want.</span></span>  
  
2.  <span data-ttu-id="68166-106">Doppelklicken Sie im Projektmappen-Explorer auf das Paket, um es zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="68166-106">In Solution Explorer, double-click the package to open it.</span></span>  
  
3.  <span data-ttu-id="68166-107">Klicken Sie auf die Registerkarte **Datenfluss** , und ziehen Sie dann aus **Toolbox**die XML-Quelle auf die Entwurfsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="68166-107">Click the **Data Flow** tab, and then, from the **Toolbox**, drag the XML source to the design surface.</span></span>  
  
4.  <span data-ttu-id="68166-108">Doppelklicken Sie auf die XML-Quelle.</span><span class="sxs-lookup"><span data-stu-id="68166-108">Double-click the XML source.</span></span>  
  
5.  <span data-ttu-id="68166-109">Wählen Sie im Bereich **Quellen-Editor für XML**auf der Seite **Verbindungs-Manager** einen Datenzugriffsmodus aus:</span><span class="sxs-lookup"><span data-stu-id="68166-109">In the **XML Source Editor**, on the **Connection Manager** page, select a data access mode:</span></span>  
  
    -   <span data-ttu-id="68166-110">Für den Zugriffsmodus **XML-Dateispeicherort** klicken Sie auf **Durchsuchen** , und suchen Sie den Ordner, der die XML-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="68166-110">For the **XML file location** access mode, click **Browse** and locate the folder that contains the XML file.</span></span>  
  
    -   <span data-ttu-id="68166-111">Für den Zugriffsmodus **XML-Datei aus Variable** wählen Sie die benutzerdefinierte Variable aus, die den Pfad der XML-Datei enthält.</span><span class="sxs-lookup"><span data-stu-id="68166-111">For the **XML file from variable** access mode, select the user-defined variable that contains the path of the XML file.</span></span>  
  
    -   <span data-ttu-id="68166-112">Für den Zugriffsmodus **XML-Daten aus Variable** wählen Sie die benutzerdefinierte Variable aus, die die XML-Daten enthält.</span><span class="sxs-lookup"><span data-stu-id="68166-112">For the **XML data from variable** access mode, select the user-defined variable that contains the XML data.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="68166-113">Die Variablen müssen im Bereich des Datenflusstasks definiert werden, der die XML-Quelle enthält, oder im Bereich des Pakets. Darüber hinaus muss die Variable einen Zeichenfolgen-Datentyp aufweisen.</span><span class="sxs-lookup"><span data-stu-id="68166-113">The variables must be defined in the scope of the Data Flow task that contains the XML source, or in the scope of the package; additionally, the variable must have a string data type.</span></span>  
  
6.  <span data-ttu-id="68166-114">Aktivieren Sie optional das Kontrollkästchen **Inlineschema verwenden** , um anzuzeigen, dass das XML-Dokument Schemainformationen enthält.</span><span class="sxs-lookup"><span data-stu-id="68166-114">Optionally, select **Use inline schema** to indicate that the XML document includes schema information.</span></span>  
  
7.  <span data-ttu-id="68166-115">Um ein externes XSD-Schema (XML Schema Definition Language) für die XML-Datei anzugeben, führen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="68166-115">To specify an external XML Schema definition language (XSD) schema for the XML file, do one of the following:</span></span>  
  
    -   <span data-ttu-id="68166-116">Klicken Sie auf **Durchsuchen** , um eine vorhandene XSD-Datei zu suchen.</span><span class="sxs-lookup"><span data-stu-id="68166-116">Click **Browse** to locate an existing XSD file.</span></span>  
  
    -   <span data-ttu-id="68166-117">Klicken Sie auf **XSD-Code generieren** , um XSD-Code von der XML-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="68166-117">Click **Generate XSD** to create an XSD from the XML file.</span></span>  
  
8.  <span data-ttu-id="68166-118">Um die Namen von Ausgabespalten zu aktualisieren, klicken Sie auf **Spalten** , und bearbeiten Sie die Werte in der Liste **Ausgabespalte** .</span><span class="sxs-lookup"><span data-stu-id="68166-118">To update the names of output columns, click **Columns** and edit the values in the **Output Column** list.</span></span>  
  
9. <span data-ttu-id="68166-119">Klicken Sie auf **Fehlerausgabe**, um die Fehlerausgabe zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="68166-119">To configure the error output, click **Error Output**.</span></span> <span data-ttu-id="68166-120">Weitere Informationen finden Sie unter [Konfigurieren einer Fehlerausgabe in einer Datenflusskomponente](../configure-an-error-output-in-a-data-flow-component.md).</span><span class="sxs-lookup"><span data-stu-id="68166-120">For more information, see [Configure an Error Output in a Data Flow Component](../configure-an-error-output-in-a-data-flow-component.md).</span></span>  
  
10. <span data-ttu-id="68166-121">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="68166-121">Click **OK**.</span></span>  
  
11. <span data-ttu-id="68166-122">Klicken Sie im Menü **Datei** auf **Ausgewählte Elemente speichern** , um das aktualisierte Paket zu speichern.</span><span class="sxs-lookup"><span data-stu-id="68166-122">To save the updated package, click **Save Selected Items** on the **File** menu.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68166-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="68166-123">See Also</span></span>  
 <span data-ttu-id="68166-124">[XML-Quelle](xml-source.md) </span><span class="sxs-lookup"><span data-stu-id="68166-124">[XML Source](xml-source.md) </span></span>  
 <span data-ttu-id="68166-125">[SQL Server Integration Services-Transformationen](transformations/integration-services-transformations.md) </span><span class="sxs-lookup"><span data-stu-id="68166-125">[Integration Services Transformations](transformations/integration-services-transformations.md) </span></span>  
 <span data-ttu-id="68166-126">[SQL Server Integration Services-Pfade](integration-services-paths.md) </span><span class="sxs-lookup"><span data-stu-id="68166-126">[Integration Services Paths](integration-services-paths.md) </span></span>  
 [<span data-ttu-id="68166-127">Datenflusstask</span><span class="sxs-lookup"><span data-stu-id="68166-127">Data Flow Task</span></span>](../control-flow/data-flow-task.md)  
  
  
