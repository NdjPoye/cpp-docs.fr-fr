---
title: "/ORDER (Mettre les fonctions dans l&#39;ordre) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCLinkerTool.FunctionOrder"
  - "/order"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/ORDER (option de l'éditeur de liens)"
  - "LINK (outil C++), optimisation de programme"
  - "LINK (outil C++), réglage de l'échange"
  - "ORDER (option de l'éditeur de liens)"
  - "-ORDER (option de l'éditeur de liens)"
  - "pagination, optimiser"
ms.assetid: ecf5eb3e-e404-4e86-9a91-4e5ec157261a
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# /ORDER (Mettre les fonctions dans l&#39;ordre)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

```  
/ORDER:@filename  
```  
  
## Paramètres  
 *filename*  
 désigne un fichier texte spécifiant l'ordre de liaison des fonctions COMDAT.  
  
## Notes  
 L'option \/ORDER indique à LINK d'optimiser votre programme en plaçant certains COMDAT dans l'image selon un ordre prédéterminé.  LINK place les fonctions dans l'ordre spécifié dans chaque section de l'image.  
  
 Spécifiez l'ordre dans l'argument *filename*, qui est un fichier texte \(fichier réponse\) répertoriant les COMDAT dans l'ordre de liaison souhaité.  Chaque ligne de l'argument *filename* contient le nom d'un COMDAT.  Un objet contient des COMDAT s'il a été compilé avec l'option \/Gy.  Les noms de fonctions respectent la casse.  
  
 LINK utilise les formes décorées des identificateurs.  Le compilateur décore un identificateur lorsqu'il crée le fichier .obj.  Utilisez l'outil [DUMPBIN](../../build/reference/dumpbin-reference.md) pour obtenir la forme décorée d'un identificateur lorsque vous devez le spécifier à l'éditeur de liens.  Pour plus d'informations sur les noms décorés, consultez [Noms décorés](../../build/reference/decorated-names.md).  
  
 Si plusieurs spécifications \/ORDER sont utilisées, la dernière spécifiée est appliquée.  
  
 Le classement vous permet d'optimiser le comportement d'échange de votre programme par le biais du réglage de l'échange en regroupant une fonction avec la fonction appelée.  Vous pouvez également regrouper les fonctions appelées fréquemment.  Ces techniques augmentent la probabilité selon laquelle une fonction appelée est en mémoire si nécessaire et n'aura pas besoin d'être échangée à partir du disque.  
  
 L'éditeur de liens ajoutera un trait de soulignement \(\_\) à chaque nom décoré dans l'argument *filename*, sauf si le nom commence par un point d'interrogation \(?\) ou un signe \(@\).  Par exemple, si un fichier objet contient `extern "C" int func(int)` et `int main(void)`, DUMPBIN [\/SYMBOLS](../../build/reference/symbols.md) va répertorier ces noms décorés :  
  
```  
009 00000000 SECT3  notype ()    External     | _func  
00A 00000008 SECT3  notype ()    External     | _main  
```  
  
 Toutefois, le nom spécifié dans le fichier d'ordres doit être `func` et `main`.  
  
 L'option \/ORDER désactive les liens incrémentiels.  
  
> [!NOTE]
>  LINK ne peut pas classer les fonctions statiques car les noms de fonctions statiques ne sont pas des noms de symboles publics.  Lorsque \/ORDER est spécifié, l'avertissement de l'éditeur de liens LNK4037 est généré pour chaque symbole, dans le fichier d'ordres, qui est soit statique, soit introuvable.  
  
### Pour définir cette option de l'éditeur de liens dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, consultez [Définition des propriétés de projets Visual C\+\+](../../ide/working-with-project-properties.md).  
  
2.  Cliquez sur le dossier **Éditeur de liens**.  
  
3.  Cliquez sur la page de propriétés **Optimisation**.  
  
4.  Modifiez la propriété **Ordre des fonctions**.  
  
### Pour définir cette option de l'éditeur de liens par programme  
  
-   Consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.FunctionOrder%2A>.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)