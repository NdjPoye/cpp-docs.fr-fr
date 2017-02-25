---
title: "CDaoIndexInfo, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoIndexInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoIndexInfo (structure)"
  - "DAO (Data Access Objects), Indexes (collection)"
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# CDaoIndexInfo, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure d' `CDaoIndexInfo` contient des informations sur un objet d'index défini pour les objets d'accès aux données \(DAO\).  
  
## Syntaxe  
  
```  
  
      struct CDaoIndexInfo {  
   CDaoIndexInfo( );                   // Constructor  
   CString m_strName;                  // Primary  
   CDaoIndexFieldInfo* m_pFieldInfos;  // Primary  
   short m_nFields;                    // Primary  
   BOOL m_bPrimary;                    // Secondary  
   BOOL m_bUnique;                     // Secondary  
   BOOL m_bClustered;                  // Secondary  
   BOOL m_bIgnoreNulls;                // Secondary  
   BOOL m_bRequired;                   // Secondary  
   BOOL m_bForeign;                    // Secondary  
   long m_lDistinctCount;              // All  
  
   // Below the // Implementation comment:  
   // Destructor, not otherwise documented  
};   
```  
  
#### Paramètres  
 `m_strName`  
 Nomme uniquement l'objet de champ.  Pour plus d'informations, consultez la rubrique « Propriété du Nom » dans l'aide du DAO.  
  
 `m_pFieldInfos`  
 Un pointeur vers un tableau d'objets d' [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) indiquant quels champs de tabledef ou de recordset sont clés dans un index.  Chaque objet identifie un champ dans l'index.  La commande par défaut d'index est croissante.  Un objet d'index peut comprendre un ou plusieurs champs qui représentent des clés d'index pour chaque enregistrement.  Ceux\-ci peuvent être croissants, décroissants, ou une combinaison.  
  
 `m_nFields`  
 Le nombre de champs stockés dans `m_pFieldInfos`.  
  
 *m\_bPrimary*  
 Si la propriété primaire est **TRUE**, l'objet index représente un index primaire.  Un index primaire consiste en un ou plusieurs champs qui identifient de manière unique tous les enregistrements dans une table dans un ordre prédéfini.  Etant donné que le champ d'index doit être unique, l'unique propriété de l'objet d'index est également définie à **TRUE** dans DAO.  Si l'index primaire se compose de plusieurs champs, chaque champ peut contenir des valeurs dupliquées, mais chaque combinaison de valeurs de tous les champs indexés doit être unique.  Un index primaire se compose d'une clé pour la table et contient généralement les mêmes champs que la clé primaire.  
  
 Lorsque vous définissez une clé primaire pour une table, la clé primaire est automatiquement définie comme l'index primaire de la table.  Pour plus d'informations, consultez les rubriques « Propriété Primaire » et « Propriété Unique » dans l'aide du DAO.  
  
> [!NOTE]
>  Il peut exister, au plus, un index primaire sur une table.  
  
 *m\_bUnique*  
 Indique si un objet d'index représente un index unique pour une table.  Si cette propriété est **TRUE**, l'objet d'index représente un index unique.  Un index unique consiste en un ou plusieurs champs qui réorganisent logiquement tous les enregistrements d'une table dans un ordre unique et prédéfini.  Si l'index se compose d'un champ, les valeurs de ce champ doivent être uniques pour la table entière.  Si l'index se compose de plusieurs champs, chaque champ peut contenir des valeurs dupliquées, mais chaque combinaison de valeurs de tous les champs indexés doit être unique.  
  
 Si les propriétés Uniques et les propriétés Primaires d'un objet d'index sont à la fois définies à **TRUE**, l'index est unique et primaire: il identifie de façon unique tous les enregistrements de la table dans un ordre prédéfini et logique.  Si la propriété primaire est définie à **FALSE**, l'index est un index secondaire.  Les index secondaires \(à la fois clé ou non\-clé\) réorganisent logiquement les enregistrements dans un ordre prédéfinies sans servir d'identification à des enregistrements dans la table.  
  
 Pour plus d'informations, consultez les rubriques « Propriété Primaire » et « Propriété Unique » dans l'aide du DAO.  
  
 *m\_bClustered*  
 Indique si un objet d'index représente un index en cluster pour une table.  Si cette propriété est **TRUE**, l'objet d'index représente un index en cluster; sinon, il ne le fait pas.  Un index en cluster est composé d'un ou plusieurs champs non\-clés qui, pris ensemble, réorganisent tous les enregistrements d'une table dans un ordre prédéfini.  Avec un index en cluster, les données dans la table est littéralement stockée dans l'ordre spécifié par l'index en cluster.  Un index en cluster permet d'accéder efficacement à des enregistrements dans une table.  Pour plus d'informations, consultez la rubrique "Propriété en cluster" dans l'aide DAO.  
  
