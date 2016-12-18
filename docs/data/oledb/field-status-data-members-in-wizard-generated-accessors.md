---
title: "Donn&#233;es membres de l&#39;&#233;tat des champs dans les accesseurs g&#233;n&#233;r&#233;s par l&#39;Assistant | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "état du champ dans les modèles OLE DB"
  - "OLE DB (modèles du consommateur), état du champ"
ms.assetid: 66e4e223-c60c-471e-860d-d23abcdfe371
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Donn&#233;es membres de l&#39;&#233;tat des champs dans les accesseurs g&#233;n&#233;r&#233;s par l&#39;Assistant
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lorsque vous utilisez l'Assistant Consommateur OLE DB ATL pour créer un consommateur, l'Assistant génère des données membres dans la classe d'enregistrement utilisateur pour chaque champ que vous spécifiez dans le mappage de colonnes.  Chaque donnée membre correspond au type `DWORD` et contient une valeur d'état correspondant à son champ respectif.  
  
 Par exemple, pour une donnée membre *m\_OwnerID*, l'Assistant génère une donnée membre supplémentaire pour l'état du champ \(*dwOwnerIDStatus*\), et une autre pour la taille du champ \(*dwOwnerIDLength*\).  Il génère également un mappage de colonnes à l'aide des entrées `COLUMN_ENTRY_LENGTH_STATUS`.  
  
 Ce cas est illustré dans le code suivant :  
  
```  
[db_source("insert connection string")]  
[db_command(" \  
   SELECT \  
      Au_ID, \  
      Author, \  
      `Year Born`, \  
      FROM Authors")]  
  
class CAuthors  
{  
public:  
  
   // The following wizard-generated data members contain status   
   // values for the corresponding fields in the column map. You   
   // can use these values to hold NULL values that the database   
   // returns or to hold error information when the compiler returns   
   // errors. See "Field Status Data Members in Wizard-Generated   
   // Accessors" in the Visual C++ documentation for more information   
   // on using these fields.  
   DWORD m_dwAuIDStatus;  
   DWORD m_dwAuthorStatus;  
   DWORD m_dwYearBornStatus;  
  
   // The following wizard-generated data members contain length  
   // values for the corresponding fields in the column map.  
   DWORD m_dwAuIDLength;  
   DWORD m_dwAuthorLength;  
   DWORD m_dwYearBornLength;  
  
BEGIN_COLUMN_MAP(CAuthorsAccessor)  
   COLUMN_ENTRY_LENGTH_STATUS(1, m_AuID, dwAuIDLength, dwAuIDStatus)  
   COLUMN_ENTRY_LENGTH_STATUS(2, m_Author, dwAuthorLength, dwAuthorStatus)  
   COLUMN_ENTRY_LENGTH_STATUS(3, m_YearBorn, dwYearBornLength, dwYearBornStatus)  
END_COLUMN_MAP()  
  
   [ db_column(1, status=m_dwAuIDStatus, length=m_dwAuIDLength) ] LONG m_AuID;  
   [ db_column(2, status=m_dwAuthorStatus, length=m_dwAuthorLength) ] TCHAR m_Author[51];  
   [ db_column(3, status=m_dwYearBornStatus, length=m_dwYearBornLength) ] SHORT m_YearBorn;  
  
   void GetRowsetProperties(CDBPropSet* pPropSet)  
   {  
      pPropSet->AddProperty(DBPROP_IRowsetChange, true);  
      pPropSet->AddProperty(DBPROP_UPDATABILITY, DBPROPVAL_UP_CHANGE | DBPROPVAL_UP_INSERT | DBPROPVAL_UP_DELETE);  
   }  
};  
```  
  
> [!NOTE]
>  Si vous modifiez la classe d'enregistrement utilisateur ou écrivez votre propre consommateur, les variables de données doivent précéder les variables d'état et de longueur.  
  
 Vous pouvez également utiliser les valeurs d'état à des fins de débogage.  Si le code généré par l'Assistant Consommateur OLE DB ATL produit des erreurs de compilation telles que **DB\_S\_ERRORSOCCURRED** ou **DB\_E\_ERRORSOCCURRED**, vous devez d'abord examiner les valeurs actuelles des données membres d'état des champs.  Celles qui contiennent des valeurs différentes de zéro correspondent aux colonnes fautives.  
  
 Vous pouvez également utiliser les valeurs d'état pour attribuer une valeur NULL à un champ particulier.  Cette méthode est utile quand vous voulez distinguer une valeur de champ NULL d'une valeur zéro.  Il vous appartient de déterminer si NULL est une valeur valide ou une valeur spéciale, et comment votre application doit la gérer.  OLE DB définit **DBSTATUS\_S\_ISNULL** comme étant le moyen correct pour spécifier une valeur NULL générique.  Si le consommateur lit les données et que la valeur est nulle, le champ d'état a la valeur **DBSTATUS\_S\_ISNULL**.  Si le consommateur souhaite définir une valeur NULL, le consommateur définit la valeur de l'état comme étant **DBSTATUS\_S\_ISNULL** avant d'appeler le fournisseur.  
  
 Ensuite, ouvrez Oledb.h et recherchez **DBSTATUSENUM**.  Vous pouvez comparer ensuite la valeur numérique de l'état différent de zéro aux valeurs d'énumération **DBSTATUSENUM**.  Si le nom d'énumération ne vous permet pas de déterminer le problème, consultez la rubrique « État » de la section « Liaison de valeurs de données » du [Guide de programmation OLE DB](http://go.microsoft.com/fwlink/?LinkId=121548).  Cette rubrique contient des tables de valeurs d'état utilisées lors de l'obtention ou de la définition des données.  Pour plus d'informations sur les valeurs de longueur, consultez la rubrique « Longueur » dans cette même section \(page éventuellement en anglais\).  
  
## Récupération de la longueur ou de l'état d'une colonne  
 Vous pouvez récupérer la longueur d'une colonne de longueur variable ou l'état d'une colonne \(pour rechercher **DBSTATUS\_S\_ISNULL**, par exemple\) :  
  
-   Pour obtenir la longueur, utilisez la macro `COLUMN_ENTRY_LENGTH`.  
  
-   Pour obtenir l'état, utilisez la macro `COLUMN_ENTRY_STATUS`.  
  
-   Pour obtenir les deux, utilisez `COLUMN_ENTRY_LENGTH_STATUS`, comme indiqué ci\-dessous.  
  
```  
class CProducts  
{  
public:  
   char      szName[40];  
   long      nNameLength;  
   DBSTATUS   nNameStatus;  
  
BEGIN_COLUMN_MAP(CProducts)  
// Bind the column to CProducts.m_ProductName.  
// nOrdinal is zero-based, so the column number of m_ProductName is 1.  
   COLUMN_ENTRY_LENGTH_STATUS(1, szName, nNameLength, nNameStatus)  
END_COLUMN_MAP()  
};  
  
CTable<CAccessor<CProducts > > product;  
  
product.Open(session, "Product");  
while (product.MoveNext() == S_OK)  
{  
   // Check the product name isn't NULL before tracing it  
   if (product.nNameStatus == DBSTATUS_S_OK)  
      ATLTRACE("%s is %d characters\n", szName, nNameLength);  
}  
```  
  
 Quand vous utilisez `CDynamicAccessor`, la longueur et l'état sont liés automatiquement.  Pour récupérer les valeurs de longueur et d'état, utilisez les fonctions membres `GetLength` et **GetStatus**.  
  
## Voir aussi  
 [Utilisation des modèles du consommateur OLE DB](../../data/oledb/working-with-ole-db-consumer-templates.md)