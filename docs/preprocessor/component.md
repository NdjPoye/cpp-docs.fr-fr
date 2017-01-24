---
title: "composant | Microsoft Docs"
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
  - "vc-pragma.component"
  - "component_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "component (pragma)"
  - "pragmas, composant"
ms.assetid: 7b66355e-3201-4c14-8190-f4a2a81a604a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# composant
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Contrôle la collecte des informations de consultation ou les informations sur les dépendances à partir des fichiers sources.  
  
## Syntaxe  
  
```  
  
      #pragma component( browser, { on | off }[, references [, name ]] )  
#pragma component( minrebuild, on | off )  
#pragma component( mintypeinfo, on | off )  
```  
  
## Notes  
  
## Navigateur  
 Vous pouvez désactiver ou activer la collecte, et spécifier des noms particuliers à ignorer lors de la collecte d'informations.  
  
 L'utilisation de l'activation et de la désactivation contrôle la collection des informations de consultation à partir du pragma.  Par exemple :  
  
```  
#pragma component(browser, off)  
```  
  
 arrête la collecte d'informations de consultation par le compilateur.  
  
> [!NOTE]
>  Pour activer la collecte d'informations de consultation avec ce pragma, [les informations de consultation doivent d'abord être activées](../build/reference/building-browse-information-files-overview.md).  
  
 L'option **references** peut être utilisée avec ou sans l'argument *name*.  L'utilisation de **references** sans *name* active ou désactive la collecte de références \(les autres informations de consultation continuent d'être collectées\).  Par exemple :  
  
```  
#pragma component(browser, off, references)  
```  
  
 arrête la collecte d'informations de référence par le compilateur.  
  
 L'utilisation de **references** avec *name* et **off** empêche les références à *name* d'apparaître dans la fenêtre des informations de consultation.  Utilisez cette syntaxe pour ignorer les noms et les types qui ne vous intéressent pas afin de réduire la taille des fichiers d'informations de consultation.  Par exemple :  
  
```  
#pragma component(browser, off, references, DWORD)  
```  
  
 ignore les références à **DWORD** à partir de ce point.  Vous pouvez réactiver la collecte des références sur `DWORD` à l'aide de **on** :  
  
```  
#pragma component(browser, on, references, DWORD)  
```  
  
 C'est la seule façon de reprendre la collecte des références à *name*. Vous devez explicitement activer tout *name* que vous avez désactivé.  
  
 Pour empêcher le préprocesseur de développer *name* \(par exemple de développer **NULL** sur **0**\), placez des guillemets autour :  
  
```  
#pragma component(browser, off, references, "NULL")  
```  
  
## Régénération minimale  
 La fonctionnalité de régénération minimale Visual C\+\+ exige que le compilateur crée et stocke des informations sur les dépendances de classe C\+\+, ce qui occupe de l'espace sur le disque.  Pour libérer de l'espace disque, vous pouvez utiliser `#pragma component( minrebuild, off )` chaque fois que vous n'avez pas besoin de collecter les informations de dépendance, par exemple, pour les fichiers d'en\-tête qui ne changent pas.  Insérez `#pragma component(minrebuild, on)` après les classes qui ne changent pas pour réactiver la collecte de dépendances.  
  
## Réduction des informations de type  
 L'option **mintypeinfo** réduit les informations de débogage pour la zone spécifiée.  Le volume de ces informations est considérable et a un impact sur les fichiers .pdb et .obj.  Vous ne pouvez pas déboguer des classes et des structures dans la zone mintypeinfo.  L'utilisation de l'option mintypeinfo peut être utile pour éviter l'avertissement suivant :  
  
```  
LINK : warning LNK4018: too many type indexes in PDB "filename", discarding subsequent type information  
```  
  
 Pour plus d'informations, consultez l'option du compilateur [Activation de la régénération minimale](../build/reference/gm-enable-minimal-rebuild.md) \(\/Gm\).  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)