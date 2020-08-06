---
title: Erstellen einer benutzerdefinierten Rolle | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: c4128993-2333-48c7-84b1-e51cdcea393d
author: chugugrace
ms.author: chugu
ms.openlocfilehash: a0ee905c2636e20315c2180a6be8f8e40f76d5f3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616612"
---
# <a name="create-a-user-defined-role"></a><span data-ttu-id="e8e59-102">Erstellen einer benutzerdefinierten Rolle</span><span class="sxs-lookup"><span data-stu-id="e8e59-102">Create a User-Defined Role</span></span>
    
### <a name="to-create-a-user-defined-role"></a><span data-ttu-id="e8e59-103">So erstellen Sie eine benutzerdefinierte Rolle</span><span class="sxs-lookup"><span data-stu-id="e8e59-103">To create a user-defined role</span></span>  
  
1.  <span data-ttu-id="e8e59-104">Öffnen Sie [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e8e59-104">Open [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="e8e59-105">Klicken Sie im Menü **Ansicht** auf **Objekt-Explorer** .</span><span class="sxs-lookup"><span data-stu-id="e8e59-105">Click **Object Explorer** on the **View** menu.</span></span>  
  
3.  <span data-ttu-id="e8e59-106">Klicken Sie auf der Symbolleiste des Objekt-Explorers auf **Verbinden**, und klicken Sie dann auf **Datenbank-Engine**.</span><span class="sxs-lookup"><span data-stu-id="e8e59-106">On the Object Explorer toolbar, click **Connect**, and then click **Database Engine**.</span></span>  
  
4.  <span data-ttu-id="e8e59-107">Geben Sie im Dialogfeld **Verbindung mit Server herstellen** einen Servernamen ein, und wählen Sie einen Authentifizierungsmodus aus.</span><span class="sxs-lookup"><span data-stu-id="e8e59-107">In the **Connect to Server** dialog box, provide a server name and select an authentication mode.</span></span> <span data-ttu-id="e8e59-108">Sie können einen Punkt (.), (local) oder `localhost` zum Angeben des lokalen Servers verwenden.</span><span class="sxs-lookup"><span data-stu-id="e8e59-108">You can use a period (.), (local), or `localhost` to indicate the local server.</span></span>  
  
5.  <span data-ttu-id="e8e59-109">Klicken Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="e8e59-109">Click **Connect**.</span></span>  
  
6.  <span data-ttu-id="e8e59-110">Erweitern Sie die Datenbanken, Systemdatenbanken, msdb, Sicherheit und Rollen.</span><span class="sxs-lookup"><span data-stu-id="e8e59-110">Expand Databases, System Databases, msdb, Security, and Roles.</span></span>  
  
7.  <span data-ttu-id="e8e59-111">Klicken Sie im Knoten „Rollen“ mit der rechten Maustaste auf „Datenbankrollen“. Klicken Sie dann auf **Neue Datenbankrolle**.</span><span class="sxs-lookup"><span data-stu-id="e8e59-111">In the Roles node, right-click Database Roles, and click **New Database Role**.</span></span>  
  
8.  <span data-ttu-id="e8e59-112">Geben Sie auf der Seite "Allgemein" einen Namen ein, und legen Sie wahlweise einen Besitzer sowie Schemas im Besitz fest, und fügen Sie Rollenmitglieder hinzu.</span><span class="sxs-lookup"><span data-stu-id="e8e59-112">On the General page, provide a name and optionally, specify an owner and owned schemas and add role members.</span></span>  
  
9. <span data-ttu-id="e8e59-113">Klicken Sie wahlweise auf **Berechtigungen** , und konfigurieren Sie die Objektberechtigungen.</span><span class="sxs-lookup"><span data-stu-id="e8e59-113">Optionally, click **Permissions** and configure object permissions.</span></span>  
  
10. <span data-ttu-id="e8e59-114">Klicken Sie wahlweise auf **Erweiterte Eigenschaften** , und konfigurieren Sie die erweiterten Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="e8e59-114">Optionally, click **Extended Properties** and configure any extended properties.</span></span>  
  
11. <span data-ttu-id="e8e59-115">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8e59-115">Click **OK**.</span></span>  
  
  
