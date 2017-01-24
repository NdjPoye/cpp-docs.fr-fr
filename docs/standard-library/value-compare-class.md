---
title: "Classes value_compare, classe | Microsoft Docs"
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
  - "value_compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "value_compare (classe)"
ms.assetid: c306c5b9-3505-4357-aa6b-216451b951ed
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Classes value_compare, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fournit un objet de la fonction qui peut comparer les éléments d'un hash\_map en comparant les valeurs de leurs clés pour déterminer leur ordre relatif au hash\_map.  
  
## Syntaxe  
  
```  
class value_compare  
    : std::public binary_function<value_type, value_type, bool>   
{  
public:  
    bool operator( )(  
        const value_type& _Left,  
        const value_type& _Right ) const  
        {  
            return ( comp( _Left.first, _Right.first ) );   
        }  
protected:  
    value_compare( const key_compare& c ) : comp (c) { }  
    key_compare comp;  
};  
```  
  
## Notes  
 Critères de comparaison fournis par le value\_compare entre **value\_types** des entiers éléments contenus dans un hash\_map est induits d'une comparaison entre les clés des éléments respectifs par la construction de la classe auxiliaire.  L'opérateur de fonction membre utilise l'objet **comp.** du type `key_compare` stocké dans l'objet function fourni par le value\_compare pour comparer les composants clés de deux éléments.  
  
 Pour les hash\_sets et les hash\_multisets, qui sont des conteneurs simples où la valeur de clé est identique aux valeurs d'élément, le value\_compare équivaut à `key_compare`; pour les hash\_maps et les hash\_multimaps elles ne le sont pas, car la valeur des éléments d'`pair` de type n'est pas identique à la valeur de la clé de l'élément.  
  
 Dans Visual C\+\+ .NET 2003, les membres des fichiers d'en\-tête [\<hash\_map\>](../standard-library/hash-map.md) et de [\<hash\_set\>](../standard-library/hash-set.md) ne sont plus dans l'espace de noms standard, mais ont été plutôt déplacés dans l'espace de noms de stdext.  Pour plus d'informations, consultez [The stdext Namespace](../standard-library/stdext-namespace.md).  
  
## Exemple  
 Consultez l'exemple de [hash\_map::value\_comp](../Topic/hash_map::value_comp.md) pour obtenir un exemple de la façon dont déclarer et utiliser le value\_compare.  
  
## Configuration requise  
 **En\-tête:** \<hash\_map\>  
  
 **Espace de noms :** stdext  
  
## Voir aussi  
 [binary\_function, struct](../standard-library/binary-function-struct.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)