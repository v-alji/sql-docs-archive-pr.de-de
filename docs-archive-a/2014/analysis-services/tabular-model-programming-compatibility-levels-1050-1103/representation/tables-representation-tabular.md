---
title: Tabellen Darstellung (tabellarisch) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: analysis-services
ms.topic: reference
ms.assetid: a636fc13-4054-4cea-bce1-192ec4796063
author: minewiskan
ms.author: owend
ms.openlocfilehash: 46ede058446778ad7e0d1a980bdd93bf5d72b966
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87617297"
---
# <a name="tables-representation-tabular"></a><span data-ttu-id="2c4fd-102">Tabellendarstellung (tabellarisch)</span><span class="sxs-lookup"><span data-stu-id="2c4fd-102">Tables Representation (Tabular)</span></span>
  <span data-ttu-id="2c4fd-103">In tabellarischen Modellen ist eine Tabelle die Basisdarstellung der Daten.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-103">In tabular models, a table is the base representation of the data.</span></span>  
  
## <a name="tables-representation"></a><span data-ttu-id="2c4fd-104">Tabellendarstellung</span><span class="sxs-lookup"><span data-stu-id="2c4fd-104">Tables Representation</span></span>  
  
### <a name="tables-in-amo"></a><span data-ttu-id="2c4fd-105">Tabellen in AMO</span><span class="sxs-lookup"><span data-stu-id="2c4fd-105">Tables in AMO</span></span>  
 <span data-ttu-id="2c4fd-106">Wenn AMO zum Verwalten einer Tabelle verwendet wird, besteht keine 1:1-Objektentsprechung.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-106">When using AMO to manage a table, there is no one-to-one object match.</span></span> <span data-ttu-id="2c4fd-107">In AMO wird eine Tabelle durch <xref:Microsoft.AnalysisServices.Dimension> und <xref:Microsoft.AnalysisServices.MeasureGroup> dargestellt.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-107">In AMO, a table is represented by a <xref:Microsoft.AnalysisServices.Dimension> and <xref:Microsoft.AnalysisServices.MeasureGroup>.</span></span> <span data-ttu-id="2c4fd-108">Damit eine Measuregruppe vorhanden sein kann, muss ein <xref:Microsoft.AnalysisServices.Cube> als Host der Measuregruppe definiert werden.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-108">For a measure group to exist, a <xref:Microsoft.AnalysisServices.Cube> must be defined to host the measure group.</span></span> <span data-ttu-id="2c4fd-109">Damit eine Dimension, eine Measuregruppe und ein Cube vorhanden sein können, muss ein Datenquellensicht-Objekt definiert werden, das die Bindungsdefinitionen zur Datenquelle enthält.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-109">For a dimension, measure group, and cube to exist, a Data Source View object must be defined to hold the binding definitions to the data source.</span></span>  
  
 <span data-ttu-id="2c4fd-110">Aus einer Verfahrensperspektive muss eine Datenquellensicht vor der Definition jedes anderen Objekts erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-110">From a procedural perspective, a Data Source View needs to be created before any other object is defined.</span></span> <span data-ttu-id="2c4fd-111">Das Datenquellensicht-Objekt enthält die Zuordnung für alle relevanten Objekte in der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-111">The data source view object contains the mapping for all relevant objects in the data source.</span></span> <span data-ttu-id="2c4fd-112">Die Zuordnung des relationalen Modells wird als .NET DataSet-Objekt in die Datenquellensicht eingebettet und in der Schema-Eigenschaft der Datenquellensicht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-112">The mapping of the relational model is embedded in the data source view as a .Net DataSet object and stored in the Schema property of the DSV.</span></span>  
  
 <span data-ttu-id="2c4fd-113">Bei folgendem Codeausschnitt wird davon ausgegangen, dass Sie über Folgendes verfügen: eine SQL-Clientverbindungszeichenfolge, ein Wörterbuch mit SELECT-Anweisungen, die allen Tabellen im relationalen Modell zugeordnet werden, das Sie im tabellarischen Modell darstellen möchten, sowie eine newDataSourceViewName-Variable mit dem Namen der Datenquellensicht (entspricht normalerweise dem Namen der relationalen Datenbank).</span><span class="sxs-lookup"><span data-stu-id="2c4fd-113">The following code snippet assumes you have a SQL client connection string, a dictionary of Select statements that map to all tables in the relational model you intend to represent in your tabular model, and a variable newDataSourceViewName with the name of the data source view (usually the name of your relational database).</span></span>  
  
