---
title: Implementieren externer Metadaten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: reference
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- disconnected validation [Integration Services]
- connected validation [Integration Services]
- custom data flow components [Integration Services], validating
- validation [Integration Services], components
- metadata [Integration Services]
- data flow components [Integration Services], validating
- data flow components [Integration Services], external metadata
- custom data flow components [Integration Services], external metadata
- external metadata [Integration Services]
ms.assetid: 8f5bd3ed-3e79-43a4-b6c1-435e4c2cc8cc
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 7a6b77229c528bc08057e662a4b3761d1daf732f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87697022"
---
# <a name="implementing-external-metadata"></a><span data-ttu-id="2c665-102">Implementieren externer Metadaten</span><span class="sxs-lookup"><span data-stu-id="2c665-102">Implementing External Metadata</span></span>
  <span data-ttu-id="2c665-103">Wenn die Verbindung einer Komponente mit einer Datenquelle getrennt ist, können Sie mithilfe der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100>-Schnittstelle die Spalten in den Eingabe- und Ausgabespaltenauflistungen anhand der Spalten der externen Datenquelle überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2c665-103">When a component is disconnected from its data source, you can validate the columns in the input and output column collections against the columns at its external data source by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100> interface.</span></span> <span data-ttu-id="2c665-104">Mit dieser Schnittstelle können Sie eine Momentaufnahme der Spalten der externen Datenquelle verwalten und diese Spalten den Eingabe- und Ausgabespaltenauflistungen der Komponente zuordnen.</span><span class="sxs-lookup"><span data-stu-id="2c665-104">This interface lets you maintain a snapshot of the columns at the external data source and map these columns to the columns in the input and output column collection of the component.</span></span>  
  
 <span data-ttu-id="2c665-105">Die Implementierung externer Metadatenspalten erhöht den Verwaltungsaufwand und die Komplexität bei der Komponentenentwicklung, da Sie eine weitere Spaltenauflistung verwalten und überprüfen müssen. Diese Entwicklungsarbeit kann sich aber lohnen, da Sie teure Roundtrips zum Server zu Überprüfungszwecken vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="2c665-105">Implementing external metadata columns adds a layer of overhead and complexity to component development, because you must maintain and validate against an additional column collection, but the ability to avoid expensive round trips to the server for validation may make this development work worthwhile.</span></span>  
  
## <a name="populating-external-metadata-columns"></a><span data-ttu-id="2c665-106">Auffüllen von externen Metadatenspalten</span><span class="sxs-lookup"><span data-stu-id="2c665-106">Populating External Metadata Columns</span></span>  
 <span data-ttu-id="2c665-107">Externe Metadatenspalten werden der Auflistung meist bei der Erstellung der entsprechenden Eingabe- oder Ausgabespalten hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2c665-107">External metadata columns are typically added to the collection when the corresponding input or output column is created.</span></span> <span data-ttu-id="2c665-108">Neue Spalten werden durch Aufrufen der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.New%2A>-Methode erstellt.</span><span class="sxs-lookup"><span data-stu-id="2c665-108">New columns are created by calling the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.New%2A> method.</span></span> <span data-ttu-id="2c665-109">Die Eigenschaften der Spalte werden anschließend entsprechend der externen Datenquelle festgelegt.</span><span class="sxs-lookup"><span data-stu-id="2c665-109">The properties of the column are then set to match the external data source.</span></span>  
  
 <span data-ttu-id="2c665-110">Die externe Metadatenspalte wird der entsprechenden Eingabe- oder Ausgabespalte durch Zuweisen der ID der externen Metadatenspalte zur <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A>-Eigenschaft der Eingabe- oder Ausgabespalte zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="2c665-110">The external metadata column is mapped to the corresponding input or output column by assigning the ID of the external metadata column to the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> property of the input or output column.</span></span> <span data-ttu-id="2c665-111">So können Sie die externe Metadatenspalte für eine spezifische Eingabe- oder Ausgabespalte leicht mithilfe der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.GetObjectByID%2A>-Methode der Auflistung finden.</span><span class="sxs-lookup"><span data-stu-id="2c665-111">This lets you locate the external metadata column easily for a specific input or output column by using the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.GetObjectByID%2A> method of the collection.</span></span>  
  
 <span data-ttu-id="2c665-112">Im folgenden Beispiel werden die Erstellung einer externen Metadatenspalte und die anschließende Zuordnung der Spalte zu einer Ausgabespalte durch Festlegen der <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A>-Eigenschaft veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="2c665-112">The following example shows how to create an external metadata column and then map the column to an output column by setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSOutputColumn100.ExternalMetadataColumnID%2A> property.</span></span>  
  
