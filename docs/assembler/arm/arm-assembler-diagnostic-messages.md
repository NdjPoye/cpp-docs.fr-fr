---
title: "ARM Assembler Diagnostic Messages | Microsoft Docs"
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
ms.assetid: 52b38267-6023-4bdc-a0ef-863362f48eec
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ARM Assembler Diagnostic Messages
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'assembleur ARM de Microsoft \(*armasm*\) émet des erreurs et avertissements Diagnostics lorsqu'il les rencontre.  Cet article décrit les messages plus couramment rencontrés.  
  
## Syntaxe  
  
```  
  
filename(lineno) : [error|warning] Anum: message  
```  
  
## Messages de diagnostic  
  
### Erreurs  
 A2193 : cette instruction génère un comportement imprévisible  
 L'architecture ARM ne peut pas garantir que se passe\-t\-il lorsque cette instruction est exécutée.  Pour plus d'informations sur les formulaires bien définies de cette instruction, consultez le [Manuel de référence d'Architecture ARM](http://go.microsoft.com/fwlink/?LinkId=246464).  
  
```  
  
ADD r0, r8, pc         ; A2193: this instruction generates unpredictable behavior  
  
```  
  
 A2196 : instruction ne peut pas être codée en 16 bits  
 L'instruction spécifiée ne peut pas être codée comme une instruction de curseur de défilement de 16 bits.  Spécifiez une instruction de 32 bits, ou réorganiser le code pour faire apparaître l'étiquette cible dans la plage d'une instruction de 16 bits.  
  
 L'assembleur peut tenter de coder une branche en 16 bits et échouer avec cette erreur, même si une branche 32 bits est codables par.  Vous pouvez résoudre ce problème en utilisant la `.W` spécificateur pour marquer explicitement la branche en tant que 32 bits.  
  
```  
  
  ADD.N r0, r1, r2      ; A2196: instruction cannot be encoded in 16 bits  
  
  B.W label             ; OK  
  B.N label             ; A2196: instruction cannot be encoded in 16 bits  
  SPACE 10000  
label  
  
```  
  
 A2202 : Syntaxe d'instruction Pre\-UEL ne pas autorisé dans la région THUMB  
 Le code Thumb doit utiliser la syntaxe de la langue unifiée de l'assembleur \(UEL\).  L'ancienne syntaxe n'est plus acceptée  
  
```  
  
ADDEQS r0, r1         ; A2202: Pre-UAL instruction syntax not allowed in THUMB region  
ADDSEQ r0, r1         ; OK  
  
```  
  
 A2513 : Rotation doit être pair  
 En mode ARM, il existe une autre syntaxe pour spécifier les constantes.  Au lieu d'écrire `#<const>`, vous pouvez écrire `#<byte>,#<rot>`, qui représente la valeur de constante est obtenue en faisant tourner la valeur `<byte>` vers la droite du `<rot>`.  Lorsque vous utilisez cette syntaxe, vous devez rendre la valeur de `<rot>` même.  
  
```  
  
MOV r0, #4, #2       ; OK  
MOV r0, #4, #1       ; A2513: Rotation must be even  
  
```  
  
 A2557 : Le nombre Incorrect d'octets à écriture différée  
 Sur la structure de néon instructions load et store \(`VLDn`, `VSTn`\), il existe une autre syntaxe pour la spécification d'écriture différée pour le Registre de base.  Plutôt que de placer un point d'exclamation \(\!\) après l'adresse, vous pouvez spécifier une valeur immédiate qui indique le décalage à ajouter au livre de base.  Si vous utilisez cette syntaxe, vous devez spécifier le nombre exact d'octets qui ont été chargées ou enregistrées par l'instruction.  
  
```  
  
VLD1.8 {d0-d3}, [r0]!         ; OK  
VLD1.8 {d0-d3}, [r0], #32     ; OK  
VLD1.8 {d0-d3}, [r0], #100    ; A2557: Incorrect number of bytes to write back  
  
```  
  
### Avertissements  
 A4228 : Valeur d'alignement dépasse l'alignement de zone ; alignement non garantie  
 L'alignement spécifié dans une `ALIGN` la directive est supérieure à l'alignement de l'englobants `AREA`.  Par conséquent, l'assembleur ne garantit pas que le `ALIGN` la directive sera respectée.  
  
 Pour résoudre ce problème, vous pouvez spécifier sur la `AREA` directive une `ALIGN` attribut est égale ou supérieure à l'alignement souhaité.  
  
```  
  
AREA |.myarea1|  
ALIGN 8           ; A4228: Alignment value exceeds AREA alignment; alignment not guaranteed  
  
AREA |.myarea2|,ALIGN=3  
ALIGN 8           ; OK  
  
```  
  
 A4508 : Utilisation de cette constante pivotée est déconseillée.  
 En mode ARM, il existe une autre syntaxe pour spécifier les constantes.  Au lieu d'écrire `#<const>`, vous pouvez écrire `#<byte>,#<rot>`, qui représente la valeur de constante est obtenue en faisant tourner la valeur `<byte>` vers la droite du `<rot>`.  Dans certains contextes, ARM a désapprouvé l'utilisation de ces constantes pivotés.  Dans ce cas, utilisez le basic `#<const>` syntaxe à la place.  
  
```  
  
ANDS r0, r0, #1                ; OK  
ANDS r0, r0, #4, #2            ; A4508: Use of this rotated constant is deprecated  
  
```  
  
 A4509 : Cette forme d'instruction conditionnelle est déconseillée.  
 Cette forme d'instruction conditionnelle a été désapprouvée par le ARM dans l'architecture ARMv8.  Nous recommandons que vous modifiez le code pour utiliser des branches conditionnelles.  Pour consulter les instructions conditionnelles sont toujours supportées, consultez le [Manuel de référence d'Architecture ARM](http://go.microsoft.com/fwlink/?LinkId=246464).  
  
 Cet avertissement n'est pas émise lorsque le  `- oldit` commutateur de ligne de commande est utilisée.  
  
```  
  
ADDEQ r0, r1, r8              ; A4509: This form of conditional instruction is deprecated  
  
```  
  
## Voir aussi  
 [ARM Assembler Command\-Line Reference](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM Assembler Directives](../../assembler/arm/arm-assembler-directives.md)