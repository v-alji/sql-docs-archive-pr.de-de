---
title: Arbeiten mit Datenbankobjekten | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- database objects [SMO]
- objects [SMO]
ms.assetid: 702fd63d-8734-4a02-872e-aecfb037c787
author: stevestein
ms.author: sstein
ms.openlocfilehash: 14dd0c0175a23f809fc925c5104ac15ac408805b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87723670"
---
# <a name="working-with-database-objects"></a><span data-ttu-id="04cf6-102">Arbeiten mit Datenbankobjekten</span><span class="sxs-lookup"><span data-stu-id="04cf6-102">Working with Database Objects</span></span>
  <span data-ttu-id="04cf6-103">Die Phasen der SMO-Objekterstellung sind:</span><span class="sxs-lookup"><span data-stu-id="04cf6-103">The stages of SMO object creation are as follows:</span></span>  
  
1.  <span data-ttu-id="04cf6-104">Erstellen einer Instanz des Objekts</span><span class="sxs-lookup"><span data-stu-id="04cf6-104">Create an instance of the object.</span></span>  
  
2.  <span data-ttu-id="04cf6-105">Festlegen der Objekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="04cf6-105">Set the object properties.</span></span>  
  
3.  <span data-ttu-id="04cf6-106">Erstellen von Instanzen der untergeordneten Objekte</span><span class="sxs-lookup"><span data-stu-id="04cf6-106">Create instances of the child objects.</span></span>  
  
4.  <span data-ttu-id="04cf6-107">Festlegen der Eigenschaften des untergeordneten Objekts</span><span class="sxs-lookup"><span data-stu-id="04cf6-107">Set the child object properties.</span></span>  
  
5.  <span data-ttu-id="04cf6-108">Erstellen des Objekts</span><span class="sxs-lookup"><span data-stu-id="04cf6-108">Create the object.</span></span>  
  
 <span data-ttu-id="04cf6-109">Wenn Instanzen von SMO-Objekten in einer SMO-Anwendung erstellt werden, sind sie auf der [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]-Instanz erst vorhanden, wenn die `Create`-Methode ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="04cf6-109">When instances of SMO objects are created in an SMO application, they do not exist on the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] until the `Create` method is issued.</span></span> <span data-ttu-id="04cf6-110">Allerdings ist es nicht notwendig, eine `Create`-Methode für jedes einzelne Objekt auszugeben.</span><span class="sxs-lookup"><span data-stu-id="04cf6-110">However, it is not necessary to issue a `Create` method for every individual object.</span></span> <span data-ttu-id="04cf6-111">Wenn ein Objekt über einen Satz untergeordneter Objekte verfügt, muss nur das übergeordnete Objekt die `Create`-Methode ausführen.</span><span class="sxs-lookup"><span data-stu-id="04cf6-111">If an object has a set of child objects, only the parent object is required to run the `Create` method.</span></span> <span data-ttu-id="04cf6-112">Zum Beispiel erfordert die Definition einer Tabelle, dass mindestens eine Spalte darin enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="04cf6-112">For example, the definition of a table requires that it contains at least one column to exist.</span></span> <span data-ttu-id="04cf6-113">Auch kann eine Spalte nicht ohne eine Tabelle erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="04cf6-113">Also, a column cannot exist in isolation without a table.</span></span> <span data-ttu-id="04cf6-114">Es besteht eine Abhängigkeitsbeziehung zwischen der Tabelle und ihren Spalten.</span><span class="sxs-lookup"><span data-stu-id="04cf6-114">There is a codependent relationship between the table and its columns.</span></span>  
  
 <span data-ttu-id="04cf6-115">Die <xref:Microsoft.SqlServer.Management.Dmf.Policy.Alter%2A>-Methode ermöglicht es Ihnen, Änderungen an einem Objekt vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="04cf6-115">The <xref:Microsoft.SqlServer.Management.Dmf.Policy.Alter%2A> method lets you make changes to an object.</span></span> <span data-ttu-id="04cf6-116">Mehrere Änderungen an einem Objekt, wie beispielsweise das Hinzufügen untergeordneter Objekte zu einer der Auflistungen des Objekts oder das Ändern eines Eigenschaftswerts, werden zu einem Batch zusammengefasst und in einem Durchgang ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="04cf6-116">Several changes to an object, such as adding child objects to one of the object's collections or changing a property value, are batched together and run as one.</span></span> <span data-ttu-id="04cf6-117">Die `Alter`-Methode reduziert den Netzwerkdatenverkehr und verbessert die Gesamtleistung.</span><span class="sxs-lookup"><span data-stu-id="04cf6-117">The `Alter` method reduces network traffic and improves overall performance.</span></span>  
  
 <span data-ttu-id="04cf6-118">Die `Drop`-Anweisung wird dazu verwendet, ein Objekt und alle seine abhängigen untergeordneten Objekte zu entfernen, die anfänglich zur Objekterstellung erforderlich waren.</span><span class="sxs-lookup"><span data-stu-id="04cf6-118">The `Drop` statement is used to remove an object and all its codependent child objects that were required to create the object initially.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04cf6-119">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="04cf6-119">See Also</span></span>  
 [<span data-ttu-id="04cf6-120">SMO-Objektmodell</span><span class="sxs-lookup"><span data-stu-id="04cf6-120">SMO Object Model</span></span>](../smo-object-model.md)  
  
  
