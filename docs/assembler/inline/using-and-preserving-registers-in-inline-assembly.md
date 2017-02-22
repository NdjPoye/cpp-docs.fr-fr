---
title: "Utilisation et conservation des registres dans l&#39;assembly inline | Microsoft Docs"
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
  - "__asm (mot clé) (C++), valeurs des registres"
  - "assembleur inline, registres"
  - "conserver les registres"
  - "registres, assembleur inline"
ms.assetid: dbcd7360-6f3e-4b22-9ee2-9f65ca6f2543
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Utilisation et conservation des registres dans l&#39;assembly inline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Spécifique à Microsoft  
 En règle générale, vous ne devez pas considérer qu'une valeur donnée dans un Registre lorsqu'un  `__asm`bloc commence.  Ne sont pas garantis que les valeurs de registres être conservé dans distinct  `__asm`blocs.  Si vous mettre fin à un bloc de code en ligne et en commencer une autre, vous ne pouvez pas compter sur les caisses enregistreuses dans le deuxième bloc de conserver leurs valeurs à partir du premier bloc.  Un  `__asm`bloc hérite quelle que soit enregistrer le résultat de valeurs à partir du flux de contrôle normal.  
  
 Si vous utilisez la  `__fastcall`convention d'appel, le compilateur passe les arguments de fonction dans des registres plutôt sur la pile.  Cela peut créer des problèmes dans les fonctions avec  `__asm`bloque parce qu'une fonction n'a aucun moyen de savoir quel paramètre est dans le Registre.  Si la fonction se produit à recevoir un paramètre dans le registre EAX et immédiatement stocke quelque chose d'autre dans le registre EAX, le paramètre d'origine est perdu.  En outre, vous devez conserver le Registre ECX dans n'importe quelle fonction déclarée avec  `__fastcall`.  
  
 Pour éviter de tels conflits de Registre, n'utilisez pas la  `__fastcall`convention pour les fonctions qui contiennent un  `__asm`bloc.  Si vous spécifiez la  `__fastcall`convention globalement avec l'option de compilateur\/GR, déclarez chaque fonction contenant un  `__asm`bloc avec  `__cdecl`ou   `__stdcall`.  \(Le  `__cdecl`attribut indique au compilateur d'utiliser la convention d'appel C pour cette fonction.\) Si vous compilez pas avec\/GR, évitez de déclarer la fonction avec le  `__fastcall`attribut.  
  
 Lorsque vous utilisez  `__asm`pour écrire du langage d'assemblage dans les fonctions C\/C\+\+, vous n'avez pas besoin de conserver les registres EAX, EBX, ECX, EDX, ESI ou EDI.  Par exemple, dans le POWER2.Exemple de C dans  [Écriture des fonctions avec un Inline Assembly](../../assembler/inline/writing-functions-with-inline-assembly.md), la  `power2`fonction ne préserve pas la valeur dans le registre EAX.  Toutefois, à l'aide de ces registres affectera la qualité du code parce que l'allocateur de Registre ne peut pas les utiliser pour stocker des valeurs entre  `__asm`blocs.  En outre, à l'aide de EBX, ESI ou EDI en code assembleur inline, vous forcez le compilateur à enregistrer et restaurer ces registres dans le prologue de fonction et un épilogue.  
  
 Conservez autres registres que vous utilisez \(DS, SS, SP, BP et registres d'indicateurs\) de l'étendue de la  `__asm`bloc.  Conservez les registres ESP et EBP à moins d'avoir une raison de les modifier \(pour changer les piles, par exemple\).  Voir aussi  [Optimiser un Inline Assembly](../../assembler/inline/optimizing-inline-assembly.md).  
  
 Certains types de SSE nécessitent alignement de pile de huit octets, forçant le compilateur à émettre du code pile\-alignement dynamique.  Pour être en mesure d'accéder aux variables locales et les paramètres de fonction après l'alignement, le compilateur gère deux pointeurs de frame.  Si le compilateur exécute l'omission du pointeur frame \(FPO\), il utilisera EBP et ESP.  Si le compilateur n'effectue pas de FPO, il utilisera EBX et EBP.  Pour vérifier le code s'exécute correctement, ne modifiez pas EBX dans code asm si la fonction nécessite un alignement pile dynamiques qu'il pourrait modifier le pointeur de frame.  Déplacez les types alignés 8 octets en dehors de la fonction ou évitez d'utiliser EBX.  
  
> [!NOTE]
>  Si votre code d'assembly inline change l'indicateur de direction en suivant les instructions STD ou CLD, vous devez restaurer l'indicateur sur sa valeur d'origine.  
  
 **FIN spécifique à Microsoft**  
  
## Voir aussi  
 [Assembleur inline](../../assembler/inline/inline-assembler.md)