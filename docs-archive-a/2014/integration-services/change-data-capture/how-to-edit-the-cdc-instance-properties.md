---
title: Bearbeiten der CDC-Instanzeigenschaften | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 7a6c719a-3735-43b7-b3ab-dfadd325eca2
author: chugugrace
ms.author: chugu
ms.openlocfilehash: b02785a32fa1f64d5da0c3202acd7916da1e65ee
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695969"
---
# <a name="how-to-edit-the-cdc-instance-properties"></a><span data-ttu-id="84aed-102">Bearbeiten der CDC-Instanzeigenschaften</span><span class="sxs-lookup"><span data-stu-id="84aed-102">How to Edit the CDC Instance Properties</span></span>
  <span data-ttu-id="84aed-103">In diesem Verfahren wird beschrieben, wie Sie die CDC Designer Console verwenden, um die Konfigurationseigenschaften für eine CDC-Instanz zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="84aed-103">This procedure describes how to use the CDC Designer Console to edit the configuration properties for a CDC instance.</span></span>  
  
### <a name="to-edit-the-cdc-instance-configuration-properties"></a><span data-ttu-id="84aed-104">So bearbeiten Sie die Konfigurationseigenschaften einer CDC-Instanz</span><span class="sxs-lookup"><span data-stu-id="84aed-104">To edit the CDC instance configuration properties</span></span>  
  
1.  <span data-ttu-id="84aed-105">Wählen Sie im Menü **Start** die Option **CDC Designer Console**aus.</span><span class="sxs-lookup"><span data-stu-id="84aed-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="84aed-106">Erweitern Sie im linken Bereich die Option **Change Data Capture** , und erweitern Sie dann den Dienst, der die Instanz mit den zu bearbeitenden Eigenschaften enthält.</span><span class="sxs-lookup"><span data-stu-id="84aed-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance with the properties that you want to edit.</span></span>  
  
3.  <span data-ttu-id="84aed-107">Wählen Sie den Namen der Instanz aus, deren Eigenschaften Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="84aed-107">Select the name of the instance where you want to edit the properties.</span></span>  
  
4.  <span data-ttu-id="84aed-108">Klicken Sie in der der CDC Designer Console rechts im Aktionsbereich auf **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="84aed-108">From the Actions pane on the right side of the CDC Designer Console, click **Properties**.</span></span>  
  
     <span data-ttu-id="84aed-109">Sie können auch mit der rechten Maustaste auf die Instanz klicken, für die Sie die Eigenschaften bearbeiten möchten, und dann auf **Eigenschaften**klicken.</span><span class="sxs-lookup"><span data-stu-id="84aed-109">You can also right-click the instance where you want to edit the properties and click **Properties**.</span></span>  
  
5.  <span data-ttu-id="84aed-110">Bearbeiten Sie im Eigenschaften-Editor die Eigenschaften auf den folgenden Registerkarten:</span><span class="sxs-lookup"><span data-stu-id="84aed-110">In the Properties editor, edit the properties in the following tabs:</span></span>  
  
    -   <span data-ttu-id="84aed-111">**Oracle**: Verwenden Sie die Registerkarte **Oracle** im Eigenschaften-Editor, um Änderungen an der Beschreibung vorzunehmen, die Sie im Assistenten für neue Instanzen auf der Seite Create CDC database angegeben haben, und um Änderungen an den Verbindungsinformationen zur Oracle Log Mining-Datenbank vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="84aed-111">**Oracle**: Use the **Oracle** tab in the Properties editor to make changes to the description you provided in the Create CDC database page in the New Instance wizard and to make changes to the Oracle Log Mining database connection information.</span></span>  
  
         <span data-ttu-id="84aed-112">Informationen zu den Bearbeitungsmöglichkeiten auf dieser Registerkarte finden Sie unter [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span><span class="sxs-lookup"><span data-stu-id="84aed-112">For information about what you can edit in this tab, see [Edit the Oracle Database Properties](edit-the-oracle-database-properties.md).</span></span>  
  
    -   <span data-ttu-id="84aed-113">**Tabellen**: Verwenden Sie die Registerkarte **Tabellen** , um Änderungen an den Tabellen und Spalten vorzunehmen, die Sie in der Oracle-Quelldatenbank ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="84aed-113">**Tables**: Use the **Tables** tab to make changes to the tables and columns that you selected from the Oracle source database.</span></span>  
  
         <span data-ttu-id="84aed-114">Informationen zu den Bearbeitungsmöglichkeiten auf dieser Registerkarte finden Sie unter [Edit Tables](edit-tables.md).</span><span class="sxs-lookup"><span data-stu-id="84aed-114">For information about what you can edit in this tab, see Edit [Edit Tables](edit-tables.md)</span></span>  
  
    -   <span data-ttu-id="84aed-115">**Skripts:** Verwenden Sie die Registerkarte **Skripts** , um ein Skript für die Oracle-Quelldatenbank auszuführen bzw. erneut auszuführen, mit dem die ergänzende Protokollierung eingerichtet wird.</span><span class="sxs-lookup"><span data-stu-id="84aed-115">**Scripts**: Use the **Scripts** tab to run or re-run a script on the Oracle source database that will set up supplemental logging.</span></span>  
  
         <span data-ttu-id="84aed-116">Informationen zu den Optionen auf dieser Registerkarte finden Sie unter [Review and Generate Supplemental Logging Scripts](review-and-generate-supplemental-logging-scripts.md).</span><span class="sxs-lookup"><span data-stu-id="84aed-116">For information about what you can do in this tab, see [Review and Generate Supplemental Logging Scripts](review-and-generate-supplemental-logging-scripts.md).</span></span>  
  
    -   <span data-ttu-id="84aed-117">**Erweitert**: Verwenden Sie die Registerkarte **Erweitert** , um der CDC-Instanz besondere Eigenschaften hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="84aed-117">**Advanced**: Use the **Advanced** tab to add special properties to the CDC instance.</span></span>  
  
         <span data-ttu-id="84aed-118">Informationen zu den Optionen auf dieser Registerkarte finden Sie unter [Edit the Advanced Properties](edit-the-advanced-properties.md).</span><span class="sxs-lookup"><span data-stu-id="84aed-118">For information about what you can do in this tab, see [Edit the Advanced Properties](edit-the-advanced-properties.md).</span></span>  
  
  
