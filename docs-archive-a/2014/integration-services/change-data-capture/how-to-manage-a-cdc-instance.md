---
title: Verwalten einer CDC-Instanz | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 5d9e677f-b872-497d-9cde-472184a214ab
author: chugugrace
ms.author: chugu
ms.openlocfilehash: e387b9e1a75b7279a68d1c9c9b637f5473071013
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87695966"
---
# <a name="how-to-manage-a-cdc-instance"></a><span data-ttu-id="2d63c-102">How to Manage a CDC Instance</span><span class="sxs-lookup"><span data-stu-id="2d63c-102">How to Manage a CDC Instance</span></span>
  <span data-ttu-id="2d63c-103">In diesem Verfahren wird beschrieben, wie Sie die CDC Designer Console zum Verwalten von CDC-Instanzvorgängen zur Laufzeit verwenden.</span><span class="sxs-lookup"><span data-stu-id="2d63c-103">This procedure describes how to use the CDC Designer Console to manage CDC instance operations at runtime.</span></span>  
  
### <a name="to-manage-cdc-instance-operations"></a><span data-ttu-id="2d63c-104">So verwalten Sie CDC-Instanzvorgänge</span><span class="sxs-lookup"><span data-stu-id="2d63c-104">To manage CDC instance operations</span></span>  
  
1.  <span data-ttu-id="2d63c-105">Wählen Sie im Menü **Start** die Option **CDC Designer Console**aus.</span><span class="sxs-lookup"><span data-stu-id="2d63c-105">From the **Start** menu, select the **CDC Designer Console**.</span></span>  
  
2.  <span data-ttu-id="2d63c-106">Erweitern Sie im linken Bereich die Option **Change Data Capture** , und erweitern Sie dann den Dienst, der die anzuzeigende Instanz enthält.</span><span class="sxs-lookup"><span data-stu-id="2d63c-106">In the left pane, expand **Change Data Capture** then expand the service that contains the instance you want to view.</span></span>  
  
3.  <span data-ttu-id="2d63c-107">Wählen Sie den Namen einer Instanz aus, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="2d63c-107">Select the name of an instance you want to work with.</span></span>  
  
