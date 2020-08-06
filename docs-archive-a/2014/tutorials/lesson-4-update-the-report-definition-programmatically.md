---
title: 'Lektion 4: Programm gesteuertes Aktualisieren der Berichts Definition | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1f0a1d46-6d6d-4f67-b51e-06dbbbffacf9
author: markingmyname
ms.author: maghan
manager: kfile
ms.openlocfilehash: c090fc023e3ac47927b99ab61a45fd8ca2c79321
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616867"
---
# <a name="lesson-4-update-the-report-definition-programmatically"></a><span data-ttu-id="1352b-102">Lektion 4: Programmgesteuertes Update der Berichtsdefinition</span><span class="sxs-lookup"><span data-stu-id="1352b-102">Lesson 4: Update the Report Definition Programmatically</span></span>
  <span data-ttu-id="1352b-103">Nachdem die Berichtsdefinition vom Berichtsserver geladen wurde und mit dem Berichtsfelds ein Verweis darauf vorhanden ist, müssen Sie die Berichtsdefinition aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="1352b-103">Now that the report definition has been loaded from the report server and you have a reference to it using the report field, you need to update the report definition.</span></span> <span data-ttu-id="1352b-104">Im folgenden Beispiel wird die `Description`-Eigenschaft für den Bericht aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="1352b-104">For this example, you will update the `Description` property for the report.</span></span>  
  
### <a name="to-update-the-report-definition"></a><span data-ttu-id="1352b-105">So aktualisieren Sie die Berichtsdefinition</span><span class="sxs-lookup"><span data-stu-id="1352b-105">To update the report definition</span></span>  
  
1.  <span data-ttu-id="1352b-106">Ersetzen Sie den Code für die UpdateReportDefinition ()-Methode in der Program.cs-Datei (Module1. vb für [!INCLUDE[vbprvb](../includes/vbprvb-md.md)] ) durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="1352b-106">Replace the code for the UpdateReportDefinition() method in the Program.cs file (Module1.vb for [!INCLUDE[vbprvb](../includes/vbprvb-md.md)]) with the following code:</span></span>  
  
    ```csharp  
    private void UpdateReportDefinition()  
    {  
        System.Console.WriteLine("Updating Report Definition");  
  
        // Create a list of the Items Choices for the Report. The   
        // ItemsChoiceType118 enum represents all the properties  
        // available in the report and the ItemsElementName   
        // represents the properties that exist in the current   
        // instance of the report.  
        List<ItemsChoiceType118> _reportItems =   
            new List<ItemsChoiceType118>(_report.ItemsElementName);  
  
        // Locate the index for the Description property  
        int index = _reportItems.IndexOf(  
            ItemsChoiceType118.Description);  
  
        // The Description item is of type StringLocIDType, so   
        // cast the item type first and then assign new value.  
        System.Console.WriteLine("- Old Description: " +   
            ((StringLocIDType)_report.Items[index]).Value );  
  
        // Update the Description for the Report  
        ((StringLocIDType)_report.Items[index]).Value =   
            "New Report Description";  
  
        System.Console.WriteLine("- New Description: " +   
            ((StringLocIDType)_report.Items[index]).Value );  
    }  
    ```  
  
    ```vb  
    Private Sub UpdateReportDefinition()  
  
        System.Console.WriteLine("Updating Report Definition")  
  
        'Create a list of the Items Choices for the Report. The   
        'ItemsChoiceType118 enum represents all the properties  
        'available in the report and the ItemsElementName   
        'represents the properties that exist in the current   
        'instance of the report.  
        Dim reportItems As List(Of ItemsChoiceType118) = _  
            New List(Of ItemsChoiceType118)(m_report.ItemsElementName)  
  
        'Locate the index for the Description property  
        Dim index As Integer = _  
            reportItems.IndexOf(ItemsChoiceType118.Description)  
  
        'The Description item is of type StringLocIDType, so   
        'cast the item type first and then assign new value.  
        System.Console.WriteLine("- Old Description: " & _  
            DirectCast(m_report.Items(index), StringLocIDType).Value)  
  
        'Update the Description for the Report  
        DirectCast(m_report.Items(index), StringLocIDType).Value = _  
            "New Report Description"  
  
        System.Console.WriteLine("- New Description: " & _  
            DirectCast(m_report.Items(index), StringLocIDType).Value)  
  
    End Sub  
    ```  
  
## <a name="next-lesson"></a><span data-ttu-id="1352b-107">Nächste Lektion</span><span class="sxs-lookup"><span data-stu-id="1352b-107">Next Lesson</span></span>  
 <span data-ttu-id="1352b-108">In der nächsten Lektion speichern Sie die aktualisierte Berichtsdefinition wieder auf dem Berichtsserver.</span><span class="sxs-lookup"><span data-stu-id="1352b-108">In the next lesson, you will save the updated report definition back to the report server.</span></span> <span data-ttu-id="1352b-109">Weitere Informationen finden [Sie unter Lektion 5: Veröffentlichen der Berichts Definition auf dem Berichts Server](../../2014/tutorials/lesson-5-publish-the-report-definition-to-the-report-server.md).</span><span class="sxs-lookup"><span data-stu-id="1352b-109">See [Lesson 5: Publish the Report Definition to the Report Server](../../2014/tutorials/lesson-5-publish-the-report-definition-to-the-report-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1352b-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1352b-110">See Also</span></span>  
 [<span data-ttu-id="1352b-111">Aktualisieren von Berichten mithilfe von Klassen, die aus dem RDL-Schema &#40;SSRS-Tutorial generiert wurden&#41;</span><span class="sxs-lookup"><span data-stu-id="1352b-111">Updating Reports Using Classes Generated from the RDL Schema &#40;SSRS Tutorial&#41;</span></span>](../../2014/tutorials/updating-reports-using-classes-generated-from-the-rdl-schema-ssrs-tutorial.md)  
  
  
