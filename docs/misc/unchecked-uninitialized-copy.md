---
title: "unchecked_uninitialized_copy | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.unchecked_uninitialized_copy"
  - "unchecked_uninitialized_copy"
  - "std::unchecked_uninitialized_copy"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unchecked_uninitialized_copy (fonction)"
ms.assetid: 38568841-314e-446b-91d0-92cc231e3b3c
caps.latest.revision: 9
caps.handback.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "douge"
---
# unchecked_uninitialized_copy
Identique à [uninitialized\_copy](../Topic/uninitialized_copy.md), mais permet l'utilisation d'un itérateur non vérifié comme itérateur de sortie lorsque \_SECURE\_SCL\=1 est défini. Cette fonction est définie dans le [Espace de noms stdext](../standard-library/stdext-namespace.md) espace de noms.  
  
> [!NOTE]
>  Cet algorithme est une extension Microsoft de la bibliothèque C\+\+ standard. Le code implémenté à l'aide de cet algorithme n'est pas portable.  
  
## Syntaxe  
  
```  
template<class InputIterator, class ForwardIterator>  
   ForwardIterator unchecked_uninitialized_copy(  
      InputIterator _First,  
      InputIterator _Last,  
      ForwardIterator _Dest  
   );  
  
template<class InputIterator, class ForwardIterator, class Allocator>  
   ForwardIterator unchecked_uninitialized_copy(  
      InputIterator _First,  
      InputIterator _Last,  
      ForwardIterator _Dest,  
      Allocator& _Al  
   );  
```  
  
#### Paramètres  
 `_First`  
 Itérateur d'entrée qui traite le premier élément de la plage source devant être copiée.  
  
 `_Last`  
 Itérateur d'entrée qui traite le dernier élément de la plage source devant être copiée.  
  
 `_Dest`  
 Itérateur forward qui traite le premier élément de la plage de destination devant être copiée.  
  
 `_Al`  
 Classe allocator à utiliser avec cet objet.[vector::get\_allocator](../Topic/vector::get_allocator.md) Retourne la classe d’allocateur pour l’objet.  
  
## Valeur de retour  
 Itérateur forward qui traite la position située immédiatement après le dernier élément de la plage de destination qui reçoit la copie.  
  
## Notes  
 Consultez [uninitialized\_copy](../Topic/uninitialized_copy.md) pour obtenir un exemple de code.  
  
 Pour plus d’informations sur les itérateurs vérifiés, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md).  
  
## Configuration requise  
 **En\-tête :** \<memory\>  
  
 **Espace de noms :** stdext