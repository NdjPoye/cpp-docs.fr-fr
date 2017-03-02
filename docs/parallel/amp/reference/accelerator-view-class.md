---
title: accelerator_view, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::accelerator_view
dev_langs:
- C++
helpviewer_keywords:
- accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
caps.latest.revision: 18
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
ms.openlocfilehash: 78569f1ff21af3ed05cb908a851f0fe05d5d271a
ms.lasthandoff: 02/24/2017

---
# <a name="acceleratorview-class"></a>accelerator_view, classe
Représente une abstraction de périphérique virtuel sur un accélérateur de parallèle de données C++ AMP.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
class accelerator_view;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[accelerator_view, constructeur](#ctor)|Initialise une nouvelle instance de la classe `accelerator_view`.|  
|[~ accelerator_view, destructeur](#dtor)|Détruit le `accelerator_view` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[create_marker (méthode)](#create_marker)|Retourne un futur pour effectuer le suivi de l’achèvement de toutes les commandes envoyées jusqu'à présent à ce `accelerator_view` objet.|  
|[Flush (méthode)](#flush)|Envoie toutes les commandes en attente en attente pour le `accelerator_view` objet à l’accélérateur pour l’exécution.|  
|[get_accelerator (méthode)](#get_accelerator)|Retourne l'objet `accelerator` de l'objet `accelerator_view`.|  
|[get_is_auto_selection (méthode)](#get_is_auto_selection)|Retourne une valeur booléenne qui indique si le runtime sélectionne automatiquement un accélérateur approprié lors de la `accelerator_view` objet est passé à une [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|  
|[get_is_debug (méthode)](#get_is_debug)|Retourne une valeur booléenne qui indique si le `accelerator_view` objet a la couche de débogage est activée pour le rapport d’erreur étendu.|  
|[get_queuing_mode (méthode)](#get_queuing_mode)|Retourne le mode file d’attente pour le `accelerator_view` objet.|  
|[get_version (méthode)](#get_version)|Retourne la version de la `accelerator_view`.|  
|[Wait (méthode)](#wait)|Attend que toutes les commandes envoyées à la `accelerator_view` objet se termine.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[opérateur ! =, opérateur](#operator_neq)|Compare cette `accelerator_view` objet avec une autre et retourne `false` si elles sont identiques ; sinon, retourne `true`.|  
|[opérateur =, opérateur](#operator_eq)|Copie le contenu de l’objet `accelerator_view` objet dans celui-ci.|  
|[opérateur ==, opérateur](#operator_eq_eq)|Compare cette `accelerator_view` objet avec une autre et retourne `true` si elles sont identiques ; sinon, retourne `false`.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[accélérateur de membre de données](#accelerator)|Obtient l'objet `accelerator` pour l'objet `accelerator_view`.|  
|[is_auto_selection (donnée membre)](#is_auto_selection)|Obtient une valeur booléenne qui indique si le runtime sélectionne automatiquement un accélérateur approprié lors de la `accelerator_view` objet est passé à une [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|  
|[is_debug (donnée membre)](#is_debug)|Obtient une valeur booléenne qui indique si le `accelerator_view` objet a la couche de débogage est activée pour le rapport d’erreur étendu.|  
|[queuing_mode (donnée membre)](#queuing_mode)|Obtient le mode de file d’attente pour le `accelerator_view` objet.|  
|[Membre de données de version](#version)|Obtient la version de l’accélérateur.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `accelerator_view`  
  
### <a name="remarks"></a>Remarques  
 Un `accelerator_view` objet représente une vue logique et isolée d’un accélérateur. Une unité de calcul physique unique peut avoir de nombreux logique et isolé `accelerator_view` objets. Chaque accélérateur a une valeur par défaut `accelerator_view` objet. Autres `accelerator_view` objets peuvent être créés.  
  
 Périphériques physiques peuvent être partagés entre plusieurs threads clients. Threads clients peuvent utiliser de manière coopérative la même `accelerator_view` objet d’un accélérateur, ou chaque client peut communiquer avec un périphérique de calcul via une indépendante `accelerator_view` objet pour l’isolement d’autres threads du client.  
  
 Un `accelerator_view` objet peut avoir une des deux [énumération queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) États. Si le mode de file d’attente est `immediate`, telles que les commandes `copy` et `parallel_for_each` sont envoyées au périphérique accélérateur correspondant dès qu’elles sont retournées à l’appelant. Si le mode de file d’attente est `deferred`, ces commandes sont la file d’attente dans une file d’attente de commande correspond à la `accelerator_view` objet. Commandes ne sont pas réellement envoyées à l’appareil jusqu'à ce que `flush()` est appelée.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amprt.h  
  
 **Espace de noms :** Concurrency  

## <a name="a-nameacceleratora-accelerator"></a><a name="accelerator"></a>accélérateur 

Obtient l’objet de l’accélérateur pour l’objet accelerator_view.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;  
```  
  
## <a name="a-namectora-acceleratorview"></a><a name="ctor"></a>accelerator_view 

Initialise une nouvelle instance de la classe accelerator_view en copiant une existante `accelerator_view` objet.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
accelerator_view( const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator_view` objet à copier.  
  
## <a name="a-nameacceleratorviewcreatemarkera-createmarker"></a><a name="accelerator_view__create_marker"></a>create_marker 

Retourne un futur pour effectuer le suivi de l’achèvement de toutes les commandes envoyées jusqu'à présent à ce `accelerator_view` objet.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
concurrency::completion_future create_marker();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un futur pour effectuer le suivi de l’achèvement de toutes les commandes envoyées jusqu'à présent à ce `accelerator_view` objet.  
  
## <a name="a-nameflusha-flush"></a><a name="flush"></a>Vider 

Envoie que toutes les commandes en attente en attente pour l’objet accelerator_view pour l’accélérateur pour l’exécution.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
void flush();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `void`.  

## <a name="a-nameacceleratorviewgetacceleratora-getaccelerator"></a><a name="accelerator_view__get_accelerator"></a>get_accelerator 

Retourne l’objet de l’accélérateur pour l’objet accelerator_view.
### <a name="syntax"></a>Syntaxe
```
accelerator get_accelerator() const;
```
### <a name="return-value"></a>Valeur de retour
L’objet de l’accélérateur pour l’objet accelerator_view.

## <a name="a-nameacceleratorviewgetisautoselectiona-getisautoselection"></a><a name="accelerator_view__get_is_auto_selection"></a>get_is_auto_selection 

Retourne une valeur booléenne qui indique si le runtime sélectionne automatiquement un accélérateur approprié lorsque l’accelerator_view est transmis à un [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).  
  
### <a name="syntax"></a>Syntaxe  
  
```  
bool get_is_auto_selection() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le runtime va sélectionner automatiquement un accélérateur approprié ; dans le cas contraire, `false`.  
  
## <a name="a-nameacceleratorviewgetisdebuga-getisdebug"></a><a name="accelerator_view__get_is_debug"></a>get_is_debug 

Retourne une valeur booléenne qui indique si l’objet accelerator_view a la couche de débogage est activée pour le rapport d’erreur étendu.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
bool get_is_debug() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur booléenne qui indique si le `accelerator_view` objet a la couche de débogage est activée pour le rapport d’erreur étendu.  

## <a name="a-nameacceleratorviewgetqueuingmodea-getqueuingmode"></a><a name="accelerator_view__get_queuing_mode"></a>get_queuing_mode 

Renvoie le mode file d’attente pour l’objet accelerator_view.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
queuing_mode get_queuing_mode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le mode de file d’attente pour le `accelerator_view` objet.  
  
## <a name="a-nameacceleratorviewgetversiona-getversion"></a><a name="accelerator_view__get_version"></a>get_version 

Retourne la version de l’accelerator_view.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
unsigned int get_version() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La version de la `accelerator_view`.  
  
## <a name="a-nameacceleratorviewisautoselectiona-isautoselection"></a><a name="accelerator_view__is_auto_selection"></a>is_auto_selection 

Obtient une valeur booléenne qui indique si le runtime sélectionne automatiquement un accélérateur approprié lorsque l’accelerator_view est transmis à un [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).  
  
### <a name="syntax"></a>Syntaxe  
  
```  
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;  
```  
  
## <a name="a-nameacceleratorviewisdebuga-isdebug"></a><a name="accelerator_view__is_debug"></a>is_debug 

Obtient une valeur booléenne qui indique si l’objet accelerator_view a la couche de débogage est activée pour le rapport d’erreur étendu.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
__declspec(property(get= get_is_debug)) bool is_debug;  
```  
  
## <a name="a-nameacceleratorviewoperatorneqa-operator"></a><a name="accelerator_view__operator_neq"></a>opérateur ! = 

Compare cet objet accelerator_view avec une autre et retourne `false` si elles sont identiques ; sinon, retourne `true`.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
bool operator!= (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator_view` objet à comparer avec celle-ci.  
  
### <a name="return-value"></a>Valeur de retour  
 `false` si les deux objets sont identiques ; sinon, `true`.  
  
## <a name="a-nameacceleratorviewoperatoreqa-operator"></a><a name="accelerator_view__operator_eq"></a>opérateur = 

Copie le contenu de l’objet accelerator_view spécifié dans celle-ci.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
accelerator_view & operator= (    const accelerator_view & _Other );  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator_view` objet d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à la modification `accelerator_view` objet.  
  
## <a name="a-nameacceleratorviewoperatoreqeqa-operator"></a><a name="accelerator_view__operator_eq_eq"></a>opérateur == 

Compare cet objet accelerator_view avec une autre et retourne `true` si elles sont identiques ; sinon, retourne `false`.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
bool operator= = (    const accelerator_view & _Other ) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `accelerator_view` objet à comparer avec celle-ci.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si les deux objets sont identiques ; sinon, `false`.  
  
## <a name="a-nameacceleratorviewqueuingmodea-queuingmode"></a><a name="accelerator_view__queuing_mode"></a>queuing_mode 

Obtient le mode de files d’attente de l’objet accelerator_view.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;  
```  
  
## <a name="a-nameacceleratorviewversiona-version"></a><a name="accelerator_view__version"></a>Version 

Obtient la version de l’accelerator_view.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
__declspec(property(get= get_version)) unsigned int version;  
```  
  
## <a name="a-nameacceleratorviewwaita-wait"></a><a name="accelerator_view__wait"></a>attente 

Attend que toutes les commandes envoyées à l’objet accelerator_view à terminer.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
void wait();  
```  
  
#### <a name="return-value"></a>Valeur de retour  
 Retourne `void`.  
  
#### <a name="remarks"></a>Remarques  
 Si le [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) est `immediate`, cette méthode est retournée immédiatement sans blocage.  
  
##  <a name="a-namedtora-acceleratorview"></a><a name="dtor"></a>~ accelerator_view 

 Détruit l’objet accelerator_view.  
  
#### <a name="syntax"></a>Syntaxe  
  
```  
~accelerator_view();  
```  
  
### <a name="return-value"></a>Valeur de retour  
  
 
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

