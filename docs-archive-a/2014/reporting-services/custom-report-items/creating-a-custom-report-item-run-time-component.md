---
title: Erstellen einer Entwurfszeitkomponente für ein benutzerdefiniertes Berichtselement | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services
ms.topic: reference
helpviewer_keywords:
- custom report items, creating
ms.assetid: b3e15a4a-98f8-4dbb-b847-bbcb20327051
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 50c5c0211bc5cd1359af9d1493782bd9d96c2b3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87608413"
---
# <a name="creating-a-custom-report-item-run-time-component"></a><span data-ttu-id="7b8e4-102">Erstellen einer Laufzeitkomponente für ein benutzerdefiniertes Berichtselement</span><span class="sxs-lookup"><span data-stu-id="7b8e4-102">Creating a Custom Report Item Run-Time Component</span></span>
  <span data-ttu-id="7b8e4-103">Die Laufzeitkomponente für ein benutzerdefiniertes Berichts Element wird als- [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] Komponente mithilfe einer beliebigen CLS-kompatiblen Sprache implementiert und vom Berichts Prozessor zur Laufzeit aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-103">The custom report item run-time component is implemented as a [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] component using any CLS-compliant language, and is called by the report processor at run time.</span></span> <span data-ttu-id="7b8e4-104">Sie definieren die Eigenschaften für die Laufzeitkomponente in der Entwurfsumgebung, indem Sie die entsprechende Entwurfszeitkomponente für ein benutzerdefiniertes Berichtselement ändern.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-104">You define the properties for the run-time component in the design environment by modifying the custom report item's corresponding design-time component.</span></span>  

<!--
Replacing the following multiValue.....

ms.technology: 
  - "docset-sql-devref"
  - "reporting-services-native"

.....with the following single value.....

ms.technology: reporting-services
.