4.  <span data-ttu-id="2d63c-108">Klicken Sie in der CDC Designer Console rechts im **Aktionsbereich** auf den Vorgang, den Sie ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="2d63c-108">From the **Actions** pane on the right side of the CDC Designer Console, click on the operation you want to carry out.</span></span>  
  
     <span data-ttu-id="2d63c-109">Sie können auch im linken Bereich mit der rechten Maustaste auf den Namen der Instanz klicken und den auszuführenden Vorgang auswählen.</span><span class="sxs-lookup"><span data-stu-id="2d63c-109">You can also right-click the name of the instance in the left pane and select the operation you want to carry out.</span></span>  
  
     <span data-ttu-id="2d63c-110">Sie können die folgenden Tasks ausführen:</span><span class="sxs-lookup"><span data-stu-id="2d63c-110">You can carry out the following tasks:</span></span>  
  
    -   <span data-ttu-id="2d63c-111">**Start**: Die Aufzeichnung der Änderungen wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="2d63c-111">**Start**: To start capturing changes.</span></span>  
  
    -   <span data-ttu-id="2d63c-112">**Beenden**: Die Aufzeichnung der Änderungen wird beendet.</span><span class="sxs-lookup"><span data-stu-id="2d63c-112">**Stop**: To stop capturing changes</span></span>  
  
    -   <span data-ttu-id="2d63c-113">**Zurücksetzen**: Klicken Sie auf **Zurücksetzen** , um die CDC-Instanz auf ihren ursprünglichen (leeren) Zustand zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="2d63c-113">**Reset**: Click **Reset** to reset the CDC instance to its initial (empty) state.</span></span> <span data-ttu-id="2d63c-114">Diese Option ist verfügbar, wenn die CDC-Instanz beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2d63c-114">This option is available when the CDC instance is stopped.</span></span> <span data-ttu-id="2d63c-115">Alle Änderungen in den Änderungstabellen und der interne Status der CDC-Instanz werden gelöscht.</span><span class="sxs-lookup"><span data-stu-id="2d63c-115">All changes in the change tables and the CDC instance internal state are deleted.</span></span> <span data-ttu-id="2d63c-116">Wenn die CDC-Instanz später dann gestartet wird, beginnt die Änderungsaufzeichnung ab diesem Zeitpunkt und schließt nur Transaktionen ein, die nach dem Starten der CDC-Instanz gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="2d63c-116">When the CDC instance is started later on, change capture will start from that point in time and only includes transactions that started after the CDC instance started.</span></span>  
  
    -   <span data-ttu-id="2d63c-117">**Löschen**: Dient zum Löschen der CDC-Instanz.</span><span class="sxs-lookup"><span data-stu-id="2d63c-117">**Delete**: To delete the CDC instance.</span></span>  
  
    -   <span data-ttu-id="2d63c-118">**Oracle Logging Script**: Klicken Sie auf **Oracle Logging Script** , um das entsprechende Dialogfeld mit dem ergänzenden Oracle-Protokollierungsskript anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="2d63c-118">**Oracle Logging Script**: Click **Oracle Logging Script** to display the Oracle Logging script dialog box with the Oracle supplemental-logging script.</span></span> <span data-ttu-id="2d63c-119">Informationen zu den Schritten, die Sie in diesem Dialogfeld ausführen können, finden Sie unter [Oracle Supplemental Logging Script](oracle-supplemental-logging-script.md).</span><span class="sxs-lookup"><span data-stu-id="2d63c-119">For information on what you can do in this dialog box, see [Oracle Supplemental Logging Script](oracle-supplemental-logging-script.md).</span></span>  
  
         <span data-ttu-id="2d63c-120">**Hinweis**: Wenn Sie die ergänzenden Protokollierungsskripts ausführen, wird das Dialogfeld Oracle Credentials for Running Script geöffnet, in dem Sie einen gültigen Oracle-Benutzernamen und das dazugehörige Kennwort angeben können.</span><span class="sxs-lookup"><span data-stu-id="2d63c-120">**Note**: When you run the supplemental logging scripts, the Oracle Credentials for Running Script dialog box opens where you provide a valid Oracle user name and password.</span></span> <span data-ttu-id="2d63c-121">Informationen zum Bereitstellen der richtigen Oracle-Anmeldeinformationen finden Sie unter [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span><span class="sxs-lookup"><span data-stu-id="2d63c-121">For information on how to provide the proper Oracle credentials, see [Oracle Credentials for Running Script](oracle-credentials-for-running-script.md).</span></span>  
  
    -   <span data-ttu-id="2d63c-122">**CDC Instance Deployment**: Dient zum Generieren eines Bereitstellungsskripts für die CDC-Instanz.</span><span class="sxs-lookup"><span data-stu-id="2d63c-122">**CDC Instance Deployment**: To generate a deployment script for the CDC Instance.</span></span> <span data-ttu-id="2d63c-123">Informationen zu diesem Dialogfeld finden Sie unter [CDC Instance Deployment Script](cdc-instance-deployment-script.md).</span><span class="sxs-lookup"><span data-stu-id="2d63c-123">For information about this dialog box, see [CDC Instance Deployment Script](cdc-instance-deployment-script.md).</span></span>  
  
     <span data-ttu-id="2d63c-124">Weitere Informationen zu diesen Tasks finden Sie unter [Manage a CDC Instance](manage-a-cdc-instance.md).</span><span class="sxs-lookup"><span data-stu-id="2d63c-124">For more information about these tasks, see [Manage a CDC Instance](manage-a-cdc-instance.md).</span></span>  
  
 <span data-ttu-id="2d63c-125">Sie können auch **Eigenschaften** wählen, um die Konfigurationseigenschaften der CDC-Instanz zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="2d63c-125">You can also select **Properties** to edit the CDC instance configuration properties.</span></span> <span data-ttu-id="2d63c-126">Weitere Informationen zum Bearbeiten der CDC-Instanzeigenschaften finden Sie unter [Edit Instance Properties](edit-instance-properties.md).</span><span class="sxs-lookup"><span data-stu-id="2d63c-126">For more information about editing the CDC instance properties, see [Edit Instance Properties](edit-instance-properties.md).</span></span>  
  
  
