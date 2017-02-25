---
title: "Record Field Exchange&#160;: utilisation du code &#233;crit par l&#39;Assistant | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoFieldExchange (méthode), substituer"
  - "données membres du champ"
  - "données membres du champ, déclarer"
  - "m_nFields (donnée membre)"
  - "m_nFields (donnée membre), initialiser"
  - "m_nParams (donnée membre)"
  - "m_nParams (donnée membre), initialiser"
  - "ODBC, RFX"
  - "substituer, DoFieldExchange"
  - "RFX (ODBC), implémenter"
  - "RFX (ODBC), code de l'Assistant"
  - "Unicode, avec des classes de base de données"
ms.assetid: f00d882a-ff1b-4a75-9717-98d8762bb237
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Record Field Exchange&#160;: utilisation du code &#233;crit par l&#39;Assistant
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La présente rubrique explique le code que l'Assistant Création d'applications MFC et **Add Class** \(comme indiqué dans [Ajout d'un consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)\) écrivent pour prendre en charge RFX, ainsi que la façon dont vous pouvez, le cas échéant, modifier ce code.  
  
> [!NOTE]
>  Cette rubrique s'applique aux classes dérivées de `CRecordset` dans lesquels l'extraction de lignes en bloc n'a pas été implémentée.  Si vous utilisez l'extraction de lignes en bloc, le mécanisme RFX en bloc \(Bulk RFX\) est implémenté.  RFX en bloc est similaire à RFX.  Pour plus d'informations sur les différences, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Lorsque vous créez une classe du recordset à l'aide de l'Assistant Création d'applications MFC ou de **Add Class**, l'Assistant écrit automatiquement les éléments ci\-après associés à RFX, en fonction des colonnes, tables et sources de données que vous avez choisies dans l'Assistant :  
  
-   les déclarations des données membres de type champ de recordset dans la classe de recordset ;  
  
-   la substitution de `CRecordset::DoFieldExchange` ;  
  
-   Initialisation des données membres de champ de recordset dans le constructeur de la classe de recordset  
  
##  <a name="_core_the_field_data_member_declarations"></a> Déclarations des membres de données de type champ  
 Les Assistants écrivent la déclaration de la classe du recordset dans un fichier .h similaire au code suivant, correspondant à la classe `CSections` :  
  
```  
class CSections : public CRecordset  
{  
public:  
   CSections(CDatabase* pDatabase = NULL);  
   DECLARE_DYNAMIC(CSections)  
  
// Field/Param Data  
   CString   m_strCourseID;  
   CString   m_strInstructorID;  
   CString   m_strRoomNo;  
   CString   m_strSchedule;  
   CString   m_strSectionNo;  
  
// Overrides  
   // Wizard generated virtual function overrides  
   protected:  
   virtual CString GetDefaultConnect();  // Default connection string  
   virtual CString GetDefaultSQL();      // Default SQL for Recordset  
   virtual void DoFieldExchange(CFieldExchange* pFX);  // RFX support  
  
// Implementation  
#ifdef _DEBUG  
   virtual void AssertValid() const;  
   virtual void Dump(CDumpContext& dc) const;  
#endif  
  
};  
```  
  
 Si vous ajoutez des membres de données de type paramètre ou de nouveaux membres de données de type champ que vous liez vous\-même, ajoutez\-les à la suite de ceux qui ont été générés par l'Assistant.  
  
 Remarquez également que l'Assistant substitue la fonction membre `DoFieldExchange` de la classe `CRecordset`.  
  
##  <a name="_core_the_dofieldexchange_override"></a> Substitution de DoFieldExchange  
 [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) est le noyau de RFX.  L'infrastructure appelle `DoFieldExchange` à chaque fois qu'il faut déplacer des données depuis la source de données vers le recordset ou du recordset vers la source de données.  `DoFieldExchange` prend en charge également l'obtention d'informations relatives aux données membres de champ via les fonctions membres [IsFieldDirty](../Topic/CRecordset::IsFieldDirty.md) et [d'IsFieldNull](../Topic/CRecordset::IsFieldNull.md).  
  
 La substitution ci\-après de `DoFieldExchange` concerne la classe `CSections`.  L'Assistant écrit la fonction dans le fichier .cpp correspondant à votre classe du recordset.  
  
```  
void CSections::DoFieldExchange(CFieldExchange* pFX)  
{  
   pFX->SetFieldType(CFieldExchange::outputColumn);  
   RFX_Text(pFX, "CourseID", m_strCourseID);  
   RFX_Text(pFX, "InstructorID", m_strInstructorID);  
   RFX_Text(pFX, "RoomNo", m_strRoomNo);  
   RFX_Text(pFX, "Schedule", m_strSchedule);  
   RFX_Text(pFX, "SectionNo", m_strSectionNo);  
}  
```  
  
 Remarquez les principaux éléments de cette fonction :  
  
-   Cette section de la fonction s'intitule mappage de champ.  
  
-   Appel de `CFieldExchange::SetFieldType` via le pointeur `pFX`.  Cet appel indique que tous les appels de fonction RFX jusqu'à la fin de `DoFieldExchange` ou jusqu'au prochain appel de `SetFieldType` sont des colonnes de sortie.  Pour plus d'informations, consultez [CFieldExchange::SetFieldType](../Topic/CFieldExchange::SetFieldType.md).  
  
-   Plusieurs appels de la fonction globale `RFX_Text` — un par membre de données de type champ \(dans l'exemple, ce sont tous des variables de type `CString`\).  Ces appels spécifient la relation entre un nom de colonne dans la source de données et un membre de données de champ.  Ce sont les fonctions RFX qui effectuent concrètement le transfert des données.  La bibliothèque de classes fournit les fonctions RFX pour la totalité des types de données les plus courants.  Pour plus d'informations sur les fonctions RFX, consultez [Record Field Exchange : utilisation des fonctions RFX](../../data/odbc/record-field-exchange-using-the-rfx-functions.md).  
  
    > [!NOTE]
    >  L'ordre des colonnes dans le jeu de résultats doit correspondre à celui des appels de fonction RFX dans `DoFieldExchange`.  
  
-   Pointeur `pFX` vers un objet [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) que l'infrastructure passe lorsqu'elle appelle `DoFieldExchange`.  L'objet `CFieldExchange` précise l'opération que `DoFieldExchange` doit effectuer, la direction du transfert et d'autres informations relatives au contexte.  
  
##  <a name="_core_the_recordset_constructor"></a> Constructeur de recordsets  
 Le constructeur de recordsets écrit par l'Assistant comporte deux éléments associés à RFX :  
  
-   Initialisation de chaque donnée membre de champ  
  
-   Initialisation de la donnée membre [m\_nFields](../Topic/CRecordset::m_nFields.md) qui contient le nombre de données membres de champ  
  
 Voici un exemple de constructeur pour le recordset `CSections` :  
  
```  
CSections::CSections(CDatabase* pdb)  
   : CRecordset(pdb)  
{  
   m_strCourseID = "";  
   m_strInstructorID = "";  
   m_strRoomNo = "";  
   m_strSchedule = "";  
   m_strSectionNo = "";  
   m_nFields = 5;  
}  
```  
  
> [!NOTE]
>  Si vous ajoutez manuellement un membre de données de type champ, comme cela peut être le cas si vous liez dynamiquement de nouvelles colonnes, vous devez incrémenter `m_nFields`.  À cette fin, ajoutez une nouvelle ligne de code :  
  
```  
m_nFields += 3;  
```  
  
 Ce code correspond à l'ajout de trois nouveaux champs.  Si vous ajoutez des membres de données de paramètre, vous devez initialiser le membre de données [m\_nParams](../Topic/CRecordset::m_nParams.md) qui contient le nombre de membres de données de paramètre.  Placez l'initialisation de `m_nParams` à l'extérieur des parenthèses.  
  
## Voir aussi  
 [Record Field Exchange \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)