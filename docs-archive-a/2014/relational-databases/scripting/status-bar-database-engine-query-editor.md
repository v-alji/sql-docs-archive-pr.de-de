---
title: Statusleiste (Abfrage-Editor der Datenbank-Engine)
ms.custom: seo-lt-2019
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
ms.assetid: e7f2d6f4-bb94-4cf5-a096-c34397e679af
author: rothja
ms.author: jroth
ms.openlocfilehash: 743ae0a4152daee19aa67f85337ae4077a3ed7f6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87620804"
---
# <a name="status-bar-database-engine-query-editor"></a><span data-ttu-id="bffdd-102">Statusleiste (Abfrage-Editor der Datenbank-Engine)</span><span class="sxs-lookup"><span data-stu-id="bffdd-102">Status Bar (Database Engine Query Editor)</span></span>
  <span data-ttu-id="bffdd-103">Die Statusleiste des [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor-Fensters kann farblich codiert sein, um so anzuzeigen, mit welcher Instanz des [!INCLUDE[ssDE](../../includes/ssde-md.md)] jedes Fenster verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="bffdd-103">The status bar of [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor windows can be color coded to indicate which instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] each window is connected to.</span></span>  
  
1.  <span data-ttu-id="bffdd-104">**Vorbereitungen:**  [Statusleistenfarben](#StatusBarColors)</span><span class="sxs-lookup"><span data-stu-id="bffdd-104">**Before you begin:**  [Status Bar Colors](#StatusBarColors)</span></span>  
  
2.  <span data-ttu-id="bffdd-105">**So legen Sie eine Serverstatusfarbe fest in:**  [Objekt-Explorer](#SetOEServerColor), [Registrierte Server](#SetRegServerColor)</span><span class="sxs-lookup"><span data-stu-id="bffdd-105">**To set a server status color in:**  [Object Explorer](#SetOEServerColor), [Registered Server](#SetRegServerColor)</span></span>  
  
3.  <span data-ttu-id="bffdd-106">**So verwenden Sie eine Statusfarbe**  [Abfrage-Editor unter Verwendung einer Serverfarbe öffnen](#OpenServerColor), [Abfrage-Editor unter Angabe einer Statusfarbe öffnen](#OpenSpecColor)</span><span class="sxs-lookup"><span data-stu-id="bffdd-106">**To use a status color:**  [Open Query Editor Using a Server Color](#OpenServerColor), [Open a Query Editor Specifying a Status Color](#OpenSpecColor)</span></span>  
  
##  <a name="status-bar-colors"></a><a name="StatusBarColors"></a> <span data-ttu-id="bffdd-107">Statusleistenfarben</span><span class="sxs-lookup"><span data-stu-id="bffdd-107">Status Bar Colors</span></span>  
 <span data-ttu-id="bffdd-108">Sie können einem bestimmten Serverknoten in entweder **Objekt-Explorer** oder **Registrierte Server**eine Statusleistenfarbe zuordnen.</span><span class="sxs-lookup"><span data-stu-id="bffdd-108">You can associate a status bar color with a specific server node in either **Object Explorer** or **Registered Servers**.</span></span> <span data-ttu-id="bffdd-109">Die Farben können nur für Serverknoten angegeben werden, die mit einer Instanz des [!INCLUDE[ssDE](../../includes/ssde-md.md)]verbunden sind, nicht aber für Serverknoten für andere SQL Server-Technologien.</span><span class="sxs-lookup"><span data-stu-id="bffdd-109">The colors can only be specified for server nodes connected to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)], not server nodes for other SQL Server technologies.</span></span> <span data-ttu-id="bffdd-110">Ebenso können Sie eine benutzerdefinierte Statusleistenfarbe angeben, wann immer Sie ein neues [!INCLUDE[ssDE](../../includes/ssde-md.md)] -Abfrage-Editor-Fenster mit einer Instanz des [!INCLUDE[ssDE](../../includes/ssde-md.md)]verbinden.</span><span class="sxs-lookup"><span data-stu-id="bffdd-110">You can also specify a custom status bar color each time you connect a new [!INCLUDE[ssDE](../../includes/ssde-md.md)] Query Editor window to an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)].</span></span> <span data-ttu-id="bffdd-111">Sie können dann entweder mit der für den Serverknoten definierten Statusfarbe ein Abfrage-Editor-Fenster öffnen oder eine eindeutige Farbe für dieses Editorfenster angeben.</span><span class="sxs-lookup"><span data-stu-id="bffdd-111">You can then open a query editor window using either the status color defined for the server node, or specify a unique color for that editor window.</span></span>  
  
 <span data-ttu-id="bffdd-112">Eine benutzerdefinierte Statusleistenfarbe für einen Serverknoten in Objekt-Explorer muss beim Herstellen der Verbindung festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="bffdd-112">Setting a custom status bar color for a server node in Object Explorer must be done when making the connection.</span></span> <span data-ttu-id="bffdd-113">Um die einem vorhandenen Serverknoten zugeordnete Farbe zu ändern, müssen Sie die Verbindung trennen und dann unter Angabe der neuen Farbe die Verbindung erneut herstellen.</span><span class="sxs-lookup"><span data-stu-id="bffdd-113">To change the color associated with an existing server node, you must disconnect and then reconnect specifying the new color.</span></span>  
  
