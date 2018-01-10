---
title: runtime_exception, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- runtime_exception
- AMPRT/runtime_exception
- AMPRT/Concurrency::runtime_exception
- AMPRT/Concurrency::runtime_exception::get_error_code
dev_langs: C++
helpviewer_keywords: runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 705949f118e85b6dfef2beeccb55fecd63a64882
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeexception-class"></a>runtime_exception (classe)
Le type de base pour les exceptions dans la bibliothèque C++ Accelerated Massive Parallelism (AMP).  
  
### <a name="syntax"></a>Syntaxe  
  
```  
class runtime_exception : public std::exception;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[runtime_exception, constructeur](#ctor)|Initialise une nouvelle instance de la classe `runtime_exception`.|  
|[~ runtime_exception, destructeur](#dtor)|Détruit le `runtime_exception` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[get_error_code](#runtime_exception__get_error_code)|Retourne le code d’erreur qui a provoqué l’exception.|  

  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[operator=](#operator_eq)|Copie le contenu de l’objet `runtime_exception` objet dans celui-ci.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `exception`  
  
 `runtime_exception`  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** amprt.h  
  
 **Espace de noms :** Concurrency  

## <a name="runtime_exception__ctor"></a>runtime_exception, constructeur  
Initialise une nouvelle instance de la classe.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
runtime_exception(  
    const char * _Message,  
    HRESULT _Hresult ) throw();  
  
explicit runtime_exception(  
    HRESULT _Hresult ) throw();  
  
runtime_exception(  
    const runtime_exception & _Other ) throw();  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Description de l’erreur qui a provoqué l’exception.  
  
 `_Hresult`  
 HRESULT de l’erreur qui a provoqué l’exception.  
  
 `_Other`  
 Le `runtime_exception` objet à copier.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `runtime_exception`.  

## <a name="dtor"></a>~ runtime_exception, destructeur  
Détruit l’objet.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
virtual ~runtime_exception() throw();  
```  
  
## <a name="runtime_exception__get_error_code"></a>get_error_code   
Retourne le code d’erreur qui a provoqué l’exception.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
HRESULT get_error_code() const throw();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 HRESULT de l’erreur qui a provoqué l’exception.  
  
## <a name="runtime_exception__operator_eq"></a>  operator=   
  Copie le contenu de l’objet `runtime_exception` objet dans celui-ci.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
runtime_exception & operator= (    const runtime_exception & _Other ) throw();  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `runtime_exception` objet à copier.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à ce `runtime_exception` objet.  
  

  
## <a name="see-also"></a>Voir aussi  
 [Concurrency, espace de noms (C++ AMP)](concurrency-namespace-cpp-amp.md)
