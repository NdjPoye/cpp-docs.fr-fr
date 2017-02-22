---
title: "CDaoFieldInfo, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoFieldInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoFieldInfo (structure)"
  - "DAO (Data Access Objects), Fields (collection)"
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# CDaoFieldInfo, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure de `CDaoFieldInfo` contient des informations sur un objet de champ défini pour les objets d'accès aux données \(DAO\).  
  
## Syntaxe  
  
```  
  
      struct CDaoFieldInfo  
{  
   CString m_strName;           // Primary  
   short m_nType;               // Primary  
   long m_lSize;                // Primary  
   long m_lAttributes;          // Primary  
   short m_nOrdinalPosition;    // Secondary  
   BOOL m_bRequired;            // Secondary  
   BOOL m_bAllowZeroLength;     // Secondary  
   long m_lCollatingOrder;      // Secondary  
   CString m_strForeignName;    // Secondary  
   CString m_strSourceField;    // Secondary  
   CString m_strSourceTable;    // Secondary  
   CString m_strValidationRule; // All  
   CString m_strValidationText; // All  
   CString m_strDefaultValue;   // All  
};  
```  
  
#### Paramètres  
 `m_strName`  
 Nomme uniquement l'objet de champ.  Pour plus d'informations, consultez la rubrique « Propriété du Nom » dans l'aide du DAO.  
  
 `m_nType`  
 Valeur qui indique le type de données du champ.  Pour plus d'informations, consultez la rubrique « Propriété du Type » dans l'aide du DAO.  À cet emplacement, la valeur de cette propriété peut être l'une des suivantes :  
  
