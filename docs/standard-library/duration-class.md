---
title: "duration, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::duration"
dev_langs: 
  - "C++"
ms.assetid: 06b863b3-65be-4ded-a72e-6e1eb1531077
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 10
---
# duration, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un type qui contient un *intervalle de temps*, qui est un temps écoulé entre deux instants temporels.  
  
## Syntaxe  
  
```  
template<  
   class Rep,  
   class Period = ratio<1>  
>  
class duration;  
template<  
   class Rep,  
   class Period  
>  
class duration;  
template<  
   class Rep,  
   class Period1,  
   class Period2  
>  
class duration  
   <duration<Rep, Period1>, Period2>;  
```  
  
## Notes  
 L'argument de modèle `Rep` décrit le type utilisé pour contenir le nombre de battements d'horloge dans l'intervalle.  L'argument template `Period` est une instanciation de [taux](../standard-library/ratio.md) qui décrit la taille de l'intervalle que chaque graduation représente.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[duration::period Typedef](http://msdn.microsoft.com/fr-fr/ebf2a1b9-769f-475f-8c66-cf9ed12015f2)|Représente un synonyme du type de paramètre de modèle `Period`.|  
|[duration::rep Typedef](http://msdn.microsoft.com/fr-fr/f47b8abb-ae2c-4dc8-858a-f44695156950)|Représente un synonyme du type de paramètre de modèle `Rep`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[duration::duration, constructeur](../Topic/duration::duration%20Constructor.md)|Construit un objet `duration`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[duration::count, méthode](../Topic/duration::count%20Method.md)|Renvoie le nombre de battements d'horloge dans l'intervalle de temps.|  
|[duration::max, méthode](../Topic/duration::max%20Method.md)|Static.  Retourne la valeur maximale autorisée du paramètre de modèle `Ref`.|  
|[duration::min, méthode](../Topic/duration::min%20Method.md)|Static.  Retourne la valeur minimale autorisée du paramètre de modèle `Ref`.|  
|[duration::zero, méthode](../Topic/duration::zero%20Method.md)|Static.  En effet, renvoie `Rep`\(0\).|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[duration::operator\-, opérateur](../Topic/duration::operator-%20Operator.md)|Retourne une copie de l'objet `duration` avec un nombre de cycles exécuté négatif.|  
|[duration::operator\-\-, opérateur](../Topic/duration::operator--%20Operator.md)|Décrémente le nombre de cycles stocké.|  
|[duration::operator\=, opérateur](../Topic/duration::operator=%20Operator.md)|Réduit le nombre de cycles stockés, modulo une valeur données.|  
|[duration::operator\*\=, opérateur](../Topic/duration::operator*=%20Operator.md)|Multiplie le nombre de cycles stocké par une valeur spécifiée.|  
|[duration::operator\/\=, opérateur](../Topic/duration::operator-=%20Operator1.md)|Divise le nombre de cycles stocké par le nombre de cycles d'un objet `duration` spécifié.|  
|[duration::operator\+, opérateur](../Topic/duration::operator+%20Operator.md)|retourne `*this` ;|  
|[duration::operator\+\+, opérateur](../Topic/duration::operator++%20Operator.md)|Incrémente le nombre de cycles stocké.|  
|[duration::operator\+\=, opérateur](../Topic/duration::operator+=%20Operator.md)|Ajoute le nombre de cycles d'un objet `duration` spécifié au nombre de cycles stocké.|  
|[duration::operator\-\=, opérateur](../Topic/duration::operator-=%20Operator2.md)|Soustrait le nombre de cycles d'un objet `duration` spécifié au nombre de cycles stocké.|  
  
## Configuration requise  
 **En\-tête :** chrono  
  
 **Espace de noms :** std::chrono  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)   
 [duration\_values, structure](../standard-library/duration-values-structure.md)