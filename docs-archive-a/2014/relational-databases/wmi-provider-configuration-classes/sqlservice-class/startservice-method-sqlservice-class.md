---
title: StartService-Methode (SqlService-Klasse) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: wmi
ms.topic: reference
api_name:
- StartService Method (SqlService Class)
api_location:
- sqlmgmproviderxpsp2up.mof
topic_type:
- apiref
helpviewer_keywords:
- StartService method
ms.assetid: 83dfb6bd-dbd5-45d8-aad2-a11926317f91
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 4d91646da2ac2c9f636655ff6c65808ba115e28f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87717611"
---
# <a name="startservice-method-sqlservice-class"></a><span data-ttu-id="b2da4-102">StartService-Methode (SqlService-Klasse)</span><span class="sxs-lookup"><span data-stu-id="b2da4-102">StartService Method (SqlService Class)</span></span>
  <span data-ttu-id="b2da4-103">Versucht, den Dienst zu starten.</span><span class="sxs-lookup"><span data-stu-id="b2da4-103">Attempts to place the service into its started state.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2da4-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b2da4-104">Syntax</span></span>  
  
```  
  
object  
.StartService()  
  
```  
  
## <a name="parts"></a><span data-ttu-id="b2da4-105">Bestandteile</span><span class="sxs-lookup"><span data-stu-id="b2da4-105">Parts</span></span>  
 <span data-ttu-id="b2da4-106">*object*</span><span class="sxs-lookup"><span data-stu-id="b2da4-106">*object*</span></span>  
 <span data-ttu-id="b2da4-107">Ein [SqlService-Klassenobjekt](sqlservice-class.md) , das den Dienst darstellt.</span><span class="sxs-lookup"><span data-stu-id="b2da4-107">A [SqlService Class](sqlservice-class.md) object that represents the service.</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="b2da4-108">Eigenschaftswert/Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b2da4-108">Property Value/Return Value</span></span>  
 <span data-ttu-id="b2da4-109">Ein uint32-Wert, der den einen der folgenden Startstatus angibt:</span><span class="sxs-lookup"><span data-stu-id="b2da4-109">A uint32 value that specifies one of the following startup states.</span></span>  
  
 <span data-ttu-id="b2da4-110">0</span><span class="sxs-lookup"><span data-stu-id="b2da4-110">0</span></span>  
 <span data-ttu-id="b2da4-111">Erfolg.</span><span class="sxs-lookup"><span data-stu-id="b2da4-111">Success.</span></span> <span data-ttu-id="b2da4-112">Die Anforderung wurde akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="b2da4-112">The request was accepted.</span></span>  
  
 <span data-ttu-id="b2da4-113">1</span><span class="sxs-lookup"><span data-stu-id="b2da4-113">1</span></span>  
 <span data-ttu-id="b2da4-114">Nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b2da4-114">Not Supported.</span></span> <span data-ttu-id="b2da4-115">Die Anforderung wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b2da4-115">The request is not supported.</span></span>  
  
 <span data-ttu-id="b2da4-116">2</span><span class="sxs-lookup"><span data-stu-id="b2da4-116">2</span></span>  
 <span data-ttu-id="b2da4-117">Zugriff verweigert.</span><span class="sxs-lookup"><span data-stu-id="b2da4-117">Access Denied.</span></span> <span data-ttu-id="b2da4-118">Der Benutzer hatte keinen entsprechenden Zugriff.</span><span class="sxs-lookup"><span data-stu-id="b2da4-118">The user did not have appropriate access.</span></span>  
  
 <span data-ttu-id="b2da4-119">3</span><span class="sxs-lookup"><span data-stu-id="b2da4-119">3</span></span>  
 <span data-ttu-id="b2da4-120">Abhängige Dienste werden ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b2da4-120">Dependent Services Running.</span></span> <span data-ttu-id="b2da4-121">Der Dienst kann nicht beendet werden, da andere ausgeführte Dienste davon abhängig sind.</span><span class="sxs-lookup"><span data-stu-id="b2da4-121">The service cannot be stopped because other services that are running are dependent on it.</span></span>  
  
 <span data-ttu-id="b2da4-122">4</span><span class="sxs-lookup"><span data-stu-id="b2da4-122">4</span></span>  
 <span data-ttu-id="b2da4-123">Ungültige Dienstkontrolle.</span><span class="sxs-lookup"><span data-stu-id="b2da4-123">Invalid Service Control.</span></span> <span data-ttu-id="b2da4-124">Der angeforderte Steuerungscode ist nicht gültig, oder es ist für den Dienst nicht akzeptabel.</span><span class="sxs-lookup"><span data-stu-id="b2da4-124">The requested control code is not valid, or it is unacceptable to the service.</span></span>  
  
 <span data-ttu-id="b2da4-125">5</span><span class="sxs-lookup"><span data-stu-id="b2da4-125">5</span></span>  
 <span data-ttu-id="b2da4-126">Die Steuerung kann vom Dienst nicht angenommen werden.</span><span class="sxs-lookup"><span data-stu-id="b2da4-126">Service Cannot Accept Control.</span></span> <span data-ttu-id="b2da4-127">Der angeforderte Steuerungscode kann nicht an den Dienst gesendet werden, weil der Status des Diensts (Win32_BaseService:State) 0, 1 oder 2 lautet.</span><span class="sxs-lookup"><span data-stu-id="b2da4-127">The requested control code cannot be sent to the service because the state of the service (Win32_BaseService:State) is equal to 0, 1, or 2.</span></span>  
  
 <span data-ttu-id="b2da4-128">6</span><span class="sxs-lookup"><span data-stu-id="b2da4-128">6</span></span>  
 <span data-ttu-id="b2da4-129">Der Dienst ist nicht aktiv.</span><span class="sxs-lookup"><span data-stu-id="b2da4-129">Service Not Active.</span></span> <span data-ttu-id="b2da4-130">Der Dienst wurde nicht gestartet.</span><span class="sxs-lookup"><span data-stu-id="b2da4-130">The service has not been started.</span></span>  
  
 <span data-ttu-id="b2da4-131">7</span><span class="sxs-lookup"><span data-stu-id="b2da4-131">7</span></span>  
 <span data-ttu-id="b2da4-132">Timeout bei der Dienstanforderung.</span><span class="sxs-lookup"><span data-stu-id="b2da4-132">Service Request Timeout.</span></span> <span data-ttu-id="b2da4-133">Der Dienst hat auf die Startanforderung nicht rechtzeitig reagiert.</span><span class="sxs-lookup"><span data-stu-id="b2da4-133">The service did not respond to the start request in a timely fashion.</span></span>  
  
 <span data-ttu-id="b2da4-134">8</span><span class="sxs-lookup"><span data-stu-id="b2da4-134">8</span></span>  
 <span data-ttu-id="b2da4-135">Unbekannter Fehler.</span><span class="sxs-lookup"><span data-stu-id="b2da4-135">Unknown Failure.</span></span> <span data-ttu-id="b2da4-136">Beim Starten des Diensts ist ein unbekannter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="b2da4-136">An unknown failure occurred when starting the service.</span></span>  
  
 <span data-ttu-id="b2da4-137">9</span><span class="sxs-lookup"><span data-stu-id="b2da4-137">9</span></span>  
 <span data-ttu-id="b2da4-138">Der Pfad wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="b2da4-138">Path Not Found.</span></span> <span data-ttu-id="b2da4-139">Der Verzeichnispfad zur ausführbaren Dienstdatei wurde nicht gefunden.</span><span class="sxs-lookup"><span data-stu-id="b2da4-139">The directory path to the service executable was not found.</span></span>  
  
 <span data-ttu-id="b2da4-140">10</span><span class="sxs-lookup"><span data-stu-id="b2da4-140">10</span></span>  
 <span data-ttu-id="b2da4-141">Der Dienst wird bereits ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b2da4-141">Service Already Running.</span></span> <span data-ttu-id="b2da4-142">Der Dienst wird schon ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b2da4-142">The service is already running.</span></span>  
  
 <span data-ttu-id="b2da4-143">11</span><span class="sxs-lookup"><span data-stu-id="b2da4-143">11</span></span>  
 <span data-ttu-id="b2da4-144">Die Dienstdatenbank ist gesperrt.</span><span class="sxs-lookup"><span data-stu-id="b2da4-144">Service Database Locked.</span></span> <span data-ttu-id="b2da4-145">Die Datenbank zum Hinzufügen eines neuen Diensts ist gesperrt.</span><span class="sxs-lookup"><span data-stu-id="b2da4-145">The database to add a new service is locked.</span></span>  
  
 <span data-ttu-id="b2da4-146">12</span><span class="sxs-lookup"><span data-stu-id="b2da4-146">12</span></span>  
 <span data-ttu-id="b2da4-147">Die Dienstabhängigkeit wurde gelöscht.</span><span class="sxs-lookup"><span data-stu-id="b2da4-147">Service Dependency Deleted.</span></span> <span data-ttu-id="b2da4-148">Eine Abhängigkeit, von der dieser Dienst abhängt, wurde aus dem System entfernt.</span><span class="sxs-lookup"><span data-stu-id="b2da4-148">A dependency on which this service relies has been removed from the system.</span></span>  
  
 <span data-ttu-id="b2da4-149">13</span><span class="sxs-lookup"><span data-stu-id="b2da4-149">13</span></span>  
 <span data-ttu-id="b2da4-150">Dienstabhängigkeitenfehler.</span><span class="sxs-lookup"><span data-stu-id="b2da4-150">Service Dependency Failure.</span></span> <span data-ttu-id="b2da4-151">Der Dienst hat den Dienst nicht gefunden, der von einem abhängigen Dienst benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="b2da4-151">The service failed to find the service needed from a dependent service.</span></span>  
  
 <span data-ttu-id="b2da4-152">14</span><span class="sxs-lookup"><span data-stu-id="b2da4-152">14</span></span>  
 <span data-ttu-id="b2da4-153">Der Dienst ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b2da4-153">Service Disabled.</span></span> <span data-ttu-id="b2da4-154">Der Dienst wurde vom System deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="b2da4-154">The service has been disabled from the system.</span></span>  
  
 <span data-ttu-id="b2da4-155">15</span><span class="sxs-lookup"><span data-stu-id="b2da4-155">15</span></span>  
 <span data-ttu-id="b2da4-156">Fehler bei der Dienstanmeldung.</span><span class="sxs-lookup"><span data-stu-id="b2da4-156">Service Logon Failed.</span></span> <span data-ttu-id="b2da4-157">Der Dienst hat nicht die richtige Authentifizierung, um im System ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="b2da4-157">The service does not have the correct authentication to run on the system.</span></span>  
  
 <span data-ttu-id="b2da4-158">16</span><span class="sxs-lookup"><span data-stu-id="b2da4-158">16</span></span>  
 <span data-ttu-id="b2da4-159">Der Dienst ist zum Löschen markiert.</span><span class="sxs-lookup"><span data-stu-id="b2da4-159">Service Marked For Deletion.</span></span> <span data-ttu-id="b2da4-160">Der Dienst wird aus dem System entfernt.</span><span class="sxs-lookup"><span data-stu-id="b2da4-160">The service is being removed from the system.</span></span>  
  
 <span data-ttu-id="b2da4-161">17</span><span class="sxs-lookup"><span data-stu-id="b2da4-161">17</span></span>  
 <span data-ttu-id="b2da4-162">Der Dienst besitzt keinen Thread.</span><span class="sxs-lookup"><span data-stu-id="b2da4-162">Service No Thread.</span></span> <span data-ttu-id="b2da4-163">Es gibt keinen Ausführungsthread für den Dienst.</span><span class="sxs-lookup"><span data-stu-id="b2da4-163">There is no execution thread for the service.</span></span>  
  
 <span data-ttu-id="b2da4-164">18</span><span class="sxs-lookup"><span data-stu-id="b2da4-164">18</span></span>  
 <span data-ttu-id="b2da4-165">Ringabhängigkeitsstatus.</span><span class="sxs-lookup"><span data-stu-id="b2da4-165">Status Circular Dependency.</span></span> <span data-ttu-id="b2da4-166">Es gibt Ringabhängigkeiten beim Starten des Diensts.</span><span class="sxs-lookup"><span data-stu-id="b2da4-166">There are circular dependencies when starting the service.</span></span>  
  
 <span data-ttu-id="b2da4-167">19</span><span class="sxs-lookup"><span data-stu-id="b2da4-167">19</span></span>  
 <span data-ttu-id="b2da4-168">Doppelter Name.</span><span class="sxs-lookup"><span data-stu-id="b2da4-168">Status Duplicate Name.</span></span> <span data-ttu-id="b2da4-169">Es wird ein Dienst unter dem gleichen Namen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b2da4-169">There is a service running under the same name.</span></span>  
  
 <span data-ttu-id="b2da4-170">20</span><span class="sxs-lookup"><span data-stu-id="b2da4-170">20</span></span>  
 <span data-ttu-id="b2da4-171">Ungültiger Name.</span><span class="sxs-lookup"><span data-stu-id="b2da4-171">Status Invalid Name.</span></span> <span data-ttu-id="b2da4-172">Im Namen des Dienstes sind ungültige Zeichen vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b2da4-172">There are characters that are not valid in the name of the service.</span></span>  
  
 <span data-ttu-id="b2da4-173">21</span><span class="sxs-lookup"><span data-stu-id="b2da4-173">21</span></span>  
 <span data-ttu-id="b2da4-174">Ungültige Parameter.</span><span class="sxs-lookup"><span data-stu-id="b2da4-174">Status Invalid Parameter.</span></span> <span data-ttu-id="b2da4-175">Ungültige Parameter wurden an den Dienst übergeben.</span><span class="sxs-lookup"><span data-stu-id="b2da4-175">Parameters that are not valid have been passed to the service.</span></span>  
  
 <span data-ttu-id="b2da4-176">22</span><span class="sxs-lookup"><span data-stu-id="b2da4-176">22</span></span>  
 <span data-ttu-id="b2da4-177">Ungültiges Dienstkonto.</span><span class="sxs-lookup"><span data-stu-id="b2da4-177">Status Invalid Service Account.</span></span> <span data-ttu-id="b2da4-178">Das Konto, unter dem dieser Dienst ausgeführt werden soll, ist nicht gültigt oder verfügt nicht über die Berechtigung zum Ausführen des Diensts.</span><span class="sxs-lookup"><span data-stu-id="b2da4-178">The account which this service is to run under is not valid, or it lacks the permissions to run the service.</span></span>  
  
 <span data-ttu-id="b2da4-179">23</span><span class="sxs-lookup"><span data-stu-id="b2da4-179">23</span></span>  
 <span data-ttu-id="b2da4-180">Der Dienst ist bereits vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b2da4-180">Status Service Exists.</span></span> <span data-ttu-id="b2da4-181">Der Dienst ist in der Datenbank der im System verfügbaren Dienste vorhanden.</span><span class="sxs-lookup"><span data-stu-id="b2da4-181">The service exists in the database of services available from the system.</span></span>  
  
 <span data-ttu-id="b2da4-182">24</span><span class="sxs-lookup"><span data-stu-id="b2da4-182">24</span></span>  
 <span data-ttu-id="b2da4-183">Der Dienst wurde bereits angehalten.</span><span class="sxs-lookup"><span data-stu-id="b2da4-183">Service Already Paused.</span></span> <span data-ttu-id="b2da4-184">Der Dienst ist im System derzeitig angehalten.</span><span class="sxs-lookup"><span data-stu-id="b2da4-184">The service is currently paused in the system.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b2da4-185">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="b2da4-185">Remarks</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b2da4-186">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b2da4-186">See Also</span></span>  
 <span data-ttu-id="b2da4-187">[Starten und Beenden von Diensten](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span><span class="sxs-lookup"><span data-stu-id="b2da4-187">[Starting and Stopping Services](https://technet.microsoft.com/library/ms174886\(v=sql.105\).aspx)</span></span>  
  
  
