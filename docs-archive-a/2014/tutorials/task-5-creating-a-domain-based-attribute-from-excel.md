---
title: 'Aufgabe 5: Erstellen eines domänenbasierten Attributs aus Excel | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 07cbc624-2c6b-4568-96e4-f18663a05d80
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: b866478150fb4c06a3c4ea1ee6c227527f963219
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87700491"
---
# <a name="task-5-creating-a-domain-based-attribute-from-excel"></a><span data-ttu-id="28e86-102">Aufgabe 5: Erstellen eines domänenbasierten Attributs aus Excel</span><span class="sxs-lookup"><span data-stu-id="28e86-102">Task 5: Creating a Domain-Based Attribute from Excel</span></span>
  <span data-ttu-id="28e86-103">In dieser Aufgabe konvertieren Sie das Attribut **State** der Entität **Supplier** in ein **domänenbasiertes Attribut**.</span><span class="sxs-lookup"><span data-stu-id="28e86-103">In this task, you convert the **State** attribute of the **Supplier** entity as a **domain-based attribute**.</span></span> <span data-ttu-id="28e86-104">Nachdem Sie das State-Attribut als domänenbasiertes Verzeichnis konfiguriert und in MDS veröffentlicht haben, wird eine neue Entität mit dem Namen **State** auf dem MDS-Server mit allen Werten in der Spalte erstellt, und das **State** -Attribut der Entität " **Supplier** " wird mit Werten aus der Entität " **State** " aufgefüllt.</span><span class="sxs-lookup"><span data-stu-id="28e86-104">After you configure the State attribute to be a domain-based one and publish it to MDS, a new entity named **State** will be created on MDS server with all the values in the column and the **State** attribute of the **Supplier** entity will be populated with values from the **State** entity.</span></span> <span data-ttu-id="28e86-105">Das Modell **Suppliers** sollte nun über zwei Entitäten verfügen: **Supplier** und **State** , wobei das **State** -Attribut der Entität **Supplier** ein domänenbasiertes Attribut ist, das von der **State** -Entität abhängt.</span><span class="sxs-lookup"><span data-stu-id="28e86-105">Now, the **Suppliers** model should have two entities: **Supplier** and **State** where the **State** attribute of the **Supplier** entity is a domain-based attribute that depends on **State** entity.</span></span>  
  
1.  <span data-ttu-id="28e86-106">Wechseln Sie zum **Excel** -Fenster, das **bereinigt wurde und #b0** geöffnet ist.</span><span class="sxs-lookup"><span data-stu-id="28e86-106">Switch to **Excel** window that has **Cleansed and Matched Suppliers.xlsx** open.</span></span>  
  
2.  <span data-ttu-id="28e86-107">Klicken Sie im Menüband auf die Schaltfläche **Aktualisieren** , um die neuesten Updates von MDS zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="28e86-107">Click **Refresh** button on the ribbon to get the latest updates from MDS.</span></span> <span data-ttu-id="28e86-108">Wenn Sie die optionale **Aufgabe 4**ausgeführt haben, sollten Sie die zwei weiteren Datensätze sehen.</span><span class="sxs-lookup"><span data-stu-id="28e86-108">You should see the two more records if you have performed the optional **Task 4**.</span></span>  
  
3.  <span data-ttu-id="28e86-109">Klicken Sie in der **Kopfzeile**auf Column Name **State** (Zelle **I1**).</span><span class="sxs-lookup"><span data-stu-id="28e86-109">Click column name **State** (cell **I1**) in the **header row**.</span></span>  
  
     <span data-ttu-id="28e86-110">![Excel – Attributeigenschaften (Schaltfläche)](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-01.jpg "Excel – Attributeigenschaften (Schaltfläche)")</span><span class="sxs-lookup"><span data-stu-id="28e86-110">![Excel - Attribute Properties Button](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-01.jpg "Excel - Attribute Properties Button")</span></span>  
  
4.  <span data-ttu-id="28e86-111">Klicken Sie im Menüband auf **Attribut Eigenschaften** .</span><span class="sxs-lookup"><span data-stu-id="28e86-111">Click **Attribute Properties** on the ribbon.</span></span>  
  
5.  <span data-ttu-id="28e86-112">Wählen Sie im Dialogfeld **Attribut Eigenschaften** für den **Attributtyp**die Option **eingeschränkte Liste (Domänen basiert)** aus.</span><span class="sxs-lookup"><span data-stu-id="28e86-112">In the **Attribute Properties** dialog box, select **Constrained list (Domain-based)** for the **Attribute type**.</span></span>  
  
6.  <span data-ttu-id="28e86-113">Geben Sie **State** als **neuen Entitäts Namen** ein, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="28e86-113">Type **State** for the **New entity name** and click **OK**.</span></span>  
  
     <span data-ttu-id="28e86-114">![Excel – Attributeigenschaften (Dialogfeld)](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-02.jpg "Excel – Attributeigenschaften (Dialogfeld)")</span><span class="sxs-lookup"><span data-stu-id="28e86-114">![Excel - Attribute Properties Dialog Box](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-02.jpg "Excel - Attribute Properties Dialog Box")</span></span>  
  
7.  <span data-ttu-id="28e86-115">In Excel sollte nun ein **Pfeil nach unten** angezeigt werden, wenn Sie auf einen beliebigen Wert in der Spalte **Status** klicken.</span><span class="sxs-lookup"><span data-stu-id="28e86-115">Now, in Excel, you should see **down arrow** when you click any value in the **State** column.</span></span> <span data-ttu-id="28e86-116">Sie können den Wert bei Bedarf über die Dropdownliste ändern.</span><span class="sxs-lookup"><span data-stu-id="28e86-116">You can change the value by using the drop-down list if you need.</span></span>  
  
     <span data-ttu-id="28e86-117">![Excel – Dropdownliste mit Bundesstaaten](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-03.jpg "Excel – Dropdownliste mit Bundesstaaten")</span><span class="sxs-lookup"><span data-stu-id="28e86-117">![Excel - Drop Down List with States](../../2014/tutorials/media/et-creatingadomainbasedattributefromexcel-03.jpg "Excel - Drop Down List with States")</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="28e86-118">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="28e86-118">Next Step</span></span>  
 [<span data-ttu-id="28e86-119">Aufgabe 6: Überprüfen, ob das domänenbasierte Attribut mithilfe von Master Data Manager erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="28e86-119">Task 6: Verify that the Domain-Based Attribute is Created using Master Data Manager</span></span>](../../2014/tutorials/task-6-verify-domain-based-attribute-master-data-manager.md)  
  
  
