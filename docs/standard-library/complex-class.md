---
title: "complexe, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "complex"
  - "std::complex"
  - "std.complex"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "complexe (classe)"
  - "nombres complexes"
ms.assetid: d6492e1c-5eba-4bc5-835b-2a88001a5868
caps.latest.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 18
---
# complexe, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe du modèle décrit un objet qui contient deux objets de type **Type**, un qui représente la partie réelle d'un nombre complexe et un qui représente la partie imaginaire.  
  
## Syntaxe  
  
```  
  
   template<class   
   Type  
   >  
class complex  
```  
  
## Notes  
 Un objet de la classe **Type**:  
  
-   Un constructeur par défaut public, un destructeur, un constructeur de copie, ainsi qu'un opérateur d'assignation avec le comportement classique.  
  
-   Peuvent être affectées integer ou les valeurs à virgule flottante, ou la conversion des types de ces valeurs avec le comportement classique.  
  
-   Définit les opérateurs arithmétiques et les fonctions mathématiques, si nécessaire, définis pour les types à virgule flottante le comportement classique.  
  
 En particulier, aucune différence subtile peut ne pas exister entre la construction de copie et la construction de valeur par défaut est suivie du.  Aucune des opérations sur des objets de classe **Type** peut ne pas lever des exceptions.  
  
 Les spécialisations explicites du type de classe de modèle existe des trois types virgule flottante.  Dans cette implémentation, la valeur de n'importe quel autre type **Type** est enfermée dans le rôle à **double** pour les calculs réels, le résultat de **double** affecté à l'objet stocké le type **Type**`.`  
  
### Constructeurs  
  
|||  
|-|-|  
|[profondeur](../Topic/complex::complex.md)|Construit un nombre complexe à true et imaginaires parties spécifiées ou comme copie d'un autre nombre complexe.|  
  
### Typedef  
  
|||  
|-|-|  
|[type valeur](../Topic/complex::value_type.md)|Type qui représente le type de données représentant les true et imaginaires parties d'un nombre complexe.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[imag](../Topic/complex::imag.md)|Extrait le composant imaginaire d'un nombre complexe.|  
|[real](../Topic/complex::real.md)|Extrait real composant d'un nombre complexe.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\*\=](../Topic/complex::operator*=.md)|Multiplie un nombre complexe cible par un facteur, qui peut être complexe ou qu'il s'agit du même type que sont les true et imaginaires parties du nombre complexe.|  
|[\+\=, opérateur](../Topic/complex::operator+=.md)|Ajoute un nombre complexe cible, où le nombre ajouté peut être complexe ou du même type que les sont true et imaginaires parties du nombre complexe auquel il est ajouté.|  
|[opérateur\-\=](../Topic/complex::operator-=1.md)|Soustrait un nombre d'un nombre complexe cible, dont le numéro soustrait peut être complexe ou du même type que les sont true et imaginaires parties du nombre complexe auquel il est ajouté.|  
|[operator\/\=](../Topic/complex::operator-=2.md)|Divise un nombre complexe cible par un diviseur, qui peut être complexe ou qu'il s'agit du même type que sont les true et imaginaires parties du nombre complexe.|  
|[operator\=](../Topic/complex::operator=.md)|Affecte un nombre complexe cible, dont le numéro affecté peut être complexe ou du même type que les sont true et imaginaires parties du nombre complexe auquel il est affecté.|  
  
## Configuration requise  
 **En\-tête**: \<complexe\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [complex Members](http://msdn.microsoft.com/fr-fr/d5c4466c-43a0-4817-aca1-9a5d492dae28)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)