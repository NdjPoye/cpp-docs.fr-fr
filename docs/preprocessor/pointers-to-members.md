---
title: "pointers_to_members | Microsoft Docs"
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
  - "pointers_to_members_CPP"
  - "vc-pragma.pointers_to_members"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "membres de classe, pointeurs vers"
  - "membres, pointeurs vers"
  - "pointers_to_members (pragma)"
  - "pragmas, pointers_to_members"
ms.assetid: 8325428c-c90a-4aed-9e82-cb1dda23f4ca
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# pointers_to_members
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Spécifie si un pointeur vers un membre de classe peut être déclaré avant la définition de classe qui lui est associée et s'il sert à contrôler la taille du pointeur et le code requis pour interpréter le pointeur.  
  
## Syntaxe  
  
```  
  
#pragma pointers_to_members( pointer-declaration, [most-general-representation] )  
```  
  
## Notes  
 Vous pouvez placer un pragma **pointeurs\_vers\_membres** dans votre fichier source au lieu d'utiliser les options du compilateur [\/vmx](../build/reference/vmb-vmg-representation-method.md) ou les [mots clés d'héritage](../cpp/inheritance-keywords.md).  
  
 L'argument *pointer\-declaration* spécifie si vous avez déclaré un pointeur vers un membre avant ou après la définition de fonction associée.  L'argument *pointer\-declaration* est l'un des deux symboles suivants :  
  
|Argument|Commentaires|  
|--------------|------------------|  
|**full\_generality**|Génère un code sécurisé, parfois non optimal.  Vous utilisez **full\_generality** si un pointeur vers un membre est déclaré avant la définition de classe associée.  Cet argument utilise toujours la représentation de pointeur spécifiée par l'argument *most\-general\-representation*.  Équivaut à \/vmg.|  
|**best\_case**|Génère un code sécurisé et optimal à l'aide de la représentation préférentielle pour tous les pointeurs vers des membres.  Nécessite de définir la classe avant de déclarer un pointeur vers un membre de la classe.  La valeur par défaut est **best\_case**.|  
  
 L'argument *most\-general\-representation* spécifie la plus petite représentation de pointeur que le compilateur peut utiliser sans risque pour référencer n'importe quel pointeur vers un membre d'une classe d'une unité de traduction.  L'argument peut être l'un des arguments suivants :  
  
|Argument|Commentaires|  
|--------------|------------------|  
|**single\_inheritance**|La représentation la plus générale est la fonction pointeur vers fonction membre héritage simple.  Génère une erreur si le modèle d'héritage d'une définition de classe pour laquelle un pointeur vers un membre est déclaré est de type multiple ou virtuel.|  
|**multiple\_inheritance**|La représentation la plus générale est la fonction pointeur vers fonction membre héritage multiple.  Génère une erreur si le modèle d'héritage d'une définition de classe pour laquelle un pointeur vers un membre est déclaré est de type virtuel.|  
|**virtual\_inheritance**|La représentation la plus générale est la fonction pointeur vers fonction membre héritage virtuel.  Ne génère jamais d'erreur.  Il s'agit de l'argument par défaut lorsque **\#pragma pointers\_to\_members\(full\_generality\)** est utilisé.|  
  
> [!CAUTION]
>  Nous vous recommandons d'insérer le pragma `pointers_to_members` uniquement dans le fichier de code source que vous souhaitez affecter, et uniquement après les directives `#include`.  Cette pratique atténue le risque que le pragma affecte d'autres fichiers et que vous spécifiiez par erreur plusieurs définitions pour la même variable, la même fonction ou le même nom de classe.  
  
## Exemple  
  
```  
//   Specify single-inheritance only  
#pragma pointers_to_members( full_generality, single_inheritance )  
```  
  
## FIN de la section spécifique à C\+\+  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)