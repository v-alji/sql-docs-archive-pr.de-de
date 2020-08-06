---
title: 'Tutorial: Erste Schritte mit der Datenbank-Engine | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- tutorials [connecting]
- tutorials [Database Engine]
- unable to connect [SQL Server]
- failure to connect [SQL Server]
- connecting tutorial [SQL Server]
ms.assetid: 655e709b-346b-469c-bddc-a5a0238d07e0
author: rothja
ms.author: jroth
ms.openlocfilehash: aaa1fb21c026d064c2b14db73aadc2b82e9c15d3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87621910"
---
# <a name="tutorial-getting-started-with-the-database-engine"></a><span data-ttu-id="bf6c4-102">Tutorial: Erste Schritte mit der Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="bf6c4-102">Tutorial: Getting Started with the Database Engine</span></span>
  <span data-ttu-id="bf6c4-103">Willkommen bei den ersten Schritten im Lernprogramm zu [!INCLUDE[ssDE](../includes/ssde-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bf6c4-103">Welcome to the Getting Started with the [!INCLUDE[ssDE](../includes/ssde-md.md)] tutorial.</span></span> <span data-ttu-id="bf6c4-104">Dieses Lernprogramm richtet sich an Benutzer, die noch nicht mit [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] vertraut sind und [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] oder [!INCLUDE[ssExpress](../includes/ssexpress-md.md)]installiert haben.</span><span class="sxs-lookup"><span data-stu-id="bf6c4-104">This tutorial is intended for users who are new to [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] and who have installed [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] or [!INCLUDE[ssExpress](../includes/ssexpress-md.md)].</span></span> <span data-ttu-id="bf6c4-105">Dieses kurze Lernprogramm hilft Ihnen bei den ersten Schritten mit [!INCLUDE[ssDE](../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="bf6c4-105">This brief tutorial helps you get started using the [!INCLUDE[ssDE](../includes/ssde-md.md)].</span></span>  
  
## <a name="what-you-will-learn"></a><span data-ttu-id="bf6c4-106">Lernziele</span><span class="sxs-lookup"><span data-stu-id="bf6c4-106">What You Will Learn</span></span>  
 <span data-ttu-id="bf6c4-107">In diesem Lernprogramm erfahren Sie, wie Sie sowohl auf dem lokalen Computer als auch von einem anderen Computer mithilfe von [!INCLUDE[ssDE](../includes/ssde-md.md)] eine Verbindung mit dem [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] herstellen.</span><span class="sxs-lookup"><span data-stu-id="bf6c4-107">This tutorial shows you how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] using [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] on both the local computer and from another computer.</span></span>  
  
 <span data-ttu-id="bf6c4-108">Dieses Lernprogramm ist in zwei Lektionen aufgeteilt:</span><span class="sxs-lookup"><span data-stu-id="bf6c4-108">This tutorial is divided into two lessons:</span></span>  
  
 [<span data-ttu-id="bf6c4-109">Lektion 1: Herstellen einer Verbindung mit der Datenbank-Engine</span><span class="sxs-lookup"><span data-stu-id="bf6c4-109">Lesson 1: Connecting to the Database Engine</span></span>](lesson-1-connecting-to-the-database-engine.md)  
 <span data-ttu-id="bf6c4-110">In dieser Lektion erfahren Sie, wie Sie eine Verbindung mit [!INCLUDE[ssDE](../includes/ssde-md.md)] herstellen und anderen Personen das Herstellen einer Verbindung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="bf6c4-110">In this lesson, you will learn how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] and enable additional people to connect.</span></span>  
  
 [<span data-ttu-id="bf6c4-111">Lektion 2: Herstellen einer Verbindung von einem anderen Computer</span><span class="sxs-lookup"><span data-stu-id="bf6c4-111">Lesson 2: Connecting from Another Computer</span></span>](lesson-2-connecting-from-another-computer.md)  
 <span data-ttu-id="bf6c4-112">In dieser Lektion erfahren Sie, wie Sie von einem zweiten Computer eine Verbindung mit [!INCLUDE[ssDE](../includes/ssde-md.md)] herstellen, einschließlich Aktivieren von Protokollen sowie Konfigurieren von Ports und Firewalleinstellungen.</span><span class="sxs-lookup"><span data-stu-id="bf6c4-112">In this lesson, you will learn how to connect to the [!INCLUDE[ssDE](../includes/ssde-md.md)] from a second computer, including enabling protocols, configuring ports, and configuring firewall settings.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf6c4-113">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="bf6c4-113">Requirements</span></span>  
 <span data-ttu-id="bf6c4-114">Für dieses Lernprogramm sind keine Vorkenntnisse erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bf6c4-114">This tutorial has no knowledge prerequisites.</span></span>  
  
 <span data-ttu-id="bf6c4-115">Auf Ihrem System müssen zum Verwenden dieses Lernprogramms folgende Anwendungen installiert sein:</span><span class="sxs-lookup"><span data-stu-id="bf6c4-115">Your system must have the following installed to use this tutorial:</span></span>  
  
-   <span data-ttu-id="bf6c4-116">[https://login.microsoftonline.com/consumers/]([!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)]).</span><span class="sxs-lookup"><span data-stu-id="bf6c4-116">[!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)].</span></span> [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] <span data-ttu-id="bf6c4-117">kann installiert werden, indem Sie das [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Setup ausführen oder das Paket vom [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=144346)herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="bf6c4-117">can be installed by running [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] setup or by downloading and installing from [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=144346).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf6c4-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bf6c4-118">See Also</span></span>  
 [<span data-ttu-id="bf6c4-119">Tutorial: SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="bf6c4-119">Tutorial: SQL Server Management Studio</span></span>](../ssms/tutorials/tutorial-sql-server-management-studio.md)  
  
  