##  <a name="set-the-status-color-for-a-server-in-object-explorer"></a><a name="SetOEServerColor"></a> <span data-ttu-id="bffdd-114">Festlegen der Statusfarbe für einen Server in Objekt-Explorer</span><span class="sxs-lookup"><span data-stu-id="bffdd-114">Set the Status Color for a Server in Object Explorer</span></span>  
 <span data-ttu-id="bffdd-115">**So legen Sie eine Serverstatusfarbe in Objekt-Explorer fest**</span><span class="sxs-lookup"><span data-stu-id="bffdd-115">**To set a server status color in Object Explorer**</span></span>  
  
1.  <span data-ttu-id="bffdd-116">Wählen Sie im **Objekt-Explorer** die Schaltfläche **Verbinden** und dann **Datenbank-Engine...** aus.</span><span class="sxs-lookup"><span data-stu-id="bffdd-116">In **Object Explorer**, select the **Connect** button and then select **Database Engine...**.</span></span>  
  
2.  <span data-ttu-id="bffdd-117">Wählen Sie im Dialogfeld **Verbindung mit Server herstellen** die Option **Optionen >>** .</span><span class="sxs-lookup"><span data-stu-id="bffdd-117">On the **Connect to Server** dialog, select **Options >>**.</span></span>  
  
3.  <span data-ttu-id="bffdd-118">Aktivieren Sie das Kontrollkästchen **Benutzerdefinierte Farbe verwenden** .</span><span class="sxs-lookup"><span data-stu-id="bffdd-118">Select the **Use custom color** check box.</span></span>  
  
4.  <span data-ttu-id="bffdd-119">Wählen Sie zur Festlegung der Farbe die Schaltfläche **Auswählen...** aus.</span><span class="sxs-lookup"><span data-stu-id="bffdd-119">To select the color, select the **Select...** button.</span></span>  
  
5.  <span data-ttu-id="bffdd-120">Wählen Sie entweder eine standardmäßige oder benutzerdefinierte Farbe aus und klicken Sie dann auf OK.</span><span class="sxs-lookup"><span data-stu-id="bffdd-120">Select either a basic or custom color, then select OK.</span></span>  
  
6.  <span data-ttu-id="bffdd-121">Geben Sie die restlichen Verbindungsinformationen ein und wählen Sie dann die Schaltfläche **Verbinden** aus.</span><span class="sxs-lookup"><span data-stu-id="bffdd-121">Fill in the rest of the connection information, and then select the **Connect** button.</span></span>  
  
##  <a name="set-the-status-color-for-a-registered-server"></a><a name="SetRegServerColor"></a> <span data-ttu-id="bffdd-122">Festlegen der Statusfarbe für einen Registrierter Server</span><span class="sxs-lookup"><span data-stu-id="bffdd-122">Set the Status Color For a Registered Server</span></span>  
 <span data-ttu-id="bffdd-123">**So legen Sie eine Serverfarbe für einen Registrierten Server fest**</span><span class="sxs-lookup"><span data-stu-id="bffdd-123">**To set a server color For a Registered Server**</span></span>  
  
1.  <span data-ttu-id="bffdd-124">Klicken Sie unter **Registrierte Server** mit der rechten Maustaste auf einen Serverknoten, und wählen Sie dann **Eigenschaften...** aus.</span><span class="sxs-lookup"><span data-stu-id="bffdd-124">In **Registered Servers**, right click the server node and then select **Properties...**.</span></span>  
  
2.  <span data-ttu-id="bffdd-125">Wählen Sie im Dialogfeld **Serverregistrierungseigenschaften bearbeiten** die Registerkarte **Verbindungseigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="bffdd-125">On the **Edit Server Registration Properties** dialog, select the **Connection Properties** tab.</span></span>  
  
3.  <span data-ttu-id="bffdd-126">Aktivieren Sie das Kontrollkästchen **Benutzerdefinierte Farbe verwenden** .</span><span class="sxs-lookup"><span data-stu-id="bffdd-126">Select the **Use custom color** check box.</span></span>  
  
4.  <span data-ttu-id="bffdd-127">Wählen Sie zur Festlegung der Farbe die Schaltfläche **Auswählen...** aus.</span><span class="sxs-lookup"><span data-stu-id="bffdd-127">To select the color, select the **Select...** button.</span></span>  
  
