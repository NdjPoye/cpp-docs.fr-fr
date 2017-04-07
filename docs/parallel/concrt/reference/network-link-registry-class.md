---
title: network_link_registry, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- network_link_registry
- AGENTS/concurrency::network_link_registry
- AGENTS/concurrency::network_link_registry::add
- AGENTS/concurrency::network_link_registry::begin
- AGENTS/concurrency::network_link_registry::contains
- AGENTS/concurrency::network_link_registry::count
- AGENTS/concurrency::network_link_registry::remove
dev_langs:
- C++
helpviewer_keywords:
- network_link_registry class
ms.assetid: 3e7b4097-09f1-4252-964e-b15b8f7f7fc6
caps.latest.revision: 20
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
ms.openlocfilehash: 28c13f1e2bf80624da3a7aba441944c051790d27
ms.lasthandoff: 03/17/2017

---
# <a name="networklinkregistry-class"></a>network_link_registry, classe
La classe de base abstraite `network_link_registry` gère les liens entre les blocs sources et cibles.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class _Block>
class network_link_registry;
```  
  
#### <a name="parameters"></a>Paramètres  
 `_Block`  
 Le bloc type de données qui est stocké dans le `network_link_registry`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`const_pointer`|Type qui fournit un pointeur vers un `const` élément dans une `network_link_registry` objet.|  
|`const_reference`|Type qui fournit une référence à un `const` élément stocké dans un `network_link_registry` objet pour la lecture et exécution d’opérations const.|  
|`iterator`|Type qui fournit un itérateur qui peut lire ou modifier tout élément dans un `network_link_registry` objet.|  
|`type`|Un type qui représente le type de bloc stocké dans le `network_link_registry` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[add](#add)|En cas de substitution dans une classe dérivée, ajoute un lien vers le `network_link_registry` objet.|  
|[begin](#begin)|En cas de substitution dans une classe dérivée, retourne un itérateur au premier élément dans le `network_link_registry` objet.|  
|[contient](#contains)|En cas de substitution dans une classe dérivée, recherche les `network_link_registry` objet un bloc spécifié.|  
|[count](#count)|En cas de substitution dans une classe dérivée, retourne le nombre d’éléments dans le `network_link_registry` objet.|  
|[remove](#remove)|En cas de substitution dans une classe dérivée, supprime un bloc spécifié de le `network_link_registry` objet.|  
  
## <a name="remarks"></a>Notes  
 Le `network link registry` n’est pas sécurisé pour l’accès simultané.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `network_link_registry`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** agents.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="add"></a>ajouter 

 En cas de substitution dans une classe dérivée, ajoute un lien vers le `network_link_registry` objet.  
  
```
virtual void add(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Link`  
 Pointeur vers un bloc à ajouter.  
  
##  <a name="begin"></a>commencer 

 En cas de substitution dans une classe dérivée, retourne un itérateur au premier élément dans le `network_link_registry` objet.  
  
```
virtual iterator begin() = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur qui traite le premier élément de la `network_link_registry` objet.  
  
### <a name="remarks"></a>Notes  
 L’état de fin de l’itérateur est indiqué par une `NULL` lien.  
  
##  <a name="contains"></a>contient 

 En cas de substitution dans une classe dérivée, recherche les `network_link_registry` objet un bloc spécifié.  
  
```
virtual bool contains(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Link`  
 Un pointeur vers un bloc qui est recherché dans le `network_link_registry` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le bloc a été trouvé, `false` dans le cas contraire.  
  
##  <a name="count"></a>nombre 

 En cas de substitution dans une classe dérivée, retourne le nombre d’éléments dans le `network_link_registry` objet.  
  
```
virtual size_t count() = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’éléments dans le `network_link_registry` objet.  
  
##  <a name="remove"></a>supprimer 

 En cas de substitution dans une classe dérivée, supprime un bloc spécifié de le `network_link_registry` objet.  
  
```
virtual bool remove(_EType _Link) = 0;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Link`  
 Pointeur vers un bloc à supprimer, si trouvé.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le lien a été trouvé et supprimé, `false` dans le cas contraire.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [single_link_registry, classe](single-link-registry-class.md)   
 [multi_link_registry, classe](multi-link-registry-class.md)

