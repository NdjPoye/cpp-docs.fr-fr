---
title: single_link_registry, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::single_link_registry
dev_langs:
- C++
helpviewer_keywords:
- single_link_registry class
ms.assetid: 09540a4e-c34e-4ff9-af49-21b8612b6ab3
caps.latest.revision: 19
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
ms.openlocfilehash: 3f4719881fac882611f68b36d410c0611f99ba01
ms.lasthandoff: 02/24/2017

---
# <a name="singlelinkregistry-class"></a>single_link_registry, classe
L'objet `single_link_registry` est un `network_link_registry` qui gère uniquement un seul bloc source ou cible.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class _Block>
class single_link_registry : public network_link_registry<_Block>;
```  
  
#### <a name="parameters"></a>Paramètres  
 `_Block`  
 Le bloc type de données qui est stocké dans le `single_link_registry` objet.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[single_link_registry, constructeur](#ctor)|Construit un objet `single_link_registry`.|  
|[~ single_link_registry, destructeur](#dtor)|Détruit le `single_link_registry` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Add, méthode](#add)|Ajoute un lien vers le `single_link_registry` objet. (Substitue [network_link_registry::add](network-link-registry-class.md#add).)|  
|[Begin (méthode)](#begin)|Retourne un itérateur au premier élément dans le `single_link_registry` objet. (Substitue [network_link_registry::begin](network-link-registry-class.md#begin).)|  
|[Contains (méthode)](#contains)|Recherche le `single_link_registry` objet un bloc spécifié. (Substitue [network_link_registry::contains](network-link-registry-class.md#contains).)|  
|[Count (méthode)](#count)|Compte le nombre d’éléments dans le `single_link_registry` objet. (Substitue [network_link_registry::count](network-link-registry-class.md#count).)|  
|[Remove (méthode)](#remove)|Supprime un lien à partir de la `single_link_registry` objet. (Substitue [network_link_registry::remove](network-link-registry-class.md#remove).)|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [network_link_registry](network-link-registry-class.md)  
  
 `single_link_registry`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-nameadda-add"></a><a name="add"></a>ajouter 

 Ajoute un lien vers le `single_link_registry` objet.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Link`  
 Pointeur vers un bloc à ajouter.  
  
### <a name="remarks"></a>Remarques  
 La méthode lève un [invalid_link_target](invalid-link-target-class.md) exception s’il existe déjà un lien dans ce Registre.  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>commencer 

 Retourne un itérateur au premier élément dans le `single_link_registry` objet.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur qui traite le premier élément de la `single_link_registry` objet.  
  
### <a name="remarks"></a>Remarques  
 L’état de fin est indiqué par une `NULL` lien.  
  
##  <a name="a-namecontainsa-contains"></a><a name="contains"></a>contient 

 Recherche le `single_link_registry` objet un bloc spécifié.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Link`  
 Pointeur vers un bloc qui doit être recherché dans le `single_link_registry` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le lien a été trouvé, `false` dans le cas contraire.  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>nombre 

 Compte le nombre d’éléments dans le `single_link_registry` objet.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’éléments dans le `single_link_registry` objet.  
  
##  <a name="a-nameremovea-remove"></a><a name="remove"></a>supprimer 

 Supprime un lien à partir de la `single_link_registry` objet.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Link`  
 Pointeur vers un bloc à supprimer, si trouvé.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le lien a été trouvé et supprimé, `false` dans le cas contraire.  
  
##  <a name="a-namectora-singlelinkregistry"></a><a name="ctor"></a>single_link_registry 

 Construit un objet `single_link_registry`.  
  
```
single_link_registry();
```  
  
##  <a name="a-namedtora-singlelinkregistry"></a><a name="dtor"></a>~ single_link_registry 

 Détruit le `single_link_registry` objet.  
  
```
virtual ~single_link_registry();
```  
  
### <a name="remarks"></a>Remarques  
 La méthode lève un [invalid_operation](invalid-operation-class.md) exception si elle est appelée avant que le lien est supprimé.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [multi_link_registry, classe](multi-link-registry-class.md)