```  
  
DataSet newDataSourceViewDataSet = new DataSet(newDataSourceViewName);  
  
Foreach( String tableName in listOfSqlStatements.Keys)  
{  
    String sqlStmt = listOfSqlStatements[tableName];  
  
    DataTable newTable = new DataTable(tableName);  
  
    using (SqlConnection SqlCnx = new SqlConnection(SqlCnxStr))  
    {  
        SqlDataAdapter dataAdapter = new SqlDataAdapter(sqlStmt, SqlCnx);  
        dataAdapter.FillSchema(newTable, SchemaType.Source);  
    }  
    newDataSourceViewDataSet.Tables.Add(newTable);  
}  
  
AMO.DataSourceView newDatasourceView = newDatabase.DataSourceViews.AddNew(newDataSourceViewName, newDataSourceViewName);  
newDatasourceView.DataSourceID = newDatasource.ID; //This is the ID of the DataSource object   
newDatasourceView.Schema = newDataSourceViewDataSet; //Here you are storing all the relational schema in the DSV  
newDatasourceView.Update();  
  
```  
  
 <span data-ttu-id="2c4fd-114">Sobald die Datenquellensicht erstellt und aktualisiert wurde, muss das Cubeobjekt zwar erstellt, aber erst auf dem Server aktualisiert werden, nachdem die erste Tabelle erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-114">Once the Data Source View has been created and updated, the cube object needs to be created, but not updated in the server until the first table is created.</span></span> <span data-ttu-id="2c4fd-115">Ein Cubeobjekt kann nicht leer erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-115">A cube object cannot be created empty.</span></span> <span data-ttu-id="2c4fd-116">Der folgende Codeausschnitt veranschaulicht, wie ein Cube erstellt wird. Beim Ausschnitt wird davon ausgegangen, dass Sie über die nicht leere Zeichenfolge newCubeName mit dem Namen des Cubes verfügen und dass dieser bereits auf Duplikate überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-116">The following code snippet shows how to create a cube; the snippet assumes you have a non-empty string newCubeName with the name of the cube already validated for duplicates too.</span></span>  
  
```  
  
modelCube = newDatabase.Cubes.Add(newCubeName, newCubeName);  
modelCube.Source = new AMO.DataSourceViewBinding(newDatasourceView.ID);  
modelCube.StorageMode = AMO.StorageMode.InMemory;  
modelCube.Language = newDatabase.Language;  
modelCube.Collation = newDatabase.Collation;  
//Create initial MdxScript  
AMO.MdxScript mdxScript = modelCube.MdxScripts.Add("MdxScript", "MdxScript");  
StringBuilder initialCommand = new StringBuilder();  
initialCommand.AppendLine("CALCULATE;");  
initialCommand.AppendLine("CREATE MEMBER CURRENTCUBE.Measures.[__No measures defined] AS 1;");  
initialCommand.AppendLine("ALTER CUBE CURRENTCUBE UPDATE DIMENSION Measures, Default_Member = [__No measures defined];");  
mdxScript.Commands.Add(new AMO.Command(initialCommand.ToString()));  
  
```  
  
 <span data-ttu-id="2c4fd-117">Nachdem der Cube lokal definiert wurde, können Tabellen erstellt und aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-117">Once the cube is defined locally, tables can be created and updated.</span></span> <span data-ttu-id="2c4fd-118">Im folgenden Verfahren werden die notwendigen Schritte zum Erstellen einer Tabelle veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="2c4fd-118">The following procedure outlines the necessary steps to create a table:</span></span>  
  
1.  <span data-ttu-id="2c4fd-119">Erstellen der Dimension, die die Tabelle darstellt (der Server darf noch nicht aktualisiert werden)</span><span class="sxs-lookup"><span data-stu-id="2c4fd-119">Create the dimension that represents the table and don't update the server yet.</span></span>  
  
2.  <span data-ttu-id="2c4fd-120">Erstellen des RowNumber-Attributs und Definieren des Attributs als Schlüsselattribut der Dimension</span><span class="sxs-lookup"><span data-stu-id="2c4fd-120">Create the RowNumber attribute and define it as the key attribute of the dimension.</span></span>  
  
