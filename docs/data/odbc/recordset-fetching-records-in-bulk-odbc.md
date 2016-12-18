---
title: "Recordset&#160;: extraction globale d&#39;enregistrements (ODBC) | Microsoft Docs"
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
  - "échange de champs d'enregistrements en bloc"
  - "fonctions RFX en bloc"
  - "extraire les lignes en bloc"
  - "extraire les lignes en bloc, implémenter"
  - "DoBulkFieldExchange (méthode)"
  - "extraire les enregistrements ODBC en bloc"
  - "ODBC (recordsets), extraire les lignes en bloc"
  - "recordsets, extraire les lignes en bloc"
  - "RFX (ODBC), en bloc"
  - "RFX (ODBC), extraire les lignes en bloc"
  - "jeux de lignes, extraire les lignes en bloc"
ms.assetid: 20d10fe9-c58a-414a-b675-cdf9aa283e4f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset&#160;: extraction globale d&#39;enregistrements (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 La classe `CRecordset` fournit la prise en charge de l'extraction de lignes en bloc, ce qui signifie que plusieurs enregistrements peuvent être récupérés à la fois lors d'une seule extraction, plutôt que de récupérer un seul enregistrement à la fois de la source de données.  Vous ne pouvez implémenter l'extraction de lignes en bloc que dans une classe `CRecordset` dérivée.  La procédure de transfert des données entre la source de données et l'objet recordset s'appelle RFX en bloc \(Bulk RFX\).  Si vous n'utilisez pas l'extraction de lignes en bloc dans une classe dérivée de `CRecordset`, les données sont transférées via le mécanisme RFX.  Pour plus d'informations, consultez [Record Field Exchange \(RFX\)](../../data/odbc/record-field-exchange-rfx.md).  
  
 Cette rubrique explique :  
  
