---
title: "Fichiers PCH utilis&#233;s dans le processus de g&#233;n&#233;ration | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "pch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .pch, processus de génération"
  - "makefiles, fichiers PCH dans le processus de génération"
  - "fichiers PCH, processus de génération"
ms.assetid: ebb4b368-8a11-4009-b347-01e79af02fbc
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Fichiers PCH utilis&#233;s dans le processus de g&#233;n&#233;ration
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La base de code d'un projet de logiciel est généralement contenue dans plusieurs fichiers source, fichiers objets, bibliothèques et fichiers d'en\-tête C ou C\+\+.  En principe, un makefile coordonne la combinaison de ces éléments en un makefile exécutable.  La figure suivante représente la structure d'un makefile qui utilise un fichier d'en\-tête précompilé.  Les noms des macros NMAKE et des fichiers dans ce diagramme sont cohérents avec ceux de l'exemple de code utilisé dans [Exemple de makefile pour PCH](../../build/reference/sample-makefile-for-pch.md) et [Exemple de code pour PCH](../../build/reference/example-code-for-pch.md).  
  
 La figure utilise trois éléments pour représenter schématiquement le flux du processus de génération.  Les rectangles nommés représentent chaque fichier ou macro ; les trois macros correspondent à un ou plusieurs fichiers.  Les zones ombrées représentent chaque action de compilation ou de liaison.  Les flèches montrent les fichiers et les macros qui sont combinés pendant le processus de compilation ou de liaison.  
  
 ![Makefile utilisant un fichier d'en&#45;tête précompilé](../../build/reference/media/vc30ow1.png "vc30OW1")  
Structure d'un makefile utilisant un fichier d'en\-tête précompilé  
  
 En haut du diagramme, STABLEHDRS et BOUNDRY sont des macros NMAKE dans lesquelles vous répertoriez les fichiers qui n'exigeront probablement pas une recompilation.  Ces fichiers sont compilés à l'aide de la chaîne de commande  
  
```  
CL /c /W3 /Yc$(BOUNDRY) applib.cpp myapp.cpp  
```  
  
 seulement si le fichier d'en\-tête précompilé \(STABLE.pch\) n'existe pas ou si vous apportez des modifications aux fichiers listés dans les deux macros.  Dans les deux cas, le fichier d'en\-tête précompilé contiendra uniquement du code provenant des fichiers indiqués dans la macro STABLEHDRS.  Indiquez dans la macro BOUNDRY le dernier fichier que vous souhaitez précompiler.  
  
 Les fichiers que vous spécifiez dans ces macros peuvent être soit des fichiers d'en\-tête,soit des fichiers source C ou C\+\+. \(Un même fichier .pch ne peut pas être utilisé avec des modules à la fois C et C\+\+.\) Notez que vous pouvez utiliser la macro **hdrstop** pour arrêter la précompilation à un point donné dans le fichier BOUNDRY.  Pour plus d'informations, consultez [hdrstop](../../preprocessor/hdrstop.md).  
  
 Plus bas dans le diagramme, APPLIB.obj représente le code de prise en charge utilisé dans l'application finale.  Il est créé à partir de APPLIB.cpp, des fichiers listés dans la macro UNSTABLEHDRS et du code précompilé à partir de l'en\-tête précompilé.  
  
 MYAPP.obj représente l'application finale.  Il est créé à partir de MYAPP.cpp, des fichiers listés dans la macro UNSTABLEHDRS et du code précompilé à partir de l'en\-tête précompilé.  
  
 Enfin, le fichier exécutable \(MYAPP.EXE\) est créé par la liaison des fichiers spécifiés dans la macro OBJS \(APPLIB.obj et MYAPP.obj\).  
  
 Pour une description supplémentaire de la figure, consultez :  
  
-   [Exemple de makefile pour PCH](../../build/reference/sample-makefile-for-pch.md)  
  
-   [Exemple de code pour PCH](../../build/reference/example-code-for-pch.md)  
  
## Voir aussi  
 [Utilisation d'en\-têtes précompilés dans un projet](../../build/reference/using-precompiled-headers-in-a-project.md)