```csharp  
public void CreateExternalMetaDataColumn(IDTSOutput100 output, int outputColumnID )  
{  
    IDTSOutputColumn100 oColumn = output.OutputColumnCollection.GetObjectByID(outputColumnID);  
    IDTSExternalMetadataColumn100 eColumn = output.ExternalMetadataColumnCollection.New();  
  
    eColumn.DataType = oColumn.DataType;  
    eColumn.Precision = oColumn.Precision;  
    eColumn.Scale = oColumn.Scale;  
    eColumn.Length = oColumn.Length;  
    eColumn.CodePage = oColumn.CodePage;  
  
    oColumn.ExternalMetadataColumnID = eColumn.ID;  
}  
```  
  
```vb  
Public Sub CreateExternalMetaDataColumn(ByVal output As IDTSOutput100, ByVal outputColumnID As Integer)   
 Dim oColumn As IDTSOutputColumn100 = output.OutputColumnCollection.GetObjectByID(outputColumnID)   
 Dim eColumn As IDTSExternalMetadataColumn100 = output.ExternalMetadataColumnCollection.New   
 eColumn.DataType = oColumn.DataType   
 eColumn.Precision = oColumn.Precision   
 eColumn.Scale = oColumn.Scale   
 eColumn.Length = oColumn.Length   
 eColumn.CodePage = oColumn.CodePage   
 oColumn.ExternalMetadataColumnID = eColumn.ID   
End Sub  
```  
  
## <a name="validating-with-external-metadata-columns"></a><span data-ttu-id="2c665-113">Überprüfen anhand externer Metadatenspalten</span><span class="sxs-lookup"><span data-stu-id="2c665-113">Validating with External Metadata Columns</span></span>  
 <span data-ttu-id="2c665-114">Die Überprüfung erfordert weitere Schritte für Komponenten, die eine externe Metadatenspaltenauflistung verwalten, denn Sie müssen die Überprüfung anhand einer weiteren Spaltenauflistung vornehmen.</span><span class="sxs-lookup"><span data-stu-id="2c665-114">Validation requires additional steps for components that maintain an external metadata column collection, because you must validate against an additional collection of columns.</span></span> <span data-ttu-id="2c665-115">Bei der Überprüfung kann zwischen einer verbundenen und einer getrennten Überprüfung unterschieden werden.</span><span class="sxs-lookup"><span data-stu-id="2c665-115">Validation can be divided into connected validation or disconnected validation.</span></span>  
  
### <a name="connected-validation"></a><span data-ttu-id="2c665-116">Verbundene Überprüfung</span><span class="sxs-lookup"><span data-stu-id="2c665-116">Connected Validation</span></span>  
 <span data-ttu-id="2c665-117">Besteht eine Verbindung einer Komponente mit einer externen Datenquelle, werden die Spalten in den Eingabe- oder Ausgabeauflistungen direkt anhand der externen Datenquelle überprüft.</span><span class="sxs-lookup"><span data-stu-id="2c665-117">When a component is connected to an external data source, the columns in the input or output collections are verified directly against the external data source.</span></span> <span data-ttu-id="2c665-118">Darüber hinaus müssen die Spalten in der externen Metadatensammlung überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="2c665-118">Additionally, the columns in the external metadata collection must be validated.</span></span> <span data-ttu-id="2c665-119">Dies ist erforderlich, da die externe Metadatensammlung unter **Erweiterter Editor** in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] verändert werden kann, und Änderungen, die an der Sammlung vorgenommen werden, nicht erkennbar sind.</span><span class="sxs-lookup"><span data-stu-id="2c665-119">This is required because the external metadata collection can be modified by using the **Advanced Editor** in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)], and changes made to the collection are not detectable.</span></span> <span data-ttu-id="2c665-120">Daher müssen die Komponenten, wenn eine Verbindung besteht, sicherstellen, dass die Spalten in der externen Metadatensammlung weiterhin den Spalten der externen Datenquelle entsprechen.</span><span class="sxs-lookup"><span data-stu-id="2c665-120">Therefore, when connected, components must make sure that the columns in the external metadata column collection continue to reflect the columns at the external data source.</span></span>  
  
 <span data-ttu-id="2c665-121">Sie können die externe Metadatenauflistung im **Erweiterter Editor** ausblenden, indem Sie die- <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.IsUsed%2A> Eigenschaft der-Auflistung auf festlegen `false` .</span><span class="sxs-lookup"><span data-stu-id="2c665-121">You may choose to hide the external metadata collection in the **Advanced Editor** by setting the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSExternalMetadataColumnCollection100.IsUsed%2A> property of the collection to `false`.</span></span> <span data-ttu-id="2c665-122">Dadurch wird jedoch auch die Registerkarte **Spaltenzuordnung** des Editors ausgeblendet, über die Benutzer Spalten der Eingabe- und Ausgabeauflistungen den Spalten in der externen Metadatenspaltenauflistung zuordnen können.</span><span class="sxs-lookup"><span data-stu-id="2c665-122">However this also hides the **Column Mapping** tab of the editor, which lets users map columns from the input or output collection to the columns in the external metadata column collection.</span></span> <span data-ttu-id="2c665-123">Ein Festlegen dieser Eigenschaft auf den Wert `false` verhindert nicht, dass Entwickler die Auflistung programmgesteuert verändern, bietet jedoch Schutz für die externe Metadatenspaltenauflistung einer Komponente, die ausschließlich in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)] verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2c665-123">Setting this property to `false` does not prevent developers from programmatically modifying the collection, but it does provide a level of protection for the external metadata column collection of a component that is used exclusively in [!INCLUDE[ssBIDevStudioFull](../../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="disconnected-validation"></a><span data-ttu-id="2c665-124">Getrennte Überprüfung</span><span class="sxs-lookup"><span data-stu-id="2c665-124">Disconnected Validation</span></span>  
 <span data-ttu-id="2c665-125">Ist die Verbindung einer Komponente mit einer externen Datenquelle getrennt, ist die Überprüfung einfacher, da die Spalten in der Eingabe- oder Ausgabeauflistung direkt anhand der Spalten der externen Metadatensammlung und nicht anhand der externen Datenquelle überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="2c665-125">When a component is disconnected from an external data source, validation is simplified because the columns in the input or output collection are verified directly against the columns in the external metadata collection and not against the external source.</span></span> <span data-ttu-id="2c665-126">Eine Komponente sollte eine getrennte Überprüfung ausführen, wenn keine Verbindung mit der externen Datenquelle besteht oder die <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A>-Eigenschaft den Wert `false` aufweist.</span><span class="sxs-lookup"><span data-stu-id="2c665-126">A component should perform disconnected validation when the connection to its external data source has not been established, or when the <xref:Microsoft.SqlServer.Dts.Pipeline.Wrapper.IDTSComponentMetaData100.ValidateExternalMetadata%2A> property is `false`.</span></span>  
  
 <span data-ttu-id="2c665-127">Im folgenden Codebeispiel wird die Implementierung einer Komponente, die eine Überprüfung anhand der externen Metadatenspaltenauflistung vornimmt, gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2c665-127">The following code example demonstrates an implementation of a component that performs validation against its external metadata column collection.</span></span>  
  
