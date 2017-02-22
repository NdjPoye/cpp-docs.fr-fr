---
title: "/MANIFESTUAC (Incorporer des informations sur le contr&#244;le de compte d&#39;utilisateur dans le manifeste) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.UACUIAccess"
  - "VC.Project.VCLinkerTool.UACExecutionLevel"
  - "VC.Project.VCLinkerTool.EnableUAC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/MANIFESTUAC (option de l'Éditeur de liens)"
  - "MANIFESTUAC (option de l'Éditeur de liens)"
  - "-MANIFESTUAC (option de l'Éditeur de liens)"
ms.assetid: 2d243c39-fa13-493c-b56f-d0d972a1603a
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# /MANIFESTUAC (Incorporer des informations sur le contr&#244;le de compte d&#39;utilisateur dans le manifeste)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Spécifie si les informations de contrôle de compte d'utilisateur \(UAC, User Account Control\) sont incorporées dans le manifeste de programme.  
  
## Syntaxe  
  
```  
/MANIFESTUAC  
/MANIFESTUAC:NO  
/MANIFESTUAC:fragment  
/MANIFESTUAC:level=_level  
/MANIFESTUAC:uiAccess=_uiAccess  
```  
  
#### Paramètres  
 `fragment`  
 Chaîne qui contient les valeurs `level` et `uiAccess`.  Pour plus d'informations, consultez la section « Notes » plus loin dans cette rubrique.  
  
 `_level`  
 Un des niveaux *asInvoker*, *highestAvailable* ou *requireAdministrator*.  La valeur par défaut est asInvoker.  Pour plus d'informations, consultez la section « Notes » plus loin dans cette rubrique.  
  
 `_uiAccess`  
 `true` si vous souhaitez que l'application ignore les niveaux de protection de l'interface utilisateur et exécute l'entrée vers des fenêtres d'autorisations supérieures sur le Bureau \(par exemple un clavier visuel\) ; dans le cas contraire, `false`.  La valeur par défaut est `false`.  Affectez `true` uniquement pour les applications d'accessibilité de l'interface utilisateur.  
  
## Notes  
 Si vous spécifiez des options \/MANIFESTUAC multiples sur la ligne de commande, la dernière entrée est prioritaire.  
  
 Les choix pour \/MANIFESTUAC:level sont les suivants :  
  
-   `asInvoker` : l'application s'exécute avec les mêmes autorisations que le processus qui l'a démarrée.  L'application peut être élevée à un niveau d'autorisation supérieur en sélectionnant **Exécuter en tant qu'administrateur**.  
  
-   highestAvailable : l'application s'exécute avec le niveau d'autorisation le plus élevé possible.  Si l'utilisateur qui démarre l'application est membre du groupe Administrateurs, cette option est la même que requireAdministrator.  Si le niveau d'autorisation disponible le plus élevé est supérieur au niveau du processus d'ouverture, le système invitera à entrer les informations d'identification.  
  
-   requireAdministrator : l'application s'exécute avec des autorisations d'administrateur.  L'utilisateur qui démarre l'application doit être membre du groupe Administrateurs.  Si le processus d'ouverture ne s'exécute pas avec des autorisations d'administrateur, le système invitera à entrer les informations d'identification.  
  
 Vous pouvez spécifier le niveau et les valeurs uiAccess en une étape en utilisant l'option \/MANIFESTUAC:fragment.  Le fragment doit prendre la forme suivante :  
  
```  
"level=[ asInvoker | highestAvailable | requireAdministrator ] uiAccess=[ true | false ]"  
```  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Comment : ouvrir les pages de propriétés d'un projet](../../misc/how-to-open-project-property-pages.md).  
  
2.  Développez le nœud **Propriétés de configuration**.  
  
3.  Développez le nœud **Éditeur de liens**.  
  
4.  Sélectionnez la page de propriétés **Fichier manifeste**.  
  
5.  Modifiez les propriétés **Activer le Contrôle de compte d'utilisateur**, **Niveau d'exécution UAC** et **Ignorer la protection UI UAC**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
1.  Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.EnableUAC%2A>, <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACExecutionLevel%2A> et <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.UACUIAccess%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)