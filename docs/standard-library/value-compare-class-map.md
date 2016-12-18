---
title: "value_compare, classe (&lt;map&gt;) | Microsoft Docs"
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
  - "std::value_compare"
  - "std.value_compare"
  - "map/std::value_compare"
  - "value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare (classe)"
ms.assetid: ea97c1d0-04b2-4d42-8d96-23522c04cc41
caps.latest.revision: 21
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# value_compare, classe (&lt;map&gt;)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fournit un objet de la fonction qui peut comparer les éléments d'une carte en comparant les valeurs de leurs clés pour déterminer leur ordre relatif dans la carte.  
  
## Syntaxe  
  
```  
class value_compare : public binary_function<value_type, value_type, bool>  
{  
public:  
   bool operator()(const value_type& _Left, const value_type& _Right) const;  
   value_compare(key_compare _Pred) : comp(_Pred);  
   protected:  
      key_compare comp;  
};  
```  
  
## Notes  
 Le critère de comparaison fourni par `value_compare` entre **value\_types** des entiers éléments contenus dans une carte est induit une comparaison entre les clés des éléments respectifs par la construction de la classe auxiliaire.  L'opérateur de fonction membre utilise l'objet **comp.** du type `key_compare` stocké dans l'objet function fourni par `value_compare` pour comparer les composants clés de deux éléments.  
  
 Pour les packages et les multiensembles, qui sont des conteneurs simples où la valeur de clé est identique aux valeurs d'élément, `value_compare` équivaut à `key_compare`; pour ajouter des cartes et des mappages multiples elles ne le sont pas, car la valeur des éléments d'`pair` de type n'est pas identique à la valeur de la clé de l'élément.  
  
## Exemple  
 Consultez l'exemple de [value\_comp](../Topic/map::value_comp.md) pour obtenir un exemple de la façon dont déclarer et utiliser `value_compare`.  
  
## Configuration requise  
 **En\-tête :** \<mappage\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [binary\_function, struct](../standard-library/binary-function-struct.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)