```csharp  
public override DTSValidationStatus Validate()  
{  
    if( this.isConnected && ComponentMetaData.ValidateExternalMetaData )  
    {  
        // TODO: Perform connected validation.  
    }  
    else  
    {  
        // TODO: Perform disconnected validation.  
    }  
}  
```  
  
```vb  
Public  Overrides Function Validate() As DTSValidationStatus   
 If Me.isConnected AndAlso ComponentMetaData.ValidateExternalMetaData Then   
  ' TODO: Perform connected validation.  
 Else   
  ' TODO: Perform disconnected validation.  
 End If   
End Function  
```  
  
<span data-ttu-id="2c665-128">![Integration Services Symbol (klein)](../../media/dts-16.gif "Integration Services (kleines Symbol)")immer auf**dem neuesten Stand bleiben mit Integration Services**  </span><span class="sxs-lookup"><span data-stu-id="2c665-128">![Integration Services icon (small)](../../media/dts-16.gif "Integration Services icon (small)")  **Stay Up to Date with Integration Services**</span></span><br /> <span data-ttu-id="2c665-129">Die neuesten Downloads, Artikel, Beispiele und Videos von Microsoft sowie ausgewählte Lösungen aus der Community finden Sie auf MSDN auf der [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] -Seite:</span><span class="sxs-lookup"><span data-stu-id="2c665-129">For the latest downloads, articles, samples, and videos from Microsoft, as well as selected solutions from the community, visit the [!INCLUDE[ssISnoversion](../../../includes/ssisnoversion-md.md)] page on MSDN:</span></span><br /><br /> [<span data-ttu-id="2c665-130">Besuchen Sie die Integration Services-Seite auf MSDN</span><span class="sxs-lookup"><span data-stu-id="2c665-130">Visit the Integration Services page on MSDN</span></span>](https://go.microsoft.com/fwlink/?LinkId=136655)<br /><br /> <span data-ttu-id="2c665-131">Abonnieren Sie die auf der Seite verfügbaren RSS-Feeds, um automatische Benachrichtigungen zu diesen Updates zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="2c665-131">For automatic notification of these updates, subscribe to the RSS feeds available on the page.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c665-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="2c665-132">See Also</span></span>  
 [<span data-ttu-id="2c665-133">Datenfluss</span><span class="sxs-lookup"><span data-stu-id="2c665-133">Data Flow</span></span>](../../data-flow/data-flow.md)  
  
  
