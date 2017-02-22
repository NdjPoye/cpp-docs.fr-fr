---
title: "CDaoRecordset Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDaoRecordset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoRecordset (classe)"
  - "enregistrements, CDaoRecordSet"
  - "recordsets, types"
ms.assetid: 2322067f-1027-4662-a5d7-aa2fc7488630
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 27
---
# CDaoRecordset Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente un ensemble d'enregistrements sélectionnés à partir d'une source de données.  
  
## Syntaxe  
  
```  
  
class CDaoRecordset : public CObject  
  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoRecordset::CDaoRecordset](../Topic/CDaoRecordset::CDaoRecordset.md)|Construit un objet `CDaoRecordset`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoRecordset::AddNew](../Topic/CDaoRecordset::AddNew.md)|Se prépare à ajouter un nouvel enregistrement.  Appel [mise à jour](../Topic/CDaoRecordset::Update.md) pour effectuer l'addition.|  
|[CDaoRecordset::CanAppend](../Topic/CDaoRecordset::CanAppend.md)|Retourne une valeur différente de zéro si les nouveaux enregistrements peuvent être ajoutés au recordset via la fonction membre d' [AddNew](../Topic/CDaoRecordset::AddNew.md) .|  
|[CDaoRecordset::CanBookmark](../Topic/CDaoRecordset::CanBookmark.md)|Retourne une valeur différente de zéro si le recordset prend en charge des signets.|  
|[CDaoRecordset::CancelUpdate](../Topic/CDaoRecordset::CancelUpdate.md)|Annule toutes les mises à jour en attente en raison de [modification](../Topic/CDaoRecordset::Edit.md) ou d'une opération d' [AddNew](../Topic/CDaoRecordset::AddNew.md) .|  
|[CDaoRecordset::CanRestart](../Topic/CDaoRecordset::CanRestart.md)|Retourne une valeur différente de zéro si [Actualiser](../Topic/CDaoRecordset::Requery.md) peut être appelé pour exécuter la requête du recordset de nouveau.|  
|[CDaoRecordset::CanScroll](../Topic/CDaoRecordset::CanScroll.md)|Retourne une valeur différente de zéro si vous pouvez parcourir les enregistrements.|  
|[CDaoRecordset::CanTransact](../Topic/CDaoRecordset::CanTransact.md)|Retourne une valeur différente de zéro si la source de données prend en charge les transactions.|  
|[CDaoRecordset::CanUpdate](../Topic/CDaoRecordset::CanUpdate.md)|Retourne une valeur différente de zéro si le recordset peut être mis à jour \(vous pouvez ajouter, mettre à jour, ou supprimer des enregistrements\).|  
|[CDaoRecordset::Close](../Topic/CDaoRecordset::Close.md)|Ferme le recordset.|  
|[CDaoRecordset::Delete](../Topic/CDaoRecordset::Delete.md)|Supprime l'enregistrement actif du recordset.  Vous devez explicitement le défilement à un autre enregistrement après la suppression.|  
|[CDaoRecordset::DoFieldExchange](../Topic/CDaoRecordset::DoFieldExchange.md)|Appelé pour échanger des données \(dans les deux sens\) entre les membres de données de type champ de recordset et l'enregistrement correspondant de la source de données.  Processus DFX d'outils \(DFX\).|  
|[CDaoRecordset::Edit](../Topic/CDaoRecordset::Edit.md)|Se prépare à des modifications apportées à l'enregistrement courant.  Appel **Mettre à jour** pour terminer la modification.|  
|[CDaoRecordset::FillCache](../Topic/CDaoRecordset::FillCache.md)|Remplit tout l'ou partie cache local d'un objet recordset qui contient des données d'une source de données ODBC.|  
|[CDaoRecordset::Find](../Topic/CDaoRecordset::Find.md)|Recherche le premier, ensuite, précédent, ou dernier emplacement d'une chaîne particulière dans un recordset de type feuille de réponse dynamique qui répond aux critères spécifiés et le fait qui signalent l'enregistrement courant.|  
|[CDaoRecordset::FindFirst](../Topic/CDaoRecordset::FindFirst.md)|Recherche le premier enregistrement dans un recordset de type feuille de réponse dynamique ou de type instantané qui répond aux critères spécifiés et le fait qui signalent l'enregistrement courant.|  
|[CDaoRecordset::FindLast](../Topic/CDaoRecordset::FindLast.md)|Recherche le dernier enregistrement dans un recordset de type feuille de réponse dynamique ou de type instantané qui répond aux critères spécifiés et le fait qui signalent l'enregistrement courant.|  
|[CDaoRecordset::FindNext](../Topic/CDaoRecordset::FindNext.md)|Recherche le premier enregistrement dans un recordset de type feuille de réponse dynamique ou de type instantané qui répond aux critères spécifiés et le fait qui signalent l'enregistrement courant.|  
|[CDaoRecordset::FindPrev](../Topic/CDaoRecordset::FindPrev.md)|Localise l'enregistrement précédent dans un recordset de type feuille de réponse dynamique ou de type instantané qui répond aux critères spécifiés et le fait qui signalent l'enregistrement courant.|  
|[CDaoRecordset::GetAbsolutePosition](../Topic/CDaoRecordset::GetAbsolutePosition.md)|Retourne le nombre d'enregistrement de l'enregistrement actuel d'un objet recordset.|  
|[CDaoRecordset::GetBookmark](../Topic/CDaoRecordset::GetBookmark.md)|Retourne une valeur qui représente le signet sur un enregistrement.|  
|[CDaoRecordset::GetCacheSize](../Topic/CDaoRecordset::GetCacheSize.md)|Retourne une valeur qui spécifie le nombre d'enregistrements dans un recordset de type feuille de réponse dynamique contenant des données à mettre en cache localement d'une source de données ODBC.|  
|[CDaoRecordset::GetCacheStart](../Topic/CDaoRecordset::GetCacheStart.md)|Retourne une valeur qui spécifie le signet au premier enregistrement du recordset à mettre en cache.|  
|[CDaoRecordset::GetCurrentIndex](../Topic/CDaoRecordset::GetCurrentIndex.md)|Retourne `CString` contenant le nom de l'index derniers fichiers utilisés sur `CDaoRecordset`indexé et de type table.|  
|[CDaoRecordset::GetDateCreated](../Topic/CDaoRecordset::GetDateCreated.md)|Retourne la date et l'heure de la table de base sous\-jacente à un objet d' `CDaoRecordset` a été créée|  
|[CDaoRecordset::GetDateLastUpdated](../Topic/CDaoRecordset::GetDateLastUpdated.md)|Retourne la date et l'heure de la modification apportée la plus récente à la conception d'une table de base sous\-jacente à un objet d' `CDaoRecordset` .|  
|[CDaoRecordset::GetDefaultDBName](../Topic/CDaoRecordset::GetDefaultDBName.md)|Retourne le nom de la source de données par défaut.|  
|[CDaoRecordset::GetDefaultSQL](../Topic/CDaoRecordset::GetDefaultSQL.md)|Appelé pour obtenir la chaîne SQL par défaut de l'exécution.|  
|[CDaoRecordset::GetEditMode](../Topic/CDaoRecordset::GetEditMode.md)|Retourne une valeur qui indique l'état de la modification de l'enregistrement actuel.|  
|[CDaoRecordset::GetFieldCount](../Topic/CDaoRecordset::GetFieldCount.md)|Retourne une valeur qui représente le nombre de champs d'un recordset.|  
|[CDaoRecordset::GetFieldInfo](../Topic/CDaoRecordset::GetFieldInfo.md)|Retourne les types spécifiques d'informations sur les champs du recordset.|  
|[CDaoRecordset::GetFieldValue](../Topic/CDaoRecordset::GetFieldValue.md)|Retourne la valeur d'un champ d'un recordset.|  
|[CDaoRecordset::GetIndexCount](../Topic/CDaoRecordset::GetIndexCount.md)|Récupère le nombre d'index dans une table sous\-jacente à un recordset.|  
|[CDaoRecordset::GetIndexInfo](../Topic/CDaoRecordset::GetIndexInfo.md)|Retourne différents types d'informations à propos d'un index.|  
|[CDaoRecordset::GetLastModifiedBookmark](../Topic/CDaoRecordset::GetLastModifiedBookmark.md)|Utilisé pour déterminer l'enregistrement récemment ajouté ou mis à jour.|  
|[CDaoRecordset::GetLockingMode](../Topic/CDaoRecordset::GetLockingMode.md)|Retourne une valeur qui indique le type de verrou qui est appliquée lors de la modification.|  
|[CDaoRecordset::GetName](../Topic/CDaoRecordset::GetName.md)|Retourne `CString` contenant le nom du recordset.|  
|[CDaoRecordset::GetParamValue](../Topic/CDaoRecordset::GetParamValue.md)|Extrait la valeur actuelle du paramètre spécifié stocké dans l'objet sous\-jacent de DAOParameter.|  
|[CDaoRecordset::GetPercentPosition](../Topic/CDaoRecordset::GetPercentPosition.md)|Retourne la position de l'enregistrement en cours comme un pourcentage du nombre total des enregistrements.|  
|[CDaoRecordset::GetRecordCount](../Topic/CDaoRecordset::GetRecordCount.md)|Retourne le nombre d'enregistrements accessibles dans un objet recordset.|  
|[CDaoRecordset::GetSQL](../Topic/CDaoRecordset::GetSQL.md)|Obtient la chaîne SQL utilisée pour sélectionner des enregistrements du recordset.|  
|[CDaoRecordset::GetType](../Topic/CDaoRecordset::GetType.md)|Appelé pour déterminer le type d'un recordset : de type table, de type feuille de réponse dynamique, ou de type instantané.|  
|[CDaoRecordset::GetValidationRule](../Topic/CDaoRecordset::GetValidationRule.md)|Retourne `CString` contenant la valeur qui valide les données à mesure qu'elle est écrite dans un champ.|  
|[CDaoRecordset::GetValidationText](../Topic/CDaoRecordset::GetValidationText.md)|Extrait le texte affiché lorsqu'une règle de validation n'est pas satisfaite.|  
|[CDaoRecordset::IsBOF](../Topic/CDaoRecordset::IsBOF.md)|Retourne une valeur différente de zéro si le recordset a été positionné avant le premier enregistrement.  Il n'existe aucun enregistrement courant.|  
|[CDaoRecordset::IsDeleted](../Topic/CDaoRecordset::IsDeleted.md)|Retourne une valeur différente de zéro si le recordset est positionné sur un enregistrement supprimé.|  
|[CDaoRecordset::IsEOF](../Topic/CDaoRecordset::IsEOF.md)|Retourne une valeur différente de zéro si le recordset a été positionnée après le dernier enregistrement.  Il n'existe aucun enregistrement courant.|  
|[CDaoRecordset::IsFieldDirty](../Topic/CDaoRecordset::IsFieldDirty.md)|Retourne une valeur différente de zéro si le champ spécifié dans l'enregistrement en cours a été modifié.|  
|[CDaoRecordset::IsFieldNull](../Topic/CDaoRecordset::IsFieldNull.md)|Retourne une valeur différente de zéro si le champ spécifié dans l'enregistrement en cours est null \(n'ayant pas de valeur\).|  
|[CDaoRecordset::IsFieldNullable](../Topic/CDaoRecordset::IsFieldNullable.md)|Retourne une valeur différente de zéro si le champ spécifié dans l'enregistrement en cours peut avoir la valeur Null \(n'ayant pas de valeur\).|  
|[CDaoRecordset::IsOpen](../Topic/CDaoRecordset::IsOpen.md)|Retourne une valeur différente de zéro si [Ouvrez](../Topic/CDaoRecordset::Open.md) a été appelé précédemment.|  
|[CDaoRecordset::Move](../Topic/CDaoRecordset::Move.md)|Positionne le recordset en nombre d'enregistrements spécifié de l'enregistrement en cours dans l'un ou l'autre direction.|  
|[CDaoRecordset::MoveFirst](../Topic/CDaoRecordset::MoveFirst.md)|Positionne l'enregistrement actif sur le premier enregistrement du recordset.|  
|[CDaoRecordset::MoveLast](../Topic/CDaoRecordset::MoveLast.md)|Positionne l'enregistrement actif sur le dernier enregistrement du recordset.|  
|[CDaoRecordset::MoveNext](../Topic/CDaoRecordset::MoveNext.md)|Positionne l'enregistrement en cours sur l'enregistrement du recordset.|  
|[CDaoRecordset::MovePrev](../Topic/CDaoRecordset::MovePrev.md)|Positionne l'enregistrement en cours sur l'enregistrement précédent dans le recordset.|  
|[CDaoRecordset::Open](../Topic/CDaoRecordset::Open.md)|Crée un recordset d'une table, d'une feuille de réponse dynamique, ou d'un instantané.|  
|[CDaoRecordset::Requery](../Topic/CDaoRecordset::Requery.md)|Exécute la requête du recordset de nouveau pour actualiser les enregistrements sélectionnés.|  
|[CDaoRecordset::Seek](../Topic/CDaoRecordset::Seek.md)|Localise l'enregistrement dans un objet indexé de recordset de type table qui répond aux critères spécifiés pour l'index actuel et le fait qui signalent l'enregistrement courant.|  
|[CDaoRecordset::SetAbsolutePosition](../Topic/CDaoRecordset::SetAbsolutePosition.md)|Définit le nombre d'enregistrement de l'enregistrement actuel d'un objet recordset.|  
|[CDaoRecordset::SetBookmark](../Topic/CDaoRecordset::SetBookmark.md)|Positionne le recordset sur un enregistrement contenant le signet spécifié.|  
|[CDaoRecordset::SetCacheSize](../Topic/CDaoRecordset::SetCacheSize.md)|Définit une valeur qui spécifie le nombre d'enregistrements dans un recordset de type feuille de réponse dynamique contenant des données à mettre en cache localement d'une source de données ODBC.|  
|[CDaoRecordset::SetCacheStart](../Topic/CDaoRecordset::SetCacheStart.md)|Définit une valeur spécifiant le signet au premier enregistrement du recordset à mettre en cache.|  
|[CDaoRecordset::SetCurrentIndex](../Topic/CDaoRecordset::SetCurrentIndex.md)|Appelé pour définir un index sur un recordset de type table.|  
|[CDaoRecordset::SetFieldDirty](../Topic/CDaoRecordset::SetFieldDirty.md)|Marque le champ spécifié dans l'enregistrement en cours comme changé.|  
|[CDaoRecordset::SetFieldNull](../Topic/CDaoRecordset::SetFieldNull.md)|Définit la valeur du champ spécifié dans l'enregistrement actif à Null \(n'ayant pas de valeur\).|  
|[CDaoRecordset::SetFieldValue](../Topic/CDaoRecordset::SetFieldValue.md)|Définit la valeur d'un champ d'un recordset.|  
|[CDaoRecordset::SetFieldValueNull](../Topic/CDaoRecordset::SetFieldValueNull.md)|Définit la valeur d'un champ d'un recordset avec la valeur Null.  \(n'ayant pas de valeur\).|  
|[CDaoRecordset::SetLockingMode](../Topic/CDaoRecordset::SetLockingMode.md)|Définit une valeur indiquant le type de verrouillage pour mettre en œuvre pendant la modification.|  
|[CDaoRecordset::SetParamValue](../Topic/CDaoRecordset::SetParamValue.md)|Définit la valeur actuelle du paramètre spécifié stocké dans l'objet sous\-jacent de DAOParameter|  
|[CDaoRecordset::SetParamValueNull](../Topic/CDaoRecordset::SetParamValueNull.md)|Définit la valeur actuelle du paramètre spécifié avec la valeur Null \(n'ayant pas de valeur\).|  
|[CDaoRecordset::SetPercentPosition](../Topic/CDaoRecordset::SetPercentPosition.md)|Définit la position de l'enregistrement actif à un emplacement correspondant à un pourcentage du nombre total des enregistrements dans un recordset.|  
|[CDaoRecordset::Update](../Topic/CDaoRecordset::Update.md)|Termine une opération d' `AddNew` ou de **Modifier** en enregistrant les données nouvelles ou modifiées dans la source de données.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CDaoRecordset::m\_bCheckCacheForDirtyFields](../Topic/CDaoRecordset::m_bCheckCacheForDirtyFields.md)|Contient une balise qui indique si les champs sont automatiquement marquées comme changés.|  
|[CDaoRecordset::m\_nFields](../Topic/CDaoRecordset::m_nFields.md)|Contient le nombre de membres de données de type champ dans la classe de recordset et le nombre de colonnes sélectionnées par le recordset de la source de données.|  
|[CDaoRecordset::m\_nParams](../Topic/CDaoRecordset::m_nParams.md)|Contient le nombre de membres de données de type paramètre dans la classe de recordset \(le nombre de paramètres passés à la requête du recordset|  
|[CDaoRecordset::m\_pDAORecordset](../Topic/CDaoRecordset::m_pDAORecordset.md)|Pointeur vers l'interface DAO sous\-jacent à l'objet recordset.|  
|[CDaoRecordset::m\_pDatabase](../Topic/CDaoRecordset::m_pDatabase.md)|Base de données source de ce jeu de résultats.  Contient un pointeur vers un objet de [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) .|  
|[CDaoRecordset::m\_strFilter](../Topic/CDaoRecordset::m_strFilter.md)|Contient une chaîne utilisée pour construire une instruction SQL **WHERE** .|  
|[CDaoRecordset::m\_strSort](../Topic/CDaoRecordset::m_strSort.md)|Contient une chaîne utilisée pour construire une instruction SQL **ORDER BY** .|  
  
## Notes  
 Appelés « recordsets, » les objets d' `CDaoRecordset` sont disponibles dans les trois formes suivantes :  
  
-   Les recordsets de type table représentent une table de base que vous pouvez utiliser pour examiner, ajouter, modifier, ou supprimer des enregistrements d'une table de base de données unique.  
  
-   Les recordsets de type feuille de réponse dynamique sont le résultat d'une requête qui peut avoir des enregistrements modifiable.  Les recordsets sont un ensemble d'enregistrements que vous pouvez utiliser pour examiner, ajouter, modifier, ou supprimer des enregistrements d'une table ou des tables de base de données sous\-jacents.  Les recordsets de type feuille de réponse dynamique peuvent contenir des champs d'une ou de plusieurs tables dans une base de données.  
  
-   Les recordsets de type instantané sont une copie statique d'un ensemble d'enregistrements que vous pouvez utiliser pour rechercher des données ou créer des rapports.  Les recordsets peuvent contenir des champs d'une ou de plusieurs tables dans une base de données mais ne peuvent pas être mis à jour.  
  
 Chaque forme de recordset représente un ensemble d'enregistrements résolus au moment où le recordset est ouvert.  Lorsque vous accédez à un enregistrement dans un recordset de type table ou un recordset de type feuille de réponse dynamique, elle reflète les modifications apportées à l'enregistrement après que le recordset est ouvert, par d'autres utilisateurs ou par d'autres recordsets dans votre application.  \(Le recordset de type instantané d'Un ne peut pas être mis à jour.\) Vous pouvez utiliser `CDaoRecordset` directement ou dériver une classe de recordset spécifique à l'application d' `CDaoRecordset`.  Ensuite, vous pouvez :  
  
-   Parcourir les enregistrements.  
  
-   Définissez un index et trouver rapidement des enregistrements à l'aide de [accès](../Topic/CDaoRecordset::Seek.md) \(recordsets de type table uniquement\).  
  
-   Recherchez les enregistrements en fonction d'une comparaison de chaînes : « \< », « \<\= », « \= », « \>\= », ou « \> » \(recordsets de type feuille de réponse dynamique et de type instantané\).  
  
-   Mettre à jour des enregistrements et spécifiez à jour le mode de verrouillage \(sauf les recordsets de type instantané\).  
  
-   Filtrez le recordset pour limiter les enregistrements il choisit parmi celles disponibles dans la source de données.  
  
-   Trier le recordset.  
  
-   Paramétrer le recordset pour personnaliser la sélection des informations inconnues qu'au moment de l'exécution.  
  
 Classez le fournit d' `CDaoRecordset` une interface semblable à celle de la classe `CRecordset`.  La principale différence est ces données d'accès d' `CDaoRecordset` de classe via objet d'accès aux données \(DAO\) avec OLE.  Classez les accès d' `CRecordset` le système de gestion de base de données via \(Open Database Connectivity\) et un pilote ODBC pour ce système de gestion de base de données.  
  
> [!NOTE]
>  Les classes de bases de données DAO sont séparées des classes de base de données MFC basée sur \(Open Database Connectivity\).  Tous les noms de classes de bases de données DAO ont le préfixe « CDao ».  Vous pouvez encore accéder aux sources de données ODBC avec les classes DAO ; les classes DAO offrent généralement des fonctionnalités améliorées car elles sont spécifiques au moteur de base de données Microsoft Jet.  
  
 Vous pouvez utiliser `CDaoRecordset` directement ou dériver une classe d' `CDaoRecordset`.  Pour utiliser une classe de recordset dans les deux cas, ouvrir une base de données et construire un objet recordset, en passant le constructeur un pointeur vers l'objet d' `CDaoDatabase` .  Vous pouvez également construire un objet d' `CDaoRecordset` et laissez MFC créer un objet temporaire d' `CDaoDatabase` pour vous.  Appelez la fonction membre d' [Ouvrez](../Topic/CDaoRecordset::Open.md) du recordset, indiquant si l'objet est un recordset de type table, un recordset de type feuille de réponse dynamique, ou un recordset de type instantané.  Appeler **Ouvrir** sélectionne des données de la base de données et extrait le premier enregistrement.  
  
 Utilisez les fonctions membres et les données membres de l'objet au défilement des enregistrements et traitez\- les.  Les opérations disponibles dépendent de si l'objet est un recordset de type table, un recordset de type feuille de réponse dynamique, ou un recordset de type instantané, et s'il est modifiables ou en lecture seule \(cela dépend de la capacité de la base de données ou de la source de données ODBC \(Open Database Connectivity\).  Pour actualiser les enregistrements qui ont peut\-être été modifiés ou ajoutés comme l'appel de **Ouvrir** , appelez la fonction membre d' [Actualiser](../Topic/CDaoRecordset::Requery.md) de l'objet.  Appelez la fonction membre de **Fermer** de l'objet et détruisez l'objet lorsque vous avez terminé avec elle.  
  
 Processus DFX d' utilisation d'`CDaoRecordset` \(DFX\) pour prendre en charge la lecture et mettre à jour les champs d'enregistrement par les membres de type sécurisé C\+\+ de votre `CDaoRecordset` ou d' `CDaoRecordset`classe dérivée.  Vous pouvez également implémenter la liaison dynamique des colonnes dans une base de données sans utiliser le mécanisme DFX à l'aide de [GetFieldValue](../Topic/CDaoRecordset::GetFieldValue.md) et [SetFieldValue](../Topic/CDaoRecordset::SetFieldValue.md).  
  
 Pour des informations connexes, consultez la rubrique « objet recordset » dans l'aide de DAO.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoRecordset`  
  
## Configuration requise  
 **Header:** afxdao.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDaoTableDef Class](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoDatabase Class](../../mfc/reference/cdaodatabase-class.md)   
 [CDaoQueryDef Class](../../mfc/reference/cdaoquerydef-class.md)