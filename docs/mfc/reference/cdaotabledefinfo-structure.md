---
title: "CDaoTableDefInfo, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoTableDefInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoTableDefInfo (structure)"
  - "DAO (Data Access Objects), TableDefs (collection)"
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoTableDefInfo, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure de `CDaoTableDefInfo` contient des informations sur un objet de type tabledef défini pour les objets d'accès aux données \(DAO\).  
  
## Syntaxe  
  
```  
  
      struct CDaoTableDefInfo  
{  
   CString m_strName;               // Primary  
   BOOL m_bUpdatable;               // Primary  
   long m_lAttributes;              // Primary  
   COleDateTime m_dateCreated;      // Secondary  
   COleDateTime m_dateLastUpdated;  // Secondary  
   CString m_strSrcTableName;       // Secondary  
   CString m_strConnect;            // Secondary  
   CString m_strValidationRule;     // All  
   CString m_strValidationText;     // All  
   long m_lRecordCount;             // All  
};  
```  
  
#### Paramètres  
 `m_strName`  
 Nomme de façon unique l'objet de tabledef.  Pour récupérer la valeur de cette propriété directement, appelez la fonction membre de [GetName](../Topic/CDaoTableDef::GetName.md) de l'objet de tabledef.  Pour plus d'informations, consultez le sujet "Propriété du nom" dans l'aide DAO.  
  
 `m_bUpdatable`  
 Indique si des modifications peuvent être apportées à la table.  La méthode rapide pour déterminer si une table peut être mise à jour est d'ouvrir un objet de `CDaoTableDef` pour la table et d'appeler la fonction membre de [CanUpdate](../Topic/CDaoTableDef::CanUpdate.md) de l'objet.  `CanUpdate` retourne toujours une valeur différente de zéro \(**TRUE**\) pour un objet nouvellement créé de tabledef et 0 \(**FALSE**\) pour un objet associé à tabledef.  Un objet de tabledef peut être ajouté uniquement à une base de données dont l'utilisateur actuel dispose d'autorisations d'écriture.  Si la table contient uniquement des champs qui ne peuvent être mis à jour, retourne 0 pour `CanUpdate`.  Lorsqu'un ou plusieurs champs peuvent être mises à jour, `CanUpdate` retourne une valeur différente de zéro.  Vous pouvez modifier uniquement les champs pouvant être mis à jour.  Pour plus d'informations, consultez le sujet "propriétés de mises à jour" dans l'aide DAO.  
  
 `m_lAttributes`  
 Spécifie les caractéristiques de la table représentée par l'objet de tabledef.  Pour extraire les attributs actuels d'un tabledef, appelez la fonction membre de [GetAttributes](../Topic/CDaoTableDef::GetAttributes.md).  La valeur retournée peut être une combinaison de ces de constantes \(à l'aide de la fonction OR en bits \(  **&#124;**\)operateur\):  
  
-   **dbAttachExclusive** Pour les bases de données qui utilisent le moteur de base de données Microsoft Jet, indique que la table est une table jointe ouverte pour une utilisation exclusive.  
  
-   **dbAttachSavePWD** Pour les bases de données qui utilisent le moteur de base de données Microsoft Jet, indique que l'ID d'utilisateur et le mot de passe pour la table jointe sont stockés avec les informations de connexion.  
  
-   **dbSystemObject** Indique que la table est une table système fournie par le moteur de base de données Microsoft Jet. \(En lecture seule.\)  
  
-   **dbHiddenObject** Indique la table est une table masquée fournie par le moteur de base de données Microsoft Jet \(pour une utilisation temporaire\). \(En lecture seule.\)  
  
-   **dbAttachedTable** Indique que la table est une table jointe d'une base de données non ODBC, telle qu'une base de données de paradoxe.  
  
-   **dbAttachedODBC** Indique que la table est une table jointe d'une base de données ODBC, telle que Microsoft SQL Server.  
  
 `m_dateCreated`  
 Date et heure de création de la table.  Pour extraire directement la date à laquelle la table a été créé, appelez la fonction membre de [GetDateCreated](../Topic/CDaoTableDef::GetDateCreated.md) de l'objet `CDaoTableDef` associé à la table.  Pour plus d'informations, consultez les commentaires ci\-dessous.  Pour plus d'informations, consultez la rubrique « DateCréation, les propriétés de Modifié » dans l'aide du DAO.  
  
 `m_dateLastUpdated`  
 Date et heure de la modification apportée la plus récente à la création de la table.  Pour extraire directement la date à laquelle la table a été mise à jour la dernière fois, appelez la fonction membre de [GetDateUpdated](../Topic/CDaoTableDef::GetDateLastUpdated.md) de l'objet `CDaoTableDef` associé à la table.  Pour plus d'informations, consultez les commentaires ci\-dessous.  Pour plus d'informations, consultez la rubrique « DateCréation, les propriétés de Modifié » dans l'aide du DAO.  
  
 *m\_strSrcTableName*  
 Spécifie le nom d'une table jointe si il y en a.  Pour extraire directement le nom de table source, appelez la fonction membre de [GetSourceTableName](../Topic/CDaoTableDef::GetSourceTableName.md) de l'objet de `CDaoTableDef` associé à la table.  
  
 `m_strConnect`  
 Fournit des informations sur la source d'une base de données ouverte.  Vous pouvez activer cette propriété en appelant la fonction membre de [GetConnect](../Topic/CDaoTableDef::GetConnect.md) de votre objet de `CDaoTableDef`.  Pour plus d'informations sur les chaînes de connexion, consultez `GetConnect`.  
  
 `m_strValidationRule`  
 Valeur qui valide les données dans le tabledef champs à mesure qu'elles sont ajoutées ou modifiées dans une table.  La validation est prise en charge uniquement pour les bases de données qui utilisent le moteur de base de données Microsoft Jet.  Pour extraire directement la règle de validation, appelez la fonction membre de [GetValidationRule](../Topic/CDaoTableDef::GetValidationRule.md) de l'objet de `CDaoTableDef` associé à la table.  Pour plus d'informations, consultez la rubrique « Propriétés RègleValidation» dans l'aide du DAO.  
  
 `m_strValidationText`  
 Valeur qui spécifie le texte du message que votre application doit afficher si la règle de validation spécifiée par la propriété de ValidationRule n'est pas remplie.  Pour plus d'informations, consultez la rubrique « Propriétés TexteValidation» dans l'aide du DAO.  
  
 *m\_lRecordCount*  
 Nombre d'enregistrements accessibles dans un objet de tabledef.  Cet paramètre de propriété est en lecture seule.  Pour extraire directement le nombre d'enregistrements, appelez la fonction membre de [GetRecordCount](../Topic/CDaoTableDef::GetRecordCount.md) de l'objet de `CDaoTableDef`.  La documentation de `GetRecordCount` décrit le nombre d'enregistrements ultérieur.  Notez que récupérer ce nombre peut être une opération qui prend du temps si la table contient de nombreux enregistrements.  
  
## Notes  
 Le tabledef est un objet de la classe [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md).  Des références au primaire, au secondaire, et au delà indiquent comment les informations sont retournées par la fonction membre de [GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md) de la classe `CDaoDatabase`.  
  
 Les informations récupérées par la fonction membre de [CDaoDatabase::GetTableDefInfo](../Topic/CDaoDatabase::GetTableDefInfo.md) sont stockées dans une structure de `CDaoTableDefInfo`.  Appelez la fonction membre de `GetTableDefInfo` de l'objet de `CDaoDatabase` dans lequel la collection de tabledefs l'objet de tabledef est enregistré.  `CDaoTableDefInfo` définit également une fonction membre `Dump` dans les versions de débogage.  Vous pouvez utiliser `Dump` pour vider le contenu d'un objet `CDaoTableDefInfo`.  
  
 Les paramètres de date et d'heure sont dérivées à partir de l'ordinateur sur lequel la table de base a été créée ou mis à jour pour la dernière fois.  Dans un environnement multi\-utilisateur, les utilisateurs doivent obtenir directement ces paramètres du serveur de fichiers pour éviter les anomalies dans les paramètres de propriété de DateCréation et DateModification.  
  
## Configuration requise  
 **En\-tête :** afxdao.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoTableDef::CanUpdate](../Topic/CDaoTableDef::CanUpdate.md)   
 [CDaoTableDef::GetAttributes](../Topic/CDaoTableDef::GetAttributes.md)   
 [CDaoTableDef::GetDateCreated](../Topic/CDaoTableDef::GetDateCreated.md)   
 [CDaoTableDef::GetDateLastUpdated](../Topic/CDaoTableDef::GetDateLastUpdated.md)   
 [CDaoTableDef::GetRecordCount](../Topic/CDaoTableDef::GetRecordCount.md)   
 [CDaoTableDef::GetSourceTableName](../Topic/CDaoTableDef::GetSourceTableName.md)   
 [CDaoTableDef::GetValidationRule](../Topic/CDaoTableDef::GetValidationRule.md)   
 [CDaoTableDef::GetValidationText](../Topic/CDaoTableDef::GetValidationText.md)