---
title: "CL appelle l&#39;&#201;diteur de liens | Microsoft Docs"
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
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cl.exe (compilateur C++), compiler sans édition des liens"
  - "cl.exe (compilateur C++), contrôler l'éditeur de liens"
  - "compiler le code source (C++), sans liaison"
  - "appeler l'éditeur de liens à partir du compilateur"
  - "LINK (outil C++), appeler à partir du compilateur CL"
ms.assetid: eae47ef7-09eb-40c9-b318-7c714cd452fc
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# CL appelle l&#39;&#201;diteur de liens
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CL appelle automatiquement l'éditeur de liens à l'issue de la compilation, sauf si l'option \/c est utilisée.  CL passe à l'éditeur de liens les noms des fichiers .obj créés pendant la compilation et le nom de tout autre fichier spécifié sur la ligne de commande.  L'éditeur de liens utilise les options énumérées dans la variable d'environnement LINK.  Vous pouvez utiliser l'option \/link pour spécifier des options de l'éditeur de liens sur la ligne de commande CL.  Les options qui suivent l'option \/link substituent celles qui se trouvent dans la variable d'environnement LINK.  Les options contenues dans le tableau suivant suppriment la liaison.  
  
|Option|Description|  
|------------|-----------------|  
|\/c|Compilation sans liaison|  
|\/E, \/EP, \/P|Prétraitement sans compilation ni liaison|  
|\/Zg|Génération de prototypes de fonctions|  
|\/Zs|Contrôle de la syntaxe|  
  
 Pour plus d'informations sur la liaison, consultez [Options de l'éditeur de liens](../../build/reference/linker-options.md).  
  
## Exemple  
 Supposons que vous compiliez trois fichiers sources C : MAIN.c, MOD1.c et MOD2.c.  Chaque fichier inclut un appel à une fonction définie dans un autre fichier :  
  
-   MAIN.c appelle la fonction `func1` dans MOD1.c et la fonction `func2` dans MOD2.c.  
  
-   MOD1.c appelle les fonctions de bibliothèque standard `printf_s` et `scanf_s`.  
  
-   MOD2.c appelle les fonctions graphiques nommées `myline` et `mycircle`, qui sont définies dans une bibliothèque nommée MYGRAPH.lib.  
  
 Pour générer ce programme, compilez à l'aide de la ligne de commande suivante :  
  
```  
CL MAIN.c MOD1.C MOD2.C MYGRAPH.lib  
```  
  
 CL compile d'abord les fichiers sources C et crée les fichiers objets MAIN.obj, MOD1.obj et MOD2.obj.  Le compilateur place le nom de la bibliothèque standard dans chaque fichier .obj.  Pour plus d'informations, consultez [Utiliser la bibliothèque runtime](../../build/reference/md-mt-ld-use-run-time-library.md).  
  
 CL passe les noms des fichiers .obj, ainsi que le nom MYGRAPH.lib, à l'éditeur de liens.  L'éditeur de liens résout les références externes de la façon suivante :  
  
1.  Dans MAIN.obj, la référence à `func1` est résolue à l'aide de la définition dans MOD1.obj ; la référence à `func2` est résolue à l'aide de la définition dans MOD2.obj.  
  
2.  Dans MOD1.obj, les références à `printf_s` et `scanf_s` sont résolues à l'aide des définitions contenues dans la bibliothèque que l'éditeur de liens trouve nommée dans MOD1.obj.  
  
3.  Dans MOD2.obj, les références à `myline` et `mycircle` sont résolues à l'aide des définitions contenues dans MYGRAPH.lib.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)