> [!NOTE]
>  La propriété en cluster est ignorée pour les bases de données qui utilisent le moteur de base de données Microsoft Jet car le moteur de base de données Jet ne prend pas en charge les index en cluster.  
  
 *m\_bIgnoreNulls*  
 Indique s'il existe des entrées d'index pour les enregistrements qui ont des valeurs NULL dans leurs champs d'index.  Si cette propriété est **TRUE**, les champs avec des valeurs NULL n'ont pas d'entrée d'index.  Pour accélérer les recherches d'enregistrements à l'aide d'un champ, vous pouvez définir un index pour le champ.  Si vous autorisez des entrées NULL dans un champ indexé et espérez que plusieurs entrées sont NULL, vous pouvez définir la propriété d'IgnoreNulls pour l'objet d'index à **TRUE** pour réduire la quantité d'espace de stockage que l'index utilise.  Le paramètre de propriété d'IgnoreNulls et les paramètres de propriétés requis déterminent ensemble si un enregistrement avec une valeur d'index Null a une entrée d'index, comme le montre le tableau suivant.  
  
|IgnoreNulls|Obligatoire|Null dans le champ d'index|  
|-----------------|-----------------|--------------------------------|  
|True|False|Valeur NULL autorisée; aucune entrée d'index ajoutée.|  
|False|False|Valeur NULL autorisée; entrée d'index ajoutée.|  
|True ou False|True|Valeur NULL non autorisée; aucune entrée d'index ajoutée.|  
  
 Pour plus d'informations, consultez le thème "Propriété IgnoreNulls" dans l'aide DAO.  
  
 `m_bRequired`  
 Indique si un objet d'index de DAO requiert une valeur non null.  Si cette propriété est **TRUE**, l'objet d'index n'autorise pas de valeur NULL.  Pour plus d'informations, consultez le thème "Propriété Requise" dans l'aide DAO.  
  
> [!TIP]
>  Lorsque vous pouvez définir cette propriété pour un objet d'index de DAO ou un pour un objet de champ \(contenu dans un objet de tabledef, de recordset, ou de querydef\), définissez\-le pour l'objet de champ.  La validité de la valeur de la propriété d'un objet de champ est vérifiée avant celle d'un objet d'index.  
  
 *m\_bForeign*  
 Indique si un objet d'index représente une clé étrangère dans une table.  Si cette propriété est **TRUE**, l'index représente une clé étrangère dans une table.  Une clé étrangère se compose d'un ou plusieurs champs d'une table étrangère qui identifient de façon unique une ligne dans une table primaire.  Le moteur de base de données Microsoft Jet crée un objet d'index pour la table étrangère et définit la propriété étrangère lorsque vous créez une relation qui impose l'intégrité référentielle.  Pour plus d'informations, consultez le thème "Propriété Etrangère" dans l'aide DAO.  
  
 *m\_lDistinctCount*  
 Indique le nombre de valeurs uniques pour l'objet d'index incluses dans la table associée.  Vérifiez la propriété DISTINCTCOUNT pour déterminer le nombre de valeurs uniques, ou de clés, dans un index.  N'importe quelle clé est comptée une seule fois, bien qu'il puisse exister plusieurs occurrences de cette valeur si l'index autorise des valeurs dupliquées.  Ces informations sont utiles dans les applications qui tentent d'optimiser l'accès aux données par l'évaluation des informations d'index.  Le nombre de valeurs uniques est également appelé cardinalité d'un objet d'index.  La propriété DISTINCTCOUNT ne reflète pas toujours le nombre réel de clés à un moment donné.  Par exemple, une modification provoquée par une restauration de transaction n'est pas transmise immédiatement dans la propriété DISTINCTCOUNT.  Pour plus d'informations, consultez le thème "Propriété DistinctCount" dans l'aide DAO.  
  
## Notes  
 Les références à Primaire, Secondaire, et Tous ceux qui se trouvent au\-dessus indiquent comment les informations sont retournées par la fonction membre d' `GetIndexInfo` dans les classes [CDaoTableDef](../Topic/CDaoTableDef::GetIndexInfo.md) et [CDaoRecordset](../Topic/CDaoRecordset::GetIndexInfo.md).  
  
 Les objets d'index ne sont pas représentés par une classe de MFC.  En revanche, les objets DAO sous\-jacents des objets MFC de la classe [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) ou de la classe [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) contiennent une collection d'objets d'index, appelée collection d'index.  Ces classes fournissent les fonctions membres pour accéder à des éléments individuels d'informations d'index, ou vous pouvez accéder à tous ces éléments en même temps avec un objet d' `CDaoIndexInfo` en appelant la fonction membre d' `GetIndexInfo` de l'objet conteneur.  
  
 `CDaoIndexInfo` a un constructeur et un destructeur afin d'alouer et de libérer correctement les informations de champs d'index dans `m_pFieldInfos`.  
  
 Les informations récupérées par la fonction membre d' `GetIndexInfo` d'un objet de tabledef sont stockées dans une structure d' `CDaoIndexInfo`.  Appelez la fonction membre d' `GetIndexInfo` de l'objet conteneur de tabledef dans lequel la collection d'index de l'objet index est stockée.  `CDaoIndexInfo` définit également une fonction membre `Dump` dans les versions de débogage.  Vous pouvez utiliser `Dump` pour vider le contenu d'un objet `CDaoIndexInfo`.  
  
## Configuration requise  
 **En\-tête :** afxdao.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../Topic/CDaoTableDef::GetIndexInfo.md)