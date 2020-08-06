---
title: Behandeln von Fehlern und Warnungen (XMLA) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
helpviewer_keywords:
- errors [XML for Analysis]
- inline errors [XMLA]
- SOAP faults [XML for Analysis]
- XML for Analysis, errors
- faults [XML for Analysis]
- messages [XML for Analysis]
- XMLA, errors
- warnings [XML for Analysis]
- inline warnings [XMLA]
ms.assetid: ab895282-098d-468e-9460-032598961f45
author: minewiskan
ms.author: owend
ms.openlocfilehash: 07b88d800237e5b4b06af0c1ff11cbd0af846600
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87616774"
---
# <a name="handling-errors-and-warnings-xmla"></a><span data-ttu-id="c5c60-102">Behandeln von Fehlern und Warnungen (XMLA)</span><span class="sxs-lookup"><span data-stu-id="c5c60-102">Handling Errors and Warnings (XMLA)</span></span>
  <span data-ttu-id="c5c60-103">Eine Fehlerbehandlung ist notwendig, wenn ein XMLA-Aufruf (XML for Analysis) der Methoden [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) oder [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) nicht ausgeführt wird, erfolgreich ausgeführt wird, aber Fehler oder Warnungen generiert oder erfolgreich ausgeführt wird, aber fehlerhafte Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="c5c60-103">Error handling is required when an XML for Analysis (XMLA) [Discover](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-discover) or [Execute](https://docs.microsoft.com/bi-reference/xmla/xml-elements-methods-execute) method call does not run, runs successfully but generates errors or warnings, or runs successfully but returns results that contain errors.</span></span>  
  
|<span data-ttu-id="c5c60-104">Fehler</span><span class="sxs-lookup"><span data-stu-id="c5c60-104">Error</span></span>|<span data-ttu-id="c5c60-105">Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="c5c60-105">Reporting</span></span>|  
|-----------|---------------|  
|<span data-ttu-id="c5c60-106">Der XMLA-Methodenaufruf wird nicht ausgeführt</span><span class="sxs-lookup"><span data-stu-id="c5c60-106">The XMLA method call does not run</span></span>|[!INCLUDE[msCoName](../../includes/msconame-md.md)]<span data-ttu-id="c5c60-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] gibt eine SOAP-Fehlermeldung zurück, die die Details des Fehlers enthält.</span><span class="sxs-lookup"><span data-stu-id="c5c60-107">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns a SOAP fault message that contains the details of the failure.</span></span><br /><br /> <span data-ttu-id="c5c60-108">Weitere Informationen finden Sie im Abschnitt [Behandeln von SOAP-Fehlern](#handling_soap_faults).</span><span class="sxs-lookup"><span data-stu-id="c5c60-108">For more information, see the section, [Handling SOAP Faults](#handling_soap_faults).</span></span>|  
|<span data-ttu-id="c5c60-109">Fehler oder Warnungen bei erfolgreichem Methodenaufruf</span><span class="sxs-lookup"><span data-stu-id="c5c60-109">Errors or warnings on a successful method call</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="c5c60-110">enthält ein [Error](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) -oder [Warning](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/warning-element-xmla) -Element für jeden Fehler bzw. jede Warnung in der [Messages](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla) -Eigenschaft des [root](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) -Elements, das die Ergebnisse des Methoden Aufrufes enthält.</span><span class="sxs-lookup"><span data-stu-id="c5c60-110">includes an [error](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/error-element-xmla) or [warning](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/warning-element-xmla) element for each error or warning, respectively, in the [Messages](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla) property of the [root](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/root-element-xmla) element that contains the results of the method call.</span></span><br /><br /> <span data-ttu-id="c5c60-111">Weitere Informationen finden Sie im Abschnitt [Behandeln von Fehlern und Warnungen](#handling_errors_and_warnings).</span><span class="sxs-lookup"><span data-stu-id="c5c60-111">For more information, see the section, [Handling Errors and Warnings](#handling_errors_and_warnings).</span></span>|  
|<span data-ttu-id="c5c60-112">Fehler im Ergebnis bei erfolgreichem Methodenaufruf</span><span class="sxs-lookup"><span data-stu-id="c5c60-112">Errors in the result for a successful method call</span></span>|[!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="c5c60-113">schließt ein Inline- `error` oder- `warning` Element für den Fehler bzw. die Warnung in das entsprechende [Zellen](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) -oder [Zeilen](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/row-element-xmla) Element der Ergebnisse des Methoden Aufrufes ein.</span><span class="sxs-lookup"><span data-stu-id="c5c60-113">includes an inline `error` or `warning` element for the error or warning, respectively, within the appropriate [Cell](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/cell-element-xmla) or [row](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/row-element-xmla) element of the results of the method call.</span></span><br /><br /> <span data-ttu-id="c5c60-114">Weitere Informationen finden Sie im Abschnitt [Behandeln von Inlinefehlern und -warnungen](#handling_inline_errors_and_warnings).</span><span class="sxs-lookup"><span data-stu-id="c5c60-114">For more information, see the section, [Handling Inline Errors and Warnings](#handling_inline_errors_and_warnings).</span></span>|  
  
##  <a name="handling-soap-faults"></a><a name="handling_soap_faults"></a><span data-ttu-id="c5c60-115">Behandeln von SOAP-Fehlern</span><span class="sxs-lookup"><span data-stu-id="c5c60-115">Handling SOAP Faults</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="c5c60-116">gibt einen SOAP-Fehler zurück, wenn die folgenden Situationen auftreten:</span><span class="sxs-lookup"><span data-stu-id="c5c60-116">returns a SOAP fault when the following situations occur:</span></span>  
  
-   <span data-ttu-id="c5c60-117">Die SOAP-Nachricht, die die XMLA-Methode enthält, ist nicht wohlgeformt oder konnte von der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz nicht überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="c5c60-117">The SOAP message that contains the XMLA method was not well-formed or could not be validated by the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
-   <span data-ttu-id="c5c60-118">Eine Kommunikations- oder anderer Fehler ist in Bezug auf die SOAP-Nachricht, die die XMLA-Methode enthält, aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="c5c60-118">A communications or other error occurred involving the SOAP message that contains the XMLA method.</span></span>  
  
-   <span data-ttu-id="c5c60-119">Die XMLA-Methode wurde nicht auf der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c5c60-119">The XMLA method did not run on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance.</span></span>  
  
 <span data-ttu-id="c5c60-120">Die SOAP-Fehlercodes für XMLstartA beginnen mit „XMLForAnalysis“ gefolgt von einem Punkt und dem hexadezimalen HRESULT-Ergebniscode.</span><span class="sxs-lookup"><span data-stu-id="c5c60-120">The SOAP fault codes for XMLstartA start with "XMLForAnalysis", followed by a period and the hexadecimal HRESULT result code.</span></span> <span data-ttu-id="c5c60-121">Beispielsweise wird ein Fehlercode von „`0x80000005`“ formatiert als „`XMLForAnalysis.0x80000005`“.</span><span class="sxs-lookup"><span data-stu-id="c5c60-121">For example, an error code of "`0x80000005`" is formatted as "`XMLForAnalysis.0x80000005`".</span></span> <span data-ttu-id="c5c60-122">Weitere Informationen über das SOAP-Fehlerformat finden Sie unter „Soap Fault in the W3C Simple Object Access Protocol (SOAP) 1.1“.</span><span class="sxs-lookup"><span data-stu-id="c5c60-122">For more information about the SOAP fault format, see Soap Fault in the W3C Simple Object Access Protocol (SOAP) 1.1.</span></span>  
  
### <a name="fault-code-information"></a><span data-ttu-id="c5c60-123">Fehlercodeinformationen</span><span class="sxs-lookup"><span data-stu-id="c5c60-123">Fault Code Information</span></span>  
 <span data-ttu-id="c5c60-124">Die folgende Tabelle zeigt die XMLA-Fehlercodeinformationen, die im Detailabschnitt der SOAP-Antwort enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="c5c60-124">The following table shows the XMLA fault code information that is contained in the detail section of the SOAP response.</span></span> <span data-ttu-id="c5c60-125">Die Spalten sind die Attribute eines Fehlers im Detailabschnitt eines SOAP-Fehlers.</span><span class="sxs-lookup"><span data-stu-id="c5c60-125">The columns are the attributes of an error in the detail section of a SOAP fault.</span></span>  
  
|<span data-ttu-id="c5c60-126">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c5c60-126">Column name</span></span>|<span data-ttu-id="c5c60-127">type</span><span class="sxs-lookup"><span data-stu-id="c5c60-127">Type</span></span>|<span data-ttu-id="c5c60-128">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c5c60-128">Description</span></span>|<span data-ttu-id="c5c60-129">NULL zulässig<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="c5c60-129">Null allowed<sup>1</sup></span></span>|  
|-----------------|----------|-----------------|------------------------------|  
|`ErrorCode`|`UnsignedInt`|<span data-ttu-id="c5c60-130">Rückgabecode, der den Erfolg oder das Scheitern der Methode angibt.</span><span class="sxs-lookup"><span data-stu-id="c5c60-130">Return code that indicates the success or failure of the method.</span></span> <span data-ttu-id="c5c60-131">Der Hexadezimalwert muss in einen `UnsignedInt`-Wert konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="c5c60-131">The hexadecimal value must be converted to an `UnsignedInt` value.</span></span>|<span data-ttu-id="c5c60-132">Nein</span><span class="sxs-lookup"><span data-stu-id="c5c60-132">No</span></span>|  
|`WarningCode`|`UnsignedInt`|<span data-ttu-id="c5c60-133">Rückgabecode, der eine Warnbedingung angibt.</span><span class="sxs-lookup"><span data-stu-id="c5c60-133">Return code that indicates a warning condition.</span></span> <span data-ttu-id="c5c60-134">Der Hexadezimalwert muss in einen `UnsignedInt`-Wert konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="c5c60-134">The hexadecimal value must be converted to an `UnsignedInt` value.</span></span>|<span data-ttu-id="c5c60-135">Ja</span><span class="sxs-lookup"><span data-stu-id="c5c60-135">Yes</span></span>|  
|`Description`|`String`|<span data-ttu-id="c5c60-136">Fehler- oder Warnungstext und Beschreibung, die durch die Komponente zurückgegeben werden, die den Fehler erzeugt hat.</span><span class="sxs-lookup"><span data-stu-id="c5c60-136">Error or warning text and description returned by the component that generated the error.</span></span>|<span data-ttu-id="c5c60-137">Ja</span><span class="sxs-lookup"><span data-stu-id="c5c60-137">Yes</span></span>|  
|`Source`|`String`|<span data-ttu-id="c5c60-138">Name der Komponente, die den Fehler oder die Warnung generiert hat.</span><span class="sxs-lookup"><span data-stu-id="c5c60-138">Name of the component that generated the error or warning.</span></span>|<span data-ttu-id="c5c60-139">Ja</span><span class="sxs-lookup"><span data-stu-id="c5c60-139">Yes</span></span>|  
|`HelpFile`|`String`|<span data-ttu-id="c5c60-140">Pfad oder URL zur Hilfedatei oder dem Thema, das den Fehler oder die Warnung beschreibt.</span><span class="sxs-lookup"><span data-stu-id="c5c60-140">Path or URL to the Help file or topic that describes the error or warning.</span></span>|<span data-ttu-id="c5c60-141">Ja</span><span class="sxs-lookup"><span data-stu-id="c5c60-141">Yes</span></span>|  
  
 <span data-ttu-id="c5c60-142"><sup>1</sup> gibt an, ob die Daten erforderlich sind und zurückgegeben werden müssen oder ob die Daten optional sind und eine NULL-Zeichenfolge zulässig ist, wenn die Spalte nicht anwendbar ist.</span><span class="sxs-lookup"><span data-stu-id="c5c60-142"><sup>1</sup> Indicates whether the data is required and must be returned, or whether the data is optional and a null string is allowed if the column does not apply.</span></span>  
  
 <span data-ttu-id="c5c60-143">Im Folgenden finden Sie ein Beispiel für einen SOAP-Fehler, der auftrat, als ein Methodenaufruf fehlschlug:</span><span class="sxs-lookup"><span data-stu-id="c5c60-143">The following is an example of a SOAP fault that occurred when a method call failed:</span></span>  
  
```  
<?xml version="1.0"?>  
   <SOAP-ENV:Envelope  
   xmlns:SOAP-ENV="http://schemas.xmlsoap.org/soap/envelope/"  
   SOAP-ENV:encodingStyle="http://schemas.xmlsoap.org/soap/encoding/">  
      <SOAP-ENV:Fault>  
         <faultcode>XMLAnalysisError.0x80000005</faultcode>  
         <faultstring>The XML for Analysis provider encountered an error.</faultstring>  
         <faultactor>XML for Analysis Provider</faultactor>  
         <detail>  
<Error  
ErrorCode="2147483653"  
Description="An unexpected error has occurred."  
Source="XML for Analysis Provider"  
HelpFile="" />  
         </detail>  
      </SOAP-ENV:Fault>  
</SOAP-ENV:Envelope>  
```  
  
##  <a name="handling-errors-and-warnings"></a><a name="handling_errors_and_warnings"></a><span data-ttu-id="c5c60-144">Behandeln von Fehlern und Warnungen</span><span class="sxs-lookup"><span data-stu-id="c5c60-144">Handling Errors and Warnings</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="c5c60-145">gibt die `Messages`-Eigenschaft im `root`-Element für einen Befehl zurück, wenn nach Ausführung des Befehls die folgenden Situationen auftreten:</span><span class="sxs-lookup"><span data-stu-id="c5c60-145">returns the `Messages` property in the `root` element for a command if the following situations occur after that command runs:</span></span>  
  
-   <span data-ttu-id="c5c60-146">Die Methode selber schlug nicht fehl, aber nach erfolgreicher Ausführung des Methodenaufrufs trat ein Fehler auf der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz ein.</span><span class="sxs-lookup"><span data-stu-id="c5c60-146">The method itself did not fail, but a failure occurred on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance after the method call succeeded.</span></span>  
  
-   <span data-ttu-id="c5c60-147">Die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz gibt eine Warnung zurück, wenn der Befehl erfolgreich ist.</span><span class="sxs-lookup"><span data-stu-id="c5c60-147">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance returns a warning when the command is successful.</span></span>  
  
 <span data-ttu-id="c5c60-148">Die `Messages`-Eigenschaft folgt allen Eigenschaften, die im `root`-Element enthalten sind, und kann ein oder mehr `Message`-Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="c5c60-148">The `Messages` property follows all other properties that are contained by the `root` element, and can contain one or more `Message` elements.</span></span> <span data-ttu-id="c5c60-149">Jedes `Message`-Element kann entweder ein einzelnes `error`- oder ein `warning`-Element enthalten, das entweder Fehler oder Warnungen beschreibt, die beim angegebenen Befehl aufgetreten sind.</span><span class="sxs-lookup"><span data-stu-id="c5c60-149">In turn, each `Message` element can contain either a single `error` or `warning` element describing any errors or warnings, respectively, that occurred for the specified command.</span></span>  
  
 <span data-ttu-id="c5c60-150">Weitere Informationen zu Fehlern und Warnungen, die in der-Eigenschaft enthalten sind `Messages` , finden Sie unter [Messages-Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla).</span><span class="sxs-lookup"><span data-stu-id="c5c60-150">For more information about errors and warnings that are contained in the `Messages` property, see [Messages Element &#40;XMLA&#41;](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/messages-element-xmla).</span></span>  
  
### <a name="handling-errors-during-serialization"></a><span data-ttu-id="c5c60-151">Behandeln von Fehlern während der Serialisierung</span><span class="sxs-lookup"><span data-stu-id="c5c60-151">Handling Errors During Serialization</span></span>  
 <span data-ttu-id="c5c60-152">Wenn ein Fehler auftritt, nachdem die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz bereits mit der Serialisierung der Ausgabe eines erfolgreich ausgeführten Befehls begonnen hat, gibt [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ein [Exception](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/exception-element-xmla) -Element an einem anderen Namespace als dem Punkt des Fehlers zurück.</span><span class="sxs-lookup"><span data-stu-id="c5c60-152">If an error occurs after the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance has already begun serializing the output of a successfully run command, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns an [Exception](https://docs.microsoft.com/bi-reference/xmla/xml-elements-properties/exception-element-xmla) element in a different namespace at the point of the error.</span></span> <span data-ttu-id="c5c60-153">Die [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] -Instanz schließt dann alle geöffneten Elemente, sodass das an den Client gesendete XML-Dokument gültig ist.</span><span class="sxs-lookup"><span data-stu-id="c5c60-153">The [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance then closes all open elements so that the XML document sent to the client is a valid document.</span></span> <span data-ttu-id="c5c60-154">Die Instanz gibt darüber hinaus ein `Messages`-Element zurück, das eine Beschreibung des Fehlers enthält.</span><span class="sxs-lookup"><span data-stu-id="c5c60-154">The instance also returns a `Messages` element that contains the description of the error.</span></span>  
  
##  <a name="handling-inline-errors-and-warnings"></a><a name="handling_inline_errors_and_warnings"></a><span data-ttu-id="c5c60-155">Behandeln von Inline Fehlern und-Warnungen</span><span class="sxs-lookup"><span data-stu-id="c5c60-155">Handling Inline Errors and Warnings</span></span>  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] <span data-ttu-id="c5c60-156">gibt einen Inline-`error` oder eine Inline-`warning` für einen Befehl zurück, wenn die XMLA-Methode selbst nicht fehlgeschlagen ist, aber nach einem erfolgreichen XMLA-Methodenaufruf ein Fehler, der spezifisch für ein Datenelement in den von der Methoden zurückgegebenen Ergebnissen ist, auf der [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]-Instanz aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="c5c60-156">returns an inline `error` or `warning` for a command if the XMLA method itself did not fail, but an error specific to a data element in the results returned by the method occurred on the [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] instance after the XMLA method call succeeded.</span></span>  
  
 [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)]<span data-ttu-id="c5c60-157">stellt Inline `error` -und- `warning` Elemente bereit, wenn Probleme auftreten, die für eine Zelle oder andere Daten in einem- `root` Element mit dem [MDDataSet](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/mddataset-data-type-xmla) -Datentyp spezifisch sind, z. b. ein Sicherheitsfehler oder ein Formatierungs Fehler für eine Zelle.</span><span class="sxs-lookup"><span data-stu-id="c5c60-157">supplies inline `error` and `warning` elements if issues specific to a cell or to other data that are contained within a `root` element using the [MDDataSet](https://docs.microsoft.com/bi-reference/xmla/xml-data-types/mddataset-data-type-xmla) data type occur, such as a security error or formatting error for a cell.</span></span> <span data-ttu-id="c5c60-158">In diesen Fällen gibt [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] ein `error`- oder ein `warning`-Element in der `Cell` oder im `row`-Element aus, das den Fehler oder die Warnung enthält.</span><span class="sxs-lookup"><span data-stu-id="c5c60-158">In these cases, [!INCLUDE[ssASnoversion](../../includes/ssasnoversion-md.md)] returns an `error` or `warning` element in the `Cell` or `row` element that contains the error or warning, respectively.</span></span>  
  
 <span data-ttu-id="c5c60-159">Das folgende Beispiel veranschaulicht ein Resultset, das einen Fehler in dem Rowset enthält, das von einer- `Execute` Methode mit dem- [Anweisungs](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) Befehl zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c5c60-159">The following example illustrates a result set that contains an error in the rowset returned from an `Execute` method using the [Statement](https://docs.microsoft.com/bi-reference/xmla/xml-elements-commands/statement-element-xmla) command.</span></span>  
  
```  
<return>  
   ...  
   <root>  
      ...  
      <CellData>  
      ...  
         <Cell CellOrdinal="10">  
            <Value>  
               <Error>  
                  <ErrorCode>2148497527</ErrorCode>   
                  <Description>Security Error.</Description>   
               </Error>  
            </Value>  
         </Cell>  
      </CellData>  
      ...  
   </root>  
   ...  
</return>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c5c60-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c5c60-160">See Also</span></span>  
 [<span data-ttu-id="c5c60-161">Entwickeln mit XMLA in Analysis Services</span><span class="sxs-lookup"><span data-stu-id="c5c60-161">Developing with XMLA in Analysis Services</span></span>](developing-with-xmla-in-analysis-services.md)  
  
  
