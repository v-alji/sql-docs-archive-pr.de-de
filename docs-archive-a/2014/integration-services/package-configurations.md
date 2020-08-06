---
title: Paket Konfigurationen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
helpviewer_keywords:
- package configuration syntax [Integration Services]
- SQL Server Integration Services packages, configurations
- SSIS packages, configurations
- XML [Integration Services]
- Integration Services packages, configurations
- configuration syntax [Integration Services]
- indirect configurations [Integration Services]
- configurations [Integration Services]
- direct configurations [Integration Services]
- packages [Integration Services], configurations
ms.assetid: d20e0311-1fc9-4ddc-a381-6d127cf11b69
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 0d22dbfedcf4cf7084e1667586f9774926f3b2a2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87622776"
---
# <a name="package-configurations"></a><span data-ttu-id="54d14-102">Paketkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="54d14-102">Package Configurations</span></span>
  [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="54d14-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] stellt Paketkonfigurationen bereit, die Sie zum Aktualisieren der Werte von Eigenschaften zur Laufzeit verwenden können.</span><span class="sxs-lookup"><span data-stu-id="54d14-103">[!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] provides package configurations that you can use to update the values of properties at run time.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="54d14-104">Konfigurationen sind für das Paketbereitstellungsmodell verfügbar.</span><span class="sxs-lookup"><span data-stu-id="54d14-104">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="54d14-105">Parameter werden für das Projektbereitstellungsmodell anstelle von Konfigurationen verwendet.</span><span class="sxs-lookup"><span data-stu-id="54d14-105">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="54d14-106">Mithilfe des Projektbereitstellungsmodells können Sie [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Projekte auf dem [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] -Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="54d14-106">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="54d14-107">Weitere Informationen zu Bereitstellungsmodellen finden Sie unter [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="54d14-107">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="54d14-108">Eine Konfiguration ist ein Eigenschaft/Wert-Paar, das zu einem fertigen Paket hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="54d14-108">A configuration is a property/value pair that you add to a completed package.</span></span> <span data-ttu-id="54d14-109">Normalerweise erstellen Sie ein Paket, legen bei der Paketentwicklung die Eigenschaften der Paketobjekte fest und fügen die Konfiguration dem Paket hinzu.</span><span class="sxs-lookup"><span data-stu-id="54d14-109">Typically, you create a package set properties on the package objects during package development, and then add the configuration to the package.</span></span> <span data-ttu-id="54d14-110">Bei der Ausführung ruft das Paket die neuen Werte für die Eigenschaften aus der Konfiguration ab.</span><span class="sxs-lookup"><span data-stu-id="54d14-110">When the package runs, it gets the new values of the property from the configuration.</span></span> <span data-ttu-id="54d14-111">Sie können mithilfe einer Konfiguration beispielsweise die Verbindungszeichenfolge eines Verbindungs-Managers ändern oder den Wert einer Variablen aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="54d14-111">For example, by using a configuration, you can change the connection string of a connection manager, or update the value of a variable.</span></span>  
  
 <span data-ttu-id="54d14-112">Paketkonfigurationen bieten die folgenden Vorteile:</span><span class="sxs-lookup"><span data-stu-id="54d14-112">Package configurations provide the following benefits:</span></span>  
  
-   <span data-ttu-id="54d14-113">Konfigurationen erleichtern das Verschieben von Paketen aus einer Entwicklungsumgebung in eine Produktionsumgebung.</span><span class="sxs-lookup"><span data-stu-id="54d14-113">Configurations make it easier to move packages from a development environment to a production environment.</span></span> <span data-ttu-id="54d14-114">Mit einer Konfiguration können Sie z. B. den Pfad einer Quelldatei aktualisieren oder den Namen einer Datenbank oder eines Servers ändern.</span><span class="sxs-lookup"><span data-stu-id="54d14-114">For example, a configuration can update the path of a source file, or change the name of a database or server.</span></span>  
  
-   <span data-ttu-id="54d14-115">Konfigurationen sind nützlich, wenn Sie Pakete für viele unterschiedliche Server bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="54d14-115">Configurations are useful when you deploy packages to many different servers.</span></span> <span data-ttu-id="54d14-116">Eine Variable in der Konfiguration für jedes bereitgestellte Paket kann beispielsweise verschiedene Speicherplatzwerte enthalten, und wenn der verfügbare Speicherplatz nicht dem Wert entspricht, kann das Paket nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="54d14-116">For example, a variable in the configuration for each deployed package can contain a different disk space value, and if the available disk space does not meet this value, the package does not run.</span></span>  
  
-   <span data-ttu-id="54d14-117">Konfigurationen machen Pakete flexibler.</span><span class="sxs-lookup"><span data-stu-id="54d14-117">Configurations make packages more flexible.</span></span> <span data-ttu-id="54d14-118">So kann z. B. eine Konfiguration den Wert einer Variablen aktualisieren, die in einem Eigenschaftsausdruck verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="54d14-118">For example, a configuration can update the value of a variable that is used in a property expression.</span></span>  
  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="54d14-119">unterstützt verschiedene unterschiedliche Methoden zum Speichern von Paketkonfigurationen, z.B. als XML-Dateien, als Tabellen in einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenbank und als Umgebungs- und Paketvariablen.</span><span class="sxs-lookup"><span data-stu-id="54d14-119">supports several different methods of storing package configurations, such as XML files, tables in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database, and environment and package variables.</span></span>  
  
 <span data-ttu-id="54d14-120">Jede Konfiguration besteht aus einem Paar aus Eigenschaft und Wert.</span><span class="sxs-lookup"><span data-stu-id="54d14-120">Each configuration is a property/value pair.</span></span> <span data-ttu-id="54d14-121">Die XML-Konfigurationsdatei und die [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Konfigurationstypen können mehrere Konfigurationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="54d14-121">The XML configuration file and [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] configuration types can include multiple configurations.</span></span>  
  
 <span data-ttu-id="54d14-122">Die Konfigurationen werden einbezogen, wenn Sie ein Paketbereitstellungshilfsprogramm zum Installieren von Paketen erstellen.</span><span class="sxs-lookup"><span data-stu-id="54d14-122">The configurations are included when you create a package deployment utility for installing packages.</span></span> <span data-ttu-id="54d14-123">Wenn Sie die Pakete installieren, können die Konfigurationen im Rahmen eines Schritts bei der Paketinstallation aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="54d14-123">When you install the packages, the configurations can be updated as a step in the package installation.</span></span>  
  
## <a name="understanding-how-package-configurations-are-applied-at-run-time"></a><span data-ttu-id="54d14-124">Grundlegendes zur Anwendung von Paketkonfigurationen zur Laufzeit</span><span class="sxs-lookup"><span data-stu-id="54d14-124">Understanding How Package Configurations Are Applied at Run Time</span></span>  
 <span data-ttu-id="54d14-125">Wenn Sie das Befehlszeilen-Hilfsprogramm **dtexec.exe** verwenden, um ein bereitgestelltes Paket auszuführen, wendet das Hilfsprogramm Paketkonfigurationen zweimal an.</span><span class="sxs-lookup"><span data-stu-id="54d14-125">When you use the **dtexec** command prompt utility (dtexec.exe) to run a deployed package, the utility applies package configurations twice.</span></span> <span data-ttu-id="54d14-126">Das Hilfsprogramm wendet Konfigurationen sowohl vor als auch nach dem Anwenden der Optionen an, die Sie in der Befehlszeile angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="54d14-126">The utility applies configurations both before and after it applies the options that you specified on command line.</span></span>  
  
 <span data-ttu-id="54d14-127">Während das Hilfsprogramm das Paket lädt und ausführt, treten Ereignisse in der folgenden Reihenfolge auf:</span><span class="sxs-lookup"><span data-stu-id="54d14-127">As the utility loads and runs the package, events occur in the following order:</span></span>  
  
1.  <span data-ttu-id="54d14-128">Das Hilfsprogramm **dtexec** lädt das Paket.</span><span class="sxs-lookup"><span data-stu-id="54d14-128">The **dtexec** utility loads the package.</span></span>  
  
2.  <span data-ttu-id="54d14-129">Das Hilfsprogramm wendet die Konfigurationen, die zur Entwurfszeit im Paket angegeben wurden, in der Reihenfolge an, die im Paket festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="54d14-129">The utility applies the configurations that were specified in the package at design time and in the order that is specified in the package.</span></span> <span data-ttu-id="54d14-130">(Die einzige Ausnahme ist hierbei die Variablenkonfiguration für übergeordnete Pakete.</span><span class="sxs-lookup"><span data-stu-id="54d14-130">(The one exception to this is the Parent Package Variables configurations.</span></span> <span data-ttu-id="54d14-131">Das Hilfsprogramm wendet diese Konfigurationen nur einmal später im Prozess an.)</span><span class="sxs-lookup"><span data-stu-id="54d14-131">The utility applies these configurations only once and later in the process.)</span></span>  
  
3.  <span data-ttu-id="54d14-132">Das Hilfsprogramm wendet dann alle Optionen an, die Sie in der Befehlszeile angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="54d14-132">The utility then applies any options that you specified on the command line.</span></span>  
  
4.  <span data-ttu-id="54d14-133">Anschließend lädt das Hilfsprogramm die Konfigurationen neu, die zur Entwurfszeit im Paket angegeben wurden. Dabei wird die Reihenfolge verwendet, die im Paket festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="54d14-133">The utility then reloads the configurations that were specified in the package at design time and in the order specified in the package.</span></span> <span data-ttu-id="54d14-134">(Die Ausnahme von dieser Regel ist wiederum die Variablenkonfiguration für übergeordnete Pakete.)</span><span class="sxs-lookup"><span data-stu-id="54d14-134">(Again, the exception to this rule is the Parent Package Variables configurations).</span></span> <span data-ttu-id="54d14-135">Das Hilfsprogramm verwendet alle angegebenen Befehlszeilenoptionen, um die Konfigurationen neu zu laden.</span><span class="sxs-lookup"><span data-stu-id="54d14-135">The utility uses any command-line options that were specified to reload the configurations.</span></span> <span data-ttu-id="54d14-136">Es kann also sein, dass andere Werte von einem anderen Speicherort erneut geladen werden.</span><span class="sxs-lookup"><span data-stu-id="54d14-136">Therefore, different values might be reloaded from a different location.</span></span>  
  
5.  <span data-ttu-id="54d14-137">Das Hilfsprogramm wendet die Variablenkonfiguration für übergeordnete Pakete an.</span><span class="sxs-lookup"><span data-stu-id="54d14-137">The utility applies the Parent Package Variable configurations.</span></span>  
  
6.  <span data-ttu-id="54d14-138">Das Hilfsprogramm führt das Paket aus.</span><span class="sxs-lookup"><span data-stu-id="54d14-138">The utility runs the package.</span></span>  
  
 <span data-ttu-id="54d14-139">Die Art und Weise, wie das Hilfsprogramm **dtexec** Konfigurationen anwendet, wirkt sich auf die folgenden Befehlszeilenoptionen aus:</span><span class="sxs-lookup"><span data-stu-id="54d14-139">The way in which the **dtexec** utility applies configurations affects the following command-line options:</span></span>  
  
-   <span data-ttu-id="54d14-140">Sie können zur Laufzeit die Option **/Connection** oder **/Set** verwenden, um Paketkonfigurationen von einem anderen Speicherort als dem zur Entwurfszeit angegebenen Speicherort zu laden.</span><span class="sxs-lookup"><span data-stu-id="54d14-140">You can use the **/Connection** or **/Set** option at run time to load package configurations from a location other than the location that you specified at design time.</span></span>  
  
-   <span data-ttu-id="54d14-141">Sie können die Option **/ConfigFile** verwenden, um zur Laufzeit zusätzliche Konfigurationen zu laden, die Sie zur Entwurfszeit nicht angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="54d14-141">You can use the **/ConfigFile** option to load additional configurations that you did not specify at design time.</span></span>  
  
 <span data-ttu-id="54d14-142">Für diese Befehlszeilenoptionen gelten jedoch einige Einschränkungen:</span><span class="sxs-lookup"><span data-stu-id="54d14-142">However, these command-line options do have some restrictions:</span></span>  
  
-   <span data-ttu-id="54d14-143">Sie können die Option **/Set** oder **/Connection** nicht verwenden, um einzelne Werte zu überschreiben, die auch von einer Konfiguration festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="54d14-143">You cannot use the **/Set** or the **/Connection** option to override single values that are also set by a configuration.</span></span>  
  
-   <span data-ttu-id="54d14-144">Sie können die Option **/ConfigFile** nicht verwenden, um Konfigurationen zu laden, die die zur Entwurfszeit angegebenen Konfigurationen ersetzen.</span><span class="sxs-lookup"><span data-stu-id="54d14-144">You cannot use the **/ConfigFile** option to load configurations that replace the configurations that you specified at design time.</span></span>  
  
 <span data-ttu-id="54d14-145">Weitere Informationen zu diesen Optionen und dazu, wie sich das Verhalten dieser Optionen zwischen [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] und früheren Versionen unterscheidet, finden [Sie unter Verhaltensänderungen in Integration Services Features in SQL Server 2014](../../2014/integration-services/behavior-changes-to-integration-services-features-in-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="54d14-145">For more information about these options, and how the behavior of these options differs between [!INCLUDE[ssISCurrent](../includes/ssiscurrent-md.md)] and earlier versions, see [Behavior Changes to Integration Services Features in SQL Server 2014](../../2014/integration-services/behavior-changes-to-integration-services-features-in-sql-server-2014.md).</span></span>  
  
## <a name="package-configuration-types"></a><span data-ttu-id="54d14-146">Paketkonfigurationstypen</span><span class="sxs-lookup"><span data-stu-id="54d14-146">Package Configuration Types</span></span>  
 <span data-ttu-id="54d14-147">Die folgende Tabelle beschreibt die verschiedenen Paketkonfigurationstypen.</span><span class="sxs-lookup"><span data-stu-id="54d14-147">The following table describes the package configuration types.</span></span>  
  
|<span data-ttu-id="54d14-148">type</span><span class="sxs-lookup"><span data-stu-id="54d14-148">Type</span></span>|<span data-ttu-id="54d14-149">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="54d14-149">Description</span></span>|  
|----------|-----------------|  
|<span data-ttu-id="54d14-150">XML-Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="54d14-150">XML configuration file</span></span>|<span data-ttu-id="54d14-151">Eine XML-Datei enthält die Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="54d14-151">An XML file contains the configurations.</span></span> <span data-ttu-id="54d14-152">Die XML-Datei kann mehrere Konfigurationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="54d14-152">The XML file can include multiple configurations.</span></span>|  
|<span data-ttu-id="54d14-153">Umgebungsvariable</span><span class="sxs-lookup"><span data-stu-id="54d14-153">Environment variable</span></span>|<span data-ttu-id="54d14-154">Eine Umgebungsvariable enthält die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="54d14-154">An environment variable contains the configuration.</span></span>|  
|<span data-ttu-id="54d14-155">Registrierungseintrag</span><span class="sxs-lookup"><span data-stu-id="54d14-155">Registry entry</span></span>|<span data-ttu-id="54d14-156">Ein Registrierungseintrag enthält die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="54d14-156">A Registry entry contains the configuration.</span></span>|  
|<span data-ttu-id="54d14-157">Variable für das übergeordnete Paket</span><span class="sxs-lookup"><span data-stu-id="54d14-157">Parent package variable</span></span>|<span data-ttu-id="54d14-158">Eine Variable im Paket enthält die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="54d14-158">A variable in the package contains the configuration.</span></span> <span data-ttu-id="54d14-159">Dieser Konfigurationstyp wird normalerweise zum Aktualisieren von Eigenschaften in untergeordneten Paketen verwendet.</span><span class="sxs-lookup"><span data-stu-id="54d14-159">This configuration type is typically used to update properties in child packages.</span></span>|  
|[!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)]<span data-ttu-id="54d14-160">-Tabelle</span><span class="sxs-lookup"><span data-stu-id="54d14-160">table</span></span>|<span data-ttu-id="54d14-161">Eine Tabelle in einer [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenbank enthält die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="54d14-161">A table in a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database contains the configuration.</span></span> <span data-ttu-id="54d14-162">Die Tabelle kann mehrere Konfigurationen enthalten.</span><span class="sxs-lookup"><span data-stu-id="54d14-162">The table can include multiple configurations.</span></span>|  
  
### <a name="xml-configuration-files"></a><span data-ttu-id="54d14-163">XML-Konfigurationsdateien</span><span class="sxs-lookup"><span data-stu-id="54d14-163">XML Configuration Files</span></span>  
 <span data-ttu-id="54d14-164">Wenn Sie den Konfigurationstyp **XML-Konfigurationsdatei** auswählen, können Sie eine neue Konfigurationsdatei erstellen, eine vorhandene Datei erneut verwenden und neue Konfigurationen hinzufügen oder eine vorhandene Datei erneut verwenden und dabei den bisherigen Dateiinhalt überschreiben.</span><span class="sxs-lookup"><span data-stu-id="54d14-164">If you select the **XML configuration file** configuration type, you can create a new configuration file, reuse an existing file and add new configurations, or reuse an existing file but overwrite existing file content.</span></span>  
  
 <span data-ttu-id="54d14-165">Eine XML-Konfigurationsdatei besteht aus zwei Abschnitten:</span><span class="sxs-lookup"><span data-stu-id="54d14-165">An XML configuration file includes two sections:</span></span>  
  
-   <span data-ttu-id="54d14-166">Einer Überschrift, die Informationen zur Konfigurationsdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="54d14-166">A heading that contains information about the configuration file.</span></span> <span data-ttu-id="54d14-167">Dieses Element enthält Attribute wie z. B. der Erstellungszeitpunkt der Datei und den Namen der Person, von der die Datei erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="54d14-167">This element includes attributes such as when the file was created and the name of the person who generated the file.</span></span>  
  
-   <span data-ttu-id="54d14-168">Konfigurationselemente können Informationen zu jeder Konfiguration enthalten.</span><span class="sxs-lookup"><span data-stu-id="54d14-168">Configuration elements that contain information about each configuration.</span></span> <span data-ttu-id="54d14-169">Dieses Element enthält Attribute wie z. B. den Eigenschaftspfad und den konfigurierten Wert einer Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="54d14-169">This element includes attributes such as the property path and the configured value of a property.</span></span>  
  
 <span data-ttu-id="54d14-170">Das folgende XML-Codebeispiel veranschaulicht die Syntax von XML-Konfigurationsdateien.</span><span class="sxs-lookup"><span data-stu-id="54d14-170">The following XML code demonstrates the syntax of an XML configuration file.</span></span> <span data-ttu-id="54d14-171">Das Beispiel zeigt eine Konfiguration für die Value-Eigenschaft der ganzzahligen Variable `MyVar`.</span><span class="sxs-lookup"><span data-stu-id="54d14-171">This example shows a configuration for the Value property of an integer variable named `MyVar`.</span></span>  
  
```  
<?xml version="1.0"?>  
<DTSConfiguration>  
   <DTSConfigurationHeading>  
      <DTSConfigurationFileInfo  
          GeneratedBy="DomainName\UserName"  
          GeneratedFromPackageName="Package"  
          GeneratedFromPackageID="{2AF06766-817A-4E28-9878-0DE37A150648}"  
          GeneratedDate="2/01/2005 5:58:09 PM"/>  
   </DTSConfigurationHeading>  
   <Configuration ConfiguredType="Property" Path="\Package.Variables[User::MyVar].Value" ValueType="Int32">  
      <ConfiguredValue>0</ConfiguredValue>  
   </Configuration>  
</DTSConfiguration>  
  
```  
  
### <a name="registry-entry"></a><span data-ttu-id="54d14-172">Registrierungseintrag</span><span class="sxs-lookup"><span data-stu-id="54d14-172">Registry Entry</span></span>  
 <span data-ttu-id="54d14-173">Wenn Sie zum Speichern einer Konfiguration einen Registrierungseintrag verwenden möchten, können Sie entweder einen vorhandenen Schlüssel verwenden oder einen neuen Schlüssel in HKEY_CURRENT_USER erstellen.</span><span class="sxs-lookup"><span data-stu-id="54d14-173">If you want to use a Registry entry to store the configuration, you can either use an existing key or create a new key in HKEY_CURRENT_USER.</span></span> <span data-ttu-id="54d14-174">Der verwendete Registrierungsschlüssel muss einen Wert mit dem Namen `Value` aufweisen.</span><span class="sxs-lookup"><span data-stu-id="54d14-174">The Registry key that you use must have a value named `Value`.</span></span> <span data-ttu-id="54d14-175">Bei diesem Wert kann es sich um einen Wert vom Typ DWORD oder um eine Zeichenfolge handeln.</span><span class="sxs-lookup"><span data-stu-id="54d14-175">The value can be a DWORD or a string.</span></span>  
  
 <span data-ttu-id="54d14-176">Wenn Sie den Konfigurationstyp **Registrierungseintrag** auswählen, geben Sie den Namen des Registrierungsschlüssels im Eingabefeld Registrierung ein.</span><span class="sxs-lookup"><span data-stu-id="54d14-176">If you select the **Registry entry** configuration type, you type the name of the Registry key in the Registry entry box.</span></span> <span data-ttu-id="54d14-177">Das Format ist \<registry key>.</span><span class="sxs-lookup"><span data-stu-id="54d14-177">The format is \<registry key>.</span></span> <span data-ttu-id="54d14-178">Wenn Sie einen Registrierungsschlüssel verwenden möchten, der nicht im Stamm von HKEY_CURRENT_USER enthalten ist, verwenden Sie das Format \<Registry key\registry key\\...>, um den Schlüssel zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="54d14-178">If you want to use a Registry key that is not at the root of HKEY_CURRENT_USER, use the format \<Registry key\registry key\\...> to identify the key.</span></span> <span data-ttu-id="54d14-179">Wenn Sie beispielsweise den Schlüssel MyPackage verwenden, der sich in SSISPackages befindet, geben Sie `SSISPackages\MyPackage` ein.</span><span class="sxs-lookup"><span data-stu-id="54d14-179">For example, to use the MyPackage key located in SSISPackages, type `SSISPackages\MyPackage`.</span></span>  
  
### <a name="sql-server"></a><span data-ttu-id="54d14-180">SQL Server</span><span class="sxs-lookup"><span data-stu-id="54d14-180">SQL Server</span></span>  
 <span data-ttu-id="54d14-181">Wenn Sie den Konfigurationstyp **SQL Server** auswählen, geben Sie die Verbindung mit der [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] -Datenbank an, in der die Konfigurationen gespeichert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="54d14-181">If you select the **SQL Server** configuration type, you specify the connection to the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] database in which you want to store the configurations.</span></span> <span data-ttu-id="54d14-182">Sie können die Konfigurationen in einer vorhandenen Tabelle speichern oder eine neue Tabelle in der angegebenen Datenbank erstellen.</span><span class="sxs-lookup"><span data-stu-id="54d14-182">You can save the configurations to an existing table or create a new table in the specified database.</span></span>  
  
 <span data-ttu-id="54d14-183">Die folgende SQL-Anweisung zeigt die standardmäßige CREATE TABLE-Anweisung, die der Paketkonfigurations-Assistent bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="54d14-183">The following SQL statement shows the default CREATE TABLE statement that the Package Configuration Wizard provides.</span></span>  
  
```  
CREATE TABLE [dbo].[SSIS Configurations]  
(  
ConfigurationFilter NVARCHAR(255) NOT NULL,  
ConfiguredValue NVARCHAR(255) NULL,  
PackagePath NVARCHAR(255) NOT NULL,  
ConfiguredValueType NVARCHAR(20) NOT NULL  
)  
  
```  
  
 <span data-ttu-id="54d14-184">Der Name, den Sie für die Konfiguration bereitstellen, ist der Wert, der in der **ConfigurationFilter** -Spalte gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="54d14-184">The name that you provide for the configuration is the value stored in the **ConfigurationFilter** column.</span></span>  
  
## <a name="direct-and-indirect-configurations"></a><span data-ttu-id="54d14-185">Direkte und indirekte Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="54d14-185">Direct and Indirect Configurations</span></span>  
 [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="54d14-186">ermöglicht direkte und indirekte Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="54d14-186">provides direct and indirect configurations.</span></span> <span data-ttu-id="54d14-187">Wenn Sie Konfigurationen direkt angeben, erstellt [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] eine direkte Verknüpfung zwischen dem Konfigurationselement und der Paketobjekteigenschaft.</span><span class="sxs-lookup"><span data-stu-id="54d14-187">If you specify configurations directly, [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] creates a direct link between the configuration item and the package object property.</span></span> <span data-ttu-id="54d14-188">Direkte Konfigurationen sind die bessere Wahl, wenn sich der Speicherort der Quelle nicht ändert.</span><span class="sxs-lookup"><span data-stu-id="54d14-188">Direct configurations are a better choice when the location of the source does not change.</span></span> <span data-ttu-id="54d14-189">Wenn Sie z. B. sicher sind, dass alle Bereitstellungen im Paket denselben Dateipfad verwenden, können Sie eine XML-Konfigurationsdatei angeben.</span><span class="sxs-lookup"><span data-stu-id="54d14-189">For example, if you are sure that all deployments in the package use the same file path, you can specify an XML configuration file.</span></span>  
  
 <span data-ttu-id="54d14-190">Indirekte Konfigurationen verwenden Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="54d14-190">Indirect configurations use environment variables.</span></span> <span data-ttu-id="54d14-191">Statt die Konfigurationseinstellung direkt anzugeben, zeigt die Konfiguration auf eine Umgebungsvariable, die ihrerseits den Konfigurationswert enthält.</span><span class="sxs-lookup"><span data-stu-id="54d14-191">Instead of specifying the configuration setting directly, the configuration points to an environment variable, which in turn contains the configuration value.</span></span> <span data-ttu-id="54d14-192">Das Verwenden indirekter Konfigurationen ist die bessere Wahl, wenn sich der Speicherort der Konfiguration für jede Bereitstellung eines Pakets ändern kann.</span><span class="sxs-lookup"><span data-stu-id="54d14-192">Using indirect configurations is a better choice when the location of the configuration can change for each deployment of a package.</span></span>  
  
## <a name="related-tasks"></a><span data-ttu-id="54d14-193">Related Tasks</span><span class="sxs-lookup"><span data-stu-id="54d14-193">Related Tasks</span></span>  
 [<span data-ttu-id="54d14-194">Erstellen von Paketkonfigurationen</span><span class="sxs-lookup"><span data-stu-id="54d14-194">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
## <a name="related-content"></a><span data-ttu-id="54d14-195">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="54d14-195">Related Content</span></span>  
  
-   <span data-ttu-id="54d14-196">Technischer Artikel [Grundlegendes zu Integration Services-Paketkonfigurationen](https://go.microsoft.com/fwlink/?LinkId=165643)auf msdn.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="54d14-196">Technical article, [Understanding Integration Services Package Configurations](https://go.microsoft.com/fwlink/?LinkId=165643), on msdn.microsoft.com</span></span>  
  
-   <span data-ttu-id="54d14-197">Blog Eintrag [Erstellen von Paketen in Code Paket Konfigurationen](https://go.microsoft.com/fwlink/?LinkId=217663)auf www.sqlis.com.</span><span class="sxs-lookup"><span data-stu-id="54d14-197">Blog entry, [Creating packages in code - Package Configurations](https://go.microsoft.com/fwlink/?LinkId=217663), on www.sqlis.com.</span></span>  
  
-   <span data-ttu-id="54d14-198">Blog Eintrag [API-Beispiel: Programm gesteuertes Hinzufügen einer Konfigurationsdatei zu einem Paket](https://go.microsoft.com/fwlink/?LinkId=217664)auf Blogs.msdn.com.</span><span class="sxs-lookup"><span data-stu-id="54d14-198">Blog entry, [API Sample - Programmatically add a configuration file to a package](https://go.microsoft.com/fwlink/?LinkId=217664), on blogs.msdn.com.</span></span>  
  
  
