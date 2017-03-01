---
title: unsupported_feature, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amprt/Concurrency::unsupported_feature
dev_langs:
- C++
helpviewer_keywords:
- unsupported_feature class
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
caps.latest.revision: 12
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
ms.openlocfilehash: 191678e0802696e7200945f96dc1f2bbd379cf57
ms.lasthandoff: 02/24/2017

---
# <a name="unsupportedfeature-class"></a>unsupported_feature, classe
Exception levée lorsqu’une fonctionnalité non prise en charge est utilisée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class unsupported_feature : public runtime_exception;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[unsupported_feature, constructeur](#ctor)|Construit une nouvelle instance de la `unsupported_feature` exception.|  

  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `exception`  
  
 `runtime_exception`  
  
 `unsupported_feature`  
  
## <a name="a-nameunsupportedfeaturectora-unsupportedfeature"></a><a name="unsupported_feature__ctor"></a>unsupported_feature 

  Construit une nouvelle instance de l’exception d’unsupported_feature.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
explicit unsupported_feature(  
    const char * _Message ) throw();  
  
unsupported_feature() throw();  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Description de l'erreur.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `unsupported_feature`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amprt.h  
  
 **Espace de noms :** Concurrency  
  
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

