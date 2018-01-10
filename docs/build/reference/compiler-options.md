---
title: Options du compilateur | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- cl.exe compiler
- IPF Visual C++ compiler
- Itanium Visual C++ compiler
- compiler options, C++
- x64 Visual C++ compiler
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c433abea04ff81c69fe1b73569ea7e043e6e81ac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-options"></a>Options du compilateur
CL.exe est un outil qui contrôle les compilateurs Microsoft C et C++ et l’éditeur de liens. CL.exe peut être exécuté uniquement sur les systèmes d’exploitation qui prennent en charge de Microsoft Visual Studio.  
  
> [!NOTE]
>  Vous pouvez démarrer cet outil uniquement à partir de l'invite de commandes [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)]. Vous ne pouvez pas le démarrer à partir d'une invite de commandes système ni de l'Explorateur de fichiers.  
  
 Les compilateurs génèrent des fichiers objets (.obj) de fichier Format COFF (Common Object). L’éditeur de liens génère des fichiers exécutables (.exe) ou des bibliothèques de liens dynamiques (DLL).  
  
 Notez que toutes les options du compilateur respectent la casse.  
  
 Pour compiler sans liaison, utilisez [/c](../../build/reference/c-compile-without-linking.md).  
  
## <a name="finding-an-option"></a>Recherche d’une Option  
 Pour rechercher une option du compilateur particulier, consultez une des listes suivantes :  
  
-   [Options du compilateur classées par ordre alphabétique](../../build/reference/compiler-options-listed-alphabetically.md)  
  
-   [Options du compilateur classées par catégorie](../../build/reference/compiler-options-listed-by-category.md)  
  
## <a name="specifying-options"></a>Spécification des Options  
 Pour chaque option du compilateur explique comment elle peut être définie dans l’environnement de développement. Pour plus d’informations sur la spécification des options à l’extérieur de l’environnement de développement, consultez :  
  
-   [Syntaxe de la ligne de commande du compilateur](../../build/reference/compiler-command-line-syntax.md)  
  
-   [Fichiers de commandes CL](../../build/reference/cl-command-files.md)  
  
-   [Variables d’environnement CL](../../build/reference/cl-environment-variables.md)  
  
## <a name="related-build-tools"></a>Outils de génération connexes  
 Utilisez [NMAKE](../../build/nmake-reference.md) pour générer le fichier de sortie.  
  
 Utilisez [BSCMAKE](../../build/reference/bscmake-reference.md) pour prendre en charge l’exploration des classes.  
  
 [Options de l’éditeur de liens](../../build/reference/linker-options.md) affectent également la manière dont votre programme est généré.  
  
## <a name="see-also"></a>Voir aussi  
 [Référence à la génération C/C++](../../build/reference/c-cpp-building-reference.md)   
 [Définition des Options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Compilation rapide](../../build/reference/fast-compilation.md)   
 [CL appelle l’éditeur de liens](../../build/reference/cl-invokes-the-linker.md)