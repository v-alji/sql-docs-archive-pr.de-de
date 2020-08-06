---
title: Aus Power Pivot wiederherstellen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
f1_keywords:
- sql11.asvs.ssmsimbi.RestoreFromPP.f1
ms.assetid: 232ac8ed-77fe-47d8-acd3-59bc2fdfdf48
author: minewiskan
ms.author: owend
ms.openlocfilehash: 4dbb0e7867451e67eaa1503c54d7e3da1c276965
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723114"
---
# <a name="restore-from-powerpivot"></a><span data-ttu-id="6fc29-102">Von PowerPivot wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="6fc29-102">Restore from PowerPivot</span></span>
  <span data-ttu-id="6fc29-103">Sie können die Funktion Von PowerPivot wiederherstellen in SQL Server Management Studio verwenden, um eine neue Datenbank für tabellarische Modelle auf einer (im Tabellenmodus ausgeführte) Analysis Services-Instanz zu erstellen oder um eine vorhandene Datenbank aus einer PowerPivot-Arbeitsmappe (.xlsx) wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="6fc29-103">You can use the Restore from PowerPivot feature in SQL Server Management Studio to create a new Tabular model database on an Analysis Services instance (running in Tabular mode), or restore to an existing database from a PowerPivot workbook (.xlsx).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6fc29-104">Die Projektvorlage Aus PowerPivot importieren in SQL Server Data Tools verfügt über ähnliche Funktionen.</span><span class="sxs-lookup"><span data-stu-id="6fc29-104">The Import from PowerPivot project template in SQL Server Data Tools provides similar functionality.</span></span> <span data-ttu-id="6fc29-105">Weitere Informationen finden Sie unter [Importieren aus Power Pivot &#40;tabellarischen SSAS-&#41;](import-from-power-pivot-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="6fc29-105">For more information, see [Import from PowerPivot &#40;SSAS Tabular&#41;](import-from-power-pivot-ssas-tabular.md).</span></span>  
  
 <span data-ttu-id="6fc29-106">Folgendes sollte bei Verwendung der Funktion Von PowerPivot wiederherstellen beachtet werden:</span><span class="sxs-lookup"><span data-stu-id="6fc29-106">When using Restore from PowerPivot, keep the following in mind:</span></span>  
  
-   <span data-ttu-id="6fc29-107">Um die Funktion Von PowerPivot wiederherstellen zu verwenden, müssen Sie als Mitglied der Rolle Serveradministrator bei der Analysis Services-Instanz angemeldet sein.</span><span class="sxs-lookup"><span data-stu-id="6fc29-107">In order to use Restore from PowerPivot, you must be logged on as a member of the Server Administrators role on the Analysis Services instance.</span></span>  
  
-   <span data-ttu-id="6fc29-108">Das Dienstkonto der Analysis Services-Instanz muss über Leseberechtigungen für die Arbeitsmappendatei verfügen, aus der Daten wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6fc29-108">The Analysis Services instance service account must have Read permissions on the workbook file you are restoring from.</span></span>  
  
