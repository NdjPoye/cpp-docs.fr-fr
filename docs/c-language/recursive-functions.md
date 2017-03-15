---
title: "Fonctions r&#233;cursives | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "appels de fonction, récursives"
  - "fonctions (C), appeler de manière récursive"
  - "fonctions (C), récursives"
  - "appels de fonction récursive"
ms.assetid: 59739040-3081-4006-abbc-9d8423992bce
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Fonctions r&#233;cursives
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Toute fonction d'un programme C peut être appelée de manière récursive. Autrement dit, elle peut s'appeler elle\-même.  Le nombre d'appels récurrents est limité à la taille de la pile.  Pour plus d'informations sur les options de l'éditeur de liens qui définissent la taille de la pile, consultez l'option de l'éditeur de liens [\/STACK, allocations de la pile](../build/reference/stack-stack-allocations.md) \(\/STACK\).  Chaque fois que la fonction est appelée, un nouveau stockage est alloué pour les paramètres et les variables **auto** et **register** afin que leurs valeurs ne soient pas remplacées dans les appels non terminés.  Les paramètres sont uniquement directement accessibles à l'instance de la fonction dans laquelle ils sont créés.  Les paramètres précédents ne sont pas directement accessibles aux instances suivantes de la fonction.  
  
 Notez que les variables déclarées avec le stockage **static** ne nécessitent pas de nouveau stockage à chaque appel récurrent.  Leur stockage existe pour la durée de vie du programme.  Chaque référence à cette variable accède à la même zone de stockage.  
  
## Exemple  
 Cet exemple illustre des appels récurrents :  
  
```  
int factorial( int num );      /* Function prototype */  
  
int main()  
{  
    int result, number;  
    .  
    .  
    .  
    result = factorial( number );  
}  
  
int factorial( int num )      /* Function definition */  
{  
    .  
    .  
    .  
    if ( ( num > 0 ) || ( num <= 10 ) )  
        return( num * factorial( num - 1 ) );  
}  
  
```  
  
## Voir aussi  
 [Appels de fonction](../c-language/function-calls.md)