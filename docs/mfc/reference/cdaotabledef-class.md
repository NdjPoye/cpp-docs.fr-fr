---
title: "CDaoTableDef Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoTableDef"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoTableDef class"
  - "classes de base de données (C++), DAO"
  - "database tables [C++], attached table definition"
  - "database tables [C++], base table definition"
  - "tabledefs [C++]"
ms.assetid: 7c5d2254-8475-43c4-8a6c-2d32ead194c9
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CDaoTableDef Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente la définition stockée d'une table de base ou d'une table jointe.  
  
## Syntaxe  
  
```  
class CDaoTableDef : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoTableDef::CDaoTableDef](../Topic/CDaoTableDef::CDaoTableDef.md)|Crée un objet de **CDaoTableDef** .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoTableDef::Append](../Topic/CDaoTableDef::Append.md)|Ajoute une nouvelle table dans la base de données.|  
|[CDaoTableDef::CanUpdate](../Topic/CDaoTableDef::CanUpdate.md)|Retourne une valeur différente de zéro si le tableau peut être mis à jour \(vous pouvez modifier la définition des champs ou des propriétés du tableau\).|  
|[CDaoTableDef::Close](../Topic/CDaoTableDef::Close.md)|Ferme un tabledef ouvert.|  
|[CDaoTableDef::Create](../Topic/CDaoTableDef::Create.md)|Crée un tableau qui peut être ajouté à la base de données à l'aide de [ajoutez](../Topic/CDaoTableDef::Append.md).|  
|[CDaoTableDef::CreateField](../Topic/CDaoTableDef::CreateField.md)|Appelé pour créer un champ d'une table.|  
|[CDaoTableDef::CreateIndex](../Topic/CDaoTableDef::CreateIndex.md)|Appelé pour créer un index pour un tableau.|  
|[CDaoTableDef::DeleteField](../Topic/CDaoTableDef::DeleteField.md)|Appelée pour supprimer un champ d'une table.|  
|[CDaoTableDef::DeleteIndex](../Topic/CDaoTableDef::DeleteIndex.md)|Appelée pour supprimer un index d'un tableau.|  
|[CDaoTableDef::GetAttributes](../Topic/CDaoTableDef::GetAttributes.md)|Retourne une valeur qui indique un ou plusieurs caractéristiques d'un objet d' `CDaoTableDef` .|  
|[CDaoTableDef::GetConnect](../Topic/CDaoTableDef::GetConnect.md)|Retourne une valeur qui fournit des informations sur la source d'un tableau.|  
|[CDaoTableDef::GetDateCreated](../Topic/CDaoTableDef::GetDateCreated.md)|Retourne la date et l'heure de la table de base sous\-jacente à un objet d' `CDaoTableDef` a été créée.|  
|[CDaoTableDef::GetDateLastUpdated](../Topic/CDaoTableDef::GetDateLastUpdated.md)|Retourne la date et l'heure de la modification apportée la plus récente à la conception de la table de base.|  
|[CDaoTableDef::GetFieldCount](../Topic/CDaoTableDef::GetFieldCount.md)|Retourne une valeur qui représente le nombre de champs dans le tableau.|  
|[CDaoTableDef::GetFieldInfo](../Topic/CDaoTableDef::GetFieldInfo.md)|Retourne les types spécifiques d'informations sur les champs du tableau.|  
|[CDaoTableDef::GetIndexCount](../Topic/CDaoTableDef::GetIndexCount.md)|Retourne le nombre d'index du tableau.|  
|[CDaoTableDef::GetIndexInfo](../Topic/CDaoTableDef::GetIndexInfo.md)|Retourne les types spécifiques d'informations sur les index du tableau.|  
|[CDaoTableDef::GetName](../Topic/CDaoTableDef::GetName.md)|Retourne le nom défini par l'utilisateur du tableau.|  
|[CDaoTableDef::GetRecordCount](../Topic/CDaoTableDef::GetRecordCount.md)|Retourne le nombre d'enregistrements dans la table.|  
|[CDaoTableDef::GetSourceTableName](../Topic/CDaoTableDef::GetSourceTableName.md)|Retourne une valeur qui spécifie le nom de table jointe dans la base de données source.|  
|[CDaoTableDef::GetValidationRule](../Topic/CDaoTableDef::GetValidationRule.md)|Retourne une valeur qui valide les données dans un domaine lorsqu'il est modifié ou ajouté à une table.|  
|[CDaoTableDef::GetValidationText](../Topic/CDaoTableDef::GetValidationText.md)|Retourne une valeur qui spécifie le texte du message que votre application affiche si la valeur d'un objet champ ne satisfait pas à la règle de validation spécifiée.|  
|[CDaoTableDef::IsOpen](../Topic/CDaoTableDef::IsOpen.md)|Retourne une valeur différente de zéro si le tableau est ouvert.|  
|[CDaoTableDef::Open](../Topic/CDaoTableDef::Open.md)|Ouvre un tabledef existant enregistré dans la collection du tabledef de la base de données.|  
|[CDaoTableDef::RefreshLink](../Topic/CDaoTableDef::RefreshLink.md)|Met à jour les informations de connexion pour une table jointe.|  
|[CDaoTableDef::SetAttributes](../Topic/CDaoTableDef::SetAttributes.md)|Définit une valeur qui indique un ou plusieurs caractéristiques d'un objet d' `CDaoTableDef` .|  
|[CDaoTableDef::SetConnect](../Topic/CDaoTableDef::SetConnect.md)|Définit une valeur qui fournit des informations sur la source d'un tableau.|  
|[CDaoTableDef::SetName](../Topic/CDaoTableDef::SetName.md)|Définit le nom de la table.|  
|[CDaoTableDef::SetSourceTableName](../Topic/CDaoTableDef::SetSourceTableName.md)|Définit une valeur qui spécifie le nom d'une table jointe dans la base de données source.|  
|[CDaoTableDef::SetValidationRule](../Topic/CDaoTableDef::SetValidationRule.md)|Définit une valeur qui valide les données dans un domaine lorsqu'il est modifié ou ajouté à une table.|  
|[CDaoTableDef::SetValidationText](../Topic/CDaoTableDef::SetValidationText.md)|Définit une valeur qui spécifie le texte du message que votre application affiche si la valeur d'un objet champ ne satisfait pas à la règle de validation spécifiée.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoTableDef::m\_pDAOTableDef](../Topic/CDaoTableDef::m_pDAOTableDef.md)|Pointeur vers l'interface DAO sous\-jacent à l'objet de tabledef.|  
|[CDaoTableDef::m\_pDatabase](../Topic/CDaoTableDef::m_pDatabase.md)|Base de données source de cette table.|  
  
## Notes  
 Chaque objet de base de données DAO gère une collection, TableDefs appelé, qui contient tous les objets tabledef enregistrés de DAO.  
  
 Vous manipulez une définition de table à l'aide d'un objet d' `CDaoTableDef` .  Par exemple, vous pouvez :  
  
-   Examinez la structure de champ et d'index de tous les variables locales, jointe, ou la table externe dans une base de données.  
  
-   Appelez les fonctions membres d' `SetConnect` et d' `SetSourceTableName` pour les tables jointes, puis utilisez la fonction membre d' `RefreshLink` pour mettre à jour des connexions aux tables jointes.  
  
-   Appelez la fonction membre d' `CanUpdate` pour déterminer si vous pouvez les définitions de champ d'édition dans le tableau.  
  
-   Obtenez ou définissez les états de validation à l'aide de `GetValidationRule` et `SetValidationRule`, et les fonctions membres d' `GetValidationText` et d' `SetValidationText` .  
  
-   Utilisez la fonction membre de **Ouvrir** pour créer une table, une feuille de réponse dynamique, ou un objet de type instantané d' `CDaoRecordset` .  
  
    > [!NOTE]
    >  Les classes de bases de données DAO sont séparées des classes de base de données MFC basée sur \(Open Database Connectivity\).  Tous les noms de classes de bases de données DAO ont le préfixe « CDao ».  Vous pouvez encore accéder aux sources de données ODBC avec les classes DAO ; les classes DAO offrent généralement des fonctionnalités améliorées car elles sont spécifiques au moteur de base de données Microsoft Jet.  
  
### Pour utiliser des objets de tabledef d'utiliser un tableau existant ou créer une table  
  
1.  Dans tous les cas, construisez d'abord un objet d' `CDaoTableDef` , en fournissant un pointeur vers un objet de [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) auquel la table appartient.  
  
2.  Effectuez ensuite les éléments suivants, selon que vous voulez :  
  
    -   Pour utiliser un existant a enregistré le tableau, appelez la fonction membre d' [Ouvrez](../Topic/CDaoTableDef::Open.md) de l'objet de tabledef, en fournissant le nom de la table enregistré.  
  
    -   Pour créer une table, appelez la fonction membre de [Create](../Topic/CDaoTableDef::Create.md) de l'objet de tabledef, en fournissant le nom de la table.  Appelez [CreateField](../Topic/CDaoTableDef::CreateField.md) et [CreateIndex](../Topic/CDaoTableDef::CreateIndex.md) pour ajouter des champs et des index à la table.  
  
    -   Appelez [ajoutez](../Topic/CDaoTableDef::Append.md) enregistrer la table en l'ajoutant à la collection des tabledefs de la base de données.  **Créer** place le tabledef dans un état ouvert, donc après avoir appelé **Créer** que vous n'appelez pas **Ouvrir**.  
  
        > [!TIP]
        >  La façon la plus facile de créer les tables enregistrées est de créer et de les enregistrer dans votre base de données à l'aide de Microsoft Access.  Vous pouvez ouvrir et les utiliser dans votre code MFC.  
  
 Pour utiliser l'objet de tabledef que vous avez ouvert ou l'avez créé, créez ou ouvrez un objet d' `CDaoRecordset` , en spécifiant le nom du tabledef avec une valeur de **dbOpenTable** dans le paramètre d' `nOpenType` .  
  
 Pour utiliser un objet de tabledef pour créer un objet d' `CDaoRecordset` , vous créez généralement ou ouvrez un tabledef comme décrit ci\-dessus, puis construisez un objet recordset, en passant un pointeur vers l'objet de tabledef lorsque vous appelez [CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md).  Le tabledef que vous passez doit être dans un état ouvert.  Pour plus d'informations, consultez la classe [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Lorsque vous avez fini d'utiliser un objet de tabledef, appelez sa fonction membre de [Fermez](../Topic/CDaoRecordset::Close.md) ; détruisez l'objet de tabledef.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoTableDef`  
  
## Configuration requise  
 **Header:** afxdao.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoRecordset Class](../../mfc/reference/cdaorecordset-class.md)