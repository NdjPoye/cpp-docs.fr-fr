---
title: "context_unblock_unbalanced, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::context_unblock_unbalanced"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "context_unblock_unbalanced (classe)"
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# context_unblock_unbalanced, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée quand des appels aux méthodes `Block` et `Unblock` d'un objet `Context` ne sont pas correctement associés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class context_unblock_unbalanced : public std::exception;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[context_unblock_unbalanced::context_unblock_unbalanced, constructeur](#context_unblock_unbalanced__context_unblock_unbalanced_constructor)|Surchargé. Construit un objet `context_unblock_unbalanced`.|  
  
## <a name="remarks"></a>Notes  
 Les appels à la `Block` et `Unblock` les méthodes d’un `Context` objet doit toujours être associé correctement. Le Runtime d’accès concurrentiel permet les opérations de se produire dans n’importe quel ordre. Par exemple, un appel à `Block` peut être suivie par un appel à `Unblock`, ou vice versa. Cette exception serait levée si, par exemple, deux appels à la `Unblock` méthode ont été effectuées dans une ligne, sur un `Context` objet qui n’a pas été bloqué.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `exception`  
  
 `context_unblock_unbalanced`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namecontextunblockunbalancedcontextunblockunbalancedconstructora-contextunblockunbalancedcontextunblockunbalanced-constructor"></a><a name="context_unblock_unbalanced__context_unblock_unbalanced_constructor"></a>  context_unblock_unbalanced::context_unblock_unbalanced, constructeur  
 Construit un objet `context_unblock_unbalanced`.  
  
```  
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

 
context_unblock_unbalanced() throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `_Message`  
 Message descriptif de l'erreur.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](../../../parallel/concrt/reference/concurrency-namespace.md)
