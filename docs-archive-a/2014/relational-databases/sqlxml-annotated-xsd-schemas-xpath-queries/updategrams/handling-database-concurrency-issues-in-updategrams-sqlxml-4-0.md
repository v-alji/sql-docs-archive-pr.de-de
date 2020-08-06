---
title: Behandeln von Problemen mit der Daten Bank Parallelität in Update grams (SQLXML 4,0) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- <before> block
- low concurrency protection
- database concurrency [SQLXML]
- timestamp column [SQLXML]
- updategrams [SQLXML], database concurrency
- high concurrency protection [SQLXML]
- optimistic concurrency control
- concurrency [SQLXML]
- intermediate concurrency protection [SQLXML]
ms.assetid: d4b908d1-b25b-4ad9-8478-9cd882e8c44e
author: rothja
ms.author: jroth
ms.openlocfilehash: dd808b2688e8bf05149a5454bee91123878fb2ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87619746"
---
# <a name="handling-database-concurrency-issues-in-updategrams-sqlxml-40"></a><span data-ttu-id="56173-102">Behandlungsdatenbankparallelität gibt in Updategrams (SQLXML 4.0) heraus</span><span class="sxs-lookup"><span data-stu-id="56173-102">Handling Database Concurrency Issues in Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="56173-103">Wie andere Datenbankupdatemechanismen müssen Updategrams gleichzeitige Updates von Daten in einer Mehrbenutzerumgebung verarbeiten können.</span><span class="sxs-lookup"><span data-stu-id="56173-103">Like other database update mechanisms, updategrams must deal with concurrent updates to data in a multiuser environment.</span></span> <span data-ttu-id="56173-104">Updategrams verwenden die Steuerung durch vollständige Parallelität, bei der ausgewählte Felddaten als Momentaufnahmen verglichen werden, um sicherzustellen, dass die zu aktualisierenden Daten seit ihrem letzten Abruf aus der Datenbank nicht von einer anderen Benutzeranwendung geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="56173-104">Updategrams use the Optimistic Concurrency Control, which uses comparison of select field data as snapshots to ensure that the data to be updated has not been altered by another user application since it was read from the database.</span></span> <span data-ttu-id="56173-105">Updategrams enthalten diese Momentaufnahme Werte in den **\<before>** Block der Update grams.</span><span class="sxs-lookup"><span data-stu-id="56173-105">Updategrams include these snapshot values in the **\<before>** block of the updategrams.</span></span> <span data-ttu-id="56173-106">Vor dem Aktualisieren der Datenbank überprüft das Update Gram die im-Block angegebenen Werte mit den Werten, die sich **\<before>** derzeit in der Datenbank befinden, um sicherzustellen, dass das Update gültig ist.</span><span class="sxs-lookup"><span data-stu-id="56173-106">Before updating the database, the updategram checks the values that are specified in the **\<before>** block against the values currently in the database to ensure that the update is valid.</span></span>  
  
 <span data-ttu-id="56173-107">Die Steuerung durch vollständige Parallelität bietet drei Ebenen des Schutzes in einem Updategram: Niedrig (kein), mittel und hoch.</span><span class="sxs-lookup"><span data-stu-id="56173-107">The Optimistic Concurrency Control offers three levels of protection in an updategram: low (none), intermediate, and high.</span></span> <span data-ttu-id="56173-108">Sie können entscheiden, welche Ebene des Schutzes Sie benötigen, indem Sie das Updategram entsprechend festlegen.</span><span class="sxs-lookup"><span data-stu-id="56173-108">You can decide what level of protection you need by specifying the updategram accordingly.</span></span>  
  
