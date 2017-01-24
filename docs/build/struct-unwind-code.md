---
title: "struct UNWIND_CODE | Microsoft Docs"
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
ms.assetid: 104955d8-7e33-4c5a-b0c6-3254648f0af3
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# struct UNWIND_CODE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le tableau des codes de déroulement permet d'enregistrer la séquence d'opérations dans le prologue qui affectent les registres non volatils et RSP.  Chaque élément de code possède le format suivant :  
  
|||  
|-|-|  
|UBYTE|Offset dans le prologue|  
|UBYTE: 4|Code d'opération de déroulement|  
|UBYTE: 4|Information sur l'opération|  
  
 Le tableau est trié par ordre décroissant d'offset dans le prologue.  
  
 **Offset dans le prologue**  
 Offset à partir du début du prologue de la fin de l'instruction qui exécute cette opération, plus 1 \(c'est\-à\-dire l'offset du début de l'instruction suivante\).  
  
 **Code d'opération de déroulement**  
 Remarque : certains codes d'opération exigent un offset non signé à une valeur située dans le frame de pile local.  Cet offset s'effectue à partir du début \(adresse la plus basse\) de l'allocation de pile fixe.  Si le champ du registre du frame de UNWIND\_INFO a la valeur zéro, cet offset s'effectue à partir de RSP.  Si le champ du registre du frame est différent de zéro, il s'agit de l'offset à partir de l'emplacement où se situait RSP lors de l'établissement du registre FP.  Cela équivaut au registre FP moins l'offset du registre FP \(16 \* l'offset du registre du frame mis à l'échelle dans UNWIND\_INFO\).  Si un registre FP est utilisé, tout code de déroulement prenant un offset ne doit être utilisé qu'après l'établissement du registre FP dans le prologue.  
  
 Pour tous les ocpodes à l'exception de UWOP\_SAVE\_XMM128 et UWOP\_SAVE\_XMM128\_FAR, l'offset est toujours un multiple de 8, car toutes les valeurs de la pile dignes d'intérêt sont stockées sur les limites de 8 octets \(la pile proprement dite est toujours alignée sur 16 octets\).  Pour les codes d'opération qui prennent un offset court \(inférieur à 512K\), le dernier USHORT dans les nœuds pour ce code conserve l'offset divisé par 8.  Pour les codes d'opération qui prennent un long offset \(512K \< \= offset \< 4Go\), les deux nœuds USHORT de fin pour ce code conserve l'offset \(au format avec primauté des octets de poids faible \(little\-endian\)\).  
  
 Pour les opcodes UWOP\_SAVE\_XMM128 et UWOP\_SAVE\_XMM128\_FAR, l'offset est toujours un multiple de 16, car toutes les opérations XMM de 128 bits doivent se produire sur de la mémoire alignée sur 16 octets.  Par conséquent, un facteur d'échelle de 16 est utilisé pour UWOP\_SAVE\_XMM128, autorisant ainsi des offsets inférieurs à 1 Mo.  
  
 Le code d'opération de déroulement est l'un des suivants :  
  
 Nœud UWOP\_PUSH\_NONVOL \(0\)1  
  
 Poussez un registre entier non volatil, en décrémentant RSP de 8.  L'information sur l'opération est numéro du registre.  Remarquez qu'en raison des contraintes sur les épilogues, les codes de déroulement UWOP\_PUSH\_NONVOL doivent apparaître en premier dans le prologue et également en dernier dans le tableau des codes de déroulement.  Ce classement relatif s'applique à tout autre code de déroulement, à l'exception de UWOP\_PUSH\_MACHFRAME.  
  
 Nœuds UWOP\_ALLOC\_LARGE \(1\)2 ou 3  
  
 Allouez une zone étendue sur la pile.  Deux formats sont disponibles.  Si l'information sur l'opération est égale à 0, la taille de l'allocation divisée par 8 est enregistrée dans l'emplacement suivant, en autorisant une allocation jusqu'à 512K – 8.  Si l'information sur l'opération est égale à 1, la taille non ajustée de l'allocation est enregistrée dans les deux emplacements suivants au format avec primauté des octets de poids faible \(little\-endian\), ce qui permet les allocations jusqu'à 4Go – 8.  
  
 Nœud UWOP\_ALLOC\_SMALL \(2\)1  
  
 Allouez une zone de petite taille sur la pile.  La taille de l'allocation est le champ de l'information sur l'opération \* 8 \+ 8, autorisant les allocations de 8 à 128 octets.  
  
 Le code de déroulement pour une pile d'allocation doit toujours utiliser l'encodage le plus court possible :  
  
