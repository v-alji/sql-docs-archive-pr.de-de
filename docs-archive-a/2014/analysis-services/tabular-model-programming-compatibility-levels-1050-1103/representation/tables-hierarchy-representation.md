---
title: Hierarchie Darstellung (tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 1d53dda1-f2c8-4a9b-8ec7-78f43ca1d7db
author: minewiskan
ms.author: owend
ms.openlocfilehash: 83d91be5152c4e7f1345cee8756abbe57c0016f0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87610088"
---
# <a name="hierarchy-representation-tabular"></a><span data-ttu-id="54012-102">Hierarchiedarstellung (tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="54012-102">Hierarchy Representation (Tabular)</span></span>
  <span data-ttu-id="54012-103">In tabellarischen Modellen stellt eine Hierarchie einen Navigationspfad von einem Attribut zu einem anderen dar, der auf Werten basiert, die vom Benutzer ausgewählt wurden.</span><span class="sxs-lookup"><span data-stu-id="54012-103">In tabular models a hierarchy is navigation path from one attribute to another based on values selected by the user.</span></span>  
  
## <a name="hierarchy-representation"></a><span data-ttu-id="54012-104">Hierarchiedarstellung</span><span class="sxs-lookup"><span data-stu-id="54012-104">Hierarchy Representation</span></span>  
  
### <a name="hierarchy-in-amo"></a><span data-ttu-id="54012-105">Hierarchie in AMO</span><span class="sxs-lookup"><span data-stu-id="54012-105">Hierarchy in AMO</span></span>  
 <span data-ttu-id="54012-106">Wenn AMO zum Verwalten einer Tabelle für ein tabellarisches Modell verwendet wird, besteht eine 1:1-Objektentsprechung zu einer Hierarchie in AMO.</span><span class="sxs-lookup"><span data-stu-id="54012-106">When using AMO to manage a tabular model table, there is a one-to-one object match for a hierarchy in AMO.</span></span> <span data-ttu-id="54012-107">Eine Hierarchie wird durch das <xref:Microsoft.AnalysisServices.Hierarchy>-Objekt dargestellt.</span><span class="sxs-lookup"><span data-stu-id="54012-107">A hierarchy is represented by the <xref:Microsoft.AnalysisServices.Hierarchy> object.</span></span>  
  
 <span data-ttu-id="54012-108">Der folgende Codeausschnitt veranschaulicht, wie einem vorhandenen tabellarischen Modell eine Hierarchie hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="54012-108">The following code snippet shows how to add a hierarchy to an existing tabular model.</span></span> <span data-ttu-id="54012-109">Im Code wird davon ausgegangen, dass Sie über das AMO-Datenbankobjekt newDatabase und das AMO-Cubeobjekt modelCube verfügen.</span><span class="sxs-lookup"><span data-stu-id="54012-109">The code assumes you have an AMO database object, newDatabase, and an AMO cube object, modelCube.</span></span>  
  
```  
  
private void addHierarchy(  
                    AMO.Database newDatabase  
                 ,  AMO.Cube modelCube  
                 ,  string tableName  
                 ,  string hierarchyName  
                 ,  string levelsText  
             )  
{  
    //Validate input  
    if (string.IsNullOrEmpty(hierarchyName) || string.IsNullOrEmpty(levelsText))  
    {  
        MessageBox.Show(String.Format("Hierarchy Name or Layout must be provided."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Warning);  
        return;  
    }  
  
    if (!overwriteHierarchy.Checked && newDatabase.Dimensions[tableName].Hierarchies.Contains(hierarchyName))  
    {  
        MessageBox.Show(String.Format("Hierarchy already exists.\nGive a new name or enable overwriting"), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Warning);  
        return;  
    }  
  
    try  
    {  
        if (newDatabase.Dimensions[tableName].Hierarchies.Contains(hierarchyName))  
        {  
            //Hierarchy exists... deleting it to write it later  
            newDatabase.Dimensions[tableName].Hierarchies.Remove(hierarchyName, true);  
            newDatabase.Dimensions[tableName].Update(AMO.UpdateOptions.AlterDependents);  
        }  
        AMO.Hierarchy currentHierarchy = newDatabase.Dimensions[tableName].Hierarchies.Add(hierarchyName, hierarchyName);  
        currentHierarchy.AllMemberName = string.Format("(All of {0})", hierarchyName);  
        //Parse hierarchyLayout  
        using (StringReader levels = new StringReader(levelsText))  
        {  
            //Each line:  
            //  must come with: The columnId of the attribute in the dimension --> this represents the SourceAttributeID  
            //  optional: A display name for the Level (if this argument doesn't come the default is the SourceAttributeID)  
            string line;  
            while ((line = levels.ReadLine()) != null)  
            {  
                if (string.IsNullOrEmpty(line) || string.IsNullOrWhiteSpace(line)) continue;  
                line = line.Trim();  
                string[] hierarchyData = line.Split(',');  
                if (string.IsNullOrEmpty(hierarchyData[0])) continue; //first argument cannot be empty or blank,   
                                                                      //assume is a blank line and ignore it  
                string levelSourceAttributeID = hierarchyData[0].Trim();  
                string levelID = (hierarchyData.Length > 1 && !string.IsNullOrEmpty(hierarchyData[1])) ? hierarchyData[1].Trim() : levelSourceAttributeID;  
                currentHierarchy.Levels.Add(levelID).SourceAttributeID = levelSourceAttributeID;  
            }  
        }  
        newDatabase.Dimensions[tableName].Update(AMO.UpdateOptions.AlterDependents);  
  
    }  
    catch (Exception ex)  
    {  
        MessageBox.Show(String.Format("Error creating hierarchy [{0}].\nError message: {1}", newHierarchyName.Text, ex.Message), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Warning);  
        if (newDatabase.Dimensions[tableName].Hierarchies.Contains(hierarchyName))  
        {  
            //Hierarchy was created but exception prevented complete hierarchy to be written... deleting incomplete hierarchy  
            newDatabase.Dimensions[tableName].Hierarchies.Remove(hierarchyName, true);  
            newDatabase.Dimensions[tableName].Update(AMO.UpdateOptions.AlterDependents);  
        }  
  
    }  
    newDatabase.Dimensions[tableName].Process(AMO.ProcessType.ProcessFull);  
    modelCube.MeasureGroups[tableName].Process(AMO.ProcessType.ProcessFull);  
}  
  
```  
  
  