-   **dbBoolean** Oui\/Non, de la même façon que **VRAI**\/**FAUX**  
  
-   **dbByte** Octets  
  
-   **dbInteger** Court  
  
-   **dbLong** Long  
  
-   **dbCurrency** Currency; see MFC class [COleCurrency](../../mfc/reference/colecurrency-class.md)  
  
-   **dbSingle** Unique  
  
-   **dbDouble** Double  
  
-   date et heure de**dbDate**; consultez la classe [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) de MFC  
  
-   texte de **dbText**; consultez la classe [CString](../../atl-mfc-shared/reference/cstringt-class.md)de MFC  
  
-   long binaire de**dbLongBinary** \(objet OLE\) ; vous pouvez utiliser la classe [CByteArray](../../mfc/reference/cbytearray-class.md) de MFC au lieu de la classe `CLongBinary` comme `CByteArray` est plus riche et plus facile à utiliser.  
  
-   mémo de **dbMemo**; consultez la classe `CString` de MFC  
  
-   **dbGUID** Un identificateur global unique ou identificateur unique universel utilisé avec les appels de procédure distante.  Pour plus d'informations, consultez le sujet "Propriétés des types" dans l'aide DAO.  
  
> [!NOTE]
>  N'utilisez pas les types de données string pour les données binaires.  Ceci amène vos données à s'exécuter via la couche de traduction Unicode ou ANSI, ce qui entraîne l'augmentation de la surcharge et éventuellement une traduction inattendue.  
  
 *m\_lSize*  
 Valeur qui indique la taille maximale, en octets, d'un objet de champ DAO qui contient le texte ou définit la taille d'un objet de champ qui contient du texte ou des valeurs numériques.  Pour plus d'informations, consultez la rubrique « Propriété de la taille » dans l'aide du DAO.  La taille peut avoir l'une des valeurs suivantes :  
  
|Type|Taille \(octets\)|Description|  
|----------|-----------------------|-----------------|  
|**dbBoolean**|1 octet|Oui\/Non \(de la même façon que VRAI ou FAUX\)|  
|**dbByte**|1|Byte|  
|**dbInteger**|2|Integer|  
|**dbLong**|4|Long|  
|**dbCurrency**|8|Devise \([COleCurrency](../../mfc/reference/colecurrency-class.md)\)|  
|**dbSingle**|4|Single|  
|**dbDouble**|8|Double|  
|**dbDate**|8|Date\/heure \([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)\)|  
|**dbText**|1 \- 255|Texte \([CString](../../atl-mfc-shared/reference/cstringt-class.md)\)|  
|**dbLongBinary**|0|Long binaire \(objet OLE ; [CByteArray](../../mfc/reference/cbytearray-class.md); utilisez\-le au lieu de `CLongBinary`\)|  
|**dbMemo**|0|Mémo \([CString](../../atl-mfc-shared/reference/cstringt-class.md)\)|  
|**dbGUID**|16|Un identificateur global unique ou identificateur unique universel utilisé avec les appels de procédure distante.|  
  
 `m_lAttributes`  
 Spécifie des fonctionnalités d'un objet champ contenu dans un tabledef, un recordset, un querydef, ou un objet d'index.  La valeur retournée peut être une somme de ces constantes, créée avec le OU C\+\+ de bits \(  **&#124;**\) opérateur :  
  
-   **dbFixedField** La longueur du champ est fixe \(valeur par défaut des champs numériques\).  
  
-   **dbVariableField** La longueur du champ est variable \(les champs de texte uniquement\).  
  
-   **dbAutoIncrField** La valeur de champ de nouveaux enregistrements est automatiquement incrémentée à un seul entier long qui ne peut pas être modifié.  Pris en charge pour les tables de base de données Microsoft Jet.  
  
-   **dbUpdatableField** La valeur de champ peut être modifié.  
  
-   **dbDescending** Le champ est trié selon un ordre décroissant \(de Z à A ou de 100 à 0, s'applique uniquement à un objet de champ dans une collection de champs d'un objet d'index ; dans MFC, les objets index eux\-mêmes sont contenus dans les objets tabledef\).  Si vous omettez cette constante, le champ est trié dans un ordre croissant \(de A à Z ou de 0 à 100\).  
  
 Lorsque vous vérifiez la valeur de cette propriété, vous pouvez utiliser l'opérateur d'opération ET C\+\+ de bits \(**&**\) pour déterminer un attribut spécifique.  En définissant plusieurs attributs, vous pouvez les combiner en combinant les constantes appropriées avec le OU de bits \(  **&#124;**\) opérateur.  Pour plus d'informations, consultez la rubrique « Propriété des Attributs » dans l'aide du DAO.  
  
 *m\_nOrdinalPosition*  
 Valeur qui spécifie l'ordre numérique dans laquelle vous souhaitez qu'un champ représenté par un objet de champ DAO champ soit affiché par rapport aux autres champs.  Vous pouvez définir cette propriété avec [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md).  Pour plus d'informations, consultez la rubrique « Propriété de PositionOrdinale » dans l'aide du DAO.  
  
 `m_bRequired`  
 Indique si un objet d'index de champ DAO requiert une valeur qui ne soit pas Null.  Si cette propriété est **VRAI**, l'objet de champ n'autorise pas de valeur NULL.  Si le nécessaire est défini à **FAUX**, le champ peut contenir des valeurs NULL et les valeurs répondant aux conditions spécifiées par les paramètres de propriété d'AllowZeroLength et de ValidationRule.  Pour plus d'informations, consultez la rubrique « Propriété Requises » dans l'aide du DAO.  Vous pouvez définir cette propriété pour un tabledef avec [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md).  
  
 *m\_bAllowZeroLength*  
 Indique si une chaîne vide \(""\) est une valeur valide d'un objet de champ DAO avec un type de données de type texte ou memo.  Si cette propriété est **VRAI**, une chaîne vide est une valeur valide.  Vous pouvez affecter à cette propriété **FAUX** pour vous assurer que vous ne pouvez pas utiliser une chaîne vide pour définir la valeur d'un champ.  Pour plus d'informations, consultez la rubrique « Propriété de AutoriseLongueurNulle » dans l'aide du DAO.  Vous pouvez définir cette propriété pour un tabledef avec [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md).  
  
 `m_lCollatingOrder`  
 Spécifie la séquence de l'ordre de tri dans le texte de la comparaison ou le tri de chaîne.  Pour plus d'informations, consultez la rubrique « personnaliser les paramètres de Registre Windows pour l'accès aux données » dans l'aide du DAO.  Pour obtenir la liste des valeurs qui peuvent être retournées, consultez l'attribut de **m\_lCollatingOrder** de la structure [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md).  Vous pouvez définir cette propriété pour un tabledef avec [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md).  
  
 `m_strForeignName`  
 Valeur qui, dans une relation, spécifie le nom de l'objet de champ DAO d'une table source contenant une clé étrangère qui correspond à un champ dans une table primaire.  Pour plus d'informations, consultez la rubrique « Propriété des NomsEtrangers » dans l'aide du DAO.  
  
 *m\_strSourceField*  
 Affiche le nom du champ qui est la source d'origine de données pour un objet de champ DAO contenu dans un objet tabledef, recordset, ou querydef.  Cette propriété indique le nom du champ d'origine associé à un objet.  Par exemple, vous pouvez utiliser cette propriété pour déterminer la source d'origine de données dans un champ de requête dont le nom est lié au nom du champ de la table sous\-jacente.  Pour plus d'informations, consultez la rubrique « SourceField, les propriétés de SourceTable » dans l'aide du DAO.  Vous pouvez définir cette propriété pour un tabledef avec [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md).  
  
 *m\_strSourceTable*  
 Affiche le nom de la table qui est la source d'origine des données pour un objet de champ DAO contenu dans un objet tabledef, recordset, ou querydef.  Cette propriété indique le nom de la table d'origine associée à un objet.  Par exemple, vous pouvez utiliser cette propriété pour déterminer la source d'origine de données dans un champ de requête dont le nom est lié au nom du champ de la table sous\-jacente.  Pour plus d'informations, consultez la rubrique « SourceField, les propriétés de SourceTable » dans l'aide du DAO.  Vous pouvez définir cette propriété pour un tabledef avec [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md).  
  
 `m_strValidationRule`  
 Valeur qui valide les données dans un domaine lorsqu'il est modifié ou ajouté à une table.  Pour plus d'informations, consultez la rubrique « Propriété de RègleDeValidation » dans l'aide du DAO.  Vous pouvez définir cette propriété pour un tabledef avec [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md).  
  
 Pour plus d'informations sur les tabledefs, consultez l'attribut de **m\_strValidationRule** de la structure [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md).  
  
 `m_strValidationText`  
 Valeur qui spécifie le texte du message que votre application affiche si la valeur d'un objet field DAO ne satisfait pas la règle de validation spécifiée par le paramètre de propriété de RègleDeValidation.  Pour plus d'informations, consultez la rubrique « Propriété de TexteDeValidation » dans l'aide du DAO.  Vous pouvez définir cette propriété pour un tabledef avec [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md).  
  
 *m\_strDefaultValue*  
 La valeur par défaut d'un champ DAO objet.  Lorsqu'un nouvel enregistrement est créé, le paramètre de la propriété ValeurParDéfaut est automatiquement écrite en tant que valeur du champ.  Pour plus d'informations, consultez la rubrique « Propriété des ValeursParDéfaut » dans l'aide du DAO.  Vous pouvez définir cette propriété pour un tabledef avec [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md).  
  
## Notes  
 Les références au Primaire, Secondaire, et Tous ceux qui se trouvent au\-dessus indiquent comment les informations sont retournées par la méthode `GetFieldInfo` dans les classes [CDaoTableDef](../Topic/CDaoTableDef::GetFieldInfo.md), [CDaoQueryDef](../Topic/CDaoQueryDef::GetFieldInfo.md) et [CDaoRecordset](../Topic/CDaoRecordset::GetFieldInfo.md).  
  
 Les objets de champ ne sont pas représentés par une classe de MFC.  En revanche, les objets DAO sous\-jacentes des objets de MFC des classes suivantes contiennent des collections de champs : [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), et [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md).  Ces classes fournissent les fonctions membres pour accéder à des éléments individuels d'informations d'index, ou vous pouvez accéder à tous ces éléments en même temps avec un objet `CDaoFieldInfo` en appelant la méthode `GetFieldInfo` de l'objet conteneur.  
  
 Outre l'utilisation pour consulter les propriétés de l'objet, vous pouvez également utiliser `CDaoFieldInfo` pour construire un paramètre d'entrée pour créer de nouveaux champs dans un tabledef.  Des options plus simples sont disponibles pour cette tâche, mais si vous voulez un contrôle plus fin, vous pouvez utiliser la version de [CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md) qui accepte un paramètre `CDaoFieldInfo`.  
  
 Les informations récupérées par la méthode `GetFieldInfo` \(de la classe qui contient le champ\) sont stockées dans une structure de `CDaoFieldInfo`.  Appelez la méthode `GetFieldInfo` de l'objet conteneur dans lequel la collection de champs l'objet de champ est enregistré.  `CDaoFieldInfo` définit également une fonction membre `Dump` dans les versions de débogage.  Vous pouvez utiliser `Dump` pour vider le contenu d'un objet `CDaoFieldInfo`.  
  
## Configuration requise  
 **En\-tête :** afxdao.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetFieldInfo](../Topic/CDaoTableDef::GetFieldInfo.md)   
 [CDaoRecordset::GetFieldInfo](../Topic/CDaoRecordset::GetFieldInfo.md)   
 [CDaoQueryDef::GetFieldInfo](../Topic/CDaoQueryDef::GetFieldInfo.md)