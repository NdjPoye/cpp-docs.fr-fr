---
title: _com_ptr_t (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_ptr_t
dev_langs:
- C++
helpviewer_keywords:
- _com_ptr_t class
ms.assetid: 3753a8a0-03d4-4cfd-8a9a-74872ea53971
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 3979a33f095092c5cbaac91793c501e31304a6d4
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="comptrt-class"></a>_com_ptr_t, classe
**Section spécifique à Microsoft**  
  
 Un objet `_com_ptr_t` encapsule un pointeur d'interface COM et est appelé un pointeur « intelligent ». Cette classe de modèle gère l’allocation des ressources et la désallocation via des appels de fonction à la **IUnknown** fonctions membres : `QueryInterface`, `AddRef`, et **version**.  
  
 Un pointeur intelligent est généralement référencé par la définition de typedef fournie par le **_COM_SMARTPTR_TYPEDEF** (macro). Cette macro accepte un nom d'interface et l'IID et déclare une spécialisation de `_com_ptr_t` avec le nom de l'interface plus un suffixe `Ptr`. Exemple :  
  
```  
_COM_SMARTPTR_TYPEDEF(IMyInterface, __uuidof(IMyInterface));  
```  
  
 déclare le `_com_ptr_t` spécialisation **IMyInterfacePtr**.  
  
 Un ensemble de [modèles de fonction](../cpp/relational-function-templates.md), pas les membres de ce modèle de classe, les comparaisons de prise en charge avec un pointeur intelligent à droite de l’opérateur de comparaison.  
  
### <a name="construction"></a>Construction  
  
|||  
|-|-|  
|[_com_ptr_t](../cpp/com-ptr-t-com-ptr-t.md)|Construit un objet `_com_ptr_t`.|  
  
### <a name="low-level-operations"></a>Opérations de bas niveau  
  
|||  
|-|-|  
|[AddRef](../cpp/com-ptr-t-addref.md)|Appelle le `AddRef` fonction membre de **IUnknown** sur le pointeur d’interface encapsulé.|  
|[Attacher](../cpp/com-ptr-t-attach.md)|Encapsule un pointeur d'interface brut du type de ce pointeur intelligent.|  
|[CreateInstance](../cpp/com-ptr-t-createinstance.md)|Crée une instance d’un objet avec un **CLSID** ou **ProgID**.|  
|[Détacher](../cpp/com-ptr-t-detach.md)|Extrait et retourne le pointeur d'interface encapsulé.|  
|[GetActiveObject](../cpp/com-ptr-t-getactiveobject.md)|Joint à une instance existante d’un objet avec un **CLSID** ou **ProgID**.|  
|[GetInterfacePtr](../cpp/com-ptr-t-getinterfaceptr.md)|Retourne le pointeur d'interface encapsulé.|  
|[QueryInterface](../cpp/com-ptr-t-queryinterface.md)|Appelle le `QueryInterface` fonction membre de **IUnknown** sur le pointeur d’interface encapsulé.|  
|[Version release](../cpp/com-ptr-t-release.md)|Appelle le **version** fonction membre de **IUnknown** sur le pointeur d’interface encapsulé.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[opérateur =](../cpp/com-ptr-t-operator-equal.md)|Assigne une nouvelle valeur à un objet `_com_ptr_t` existant.|  
|[les opérateurs ==, ! =, \<, >, \<=, > =](../cpp/com-ptr-t-relational-operators.md)|Comparer l’objet pointeur intelligent avec un autre pointeur intelligent, un pointeur d’interface brut ou **NULL**.|  
|[Extracteurs](../cpp/com-ptr-t-extractors.md)|Récupérez le pointeur d'interface COM encapsulé.|  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** comip.h  
  
 **Lib :** comsuppw.lib ou comsuppwd.lib (consultez [/Zc : wchar_t (wchar_t est un Type natif)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) pour plus d’informations)  
  
## <a name="see-also"></a>Voir aussi  
 [Classes du support COM du compilateur](../cpp/compiler-com-support-classes.md)