|||  
|-|-|  
|**Taille d'allocation**|**Code de déroulement**|  
|8 à 128 octets|UWOP\_ALLOC\_SMALL|  
|136 à 512 Ko \- 8 octets|UWOP\_ALLOC\_LARGE, information sur l'opération \= 0|  
|512 Ko à 4 Go \- 8 octets|UWOP\_ALLOC\_LARGE, information sur l'opération \= 1|  
  
 Nœud UWOP\_SET\_FPREG \(3\)1  
  
 Établissez le registre du pointeur de frame le définissant à un certain offset du RSP actuel.  L'offset est égal au champ de l'offset du registre de frame \(mis à l'échelle\) dans UNWIND\_INFO \* 16, ce qui permet des offsets de 0 à 240.  L'utilisation d'un offset autorise l'établissement d'un pointeur de frame qui pointe sur le milieu de l'allocation de pile fixe, en aidant la densité de code en permettant à plus d'accès d'utiliser des formulaires d'instruction courts.  Notez que le champ de l'information sur l'opération est réservé et ne doit pas être utilisé.  
  
 Nœud UWOP\_SAVE\_NONVOL \(4\)2  
  
 Enregistrez un registre entier non volatil sur la pile à l'aide de MOV plutôt que de PUSH.  Cela est principalement utilisé pour l'emballage, lorsqu'un registre non volatil est enregistré sur la pile à une position allouée précédemment.  L'information sur l'opération est numéro du registre.  L'offset de pile mis à l'échelle par 8 est enregistré à l'emplacement de code d'opération de déroulement suivant, comme décrit dans la remarque ci\-dessus.  
  
 Nœuds UWOP\_SAVE\_NONVOL\_FAR \(5\)3  
  
 Enregistrez un registre entier non volatil sur la pile avec un offset long, à l'aide de MOV plutôt que de PUSH.  Cela est principalement utilisé pour l'emballage, lorsqu'un registre non volatil est enregistré sur la pile à une position allouée précédemment.  L'information sur l'opération est numéro du registre.  L'offset de pile non mis à l'échelle est enregistré aux deux emplacements de code d'opération de déroulement suivants, comme décrit dans la remarque ci\-dessus.  
  
 Nœuds UWOP\_SAVE\_XMM128 \(8\)2  
  
 Enregistrez les 128 bits d'un registre XMM non volatil sur la pile.  L'information sur l'opération est numéro du registre.  L'offset de pile mis à l'échelle par 16 est enregistré à l'emplacement suivant.  
  
 Nœuds UWOP\_SAVE\_XMM128\_FAR \(9\)3  
  
 Enregistrez les 128 bits d'un registre XMM non volatil sur la pile avec un offset long.  L'information sur l'opération est numéro du registre.  L'offset de pile non mis à l'échelle est enregistré aux deux emplacements suivants.  
  
 Nœud UWOP\_PUSH\_MACHFRAME \(10\)1  
  
 Effectuez un push sur un frame d'ordinateur.  Cela permet d'enregistrer l'effet d'une interruption ou d'une exception matérielle.  Deux formats sont disponibles.  Si l'information sur l'opération a la valeur 0, les éléments suivants ont fait l'objet d'un push sur la pile :  
  
|||  
|-|-|  
|RSP\+32|SS|  
|RSP\+24|Ancien RSP|  
|RSP\+16|EFLAGS|  
|RSP\+8|CS|  
|RSP|RIP|  
  
 Si l'information sur l'opération a la valeur 1, les éléments suivants ont fait l'objet d'un push :  
  
|||  
|-|-|  
|RSP\+40|SS|  
|RSP\+32|Ancien RSP|  
|RSP\+24|EFLAGS|  
|RSP\+16|CS|  
|RSP\+8|RIP|  
|RSP|Code de l'erreur|  
  
 Ce code de déroulement s'affiche toujours dans un prologue factice. Il 'est jamais exécuté réellement, mais apparaît plutôt avant le véritable point d'entrée d'une routine d'interruption et n'existe que dans le but de fournir un endroit auquel simuler l'opération push d'un frame d'ordinateur.  UWOP\_PUSH\_MACHFRAME enregistre cette simulation, ce qui indique que l'ordinateur a procédé conceptuellement comme suit :  
  
 Exécution d'un pop sur l'adresse de retour de RIP à partir du haut de la pile dans *Temp*  
  
 Exécution d'un push de SS  
  
 Exécution d'un push de l'ancien RSP  
  
 Exécution d'un push de EFLAGS  
  
 Exécution d'un push de CS  
  
 Exécution d'un push de *Temp*  
  
 Exécution d'un push du code d'erreur \(si l'information sur l'opération a la valeur 1\)  
  
 L'opération UWOP\_PUSH\_MACHFRAME simulée décrémente RSP de 40 \(l'information sur l'opération a la valeur 0\) ou de 48 \(l'information sur l'opération a la valeur 1\).  
  
 **Information sur l'opération**  
 La signification de ces 4 bits dépend du code d'opération.  Pour encoder un registre à usage général \(entier\), le mappage suivant est utilisé :  
  
|||  
|-|-|  
|0|RAX|  
|1|RCX|  
|2|RDX|  
|3|RBX|  
|4|RSP|  
|5|RBP|  
|6|RSI|  
|7|RDI|  
|8 à 15|R8 to R15|  
  
## Voir aussi  
 [Données de déroulement pour la gestion des exceptions et la prise en charge du débogueur](../build/unwind-data-for-exception-handling-debugger-support.md)