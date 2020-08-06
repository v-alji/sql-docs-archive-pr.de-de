---
title: CDC Instance Deployment Script | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
ms.assetid: 8fa82822-ac99-48ef-a18d-f4f3a77105b4
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 6deea884168c2329e312eeaa2be16c28a955cca3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87724878"
---
# <a name="cdc-instance-deployment-script"></a><span data-ttu-id="90960-102">CDC Instance Deployment Script</span><span class="sxs-lookup"><span data-stu-id="90960-102">CDC Instance Deployment Script</span></span>
  <span data-ttu-id="90960-103">In diesem Abschnitt wird das Dialogfeld CDC Instance Deployment Script beschrieben, in dem das Bereitstellungsskript der CDC-Instanz angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="90960-103">The CDC Instance Deployment Script dialog box that displays the CDC instance deployment script.</span></span> <span data-ttu-id="90960-104">Dieses Skript kann verwendet werden, um die CDC-Datenbank mit ihren Artefakten auf einer anderen [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Instanz neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="90960-104">This script can be used to re-create the CDC database with all of its artifacts on a different [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="90960-105">Nach Abschluss des Bereitstellungsskripts sollten Sie Folgendes sicherstellen:</span><span class="sxs-lookup"><span data-stu-id="90960-105">At the completion of the deployment script, you should make sure of the following:</span></span>  
  
-   <span data-ttu-id="90960-106">Das Bereitstellungsskript setzt voraus, dass die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] -Zielinstanz für Oracle CDC mit der Oracle CDC Service Configuration Console oder mit dem vom Programm erstellten **prepare script** (Vorbereitungsskript) vorbereitet wurde.</span><span class="sxs-lookup"><span data-stu-id="90960-106">The deployment script assumes that the target [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance was prepared for Oracle CDC, by using the Oracle CDC Service Configuration Console or by using **prepare script** that program creates.</span></span>  
  
-   <span data-ttu-id="90960-107">Der Teil des Skripts, der zum Aktivieren der Datenbank für CDC verwendet wird, muss von einem `sysadmin`ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="90960-107">The part of the script that is used to enable the database for CDC needs to be run by a `sysadmin`.</span></span>  
  
-   <span data-ttu-id="90960-108">Das Skript behält das Oracle Log Mining-Kennwort nicht bei.</span><span class="sxs-lookup"><span data-stu-id="90960-108">The script does not preserve the Oracle log-mining password.</span></span> <span data-ttu-id="90960-109">Das Kennwort muss manuell festgelegt werden, nachdem das Skript ausgeführt und der Oracle CDC Service gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="90960-109">This needs to be set manually after the script is run and the Oracle CDC Service is started.</span></span>  
  
 <span data-ttu-id="90960-110">Aktivieren Sie im Dialogfeld **CDC Instance Deployment Script** die folgenden Optionen.</span><span class="sxs-lookup"><span data-stu-id="90960-110">Select the following options in the **CDC Instance Deployment Script** dialog box.</span></span>  
  
 <span data-ttu-id="90960-111">**Speichern unter**</span><span class="sxs-lookup"><span data-stu-id="90960-111">**Save As**</span></span>  
 <span data-ttu-id="90960-112">Speichert das Skript in einer Textdatei, die Sie an einem beliebigen Speicherort ablegen können.</span><span class="sxs-lookup"><span data-stu-id="90960-112">Saves the script in a text file that you can save in any location you want.</span></span> <span data-ttu-id="90960-113">Sie können die Datei mit dem Skript auf einen beliebigen anderen Server kopieren, um es dort auszuführen.</span><span class="sxs-lookup"><span data-stu-id="90960-113">You can copy the file with the script to any other server to run it there.</span></span>  
  
 <span data-ttu-id="90960-114">**Copy**</span><span class="sxs-lookup"><span data-stu-id="90960-114">**Copy**</span></span>  
 <span data-ttu-id="90960-115">Kopiert das Skript in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="90960-115">Copies the script to the clipboard.</span></span> <span data-ttu-id="90960-116">Sie können das Skript dann in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] oder einen beliebigen Texteditor einfügen, um die Skripts später auszuführen.</span><span class="sxs-lookup"><span data-stu-id="90960-116">You can then paste the script into the [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or any text editor to run the scripts later.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90960-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="90960-117">See Also</span></span>  
 [<span data-ttu-id="90960-118">Vorbereiten von SQL Server für CDC</span><span class="sxs-lookup"><span data-stu-id="90960-118">Prepare SQL Server for CDC</span></span>](prepare-sql-server-for-cdc.md)  
  
  
