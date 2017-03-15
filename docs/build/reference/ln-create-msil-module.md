---
title: "/LN (Cr&#233;er le module MSIL) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "/LN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/LN (option du compilateur C++)"
  - "-LN (option du compilateur C++)"
ms.assetid: 4f38f4f4-3176-4caf-8200-5c7585dc1ed3
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# /LN (Cr&#233;er le module MSIL)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Indique qu'un manifeste d'assembly ne doit pas être inséré dans le fichier de sortie.  
  
## Syntaxe  
  
```  
/LN  
```  
  
## Notes  
 Par défaut, :**\/LN** n'est pas activé \(un manifeste d'assembly est inséré dans le fichier de sortie\).  
  
 Lorsque **\/LN** est utilisé, l'une des options [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md) doit également être employée.  
  
 Un programme managé qui ne possède pas de métadonnées d'assembly dans le manifeste est appelé module.  Si vous compilez avec [\/c \(Compiler sans liaison\)](../../build/reference/c-compile-without-linking.md) et **\/LN**, spécifiez [\/NOASSEMBLY \(Créer un module MSIL\)](../../build/reference/noassembly-create-a-msil-module.md) dans la phase de l'éditeur de liens pour créer le fichier de sortie.  
  
 Vous pouvez créer des modules si vous souhaitez utiliser une approche basée sur les composants pour générer des assemblys.  Cela signifie que vous pouvez créer des types et les compiler dans des modules.  Ensuite, vous pouvez générer un assembly à partir d'un ou plusieurs modules.  Pour plus d'informations sur la création d'assemblys à partir de modules, consultez [Fichiers .netmodule en tant qu'entrée de l'Éditeur de liens](../../build/reference/netmodule-files-as-linker-input.md) ou [Al.exe \(Assembly Linker\)](../Topic/Al.exe%20\(Assembly%20Linker\).md).  
  
 L'extension de fichier par défaut pour un module de code est .netmodule.  
  
 Dans les versions de [!INCLUDE[vcprvc](../../build/includes/vcprvc_md.md)] antérieures à  Visual C\+\+ 2005, un module a été créé avec **\/clr:noAssembly**.  
  
 L'éditeur de liens Visual C\+\+ reçoit des fichiers .netmodule en entrée et le fichier de sortie produit par l'éditeur de liens sera un assembly ou un .netmodule sans dépendance au moment de l'exécution sur tout .netmodules qui ont été reliés en entrée à l'éditeur de liens.  Pour plus d'informations, consultez [Fichiers .netmodule en tant qu'entrée de l'Éditeur de liens](../../build/reference/netmodule-files-as-linker-input.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
-   Spécifiez [\/NOASSEMBLY \(Créer un module MSIL\)](../../build/reference/noassembly-create-a-msil-module.md) dans la phase de l'éditeur de liens pour créer le fichier de sortie.  
  
### Pour définir cette option du compilateur par programmation  
  
-   Cette option du compilateur ne peut pas être modifiée par programme.  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)