-   [comment CRecordset prend en charge l'extraction de lignes en bloc](#_core_how_crecordset_supports_bulk_row_fetching) ;  
  
-   [certaines instructions relatives à l'utilisation de l'extraction de lignes en bloc](#_core_special_considerations) ;  
  
-   [l'implémentation de RFX en bloc](#_core_how_to_implement_bulk_record_field_exchange).  
  
##  <a name="_core_how_crecordset_supports_bulk_row_fetching"></a> Prise en charge par CRecordset de l'extraction de lignes en bloc  
 Avant d'ouvrir l'objet recordset, vous pouvez définir la taille d'un jeu de lignes à l'aide de la fonction membre `SetRowsetSize`.  La taille du jeu de lignes définit le nombre d'enregistrements qui doivent être récupérés lors d'une seule extraction.  Lorsque l'extraction de lignes en bloc est implémentée, la taille de l'ensemble de lignes par défaut est 25.  Si l'extraction de lignes en bloc n'est pas implémentée, la taille de l'ensemble de lignes reste fixe à 1.  
  
 Une fois que vous avez initialisé la taille du jeu de lignes, appelez la fonction membre [Open](../Topic/CRecordset::Open.md).  Maintenant vous devez spécifier l'option `CRecordset::useMultiRowFetch` du paramètre **dwOptions** afin d'implémenter l'extraction de lignes en bloc.  Vous pouvez en outre définir l'option **CRecordset::userAllocMultiRowBuffers**.  Le mécanisme RFX en bloc utilise des tableaux pour stocker les lignes de données récupérées lors d'une extraction.  Ces tampons de stockage peuvent être alloués automatiquement par l'infrastructure ou vous pouvez les allouer manuellement.  Si vous définissez l'option **CRecordset::userAllocMultiRowBuffers, cela signifie que vous procéderez vous\-même à l'allocation**.  
  
 Le tableau suivant répertorie les fonctions membres fournies par `CRecordset` pour prendre en charge l'extraction de lignes en bloc.  
  
|Fonctions membres|Description|  
|-----------------------|-----------------|  
|[CheckRowsetError](../Topic/CRecordset::CheckRowsetError.md)|Fonction virtuelle gérant toute erreur se produisant lors de l'extraction.|  
|[DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md)|Implémente le mécanisme RFX en bloc.  Appelée automatiquement pour transférer plusieurs lignes de données entre la source de données et l'objet recordset.|  
|[GetRowsetSize](../Topic/CRecordset::GetRowsetSize.md)|Récupère la valeur en cours de la taille du jeu de lignes.|  
|[GetRowsFetched](../Topic/CRecordset::GetRowsFetched.md)|Indique le nombre de lignes réellement récupérées après une extraction donnée.  Dans la plupart des cas, cette valeur est égale à la taille du jeu de lignes, sauf si un jeu de lignes incomplet a été extrait.|  
|[GetRowStatus](../Topic/CRecordset::GetRowStatus.md)|Retourne l'état d'une extraction pour une ligne donnée du jeu de lignes.|  
|[RefreshRowset](../Topic/CRecordset::RefreshRowset.md)|Actualise les données et l'état d'une ligne particulière du jeu de lignes.|  
|[SetRowsetCursorPosition](../Topic/CRecordset::SetRowsetCursorPosition.md)|Déplace le curseur vers une ligne donnée du jeu de lignes.|  
|[SetRowsetSize](../Topic/CRecordset::SetRowsetSize.md)|Fonction virtuelle modifiant la valeur de la taille du jeu de lignes à une valeur définie.|  
  
##  <a name="_core_special_considerations"></a> Considérations particulières  
 Même si l'extraction de lignes en bloc représente un gain de performances, certaines caractéristiques fonctionnent différemment.  Avant de vous décider d'implémenter l'extraction de lignes en bloc, prenez en compte les points suivants :  
  
-   L'infrastructure appelle automatiquement la fonction membre `DoBulkFieldExchange` pour transférer les données depuis la source de données vers l'objet recordset.  Cependant, les données ne sont pas retransférées du recordset vers la source de données.  L'appel des fonctions membres `AddNew`, **Edit**, **Delete**, ou **Update** se traduit par l'échec de l'assertion.  Bien que la classe `CRecordset` ne fournisse aucun mécanisme permettant la mise à jour en bloc des lignes de données, vous pouvez écrire vos propres fonctions à l'aide de la fonction API ODBC **SQLSetPos**.  Pour plus d'informations sur **SQLSetPos**, consultez le guide ODBC SDK *Programmer's Reference* sur le CD\-ROM MSDN Library.  
  
-   Les fonctions membres `IsDeleted`, `IsFieldDirty`, `IsFieldNull`, `IsFieldNullable`, `SetFieldDirty` et `SetFieldNull` ne peuvent pas être utilisées sur les recordsets implémentant l'extraction de lignes en bloc.  Cependant, vous pouvez appeler `GetRowStatus` au lieu de `IsDeleted` et `GetODBCFieldInfo` au lieu de `IsFieldNullable`.  
  
-   Les opérations **Move** repositionnent le recordset par jeu de lignes.  Par exemple, supposons que vous ouvrez un recordset de 100 enregistrements dont la taille initiale de l'ensemble de lignes est de 10.  **Open** extrait les lignes 1 à 10, avec l'enregistrement actif positionné sur la ligne 1.  Un appel à `MoveNext` extrait l'ensemble de lignes suivant, pas la ligne suivante.  Cet ensemble de lignes se compose des lignes 11 à 20, avec l'enregistrement actif positionné sur la ligne 11.  Notez que `MoveNext` et **Move\( 1 \)** ne sont pas équivalents lorsque l'extraction de lignes en bloc est implémentée.  **Move\( 1 \)** extrait le jeu de lignes commençant à la ligne qui suit celle de l'enregistrement courant.  Dans cet exemple, appeler **Move\( 1 \)** après avoir appelé les extractions **Open** extrait l'ensemble de lignes contenant les lignes 2 à 11, avec l'enregistrement actif positionné sur la ligne 2.  Pour plus d'informations, consultez la fonction membre [Move](../Topic/CRecordset::Move.md).  
  
-   Contrairement au mécanisme RFX, les Assistants ne prennent pas en charge le mécanisme RFX en bloc.  Cela signifie que vous devez déclarer manuellement les membres de données de type champ ainsi que substituer manuellement `DoBulkFieldExchange` en écrivant les appels des fonctions RFX en bloc.  Pour plus d'informations, consultez [Record Field Exchange Functions](../../mfc/reference/record-field-exchange-functions.md) dans *Class Library Reference*.  
  
##  <a name="_core_how_to_implement_bulk_record_field_exchange"></a> Implémentation du mécanisme RFX en bloc  
 Le mécanisme RFX en bloc transfère un jeu de lignes de données entre la source de données et l'objet recordset.  Les fonctions RFX en bloc utilisent des tableaux pour stocker ces données et la longueur de chaque élément de donnée du jeu de lignes.  Dans la définition de la classe, vous devez définir les membres de données de type champ comme pointeurs pour accéder aux tableaux de données.  En outre, vous devez définir un ensemble de pointeurs pour accéder aux tableaux des longueurs.  Les membres de données de type paramètre ne doivent pas être déclarés comme pointeurs ; la déclaration de ces membres, lorsque vous utilisez le mécanisme RFX en bloc, est identique à leur déclaration dans le cas de RFX.  Le code suivant est fourni à titre d'exemple :  
  
```  
class MultiRowSet : public CRecordset  
{  
public:  
   // Field/Param Data  
      // field data members  
      long* m_rgID;  
      LPSTR m_rgName;  
  
      // pointers for the lengths  
      // of the field data  
      long* m_rgIDLengths;  
      long* m_rgNameLengths;  
  
      // input parameter data member  
      CString m_strNameParam;  
  
   .  
   .  
   .  
}  
```  
  
 Vous pouvez allouer ces tampons de stockage manuellement ou charger l'infrastructure d'effectuer cette allocation.  Pour allouer les tampons vous\-même, vous devez définir l'option **CRecordset::userAllocMultiRowBuffers** du paramètre **dwOptions** de la fonction membre **Open**.  Vérifiez que les tailles des tableaux soient au moins égales à celle du jeu de lignes.  Si vous voulez que l'infrastructure fasse elle\-même l'allocation, vous devez initialiser les pointeurs avec la valeur **NULL.** Cela est généralement fait dans le constructeur de l'objet recordset :  
  
```  
MultiRowSet::MultiRowSet( CDatabase* pDB )  
   : CRecordset( pDB )  
{  
   m_rgID = NULL;  
   m_rgName = NULL;  
   m_rgIDLengths = NULL;  
   m_rgNameLengths = NULL;  
   m_strNameParam = "";  
  
   m_nFields = 2;  
   m_nParams = 1;  
  
   .  
   .  
   .  
}  
```  
  
 Enfin, vous devez substituer la fonction membre `DoBulkFieldExchange`.  Pour les membres de données de type champ, appelez les fonctions RFX en bloc ; pour les membres de données de type paramètre, appelez les fonctions RFX.  Si vous avez ouvert le recordset en passant une instruction SQL ou une procédure stockée à **Open**, l'ordre dans lequel vous effectuez les appels RFX en bloc doit correspondre à celui des colonnes du recordset ; de même, l'ordre des appels RFX en ce qui concerne les paramètres doit correspondre à celui des paramètres dans l'instruction SQL ou la procédure stockée.  
  
```  
void MultiRowSet::DoBulkFieldExchange( CFieldExchange* pFX )  
{  
   // call the Bulk RFX functions  
   // for field data members  
   pFX->SetFieldType( CFieldExchange::outputColumn );  
   RFX_Long_Bulk( pFX, _T( "[colRecID]" ),  
                  &m_rgID, &m_rgIDLengths );  
   RFX_Text_Bulk( pFX, _T( "[colName]" ),  
                  &m_rgName, &m_rgNameLengths, 30 );  
  
   // call the RFX functions for  
   // for parameter data members  
   pFX->SetFieldType( CFieldExchange::inputParam );  
   RFX_Text( pFX, "NameParam", m_strNameParam );  
}  
```  
  
> [!NOTE]
>  Vous devez appeler la fonction membre **Close** avant que la classe dérivée `CRecordset` ne devienne hors de portée.  Cet appel garantit que toute mémoire allouée par l'infrastructure est libérée.  **Close** est un bon réflexe de programmation, indépendamment du fait que vous ayez implémenté ou non l'extraction de lignes en bloc.  
  
 Pour plus d'informations sur RFX, consultez [Record Field Exchange : fonctionnement de RFX](../../data/odbc/record-field-exchange-how-rfx-works.md).  Pour plus d'informations sur l'utilisation des paramètres, consultez [CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md) et [Recordset : paramétrage d'un recordset \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [CRecordset::m\_nFields](../Topic/CRecordset::m_nFields.md)   
 [CRecordset::m\_nParams](../Topic/CRecordset::m_nParams.md)