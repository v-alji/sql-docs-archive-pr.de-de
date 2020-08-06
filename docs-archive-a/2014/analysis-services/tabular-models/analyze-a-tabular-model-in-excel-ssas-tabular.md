---
title: Analysieren eines tabellarischen Modells in Excel (SSAS-tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql12.asvs.bidtoolset.chooseperspect.f1
ms.assetid: 47fa45fc-60ab-41a1-bde3-5781c8462889
author: minewiskan
ms.author: owend
ms.openlocfilehash: fae542ffb5b470d23d9cf27fcc11367f571e7cec
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620527"
---
# <a name="analyze-a-tabular-model-in-excel-ssas-tabular"></a><span data-ttu-id="7f578-102">Analysieren eines Tabellenmodells in Excel (SSAS – tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="7f578-102">Analyze a Tabular Model in Excel (SSAS Tabular)</span></span>
  <span data-ttu-id="7f578-103">Über die Funktion In Excel analysieren in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] wird Microsoft Excel geöffnet, eine Datenquellenverbindung mit der Arbeitsbereichsdatenbank des Modells hergestellt und eine PivotTable in das Arbeitsblatt eingefügt.</span><span class="sxs-lookup"><span data-stu-id="7f578-103">The Analyze in Excel feature in [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)] opens Microsoft Excel, creates a data source connection to the model workspace database, and adds a PivotTable to the worksheet.</span></span> <span data-ttu-id="7f578-104">Modellobjekte (Tabellen, Spalten, Measures, Hierarchien und KPIs) sind als Felder in der PivotTable-Feldliste enthalten.</span><span class="sxs-lookup"><span data-stu-id="7f578-104">Model objects (tables, columns, measures, hierarchies, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f578-105">Um die Funktion In Excel analysieren zu verwenden, muss Microsoft Office 2003 oder höher auf demselben Computer wie [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]installiert sein.</span><span class="sxs-lookup"><span data-stu-id="7f578-105">To use the Analyze in Excel feature, you must have Microsoft Office 2003 or later installed on the same computer as [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)].</span></span> <span data-ttu-id="7f578-106">Wenn Office nicht auf demselben Computer installiert ist, können Sie Excel auf einem anderen Computer verwenden und eine Datenquellenverbindung mit der Arbeitsbereichsdatenbank des Modells herstellen.</span><span class="sxs-lookup"><span data-stu-id="7f578-106">If Office is not installed on the same computer, you can use Excel on another computer and connect to the model workspace database as a data source.</span></span> <span data-ttu-id="7f578-107">Sie können dem Arbeitsblatt dann manuell eine PivotTable hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="7f578-107">You can then manually add a PivotTable to the worksheet.</span></span> <span data-ttu-id="7f578-108">Modellobjekte (Tabellen, Spalten, Measures und KPIs) sind als Felder in der PivotTable-Feldliste enthalten.</span><span class="sxs-lookup"><span data-stu-id="7f578-108">Model objects (tables, columns, measures, and KPIs) are included as fields in the PivotTable field list.</span></span>  
  
## <a name="tasks"></a><span data-ttu-id="7f578-109">Aufgaben</span><span class="sxs-lookup"><span data-stu-id="7f578-109">Tasks</span></span>  
  
#### <a name="to-analyze-a-tabular-model-project-by-using-the-analyze-in-excel-feature"></a><span data-ttu-id="7f578-110">So analysieren Sie ein tabellarisches Modellprojekt mithilfe der Funktion "In Excel analysieren"</span><span class="sxs-lookup"><span data-stu-id="7f578-110">To analyze a tabular model project by using the Analyze in Excel feature</span></span>  
  
1.  <span data-ttu-id="7f578-111">Klicken Sie in [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)]auf das Menü **Modell** und dann auf **In Excel analysieren**.</span><span class="sxs-lookup"><span data-stu-id="7f578-111">In [!INCLUDE[ssBIDevStudio](../../includes/ssbidevstudio-md.md)], click the **Model** menu, and then click **Analyze in Excel**.</span></span>  
  