## <a name="lowest-level-of-protection"></a><span data-ttu-id="56173-109">Niedrigste Ebene des Schutzes</span><span class="sxs-lookup"><span data-stu-id="56173-109">Lowest Level of Protection</span></span>  
 <span data-ttu-id="56173-110">Diese Ebene ist ein blindes Update, bei dem das Update ohne Verweis auf andere Updates verarbeitet wird, die seit dem letzten Lesen der Datenbank vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="56173-110">This level is a blind update, in which the update is processed without reference to other updates that have been made since the database was last read.</span></span> <span data-ttu-id="56173-111">In einem solchen Fall geben Sie nur die Primärschlüssel Spalte (n) im- **\<before>** Block an, um den Datensatz zu identifizieren, und Sie geben die aktualisierten Informationen im- **\<after>** Block an.</span><span class="sxs-lookup"><span data-stu-id="56173-111">In such a case, you specify only the primary key column(s) in the **\<before>** block to identify the record, and you specify the updated information in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="56173-112">Die neue Telefonnummer des Kontakts im folgenden Updategram ist beispielsweise korrekt, unabhängig davon, welche Telefonnummer davor verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="56173-112">For example, the new contact phone number in the following updategram is correct, regardless of what the phone number was previously.</span></span> <span data-ttu-id="56173-113">Beachten Sie, dass der- **\<before>** Block nur die Primärschlüssel Spalte (ContactID) angibt.</span><span class="sxs-lookup"><span data-stu-id="56173-113">Notice how the **\<before>** block specifies only the primary key column (ContactID).</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" />  
</updg:before>  
<updg:after>  
   <Person.Contact ContactID="1" Phone="111-111-1111" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="intermediate-level-of-protection"></a><span data-ttu-id="56173-114">Mittlere Ebene des Schutzes</span><span class="sxs-lookup"><span data-stu-id="56173-114">Intermediate Level of Protection</span></span>  
 <span data-ttu-id="56173-115">Bei dieser Ebene des Schutzes vergleicht das Updategram die aktuellen Werte der Daten, die mit den Werten in den Datenbankspalten aktualisiert werden, um sicherzustellen, dass die Werte seit dem Lesen des Datensatzes durch Ihre Transaktion durch keine andere Transaktion geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="56173-115">In this level of protection, the updategram compares the current value(s) of the data being updated with the value(s) in the database column(s) to ensure that the values have not been changed by some other transaction since the record was read by your transaction.</span></span>  
  
 <span data-ttu-id="56173-116">Sie können dieses Maß an Schutz erreichen, indem Sie die Primärschlüssel Spalte (n) und die Spalte (n), die Sie im-Block aktualisieren, angeben **\<before>** .</span><span class="sxs-lookup"><span data-stu-id="56173-116">You can get this level of protection by specifying the primary key column(s) and the column(s) that you are updating in the **\<before>** block.</span></span>  
  
 <span data-ttu-id="56173-117">Bei diesem Updategam wird beispielsweise der Wert in der Spalte Phone der Tabelle Person.Contact für den Kontakt mit der ContactID 1 geändert.</span><span class="sxs-lookup"><span data-stu-id="56173-117">For example, this updategram changes the value in the Phone column of the Person.Contact table for the contact with ContactID of 1.</span></span> <span data-ttu-id="56173-118">Der- **\<before>** Block gibt das **Telefon** Attribut an, um sicherzustellen, dass dieser Attribut Wert mit dem Wert in der entsprechenden Spalte in der Datenbank übereinstimmt, bevor der aktualisierte Wert angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="56173-118">The **\<before>** block specifies the **Phone** attribute to ensure that this attribute value matches the value in the corresponding column in the database before applying the updated value.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" Phone="398-555-0132" />  
</updg:before>  
<updg:after>  
   <Person.Contact ContactID="1" Phone="111-111-1111" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="high-level-of-protection"></a><span data-ttu-id="56173-119">Höchste Ebene des Schutzes</span><span class="sxs-lookup"><span data-stu-id="56173-119">High Level of Protection</span></span>  
 <span data-ttu-id="56173-120">Eine hohe Ebene des Schutzes stellt sicher, dass der Datensatz seit dem letzten Lesen dieses Datensatzes durch Ihre Anwendung gleich geblieben ist (d. h. seitdem Ihre Anwendung den Datensatz gelesen hat, wurde er von keiner anderen Transaktion geändert).</span><span class="sxs-lookup"><span data-stu-id="56173-120">A high level of protection ensures that the record remains the same since your application last read that record (that is, since your application has read the record, it has not been changed by any other transaction).</span></span>  
  
 <span data-ttu-id="56173-121">Es gibt zwei Methoden, diese hohe Ebene des Schutzes gegen gleichzeitige Updates zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="56173-121">There are two ways you can get this high level of protection against concurrent updates:</span></span>  
  
