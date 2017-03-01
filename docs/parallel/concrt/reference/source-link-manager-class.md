---
title: source_link_manager, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::source_link_manager
dev_langs:
- C++
helpviewer_keywords:
- source_link_manager class
ms.assetid: 287487cf-e0fe-4c35-aa3c-24f081d1ddae
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: b9323da4d2ccefe09ba38df088e546828d41f2ee
ms.lasthandoff: 02/24/2017

---
# <a name="sourcelinkmanager-class"></a>source_link_manager, classe
L'objet `source_link_manager` gère les liens réseau des blocs de messagerie avec les blocs `ISource`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class _LinkRegistry>
class source_link_manager;
```  
  
#### <a name="parameters"></a>Paramètres  
 `_LinkRegistry`  
 Registre de liens réseau.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`const_pointer`|Type qui fournit un pointeur vers un `const` élément dans une `source_link_manager` objet.|  
|`const_reference`|Type qui fournit une référence à un `const` élément stocké dans un `source_link_manager` objet pour la lecture et exécution d’opérations const.|  
|`iterator`|Type qui fournit un itérateur qui peut lire ou modifier tout élément dans le `source_link_manager` objet.|  
|`type`|Le type de Registre de liens géré par la `source_link_manager` objet.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[source_link_manager, constructeur](#ctor)|Construit un objet `source_link_manager`.|  
|[~ source_link_manager, destructeur](#dtor)|Détruit le `source_link_manager` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Add, méthode](#add)|Ajoute un lien source vers le `source_link_manager` objet.|  
|[Begin (méthode)](#begin)|Retourne un itérateur au premier élément dans le `source_link_manager` objet.|  
|[Contains (méthode)](#contains)|Recherche le `network_link_registry` dans cette `source_link_manager` objet un bloc spécifié.|  
|[Count (méthode)](#count)|Compte le nombre de blocs liés dans le `source_link_manager` objet.|  
|[référence (méthode)](#reference)|Acquiert une référence sur le `source_link_manager` objet.|  
|[register_target_block (méthode)](#register_target_block)|Inscrit le bloc cible qui conserve ce `source_link_manager` objet.|  
|[Release (méthode)](#release)|Libère la référence sur le `source_link_manager` objet.|  
|[Remove (méthode)](#remove)|Supprime un lien à partir de la `source_link_manager` objet.|  
|[set_bound (méthode)](#set_bound)|Définit le nombre maximal de liens source qui peuvent être ajoutés à ce `source_link_manager` objet.|  
  
## <a name="remarks"></a>Notes  
 Actuellement, les blocs de code source ont un décompte. C’est un wrapper sur un `network_link_registry` qui autorise l’accès simultané aux liens et fournit la capacité de référencer les liens via des rappels. Blocs de messages ( `target_block`s ou `propagator_block`s) doivent utiliser cette classe pour leurs liens source.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `source_link_manager`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-nameadda-add"></a><a name="add"></a>ajouter 

 Ajoute un lien source vers le `source_link_manager` objet.  
  
```
void add(_EType _Link);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Link`  
 Pointeur vers un bloc à ajouter.  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>commencer 

 Retourne un itérateur au premier élément dans le `source_link_manager` objet.  
  
```
iterator begin();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur qui traite le premier élément de la `source_link_manager` objet.  
  
### <a name="remarks"></a>Notes  
 L’état de fin de l’itérateur est indiqué par une `NULL` lien.  
  
##  <a name="a-namecontainsa-contains"></a><a name="contains"></a>contient 

 Recherche le `network_link_registry` dans cette `source_link_manager` objet un bloc spécifié.  
  
```
bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Link`  
 Pointeur vers un bloc qui doit être recherché dans le `source_link_manager` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le bloc spécifié a été trouvé, `false` dans le cas contraire.  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>nombre 

 Compte le nombre de blocs liés dans le `source_link_manager` objet.  
  
```
size_t count();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de blocs liés dans le `source_link_manager` objet.  
  
##  <a name="a-namereferencea-reference"></a><a name="reference"></a>référence 

 Acquiert une référence sur le `source_link_manager` objet.  
  
```
void reference();
```  
  
##  <a name="a-nameregistertargetblocka-registertargetblock"></a><a name="register_target_block"></a>register_target_block 

 Inscrit le bloc cible qui conserve ce `source_link_manager` objet.  
  
```
void register_target_block(_Inout_ ITarget<typename _Block::source_type>* _PTarget);
```  
  
### <a name="parameters"></a>Paramètres  
 `_PTarget`  
 Le bloc cible contenant cet `source_link_manager` objet.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>version 

 Libère la référence sur le `source_link_manager` objet.  
  
```
void release();
```  
  
##  <a name="a-nameremovea-remove"></a><a name="remove"></a>supprimer 

 Supprime un lien à partir de la `source_link_manager` objet.  
  
```
bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Link`  
 Pointeur vers un bloc à supprimer, si trouvé.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le lien a été trouvé et supprimé, `false` dans le cas contraire.  
  
##  <a name="a-namesetbounda-setbound"></a><a name="set_bound"></a>set_bound 

 Définit le nombre maximal de liens source qui peuvent être ajoutés à ce `source_link_manager` objet.  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MaxLinks`  
 Le nombre maximal de liens.  
  
##  <a name="a-namectora-sourcelinkmanager"></a><a name="ctor"></a>source_link_manager 

 Construit un objet `source_link_manager`.  
  
```
source_link_manager();
```  
  
##  <a name="a-namedtora-sourcelinkmanager"></a><a name="dtor"></a>~ source_link_manager 

 Détruit le `source_link_manager` objet.  
  
```
~source_link_manager();
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [single_link_registry, classe](single-link-registry-class.md)   
 [multi_link_registry, classe](multi-link-registry-class.md)

