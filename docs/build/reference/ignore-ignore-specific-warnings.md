---
title: "/IGNORE (ignorer des avertissements sp&#233;cifiques) | Microsoft Docs"
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
  - "/ignore"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/IGNORE, option de l'éditeur de liens"
ms.assetid: 37e77387-8838-4697-898f-d376ac641124
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /IGNORE (ignorer des avertissements sp&#233;cifiques)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/IGNORE:warning[,warning]  
```  
  
## Paramètres  
 `warning`  
 Numéro d'avertissement de l'éditeur de liens à supprimer, dans la plage 4 000 à 4 999.  
  
## Notes  
 Par défaut, LINK signale tous les avertissements.  Spécifiez **\/IGNORE:**`warning` pour indiquer à l'éditeur de liens de supprimer un numéro d'avertissement spécifique.  Pour ignorer plusieurs avertissements, séparez les numéros d'avertissements avec des virgules.  
  
 L'éditeur de liens ne permet pas d'ignorer certains avertissements.  Le tableau suivant répertorie les avertissements qui ne sont pas supprimés par **\/IGNORE** :  
  
|Avertissement de l'éditeur de liens||  
|-----------------------------------------|-|  
|LNK4017|Instruction `keyword` non prise en charge pour la plateforme cible ; ignorée|  
|[LNK4044](../../error-messages/tool-errors/linker-tools-warning-lnk4044.md)|option '`option`' non reconnue ; ignorée|  
|LNK4062|'`option`' non compatible avec l'ordinateur cible '`architecture`' ; option ignorée|  
|[LNK4075](../../error-messages/tool-errors/linker-tools-warning-lnk4075.md)|"`option1`" ignoré à cause de la spécification "`option2`"|  
|[LNK4086](../../error-messages/tool-errors/linker-tools-warning-lnk4086.md)|'`function`' de point d'entrée n'est pas \_\_stdcall avec des arguments de '`number`' octets ; l'image risque de ne pas s'exécuter|  
|LNK4088|image en cours de génération à cause de l'option \/FORCE ; l'image risque de ne pas s'exécuter|  
|[LNK4105](../../error-messages/tool-errors/linker-tools-warning-lnk4105.md)|aucun argument spécifié avec l'option '`option`' ; commutateur ignoré|  
|LNK4203|erreur lors de la lecture de la base de données '`filename`' du programme ; édition de liens des objets comme s'il n'y avait aucune information de débogage|  
|[LNK4204](../../error-messages/tool-errors/linker-tools-warning-lnk4204.md)|'`filename`' n'a pas d'informations de débogage pour référencer le module ; édition de liens des objets comme s'il n'y avait aucune information de débogage|  
|[LNK4205](../../error-messages/tool-errors/linker-tools-warning-lnk4205.md)|'`filename`' n'a pas d'informations de débogage en cours pour référencer le module ; édition de liens des objets comme s'il n'y avait aucune information de débogage|  
|[LNK4206](../../error-messages/tool-errors/linker-tools-warning-lnk4206.md)|informations sur le type précompilé introuvables ; '`filename`' non lié ou remplacé ; édition de liens des objets comme s'il n'y avait aucune information de débogage|  
|LNK4207|'`filename`' compilé avec \/Yc \/Yu \/Z7 ; impossible de créer le PDB ; recompilez avec \/Zi ; édition de liens des objets comme s'il n'y avait aucune information de débogage|  
|LNK4208|format PDB non compatible dans '`filename`' ; supprimez\-le et régénérez ; édition de liens des objets comme s'il n'y avait aucune information de débogage|  
|LNK4209|informations de débogage endommagées ; recompilez le module ; édition de liens des objets comme s'il n'y avait aucune information de débogage|  
|[LNK4224](../../error-messages/tool-errors/linker-tools-warning-lnk4224.md)|`option` n'est plus pris en charge ; ignoré|  
|LNK4228|'`option`' non valide pour une DLL ; ignoré|  
|[LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)|directive \/`directive` non valide rencontrée ; ignorée|  
  
 En règle générale, les avertissements de l'éditeur de liens qui ne peuvent pas être ignorés correspondent à des échecs de génération, des erreurs de ligne de commande ou des erreurs de configuration que vous devez corriger.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Dans le dossier **Éditeur de liens**, sélectionnez la page de propriétés **Ligne de commande**.  
  
3.  Modifiez la propriété **Options supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programmation  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.