-   <span data-ttu-id="56173-122">Geben Sie zusätzliche Spalten in der-Tabelle im- **\<before>** Block an.</span><span class="sxs-lookup"><span data-stu-id="56173-122">Specify additional columns in the table in the **\<before>** block.</span></span>  
  
     <span data-ttu-id="56173-123">Wenn Sie zusätzliche Spalten im- **\<before>** Block angeben, vergleicht das Update Gram die Werte, die für diese Spalten angegeben wurden, mit den Werten, die vor dem Anwenden des Updates in der Datenbank gespeichert waren.</span><span class="sxs-lookup"><span data-stu-id="56173-123">If you specify additional columns in the **\<before>** block, the updategram compares the values that are specified for these columns with the values that were in the database before applying the update.</span></span> <span data-ttu-id="56173-124">Wenn eine der Datensatzspalten seit dem letzten Lesen des Datensatzes durch Ihre Transaktion geändert wurde, wird das Update vom Updategram nicht durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="56173-124">If any of the record columns has changed since your transaction read the record, the updategram does not perform the update.</span></span>  
  
     <span data-ttu-id="56173-125">Das folgende Update Gram aktualisiert z. b. den Verschiebungs Namen, gibt jedoch zusätzliche Spalten (StartTime, EndTime) im-Block an und **\<before>** fordert somit eine höhere Schutz Ebene gegen gleichzeitige Updates an.</span><span class="sxs-lookup"><span data-stu-id="56173-125">For example, the following updategram updates the shift name, but specifies additional columns (StartTime,EndTime) in the **\<before>** block, thereby requesting a higher level of protection against concurrent updates.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="1"   
                 Name="Day"   
                 StartTime="1900-01-01 07:00:00.000"   
                 EndTime="1900-01-01 15:00:00.000" />  
    </updg:before>  
    <updg:after>  
       <HumanResources.Shift Name="Morning" />  
    </updg:after>  
    </updg:sync>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="56173-126">In diesem Beispiel wird die höchste Schutz Ebene angegeben, indem alle Spaltenwerte für den Datensatz im-Block angegeben werden **\<before>** .</span><span class="sxs-lookup"><span data-stu-id="56173-126">This example specifies the highest level of protection by specifying all column values for the record in the **\<before>** block.</span></span>  
  
