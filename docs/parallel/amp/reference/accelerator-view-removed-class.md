---
title: accelerator_view_removed, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::accelerator_view_removed
dev_langs:
- C++
helpviewer_keywords:
- amprt/Concurrency::accelerator_view_removed Class
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 6e7a56a3315dc38a9e7def2144f3a2f8efd363fc
ms.lasthandoff: 02/24/2017

---
# <a name="acceleratorviewremoved-class"></a>accelerator_view_removed, classe
Exception levée lorsqu’un appel de DirectX sous-jacent échoue car le mécanisme de détection et récupération de délai d’attente Windows.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class accelerator_view_removed : public runtime_exception;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[accelerator_view_removed, constructeur](#ctor)|Initialise une nouvelle instance de la classe `accelerator_view_removed`.|  

### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[get_view_removed_reason (méthode)](#get_view_removed_reason)|Retourne un code d’erreur HRESULT indiquant la cause de le `accelerator_view` suppression de l’objet.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amprt.h  
  
 **Espace de noms :** Concurrency  

## <a name="a-namectora-acceleratorviewremoved"></a><a name="ctor"></a>accelerator_view_removed 

Initialise une nouvelle instance de la [accelerator_view_removed](accelerator-view-removed-class.md) (classe).  
  
### <a name="syntax"></a>Syntaxe  
  
```  
explicit accelerator_view_removed(  
    const char * _Message,  
    HRESULT _View_removed_reason ) throw();  
  
explicit accelerator_view_removed(  
    HRESULT _View_removed_reason ) throw();  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Description de l'erreur.  
  
 `_View_removed_reason`  
 Un code d’erreur HRESULT indiquant la cause de la suppression de la `accelerator_view` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Une nouvelle instance de la classe accelerator_view_removed.  
  
## <a name="a-namegetviewremovedreasonmethoda-getviewremovedreason"></a><a name="get_view_removed_reason_method"></a>get_view_removed_reason 

Retourne un code d’erreur HRESULT indiquant la cause de le `accelerator_view` suppression de l’objet.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
HRESULT get_view_removed_reason() const throw();  
```  
  
 
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

