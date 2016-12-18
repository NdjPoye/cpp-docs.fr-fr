---
title: "Indirection et op&#233;rateurs d&#39;adresse | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "& (opérateur), address-of (opérateur)"
  - "* (opérateur)"
  - "* (opérateur), address-of (opérateur)"
  - "* (opérateur), opérateur d'indirection"
  - "adresses (C++)"
  - "adresses (C++), indirection"
  - "address-of (opérateur) (&)"
  - "et commercial (opérateur &)"
  - "opérateur d'indirection"
  - "pointeurs null (C++)"
  - "opérateurs (C++), address-of"
  - "opérateurs (C++), indirection"
ms.assetid: 10d62b00-12ba-4ea9-a2d5-09ac29ca2232
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Indirection et op&#233;rateurs d&#39;adresse
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'opérateur d'indirection \(**\***\) accède à une valeur indirectement, via un pointeur.  L'opérande doit être une valeur de pointeur.  Le résultat de l'opération est la valeur adressée par l'opérande ; autrement dit, la valeur à l'adresse vers laquelle son opérande pointe.  Le type du résultat est le type traité par l'opérande.  
  
 Si l'opérande pointe vers une fonction, le résultat est un désignateur de fonction.  S'il pointe vers un emplacement de stockage, le résultat est une l\-value désignant l'emplacement de stockage.  
  
 Si la valeur du pointeur n'est pas valide, le résultat n'est pas défini.  La liste ci\-dessous inclut certaines des conditions les plus courantes qui invalident une valeur de pointeur.  
  
-   Le pointeur est un pointeur null.  
  
-   Le pointeur spécifie l'adresse d'un élément local qui n'est pas visible au moment de la référence.  
  
-   Le pointeur spécifie une adresse alignée de façon inappropriée pour le type de l'objet désigné.  
  
-   Le pointeur spécifie une adresse non utilisée par le programme en cours d'exécution.  
  
 L'opérateur d'adresse \(**&**\) fournit l'adresse de son opérande.  L'opérande de l'opérateur d'adresse peut être un désignateur de fonction ou une l\-value qui désigne un objet qui n'est pas un champ de bits et n'est pas déclaré avec le spécificateur de classe de stockage **register**.  
  
 Le résultat de l'opération d'adresse est un pointeur désignant l'opérande.  Le type traité par le pointeur est le type de l'opérande.  
  
 L'opérateur d'adresse peut être appliqué uniquement aux variables dotées de types fondamentaux, de structure ou d'union qui sont déclarées au niveau de la portée du fichier, ou aux références indicées de tableau.  Dans ces expressions, une expression constante qui n'inclut pas l'opérateur d'adresse peut être ajoutée ou soustraite dans l'expression d'adresse.  
  
## Exemples  
 Les exemples ci\-dessous utilisent ces déclarations :  
  
```  
int *pa, x;  
int a[20];  
double d;  
```  
  
 Cette instruction utilise l'opérateur d'adresse :  
  
```  
pa = &a[5];  
```  
  
 L'opérateur d'adresse \(**&**\) prend l'adresse du sixième élément du tableau `a`.  Le résultat est stocké dans la variable pointeur `pa`.  
  
```  
x = *pa;  
```  
  
 L'opérateur d'indirection \(**\***\) est utilisé dans cet exemple pour accéder à la valeur `int`, à l'adresse stockée dans `pa`.  La valeur est assignée à la variable de type entier `x`.  
  
```  
if( x == *&x )  
    printf( "True\n" );  
```  
  
 Cet exemple imprime le mot `True`, démontrant ainsi que le résultat de l'application de l'opérateur d'indirection à l'adresse de `x` équivaut à `x`.  
  
```  
int roundup( void );     /* Function declaration */  
  
int  *proundup  = roundup;  
int  *pround  = &roundup;  
```  
  
 Une fois que la fonction `roundup` est déclarée, deux pointeurs désignant `roundup` sont déclarés et initialisés.  Le premier pointeur, `proundup`, est initialisé en utilisant uniquement le nom de la fonction, tandis que le second, `pround`, utilise l'opérateur d'adresse dans l'initialisation.  Les initialisations sont équivalentes.  
  
## Voir aussi  
 [Opérateur d'indirection : \*](../cpp/indirection-operator-star.md)   
 [Opérateur address\-of : &](../cpp/address-of-operator-amp.md)