3.  <span data-ttu-id="2c4fd-121">Erstellen der Dimensionsattribute und Kennzeichnen der Attribute mit einer 1:n-Beziehung zu RowNumber</span><span class="sxs-lookup"><span data-stu-id="2c4fd-121">Create dimension attributes and mark them with a one-to-many relationship to RowNumber.</span></span>  
  
4.  <span data-ttu-id="2c4fd-122">Hinzufügen einer Dimension zu den Cubedimensionen</span><span class="sxs-lookup"><span data-stu-id="2c4fd-122">Add dimension to cube dimensions.</span></span>  
  
5.  <span data-ttu-id="2c4fd-123">Erstellen der Measuregruppe, die auch die Tabelle darstellt</span><span class="sxs-lookup"><span data-stu-id="2c4fd-123">Create the measure group that also represents the table.</span></span>  
  
6.  <span data-ttu-id="2c4fd-124">Hinzufügen einer Dimension zur Measuregruppe</span><span class="sxs-lookup"><span data-stu-id="2c4fd-124">Add dimension to measure group.</span></span>  
  
7.  <span data-ttu-id="2c4fd-125">Erstellen eines AMO-Standardmeasureobjekts für die Measuregruppe.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-125">Create AMO default measure object to the measure group.</span></span> <span data-ttu-id="2c4fd-126">Beachten Sie, dass das AMO-Measureobjekt nur ein einziges Mal verwendet wird. Berechnete Measures in tabellarischen Modellen werden im AMO-Objekt MdxScripts["MdxScript"] definiert.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-126">Note, this is the only time an AMO measure object is used; calculated measures, in tabular models, are defined in the AMO MdxScripts["MdxScript"] object.</span></span>  
  
8.  <span data-ttu-id="2c4fd-127">Erstellen der Standardpartition</span><span class="sxs-lookup"><span data-stu-id="2c4fd-127">Create default partition.</span></span>  
  
9. <span data-ttu-id="2c4fd-128">Aktualisieren der Datenbank</span><span class="sxs-lookup"><span data-stu-id="2c4fd-128">Update database.</span></span>  
  
 <span data-ttu-id="2c4fd-129">Der folgende Codeausschnitt veranschaulicht das Erstellen einer Tabelle:</span><span class="sxs-lookup"><span data-stu-id="2c4fd-129">The following code snippet shows how to create a table:</span></span>  
  
