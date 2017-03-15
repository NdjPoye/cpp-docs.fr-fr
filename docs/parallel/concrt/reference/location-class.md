---
title: location, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::location
dev_langs:
- C++
helpviewer_keywords:
- location class
ms.assetid: c3289f51-5bf1-4dff-a18d-d0dab8e5d9c7
caps.latest.revision: 10
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
ms.openlocfilehash: 1a404f44600addcbf332fabcfc19a7b48dab0c81
ms.lasthandoff: 02/24/2017

---
# <a name="location-class"></a>location, classe
Abstraction d'un emplacement physique sur du matériel.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class location;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[emplacement du constructeur](#ctor)|Surchargé. Construit un objet `location`.|  
|[~ location, destructeur](#dtor)|Détruit un objet `location`.|  
  
### <a name="public-methods"></a>Méthodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Méthode actuelle](#current)|Retourne un `location` objet représentant le lieu plus spécifique que le thread appelant s’exécute.|  
|[from_numa_node (méthode)](#from_numa_node)|Retourne un `location` objet qui représente un nœud NUMA donné.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[opérateur ! =, opérateur](#operator_neq)|Détermine si deux `location` objets représentent l’autre emplacement.|  
|[opérateur =, opérateur](#operator_eq)|Assigne le contenu d’un autre `location` objet à celui-ci.|  
|[opérateur ==, opérateur](#operator_eq_eq)|Détermine si deux `location` objets représentent le même emplacement.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `location`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namedtora-location"></a><a name="dtor"></a>~ emplacement 

 Détruit un objet `location`.  
  
```
~location();
```  
  
##  <a name="a-namecurrenta-current"></a><a name="current"></a>en cours 

 Retourne un `location` objet représentant le lieu plus spécifique que le thread appelant s’exécute.  
  
```
static location __cdecl current();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un emplacement qui représente le lieu plus spécifique que le thread appelant s’exécute.  
  
##  <a name="a-namefromnumanodea-fromnumanode"></a><a name="from_numa_node"></a>from_numa_node 

 Retourne un `location` objet qui représente un nœud NUMA donné.  
  
```
static location __cdecl from_numa_node(unsigned short _NumaNodeNumber);
```  
  
### <a name="parameters"></a>Paramètres  
 `_NumaNodeNumber`  
 Le nombre de nœuds NUMA pour construire un emplacement pour.  
  
### <a name="return-value"></a>Valeur de retour  
 Un emplacement qui représente le nœud NUMA spécifié par le `_NumaNodeNumber` paramètre.  
  
##  <a name="a-namectora-location"></a><a name="ctor"></a>emplacement 

 Construit un objet `location`.  
  
```
location();

location(
    const location& _Src);

location(
    T _LocationType,
    unsigned int _Id,
    unsigned int _BindingId = 0,
    _Inout_opt_ void* _PBinding = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Src`  
 `_LocationType`  
 `_Id`  
 `_BindingId`  
 `_PBinding`  
  
### <a name="remarks"></a>Remarques  
 Un emplacement par défaut construit représente le système dans son ensemble.  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>opérateur ! = 

 Détermine si deux `location` objets représentent l’autre emplacement.  
  
```
bool operator!= (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rhs`  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si les deux emplacements sont différents, `false` dans le cas contraire.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>opérateur = 

 Assigne le contenu d’un autre `location` objet à celui-ci.  
  
```
location& operator= (const location& _Rhs);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rhs`  
 Objet `location` source.  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>opérateur == 

 Détermine si deux `location` objets représentent le même emplacement.  
  
```
bool operator== (const location& _Rhs) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rhs`  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si les deux emplacements sont identiques, et `false` dans le cas contraire.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

