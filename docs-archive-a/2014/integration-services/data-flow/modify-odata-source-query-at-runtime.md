---
title: Ändern der odata-Quell Abfrage zur Laufzeit | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: bcbba7f4-6e5d-46e6-a73a-3f17d3ff376a
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b3dbc4d27f2d11537a9d66980ef6ca59b80811b2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724825"
---
# <a name="modify-odata-source-query-at-runtime"></a><span data-ttu-id="8ecc6-102">Ändern einer OData-Quellabfrage zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="8ecc6-102">Modify OData Source Query at Runtime</span></span>
  <span data-ttu-id="8ecc6-103">Sie können die OData-Quellabfrage zur Laufzeit ändern, indem Sie der Eigenschaft [OData-Quelle].[Abfrage] des Datenflusstasks einen **Ausdruck** hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-103">You can modify the OData Source query at runtime by adding an expression to the **[OData Source].[Query]** property of the Data Flow task.</span></span>  
  
 <span data-ttu-id="8ecc6-104">Beachten Sie, dass die Spalten gegenüber der Entwurfszeit unverändert bleiben müssen, da bei der Paketausführung ansonsten ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-104">Note that the columns must remain the same as what was used at design time; otherwise you will get an error when the package is executed.</span></span> <span data-ttu-id="8ecc6-105">Geben Sie bei Verwendung der $select-Abfrageoption die gleichen Spalten (in der gleichen Reihenfolge) an.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-105">Be sure to specify the same columns (in the same order) when using the $select query option.</span></span> <span data-ttu-id="8ecc6-106">Eine sicherere Alternative zur Verwendung der $select-Option besteht darin, die nicht benötigten Spalten direkt über die Benutzeroberfläche der Quellkomponente zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-106">A safer alternative to using the $select option is to deselect the columns you don't want directly from the Source Component UI.</span></span>  
  
 <span data-ttu-id="8ecc6-107">Es gibt einige verschiedene Möglichkeiten, den Abfragewert zur Laufzeit dynamisch festzulegen.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-107">There are a few different ways of dynamically setting the query value at runtime.</span></span> <span data-ttu-id="8ecc6-108">Im Folgenden sind einige der gängigeren Methoden beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-108">Below are some of the more common methods.</span></span>  
  
## <a name="exposing-the-query-as-a-parameter"></a><span data-ttu-id="8ecc6-109">Verfügbarmachen der Abfrage als Parameter</span><span class="sxs-lookup"><span data-stu-id="8ecc6-109">Exposing the Query as a Parameter</span></span>  
 <span data-ttu-id="8ecc6-110">Anhand der folgenden Schritte können Sie eine Abfrage, die von der OData-Quellkomponente als Parameter verwendet wird, für das Paket verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-110">The following procedure has steps to expose query used by an OData Source component as a parameter to the package.</span></span>  
  
1.  <span data-ttu-id="8ecc6-111">Klicken Sie mit der rechten Maustaste auf **Datenflusstask**, und wählen Sie die Option **Parametrisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-111">Right click on the **Data Flow task** and select the **Parameterize...** option.</span></span>  
  
2.  <span data-ttu-id="8ecc6-112">Wählen Sie im Dialogfeld **Parametrisieren** für **Eigenschaft** **[\<Name of the OData Source Component>].[Abfrage]** aus.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-112">In the **Parameterize** dialog, select **[\<Name of the OData Source Component>].[Query]** for **Property**.</span></span>  
  
3.  <span data-ttu-id="8ecc6-113">Wählen Sie **Neuen Parameter erstellen** oder **Vorhandenen Parameter verwenden**aus.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-113">Choose whether to **create new parameter** or **use an existing parameter**.</span></span>  
  
4.  <span data-ttu-id="8ecc6-114">Wenn Sie **Neuen Parameter erstellen**auswählen, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="8ecc6-114">If you select **Create new parameter**, do the following:</span></span>  
  
    1.  <span data-ttu-id="8ecc6-115">Geben Sie den **Name** und eine **Beschreibung** für den Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-115">Enter **name** and **description** for the parameter.</span></span>  
  
    2.  <span data-ttu-id="8ecc6-116">Geben Sie den standardmäßigen **Wert** für den Parameter ein.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-116">Specify default **value** for the parameter.</span></span>  
  
    3.  <span data-ttu-id="8ecc6-117">Geben Sie den **Bereich** (**Paket** oder **Projekt**) für den Parameter an.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-117">Specify the **scope** (**package** or **project**) for the parameter.</span></span>  
  
    4.  <span data-ttu-id="8ecc6-118">Geben Sie an, ob der Parameter **erforderlich** ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-118">Specify whether the parameter is **required** or not</span></span>  
  
5.  <span data-ttu-id="8ecc6-119">Klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-119">Click **OK** to close the dialog box.</span></span>  
  
## <a name="using-an-expression"></a><span data-ttu-id="8ecc6-120">Verwenden eines Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="8ecc6-120">Using an Expression</span></span>  
 <span data-ttu-id="8ecc6-121">Diese Methode ist hilfreich, wenn Sie eine Abfragezeichenfolge zur Laufzeit dynamisch erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-121">This method is useful when you want to dynamically construct query string at runtime.</span></span> <span data-ttu-id="8ecc6-122">In diesem Beispiel wird die MaxRows-Variable auf andere Weise (Skript, Parameter usw.) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-122">In this example, MaxRows variable will be set through other means (script, parameter, etc).</span></span>  
  
1.  <span data-ttu-id="8ecc6-123">Wählen Sie den **Datenflusstask** aus, der die **OData-Quelle**enthält.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-123">Select the **Data Flow Task** which contains your **OData Source**.</span></span>  
  
2.  <span data-ttu-id="8ecc6-124">Heben Sie im Fenster **Eigenschaften** die Eigenschaft **Ausdrücke** hervor.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-124">In the **Properties** window, highlight the **Expressions** property.</span></span>  
  
3.  <span data-ttu-id="8ecc6-125">Klicken Sie auf... (Ellipsen), um den **Eigenschafts Ausdrucks-Editor**zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-125">Click the ... (ellipses) button to bring up the **Property Expressions Editor**.</span></span>  
  
4.  <span data-ttu-id="8ecc6-126">Wählen Sie die Eigenschaft **[OData-Quelle].[Abfrage]** aus.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-126">Select the **[OData Source].[Query]** property.</span></span>  
  
5.  <span data-ttu-id="8ecc6-127">Klicken Sie auf... (Ellipsen) Schaltfläche für **Ausdruck**.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-127">Click the ... (ellipses) button for **Expression**.</span></span>  
  
6.  <span data-ttu-id="8ecc6-128">Geben Sie den **Ausdruck**ein.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-128">Enter the **expression**.</span></span>  
  
7.  <span data-ttu-id="8ecc6-129">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-129">Click **OK**.</span></span>  
  
> [!WARNING]  
>  <span data-ttu-id="8ecc6-130">Beachten Sie bei Verwendung dieser Methode, dass die festgelegten Werte ordnungsgemäß URL-codiert sind.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-130">Note that when using this approach you need to ensure that the values set are properly URL encoded.</span></span> <span data-ttu-id="8ecc6-131">Bei der Übernahme der Werte aus der Benutzereingabe (z. B. der parameterbasierten Festlegung einzelner Abfrageoptionswerte) müssen Sie sicherstellen, dass die Werte überprüft werden, um potenzielle Angriffe durch die Einschleusung von SQL-Befehlen zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="8ecc6-131">When receiving values from user input (for example, setting individual query option values from a parameter), you must ensure that the values are validated to avoid potential SQL injection-type attacks.</span></span>  
  
  