-   <span data-ttu-id="6fc29-109">Wenn Sie eine Datenbank von PowerPivot wiederherstellen, ist die Eigenschaft Identitätswechselinformationen der Datenquelle der Datenbank für tabellarische Modelle auf den Standardwert festgelegt, der dem Dienstkonto der Analysis Services-Instanz entspricht.</span><span class="sxs-lookup"><span data-stu-id="6fc29-109">By default, when you restore a database from PowerPivot, the Tabular model database Data Source Impersonation Info property is set to Default, which specifies the Analysis Services instance service account.</span></span> <span data-ttu-id="6fc29-110">Es wird empfohlen, die Identitätswechsel-Anmeldeinformationen in den Datenbankeigenschaften in ein Windows-Benutzerkonto zu ändern.</span><span class="sxs-lookup"><span data-stu-id="6fc29-110">It is recommended you change the impersonation credentials to a Windows user account in Database Properties.</span></span> <span data-ttu-id="6fc29-111">Weitere Informationen finden Sie unter [Identitätswechsel &#40;SSAS – tabellarisch&#41;](impersonation-ssas-tabular.md).</span><span class="sxs-lookup"><span data-stu-id="6fc29-111">For more information, see [Impersonation &#40;SSAS Tabular&#41;](impersonation-ssas-tabular.md).</span></span>  
  
-   <span data-ttu-id="6fc29-112">Daten im PowerPivot-Datenmodell werden in eine vorhandene oder neue Datenbank für tabellarische Modelle auf der Analysis Services-Instanz kopiert.</span><span class="sxs-lookup"><span data-stu-id="6fc29-112">Data in the PowerPivot data model will be copied into an existing or new Tabular model database on the Analysis Services instance.</span></span> <span data-ttu-id="6fc29-113">Wenn die PowerPivot-Arbeitsmappe verknüpfte Tabellen enthält, werden sie ähnlich wie eine Tabelle, die mit In neue Tabelle einfügen erstellt wurde, als Tabelle ohne Datenquelle neu erstellt.</span><span class="sxs-lookup"><span data-stu-id="6fc29-113">If your PowerPivot workbook contains linked tables, they will be recreated as a table without a data source, similar to a table created using Paste To New table.</span></span>  
  
### <a name="to-restore-from-powerpivot"></a><span data-ttu-id="6fc29-114">So stellen Sie Daten von PowerPivot wieder her</span><span class="sxs-lookup"><span data-stu-id="6fc29-114">To Restore from PowerPivot</span></span>  
  
1.  <span data-ttu-id="6fc29-115">Klicken Sie in SSMS in der Active Directory Instanz, die Sie wiederherstellen möchten, mit der rechten Maustaste auf **Datenbanken**, und klicken Sie dann auf **aus Power Pivot wiederherstellen**.</span><span class="sxs-lookup"><span data-stu-id="6fc29-115">In SSMS, in the Active Directory instance you want to restore to, right click **Databases**, and then click **Restore from PowerPivot**.</span></span>  
  
2.  <span data-ttu-id="6fc29-116">Klicken Sie im Dialogfeld **von Power Pivot wiederherstellen** unter **Wiederherstellungs Quelle**in **Sicherungsdatei**auf **Durchsuchen**, und wählen Sie dann eine ABF-oder XSLX-Datei aus, aus der wieder hergestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="6fc29-116">In the **Restore from PowerPivot** dialog box, in **Restore Source**, in **Backup file**, click **Browse**, and then select an .abf or .xslx file to restore from.</span></span>  
  
3.  <span data-ttu-id="6fc29-117">Geben Sie in **Datenbank wiederherstellen**unter **Wiederherstellungsziel**den Namen einer neuen oder vorhandenen Datenbank ein.</span><span class="sxs-lookup"><span data-stu-id="6fc29-117">In **Restore Target**, in **Restore database**, type a name for a new database or for an existing database.</span></span> <span data-ttu-id="6fc29-118">Wenn Sie keinen Namen angeben, wird der Name der Arbeitsmappe verwendet.</span><span class="sxs-lookup"><span data-stu-id="6fc29-118">If you do not specify a name, the name of the workbook is used.</span></span>  
  
4.  <span data-ttu-id="6fc29-119">Klicken Sie unter **Speicherort**auf **Durchsuchen**, und wählen Sie anschließend einen Ort zum Speichern der Datenbank aus.</span><span class="sxs-lookup"><span data-stu-id="6fc29-119">In **Storage location**, click **Browse**, and then select a location to store the database.</span></span>  
  
5.  <span data-ttu-id="6fc29-120">Lassen Sie unter **Optionen**das Kontrollkästchen **Sicherheitsinformationen einschließen** aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6fc29-120">In **Options**, leave **Include security information** checked.</span></span> <span data-ttu-id="6fc29-121">Diese Einstellung gilt nicht beim Wiederherstellen von Daten aus einer PowerPivot-Arbeitsmappe.</span><span class="sxs-lookup"><span data-stu-id="6fc29-121">When restoring from a PowerPivot workbook, this setting does not apply.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fc29-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6fc29-122">See Also</span></span>  
 <span data-ttu-id="6fc29-123">[Tabellarische Modell Datenbanken &#40;tabellarischen SSAS-&#41;](tabular-model-databases-ssas-tabular.md) </span><span class="sxs-lookup"><span data-stu-id="6fc29-123">[Tabular Model Databases &#40;SSAS Tabular&#41;](tabular-model-databases-ssas-tabular.md) </span></span>  
 [<span data-ttu-id="6fc29-124">Aus Power Pivot &#40;tabellarischen SSAS-&#41;importieren</span><span class="sxs-lookup"><span data-stu-id="6fc29-124">Import from PowerPivot &#40;SSAS Tabular&#41;</span></span>](import-from-power-pivot-ssas-tabular.md)  
  
  