(GeneMi = MightyPen  ,  2019-04-20  ,  DevO= 1515083)
-->

 <span data-ttu-id="7b8e4-105">Ein Beispiel für ein vollständig implementiertes benutzerdefiniertes Berichtselement finden Sie unter [SQL Server Reporting Services-Produktbeispiele](https://go.microsoft.com/fwlink/?LinkId=177889).</span><span class="sxs-lookup"><span data-stu-id="7b8e4-105">For a sample of a fully implemented custom report item, see [SQL Server Reporting Services Product Samples](https://go.microsoft.com/fwlink/?LinkId=177889).</span></span>  
  
## <a name="definition-and-instance-objects"></a><span data-ttu-id="7b8e4-106">Definitions- and Instanzobjekte</span><span class="sxs-lookup"><span data-stu-id="7b8e4-106">Definition and Instance Objects</span></span>  
 <span data-ttu-id="7b8e4-107">Bevor Sie ein benutzerdefiniertes Berichtselement implementieren, sollten Sie den Unterschied zwischen *Definitionsobjekten* und *Instanzobjekten* kennen.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-107">Before implementing a custom report item it is important to understand the difference between *definition objects* and *instance objects*.</span></span> <span data-ttu-id="7b8e4-108">Definitionsobjekte stellen die RDL-Darstellung des benutzerdefinierten Berichtselements bereit, wohingegen es sich bei Instanzobjekten um die bewerteten Versionen von Definitionsobjekten handelt.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-108">Definition objects provide the RDL representation of the custom report item whereas instance objects are the evaluated versions of the definition objects.</span></span> <span data-ttu-id="7b8e4-109">Für jedes Element des Berichts gibt es nur ein Definitionsobjekt.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-109">There is only one definition object for each item on the report.</span></span> <span data-ttu-id="7b8e4-110">Beim Zugreifen auf Eigenschaften auf einem Definitionsobjekt, die Ausdrücke enthalten, erhalten Sie die nicht bewertete Ausdruckszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-110">When accessing properties on a definition object that contain expressions, you will get the unevaluated expression string.</span></span> <span data-ttu-id="7b8e4-111">Instanzobjekte enthalten die bewerteten Versionen der Definitionsobjekte und können in einer 1:n-Beziehung mit dem Definitionsobjekt eines Elements stehen.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-111">Instance objects contain the evaluated versions of the definition objects and can have a one-to-many relationship with an item's definition object.</span></span> <span data-ttu-id="7b8e4-112">Wenn beispielsweise ein Bericht einen <xref:Microsoft.ReportingServices.OnDemandReportRendering.Tablix>-Datenbereich besitzt, der ein <xref:Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem> in einer Detailzeile enthält, ist nur ein einziges Definitionsobjekt vorhanden, es gibt jedoch für jede Zeile im Datenbereich eine Instanz.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-112">For example, if a report has a <xref:Microsoft.ReportingServices.OnDemandReportRendering.Tablix> data region that contains a <xref:Microsoft.ReportingServices.OnDemandReportRendering.CustomReportItem> in a detail row, there will be only one definition object but there will be an instance object for each row in the data region.</span></span>  
  
## <a name="implementing-the-icustomreportitem-interface"></a><span data-ttu-id="7b8e4-113">Implementieren der ICustomReportItem-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="7b8e4-113">Implementing the ICustomReportItem Interface</span></span>  
 <span data-ttu-id="7b8e4-114">Um eine `CustomReportItem`-Laufzeitkomponente zu erstellen, müssen Sie die <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem>-Schnittstelle implementieren, die in der Datei Microsoft.ReportingServices.ProcessingCore.dll definiert ist:</span><span class="sxs-lookup"><span data-stu-id="7b8e4-114">To create a `CustomReportItem` run-time component you will need to implement the <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem> interface that is defined in the Microsoft.ReportingServices.ProcessingCore.dll:</span></span>  
  
```csharp  
namespace Microsoft.ReportingServices.OnDemandReportRendering  
{  
    public interface ICustomReportItem  
    {  
        void GenerateReportItemDefinition(CustomReportItem customReportItem);  
void EvaluateReportItemInstance(CustomReportItem customReportItem);  
    }  
}  
```  
  
 <span data-ttu-id="7b8e4-115">Nachdem die <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem>-Schnittstelle implementiert ist, werden zwei Methodenstubs generiert: <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> und <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A>.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-115">After you have implemented the <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem> interface, two method stubs will be generated for you: <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> and <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A>.</span></span> <span data-ttu-id="7b8e4-116">Die <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A>-Methode wird zuerst aufgerufen. Sie wird zum Festlegen der Definitionseigenschaften and zum Erstellen des <xref:Microsoft.ReportingServices.OnDemandReportRendering.Image>-Objekts verwendet, das sowohl die zum Rendern des Elements verwendeten Definitions- und die Instanzeigenschaften enthält.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-116">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.GenerateReportItemDefinition%2A> method is called first and is used for setting definition properties and creating the <xref:Microsoft.ReportingServices.OnDemandReportRendering.Image> object that will contain both the definition and instance properties that are used for rendering the item.</span></span> <span data-ttu-id="7b8e4-117">Nachdem die Definitionsobjekte bewertet wurden, wird die <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A>-Methode aufgerufen. Sie stellt die Instanzobjekte zum Rendern des Elements bereit.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-117">The <xref:Microsoft.ReportingServices.OnDemandReportRendering.ICustomReportItem.EvaluateReportItemInstance%2A> method is called after the definition objects have been evaluated, and it provides the instance objects that will be used for rendering the item.</span></span>  
  
 <span data-ttu-id="7b8e4-118">Im Folgenden sehen Sie eine Beispielimplementierung eines benutzerdefinierten Berichtselements, das den Namen der Steuerung als Bild rendert.</span><span class="sxs-lookup"><span data-stu-id="7b8e4-118">The following is an example implementation of a custom report item that renders the name of the control as an image.</span></span>  
  
```csharp  
namespace Microsoft.Samples.ReportingServices  
{  
    using System;  
    using System.Collections.Generic;  
    using System.Collections.Specialized;  
    using System.Drawing.Imaging;  
    using System.IO;  
    using System.Text;  
    using Microsoft.ReportingServices.OnDemandReportRendering;  
  
    public class PolygonsCustomReportItem : ICustomReportItem  
    {  
        #region ICustomReportItem Members  
  
        public void GenerateReportItemDefinition(CustomReportItem cri)  
        {  
            // Create the Image object that will be   
            // used to render the custom report item  
            cri.CreateCriImageDefinition();  
            Image polygonImage = (Image)cri.GeneratedReportItem;  
        }  
  
        public void EvaluateReportItemInstance(CustomReportItem cri)  
        {  
            // Get the Image definition  
            Image polygonImage = (Image)cri.GeneratedReportItem;  
  
            // Create the image for the custom report item  
            polygonImage.ImageInstance.ImageData = DrawImage(cri);  
        }  
  
        #endregion  
  
        /// <summary>  
        /// Creates an image of the CustomReportItem's name  
        /// </summary>  
        private byte[] DrawImage(CustomReportItem customReportItem)  
        {  
            int width = 1;          // pixels  
            int height = 1;         // pixels  
            int resolution = 75;    // dpi  
  
            System.Drawing.Bitmap bitmap = new System.Drawing.Bitmap(width, height);  
            bitmap.SetResolution(resolution, resolution);  
  
            System.Drawing.Graphics graphics = System.Drawing.Graphics.FromImage(bitmap);  
            graphics.PageUnit = System.Drawing.GraphicsUnit.Pixel;  
  
            // Get the Font for the Text  
            System.Drawing.Font font = new System.Drawing.Font(System.Drawing.FontFamily.GenericMonospace,  
                12, System.Drawing.FontStyle.Regular);  
  
            // Get the Brush for drawing the Text  
            System.Drawing.Brush brush = new System.Drawing.SolidBrush(System.Drawing.Color.LightGreen);  
  
            // Get the measurements for the image  
            System.Drawing.SizeF maxStringSize = graphics.MeasureString(customReportItem.Name, font);  
            width = (int)(maxStringSize.Width + 2 * font.GetHeight(resolution));  
            height = (int)(maxStringSize.Height + 2 * font.GetHeight(resolution));  
  
            bitmap.Dispose();  
            bitmap = new System.Drawing.Bitmap(width, height);  
            bitmap.SetResolution(resolution, resolution);  
  
            graphics.Dispose();  
            graphics = System.Drawing.Graphics.FromImage(bitmap);  
            graphics.PageUnit = System.Drawing.GraphicsUnit.Pixel;  
  
            // Draw the text  
            graphics.DrawString(customReportItem.Name, font, brush, font.GetHeight(resolution),   
                font.GetHeight(resolution));  
  
            // Create the byte array of the image data  
            MemoryStream memoryStream = new MemoryStream();  
            bitmap.Save(memoryStream, ImageFormat.Bmp);  
            memoryStream.Position = 0;  
            byte[] imageData = new byte[memoryStream.Length];  
            memoryStream.Read(imageData, 0, imageData.Length);  
  
            return imageData;  
        }  
    }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="7b8e4-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7b8e4-119">See Also</span></span>  
 <span data-ttu-id="7b8e4-120">[Architektur des benutzerdefinierten Berichts Elements](custom-report-item-architecture.md) </span><span class="sxs-lookup"><span data-stu-id="7b8e4-120">[Custom Report Item Architecture](custom-report-item-architecture.md) </span></span>  
 <span data-ttu-id="7b8e4-121">[Erstellen einer Entwurfszeit Komponente für ein benutzerdefiniertes Berichts Element](creating-a-custom-report-item-design-time-component.md) </span><span class="sxs-lookup"><span data-stu-id="7b8e4-121">[Creating a Custom Report Item Design-Time Component](creating-a-custom-report-item-design-time-component.md) </span></span>  
 <span data-ttu-id="7b8e4-122">[Klassenbibliotheken für benutzerdefinierte Berichts Elemente](custom-report-item-class-libraries.md) </span><span class="sxs-lookup"><span data-stu-id="7b8e4-122">[Custom Report Item Class Libraries](custom-report-item-class-libraries.md) </span></span>  
 [<span data-ttu-id="7b8e4-123">Vorgehensweise: Bereitstellen eines benutzerdefinierten Berichtselements</span><span class="sxs-lookup"><span data-stu-id="7b8e4-123">How to: Deploy a Custom Report Item</span></span>](how-to-deploy-a-custom-report-item.md)  
  
  
