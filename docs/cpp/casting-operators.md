---
title: "Opérateurs de casting | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: 'index-page '
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], casting
- casting operators [C++]
ms.assetid: 16240348-26bc-4f77-8eab-57253f00ce52
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a516297b687db349a6bcc867fc94dcd85118a8a5
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="casting-operators"></a>Opérateurs de casting
Il existe plusieurs opérateurs de cast spécifiques au langage C++. Ces opérateurs ont pour but de supprimer une partie de l'ambiguïté et du risque inhérents aux casts en langage C de style ancien. Ces opérateurs sont :  
  
-   [dynamic_cast](../cpp/dynamic-cast-operator.md) utilisées pour la conversion des types polymorphes.  
  
-   [static_cast](../cpp/static-cast-operator.md) utilisées pour la conversion des types non polymorphes.  
  
-   [const_cast](../cpp/const-cast-operator.md) permet de supprimer le `const`, `volatile`, et `__unaligned` attributs.  
  
-   [reinterpret_cast](../cpp/reinterpret-cast-operator.md) utilisé pour la réinterprétation simple des bits.  
  
-   [safe_cast](../windows/safe-cast-cpp-component-extensions.md) permettent de générer du code MSIL vérifiable.  
  
 Utilisez `const_cast` et `reinterpret_cast` en dernier recours, car ces opérateurs présentent les mêmes risques que les casts de style ancien. Ils sont néanmoins encore nécessaires pour remplacer complètement les casts de style ancien.  
  
## <a name="see-also"></a>Voir aussi  
 [Cast](../cpp/casting.md)
