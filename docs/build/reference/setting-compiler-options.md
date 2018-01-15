---
title: "Définition des Options du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- compiler options, setting
- cl.exe compiler, setting options
ms.assetid: 4b079f5b-0017-4124-aad6-0d2b58e427e0
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dbbc7111ceae2353e8bc9820ead319556ce0016b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="setting-compiler-options"></a>Définition des options du compilateur
Les options de compilateur C et C++peuvent être définies dans l'environnement de développement ou sur la ligne de commande.  
  
## <a name="in-the-development-environment"></a>Dans l'environnement de développement  
 Vous pouvez définir les options du compilateur pour chaque projet dans son **Pages de propriétés** boîte de dialogue. Dans le volet gauche, sélectionnez **propriétés de Configuration**, **C/C++** , puis choisissez la catégorie d’options du compilateur. La rubrique relative à chaque option de compilateur explique comment définir cette dernière et où la trouver dans l'environnement de développement. Consultez [Options du compilateur](../../build/reference/compiler-options.md) pour une liste complète.  
  
## <a name="outside-the-development-environment"></a>En dehors de l'environnement de développement  
 Vous pouvez définir les options de compilateur (CL.exe) :  
  
-   [Sur la ligne de commande](../../build/reference/compiler-command-line-syntax.md)  
  
-   [Dans les fichiers de commandes](../../build/reference/cl-command-files.md)  
  
-   [Dans la variable d’environnement CL](../../build/reference/cl-environment-variables.md)  
  
 Les options spécifiées dans la variable d'environnement CL sont utilisées chaque fois qu'elle est appelée. Si un fichier de commandes est nommé dans la variable d'environnement CL ou sur la ligne de commande, les options qu'il spécifie sont utilisées. Contrairement à la ligne de commande ou à la variable d'environnement CL, un fichier de commandes vous permet d'utiliser plusieurs lignes d'options et de noms de fichiers.  
  
 Les options de compilateur sont traitées de « gauche à droite », et quand un conflit est détecté, la dernière option (la plus à droite) est celle qui prévaut. La variable d'environnement CL est traitée avant la ligne de commande, de sorte qu'en cas de conflit entre CL et la ligne de commande, c'est cette dernière qui est prioritaire.  
  
## <a name="additional-compiler-topics"></a>Rubriques supplémentaires relatives au compilateur  
  
-   [Compilation rapide](../../build/reference/fast-compilation.md)  
  
-   [CL appelle l’éditeur de liens](../../build/reference/cl-invokes-the-linker.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Référence à la génération C/C++](../../build/reference/c-cpp-building-reference.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)