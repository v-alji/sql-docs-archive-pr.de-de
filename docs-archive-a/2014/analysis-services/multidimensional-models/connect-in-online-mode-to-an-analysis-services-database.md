---
title: Herstellen einer Verbindung im Online Modus mit einer Analysis Services Datenbank | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: conceptual
helpviewer_keywords:
- Analysis Services, connecting
ms.assetid: 33041234-7106-404f-a289-8e904f32aff2
author: minewiskan
ms.author: owend
ms.openlocfilehash: 363beb7132eae92907198979fe2d9892c5d07b79
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87721965"
---
# <a name="connect-in-online-mode-to-an-analysis-services-database"></a><span data-ttu-id="c3f1c-102">Herstellen in Onlinemodus einer Verbindung mit einer Analysis Services-Datenbank</span><span class="sxs-lookup"><span data-stu-id="c3f1c-102">Connect in Online Mode to an Analysis Services Database</span></span>
  <span data-ttu-id="c3f1c-103">Sie können eine direkte Verbindung mit einer vorhandenen [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] Datenbank herstellen und Objekte in dieser Datenbank direkt ändern.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-103">You can connect directly to an existing [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database and directly modify objects within that database.</span></span> <span data-ttu-id="c3f1c-104">Wenn Sie eine direkte Verbindung mit einer [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank herstellen, werden Änderungen an Objekten unmittelbar wirksam, und es wird kein [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Projekt innerhalb von [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)]erstellt.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-104">When you connect directly to an [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database, changes to objects occur immediately and no [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] project is created within [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
### <a name="to-connect-directly-to-an-analysis-services-database-by-using-sql-server-data-tools"></a><span data-ttu-id="c3f1c-105">So stellen Sie eine direkte Verbindung zu einer Analysis Services-Datenbank mit SQL Server-Datentools her</span><span class="sxs-lookup"><span data-stu-id="c3f1c-105">To Connect Directly to an Analysis Services Database by using SQL Server Data Tools</span></span>  
  
1.  <span data-ttu-id="c3f1c-106">Öffnen Sie [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c3f1c-106">Open [!INCLUDE[ssBIDevStudioFull](../../includes/ssbidevstudiofull-md.md)].</span></span>  
  
2.  <span data-ttu-id="c3f1c-107">Zeigen Sie im Menü **Datei** auf **Öffnen** , und klicken Sie dann auf **Analysis Services-Datenbank**.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-107">On the **File** menu, point to **Open** and then click **Analysis Services Database**.</span></span>  
  
3.  <span data-ttu-id="c3f1c-108">Wählen Sie **Verbindung mit vorhandener Datenbank herstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-108">Select **Connect to existing database**.</span></span>  
  
4.  <span data-ttu-id="c3f1c-109">Geben Sie den Server- und den Datenbanknamen an.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-109">Specify the server name and the database name.</span></span>  
  
     <span data-ttu-id="c3f1c-110">Sie können den Datenbanknamen entweder eingeben oder den Server abfragen, um die vorhandenen Datenbanken auf dem Server anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-110">You can either type the database name or query the server to view the existing databases on the server.</span></span>  
  
5.  <span data-ttu-id="c3f1c-111">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-111">Click **OK**.</span></span>  
  
     <span data-ttu-id="c3f1c-112">Sie können nun alle Objekte innerhalb der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Datenbank direkt bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c3f1c-112">You can now directly edit any objects within the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] database.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3f1c-113">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c3f1c-113">See Also</span></span>  
 <span data-ttu-id="c3f1c-114">[Arbeiten mit Analysis Services Projekten und Datenbanken während der Entwicklungs Phase](work-with-analysis-services-projects-and-databases-in-development.md) </span><span class="sxs-lookup"><span data-stu-id="c3f1c-114">[Working with Analysis Services Projects and Databases During the Development Phase](work-with-analysis-services-projects-and-databases-in-development.md) </span></span>  
 [<span data-ttu-id="c3f1c-115">Erstellen mehrdimensionaler Modelle mit SQL Server-Datentools &#40;SSDT&#41;</span><span class="sxs-lookup"><span data-stu-id="c3f1c-115">Creating Multidimensional Models Using SQL Server Data Tools &#40;SSDT&#41;</span></span>](creating-multidimensional-models-using-sql-server-data-tools-ssdt.md)  
  
  
