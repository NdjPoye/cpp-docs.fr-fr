---
title: "/VERBOSE (Imprimer les messages d&#39;avancement) | Microsoft Docs"
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
  - "/verbose"
  - "VC.Project.VCLinkerTool.ShowProgress"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/VERBOSE (option de l'éditeur de liens)"
  - "dépendances (C++), informations de dépendance dans la sortie de l'éditeur de liens"
  - "éditeur de liens (C++), informations de dépendance en sortie"
  - "liaison (C++), informations sur la progression de la session"
  - "imprimer les messages d'avancement (option de l'éditeur de liens)"
  - "VERBOSE (option de l'éditeur de liens)"
  - "-VERBOSE (option de l'éditeur de liens)"
ms.assetid: 9c347d98-4c37-4724-a39e-0983934693ab
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /VERBOSE (Imprimer les messages d&#39;avancement)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/VERBOSE[:{ICF|INCR|LIB|REF|SAFESEH|UNUSEDLIBS}]  
```  
  
## Notes  
 L'éditeur de liens envoie des informations concernant la progression de la session de liaison à la fenêtre **Sortie**.  Sur la ligne de commande, les informations sont envoyées à la sortie standard et peuvent être redirigées vers un fichier.  
  
|Option|Description|  
|------------|-----------------|  
|\/VERBOSE|Affiche des détails sur le processus de liaison.|  
|\/VERBOSE:ICF|Affiche des informations relatives aux activités de l'éditeur de liens qui résultent de l'utilisation de [\/OPT:ICF](../../build/reference/opt-optimizations.md).|  
|\/VERBOSE:INCR|Affiche des informations sur le processus incrémental de liens.|  
|\/VERBOSE:LIB|Affiche les messages de progression qui indiquent uniquement les bibliothèques recherchées.<br /><br /> Les informations affichées incluent le processus de recherche de bibliothèques et répertorient chaque bibliothèque et nom d'objet \(avec le chemin d'accès complet\), le symbole en cours de résolution dans la bibliothèque et une liste d'objets référençant le symbole.|  
|\/VERBOSE:REF|Affiche des informations relatives aux activités de l'éditeur de liens qui résultent de l'utilisation de [\/OPT:IREF](../../build/reference/opt-optimizations.md).|  
|\/VERBOSE:SAFESEH|Affiche des informations concernant les modules non compatibles avec la gestion sécurisée des exceptions lorsque [\/SAFESEH](../../build/reference/safeseh-image-has-safe-exception-handlers.md) n'est pas spécifié.|  
|\/VERBOSE:UNUSEDLIBS|Affiche des informations sur tous les fichiers bibliothèques qui ne sont pas utilisés lorsque l'image est créée.|  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Rentrez dans le dossier **Éditeur de liens**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Ajoutez l'option dans la zone **Options supplémentaires**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.ShowProgress%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)