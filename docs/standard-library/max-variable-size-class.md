---
title: max_variable_size, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- allocators/stdext::max_variable_size
- allocators/stdext::max_variable_size::allocated
- allocators/stdext::max_variable_size::deallocated
- allocators/stdext::max_variable_size::full
- allocators/stdext::max_variable_size::released
- allocators/stdext::max_variable_size::saved
dev_langs: C++
helpviewer_keywords:
- stdext::max_variable_size
- stdext::max_variable_size [C++], allocated
- stdext::max_variable_size [C++], deallocated
- stdext::max_variable_size [C++], full
- stdext::max_variable_size [C++], released
- stdext::max_variable_size [C++], saved
ms.assetid: 9f2e9df0-4148-4b37-bc30-f8eca0ef86ae
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 4e66f5bdf70997c541c4fa7f0c0f05599a25d2c8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="maxvariablesize-class"></a>max_variable_size, classe
Décrit un objet de [classe max](../standard-library/allocators-header.md) qui limite un objet [freelist](../standard-library/freelist-class.md) à une longueur maximale qui est à peu près proportionnelle au nombre de blocs de mémoire alloués.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class max_variable_size
```  
  
### <a name="constructors"></a>Constructeurs  
  
|||  
|-|-|  
|[max_variable_size](#max_variable_size)|Construit un objet de type `max_variable_size`.|  
  
### <a name="member-functions"></a>Fonctions membres  
  
|||  
|-|-|  
|[allocated](#allocated)|Incrémente le nombre de blocs de mémoire alloués.|  
|[deallocated](#deallocated)|Décrémente le nombre de blocs de mémoire alloués.|  
|[full](#full)|Retourne une valeur qui indique si davantage de blocs de mémoire doivent être ajoutés à la liste libre.|  
|[released](#released)|Décrémente le nombre de blocs de mémoire dans la liste libre.|  
|[saved](#saved)|Incrémente le nombre de blocs de mémoire dans la liste libre.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** \<allocators>  
  
 **Espace de noms :** stdext  
  
##  <a name="allocated"></a>  max_variable_size::allocated  
 Incrémente le nombre de blocs de mémoire alloués.  
  
```
void allocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Nx`|Valeur d’incrément.|  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre ajoute `_Nx` à la valeur stockée `_Nallocs`. Cette fonction membre est appelée après chaque appel réussi par `cache_freelist::allocate` à l’opérateur `new`. L’argument `_Nx` est le nombre de blocs de mémoire dans le bloc alloués par l’opérateur `new`.  
  
##  <a name="deallocated"></a>  max_variable_size::deallocated  
 Décrémente le nombre de blocs de mémoire alloués.  
  
```
void deallocated(std::size_t _Nx = 1);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`_Nx`|Valeur d’incrément.|  
  
### <a name="remarks"></a>Notes  
 La fonction membre soustrait `_Nx` de la valeur stockée `_Nallocs`. Cette fonction membre est appelée après chaque appel par `cache_freelist::deallocate` à l’opérateur `delete`. L’argument `_Nx` est le nombre de blocs de mémoire dans le bloc libérés par l’opérateur `delete`.  
  
##  <a name="full"></a>  max_variable_size::full  
 Retourne une valeur qui indique si davantage de blocs de mémoire doivent être ajoutés à la liste libre.  
  
```
bool full();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si `_Nallocs / 16 + 16 <= _Nblocks`.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre est appelée par `cache_freelist::deallocate`. Si l’appel retourne `true`, `deallocate` place le bloc de mémoire dans la liste libre ; s’il retourne false, `deallocate` appelle l’opérateur `delete` pour libérer le bloc.  
  
##  <a name="max_variable_size"></a>  max_variable_size::max_variable_size  
 Construit un objet de type `max_variable_size`.  
  
```
max_variable_size();
```  
  
### <a name="remarks"></a>Notes  
 Le constructeur initialise les valeurs stockées `_Nblocks` et `_Nallocs` à zéro.  
  
##  <a name="released"></a>  max_variable_size::released  
 Décrémente le nombre de blocs de mémoire dans la liste libre.  
  
```
void released();
```  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre décrémente la valeur stockée `_Nblocks`. La fonction membre `released` de la classe max actuelle est appelée par `cache_freelist::allocate` chaque fois qu’elle supprime un bloc de mémoire de la liste libre.  
  
##  <a name="saved"></a>  max_variable_size::saved  
 Incrémente le nombre de blocs de mémoire dans la liste libre.  
  
```
void saved();
```  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre incrémente la valeur stockée `_Nblocks`. Cette fonction membre est appelée par `cache_freelist::deallocate` chaque fois qu’elle place un bloc de mémoire dans la liste libre.  
  
## <a name="see-also"></a>Voir aussi  
 [\<allocators>](../standard-library/allocators-header.md)



