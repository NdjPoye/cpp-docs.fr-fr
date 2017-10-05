---
title: Classes du Support COM du compilateur | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- cl.exe compiler, COM support
- COM, compiler support
ms.assetid: 6d800d9b-b902-4033-9639-740a30b06f88
caps.latest.revision: 6
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
ms.openlocfilehash: 48540910db97e7662eeaa7e8a7febf7e44df653b
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="compiler-com-support-classes"></a>Classes du support COM du compilateur
**Section spécifique à Microsoft**  
  
 Les classes standard sont utilisées pour prendre en charge certains types COM. Les classes sont définies dans comdef.h et les fichiers d'en-tête sont générés à partir de la bibliothèque de types.  
  
|Classe|Objectif|  
|-----------|-------------|  
|[_bstr_t](../cpp/bstr-t-class.md)|Encapsule le type `BSTR` pour fournir des opérateurs et des méthodes utiles.|  
|[_com_error](../cpp/com-error-class.md)|Définit l’objet d’erreur levé par [_com_raise_error](../cpp/com-raise-error.md) dans la plupart des défaillances.|  
|[_com_ptr_t](../cpp/com-ptr-t-class.md)|Encapsule des pointeurs d’interface COM et automatise les appels requis à `AddRef`, **version**, et `QueryInterface`.|  
|[_variant_t](../cpp/variant-t-class.md)|Encapsule le **VARIANT** type pour fournir des méthodes et opérateurs utiles.|  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Support COM du compilateur](../cpp/compiler-com-support.md)   
 [Fonctions globales COM du compilateur](../cpp/compiler-com-global-functions.md)   
 [Informations de référence sur le langage C++](../cpp/cpp-language-reference.md)
