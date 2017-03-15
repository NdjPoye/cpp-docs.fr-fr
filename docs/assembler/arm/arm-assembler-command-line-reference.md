---
title: "ARM Assembler Command-Line Reference | Microsoft Docs"
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
ms.assetid: f7b89478-1ab5-4995-8cde-a805f0462c45
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ARM Assembler Command-Line Reference
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cet article fournit des informations de ligne de commande pour l'assembleur Microsoft ARM,  *armasm*, qui compile un langage assembleur ARMv7 Thumb dans l'implémentation Microsoft de l'objet fichier Format COFF \(Common\).  L'éditeur de liens peut lier code COFF avec du code objet généré par l'assembleur ARM ou par le compilateur c avec les bibliothèques d'objets qui sont créés par le Générateur de bibliothèques.  
  
## Syntaxe  
  
```  
armasm [[options]] sourcefile objectfile  
```  
  
```  
armasm [[options]] -o objectfile sourcefile  
```  
  
#### Paramètres  
 `options`  
 \-erreurs`filename`  
 Rediriger les messages d'erreur et avertissement pour `filename`.  
  
 \-i`dir[;dir]`  
 Ajouter les répertoires spécifiés dans le chemin de recherche include.  
  
 \-prédéfinir`directive`  
 Spécifier une directive de jeu de NŒUDSUNE, SETL ou des ensembles de prédéfinir un symbole.  Par exemple : **armasm.exe \-predefine "COUNT SETA 150" source.asm** Pour plus d'informations, consultez la [guide des outils assembleur ARM](http://go.microsoft.com/fwlink/?LinkId=246102).  
  
 nowarn\-  
 Désactiver tous les messages d'avertissement.  
  
 \-Ignorer`warning`  
 Désactiver l'avertissement spécifié.  Les valeurs possibles, consultez la section à propos des avertissements.  
  
 \-aide  
 Imprimer le message d'aide de ligne de commande.  
  
 \-machine`machine`  
 Spécifier le type de machine à définir dans l'en\-tête PE.  Valeurs possibles pour `machine` sont :   
**ARM**— Définit le type de machine à IMAGE\_FILE\_MACHINE\_ARMNT.  Il s'agit de la valeur par défaut.   
**THUMB**— Définit le type de machine à IMAGE\_FILE\_MACHINE\_THUMB.  
  
 \-oldit  
 Générer ARMv7 style blocs informatique.  Par défaut, ARMv8\-compatible avec les blocs d'informatique sont générées.  
  
 \-via`filename`  
 Lire les arguments de ligne de commande supplémentaires à partir de `filename`.  
  
 \-16  
 Assembler source comme instructions de curseur de défilement de 16 bits.  Il s'agit de la valeur par défaut.  
  
 \-32  
 Assembler source pour obtenir les instructions ARM 32 bits.  
  
 \-g  
 Générer des informations de débogage.  
  
 \-\/errorreport :`option`  
 Spécifiez comment interne assembleur erreurs sont signalées à Microsoft.  Valeurs possibles pour `option` sont :   
**none**— Ne pas envoyer de rapports.   
**prompt**— Invite l'utilisateur à envoyer immédiatement des rapports.   
**queue**— Invite l'utilisateur à envoyer des rapports à la prochaine ouverture de session admin.  Il s'agit de la valeur par défaut.   
**send**— Envoyer automatiquement des rapports.  
  
 `sourcefile`  
 Le nom du fichier source.  
  
 `objectfile`  
 Le nom du fichier objet \(sortie\).  
  
 L'exemple suivant montre comment utiliser armasm dans un scénario classique.  Tout d'abord, utilisez armasm pour générer un fichier source \(.asm\) de langage d'assemblage pour un fichier objet \(.obj\).  Ensuite, utilisez le compilateur c de ligne de commande pour compiler un fichier source \(.c\) et spécifiez également l'option d'éditeur de liens pour lier le fichier objet ARM.  
  
 **armasm myasmcode.asm \-o myasmcode.obj**  
  
 **cl myccode.c \/link myasmcode.obj**  
  
## Voir aussi  
 [ARM Assembler Diagnostic Messages](../../assembler/arm/arm-assembler-diagnostic-messages.md)   
 [ARM Assembler Directives](../../assembler/arm/arm-assembler-directives.md)