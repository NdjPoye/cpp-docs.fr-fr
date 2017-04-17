---
title: multi_link_registry, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- multi_link_registry
- AGENTS/concurrency::multi_link_registry
- AGENTS/concurrency::multi_link_registry::multi_link_registry
- AGENTS/concurrency::multi_link_registry::add
- AGENTS/concurrency::multi_link_registry::begin
- AGENTS/concurrency::multi_link_registry::contains
- AGENTS/concurrency::multi_link_registry::count
- AGENTS/concurrency::multi_link_registry::remove
- AGENTS/concurrency::multi_link_registry::set_bound
dev_langs:
- C++
helpviewer_keywords:
- multi_link_registry class
ms.assetid: b2aa73a8-e8a6-4255-b117-d07530c328b2
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: b52ee20ed16a4ce8d0b9f11b6acf25112464b49b
ms.lasthandoff: 03/17/2017

---
# <a name="multilinkregistry-class"></a>multi_link_registry, classe
L'objet `multi_link_registry` est un `network_link_registry` qui gère plusieurs blocs sources ou plusieurs blocs cibles.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class _Block>
class multi_link_registry : public network_link_registry<_Block>;
```  
  
#### <a name="parameters"></a>Paramètres  
 `_Block`  
 Le bloc type de données qui est stocké dans le `multi_link_registry` objet.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[multi_link_registry](#ctor)|Construit un objet `multi_link_registry`.|  
|[~ multi_link_registry, destructeur](#dtor)|Détruit le `multi_link_registry` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[add](#add)|Ajoute un lien vers le `multi_link_registry` objet. (Substitue [network_link_registry::add](network-link-registry-class.md#add).)|  
|[begin](#begin)|Retourne un itérateur au premier élément dans le `multi_link_registry` objet. (Substitue [network_link_registry::begin](network-link-registry-class.md#begin).)|  
|[contient](#contains)|Recherche le `multi_link_registry` objet un bloc spécifié. (Substitue [network_link_registry::contains](network-link-registry-class.md#contains).)|  
|[count](#count)|Compte le nombre d’éléments dans le `multi_link_registry` objet. (Substitue [network_link_registry::count](network-link-registry-class.md#count).)|  
|[remove](#remove)|Supprime un lien à partir de la `multi_link_registry` objet. (Substitue [network_link_registry::remove](network-link-registry-class.md#remove).)|  
|[set_bound](#set_bound)|Définit une limite supérieure sur le nombre de liens qui les `multi_link_registry` objet peut contenir.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [network_link_registry](network-link-registry-class.md)  
  
 `multi_link_registry`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="add"></a>ajouter 

 Ajoute un lien vers le `multi_link_registry` objet.  
  
```
virtual void add(_EType _Link);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Link`  
 Pointeur vers un bloc à ajouter.  
  
### <a name="remarks"></a>Remarques  
 La méthode lève un [invalid_link_target](invalid-link-target-class.md) exception si le lien est déjà présent dans le Registre, ou si une limite a déjà été définie avec la `set_bound` fonction et un lien a été supprimé depuis.  
  
##  <a name="begin"></a>commencer 

 Retourne un itérateur au premier élément dans le `multi_link_registry` objet.  
  
```
virtual iterator begin();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur qui traite le premier élément de la `multi_link_registry` objet.  
  
### <a name="remarks"></a>Remarques  
 L’état de fin est indiqué par une `NULL` lien.  
  
##  <a name="contains"></a>contient 

 Recherche le `multi_link_registry` objet un bloc spécifié.  
  
```
virtual bool contains(_EType _Link);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Link`  
 Pointeur vers un bloc qui doit être recherché dans le `multi_link_registry` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le bloc spécifié a été trouvé, `false` dans le cas contraire.  
  
##  <a name="count"></a>nombre 

 Compte le nombre d’éléments dans le `multi_link_registry` objet.  
  
```
virtual size_t count();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’éléments dans le `multi_link_registry` objet.  
  
##  <a name="ctor"></a>multi_link_registry 

 Construit un objet `multi_link_registry`.  
  
```
multi_link_registry();
```  
  
##  <a name="dtor"></a>~ multi_link_registry 

 Détruit le `multi_link_registry` objet.  
  
```
virtual ~multi_link_registry();
```  
  
### <a name="remarks"></a>Remarques  
 La méthode lève un [invalid_operation](invalid-operation-class.md) exception si elle est appelée avant que tous les liens sont supprimés.  
  
##  <a name="remove"></a>supprimer 

 Supprime un lien à partir de la `multi_link_registry` objet.  
  
```
virtual bool remove(_EType _Link);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Link`  
 Pointeur vers un bloc à supprimer, si trouvé.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le lien a été trouvé et supprimé, `false` dans le cas contraire.  
  
##  <a name="set_bound"></a>set_bound 

 Définit une limite supérieure sur le nombre de liens qui les `multi_link_registry` objet peut contenir.  
  
```
void set_bound(size_t _MaxLinks);
```  
  
### <a name="parameters"></a>Paramètres  
 `_MaxLinks`  
 Le nombre maximal de liens qui les `multi_link_registry` objet peut contenir.  
  
### <a name="remarks"></a>Remarques  
 Une fois une limite définie, une entrée entraîne la `multi_link_registry` objet passe à un état immuable où autre appel aux `add` lèvera une `invalid_link_target` exception.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [single_link_registry, classe](single-link-registry-class.md)