5.  <span data-ttu-id="bffdd-128">Wählen Sie entweder eine standardmäßige oder benutzerdefinierte Farbe aus und klicken Sie dann auf OK.</span><span class="sxs-lookup"><span data-stu-id="bffdd-128">Select either a basic or custom color, then select OK.</span></span>  
  
6.  <span data-ttu-id="bffdd-129">Wählen Sie im Dialogfeld **Serverregistrierungseigenschaften bearbeiten** die Schaltfläche **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="bffdd-129">Select the **Save** button on the **Edit Server Registration Properties** dialog.</span></span>  
  
##  <a name="open-an-editor-using-a-server-color"></a><a name="OpenServerColor"></a> <span data-ttu-id="bffdd-130">Öffnen eines Editors mithilfe einer Serverfarbe</span><span class="sxs-lookup"><span data-stu-id="bffdd-130">Open An Editor Using a Server Color</span></span>  
 <span data-ttu-id="bffdd-131">**So öffnen Sie ein Editorfenster mithilfe einer Serverfarbe**</span><span class="sxs-lookup"><span data-stu-id="bffdd-131">**To open an editor window using a server color**</span></span>  
  
-   <span data-ttu-id="bffdd-132">Klicken Sie mit der rechten Maustaste entweder in **Objekt-Explorer** oder **Registrierte Server**auf einen Serverknoten, und wählen Sie **Neue Abfrage**aus.</span><span class="sxs-lookup"><span data-stu-id="bffdd-132">Right-click a server node in either **Object Explorer** or **Registered Servers**, and select **New Query**.</span></span>  
  
-   <span data-ttu-id="bffdd-133">Markieren Sie alternativ einen Serverknoten und wählen Sie dann die Symbolleistenschaltfläche **Neue Abfrage** aus.</span><span class="sxs-lookup"><span data-stu-id="bffdd-133">Alternatively, highlight a server node, and then select the **New Query** toolbar button.</span></span>  
  
-   <span data-ttu-id="bffdd-134">Die Statusleiste im Editorfenster verwendet die für den zugeordneten Server definierte Farbe.</span><span class="sxs-lookup"><span data-stu-id="bffdd-134">The status bar in the editor window will use the color defined for the associated server.</span></span>  
  
##  <a name="open-an-editor-specifying-a-status-color"></a><a name="OpenSpecColor"></a> <span data-ttu-id="bffdd-135">Öffnen eines Editors unter Angabe einer Statusfarbe</span><span class="sxs-lookup"><span data-stu-id="bffdd-135">Open an Editor Specifying a Status Color</span></span>  
 <span data-ttu-id="bffdd-136">**So öffnen Sie ein Editorfenster unter Angabe einer Statusfarbe**</span><span class="sxs-lookup"><span data-stu-id="bffdd-136">**To open an editor window specifying a status color**</span></span>  
  
-   <span data-ttu-id="bffdd-137">Öffnen Sie das Menü **Datei**, wählen Sie **Neu** aus, und wählen Sie dann **Datenbank-Engine-Abfrage** aus.</span><span class="sxs-lookup"><span data-stu-id="bffdd-137">Open the **File** menu, select **New**, and then select **Database Engine Query**.</span></span>  
  
-   <span data-ttu-id="bffdd-138">Wählen Sie im Dialogfeld **Verbindung mit Server herstellen** die Option **Optionen >>** .</span><span class="sxs-lookup"><span data-stu-id="bffdd-138">On the **Connect to Server** dialog, select **Options >>**.</span></span>  
  
-   <span data-ttu-id="bffdd-139">Aktivieren Sie das Kontrollkästchen **Benutzerdefinierte Farbe verwenden** .</span><span class="sxs-lookup"><span data-stu-id="bffdd-139">Select the **Use custom color** check box.</span></span>  
  
-   <span data-ttu-id="bffdd-140">Wählen Sie zur Festlegung der Farbe die Schaltfläche **Auswählen...** aus.</span><span class="sxs-lookup"><span data-stu-id="bffdd-140">To select the color, select the **Select...** button.</span></span>  
  
-   <span data-ttu-id="bffdd-141">Wählen Sie entweder eine standardmäßige oder benutzerdefinierte Farbe aus und klicken Sie dann auf OK.</span><span class="sxs-lookup"><span data-stu-id="bffdd-141">Select either a basic or custom color, then select OK.</span></span>  
  
-   <span data-ttu-id="bffdd-142">Geben Sie die restlichen Verbindungsinformationen ein und wählen Sie dann die Schaltfläche **Verbinden** aus.</span><span class="sxs-lookup"><span data-stu-id="bffdd-142">Fill in the rest of the connection information, and then select the **Connect** button.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bffdd-143">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bffdd-143">See Also</span></span>  
 [<span data-ttu-id="bffdd-144">Abfrage- und Text-Editoren &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="bffdd-144">Query and Text Editors &#40;SQL Server Management Studio&#41;</span></span>](../scripting/query-and-text-editors-sql-server-management-studio.md)  
  
  
