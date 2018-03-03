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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 54377893135c2b933c25387bccbb750d2f3eb734
ms.sourcegitcommit: 9a0a287d6940591523af959ebdac5affa36220da
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/25/2018
---
# <a name="compiler-com-support-classes"></a>Classes du support COM du compilateur
**Section spécifique à Microsoft**  
  
 Les classes standard sont utilisées pour prendre en charge certains types COM. Les classes sont définies dans \<comdef.h > et les fichiers d’en-tête générés à partir de la bibliothèque de types.  
  
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