```  
  
private Boolean CreateTable(  
                       AMO.Database db      //the AMO database object where dimension are created  
                     , AMO.Cube cb          //the AMO cube where measure group is created  
                     , DataTable dataTable  //the schema of the table to be created  
                     )  
{  
    String tableID = dataTable.TableName;  
  
    if (db.Dimensions.Contains(tableID))  
    {  
        if (cb.MeasureGroups.Contains(tableID))  
        {  
            cb.MeasureGroups[tableID].Measures.Clear();  
            cb.MeasureGroups[tableID].Partitions.Clear();  
            cb.MeasureGroups.Remove(tableID, true);  
        }  
        if (cb.Dimensions.Contains(tableID))  
        {  
            cb.Dimensions.Remove(tableID, true);  
        }  
        db.Dimensions.Remove(tableID);  
    }  
  
    #region Create Dimension  
    //Define Dimension general properties  
    AMO.Dimension currentDimension = db.Dimensions.AddNew(tableID, tableID);  
    currentDimension.Source = new AMO.DataSourceViewBinding(newDatasourceView.ID);  
    currentDimension.StorageMode = AMO.DimensionStorageMode.InMemory;  
    currentDimension.UnknownMember = AMO.UnknownMemberBehavior.AutomaticNull;  
    currentDimension.UnknownMemberName = "Unknown";  
    currentDimension.ErrorConfiguration = new AMO.ErrorConfiguration();  
    currentDimension.ErrorConfiguration.KeyNotFound = AMO.ErrorOption.IgnoreError;  
    currentDimension.ErrorConfiguration.KeyDuplicate = AMO.ErrorOption.ReportAndStop;  
    currentDimension.ErrorConfiguration.NullKeyNotAllowed = AMO.ErrorOption.ReportAndStop;  
    currentDimension.Language = db.Language;  
    currentDimension.Collation = db.Collation;  
    currentDimension.ProactiveCaching = new AMO.ProactiveCaching();  
    TimeSpan defaultProactiveChachingTimeSpan = new TimeSpan(0, 0, -1);  
    currentDimension.ProactiveCaching.SilenceInterval = defaultProactiveChachingTimeSpan;  
    currentDimension.ProactiveCaching.Latency = defaultProactiveChachingTimeSpan;  
    currentDimension.ProactiveCaching.SilenceOverrideInterval = defaultProactiveChachingTimeSpan;  
    currentDimension.ProactiveCaching.ForceRebuildInterval = defaultProactiveChachingTimeSpan;  
    currentDimension.ProactiveCaching.Source = new AMO.ProactiveCachingInheritedBinding();  
  
    //Manualy add a "RowNumber" attribute as the key attribute of the dimension, until a primary key is defined  
    //"RowNumber" a required column for a tabular model and has to be of type AMO.AttributeType.RowNumber and binding AMO.RowNumberBinding.  
    //The name of the "RowNumber" attribute can be any name, as long as type and binding are correctly set  
    //By default, the MS client tools set the column name and column ID of the RowNumber attribute to "RowNumber"  
    //In this sample, to avoid problems, on any customer table that contains a column named 'RowNumber'   
    //the Id value of the column (in the dimension object) will be renamed to 'RowNumber_in_<TableName>' and the Name of the column will remain "RowNumber"  
  
    AMO.DimensionAttribute currentAttribute = currentDimension.Attributes.Add("RowNumber", "RowNumber");  
    currentAttribute.Type = AMO.AttributeType.RowNumber;  
    currentAttribute.KeyUniquenessGuarantee = true;  
    currentAttribute.Usage = AMO.AttributeUsage.Key;  
    currentAttribute.KeyColumns.Add(new AMO.DataItem());  
    currentAttribute.KeyColumns[0].DataType = System.Data.OleDb.OleDbType.Integer;  
    currentAttribute.KeyColumns[0].DataSize = 4;  
    currentAttribute.KeyColumns[0].NullProcessing = AMO.NullProcessing.Error;  
    currentAttribute.KeyColumns[0].Source = new AMO.RowNumberBinding();  
    currentAttribute.NameColumn = new AMO.DataItem();  
    currentAttribute.NameColumn.DataType = System.Data.OleDb.OleDbType.WChar;  
    currentAttribute.NameColumn.DataSize = 4;  
    currentAttribute.NameColumn.NullProcessing = AMO.NullProcessing.ZeroOrBlank;  
    currentAttribute.NameColumn.Source = new AMO.RowNumberBinding();  
    currentAttribute.OrderBy = AMO.OrderBy.Key;  
    currentAttribute.AttributeHierarchyVisible = false;  
    //Deferring AttributeRelationships until after adding each other attribute  
    //Add each column in the table as an attribute in the dimension  
    foreach (DataColumn dataColumn in dataTable.Columns)  
    {  
        string attributeID, attributeName;  
        if (dataColumn.ColumnName != "RowNumber")  
        {  
            attributeID = dataColumn.ColumnName;  
        }  
        else  
        {  
            attributeID = string.Format("RowNumber_in_{0}", dataTable.TableName);  
        }  
        attributeName = dataColumn.ColumnName;  
        currentAttribute = currentDimension.Attributes.Add(attributeName, attributeID);  
        currentAttribute.Usage = AMO.AttributeUsage.Regular;  
        currentAttribute.KeyUniquenessGuarantee = false;  
        currentAttribute.KeyColumns.Add(new AMO.DataItem(dataTable.TableName, dataColumn.ColumnName, AMO.OleDbTypeConverter.GetRestrictedOleDbType(dataColumn.DataType)));  
        currentAttribute.KeyColumns[0].Source = new AMO.ColumnBinding(dataTable.TableName, dataColumn.ColumnName);  
        currentAttribute.KeyColumns[0].NullProcessing = AMO.NullProcessing.Preserve;  
        currentAttribute.NameColumn = new AMO.DataItem(dataTable.TableName, dataColumn.ColumnName, System.Data.OleDb.OleDbType.WChar);  
        currentAttribute.NameColumn.Source = new AMO.ColumnBinding(dataTable.TableName, dataColumn.ColumnName);  
        currentAttribute.NameColumn.NullProcessing = AMO.NullProcessing.ZeroOrBlank;  
        currentAttribute.OrderBy = AMO.OrderBy.Key;  
        AMO.AttributeRelationship currentAttributeRelationship = currentDimension.Attributes["RowNumber"].AttributeRelationships.Add(currentAttribute.ID);  
        currentAttributeRelationship.Cardinality = AMO.Cardinality.Many;  
        currentAttributeRelationship.OverrideBehavior = AMO.OverrideBehavior.None;  
    }  
    #endregion  
  
    #region Add Dimension to Model cube  
    cb.Dimensions.Add(tableID, tableID, tableID);  
    #endregion  
  
    #region Add MeasureGroup to Model cube  
    AMO.MeasureGroup currentMeasureGroup = cb.MeasureGroups.Add(tableID, tableID);  
    currentMeasureGroup.StorageMode = AMO.StorageMode.InMemory;  
    currentMeasureGroup.ProcessingMode = AMO.ProcessingMode.Regular;  
  
    //Adding Dimension  
    AMO.DegenerateMeasureGroupDimension currentMGDim = new AMO.DegenerateMeasureGroupDimension(tableID);  
    currentMeasureGroup.Dimensions.Add(currentMGDim);  
    currentMGDim.ShareDimensionStorage = AMO.StorageSharingMode.Shared;  
    currentMGDim.CubeDimensionID = tableID;  
    foreach (AMO.CubeAttribute ca in cb.Dimensions[tableID].Attributes)  
    {  
        AMO.MeasureGroupAttribute mga = new AMO.MeasureGroupAttribute(ca.AttributeID);  
        if (mga.AttributeID == "RowNumber")  
        {  
            mga.Type = AMO.MeasureGroupAttributeType.Granularity;  
            AMO.DataItem rowNumberKeyColumn = new AMO.DataItem(new AMO.ColumnBinding(tableID, "RowNumber"));  
            rowNumberKeyColumn.DataType = System.Data.OleDb.OleDbType.Integer;  
            mga.KeyColumns.Add(rowNumberKeyColumn);  
        }  
        else  
        {  
            foreach (AMO.DataItem di in ca.Attribute.KeyColumns)  
            {  
                AMO.DataItem keyColumn = new AMO.DataItem(new AMO.ColumnBinding(tableID, ((AMO.ColumnBinding)di.Source).ColumnID));  
                keyColumn.DataType = di.DataType;  
                keyColumn.NullProcessing = AMO.NullProcessing.Preserve;  
                keyColumn.InvalidXmlCharacters = AMO.InvalidXmlCharacters.Remove;  
                mga.KeyColumns.Add(keyColumn);  
            }  
        }  
        currentMGDim.Attributes.Add(mga);  
    }  
  
    //Adding default Measure  
    String defaultMeasureID = string.Concat("_Count ", tableID);  
    AMO.Measure currentMeasure = currentMeasureGroup.Measures.Add(defaultMeasureID, defaultMeasureID);  
    currentMeasure.AggregateFunction = AMO.AggregationFunction.Count;  
    currentMeasure.DataType = AMO.MeasureDataType.BigInt;  
    AMO.DataItem currentMeasureSource = new AMO.DataItem(new AMO.RowBinding(tableID));  
    currentMeasureSource.DataType = System.Data.OleDb.OleDbType.BigInt;  
    currentMeasure.Source = currentMeasureSource;  
  
    //Partitions  
    AMO.Partition currentPartition = new AMO.Partition(tableID, tableID);  
    currentPartition.StorageMode = AMO.StorageMode.InMemory;  
    currentPartition.ProcessingMode = AMO.ProcessingMode.Regular;  
    currentPartition.Source = new AMO.QueryBinding(newDatasource.ID, (String)dataTable.ExtendedProperties["sqlStmt"]);  
    currentMeasureGroup.Partitions.Add(currentPartition);  
  
    #endregion  
  
    #region Update new objects in database  
    db.Update(AMO.UpdateOptions.ExpandFull, AMO.UpdateMode.UpdateOrCreate);  
    #endregion  
  
    return true;  
}  
  
```  
  
> [!CAUTION]  
>  <span data-ttu-id="2c4fd-130">Der oben erwähnte Codeausschnitt umfasst keine Fehlerüberprüfungs- bzw. Cleanupverfahren bei Fehlern.</span><span class="sxs-lookup"><span data-stu-id="2c4fd-130">The above code snippet has no error checking or clean up procedures in case of failure.</span></span>  
  
  
