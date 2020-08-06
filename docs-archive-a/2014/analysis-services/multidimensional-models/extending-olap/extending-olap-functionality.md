---
title: Erweitern von OLAP-Funktionen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: 49a17ff3-94e9-4969-84fc-37d49e63933b
author: minewiskan
ms.author: owend
ms.openlocfilehash: d64d1ac46e2571aa6f8065a8ea42e4cc43aa589e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622902"
---
# <a name="extending-olap-functionality"></a><span data-ttu-id="d8142-102">Erweiterte von OLAP-Funktionalität</span><span class="sxs-lookup"><span data-stu-id="d8142-102">Extending OLAP functionality</span></span>
  <span data-ttu-id="d8142-103">Als Programmierer können Sie Analysis Services erweitern, indem Sie Assemblys, personalisierte Erweiterungen und gespeicherten Prozeduren schreiben, die die Funktionalität bereitstellen, die Sie in mehreren Datenbankanwendungen verwenden oder wiederverwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="d8142-103">As a programmer, you can extend Analysis Services by writing assemblies, personalized extensions, and stored procedures that provide functionality you want to use and repurpose in multiple database applications.</span></span> <span data-ttu-id="d8142-104">Assemblys werden verwendet, um durch Hinzufügen von neuen Prozeduren und Funktionen zur MDX-Sprache oder mittels des Personalisierungs-Add-Ins die mehrdimensionale Modelle-Funktionalität zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d8142-104">Assemblies are used to extend multidimensional models functionality by adding new procedures and functions to the MDX language or by means of the personalization addin.</span></span>  
  
 <span data-ttu-id="d8142-105">Gespeicherte Prozeduren können verwendet werden, um externe Routinen aufzurufen, und vereinfachen so die Entwicklung und Implementierung von Analysis Services-Datenbanken, da gemeinsamer Code nur einmal entwickelt werden muss und an einem einzelnen Ort gespeichert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d8142-105">Stored procedures can be used to call external routines, simplifying Analysis Services database development and implementation by allowing common code to be developed once and stored in a single location.</span></span> <span data-ttu-id="d8142-106">Mit gespeicherten Prozeduren kann Anwendungen Geschäftsfunktionalität hinzugefügt werden, die von der systemeigenen Funktionalität von MDX nicht bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="d8142-106">Stored procedures can be used to add business functionality to your applications that is not provided by the native functionality of MDX.</span></span>  
  
 <span data-ttu-id="d8142-107">Personalisierungen sind benutzerdefinierte Objekte, die Sie einem Cube hinzufügen, um ein Verhalten bereitzustellen, das sich je nach Benutzer ändert.</span><span class="sxs-lookup"><span data-stu-id="d8142-107">Personalizations are custom objects that you add to a cube to provide a behavior that varies by user.</span></span> <span data-ttu-id="d8142-108">Personalisierungen sind keine permanenten Objekte im Cube, sondern Objekte, die von der Clientanwendung während der Sitzung des Benutzers dynamisch angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d8142-108">Personalizations are not permanent objects in the cube, but are objects that the client application applies dynamically during the user's session.</span></span> <span data-ttu-id="d8142-109">Beispiele umfassen das Ändern der Währung von einem Währungswert abhängig von der Person, die auf die Daten zugreift, Bereitstellen von individualisierten KPIs oder eine gezielte Vorschlagsliste für Stammkunden, die online kaufen.</span><span class="sxs-lookup"><span data-stu-id="d8142-109">Examples include changing the currency of a monetary value depending on the person accessing the data, providing individualized KPIs, or a targeted suggestion list for regular customers who purchase online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d8142-110">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="d8142-110">In This Section</span></span>  
 [<span data-ttu-id="d8142-111">Erweitern von OLAP durch Personalisierungen</span><span class="sxs-lookup"><span data-stu-id="d8142-111">Extending OLAP through personalizations</span></span>](extending-olap-through-personalizations.md)  
  
 [<span data-ttu-id="d8142-112">Personalisierungserweiterungen für Analysis Services</span><span class="sxs-lookup"><span data-stu-id="d8142-112">Analysis Services Personalization Extensions</span></span>](analysis-services-personalization-extensions.md)  
  
 [<span data-ttu-id="d8142-113">Definieren von gespeicherten Proze</span><span class="sxs-lookup"><span data-stu-id="d8142-113">Defining Stored Procedures</span></span>](../../multidimensional-models-extending-olap-stored-procedures/defining-stored-procedures.md)  
  
  
