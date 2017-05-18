---
title: improper_lock, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- improper_lock
- CONCRT/concurrency::improper_lock
- CONCRT/concurrency::improper_lock::improper_lock
dev_langs:
- C++
helpviewer_keywords:
- improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 336cd222ee70253954905b1ea01144160eeb2f06
ms.contentlocale: fr-fr
ms.lasthandoff: 03/17/2017

---
# <a name="improperlock-class"></a>improper_lock, classe
Cette classe décrit une exception levée quand un verrou est incorrectement acquis.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class improper_lock : public std::exception;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[improper_lock](#ctor)|Surchargé. Construit un objet `improper_lock exception`.|  
  
## <a name="remarks"></a>Remarques  
 En général, cette exception est levée lorsqu’une tentative est faite pour acquérir un verrou non réentrant de manière récursive dans le même contexte.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `exception`  
  
 `improper_lock`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="ctor"></a>improper_lock 

 Construit un objet `improper_lock exception`.  
  
```
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Message descriptif de l'erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [critical_section, classe](critical-section-class.md)   
 [reader_writer_lock, classe](reader-writer-lock-class.md)

