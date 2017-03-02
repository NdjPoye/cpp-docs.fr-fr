---
title: cancellation_token_source, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- pplcancellation_token/concurrency::cancellation_token_source
dev_langs:
- C++
helpviewer_keywords:
- cancellation_token_source class
ms.assetid: 3548b1a0-12b0-4334-95db-4bf57141c066
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
ms.openlocfilehash: 5c80977656308d3174f4141b131c27fd3c162bbe
ms.lasthandoff: 02/24/2017

---
# <a name="cancellationtokensource-class"></a>cancellation_token_source, classe
La classe `cancellation_token_source` représente la capacité d'annulation d'une opération annulable.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class cancellation_token_source;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[cancellation_token_source, constructeur](#ctor)|Surchargé. Construit une nouvelle classe `cancellation_token_source`. La source peut être utilisée pour signaler l'annulation d'une opération annulable.|  
|[~ cancellation_token_source, destructeur](#dtor)||  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Cancel (méthode)](#cancel)|Annule le jeton. N'importe quel `task_group`, `structured_task_group` ou `task` qui utilise le jeton sera annulé lors de cet appel et lèvera une exception au point d'interruption suivant.|  
|[create_linked_source (méthode)](#create_linked_source)|Surchargé. Crée une classe `cancellation_token_source` qui est annulée lorsque le jeton fourni est annulé.|  
|[get_token (méthode)](#get_token)|Retourne un jeton d'annulation associé à cette source. Le jeton retourné peut être interrogé pour l'annulation ou fournir un rappel si et quand l'annulation se produit.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[opérateur ! =, opérateur](#operator_neq)||  
|[opérateur =, opérateur](#operator_eq)||  
|[opérateur ==, opérateur](#operator_eq_eq)||  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `cancellation_token_source`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** pplcancellation_token.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namedtora-cancellationtokensource"></a><a name="dtor"></a>~ cancellation_token_source 

```
~cancellation_token_source();
```  
  
##  <a name="a-namecancela-cancel"></a><a name="cancel"></a>Annuler 

 Annule le jeton. N'importe quel `task_group`, `structured_task_group` ou `task` qui utilise le jeton sera annulé lors de cet appel et lèvera une exception au point d'interruption suivant.  
  
```
void cancel() const;
```  
  
##  <a name="a-namectora-cancellationtokensource"></a><a name="ctor"></a>cancellation_token_source 

 Construit une nouvelle classe `cancellation_token_source`. La source peut être utilisée pour signaler l'annulation d'une opération annulable.  
  
```
cancellation_token_source();

cancellation_token_source(const cancellation_token_source& _Src);

cancellation_token_source(cancellation_token_source&& _Src);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Src`  
  
##  <a name="a-namecreatelinkedsourcea-createlinkedsource"></a><a name="create_linked_source"></a>create_linked_source 

 Crée une classe `cancellation_token_source` qui est annulée lorsque le jeton fourni est annulé.  
  
```
static cancellation_token_source create_linked_source(
    cancellation_token& _Src);

template<typename _Iter>
static cancellation_token_source create_linked_source(_Iter _Begin, _Iter _End);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Iter`  
 `_Src`  
 Jeton dont l'annulation provoque l'annulation de la source du jeton retourné. Notez que la source du jeton retourné peut également être annulée indépendamment de la source contenue dans ce paramètre.  
  
 `_Begin`  
 Itérateur de bibliothèque C++ Standard correspondant au début de la plage de jetons à écouter pour l’annulation.  
  
 `_End`  
 Itérateur de bibliothèque C++ Standard correspondant à la fin de la plage de jetons à écouter pour l’annulation.  
  
### <a name="return-value"></a>Valeur de retour  
 `cancellation_token_source` qui est annulée lorsque le jeton fourni par le paramètre `_Src` est annulé.  
  
##  <a name="a-namegettokena-gettoken"></a><a name="get_token"></a>get_token 

 Retourne un jeton d'annulation associé à cette source. Le jeton retourné peut être interrogé pour l'annulation ou fournir un rappel si et quand l'annulation se produit.  
  
```
cancellation_token get_token() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Jeton d'annulation associé à cette source.  
  
##  <a name="a-nameoperatorneqa-operator"></a><a name="operator_neq"></a>opérateur ! = 

```
bool operator!= (const cancellation_token_source& _Src) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Src`  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>opérateur = 

```
cancellation_token_source& operator= (const cancellation_token_source& _Src);

cancellation_token_source& operator= (cancellation_token_source&& _Src);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Src`  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-nameoperatoreqeqa-operator"></a><a name="operator_eq_eq"></a>opérateur == 

```
bool operator== (const cancellation_token_source& _Src) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Src`  
  
### <a name="return-value"></a>Valeur de retour  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