2.  <span data-ttu-id="7f578-112">Wählen Sie im Dialogfeld **Anmeldeinformationen und Perspektive auswählen** eine der folgenden Optionen für Anmeldeinformationen aus, um eine Verbindung mit der Arbeitsbereichsdatenquelle des Modells herzustellen:</span><span class="sxs-lookup"><span data-stu-id="7f578-112">In the **Choose Credential and Perspective** dialog box, select one of the following credential options to connect to the model workspace data source:</span></span>  
  
    -   <span data-ttu-id="7f578-113">Um das aktuelle Benutzerkonto zu verwenden, wählen Sie **Aktueller Windows-Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="7f578-113">To use the current user account, select **Current Windows User**.</span></span>  
  
    -   <span data-ttu-id="7f578-114">Um ein anderes Benutzerkonto zu verwenden, wählen Sie **Anderer Windows-Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="7f578-114">To use a different user account, select **Other Windows User**.</span></span>  
  
         <span data-ttu-id="7f578-115">In der Regel ist dieser Benutzer Mitglied einer Rolle.</span><span class="sxs-lookup"><span data-stu-id="7f578-115">Typically, this user account will be a member of a role.</span></span> <span data-ttu-id="7f578-116">Es ist kein Kennwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="7f578-116">No password is required.</span></span> <span data-ttu-id="7f578-117">Das Konto kann nur im Kontext einer Excel-Verbindung mit der Arbeitsbereichsdatenbank verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7f578-117">The account can only be used in the context of an Excel connection to the workspace database.</span></span>  
  
    -   <span data-ttu-id="7f578-118">Um eine Sicherheitsrolle zu verwenden, wählen Sie **Rolle**und anschließend mindestens eine Rolle im Listenfeld aus.</span><span class="sxs-lookup"><span data-stu-id="7f578-118">To use a security role, select **Role**, and then in the listbox, select one or more roles.</span></span>  
  
         <span data-ttu-id="7f578-119">Sicherheitsrollen müssen mit dem Rollen-Manager definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7f578-119">Security roles must be defined using the Role Manager.</span></span> <span data-ttu-id="7f578-120">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen &#40;SSAS – tabellarisch&#41;](roles-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="7f578-120">For more information, see [Create and Manage Roles &#40;SSAS Tabular&#41;](roles-ssas-tabular.md).</span></span>  
  
3.  <span data-ttu-id="7f578-121">Um eine Perspektive aus dem Listenfeld **Perspektive** zu verwenden, wählen Sie die Perspektive aus.</span><span class="sxs-lookup"><span data-stu-id="7f578-121">To use a perspective, in the **Perspective** listbox, select a perspective.</span></span>  
  
     <span data-ttu-id="7f578-122">Perspektiven (mit Ausnahme der Standardeinstellung) müssen im Dialogfeld Perspektiven definiert werden.</span><span class="sxs-lookup"><span data-stu-id="7f578-122">Perspectives (other than default) must be defined using the Perspectives dialog box.</span></span> <span data-ttu-id="7f578-123">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Perspektiven &#40;tabellarischen SSAS-&#41;](perspectives-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="7f578-123">For more information, see [Create and Manage Perspectives &#40;SSAS Tabular&#41;](perspectives-ssas-tabular.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7f578-124">Die PivotTable-Feldliste in Excel wird nicht automatisch aktualisiert, wenn Sie im Modell-Designer Änderungen am Modellprojekt vornehmen.</span><span class="sxs-lookup"><span data-stu-id="7f578-124">The PivotTable Field List in Excel does not refresh automatically as you make changes to the model project in the model designer.</span></span> <span data-ttu-id="7f578-125">Um die PivotTable-Feldliste zu aktualisieren, klicken Sie in Excel im Menüband **Optionen** auf **Aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="7f578-125">To refresh the PivotTable Field List, in Excel, on the **Options** ribbon, click **Refresh**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f578-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7f578-126">See Also</span></span>  
 [<span data-ttu-id="7f578-127">Analysieren in Excel &#40;SSAS – tabellarisch&#41;</span><span class="sxs-lookup"><span data-stu-id="7f578-127">Analyze in Excel &#40;SSAS Tabular&#41;</span></span>](analyze-in-excel-ssas-tabular.md)  
  
  
