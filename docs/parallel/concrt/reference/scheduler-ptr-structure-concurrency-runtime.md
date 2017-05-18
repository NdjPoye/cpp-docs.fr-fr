---
title: scheduler_ptr::structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::scheduler_ptr
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::get
- PPLINTERFACE/concurrency::scheduler_ptr::scheduler_ptr::operator bool
dev_langs:
- C++
ms.assetid: e88c84af-c306-476d-aef1-f42a0fa0a80f
caps.latest.revision: 8
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 4bef1995724d078c9702669806ff61d5563ac465
ms.contentlocale: fr-fr
ms.lasthandoff: 03/17/2017

---
# <a name="schedulerptr-structure"></a>scheduler_ptr::structure
Représente un pointeur vers un planificateur. Cette classe a pour fonction de permettre la spécification d'une durée de vie partagée à l'aide de shared_ptr ou d'une référence simple à l'aide d'un pointeur brut.  
  
## <a name="syntax"></a>Syntaxe  
  
```
struct scheduler_ptr;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[scheduler_ptr::scheduler_ptr](#ctor)|Surchargé. Crée un pointeur de planificateur de shared_ptr vers le planificateur|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[scheduler_ptr::Get](#get)|Retourne le pointeur brut au planificateur|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[scheduler_ptr::operator bool](#operator_bool)|Teste si le pointeur du planificateur a une valeur non null|  
|[scheduler_ptr::operator-&gt;](#operator_ptr)|Se comporte comme un pointeur|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `scheduler_ptr`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** pplinterface.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="get"></a>scheduler_ptr::Get, méthode  
 Retourne le pointeur brut au planificateur  
  
```
scheduler_interface* get() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="operator_bool"></a>scheduler_ptr::operator bool   
 Teste si le pointeur du planificateur a une valeur non null  
  
''' opérateur bool() const ;
```  
  
##  <a name="operator_ptr"></a>  scheduler_ptr::operator-&gt;   
 Behave like a pointer  
  
```
scheduler_interface * operator->() const ;
```  
  
### Return Value  
  
##  <a name="ctor"></a>  scheduler_ptr::scheduler_ptr Constructor  
 Creates a scheduler pointer from shared_ptr to scheduler  
  
```
explicite scheduler_ptr(std::shared_ptr<scheduler_interface> scheduler) ;</scheduler_interface>

scheduler_ptr explicite (_In_opt_ scheduler_interface * pScheduler) ;
```  
  
### Parameters  
 `scheduler`  
 `pScheduler`  
  
## See Also  
 [concurrency Namespace](concurrency-namespace.md)

