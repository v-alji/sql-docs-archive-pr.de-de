---
title: Perspektivische Darstellung (tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 6d2636c4-dae4-448f-a1d4-dbee739e177c
author: minewiskan
ms.author: owend
ms.openlocfilehash: ca8a66d3134748fd524dc0c6b524d944213533e2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616226"
---
# <a name="perspective-representation-tabular"></a><span data-ttu-id="ecf10-102">Perspektivische Darstellung (tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="ecf10-102">Perspective Representation (Tabular)</span></span>
  <span data-ttu-id="ecf10-103">Eine Perspektive ist ein Mechanismus, um das Modell zu vereinfachen oder einen kleineren Teil davon für die Clientanwendung zu fokussieren.</span><span class="sxs-lookup"><span data-stu-id="ecf10-103">A perspective is a mechanism to simplify or focus the model into a smaller portion of it for the client application.</span></span>  
  
 <span data-ttu-id="ecf10-104">Eine ausführliche Erläuterung zum Erstellen und Bearbeiten der perspektivischen Darstellung finden Sie unter [perspektivische Darstellung (tabellarisch)](perspective-representation-tabular.md) .</span><span class="sxs-lookup"><span data-stu-id="ecf10-104">See [Perspective Representation (Tabular)](perspective-representation-tabular.md) for a detailed explanation on how to create and manipulate the perspective representation.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="ecf10-105">Perspektiven sind kein Sicherheitsmechanismus; auf Objekte außerhalb der Perspektive kann immer noch vom Benutzer über andere Schnittstellen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="ecf10-105">Perspectives are not a security mechanism; objects outside the perspective can still be accessed by the user through other interfaces.</span></span>  
  
## <a name="perspective-representation"></a><span data-ttu-id="ecf10-106">Perspektivendarstellung</span><span class="sxs-lookup"><span data-stu-id="ecf10-106">Perspective Representation</span></span>  
 <span data-ttu-id="ecf10-107">Im Hinblick auf AMO-Objekte verfügt eine Perspektivendarstellung über eine 1:1-Zuordnungsbeziehung zu <xref:Microsoft.AnalysisServices.Perspective>, und es sind keine weiteren AMO-Hauptobjekte erforderlich.</span><span class="sxs-lookup"><span data-stu-id="ecf10-107">In terms of AMO objects a perspective representation has a one to one mapping relationship with <xref:Microsoft.AnalysisServices.Perspective> and no other main AMO objects are required.</span></span>  
  
### <a name="perspective-in-amo"></a><span data-ttu-id="ecf10-108">Perspektive in AMO</span><span class="sxs-lookup"><span data-stu-id="ecf10-108">Perspective in AMO</span></span>  
 <span data-ttu-id="ecf10-109">Der folgende Codeausschnitt veranschaulicht, wie eine Perspektive in einem tabellarischen Modell erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ecf10-109">The following code snippet shows how to create a perspective in a Tabular model.</span></span> <span data-ttu-id="ecf10-110">Das wichtigste Element in diesem Codeausschnitt ist perspectiveElements. Dieses Objekt ist eine grafische Darstellung aller Objekte im tabellarischen Modell, die für den Benutzer verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="ecf10-110">The key element in this piece of code is the perspectiveElements; this object is a graphical representation of all the objects in the tabular model that are exposed to the user.</span></span> <span data-ttu-id="ecf10-111">*perspectiveelements* enthält vier Spalten. in diesem Szenario sind nur die Spalten 1, 2 und 3 relevant.</span><span class="sxs-lookup"><span data-stu-id="ecf10-111">*perspectiveElements* contains 4 columns and for this scenario only columns 1, 2 and 3 are relevant.</span></span> <span data-ttu-id="ecf10-112">Spalte 1 enthält den Typ des angezeigten Elements: -elementTypeValue-. Spalte 2 enthält den vollständigen Namen des Elements, der u. U. analysiert werden muss, um das Element in die Perspektive einzufügen. Spalte 3 enthält das Kontrollkästchenelement -checkedElement-, das angibt, ob das Element Teil der Perspektive ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="ecf10-112">Column 1 contains the type of element displayed -elementTypeValue-; column 2 contains the complete name of the element --, that probably will need to parsed to enter the element in the perspective; column 3 contains a checkbox item -checkedElement- that tells if the element is part of the perspective or not.</span></span>  
  
```  
  
private void updatePerspective_Click(  
                     AMO.Cube modelCube  
                  ,  DataGridView perspectiveElements  
                  ,  string updatedPerspectiveID  
             )  
{  
    //Update is done by delete first, create new and insert after  
    //if perspective doesn't exist then create first and insert after  
    updatedPerspectiveID = updatedPerspectiveID.Trim();  
    if (modelCube.Perspectives.Contains(updatedPerspectiveID))  
    {  
        modelCube.Perspectives.Remove(updatedPerspectiveID, true);  
        newDatabase.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
    }  
    AMO.Perspective currentPerspective = modelCube.Perspectives.Add(updatedPerspectiveID, updatedPerspectiveID);  
  
    foreach (DataGridViewRow currentDGVRow in perspectiveElements.Rows)  
    {  
        bool checkedElement = (bool)currentDGVRow.Cells[3].Value;  
        if (checkedElement)  
        {  
            string elementTypeValue = currentDGVRow.Cells[1].Value.ToString();  
            string elementNameValue = currentDGVRow.Cells[2].Value.ToString();  
            switch (elementTypeValue)  
            {  
                case "Column: Attribute":  
                case "Column: Calculated Column":  
                    {  
                        string perspectiveDimensionName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string perspectiveDimensionAttributeName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        AMO.PerspectiveDimension currentPerspectiveDimension;  
                        if (!currentPerspective.Dimensions.Contains(perspectiveDimensionName))  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions.Add(perspectiveDimensionName);  
                        }  
                        else  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions[perspectiveDimensionName];  
                        }  
                        if (!currentPerspectiveDimension.Attributes.Contains(perspectiveDimensionAttributeName))  
                        {  
                            currentPerspectiveDimension.Attributes.Add(perspectiveDimensionAttributeName);  
                        }  
                    }  
                    break;  
                case "Hierarchy":  
                    {  
                        string perspectiveDimensionName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string perspectiveDimensionHierarchyName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        AMO.PerspectiveDimension currentPerspectiveDimension;  
                        if (!currentPerspective.Dimensions.Contains(perspectiveDimensionName))  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions.Add(perspectiveDimensionName);  
                        }  
                        else  
                        {  
                            currentPerspectiveDimension = currentPerspective.Dimensions[perspectiveDimensionName];  
                        }  
                        if (!currentPerspectiveDimension.Hierarchies.Contains(perspectiveDimensionHierarchyName))  
                        {  
                            currentPerspectiveDimension.Hierarchies.Add(perspectiveDimensionHierarchyName);  
                        }  
                    }  
                    break;  
                case "Measure":  
                    {  
                        string perspectiveMeasureGroupName = Regex.Match(elementNameValue, @"(?<=')(.*?)(?=')").ToString();  
                        string measureName = Regex.Match(elementNameValue, @"(?<=\[)(.*?)(?=\])").ToString();  
                        string perspectiveMeasureName = string.Format("[Measures].[{0}]", measureName);  
                        AMO.PerspectiveCalculation currentPerspectiveCalculation = new AMO.PerspectiveCalculation(perspectiveMeasureName, AMO.PerspectiveCalculationType.Member);  
                        if (!currentPerspective.Calculations.Contains(perspectiveMeasureName))  
                        {  
                            currentPerspective.Calculations.Add(currentPerspectiveCalculation);  
                        }  
                        if (modelCube.MdxScripts["MdxScript"].CalculationProperties.Contains(string.Format("KPIs.[{0}]", measureName)))  
                        {//Current Measure is also a KPI ==> will be added to the KPIs collection of the perspective  
                            AMO.PerspectiveKpi currentPerspectiveKpi = new AMO.PerspectiveKpi(perspectiveMeasureName);  
                            if (!currentPerspective.Kpis.Contains(perspectiveMeasureName))  
                            {  
                                currentPerspective.Kpis.Add(currentPerspectiveKpi);  
                            }  
                        }  
                    }  
                    break;  
                default:  
                    break;  
            }  
        }  
    }  
  
    newDatabase.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.CreateOrReplace);  
    MessageBox.Show(String.Format("Perpective successfully updated."), "AMO to Tabular message", MessageBoxButtons.OK, MessageBoxIcon.Information);  
}  
  
```  
  
## <a name="amo2tabular-sample"></a><span data-ttu-id="ecf10-113">AMO2Tabular-Beispiel</span><span class="sxs-lookup"><span data-stu-id="ecf10-113">AMO2Tabular sample</span></span>  
 <span data-ttu-id="ecf10-114">Um jedoch einen Einblick in die Verwendung von AMO zur Erstellung und Bearbeitung von Perspektivendarstellungen zu gewinnen, können Sie den Quellcode im AMO2Tabular-Beispiel einsehen.</span><span class="sxs-lookup"><span data-stu-id="ecf10-114">However, to have an understanding on how to use AMO to create and manipulate perspective representations see the source code of the AMO to Tabular sample.</span></span> <span data-ttu-id="ecf10-115">Das Beispiel ist auf Codeplex verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ecf10-115">The sample is available at Codeplex.</span></span> <span data-ttu-id="ecf10-116">Ein wichtiger Hinweis zum Code: Der Code wird nur zur Verdeutlichung für die logischen Konzepte bereitgestellt, die hier erläutert werden, und sollte nicht in einer Produktionsumgebung verwendet oder zu anderen als Lehrzwecken eingesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ecf10-116">An important note about the code: the code is provided only as a support to the logical concepts explained here and should not be used in a production environment; nor should it be used for other purpose other than the pedagogical one.</span></span>  
  
  
