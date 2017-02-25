---
title: "Prologue et &#233;pilogue | Microsoft Docs"
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
ms.assetid: 0453ed1a-3ff1-4bee-9cc2-d6d3d6384984
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Prologue et &#233;pilogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Chaque fonction qui alloue l'espace de pile, appelle d'autres fonctions, enregistre des registres non volatils ou utilise la gestion des exceptions doit posséder un prologue dont les limites d'adresse sont décrites dans les données de déroulement associées à l'entrée de table de fonctions respective \(consultez [Gestion des exceptions \(x64\)](../build/exception-handling-x64.md)\).  Le cas échéant, le prologue enregistre des registres d'arguments dans leurs adresses personnelles, émet des registres non volatils sur la pile, alloue la partie fixe de la pile pour des variables locales et temporaires, et établit éventuellement un pointeur de frame.  Les données de déroulement associées doivent décrire l'action du prologue et fournir les informations nécessaires à l'annulation de l'effet du code de prologue.  
  
 Si l'allocation fixe dans la pile comprend plusieurs pages \(c'est\-à\-dire est supérieure à 4 096 octets\), il est possible que la pile d'allocation couvre plusieurs pages de mémoire virtuelle ; par conséquent, l'allocation doit être vérifiée avant d'être réellement exécutée.  Une routine spéciale pouvant être appelée par le prologue et qui ne détruit aucun des registres d'arguments est fournie à cette fin.  
  
 La méthode recommandée pour enregistrer des registres non volatils consiste à les déplacer sur la pile avant l'allocation de pile fixe.  Si l'allocation de pile fixe a été exécutée avant l'enregistrement des registres non volatils, un offset de 32 bits sera probablement requis pour adresser la zone de registre enregistrée \(il semble que les push de registre sont aussi rapides que les déplacements et devraient le rester dans un futur prévisible malgré la dépendance implicite entre les push\).  Les registres non volatils peuvent être enregistrés dans n'importe quel ordre.  Toutefois, la première utilisation d'un registre non volatil dans le prologue doit être son enregistrement.  
  
 Le code d'un prologue standard peut être le suivant :  
  
```  
mov       [RSP + 8], RCX  
push   R15  
push   R14  
push   R13  
sub      RSP, fixed-allocation-size  
lea      R13, 128[RSP]  
...  
```  
  
 Ce prologue stocke le registre d'arguments RCX à sa position initiale, enregistre les registres non volatils R13\-R15, alloue la partie fixe du frame de pile et établit un pointeur de frame désignant 128 octets dans la zone d'allocation fixe.  L'utilisation d'un offset permet d'adresser une plus grande partie de la zone d'allocation fixe à l'aide d'offsets d'un octet.  
  
 Si la taille d'allocation fixe est supérieure ou égale à une page de mémoire, une fonction d'assistance doit être appelée avant de modifier RSP.  Cette application d'assistance, \_\_chkstk, est chargée d'analyser la plage de la pile à allouer afin de garantir que la pile est correctement étendue.  Dans ce cas, l'exemple de prologue précédent serait plutôt le suivant :  
  
```  
mov       [RSP + 8], RCX  
push   R15  
push   R14  
push   R13  
mov      RAX,  fixed-allocation-size  
call   __chkstk  
sub      RSP, RAX  
lea      R13, 128[RSP]  
...  
```  
  
 L'application d'assistance \_\_chkstk ne modifie aucun registre autre que R10, R11 et les indicateurs d'état.  En particulier, il retourne RAX inchangé et ne modifie aucun des registres non volatils et des registres qui passent des arguments.  
  
 Un code d'épilogue se trouve à chaque sortie vers une fonction.  Même s'il n'existe normalement qu'un seul prologue, il peut en exister un grand nombre.  Le code d'épilogue découpe la pile à sa taille d'allocation fixe \(le cas échéant\), libère la pile allocation fixe, restaure des registres non volatils en dépilant leurs valeurs enregistrées et retourne.  
  
 Le code d'épilogue doit respecter un jeu de règles strict pour permettre au code de déroulement de se dérouler de manière fiable à l'aide d'exceptions et d'interruptions.  Cela réduit la quantité de données de déroulement requise, car aucune donnée supplémentaire n'est nécessaire pour décrire chaque épilogue.  Par contre, le code de déroulement peut déterminer qu'un épilogue est en cours d'exécution en analysant un flux de code afin d'identifier un épilogue.  
  
 Si aucun pointeur de frame n'est utilisé dans la fonction, l'épilogue doit d'abord libérer la partie fixe de la pile, les registres non volatils sont dépilés et le contrôle est retourné à la fonction appelante.  Par exemple :  
  
```  
add      RSP, fixed-allocation-size  
pop      R13  
pop      R14  
pop      R15  
ret  
```  
  
 Si un pointeur de frame est utilisé dans la fonction, la pile doit être tronquée à son allocation fixe avant l'exécution de l'épilogue.  D'un point de vue technique, cela ne fait pas partie de l'épilogue.  Par exemple, l'épilogue suivant peut être utilisé pour annuler le prologue utilisé précédemment :  
  
```  
lea      RSP, -128[R13]  
; epilogue proper starts here  
add      RSP, fixed-allocation-size  
pop      R13  
pop      R14  
pop      R15  
ret  
```  
  
 Sur le plan pratique, lorsqu'un pointeur de frame est utilisé, il n'existe aucune bonne raison d'ajuster RSP en deux étapes. L'épilogue suivant est donc utilisé à la place :  
  
```  
lea      RSP, fixed-allocation-size – 128[R13]  
pop      R13  
pop      R14  
pop      R15  
ret  
```  
  
 Ce sont les seules formes légales d'un épilogue.  Il doit se composer de `add RSP,constant` ou `lea RSP,constant[FPReg]`, suivi d'une série de zéro ou davantage de dépilements de registres de 8 octets et un retour ou une instruction jmp.  \(Seul un sous\-ensemble d'instructions jmp est autorisé dans l'épilogue.  Il s'agit exclusivement de la classe de jmps avec les références mémoires ModRM où la valeur de champ modifiée ModRM est 00.  L'utilisation de jmps dans l'épilogue avec la valeur de champ mod ModRM 01 ou 10 est interdite.  Pour plus d'informations sur les références ModRM autorisées, consultez le Tableau A\-15 du volume 3 du manuel « AMD x86\-64 Architecture Programmer's Manual » : General Purpose and System Instructions.\)  Aucun autre code ne peut s'afficher.  En particulier, rien ne peut être planifié dans un épilogue, y compris le chargement d'une valeur de retour.  
  
 Notez que, lorsqu'un pointeur de frame n'est pas utilisé, l'épilogue doit utiliser `add RSP,constant` pour libérer la partie fixe de la pile.  Il ne peut pas utiliser `lea RSP,constant[RSP]` à la place.  Cette restriction a pour objectif de réduire le nombre de motifs à reconnaître par le code de déroulement lors de la recherche d'épilogues.  
  
 Le respect de ces règles permet au code de déroulement de déterminer qu'un épilogue est actuellement exécuté et de simuler l'exécution du reste de l'épilogue afin d'autoriser la recréation du contexte de la fonction appelante.  
  
## Voir aussi  
 [Conventions des logiciels x64](../build/x64-software-conventions.md)