-   <span data-ttu-id="56173-127">Geben Sie die Zeitstempel-Spalte (falls verfügbar) im- **\<before>** Block an.</span><span class="sxs-lookup"><span data-stu-id="56173-127">Specify the timestamp column (if available) in the **\<before>** block.</span></span>  
  
     <span data-ttu-id="56173-128">Anstatt alle Daten Satz Spalten im `<before`>-Block anzugeben, können Sie einfach die Zeitstempel-Spalte (wenn die Tabelle über eine Tabelle verfügt) zusammen mit der Primärschlüssel Spalte (n) im- **\<before>** Block angeben.</span><span class="sxs-lookup"><span data-stu-id="56173-128">Instead of specifying all the record columns in the `<before`> block, you can just specify the timestamp column (if the table has one) along with the primary key column(s) in the **\<before>** block.</span></span> <span data-ttu-id="56173-129">Die Datenbank aktualisiert nach jedem Update des Datensatzes die timestamp-Spalte auf einen eindeutigen Wert.</span><span class="sxs-lookup"><span data-stu-id="56173-129">The database updates the timestamp column to a unique value after each update of the record.</span></span> <span data-ttu-id="56173-130">In diesem Fall vergleicht das Updategram den Wert des Timestamps mit dem zugehörigen Wert in der Datenbank.</span><span class="sxs-lookup"><span data-stu-id="56173-130">In this case, the updategram compares the value of the timestamp with the corresponding value in the database.</span></span> <span data-ttu-id="56173-131">Der in der Datenbank gespeicherte Timestampwert ist ein Binärwert.</span><span class="sxs-lookup"><span data-stu-id="56173-131">The timestamp value stored in the database is a binary value.</span></span> <span data-ttu-id="56173-132">Deshalb muss die timestamp-Spalte im Schema als `dt:type="bin.hex"`, `dt:type="bin.base64"` oder `sql:datatype="timestamp"` angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="56173-132">Therefore, the timestamp column must be specified in the schema as `dt:type="bin.hex"`, `dt:type="bin.base64"`, or `sql:datatype="timestamp"`.</span></span> <span data-ttu-id="56173-133">(Sie können entweder den- `xml` Datentyp oder den- [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Datentyp angeben.)</span><span class="sxs-lookup"><span data-stu-id="56173-133">(You can specify either the `xml` data type or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type.)</span></span>  
  
#### <a name="to-test-the-updategram"></a><span data-ttu-id="56173-134">So testen Sie das Updategram</span><span class="sxs-lookup"><span data-stu-id="56173-134">To test the updategram</span></span>  
  
1.  <span data-ttu-id="56173-135">Erstellen Sie diese Tabelle in der **tempdb** -Datenbank:</span><span class="sxs-lookup"><span data-stu-id="56173-135">Create this table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Customer (  
                 CustomerID  varchar(5),  
                 ContactName varchar(20),  
                 LastUpdated timestamp)  
    ```  
  
2.  <span data-ttu-id="56173-136">Fügen Sie diesen Beispieldatensatz hinzu:</span><span class="sxs-lookup"><span data-stu-id="56173-136">Add this sample record:</span></span>  
  
    ```  
    INSERT INTO Customer (CustomerID, ContactName) VALUES   
                         ('C1', 'Andrew Fuller')  
    ```  
  
3.  <span data-ttu-id="56173-137">Kopieren Sie das folgende XSD-Schema, und fügen Sie es in den Editor ein.</span><span class="sxs-lookup"><span data-stu-id="56173-137">Copy the following XSD schema and paste it into Notepad.</span></span> <span data-ttu-id="56173-138">Speichern Sie es unter dem Namen ConcurrencySampleSchema.xml:</span><span class="sxs-lookup"><span data-stu-id="56173-138">Save it as ConcurrencySampleSchema.xml:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="Customer" sql:relation="Customer" >  
       <xsd:complexType>  
            <xsd:attribute name="CustomerID"    
                           sql:field="CustomerID"   
                           type="xsd:string" />   
  
            <xsd:attribute name="ContactName"    
                           sql:field="ContactName"   
                           type="xsd:string" />  
  
            <xsd:attribute name="LastUpdated"   
                           sql:field="LastUpdated"   
                           type="xsd:hexBinary"   
                 sql:datatype="timestamp" />  
  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
4.  <span data-ttu-id="56173-139">Kopieren Sie den folgenden Updategramcode in Editor, und speichern Sie ihn unter dem Namen ConcurrencySampleTemplate.xml im selben Verzeichnis, in dem Sie das im vorherigen Schritt erstellte Schema gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="56173-139">Copy the following updategram code into Notepad and save it as ConcurrencySampleTemplate.xml in the same directory where you saved the schema created in the previous step.</span></span> <span data-ttu-id="56173-140">(Beachten Sie, dass der unten aufgeführte Timestampwert für LastUpdated sich von dem in Ihrer Customer-Tabelle unterscheidet. Kopieren Sie daher den tatsächlichen Wert für LastUpdated aus der Tabelle, und fügen Sie ihn in das Updategram ein.)</span><span class="sxs-lookup"><span data-stu-id="56173-140">(Note the timestamp value below for LastUpdated will differ in your example Customer table, so copy the actual value for LastUpdated from the table and paste it into the updategram.)</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync mapping-schema="SampleSchema.xml" >  
    <updg:before>  
       <Customer CustomerID="C1"   
                 LastUpdated = "0x00000000000007D1" />  
    </updg:before>  
    <updg:after>  
       <Customer ContactName="Robert King" />  
    </updg:after>  
    </updg:sync>  
    </ROOT>  
    ```  
  
5.  <span data-ttu-id="56173-141">Erstellen und verwenden Sie das SQLXML 4.0-Testskript (Sqlxml4test.vbs), um die Vorlage auszuführen.</span><span class="sxs-lookup"><span data-stu-id="56173-141">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="56173-142">Weitere Informationen finden Sie unter [Verwenden von ADO zum Ausführen von SQLXML 4,0-Abfragen](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="56173-142">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="56173-143">Dies ist das entsprechende XDR-Schema:</span><span class="sxs-lookup"><span data-stu-id="56173-143">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<ElementType name="Customer" sql:relation="Customer" >  
    <AttributeType name="CustomerID" />  
    <AttributeType name="ContactName" />  
    <AttributeType name="LastUpdated"  dt:type="bin.hex"   
                                       sql:datatype="timestamp" />  
    <attribute type="CustomerID" />  
    <attribute type="ContactName" />  
    <attribute type="LastUpdated" />  
</ElementType>  
</Schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="56173-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="56173-144">See Also</span></span>  
 [<span data-ttu-id="56173-145">Sicherheitsüberlegungen zu Update grams &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="56173-145">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
