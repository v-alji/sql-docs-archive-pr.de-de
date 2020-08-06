---
title: 'Aufgabe 10: Konfigurieren der Verbund Domäne für die Verwendung von Reference Data Service | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: data-quality-services
ms.topic: conceptual
ms.assetid: 752eefde-8b87-4f54-878e-9963ccbadc8e
author: lrtoyou1223
ms.author: lle
ms.openlocfilehash: d70966b4cde110540bf5008eda4e3151fe32f28d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87726386"
---
# <a name="task-10-configuring-composite-domain-to-use-reference-data-service"></a><span data-ttu-id="eb9ee-102">Aufgabe 10: Konfigurieren der Verbunddomäne für die Verwendung von Verweisdatendiensten</span><span class="sxs-lookup"><span data-stu-id="eb9ee-102">Task 10: Configuring Composite Domain to Use Reference Data Service</span></span>
  <span data-ttu-id="eb9ee-103">In dieser Aufgabe konfigurieren Sie die Verbund Domäne für die **Adressvalidierung** so, dass Sie den Dienst **Melissa-Daten Adressüberprüfung** verwendet.</span><span class="sxs-lookup"><span data-stu-id="eb9ee-103">In this task, you configure the **Address Validation** composite domain to use the **Melissa Data - Address Check** service.</span></span> <span data-ttu-id="eb9ee-104">Zur Laufzeit während der Bereinigungsaktivität gibt DQS die Werte der Domänen in der Domäne "Address Validation" zur Bereinigung an den Dienst weiter.</span><span class="sxs-lookup"><span data-stu-id="eb9ee-104">At runtime, during cleansing activity, DQS passes the values of domains in the Address Validation domain to the service for cleansing.</span></span> <span data-ttu-id="eb9ee-105">Weitere Informationen finden [Sie unterzuordnen einer Domäne/Verbund Domäne zu Verweis Daten](https://msdn.microsoft.com/library/hh213030.aspx) .</span><span class="sxs-lookup"><span data-stu-id="eb9ee-105">See [Map Domain/Composite Domain to Reference Data](https://msdn.microsoft.com/library/hh213030.aspx) for more details.</span></span>  
  
1.  <span data-ttu-id="eb9ee-106">Klicken Sie auf der Hauptseite des **DQS-Clients**unter **zuletzt verwendete Wissensdatenbanken** auf **Suppliers (Domänen Verwaltung)** , um die Seite **Domänen Verwaltung** zu starten.</span><span class="sxs-lookup"><span data-stu-id="eb9ee-106">In the main page of **DQS Client**, click **Suppliers (Domain Management)** under **Recent Knowledge Bases** to launch the **Domain Management** page.</span></span>  
  
2.  <span data-ttu-id="eb9ee-107">Wählen Sie die Verbund Domäne **Address Validation** in der **Liste der Domänen aus**.</span><span class="sxs-lookup"><span data-stu-id="eb9ee-107">Select the **Address Validation** composite domain in the **list of domains**.</span></span>  
  
3.  <span data-ttu-id="eb9ee-108">Wechseln Sie im rechten Bereich zur Registerkarte **Verweis Daten** .</span><span class="sxs-lookup"><span data-stu-id="eb9ee-108">In the right pane, switch to the **Reference Data** tab.</span></span>  
  
     <span data-ttu-id="eb9ee-109">![Verweisdaten (Registerkarte)](../../2014/tutorials/media/et-configuringcdtouserds-01.jpg "Verweisdaten (Registerkarte)")</span><span class="sxs-lookup"><span data-stu-id="eb9ee-109">![Reference Data Tab](../../2014/tutorials/media/et-configuringcdtouserds-01.jpg "Reference Data Tab")</span></span>  
  
4.  <span data-ttu-id="eb9ee-110">Klicken Sie auf der Symbolleiste auf **Durchsuchen** .</span><span class="sxs-lookup"><span data-stu-id="eb9ee-110">Click **Browse** button on the toolbar.</span></span>  
  
5.  <span data-ttu-id="eb9ee-111">Aktivieren Sie im Dialogfeld **Online Katalog der Verweis Datenanbieter** das **Kontrollkästchen** neben **Melissa Data-Address Check**.</span><span class="sxs-lookup"><span data-stu-id="eb9ee-111">On the **Online Reference Data Providers Catalog** dialog box, select **check box** next to **Melissa Data - Address Check**.</span></span>  
  
     <span data-ttu-id="eb9ee-112">![Auswählen von "Melissa Data – Adresse"](../../2014/tutorials/media/et-configuringcdtouserds-02.jpg "Auswählen von "Melissa Data – Adresse"")</span><span class="sxs-lookup"><span data-stu-id="eb9ee-112">![Select Melissa Data - Address Check](../../2014/tutorials/media/et-configuringcdtouserds-02.jpg "Select Melissa Data - Address Check")</span></span>  
  
6.  <span data-ttu-id="eb9ee-113">Ordnen Sie im rechten Bereich im Abschnitt **Schema** **der Adresszeile** **(M)** das Schema Element mithilfe der Dropdown Liste zu.</span><span class="sxs-lookup"><span data-stu-id="eb9ee-113">In the right pane, in the **Schema** section, map **Address Line** domain to the **Address Line (M)** schema item by using the drop-down list.</span></span>  
  
     <span data-ttu-id="eb9ee-114">![Zuordnen des RDS-Schemaelements zur Domäne](../../2014/tutorials/media/et-configuringcdtouserds-03.jpg "Zuordnen des RDS-Schemaelements zur Domäne")</span><span class="sxs-lookup"><span data-stu-id="eb9ee-114">![Map RDS Schema Item to Domain](../../2014/tutorials/media/et-configuringcdtouserds-03.jpg "Map RDS Schema Item to Domain")</span></span>  
  
7.  <span data-ttu-id="eb9ee-115">Klicken Sie in der Symbolleiste auf die Schaltfläche **Schema Eintrag hinzufügen (+)** , um einen Eintrag in der Liste zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eb9ee-115">Click **Add Schema Entry (+)** button on the toolbar to create an entry in the list.</span></span>  
  
     <span data-ttu-id="eb9ee-116">![Schemaeintrag hinzufügen (Symbolleistenschaltfläche)](../../2014/tutorials/media/et-configuringcdtouserds-04.jpg "Schemaeintrag hinzufügen (Symbolleistenschaltfläche)")</span><span class="sxs-lookup"><span data-stu-id="eb9ee-116">![Add Schema Entry Toolbar Button](../../2014/tutorials/media/et-configuringcdtouserds-04.jpg "Add Schema Entry Toolbar Button")</span></span>  
  
8.  <span data-ttu-id="eb9ee-117">Ordnen Sie die folgenden DQS-Domänen mit den Dropdownlisten zu, wie in der folgenden Abbildung gezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb9ee-117">Map the following DQS domains by using the drop-down lists as shown in the following picture.</span></span>  
  
     <span data-ttu-id="eb9ee-118">![Zuordnen von RDS-Schemaelementen zu Domänen](../../2014/tutorials/media/et-configuringcdtouserds-05.jpg "Zuordnen von RDS-Schemaelementen zu Domänen")</span><span class="sxs-lookup"><span data-stu-id="eb9ee-118">![Map RDS Schema Items to Domains](../../2014/tutorials/media/et-configuringcdtouserds-05.jpg "Map RDS Schema Items to Domains")</span></span>  
  
9. <span data-ttu-id="eb9ee-119">Klicken Sie auf **OK** , um das Dialogfeld zu schließen.</span><span class="sxs-lookup"><span data-stu-id="eb9ee-119">Click **OK** to close the dialog box.</span></span>  
  
## <a name="next-step"></a><span data-ttu-id="eb9ee-120">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="eb9ee-120">Next Step</span></span>  
 [<span data-ttu-id="eb9ee-121">Aufgabe 11: Veröffentlichen der Wissensdatenbank</span><span class="sxs-lookup"><span data-stu-id="eb9ee-121">Task 11: Publishing the Knowledge Base</span></span>](../../2014/tutorials/task-11-publishing-the-knowledge-base.md)  
  
  
