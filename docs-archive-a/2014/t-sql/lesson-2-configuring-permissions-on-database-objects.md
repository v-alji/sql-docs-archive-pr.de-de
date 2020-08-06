---
title: 'Lektion 2: Konfigurieren von Berechtigungen für Datenbankobjekte | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: t-sql
ms.topic: conceptual
helpviewer_keywords:
- database permissions
ms.assetid: f964b66a-ec32-44c2-a185-6a0f173bfa22
author: VanMSFT
ms.author: vanto
ms.openlocfilehash: fcc6ee3ddf9be072b51bd568fd3e72eb6c871785
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724333"
---
# <a name="lesson-2-configuring-permissions-on-database-objects"></a><span data-ttu-id="c9802-102">Lektion 2: Konfigurieren von Berechtigungen für Datenbankobjekte</span><span class="sxs-lookup"><span data-stu-id="c9802-102">Lesson 2: Configuring Permissions on Database Objects</span></span>
  <span data-ttu-id="c9802-103">Wenn Sie einem Benutzer Zugriff auf eine Datenbank gewähren möchten, müssen drei Schritte ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="c9802-103">Granting a user access to a database involves three steps.</span></span> <span data-ttu-id="c9802-104">Zuerst erstellen Sie einen Anmeldenamen.</span><span class="sxs-lookup"><span data-stu-id="c9802-104">First, you create a login.</span></span> <span data-ttu-id="c9802-105">Dieser Anmeldename ermöglicht es dem Benutzer, eine Verbindung mit [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)]herzustellen.</span><span class="sxs-lookup"><span data-stu-id="c9802-105">The login lets the user connect to the [!INCLUDE[ssDEnoversion](../includes/ssdenoversion-md.md)].</span></span> <span data-ttu-id="c9802-106">Anschließend konfigurieren Sie den Anmeldenamen als Benutzer in der angegebenen Datenbank.</span><span class="sxs-lookup"><span data-stu-id="c9802-106">Then you configure the login as a user in the specified database.</span></span> <span data-ttu-id="c9802-107">Im letzten Schritt erteilen Sie diesem Benutzer Berechtigungen für Datenbankobjekte.</span><span class="sxs-lookup"><span data-stu-id="c9802-107">And finally, you grant that user permission to database objects.</span></span> <span data-ttu-id="c9802-108">In dieser Lektion werden diese drei Schritte beschrieben, und es wird gezeigt, wie eine Sicht und eine gespeicherte Prozedur als Objekt erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="c9802-108">This lesson shows you these three steps, and shows you how to create a view and a stored procedure as the object.</span></span>  
  
 <span data-ttu-id="c9802-109">Diese Lektion enthält die folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="c9802-109">This lesson contains the following topics:</span></span>  
  
-   [<span data-ttu-id="c9802-110">Erstellen einer Anmeldung</span><span class="sxs-lookup"><span data-stu-id="c9802-110">Creating a Login</span></span>](lesson-2-1-creating-a-login.md)  
  
-   [<span data-ttu-id="c9802-111">Gewähren von Zugriff auf eine Datenbank</span><span class="sxs-lookup"><span data-stu-id="c9802-111">Granting Access to a Database</span></span>](lesson-2-2-granting-access-to-a-database.md)  
  
-   [<span data-ttu-id="c9802-112">Erstellen von Sichten und gespeicherten Prozeduren</span><span class="sxs-lookup"><span data-stu-id="c9802-112">Creating Views and Stored Procedures</span></span>](lesson-2-3-creating-views-and-stored-procedures.md)  
  
-   [<span data-ttu-id="c9802-113">Erteilen des Zugriffs auf ein Datenbankobjekt</span><span class="sxs-lookup"><span data-stu-id="c9802-113">Granting Access to a Database Object</span></span>](lesson-2-4-granting-access-to-a-database-object.md)  
  
-   [<span data-ttu-id="c9802-114">Zusammenfassung: Konfigurieren von Berechtigungen für Datenbankobjekte</span><span class="sxs-lookup"><span data-stu-id="c9802-114">Summary: Configuring Permissions on Database Objects</span></span>](lesson-2-5-summary-configuring-permissions-on-database-objects.md)  
  
## <a name="next-task-in-lesson"></a><span data-ttu-id="c9802-115">Nächste Aufgabe in der Lektion</span><span class="sxs-lookup"><span data-stu-id="c9802-115">Next Task in Lesson</span></span>  
 [<span data-ttu-id="c9802-116">Erstellen einer Anmeldung</span><span class="sxs-lookup"><span data-stu-id="c9802-116">Creating a Login</span></span>](lesson-2-1-creating-a-login.md)  
  
  
